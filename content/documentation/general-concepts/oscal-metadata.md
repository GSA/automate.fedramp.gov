---
title: OSCAL Metadata
weight: 140
---
# Working with Roles, Locations, People, and Organizations

An OSCAL file defines roles, locations, people, and organizations within the
metadata as part of four separate assemblies.

| Assembly                         | Description                                                                                                                                                        |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| role <br><br>                    | A role `id` and `title` are required. Other content, such as a `short-name`, `description`, or `remarks`, is optional.                                             |
| location <br><br>                | Locations, such as corporate offices and data center addresses, are defined as `location` assemblies.                                                              |
| party <br><br>                   | People and organizations are defined as `party` assemblies. An organization is any collection of people, and can represent a company, agency, department, or team. |
| responsible&#8209;party <br><br> | Links roles to parties. The same `role` can have more than one `party` assigned to it. Additionally, a `party` may be assigned to more than one `role`.            |

## FedRAMP-Defined Party Identifiers

FedRAMP has eliminated the use of FedRAMP-defined party identifiers.

## Working with Role Assemblies

All roles within the document are defined under the metadata element.

{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        // cut
        "roles": [
            {
                "id": "prepared-by",
                "title": "Prepared By",
                "description": "The organization that prepared this SSP. If developed in-house, this is the CSP itself."
            }
            {
                "id": "prepared-for",
                "title": "Prepared For",
                "description": "The organization for which this SSP was prepared (typically, the CSP)."
            }
        ]
        // cut
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- cut -->
    <role id="prepared-by">
      <title>Prepared By</title>
      <description>
        <p>The organization that prepared this SSP. If developed in-house, this is the CSP itself.</p>
      </description>
    </role>
    <role id="prepared-for">
      <title>Prepared For</title>
      <description>
        <p>The organization for which this SSP was prepared (typically, the CSP).</p>
      </description>
    </role>
    <!-- cut -->
</metadata>
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  metadata:
    # cut
    roles:
    - id: prepared-by
      title: Prepared By
      description: The organization that prepared this SSP. If developed in-house, this is the CSP itself.
    - id: prepared-for
      title: Prepared For
      description: The organization for which this SSP was prepared (typically, the CSP).
    # cut
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

To ensure consistent processing, FedRAMP has defined a specific set of
roles that must exist with a FedRAMP SSP, SAP, SAR, or POA&M. **Most are
pre-populated in the OSCAL-based FedRAMP Templates.** They vary by
template.

OSCAL-based FedRAMP tools must ensure these roles, titles, and
descriptions exist using the prescribed role IDs within an OSCAL-based
FedRAMP file. Additional roles may be added, provided these roles
remain.

{{<callout>}}
_Note:_ OSCAL-defined and FedRAMP-defined role identifiers are cited in
relevant portions of each guide. They are summarized in the FedRAMP OSCAL
Registry.
{{</callout>}}


## Working with Location Assemblies

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

{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        // role
        "locations": [
            {
                "uuid": "11111111-2222-4000-8000-003000000002",
                "title": "Primary Data Center",
                "address": {
                    "addr-lines": ["2222 Main Street"],
                    "city": "Anywhere",
                    "state": "--",
                    "postal-code": "00000-0000",
                    "country": "US"
                },
                "props": [
                    {
                        "name": "type",
                        "value": "data-center",
                        "class": "primary"
                    }
                ],
            },
        ],
        // party
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- role -->
    <location uuid="11111111-2222-4000-8000-003000000002">
        <title>Primary Data Center</title>
        <address>
            <addr-line>2222 Main Street</addr-line>
            <city>Anywhere</city>
            <state>--</state>
            <postal-code>00000-0000</postal-code>
            <country>US</country>
        </address>
        <prop name="type" class="primary" value="data-center"/>
    </location>
    <!-- party -->
</metadata>
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  metadata:
    # role
    locations:
    - uuid: 11111111-2222-4000-8000-003000000002
      title: Primary Data Center
      address:
        addr-lines:
        - 2222 Main Street
        city: Anywhere
        state: --
        postal-code: 00000-0000
        country: US
      props:
      - name: type
        value: data-center
        class: primary
    # party
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

Some locations require `type` properties to ensure FedRAMP tools can accurately identify required content.

For example, the location assembly for a data center must include a `type` property with a value of
`data-center`. The `class` may be used to indicate whether the data center is `primary` or `alternate`.


## Working with Party Assemblies

Party assemblies may be used to represent individuals, teams, or an
entire company/agency. When representing an individual, the `type` flag
must have a value of `person`. When representing a team, company or
agency, the `type` flag must have a value of `organization`. FedRAMP
artifacts typically require an individual's title to be identified. The
`prop` name `job-title` is designated for this purpose.

Contact details, such as an individual's email address and phone
number, or a business website link, may be included. Moreover, FedRAMP artifacts often require such details.

All parties must have the `name` field. 

{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        // location
        "parties": [
            {
                "uuid": "11111111-2222-4000-8000-004000000008",
                "type": "person",
                "name": "ICA POC's Name",
                "props": [
                    {
                        "name": "job-title",
                        "value": "Individual's Title"
                    }
                ],
                "email-addresses": ["person@ica.example.org"],
                "telephone-numbers": [
                    {"number": "2025551212"}
                ],
                "member-of-organizations": ["11111111-2222-4000-8000-004000000007"]
            },
            {
                "uuid": "22222222-2222-4000-8000-c0040000000a",
                "type": "organization",
                "name": "Example IaaS Provider",
                "short-name": "E.I.P.",
                "links": [
                    {
                        "href": "https://www.eip.com"
                    }
                ],
            },
        ]
        // responsible-party
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- location -->
    <party uuid="11111111-2222-4000-8000-004000000008" type="person">
        <name>ICA POC's Name</name>
        <prop name="job-title" value="Individual's Title"/>
        <email-address>person@ica.example.org</email-address>
        <telephone-number>2025551212</telephone-number>
        <member-of-organization>11111111-2222-4000-8000-004000000007</member-of-organization>
    </party>
    <party uuid="22222222-2222-4000-8000-c0040000000a" type="organization">
        <name>Example IaaS Provider</name>
        <short-name>E.I.P.</short-name>
        <link href="https://www.eip.com"/>
    </party>
    <!-- responsible-party -->
</metadata>
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  metadata:
    # locations
    parties:
    - uuid: 11111111-2222-4000-8000-004000000008
      type: person
      name: 'ICA POC''s Name'
      props:
      - name: job-title
        value: Individual's Title
      email-addresses:
      - person@ica.example.org
      telephone-numbers:
      - number: '2025551212'
      member-of-organizations:
      - 11111111-2222-4000-8000-004000000007
    - uuid: 22222222-2222-4000-8000-c0040000000a
      type: organization
      name: 'Example IaaS Provider'
      short-name: E.I.P.
      links:
      - href: https://www.eip.com
    # responsible-party
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

<br>
{{<callout>}}
_Note:_ FedRAMP extensions are cited in relevant portions of each guide, and summarized in the FedRAMP OSCAL Registry.
{{</callout>}}


## Identifying Organizational Membership of Individuals

An individual may be affiliated with one or more teams/organizations. Use one `member-of-organization` field for each team, and one to link the
individual to their employer.

{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        // location
        "parties": [
            {
                "uuid": "11111111-2222-4000-8000-004000000008",
                "type": "person",
                "name": "ICA POC's Name",
                "props": [
                    {
                        "name": "job-title",
                        "value": "Individual's Title"
                    }
                ],
                "email-addresses": ["person@ica.example.org"],
                "telephone-numbers": [
                    {"number": "2025551212"}
                ],
                "member-of-organizations": [
                    "11111111-2222-4000-8000-004000000001",
                    "11111111-2222-4000-8000-004000000002",
                    "11111111-2222-4000-8000-004000000003"
                ]
            },
        ]
        // responsible-party
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- location -->
    <party uuid="11111111-2222-4000-8000-004000000008" type="person">
        <name>ICA POC's Name</name>
        <prop name="job-title" value="Individual's Title"/>
        <email-address>person@ica.example.org</email-address>
        <telephone-number>2025551212</telephone-number>
        <member-of-organization>11111111-2222-4000-8000-004000000001</member-of-organization>
        <member-of-organization>11111111-2222-4000-8000-004000000002</member-of-organization>
        <member-of-organization>11111111-2222-4000-8000-004000000003</member-of-organization>
    </party>
    <!-- responsible-party -->
</metadata>
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  metadata:
    # locations
    parties:
    - uuid: 11111111-2222-4000-8000-004000000008
      type: person
      name: 'ICA POC''s Name'
      props:
      - name: job-title
        value: Individual's Title
      email-addresses:
      - person@ica.example.org
      telephone-numbers:
      - number: '2025551212'
      member-of-organizations:
      - 11111111-2222-4000-8000-004000000001
      - 11111111-2222-4000-8000-004000000002
      - 11111111-2222-4000-8000-004000000003
    # responsible-party
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


## Identifying the Address of People and Organizations

Representing the address of people or organizations (parties) may be
accomplished with one of three approaches.

| Approach                             | Description                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Preferred&nbsp;approach<br><br><br>  | When multiple parties share the same address, such as multiple staff members at a company HQ, define the address once as a `location` assembly, then use the `location-uuid` field within each `party` assembly to identify the location of that individual or team.                                                                                               |
| Alternate&nbsp;approach<br>          | If the address is unique to this individual, it may be included in the `party` assembly itself.                                                                                                                                                                                                                                                                    |
| Hybrid&nbsp;approach<br><br><br><br> | It is possible to include both a `location-uuid` and an `address` assembly within a `party` assembly. This may be used where multiple staff are in the same building, yet have different office numbers or mail stops. Use the `location-uuid` to identify the shared building, and only include a single `addr-line` field within the party's `address` assembly. |

A tool developer may always choose to create a location assembly, even
when it is used only once. However, tools must recognize and handle all of the
above approaches when processing OSCAL files.

{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        // cut
        "locations": [
            {
                "uuid": "11111111-2222-4000-8000-003000000002",
                "title": "Primary Data Center",
                "address": {
                    "addr-lines": ["2222 Main Street"],
                    "city": "Anywhere",
                    "state": "--",
                    "postal-code": "00000-0000",
                    "country": "US"
                },
            },
        ],
        "parties": [
            {
                "uuid": "22222222-2222-4000-8000-c0040000000a",
                "type": "organization",
                "name": "Example IaaS Provider",
                "location-uuids": ["11111111-2222-4000-8000-003000000002"]
            },
            {
                "uuid": "11111111-2222-4000-8000-004000000008",
                "type": "person",
                "name": "ICA POC's Name",
                "props": [
                    {
                        "name": "mail-stop",
                        "value": "A-1"
                    }
                ],
                "location-uuids": ["11111111-2222-4000-8000-003000000002"]
            },
        ]
        // cut
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- cut -->
    <location uuid="11111111-2222-4000-8000-003000000002">
        <title>Primary Data Center</title>
        <address type="work">
            <addr-line>2222 Main Street</addr-line>
            <city>Anywhere</city>
            <state>--</state>
            <postal-code>00000-0000</postal-code>
            <country>US</country>
        </address>
    </location>
    <party uuid="22222222-2222-4000-8000-c0040000000a" type="organization">
        <name>Example IaaS Provider</name>
        <location-uuid>11111111-2222-4000-8000-003000000002</location-uuid>
    </party>
    <party uuid="11111111-2222-4000-8000-004000000008" type="person">
        <name>ICA POC's Name</name>
        <prop name="mail-stop" value="A-1"/>
        <location-uuid>11111111-2222-4000-8000-003000000002</location-uuid>
    </party>
    <!-- cut -->
</metadata>
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  metadata:
    # cut
    locations:
    - uuid: 11111111-2222-4000-8000-003000000002
      title: Primary Data Center
      address:
        addr-lines:
        - 2222 Main Street
        city: Anywhere
        state: --
        postal-code: 00000-0000
        country: US
    parties:
    - uuid: 22222222-2222-4000-8000-c0040000000a
      type: organization
      name: 'Example IaaS Provider'
      location-uuids:
        - 11111111-2222-4000-8000-003000000002
    - uuid: 11111111-2222-4000-8000-004000000008
      type: person
      name: 'ICA POC''s Name'
      props:
      - name: mail-stop
        value: A-1
      location-uuids:
        -  11111111-2222-4000-8000-003000000002
    # cut
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


## Using Responsible Party Assemblies

The responsible party assembly links party assemblies (people and
organizations) to defined roles. FedRAMP tools rely on these linkages to
find required content.

For example, an OSCAL-based SSP must have a role defined for the System
Owner using the role ID value `system-owner`. The responsible-party
assembly links this required role to the individual (party). FedRAMP
tools follow this linkage to

1. Verify that a system owner was identified in the SSP, and
2. Display that information to reviewers.

{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        // parties
        "responsible-parties": [
            {
                "role-id": "system-owner",
                "party-uuids": ["11111111-2222-4000-8000-004000000008"]
            },
        ]
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- party -->
    <responsible-party role-id="system-owner">
        <party-uuid>11111111-2222-4000-8000-004000000008</party-uuid>
    </responsible-party>
</metadata>
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  metadata:
    # parties
    responsible-parties:
    - role-id: system-owner
      party-uuids:
      - 11111111-2222-4000-8000-004000000008
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}
 