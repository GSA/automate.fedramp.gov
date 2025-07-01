---
title: Rules of Behavior
weight: 110
---
# Rules of Behavior

FedRAMP has a [template for the Rules of Behavior](https://www.fedramp.gov/assets/resources/templates/SSP-Appendix-F-Rules-of-Behavior-(RoB)-Template.docx) document.  All FedRAMP OSCAL SSPs must include a Rules of Behavior attachment  using the same approach for creating [Attachments in OSCAL Content](/documentation/general-concepts/oscal-attachments/).  The key differences are that:
- Rules of Behavior `back-matter` `resource`s must have a "type" `prop` with its `value` set to "rules-of-behavior"
- Rules of Behavior `back-matter` `resource`s should have "published" `prop` that captures when the document was (last) published
- If provided, the "published" `prop` value must match the lexical form of the 'date-time-with-timezone' data type (e.g., 2025-01-01T00:00:00Z).
- Any specified `rlink` must be resolvable and accessible by FedRAMP

#### Representation: Rules of Behavior Back Matter Resource
{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "system-security-plan": {
        "uuid": "11111111-2222-4000-8000-000000000000",
        "back-matter": {
            "resources": [
                {
                    "uuid": "11111111-2222-4000-8000-001000000042",
                    "title": "Document Title",
                    "description": "Rules of Behavior",
                    "props": [
                        {
                            "name": "type",
                            "value": "rules-of-behavior"
                        },
                        {
                            "name": "published",
                            "value": "2023-01-01T00:00:00Z"
                        },
                        {
                            "name": "version",
                            "value": "Document Version"
                        }
                    ],
                    "rlinks": [
                        {
                            "href": "./attachments/rob.docx",
                            "media-type": "application/msword"
                        }
                    ],
                    "base64": {
                        "filename": "rob.docx",
                        "media-type": "application/msword",
                        "value": "00000000"
                    },
                    "remarks": "Table 12-1 Attachments: Rules of Behavior (ROB)\n\nMay use `rlink` with a relative path, or embedded as `base64`."
                }
            ]
        }
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan uuid="11111111-2222-4000-8000-000000000000">
	<back-matter>
        <resource uuid="11111111-2222-4000-8000-001000000042">
            <title>Document Title</title>
            <description>
                <p>Rules of Behavior</p>
            </description>
            <prop name="type" value="rules-of-behavior"/>
            <prop name="published" value="2023-01-01T00:00:00Z"/>
            <prop name="version" value="Document Version"/>
            <rlink href="./attachments/rob.docx" media-type="application/msword"/>
            <base64 filename="rob.docx" media-type="application/msword">00000000</base64>
            <remarks>
                <p>Table 12-1 Attachments: Rules of Behavior (ROB)</p>
                <p>May use <code>rlink</code> with a relative path, or embedded as <code>base64</code>.</p>
            </remarks>
        </resource>
	</back-matter>
</system-security-plan>
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
system-security-plan:
  back-matter:
    resources:
    - uuid: 11111111-2222-4000-8000-001000000042
      title: Document Title
      description: Rules of Behavior
      props:
      - name: type
        value: rules-of-behavior
      - name: published
        value: '2023-01-01T00:00:00Z'
      - name: version
        value: Document Version
      rlinks:
      - href: ./attachments/rob.docx
        media-type: application/msword
      base64:
        filename: rob.docx
        media-type: application/msword
        value: '00000000'
      remarks: |-
        Table 12-1 Attachments: Rules of Behavior (ROB)

        May use `rlink` with a relative path, or embedded as `base64`.
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


{{<callout>}}
**NOTE**

- The Rules of Behavior must be associated with PL-4 part (a).
- CSPs should create a `component` for the Rules of Behavior so it can be referenced via a `by-component` assembly in the control implementation statement for PL-4 part (a). Follow the same approach as [Policies and Procedures](/documentation/ssp/oscal-representation/required-attachments/policies-and-procedures) attachments.
{{</callout>}}