---
title: Validation Rule Catalog
weight: 240
---
# Validation Rule Catalog

<div>
    <input type="text" id="searchInput" placeholder="Search constraints by ID, description, etc. ...">
</div>
<div id="constraintsList"></div>

<script>
    $(document).ready(function() {
        let allConstraints = [];
        let selectedId = new URLSearchParams(window.location.search).get('constraint-id');
        let searchTerm = new URLSearchParams(window.location.search).get('search') || '';

        // Set initial search value from URL
        $('#searchInput').val(searchTerm);

        // Load both JSON files
        Promise.all([
            $.getJSON('/json/fedramp_external_constraints.json'),
            $.getJSON('/json/fedramp_allowed_values.json')
        ]).then(function([constraints, allowedValues]) {
            // Process constraints while preserving context information
            allConstraints = [constraints, allowedValues]
                .flatMap(x => x["metaschema-meta-constraints"])
                .flatMap(metaConstraint => 
                    metaConstraint["contexts"].flatMap(context => 
                        context.constraints.rules.flatMap(rule => {
                            // Get all variables that are referenced in test or target
                            const referencedVars = new Set();
                            const varMap = new Map();
                            
                            // Create a map of variable names to their values
                            context.constraints.lets?.forEach(v => {
                                varMap.set(v.var, v.expression);
                            });

                            // Function to find variables in a string
                            function findVarsInString(str) {
                                const vars = new Set();
                                if (!str) return vars;
                                
                                // Match $varname or ${varname} patterns
                                const matches = str.match(/\$\{?([a-zA-Z0-9_-]+)\}?/g) || [];
                                matches.forEach(match => {
                                    const varName = match.replace(/[\$\{\}]/g, '');
                                    vars.add(varName);
                                });
                                return vars;
                            }

                            // Function to recursively find all referenced variables
                            function findAllReferencedVars(varName, visited = new Set()) {
                                console.log(varName);
if (visited.has(varName)) return;
                                visited.add(varName);
                                referencedVars.add(varName);

                                const value = varMap.get(varName);
                                console.log(varMap,varName);
                                if (value) {
                                    const nestedVars = findVarsInString(value);
                                    nestedVars.forEach(v => findAllReferencedVars(v, visited));
                                }
                            }
                            
                            const testVars = findVarsInString(rule.test);
                            const targetVars = findVarsInString(rule.target);
                            testVars.forEach(v => findAllReferencedVars(v));
                            targetVars.forEach(v => findAllReferencedVars(v));
                        
                            // Filter variables to only include referenced ones
                            const filteredVars = context.constraints.lets?.filter(v => referencedVars.has(v.var)) || [];
                            return {
                                ...rule,
                                contextMetapaths: context.metapaths,
                                contextName: context.name,
                                variables: filteredVars
                            };
                        })
                    )
                )
                .filter(x => typeof x.id !== 'undefined')
                .sort((a, b) => a.id.localeCompare(b.id));

            displayConstraints(filterConstraints(allConstraints, searchTerm));
            
            if (selectedId) {
                const $selectedElement = $(`#${selectedId}`);
                $selectedElement.addClass('selected');
                setTimeout(() => {
                    $selectedElement[0].scrollIntoView({ behavior: 'smooth', block: 'center' });
                }, 100);
            }

        });

        function filterConstraints(constraints, term) {
            if (!term) return constraints;
            term = term.toLowerCase();
            return constraints.filter(item => 
                item['formal-name']?.toLowerCase().includes(term) ||
                item['object-type']?.toLowerCase().includes(term) ||
                item['id']?.toLowerCase().includes(term) ||
                item['message']?.toLowerCase().includes(term) ||
                item['contextName']?.toLowerCase().includes(term) ||
                item['contextTarget']?.toLowerCase().includes(term) ||
                item.enums?.some(enumItem => enumItem.value?.toLowerCase().includes(term))
            );
        }

        function displayConstraints(constraints) {
            const $list = $('#constraintsList');
            $list.empty();

            constraints.forEach(function(item) {
                const $div = $('<div>')
                    .attr('id', item.id)
                    .addClass('constraint-item')
                    .click(function() {
                        $('.constraint-item').removeClass('selected');
                        $(this).addClass('selected');
                        selectedId = item.id;
                        updateURL();
                        // Smooth scroll to clicked element
                        this.scrollIntoView({ behavior: 'smooth', block: 'center' });
                    });

                $div.append(
                    $('<h3>').text(item['formal-name']),
                    $('<span>').text(item['id']),
                   
                );
                if(item['message']){
                    $div.append($('<h4>').text('Message'),
                    $('<p>').text(item['message']))
                }
                // Add context section with h4
                const $contextDiv = $('<div>').addClass('context-section');
                $contextDiv.append(
                    $('<h4>').text('Context'),
                );
 item.contextMetapaths.filter(Boolean).forEach(function(path) {
                        const $enumValue = $('<code style="padding:4px">').addClass('enum-value');
$contextDiv.append(
                   $enumValue.append(path.target),
                );                                   
                                    });
$div.append($contextDiv);

                // Add constraint section with h4
                const $constraintDiv = $('<div>').addClass('constraint-section');
 if(item['test']){
                  $constraintDiv.append("<h4>Test</h4>");
                  $constraintDiv.append($('<code style="white-space:pre-line">').text(item['test']))
                }
                if(item['target']&&item['target']!='.'){
                  $constraintDiv.append("<h4>Target</h4>");
                  $constraintDiv.append($('<code style="white-space:pre-line">').text(item['target']))
                }                $div.append($constraintDiv);

                // Add variables section with h4 if variables exist
                if (item.variables && item.variables.length > 0) {
                    const $variablesDiv = $('<div>').addClass('variables-section');
                    $variablesDiv.append($('<h4>').text('Variables'));
                    
                    const $variablesList = $('<ul>');
                    item.variables.forEach(function(variable) {
                        $variablesList.append(
                            $('<li>')
                                .append($('<pre>').text(variable.var))
                                .append($('<code style="white-space:pre-line">').text(variable.expression))
                        );
                    });
                    $variablesDiv.append($variablesList);
                    $div.append($variablesDiv);
                }

                if(item['description']){
                $div.append("<h4>Description</h4>");
                $div.append($('<p>').text(item.description));
                }             

                if (item['props']) {
                    $div.append($('<a>').text("learn more").attr('href', item['props'].find(x => x.name === 'help-url').value));
                }

                // Add allowed values section with h4 if they exist
                if (item['object-type'] === 'allowed-values' && item.enums) {
                    const $enumDiv = $('<div>').addClass('allowed-values-section');
                    $enumDiv.append($('<h4>').text('Allowed Values'));
                    
                    item.enums.forEach(function(enumItem) {
                        const $enumValue = $('<span style="padding:4px">').addClass('enum-value');
                        $enumValue.append($('<code>').text(enumItem.value));
                        $enumDiv.append($enumValue);
                    });
                    
                    $div.append($enumDiv);
                }

                $list.append($div);
            });
        }

        function updateURL() {
            const url = new URL(window.location);
            if (selectedId) url.searchParams.set('constraint-id', selectedId);
            if (searchTerm) url.searchParams.set('search', searchTerm);
            history.pushState({}, '', url);
        }

        $('#searchInput').on('input', function() {
            searchTerm = $(this).val();
            const filtered = filterConstraints(allConstraints, searchTerm);
            displayConstraints(filtered);
            updateURL();
        });
    });
</script>

<style>
    .constraint-item {
        margin: 10px 0;
        padding: 10px;
        border: 1px solid #ccc;
        cursor: pointer;
    }
    .constraint-item.selected {
        border-color: blue;
        background-color: #f0f0f0;
    }
    .constraint-item h3 {
        margin-top: 0;
    }
    .constraint-item h4 {
        margin: 10px 0 5px 0;
        color: #666;
    }    #searchInput {
        width: 100%;
        padding: 5px;
        margin-bottom: 10px;
    }
    code {
        background-color: #f5f5f5;
        padding: 2px 4px;
        border-radius: 3px;
    }
</style>
