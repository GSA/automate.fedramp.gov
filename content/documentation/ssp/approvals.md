---
title: Approvals
weight: 315
---
# Approvals

Typically, SSP documents are reviewed and approved by CSP executives. The screen shot below shows the document approval section in the FedRAMP SSP template.

{{< figure src="/img/content-figure-10.png" title="Document approvers in the FedRAMP SSP template" alt="Screenshot of document approvals information in the FedRAMP template." >}}


## Representation

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
        "metadata": {
            "roles": [
                {
                    "id": "content-approver",
                    "title": "Document Approval",
                    "description": "Individuals responsible for the accuracy of this document."
                },
                {
                    "id": "cloud-service-provider",
                    "title": "Cloud Service Provider",
                },
            ],
    
            "parties": [
                {
                    "uuid": "816b232b-d718-4999-a506-9832329d5faa",
                    "type": "organization",
                    "name": "Name of the CSP",
                },
                {
                    "uuid": "f8a45bc6-d9eb-41f9-a375-2345d161a12",
                    "type": "person",
                    "name": "Name of person 1",
                    "props": [
                        {
                            "name": "job-title",
                            "value": "Title of person 1"
                        },
                    ],
                    "member-of-organizations": ["816b232b-d718-4999-a506-9832329d5faa"],
                },
                {
                    "uuid": "d5fc263c-b32f-4caa-9454-01e74a39c97e",
                    "type": "person",
                    "name": "Name of person 2",
                    "props": [
                        {
                            "name": "job-title",
                            "value": "Title of person 2"
                        }
                    ],
                    "member-of-organizations": ["816b232b-d718-4999-a506-9832329d5faa"],
                },
            ],
    
            "responsible-parties": [
                {
                    "role-id": "cloud-service-provider",
                    "party-uuids": ["816b232b-d718-4999-a506-9832329d5faa"]
                },
                {
                    "role-id": "content-approver",
                    "party-uuids": [
                        "f8a45bc6-d9eb-41f9-a375-2345d161a12",
                        "d5fc263c-b32f-4caa-9454-01e74a39c97e"
                    ],
                },
            ]
        }
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
    metadata:
        roles:
        - id: content-approver
          title: Document Approval
          description: Individuals responsible for the accuracy of this document.
        - id: cloud-service-provider
          title: Cloud Service Provider
    
        parties:
        - uuid: 816b232b-d718-4999-a506-9832329d5faa
          type: organization
          name: 'Name of the CSP'
        - uuid: f8a45bc6-d9eb-41f9-a375-2345d161a12
          type: person
          name: 'Name of person 1'
          props:
          - name: job-title
            value: 'Title of person 1'
          member-of-organizations:
          - 816b232b-d718-4999-a506-9832329d5faa
        - uuid: d5fc263c-b32f-4caa-9454-01e74a39c97e
          type: person
          name: 'Name of person 2'
          props:
          - name: job-title
            value: 'Title of person 2'
          member-of-organizations:
          - 816b232b-d718-4999-a506-9832329d5faa
    
        responsible-parties:
        - role-id: cloud-service-provider
          party-uuids:
          - 816b232b-d718-4999-a506-9832329d5faa
        - role-id: content-approver
          party-uuids:
          - f8a45bc6-d9eb-41f9-a375-2345d161a12
          - d5fc263c-b32f-4caa-9454-01e74a39c97e
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan> 
    <metadata>
        <role id="content-approver">
            <title>Document Approval</title>
            <description>
                <p>Individuals responsible for the accuracy of this document.</p>
            </description>
        </role>
        <role id="cloud-service-provider">
            <title>Cloud Service Provider</title>
        </role>
        
        <party uuid="816b232b-d718-4999-a506-9832329d5faa" type="organization">
            <name>Name of the CSP</name>
        </party>
        <party uuid="f8a45bc6-d9eb-41f9-a375-2345d161a12c" type="person">
            <name>Name of person 1</name>
            <prop name="job-title" value="Title of person 1"/>
            <member-of-organization>816b232b-d718-4999-a506-9832329d5faa</member-of-organization>
        </party>
        <party uuid="d5fc263c-b32f-4caa-9454-01e74a39c97e" type="person">
            <name>Name of person 2</name>
            <prop name="job-title" value="Title of person 2"/>
            <member-of-organization>816b232b-d718-4999-a506-9832329d5faa</member-of-organization>
        </party>
        
        <responsible-party role-id="cloud-service-provider">
            <party-uuid>816b232b-d718-4999-a506-9832329d5faa</party-uuid>
        </responsible-party>
        <responsible-party role-id="content-approver">
            <party-uuid>f8a45bc6-d9eb-41f9-a375-2345d161a12c</party-uuid>
            <party-uuid>d5fc263c-b32f-4caa-9454-01e74a39c97e</party-uuid>
        </responsible-party>
    </metadata>
</system-security-plan>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

<br/>

{{<callout>}}
**Required Roles**\
1. `content-approver`
2. `cloud-service-provider`

**FedRAMP Extension for Person's Title** \
`<prop ns="http://fedramp.gov/ns/oscal" name="title">`
{{</callout>}}

## XPath Queries

| Item             | XPath&nbsp;query                                                                                                                                                                                                                                                                 |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Approver’s name  | `(/*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id='content-approver']/party-uuid]]/party-name)[1]`<br/>{{<callout>}}*Note:* For each additional approver, replace `[1]` with `[2]`, `[3]`, and so on.{{</callout>}}                                              |
| Approver’s title | `(/*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id='content-approver'] /party-uuid]]/prop[@name='title'][@ns='http://fedramp.gov/ns/oscal'])[1]`<br/>{{<callout>}}*Note:* For each additional approver, replace `[1]` with `[2]`, `[3]`, and so on.{{</callout>}} |
| CSP's name       | `/*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id='cloud-service-provider']/party-uuid]]/party-name`                                                                                                                                                              |

