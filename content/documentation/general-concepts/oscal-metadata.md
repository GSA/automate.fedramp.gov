---
title: OSCAL Metadata
weight: 125
---
# Working with Roles, Locations, People, and Organizations

An OSCAL file defines roles, locations, people, and organizations within the
metadata as part of four separate assemblies:

- **role**: A role `id` and `title` are required. Other content, such
    as a `short-name`, `description`, or `remarks` is optional.

- **location**: Locations, such as corporate offices and data center
    addresses, are defined as `location` assemblies

- **party**: People and organizations are defined as `party` assemblies.
    An organization is any collection of people, and can represent a
    company, agency, department, or team.

- **responsible-party**: Links roles to parties. The same `role` can
    have more than one `party` assigned to it. Also a `party` can be
    assigned to more than one `role`.

### FedRAMP Defined Party Identifiers

FedRAMP has eliminated the use of FedRAMP-Defined Party Identifiers.

### Working with Role Assemblies

All roles within the document are defined under the metadata element as
follows:

{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- cut -->
    <role id="prepared-by">
        <title>Prepared By</title>
        <description>
          <p>The organization that prepared this SSP.</p>
        </description>
    </role>
    <role id="prepared-for">
        <title>Prepared For</title>
        <description>
          <p>The organization for which this SSP was prepared</p>
        </description>
    </role>
    <!-- cut -->
</metadata>
{{</ highlight >}}

To ensure consistent processing, FedRAMP has defined a specific set of
roles that must exist with a FedRAMP SSP, SAP, SAR, or POA&M. **Most are
pre-populated in the OSCAL-based FedRAMP Templates.** They vary by
template.

OSCAL-based FedRAMP tools must ensure these roles, titles, and
descriptions exist using the prescribed role IDs within an OSCAL-based
FedRAMP file. Additional roles may be added, provided these roles
remain.

{{<callout>}}
OSCAL-defined and FedRAMP-defined role-identifiers are cited in
relevant portions of each guide, and summarized in the FedRAMP OSCAL
Registry.
{{</callout>}}

### Working with Location Assemblies

The `location` assembly is intended to represent a physical address,
such as the HQ of a CSP or 3PAO, a data center, or an Agency.

Some locations are required. For example, the SSP must contain at
least one `location` assembly with the primary business address of the
CSP. The SAP and SAR must contain at least one `location` assembly with
the primary business address of the assessor.

OSCAL allows the location `title` field to be optional. FedRAMP requires
an explicit `country` code. FedRAMP tools must generate and/or check that
an address has defined its country as the United States with the abbreviation
`US`.

{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- role -->
    <location uuid="uuid-of-hq-location">
        <title>CSP HQ</title>
        <address type="work">
            <addr-line>1234 Some Street</addr-line>
            <city>Haven</city>
            <state>ME</state>
            <postal-code>00000</postal-code>
            <country>US</country>
        </address>
        <prop name="type" class="primary" value="data-center"/>
    </location>
    <!-- party -->
</metadata>
{{</ highlight >}}

Some locations require type properties to ensure FedRAMP tools can
accurately identify required content. For example, the location assembly
for a data center must include a `type` property with a value of
`data-center`. The `class` may be used to indicate whether the data
center is `primary` or `alternate`.

### Working with Party Assemblies

Party assemblies may be used to represent individuals, teams, or an
entire company/agency. When representing an individual, the `type` flag
must have a value of `person`. When representing a team, company or
agency, the `type` flag must have a value of `organization`. FedRAMP
artifacts typically require an individual's title to be identified; the
`prop` name `job-title` is designated for this purpose.

Contact details, such as an individual's email address and phone
number, or a business web site may be included and are often required
within FedRAMP artifacts. All parties require `name` field. 

{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- role -->
    <party uuid="uuid-of-csp" type="organization">
        <name>Cloud Service Provider (CSP) Name</name>
        <short-name>CSP Acronym</short-name>
        <link href="https://www.csp.com" />
    </party>
    <party uuid="uuid-of-person-1" type="person">
        <name>[SAMPLE]Person Name 1</name>
        <prop name="job-title" value="Individual's Title"/>
        <email-address>name@org.domain</email-address>
        <telephone-number>202-555-0000</telephone-number>
    </party>
</metadata>
{{</ highlight >}}

{{<callout>}}
Note: FedRAMP extensions are cited in relevant portions of each guide, and summarized in the FedRAMP OSCAL Registry.
{{</callout>}}

### Identifying Organizational Membership of Individuals

An individual may be affiliated with one or more teams/organizations. Use one `member-of-organization` field for each team, and one to link the
individual to their employer.

{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- role -->
    <party uuid="uuid-of-csp" type="organization">
        <name>Cloud Service Provider (CSP) Name</name>
    </party>
    <party uuid="uuid-of-it-dept" type="organization">
        <name>CSP's IT Department</name>
    </party>
    <party uuid="uuid-of-person-1" type="person">
        <name>[SAMPLE]Person Name 1</name>
        <member-of-organization>uuid-of-csp</member-of-organization>
        <member-of-organization>uuid-of-it-dept</member-of-organization>
    </party>
</metadata>
{{</ highlight >}}

### Identifying the Address of People and Organizations

Representing the address of people or organizations (parties) may be
accomplished with one of three approaches:

1. **Preferred Approach**: When multiple parties share the same address,
such as multiple staff members at a company HQ, define the address once
as a `location` assembly, then use the `location-uuid` field within each
`party` assembly to identify the location of that individual or team.
1. **Alternate Approach**: If the address is unique to this individual, it
may be included in the `party` assembly itself.

1. **Hybrid Approach**: It is possible to include both a `location-uuid` and
an `address` assembly within a `party` assembly. This may be used where
multiple staff are in the same building, yet have different office
numbers or mail stops. Use the `location-uuid` to identify the shared
building, and only include a single `addr-line` field within the party's
`address` assembly.

A tool developer may elect to always create a location assembly, even
when only used once; however, tools must recognize and handle all of the
approaches above when processing OSCAL files.

{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- cut -->
    <location uuid="uuid-of-hq-location">
        <title>CSP HQ</title>
        <address type="work">
            <addr-line>1234 Some Street</addr-line>
            <city>Haven</city>
            <state>ME</state>
            <postal-code>00000</postal-code>
        </address>
    </location>
    <party uuid="uuid-of-csp" type="organization">
        <name>Cloud Service Provider (CSP) Name</name>
        <location-uuid>uuid-of-hq-location</location-uuid>
    </party>
    <party uuid="uuid-of-person-1" type="person">
        <name>[SAMPLE]Person Name 1</name>
        <prop name="mail-stop" value="A-1"/>
        <location-uuid>uuid-of-hq-location</location-uuid>
    </party>
</metadata>
{{</ highlight >}}

### Using Responsible Party Assemblies

The responsible party assembly links party assemblies (people and
organizations) to defined roles. FedRAMP tools rely on these linkages to
find required content.

For example, an OSCAL-based SSP must have a role defined for the System
Owner using the role ID value `system-owner`. The responsible-party
assembly links this required role to the individual (party). FedRAMP
tools follow this linkage to verify that a system owner was identified
in the SSP, and to display that information to reviewers.

{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- party -->
    <responsible-party role-id="system-owner">
        <party-uuid>uuid-of-person-1</party-uuid>
    </responsible-party>
</metadata>
{{</ highlight >}}
