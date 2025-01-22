---
title: Title Page
weight: 302
---
# Expressing FedRAMP Template Metadata in OSCAL


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


