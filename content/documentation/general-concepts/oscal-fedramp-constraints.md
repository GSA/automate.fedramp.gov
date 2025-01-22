---
title: FedRAMP Constraints Browser
---
# Fedramp Constraints

<div>
    <input type="text" id="searchInput" placeholder="Search constraints...">
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
            allConstraints=([constraints,allowedValues].flatMap(x=>x["metaschema-meta-constraints"]).flatMap(x=>x["contexts"]).flatMap(x=>x.constraints).flatMap(x=>x.rules)).filter(x=>typeof x.id!='undefined').sort((a,b)=>a.id.localeCompare(b.id));
            displayConstraints(filterConstraints(allConstraints, searchTerm));
            
            if (selectedId) {
                $(`#${selectedId}`).addClass('selected');
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
                    });

                $div.append(
                    $('<h3>').text(item['formal-name']),
                    $('<span>').text(item['id']),
                    $('<p>').text(item['message']),
                    $('<pre style="white-space:pre-line">').text(item['test']),
                    $('<p>').text(item.description),
                    item['props']&&$('<a>').text("learn more").attr('href',item['props'].find(x=>x.name==='help-url').value),
                );

                if (item['object-type'] === 'allowed-values' && item.enums) {
                    const $enumDiv = $('<div style="white-space:pre-line">');
                    $enumDiv.append($('<h4>').text('Allowed Values:'));
                    
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
            if (selectedId) {
                $(`#${selectedId}`).addClass('selected');
            }
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
    #searchInput {
        width: 100%;
        padding: 5px;
        margin-bottom: 10px;
    }
    ul {
        margin: 5px 0;
        padding-left: 20px;
    }
</style>