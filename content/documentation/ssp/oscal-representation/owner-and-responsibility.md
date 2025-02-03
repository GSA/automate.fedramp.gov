---
title: System Owner and Assignment of Responsibility
weight: 110
---
# System Owner and Assignment of Responsibility

FedRAMP requires clearly defined roles and assignment of responsibility for those roles in a SSP. The cloud service offering's system owner, security officer, and the customer agency's authorizing official are important roles described below.

## Parties and Roles in OSCAL

In a FedRAMP OSCAL SSP, OSCAL must encode information about the relevant `party`, define a `role`, and only then bind them together. For a `party`, this data includes a required unique identifier; required type of `party` (whether it is an individual person or organization); an optional binding between a party (`member-of-organization`) and their organization if that party is a person; and information about their location for address and contact information.

## System Owner

In the FedRAMP SSP template, a CSP must identify the system owner for the cloud service offering in the relevant table like below.

{{< figure src="/img/ssp-figure-12.png" alt="Screenshot of the SSP template's system owner information." >}}

A FedRAMP OSCAL SSP encodes the system owner like the example below.

{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan" : {
    "metadata" : {
      "parties": [
        {
            "uuid": "11111111-2222-4000-8000-004000000010",
            "type": "person",
            "name": "[SAMPLE]Person Name 1",
            "props": [
                {
                    "name": "job-title",
                    "value": "Individual's Title"
                },
                {
                    "name": "mail-stop",
                    "value": "Mailstop A-1"
                }
            ],
            "email-addresses": ["name@example.com"],
            "telephone-numbers": [
                {"number": "2020000001"}
            ],
            "location-uuids": ["11111111-2222-4000-8000-003000000001"],
            "member-of-organizations": ["11111111-2222-4000-8000-004000000001"]
        },
        {
            "uuid": "11111111-2222-4000-8000-004000000001",
            "type": "organization",
            "name": "Cloud Service Provider (CSP) Name",
            "short-name": "CSP Acronym/Short Name",
            "links": [
                {
                    "href": "#11111111-2222-4000-8000-001000000052",
                    "rel": "logo"
                }
            ],
            "location-uuids": ["11111111-2222-4000-8000-003000000001"],
            "remarks": "Replace sample CSP information.\n\nCSP information must be present and associated with the \\\"cloud-service-provider\\\" role via `responsible-party`."
        }
      ]
    },
    "uuid" : "12345678-1234-4321-8765-123456789012"
  }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan uuid="12345678-1234-4321-8765-123456789012">
    <metadata>
      <party uuid="11111111-2222-4000-8000-004000000010" type="person">
        <name>[SAMPLE]Person Name 1</name>
        <prop name="job-title" value="Individual's Title"/>
        <prop name="mail-stop" value="Mailstop A-1"/>
        <email-address>name@example.com</email-address>
        <telephone-number>2020000001</telephone-number>
        <location-uuid>11111111-2222-4000-8000-003000000001</location-uuid>
        <member-of-organization>11111111-2222-4000-8000-004000000001</member-of-organization>
      </party>
      <party uuid="11111111-2222-4000-8000-004000000001" type="organization">
        <name>Cloud Service Provider (CSP) Name</name>
        <short-name>CSP Acronym/Short Name</short-name>
        <link href="#11111111-2222-4000-8000-001000000052" rel="logo"/>
        <location-uuid>11111111-2222-4000-8000-003000000001</location-uuid>
        <remarks>
          <p>Replace sample CSP information.</p>
          <p>CSP information must be present and associated with the "cloud-service-provider" role via
              <code>responsible-party</code>.</p>
        </remarks>
      </party>      
    </metadata>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  uuid: 12345678-1234-4321-8765-123456789012
  metadata:
    - uuid: 11111111-2222-4000-8000-004000000010
      type: person
      name: '[SAMPLE]Person Name 1'
      props:
      - name: job-title
        value: Individual's Title
      - name: mail-stop
        value: Mailstop A-1
      email-addresses:
      - name@example.com
      telephone-numbers:
      - number: '2020000001'
      location-uuids:
      - 11111111-2222-4000-8000-003000000001
      member-of-organizations:
      - 11111111-2222-4000-8000-004000000001
    - uuid: 11111111-2222-4000-8000-004000000001
      type: organization
      name: Cloud Service Provider (CSP) Name
      short-name: CSP Acronym/Short Name
      links:
      - href: '#11111111-2222-4000-8000-001000000052'
        rel: logo
      location-uuids:
      - 11111111-2222-4000-8000-003000000001
      remarks: |-
        Replace sample CSP information.

        CSP information must be present and associated with the \"cloud-service-provider\" role via `responsible-party`.
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}


## Information System Security Officer

In the FedRAMP SSP template, a CSP must identify the information system security officer (ISSO) assigned responsibility for the system like the image below.

{{< figure src="/img/ssp-figure-13.png" title="Assignment of Responsibility" alt="Screenshot of the SSP template's assignment of responsibility information." >}}

## Authorizing Official

A role with an ID value of `authorizing-official` is required. Use the responsible-party assembly to associate this role with the party assembly containing the Authorizing Official's information.

{{< figure src="/img/ssp-figure-13.png" title="FedRAMP SSP template federal authorizing officials." alt="Screenshot of the federal authorizing official information in the FedRAMP SSP template." >}}

##### Federal Agency Authorization Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <role id="authorizing-official">
        <title>Authorizing Official</title>
    </role>
    <party uuid="uuid-of-agency" type="organization">
        <name>Agency Name</name>
    </party>
    <party uuid="uuid-of-person-6" type="person">
        <name>[SAMPLE]Person Name 6</name>
        <prop name="job-title" value="Individual's Title"/>
            <email-address>name@example.com</email-address>
            <telephone-number>202-000-0000</telephone-number>
            <member-of-organization>uuid-of-agency</member-of-organization>
    </party>
    <role id="authorizing-official"/>
    <responsible-party role-id="authorizing-official">
        <party-uuid>uuid-of-person-6</party-uuid>
    </responsible-party>
</metadata>>
<system-characteristics>
    <prop ns="https://fedramp.gov/ns/oscal" name="authorization-type" value="fedramp-agency" />
</system-characteristics>
{{</ highlight >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    FedRAMP Authorization Type:
        /*/system-characteristics/prop[@name="authorization-type"][@ns="https://fedramp.gov/ns/oscal"]/@value
    Authorizing Official’s Name:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="authorizing-official"]/party-uuid]]/name
    NOTE: Replace "name" with "email-address" or "telephone-number" above as needed.
    Authorizing Official’s Title:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="authorizing-official"]/party-uuid]]/prop[@name='job-title']
    Authorizing Official's Agency:
        /*/metadata/party[@uuid=/*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="authorizing-official"]/party-uuid]]/member-of-organization]/name
{{</ highlight >}}

**NOTE:**

If the authorization-type field is "fedramp-jab", the responsible-party/party-uuid field must be the uuid value for the FedRAMP JAB.

---
#### Federal JAB P-ATO Authorization Representation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan" : {
    "uuid" : "11111111-2222-4000-8000-000000000000",
    "metadata" : {
      "parties" : [ {
        "short-name" : "FedRAMP JAB",
        "type" : "organization",
        "name" : "FedRAMP: Joint Authorization Board",
        "uuid" : "11111111-2222-4000-8000-004000000003"
      } ],
      "roles" : [ {
        "id" : "authorizing-official",
        "title" : "Authorizing Official"
      } ],
      "responsible-parties" : [ {
        "party-uuids" : [ "11111111-2222-4000-8000-004000000003" ],
        "role-id" : "authorizing-official"
      } ]
    },
    "system-characteristics" : {
      "props" : [ {
        "ns" : "https://fedramp.gov/ns/oscal",
        "value" : "fedramp-jab",
        "name" : "authorization-type"
      } ]
    }
  }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
    <metadata>
        <role id="authorizing-official">
            <title>Authorizing Official</title>
            <desc>The government executive(s) who authorize this system.</desc>
        </role>
        <party uuid="uuid-of-fedramp-jab" type="organization">
            <name>FedRAMP: Joint Authorization Board</name>
            <short-name>FedRAMP JAB</short-name>
        </party>
        <responsible-party role-id="authorizing-official">
            <party-uuid>uuid-of-fedramp-jab</party-uuid>
        </responsible-party>
    </metadata>
    <system-characteristics>
        <prop ns="https://fedramp.gov/ns/oscal" name="authorization-type" value="fedramp-jab"/>
    </system-characteristics>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
Converting 'file:/private/tmp/example.xml'.
---
system-security-plan:
  system-characteristics:
    props:
    - name: authorization-type
      value: fedramp-jab
      ns: https://fedramp.gov/ns/oscal
  metadata:
    responsible-parties:
    - role-id: authorizing-official
      party-uuids:
      - 11111111-2222-4000-8000-004000000003
    roles:
    - title: Authorizing Official
      id: authorizing-official
    parties:
    - uuid: 11111111-2222-4000-8000-004000000003
      name: "FedRAMP: Joint Authorization Board"
      type: organization
      short-name: FedRAMP JAB
  uuid: 11111111-2222-4000-8000-000000000000
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Authorizing Official’s Name:
        //metadata/party[@uuid=[//metadata/responsible-party[@role-id="authorizing-official"]/party-uuid]]/name
{{</ highlight >}}

<br />
{{<callout>}}

**FedRAMP Extension:**

prop (ns="https://fedramp.gov/ns/oscal")
- name="authorization-type" 

**FedRAMP Allowed Values**
- fedramp-jab
- fedramp-agency
- fedramp-li-saas

**OSCAL Allowed Value**

Required Role ID:
- authorizing-official

{{</callout>}}


---

