---
title: Document Approvals
weight: 315
---
## Document Approvals

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

