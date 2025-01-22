---
title: Document Revision History
weight: 305
---

## Document Revision History

{{< figure src="/img/content-figure-8.png" title="FedRAMP template document revision history." alt="Screenshot of document revision history information in the FedRAMP template." >}}

{{<callout>}}
The `remarks` field is Markup multiline, which enables the text to be formatted. This requires special handling. See the section on [markup-line and markup-multiline Fields in OSCAL](/documentation/general-concepts/oscal-data-types/#markup-line-and-markup-multiline-fields-in-oscal), or visit: https://pages.nist.gov/metaschema/specification/datatypes/#markup-multiline<br/>
{{</callout>}}

The OSCAL revision history requires one FedRAMP extension to fully meet
FedRAMP's revision history requirements.

##### Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- title, published, last-modified, version, oscal-version -->
    <revisions>
        <revision>
            <published>2022-06-01T00:00:00.000Z</published>
            <version>1.0</version>
            <oscal-version>1.1.2</oscal-version>
            <prop name="party-uuid" ns="http://fedramp.gov/ns/oscal"
                value="f84d8edc-d83e-440d-96c9-09b28c395ad5"/>
            <remarks><p>Initial publication.</p></remarks>
        </revision>
        <revision>
            <published>2022-06-01T00:00:00.000Z</published>
            <version>2.0</version>
            <oscal-version>1.1.2</oscal-version>
            <prop name="party-uuid" ns="http://fedramp.gov/ns/oscal"
                value="2e0db7cf-08f5-472e-9360-fb3a9698476d"/>
            <remarks><p>Updated for annual assessment.</p></remarks>
        </revision>
        <!-- Additional revision assemblies as needed. -->
    </revisions>
    <!-- doc-id, prop, link, role -->
</metadata>
{{</ highlight >}}

{{<callout>}}
**FedRAMP Extension (Author)** \
prop (`ns="http://fedramp.gov/ns/oscal"`):
- `name="party-uuid"`

{{</callout>}}

##### XPath Queries

- Number of Revision Entries: `count(/*/metadata/revision-history/revision)`
- Revision Date for Individual Entry: `/*/metadata/revision-history/revision[1]/published`
- Description for Individual Entry: `/*/metadata/revision-history/revision[1]/remarks/string()`
- Version for Individual Entry: `/*/metadata/revision-history/revision[1]/version`
- Author for Individual Entry: `/*/metadata/party[@uuid=/*/metadata/revision-history/revision[1]/prop [@name='party-uuid'][@ns='http://fedramp.gov/ns/oscal']]/org/short-name`

{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

**NOTES:**

- The Revision History's Author field is addressed using a FedRAMP
    extension, which points to a metadata `party`.
- The published field requires the OSCAL data type,
    [date-time-with-timezone](https://pages.nist.gov/metaschema/specification/datatypes/#date-time-with-timezone).
- FedRAMP only requires the publication date, not the time.
    - The time portion may be replaced with all zeros.
    - FedRAMP tools should present only the date, and use a more
        user-friendly format.
