---
title: Document Revision History
weight: 305
---

# Document Revision History

The OSCAL revision history requires one FedRAMP extension to meet FedRAMP's revision history requirements.

{{< figure src="/img/content-figure-8.png" title="Document revision history in a FedRAMP template" alt="Screenshot of document revision history information in the FedRAMP template." >}}

The revision history's author is populated from the FedRAMP's `party-uuid` flag, which points to a metadata `party` UUID value.

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
        // title, published, last-modified, version, oscal-version
        "revisions": [
            {
                "published": "2025-03-30T00:00:00Z",
                "version": "1.0",
                "oscal-version": "1.0.4",
                "props": [
                    {
                        "name": "party-uuid",
                        "ns": "http://fedramp.gov/ns/oscal",
                        "value": "11111111-2222-4000-8000-004000000001"
                    }
                ],
                "remarks": "Initial publication."
            }
        ]
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
metadata:
  # title, published, last-modified, version, oscal-version
  revisions:
  - published: '2025-03-30T00:00:00Z'
    version: '1.0'
    oscal-version: 1.0.4
    props:
    - name: party-uuid
      ns: http://fedramp.gov/ns/oscal
      value: 11111111-2222-4000-8000-004000000001
    remarks: Initial publication.
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- title, published, last-modified, version, oscal-version -->
    <revisions>
        <revision>
            <published>2025-03-30T00:00:00Z</published>
            <version>1.0</version>
            <oscal-version>1.0.4</oscal-version>
            <prop ns="http://fedramp.gov/ns/oscal" name="party-uuid" value="11111111-2222-4000-8000-004000000001"/>
            <remarks>
                <p>Initial publication.</p>
            </remarks>
        </revision>
    </revisions>
</metadata>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


## XPath Queries

{{<callout>}}
*Note:* To locate information for a specific revision, replace `[1]` with `[2]`, `[3]`, and so on.
{{</callout>}}

| Revision&nbsp;search                  | XPath&nbsp;query                                                                                                                                |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Number of revision entries            | `count(/*/metadata/revision-history/revision)`                                                                                                  |
| Revision date for an individual entry | `/*/metadata/revision-history/revision[1]/published`                                                                                            |
| Description of an individual entry    | `/*/metadata/revision-history/revision[1]/remarks/string()`                                                                                     |
| Version of an individual entry        | `/*/metadata/revision-history/revision[1]/version`                                                                                              |
| Author of an individual entry         | `/*/metadata/party[@uuid=/*/metadata/revision-history/revision[1]/prop [@name='party-uuid'][@ns='http://fedramp.gov/ns/oscal']]/org/short-name` |

