---
title: Information System Contingency Plan (ISCP)
weight: 115
---
# Information System Contingency Plan (ISCP)

FedRAMP has a [template for the Information System Contingency Plan (ISCP)](https://www.fedramp.gov/assets/resources/templates/SSP-Appendix-G-Information-System-Contingency-Plan-(ISCP)-Template.docx).  All FedRAMP OSCAL SSPs must include a Contingency Plan attachment  using the same approach for creating [Attachments in OSCAL Content](/documentation/general-concepts/oscal-attachments/).  The key differences are that:
- the Contingency Plan `back-matter` `resource`s must have a "type" `prop` with its `value` set to "plan" and `class` equal to "information-system-contingency-plan"
- the Contingency Plan `back-matter` `resource`s should have "published" `prop` that captures when the document was (last) published
- If provided, the "published" `prop` value must match the lexical form of the 'date-time-with-timezone' data type (e.g., 2025-01-01T00:00:00Z).
- Any specified `rlink` must be resolvable and accessible by FedRAMP

#### Representation: Contingency Plan Back Matter Resource
{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "system-security-plan": {
        "uuid": "11111111-2222-4000-8000-000000000000",
        "back-matter": {
            "resources": [
                {
                    "uuid": "11111111-2222-4000-8000-001000000043",
                    "title": "Document Title",
                    "description": "Contingency Plan (CP)",
                    "props": [
                        {
                            "name": "type",
                            "value": "plan",
                            "class": "information-system-contingency-plan"
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
                            "href": "./attachments/cp.docx",
                            "media-type": "application/msword"
                        }
                    ],
                    "base64": {
                        "filename": "cp.docx",
                        "media-type": "application/msword",
                        "value": "00000000"
                    },
                    "remarks": "Table 12-1 Attachments: Contingency Plan (CP) Attachment\n\nMay use `rlink` with a relative path, or embedded as `base64`."
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
        <resource uuid="11111111-2222-4000-8000-001000000043">
            <title>Document Title</title>
            <description>
                <p>Contingency Plan (CP)</p>
            </description>
            <prop name="type" value="plan" class="information-system-contingency-plan"/>
            <prop name="published" value="2023-01-01T00:00:00Z"/>
            <prop name="version" value="Document Version"/>
            <rlink href="./attachments/cp.docx" media-type="application/msword"/>
            <base64 filename="cp.docx" media-type="application/msword">00000000</base64>
            <remarks>
                <p>Table 12-1 Attachments: Contingency Plan (CP) Attachment</p>
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
    - uuid: 11111111-2222-4000-8000-001000000043
      title: Document Title
      description: Contingency Plan (CP)
      props:
      - name: type
        value: plan
        class: information-system-contingency-plan
      - name: published
        value: '2023-01-01T00:00:00Z'
      - name: version
        value: Document Version
      rlinks:
      - href: ./attachments/cp.docx
        media-type: application/msword
      base64:
        filename: cp.docx
        media-type: application/msword
        value: '00000000'
      remarks: |-
        Table 12-1 Attachments: Contingency Plan (CP) Attachment

        May use `rlink` with a relative path, or embedded as `base64`.
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


{{<callout>}}
**NOTE**

- The Contingency Plan must be associated with CP-2 part (a).
- CSPs should create a `component` for the Contingency Plan so it can be referenced via a `by-component` assembly in the control implementation statement for CP-2 part (a). Follow the same approach as [Policies and Procedures](/documentation/ssp/oscal-representation/required-attachments/policies-and-procedures) attachments.
{{</callout>}}