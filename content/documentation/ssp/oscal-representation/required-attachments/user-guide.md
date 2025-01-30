---
title: User Guide
weight: 105
---
# User Guide

The CSP's User Guide helps explain (to agency customers) how to use the cloud service offering.  FedRAMP SSPs must include a User Guide, however, CSPs can either attach it as a static document or provide a URL reference if they have an online documentation website.  For OSCAL SSPs, the User Guide must specified as an SSP `back-matter` `resource`, similar to the overall general approach for creating [Attachments in OSCAL Content](/documentation/general-concepts/oscal-attachments/).   The key differences are that:
- User Guide `back-matter` `resource`s must have a "type" `prop` with its `value` set to "users-guide"
- User Guide `back-matter` `resource`s should have "published" `prop` that captures when the document was (last) published
- If provided, the "published" `prop` value must match the lexical form of the 'date-time-with-timezone' data type (e.g., 2025-01-01T00:00:00Z).
- Any specified `rlink` must be resolvable and accessible by FedRAMP

#### Representation: User Guide Back Matter Resource
{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "system-security-plan": {
        "uuid": "11111111-2222-4000-8000-000000000000",
        "back-matter": {
            "resources": [
                {
                    "uuid": "11111111-2222-4000-8000-001000000041",
                    "title": "User's Guide",
                    "description": "User's Guide",
                    "props": [
                        {
                            "name": "type",
                            "value": "users-guide"
                        },
                        {
                            "name": "published",
                            "value": "2023-01-01T00:00:00Z"
                        }
                    ],
                    "rlinks": [
                        {"href": "./attachments/guides/sample_guide.pdf"}
                    ],
                    "remarks": "Table 12-1 Attachments: User's Guide Attachment\n\nMay use `rlink` with a relative path, or embedded as `base64`."
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
        <resource uuid="11111111-2222-4000-8000-001000000041">
        <title>User's Guide</title>
        <description>
            <p>User's Guide</p>
        </description>
        <prop name="type" value="users-guide"/>
        <prop name="published" value="2023-01-01T00:00:00Z"/>
        <rlink href="./attachments/guides/sample_guide.pdf"/>
        <remarks>
            <p>Table 12-1 Attachments: User's Guide Attachment</p>
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
    - uuid: 11111111-2222-4000-8000-001000000041
      title: User's Guide
      description: User's Guide
      props:
      - name: type
        value: users-guide
      - name: published
        value: '2023-01-01T00:00:00Z'
      rlinks:
      - href: ./attachments/guides/sample_guide.pdf
      remarks: |-
        Table 12-1 Attachments: User's Guide Attachment
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


{{<callout>}}
**NOTE**

CSPs do not need to create a `component` for the User Guide unless they need to reference it (e.g., via a `by-component` assembly) in a control implementation statement. 
{{</callout>}}