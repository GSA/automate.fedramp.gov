---
title: Prepared By/For
weight: 303
---
## Prepared By/For

This addresses:
- Prepared By (Third Party)
- Prepared By (CSP/Self-Prepared)
- Prepared For (CSP)

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

### Prepared By (CSP/Self-Prepared)

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
