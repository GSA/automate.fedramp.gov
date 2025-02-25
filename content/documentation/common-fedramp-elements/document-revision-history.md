---
title: Document Revision History
weight: 305
---

# Document Revision History

The OSCAL revision history requires one FedRAMP extension to meet FedRAMP's revision history requirements.

{{< figure src="/img/content-figure-8.png" title="Document revision history in a FedRAMP template" alt="Screenshot of document revision history information in the FedRAMP template." >}}

The revision history's author information is derived from FedRAMP's `party-uuid` flag, which points to a metadata `party` UUID value.

{{<callout>}}
**FedRAMP Revision Author** \
`<prop ns="http://fedramp.gov/ns/oscal" name="party-uuid" value="[party-uuid-value]"/>`
{{</callout>}}

The `published` field accepts the NIST OSCAL data type format. For details, see [date-time-with-timezone](https://pages.nist.gov/metaschema/specification/datatypes/#date-time-with-timezone) on the NIST website.

{{<callout>}}
*Note:* FedRAMP OSCAL requires only the publication date, not the time. You may replace the time portion with all zeros.\
FedRAMP tools should present only the date in a user-friendly format.
{{</callout>}}

The `remarks` field is a Markup multiline format, which enables formatting of text and requires special handling.\
For details, see [markup-line and markup-multiline Fields in OSCAL](/documentation/general-concepts/oscal-data-types/#markup-line-and-markup-multiline-fields-in-oscal) 
and [NIST markup-multiline](https://pages.nist.gov/metaschema/specification/datatypes/#markup-multiline).


## Representation

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        "revisions": [
            {
                "published": "2025-03-30T00:00:00Z",
                "version": "1.0",
                "oscal-version": "1.1.3",
                "props": [
                    {
                        "name": "party-uuid",
                        "ns": "http://fedramp.gov/ns/oscal",
                        "value": "9f411fde-00b2-45b4-8043-129da20ce6dd"
                    }
                ],
                "remarks": "Initial publication."
            }
        ],

        "roles": [
            {
                "id": "prepared-by",
                "title": "Prepared By",
                "description": "Cloud Service Provider"
            },
        ],

        "parties": [
            {
                "uuid": "9f411fde-00b2-45b4-8043-129da20ce6dd",
                "type": "organization",
                "name": "Cloud Service Provider"
            }
        ],

        "responsible-parties": [
            {
                "role-id": "cloud-service-provider",
                "party-uuids": ["9f411fde-00b2-45b4-8043-129da20ce6dd"]
            },
            {
                "role-id": "prepared-by",
                "party-uuids": ["9f411fde-00b2-45b4-8043-129da20ce6dd"]
            },
        ],
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
metadata:
  revisions:
  - published: '2025-03-30T00:00:00Z'
    version: '1.0'
    oscal-version: '1.1.3'
    props:
    - name: party-uuid
      ns: http://fedramp.gov/ns/oscal
      value: 9f411fde-00b2-45b4-8043-129da20ce6dd
    remarks: Initial publication.

    roles:
    - id: prepared-by
      title: Prepared By
      description: Cloud Service Provider

    parties:
    - uuid: 9f411fde-00b2-45b4-8043-129da20ce6dd
      type: organization
      name: Cloud Service Provider

    responsible-parties:
    - role-id: cloud-service-provider
      party-uuids:
      - 9f411fde-00b2-45b4-8043-129da20ce6dd
    - role-id: prepared-by
      party-uuids:
      - 9f411fde-00b2-45b4-8043-129da20ce6dd
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <revisions>
        <revision>
            <published>2025-03-30T00:00:00Z</published>
            <version>1.0</version>
            <oscal-version>1.1.3</oscal-version>
            <prop ns="http://fedramp.gov/ns/oscal" name="party-uuid" value="9f411fde-00b2-45b4-8043-129da20ce6dd"/>
            <remarks>
                <p>Initial publication.</p>
            </remarks>
        </revision>
    </revisions>

    <role id="prepared-by">
      <title>Prepared By</title>
      <description>
        <p>Cloud Service Provider</p>
      </description>
    </role>

    <party uuid="9f411fde-00b2-45b4-8043-129da20ce6dd" type="organization">
        <name>Cloud Service Provider</name>
    </party>

    <responsible-party role-id="cloud-service-provider">
        <party-uuid>9f411fde-00b2-45b4-8043-129da20ce6dd</party-uuid>
    </responsible-party>
    <responsible-party role-id="prepared-by">
        <party-uuid>9f411fde-00b2-45b4-8043-129da20ce6dd</party-uuid>
    </responsible-party>
</metadata>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


## XPath Queries

{{<callout>}}
*Note:* To locate information for a specific revision, replace `[1]` with `[2]`, `[3]`, and so on.
{{</callout>}}

| Item                                  | XPath&nbsp;query                                                                                                                                |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Number of revision entries            | `count(/*/metadata/revision-history/revision)`                                                                                                  |
| Revision date for an individual entry | `/*/metadata/revision-history/revision[1]/published`                                                                                            |
| Description of an individual entry    | `/*/metadata/revision-history/revision[1]/remarks/string()`                                                                                     |
| Version of an individual entry        | `/*/metadata/revision-history/revision[1]/version`                                                                                              |
| Author of an individual entry         | `/*/metadata/party[@uuid=/*/metadata/revision-history/revision[1]/prop [@name='party-uuid'][@ns='http://fedramp.gov/ns/oscal']]/org/short-name` |

