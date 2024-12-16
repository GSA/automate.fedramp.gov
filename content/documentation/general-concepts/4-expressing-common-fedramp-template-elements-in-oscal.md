---
title: Expressing FedRAMP Template Metadata
weight: 124
---
# Expressing FedRAMP Template Metadata in OSCAL

While each FedRAMP template has a unique purpose, they share common
information elements, such as title and publication date. These common
elements are expressed using the same OSCAL syntax for the SSP, SAP,
SAR, and POA&M. This section provides OSCAL syntax for these common
elements, including:

- Document Basics:
    - Document Title
    - Document Publication Date
    - Document Version
    - Document Sensitivity & Ownership Markings
    - Prepared By
    - Prepared For
    - Document Revision History
- OSCAL-Additional Document Basics:
    - Last Modified Date
    - OSCAL Syntax Version
    - FedRAMP Version
- Logos:
    - FedRAMP Logo
    - CSP Logo
    - Assessor Logo
    - Consulting 3PAO Logo
- Attachments:
    - FedRAMP Acronyms
    - FedRAMP Citations (Laws, Regulations, Standards, and Guidance)

### Title Page

{{< figure src="/img/content-figure-5.png" title="FedRAMP document template title page." alt="Screenshot of a FedRAMP document template cover page." >}}

{{<callout>}}
The **FedRAMP Logo** is a resource in the back-matter section of the OSCAL-based FedRAMP Templates, and can be referenced with the following XPath:

`/*/metadata/party[@uuid=../responsible-party[@role-id='fedramp-pmo']/party-uuid]/link[@rel='logo']/@href`

As with any href value, this can include a relative or absolute URI external to the OSCAL file, or it can contain a URI fragment, pointing to a resource inside the OSCAL file itself (or other OSCAL files in the stack).

If the above returns an href value beginning with a hashtag (#), the rest of the value is the UUID value for the resource containing the logo. Drop the hashtag and use the remaining value to locate the resource as follows:

`/*/back-matter/resource[@uuid='[UUID-value-returned-above]']/rlink/@href`

OR

`/*/back-matter/resource[@uuid='[UUID-value-returned-above]']/base64`
{{</callout>}}

##### Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <title>FedRAMP System Security Plan (SSP)</title>
    <published>2022-06-01T00:00:00.000Z</published>
    <last-modified>2023-03-03T00:00:00.000Z </last-modified>
    <version>0.0</version>
    <oscal-version>1.1.2</oscal-version>
    <prop name="fedramp-version" ns="http://fedramp.gov/ns/oscal" value="3.0.0-rc1"/>
    <prop name="marking" value="cui"/>
    <role id="fedramp-pmo">
        <title>FedRAMP PMO</title>
        <description><p>Description</p></description>
    </role>
    <!-- cut: location assemblies-->
    <party uuid="77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d" type="organization">
        <name>FedRAMP: Program Management Office</name>
        <short-name>FedRAMP PMO</short-name>
        <link href="#a2381e87-3d04-4108-a30b-b4d2f36d001f" rel="logo"/>
    </party>
    <responsible-party role-id="fedramp-pmo">
        <party-id>77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d</party-id>
    </responsible-party>
</metadata>
<!-- OSCAL File Body -->
<back-matter>
    <resource uuid="a2381e87-3d04-4108-a30b-b4d2f36d001f">
        <description><p>FedRAMP Logo</p></description>
        <prop name="type" value="logo" />
        <rlink href="https://www.fedramp.gov/assets/img/logo-main-fedramp.png"/>
        <base64 filename="FedRAMP_LOGO.png">
            <!-- Base64-encoded Logo Cut -->00000000
        </base64>
    </resource>
</back-matter>
{{</ highlight >}}

{{<callout>}}
**FedRAMP Allowed Value**\
Required Role ID:
- `fedramp-pmo`
{{</callout>}}

##### XPath Queries

- Document Title: `/*/metadata/title`
- Document Published Version #: `/*/metadata/version`
- Document Published Date (will need to convert data for presentation): `/*/metadata/published`
- FedRAMP's Logo: `/*/metadata/party[@uuid=../responsible-party[@role-id='fedramp-pmo']/party-uuid]/link[@rel='logo']/@href`
- Document Sensitivity Label (If more than one, tools should present all): `/*/metadata/prop[@name="marking"]`

**NOTES:**

- There may be more than one *Document Sensitivity Label* (`marking`), if needed. The only required value is `cui` (Controlled Unclassified Information). Tools should display and/or notify the user of all sensitivity markings.

- The logos on older FedRAMP Templates are not necessary. This includes the NIST Logo, as well as the three Joint Authorization Board (JAB) Agency Logos.

### Prepared By (Third Party)

{{< figure src="/img/content-figure-6.png" title="FedRAMP template \"Prepared By\"." alt="Screenshot of third party \"prepared by\" information in the FedRAMP template." >}}

The FedRAMP SAP and SAR must always indicate the assessing organization
using this Prepared By syntax.

##### Representation 

{{< highlight xml "linenos=table" >}}
<metadata>
    <role id="prepared-by">
        <title>Prepared By</title>
        <description><p>Description</p></description>
    </role>
    <!-- cut: other role assemblies-->
    <!-- cut: location assemblies-->
    <party uuid="f84d8edc-d83e-440d-96c9-09b28c395ad5">
        <name>Name of Consulting Org</name>
        <short-name>Acronym/Short Name</short-name>
        <address type="work">
            <!-- address lines cut here for space -->
        </address>
    </party>
    <!-- cut: other party assemblies -->
    <responsible-party role-id="prepared-by">
        <party-id>f84d8edc-d83e-440d-96c9-09b28c395ad5</party-id>
    </responsible-party>
</metadata>

<!-- OSCAL File Body -->

<back-matter>
    <resource id="1507f5e0-635c-4e23-a5f3-93f368f8e022">
        <description><p>Preparer Logo</p></description>
        <prop name="type" value="logo" />
        <!-- Use rlink and/or base64 -->
        <rlink href="./party-1-logo.png" media-type="image/png" />
        <base64>00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}

{{<callout>}}
**OSCAL Allowed Value** \
Required Role ID:

- `prepared-by`
{{</callout>}}

##### XPath Queries

- Preparer Organization's Name and Address: `/*/metadata/party[@id=[/*/metadata/responsible-party[@role-id='prepared-by']/party-id]]/org/org-name`

NOTE: Replace "org-name" with "address/addr-line", "address/city", "address/state", or "address/zip" as needed. There may be more than one addr-line.

**NOTES:**

- The `responsible-party` assembly connects the role to the party and is
    required for compliance.

- If the content was prepared by an organization other than the CSP,
    their logo should also appear in back-matter.

### Prepared By (CSP Self-Prepared)

{{< figure src="/img/content-figure-6.png" title="FedRAMP template \"Prepared By\"." alt="Screenshot of CSP self \"prepared by\" information in the FedRAMP template." >}}

This is applicable where the CSP creates or updates its own SSP or POA&M
content. The FedRAMP SAP and SAR must never be CSP self-prepared.

##### Representation 
{{< highlight xml "linenos=table" >}}
<metadata>
    <role id="prepared-by">
        <title>Prepared By</title>
        <description><p>Description</p></description>
    </role>
     <location uuid="27b78960-59ef-4619-82b0-ae20b9c709ac">
      <title>CSP HQ</title>
      <address type="work">
        <addr-line>Suite 0000</addr-line>
        <addr-line>1234 Some Street</addr-line>
        <city>Haven</city>
        <state>ME</state>
        <postal-code>00000</postal-code>
        <country>US</country>
      </address>
    </location>
    <party id="2e0db7cf-08f5-472e-9360-fb3a9698476d">
        <name>Cloud Service Provider (CSP) Name</name>
        <short-name>CSP Acronym/Short Name</short-name>
        <location-uuid>27b78960-59ef-4619-82b0-ae20b9c709ac</location-uuid>
    </party>
    <responsible-party role-id="prepared-by">
        <party-id>2e0db7cf-08f5-472e-9360-fb3a9698476d</party-id>
    </responsible-party>
</metadata>

<!-- OSCAL File Body -->

<back-matter>
    <resource id="74a61c36-ad18-4ee3-8bc4-6e2f917b0ce8">
        <description><p>CSP Logo</p></description>
        <prop name="type" value="logo" />
        <!-- Use rlink and/or base64 -->
        <rlink href="./logo.png" media-type="image/png" />
        <base64>00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}

<br />
{{<callout>}}
**OSCAL Allowed Value** \
Required Role ID:
- `prepared-by`

{{</callout>}}

##### XPath Queries

- Preparer Organization's Name and Address: `/*/metadata/party[@id=[/*/metadata/responsible-party[@role-id='prepared-by']/party-id]]/org/org-name`

NOTE: Replace "org-name" with "address/addr-line", "address/city", "address/state", or "address/zip" as needed. There may be more than one addr-line.

**NOTES:**

- The `responsible-party` assembly connects the role to the party and is
    required for compliance.

### Prepared For (CSP)

{{< figure src="/img/content-figure-7.png" title="FedRAMP template \"Prepared For\"." alt="Screenshot of \"prepared for\" information in the FedRAMP template." >}}

For FedRAMP SSP, SAP, SAR, and POA&M, the `Prepared For` is typically
the CSP; however, it may be different if an unforeseen circumstance
requires another party to be named. For this reason, `Prepared For`
and CSP have separately defined roles.

##### Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- prop -->
    <role id="prepared-for">
        <title>Prepared For</title>
        <description><p>The CSP for FedRAMP SSP, SAP, SAR, and POA&amp;M.</p></description>
    </role>
    <role id="cloud-service-provider">
        <title>Cloud Service Provider</title>
        <short-name>CSP</short-name>
    </role>
    <location uuid="27b78960-59ef-4619-82b0-ae20b9c709ac">
      <title>CSP HQ</title>
      <address type="work">
        <addr-line>Suite 0000</addr-line>
        <addr-line>1234 Some Street</addr-line>
        <city>Haven</city>
        <state>ME</state>
        <postal-code>00000</postal-code>
        <country>US</country>
      </address>
    </location>
    <party id="2e0db7cf-08f5-472e-9360-fb3a9698476d">
        <name>Cloud Service Provider (CSP) Name</name>
        <short-name>CSP Acronym/Short Name</short-name>
        <location-uuid>27b78960-59ef-4619-82b0-ae20b9c709ac</location-uuid>
    </party>
    <!-- cut: other party assemblies -->
    <responsible-party role-id="prepared-for">
        <party-id>2e0db7cf-08f5-472e-9360-fb3a9698476d</party-id>
    </responsible-party>
</metadata>
<!-- OSCAL File Body -->
<back-matter>
    <resource id="74a61c36-ad18-4ee3-8bc4-6e2f917b0ce8">
        <description><p>CSP Logo</p></description>
        <prop name='type'>logo</prop>
        <!-- Use rlink and/or base64 -->
        <rlink href="./logo.png" media-type="image/png" />
        <base64>00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}

##### XPath Queries

- Prepared For (CSP) Details: `/*/metadata/party[@id=[/*/metadata/responsible-party[@role-id='prepared-for']/party-id]]/org/org-name`
- Prepared For Details: `/*/metadata/party[@id=[/*/metadata/responsible-party[@role-id='prepared-for']/party-id]]/org/org-name`

NOTE: Replace "org-name" with "address/addr-line", "address/city", "address/state", or "address/zip" as needed. There may be more than one addr-line.

### Document Revision History

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

### FedRAMP Version

All documents in a digital authorization package for FedRAMP must specify the version that identifies which FedRAMP policies, guidance, and technical specifications its authors used during the creation and maintenance of the package.

FedRAMP maintains an official list of the versions on the [fedramp-automation releases](https://github.com/GSA/fedramp-automation/releases) page. Unless noted otherwise, a valid version is a [published tag name](https://github.com/GSA/fedramp-automation/tags).

##### Representation
{{< highlight xml "linenos=table, hl_lines=7" >}}
<metadata>
    <title>FedRAMP System Security Plan (SSP)</title>
    <published>2022-06-01T00:00:00.000Z</published>
    <last-modified>2023-03-03T00:00:00.000Z </last-modified>
    <version>0.0</version>
    <oscal-version>1.1.2</oscal-version>
    <prop name="fedramp-version" ns="http://fedramp.gov/ns/oscal" value="3.0.0-rc1"/>
</metadata>
{{</ highlight >}}

##### XPath Query
`/*/metadata/prop[@name='fedramp-version'][@ns='http://fedramp.gov/ns/oscal']/@value`

### How to Contact Us

{{< figure src="/img/content-figure-9.png" title="FedRAMP template contact us." alt="Screenshot of \"contact us\" information in the FedRAMP template." >}}

The FedRAMP email and web site addresses are part of the organizational
content for the FedRAMP PMO party. This information already exists in
OSCAL-based FedRAMP Templates.

There must be a `role` defined in the file with the ID value set to
`fedramp-pmo`. There must be a `party` defined with FedRAMP's details,
and there must be a `responsible-party` defined, linking the
`fedramp-pmo` `role-id` to the FedRAMP `party` uuid.

##### Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    
    <role id="fedramp-pmo">
        <title>FedRAMP Program Management Office</title>
    </role>
    
    <!-- location -->
    
    <party uuid="77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d" type="organization">
        <name>FedRAMP Program Management Office</name>
        <short-name>FedRAMP PMO</short-name>
        <link href="https://fedramp.gov" />
        <email>oscal@fedramp.gov</email>
        <address type="work">
            <addr-line>1800 F St. NW</addr-line>
            <addr-line/>
            <city>Washington</city>
            <state>DC</state>
            <postal-code/>
            <country>US</country>
        </address>
    </party>
    
    <responsible-party role-id="fedramp-pmo">
        <party-uuid>77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d</party-uuid>
    </responsible-party>
    
</metadata>
{{</ highlight >}}

{{<callout>}}
**FedRAMP-Role Identifiers:**
- `fedramp-pmo`

{{</callout>}}

##### XPath Queries

- FedRAMP Email Address: `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='fedramp-pmo'] /party-uuid]/email`
- FedRAMP Web Site Address: `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='fedramp-pmo'] /party-uuid]/link/@href`

### Document Approvals

{{< figure src="/img/content-figure-10.png" title="FedRAMP template document approvals." alt="Screenshot of document approvals information in the FedRAMP template." >}}

The OSCAL syntax is the same for document approvers in the SSP, SAP, and
SAR. For the SSP, approvers are typically executives within the CSP. For
the SAP and SAR, approvers are typically executives within the
assessor's organization.

##### Representation
{{< highlight xml "linenos=table" >}}
<!-- Representation -->
<metadata>
    <!-- title, published ... prop, link -->
    <role id="content-approver">
        <title>[SSP, SAP, or SAR] Approval</title>
        <desc>The executive(s) accountable for the accuracy of this content.</desc>
    </role>
    <role id="cloud-service-provider">
        <title>Cloud Service Provider</title>
        <short-name>CSP</short-name>
    </role>
    <party uuid="uuid-of-csp" type="organization">
        <name>Cloud Service Provider (CSP) Name</name>
        <short-name>CSP Acronym/Short Name</short-name>
    </party>
    <party uuid="uuid-of-person-1" type="person">
        <name>[SAMPLE]Person Name 1</name>
        <prop name="title" ns="http://fedramp.gov/ns/oscal">Individual's Title</prop>
        <member-of-organization>uuid-of-csp</member-of-organization>         
    </party>
    <party uuid="uuid-of-person-2" type="person">
        <name>[SAMPLE]Person Name 2</name>
        <prop name="title" ns="http://fedramp.gov/ns/oscal">Individual's Title</prop>
        <member-of-organization>uuid-of-csp</member-of-organization>         
    </party>
    <responsible-party role-id="cloud-service-provider">
        <party-uuid>uuid-of-csp</party-uuid>
    </responsible-party>
    <responsible-party role-id="content-approver">
        <party-uuid>uuid-of-person-1</party-uuid>
        <party-uuid>uuid-of-person-2</party-uuid>
    </responsible-party>
</metadata>
{{</ highlight >}}

{{<callout>}}
**Defined Identifiers**\
Required Role IDs:
- `content-approver`
- `cloud-service-provider`

**FedRAMP Extension (Person's Title)** \
prop (`ns="http://fedramp.gov/ns/oscal"`):
- `name="title"`
{{</callout>}}

##### XPath Queries

- Approver’s Name: `(/*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id='content-approver']/party-uuid]]/party-name)[1]`
- Approver’s Title: `(/*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id='content-approver'] /party-uuid]]/prop[@name='title'][@ns='http://fedramp.gov/ns/oscal'])[1]`

   NOTE: For each additional approver, replace the "[1]" with "[2]", "[3]", and so on.

- CSP Name: `/*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id='cloud-service-provider']/party-uuid]]/party-name`

**NOTES:**

The code above is an SSP example. For SAP and SAR, a similar approach is
used for the assessor, using the `"assessor"` role ID instead of the
`"cloud-service-provider"` role ID.

### FedRAMP Standard Attachments (Acronyms, Laws/Regulations)

The FedRAMP MS Word-based SSP, SAP and SAR templates included links to
the FedRAMP Laws and Regulations file, as well as the FedRAMP Acronyms
file posted on <https://fedramp.gov>.

These are already included in the OSCAL-based FedRAMP templates as
resources. The `resource` linking to the FedRAMP citations file is
identified with links from the property type, `fedramp-citations`. The
`resource` linking to the FedRAMP acronyms file is identified with the
property type, `fedramp-acronyms`.

##### Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- cut -->
    <party uuid="77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d" type="organization">
        <name>FedRAMP: Program Management Office</name>
        <short-name>FedRAMP PMO</short-name>
        <link href="#985475ee-d4d6-4581-8fdf-d84d3d8caa48" rel="reference" />
        <link href="#1a23a771-d481-4594-9a1a-71d584fa4123" rel="reference" />
    </party>
</metadata>

<back-matter>
    
    <resource uuid="985475ee-d4d6-4581-8fdf-d84d3d8caa48">
        <title>FedRAMP Applicable Laws and Regulations</title>
        <prop ns="http://fedramp.gov/ns/oscal" name="type" value="fedramp-citations"/>
        <rlink href="https://-cut-/SSP-A12-FedRAMP-Laws-and-Regulations-Template.xlsx"/>
    </resource>
    
    <resource uuid="1a23a771-d481-4594-9a1a-71d584fa4123">
        <title>FedRAMP Master Acronym and Glossary</title>
        <prop ns="http://fedramp.gov/ns/oscal" name="type" value="fedramp-acronyms"/>
        <rlink href="https://-cut-/FedRAMP_Master_Acronym_and_Glossary.pdf" />
    </resource>
    
</back-matter>
{{</ highlight >}}

##### XPath Queries
{{< highlight xml "linenos=table" >}}
Link to FedRAMP Applicable Laws and Regulations:
    /*/back-matter/resource/prop[@name='type'][string(.)='fedramp-citations']/../rlink/@href
Link to FedRAMP Acronyms and Glossary:
    /*/back-matter/resource/prop[@name='type'][string(.)='fedramp-acronyms']/../rlink/@href
{{</ highlight >}}

### Additional Laws, Regulations, Standards or Guidance

{{< figure src="/img/content-figure-11.png" title="FedRAMP template laws and regulations." alt="Screenshot of laws, regulations, standards, and guidance information in the FedRAMP template." >}}

Additional citations must be represented as
additional `resource` assemblies with one `resource` assembly per citation. This
applies to applicable laws, regulations, standards, or guidance beyond
FedRAMP's predefined set.

Each must have a type defined. The value of the type filed must be set
to `law`, `regulation`, `standard`, or `guidance` as
appropriate. There may be more than one type defined. FedRAMP tools use
the `type` property to differentiate these resource assemblies from
others.

##### Representation
{{< highlight xml "linenos=table" >}}
<back-matter>
    <resource uuid="d45612a9-cf25-4ef6-b2dd-69e38ba2967a">
        <title>[SAMPLE]Name or Title of Cited Law</title>
        <prop name="type" value="law"/>
        <prop name="publication" value="Document Date"/>
        <prop name="version" value="Document Version"/>
        <doc-id type="doi">Identification Number</doc-id>
        <rlink href="https://domain.example/path/to/document.pdf" />
    </resource>
    <resource uuid="a8a0cc81-800f-479f-93d3-8b8743d9b98d">
        <title>[SAMPLE]Name or Title of Cited Regulation</title>
        <prop name="type" value="regulation"/>
        <prop name="publication" value="Document Date"/>
        <prop name="version" value="Document Version"/>
        <doc-id type="doi">Identification Number</doc-id>
        <rlink href="https://domain.example/path/to/document.pdf" />
    </resource>
    <!-- repeat citation assembly for each law, regulation, standard or guidance -->
    <!-- resource -->
</back-matter>
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

##### XPath Queries

- Number of Laws and Regulations (integer): `count(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])`
- Laws and Regulations: Identification Number: `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../doc-id`
- Laws and Regulations: Title: `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../title`
- Laws and Regulations: Date: `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../prop[@name="publication"]`
- Laws and Regulations: Link: `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../rlink/@href`

NOTE: For Standards and Guidance replace "law" with "standard" and "regulation" with "guidance" in the above queries to generate the Standards and Guidance tables.

### Attachments and Embedded Content

There are several attachments in a classic
FedRAMP MS Word based SSP, SAP, SAR document or Deviation Request (DR)
form. Some lend well to machine-readable format, while others do not.
Those that are readily modeled in machine-readable format are typically
addressed within the OSCAL syntax, while attachments such as policies,
procedures, plans, guides, and rules of behavior documents are all
treated as attachments in OSCAL as well.

Further, any diagrams or images that normally appear in context, such as
the authorization boundary diagram, are attached in the back-matter and
referenced from the body of the OSCAL file, as described in [*Citations and Attachments in OSCAL Files*](/documentation/general-concepts/oscal-citations-and-attachments/). The following table represents
attachments and embedded content.

{{< figure src="/img/content-figure-12.png" title="FedRAMP template attachments and embedded content." alt="Screenshot of attachments and embedded content information in the FedRAMP template." >}}

##### Representation
{{< highlight xml "linenos=table" >}}
<!-- cut -->
<back-matter>
    <!-- citation -->
    <resource uuid="fab59751-b855-40cb-93c1-492562e20e18">
        <title>Name of Procedure Document</title>
        <prop name="type" value="procedure"/>
        <prop name="publication" value="Document Date"/>
        <prop name="version" value="Document Version"/>
        <!-- Add rlink with relative path OR embed with base64 encoding -->
        <rlink href="./procedure.docx" />
        <base64>00000000</base64>
    </resource>
    
    <resource id="diag-boundary-1">
        <description>
            <p>The primary authorization boundary diagram.</p>
        </description>
        <!-- Add rlink with relative path or embed with base64 encoding -->
        <rlink media-type="image/png" href="./boundary.png" />
        <base64 media-type="image/png" filename="boundary.png">00000000</base64>
        <remarks><p>Set system-characteristics/authorization-boundary/diagram/link/@href = "#diag-boundary-1"</p></remarks>
    </resource>
</back-matter>
{{</ highlight >}}

<br />
{{<callout>}}
Replace "policy" with "plan", "rob", etc. for each attachment type.
{{</callout>}}

##### XPath Queries

- PIA Attachment (Embedded Base64 encoded): `/*/back-matter/resource/prop[@name='type'][string(.)='privacy-impact-assessment']/../base64`
- PIA Attachment (Relative Link): `/*/back-matter/resource/prop[@name=type][string(.)='privacy-impact-assessment']/../rlink/@href`
- Publication Date of PIA: `/*/back-matter/resource/prop[@name=type][string(.)='privacy-impact-assessment']/../prop[@name="publication"]`

Tools creating OSCAL content should include a `media-type` for all `rlink`
and `base64` fields, as well as a `filename` for all `base64` fields.

Tools should process `rlink` and `base64` content with or without these
fields. Where present they should be used when validating or rendering
the linked or embedded content.
