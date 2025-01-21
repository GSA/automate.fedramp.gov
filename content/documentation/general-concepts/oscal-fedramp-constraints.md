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

        // Load both JSON files
        Promise.all([
            $.getJSON('/json/fedramp_external_constraints.json'),
            $.getJSON('/json/fedramp_allowed_values.json')
        ]).then(function([constraints, allowedValues]) {
            allConstraints=([constraints,allowedValues].flatMap(x=>x["metaschema-meta-constraints"]).flatMap(x=>x["contexts"]).flatMap(x=>x.constraints).flatMap(x=>x.rules))
            console.log(allConstraints)
            displayConstraints(allConstraints);
            
            if (selectedId) {
                $(`#${selectedId}`).addClass('selected');
            }
        });

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
                        // Update URL
                        const url = new URL(window.location);
                        url.searchParams.set('constraint-id', selectedId);
                        history.pushState({}, '', url);
                    });

                // Title and type
                $div.append(
                    $('<h3>').text(item['formal-name']),
                    $('<span>').text(item['id']),
                    $('<pre>').text(item['test']),
                    $('<p>').text(item['message']),
                );

                // Description
                $div.append($('<p>').text(item.description));

                // Message for constraints
                if (item.type === 'constraint' && item.message) {
                    $div.append(
                        $('<p>').append(
                            $('<strong>').text('Message: '),
                            document.createTextNode(item.message)
                        )
                    );
                }

                // Enum values for allowed-values
                if (item.type === 'allowed-values' && item.enums) {
                    const $ul = $('<ul>');
                    item.enums.forEach(function(enumItem) {
                        $ul.append(
                            $('<li>').append(
                                $('<code>').text(enumItem.value),
                                enumItem.description ? 
                                    document.createTextNode(': ' + enumItem.description) : 
                                    ''
                            )
                        );
                    });
                    $div.append($('<p>').text('Allowed Values:'), $ul);
                }

                // Help URL
                if (item.helpUrl) {
                    $div.append(
                        $('<a>')
                            .attr('href', item.helpUrl)
                            .attr('target', '_blank')
                            .text('View Documentation')
                    );
                }

                $list.append($div);
            });
        }

        // Search functionality
        $('#searchInput').on('input', function(info) {
            console.log($(this).val());
            const searchTerm = (($(this).val())+"").toLowerCase();
            const filtered = allConstraints.filter(item => 
                item['formal-name']&&item['formal-name'].toLowerCase().includes(searchTerm) ||
                item['id']&&item['id'].toLowerCase().includes(searchTerm)||
                item['message']&&item['message'].toLowerCase().includes(searchTerm)

);
            console.log(filtered.length)
            displayConstraints(filtered);
            // Restore selection after filtering
            if (selectedId) {
                $(`#${selectedId}`).addClass('selected');
            }
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