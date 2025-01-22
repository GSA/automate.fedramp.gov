---
title: FedRAMP Contact Information
weight: 310
---

## FedRAMP Contact Information

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
