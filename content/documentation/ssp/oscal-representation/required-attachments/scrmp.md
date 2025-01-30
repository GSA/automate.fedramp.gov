---
title: Supply Chain Risk Management Plan (SCRMP)
weight: 140
---
# Supply Chain Risk Management Plan (SCRMP)

FedRAMP does not provide a template for the Supply Chain Risk Management Plan, however all FedRAMP OSCAL SSPs must include it as attachment using the same approach for creating [Attachments in OSCAL Content](/documentation/general-concepts/oscal-attachments/).  The key differences are that:
- the Supply Chain Risk Management Plan `back-matter` `resource`s must have a "type" `prop` with its `value` set to "plan" and `class` equal to "supply-chain-risk-management-plan"
- the Supply Chain Risk Management Plan `back-matter` `resource`s should have "published" `prop` that captures when the document was (last) published
- If provided, the "published" `prop` value must match the lexical form of the 'date-time-with-timezone' data type (e.g., 2025-01-01T00:00:00Z).
- Any specified `rlink` must be resolvable and accessible by FedRAMP

#### Representation: Supply Chain Risk Management Plan Back Matter Resource
{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "system-security-plan": {
        "uuid": "11111111-2222-4000-8000-000000000000",
        "back-matter": {
            "resources": [
                {
                    "uuid": "11111111-2222-4000-8000-001000000049",
                    "title": "Supply Chain Risk Management Plan",
                    "description": "Supply Chain Risk Management Plan",
                    "props": [
                        {
                            "name": "type",
                            "value": "plan",
                            "class": "supply-chain-risk-management-plan"
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
                        {"href": "./attachments/plans/sample_SCRMP_procedure.pdf"}
                    ],
                    "base64": {
                        "filename": "sample_SCRMP.pdf",
                        "media-type": "application/pdf",
                        "value": "00000000"
                    },
                    "remarks": "Table 12-1 Attachments: Procedure Attachment\n\nMay use `rlink` with a relative path, or embedded as `base64`."
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
        <resource uuid="11111111-2222-4000-8000-001000000049">
            <title>Supply Chain Risk Management Plan</title>
            <description>
                <p>Supply Chain Risk Management Plan</p>
            </description>
            <prop name="type" value="plan" class="supply-chain-risk-management-plan"/>
            <prop name="published" value="2023-01-01T00:00:00Z"/>
            <prop name="version" value="Document Version"/>
            <rlink href="./attachments/plans/sample_SCRMP_procedure.pdf"/>
            <base64 filename="sample_SCRMP.pdf" media-type="application/pdf">00000000</base64>
            <remarks>
                <p>Table 12-1 Attachments: Procedure Attachment</p>
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
    - uuid: 11111111-2222-4000-8000-001000000049
      title: Supply Chain Risk Management Plan
      description: Supply Chain Risk Management Plan
      props:
      - name: type
        value: plan
        class: supply-chain-risk-management-plan
      - name: published
        value: '2023-01-01T00:00:00Z'
      - name: version
        value: Document Version
      rlinks:
      - href: ./attachments/plans/sample_SCRMP_procedure.pdf
      base64:
        filename: sample_SCRMP.pdf
        media-type: application/pdf
        value: '00000000'
      remarks: |-
        Table 12-1 Attachments: Procedure Attachment

        May use `rlink` with a relative path, or embedded as `base64`.
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


{{<callout>}}
**NOTE**

- The Supply Chain Risk Management Plan must be associated with SR-2 part (a).
- CSPs should create a `component` for the Supply Chain Risk Management Plan so it can be referenced via a `by-component` assembly in the control implementation statement for SR-2 part (a). Follow the same approach as [Policies and Procedures](/documentation/ssp/oscal-representation/required-attachments/policies-and-procedures) attachments.
{{</callout>}}