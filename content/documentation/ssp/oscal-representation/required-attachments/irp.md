---
title: Incident Response Plan (IRP)
weight: 125
---
# Incident Response Plan (IRP)

FedRAMP does not provide a template for the Incident Response Plan (IRP), however, all FedRAMP OSCAL SSPs must include a Incident Response Plan attachment using the same approach for creating [Attachments in OSCAL Content](/documentation/general-concepts/oscal-attachments/).  The key differences are that:
- the Incident Response Plan `back-matter` `resource`s must have a "type" `prop` with its `value` set to "plan" and `class` equal to "incident-response-plan"
- the Incident Response Plan `back-matter` `resource`s should have "published" `prop` that captures when the document was (last) published
- If provided, the "published" `prop` value must match the lexical form of the 'date-time-with-timezone' data type (e.g., 2025-01-01T00:00:00Z).
- Any specified `rlink` must be resolvable and accessible by FedRAMP

#### Representation: Incident Response Plan Back Matter Resource
{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "system-security-plan": {
        "uuid": "11111111-2222-4000-8000-000000000000",
        "back-matter": {
            "resources": [
                {
                    "uuid": "11111111-2222-4000-8000-001000000045",
                    "title": "Document Title",
                    "description": "Incident Response (IR) Plan",
                    "props": [
                        {
                            "name": "type",
                            "value": "plan",
                            "class": "incident-response-plan"
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
                            "href": "./attachments/IR_Plan.docx",
                            "media-type": "application/msword"
                        }
                    ],
                    "base64": {
                        "filename": "IR_Plan.docx",
                        "media-type": "application/msword",
                        "value": "00000000"
                    },
                    "remarks": "Table 12-1 Attachments: Incident Response (IR) Plan Attachment\n\nMay use `rlink` with a relative path, or embedded as `base64`."
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
        <resource uuid="11111111-2222-4000-8000-001000000045">
            <title>Document Title</title>
            <description>
                <p>Incident Response (IR) Plan</p>
            </description>
            <prop name="type" value="plan" class="incident-response-plan"/>
            <prop name="published" value="2023-01-01T00:00:00Z"/>
            <prop name="version" value="Document Version"/>
            <rlink href="./attachments/IR_Plan.docx" media-type="application/msword"/>
            <base64 filename="IR_Plan.docx" media-type="application/msword">00000000</base64>
            <remarks>
                <p>Table 12-1 Attachments: Incident Response (IR) Plan Attachment</p>
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
    - uuid: 11111111-2222-4000-8000-001000000045
      title: Document Title
      description: Incident Response (IR) Plan
      props:
      - name: type
        value: plan
        class: incident-response-plan
      - name: published
        value: '2023-01-01T00:00:00Z'
      - name: version
        value: Document Version
      rlinks:
      - href: ./attachments/IR_Plan.docx
        media-type: application/msword
      base64:
        filename: IR_Plan.docx
        media-type: application/msword
        value: '00000000'
      remarks: |-
        Table 12-1 Attachments: Incident Response (IR) Plan Attachment

        May use `rlink` with a relative path, or embedded as `base64`.
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


{{<callout>}}
**NOTE**

- The Incident Response Plan must be associated with IR-8 part (a).
- CSPs should create a `component` for the Incident Response Plan so it can be referenced via a `by-component` assembly in the control implementation statement for IR-8 part (a). Follow the same approach as [Policies and Procedures](/documentation/ssp/oscal-representation/required-attachments/policies-and-procedures) attachments.
{{</callout>}}