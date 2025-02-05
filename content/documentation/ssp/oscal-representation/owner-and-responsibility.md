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

{{< tabs YAML JSON XML >}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  metadata:
    parties:
    - type: organization
      name: Cloud Service Provider (CSP) Name
      uuid: 11111111-2222-4000-8000-004000000001
      short-name: CSP Acronym/Short Name
      location-uuids:
      - 11111111-2222-4000-8000-003000000001
    - type: person
      name: "[SAMPLE]Person Name 1"
      props:
      - name: job-title
        value: Individual's Title
      - name: mail-stop
        value: Mailstop A-1
      uuid: 11111111-2222-4000-8000-004000000010
      member-of-organizations:
      - 11111111-2222-4000-8000-004000000001
      email-addresses:
      - name@example.com
    roles:
    - id: system-owner
    responsible-parties:
    - role-id: system-owner
      party-uuids:
      - 11111111-2222-4000-8000-004000000010
  uuid: 11111111-2222-4000-8000-000000000000
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "metadata": {
      "roles": [
        {
          "id": "system-owner"
        }
      ],
      "parties": [
        {
          "name": "Cloud Service Provider (CSP) Name",
          "type": "organization",
          "location-uuids": [
            "11111111-2222-4000-8000-003000000001"
          ],
          "short-name": "CSP Acronym/Short Name",
          "uuid": "11111111-2222-4000-8000-004000000001"
        },
        {
          "props": [
            {
              "value": "Individual's Title",
              "name": "job-title"
            },
            {
              "value": "Mailstop A-1",
              "name": "mail-stop"
            }
          ],
          "name": "[SAMPLE]Person Name 1",
          "type": "person",
          "email-addresses": [
            "name@example.com"
          ],
          "member-of-organizations": [
            "11111111-2222-4000-8000-004000000001"
          ],
          "uuid": "11111111-2222-4000-8000-004000000010"
        }
      ],
      "responsible-parties": [
        {
          "party-uuids": [
            "11111111-2222-4000-8000-004000000010"
          ],
          "role-id": "system-owner"
        }
      ]
    },
    "uuid": "11111111-2222-4000-8000-000000000000"
  }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan xmlns="http://csrc.nist.gov/ns/oscal/1.0"
  uuid="11111111-2222-4000-8000-000000000000">
  <metadata>
    <role id="system-owner"/>
    <party uuid="11111111-2222-4000-8000-004000000001" type="organization">
      <name>Cloud Service Provider (CSP) Name</name>
      <short-name>CSP Acronym/Short Name</short-name>
      <location-uuid>11111111-2222-4000-8000-003000000001</location-uuid>
    </party>
    <party uuid="11111111-2222-4000-8000-004000000010" type="person">
      <name>[SAMPLE]Person Name 1</name>
      <prop name="job-title" value="Individual's Title"/>
      <prop name="mail-stop" value="Mailstop A-1"/>
      <email-address>name@example.com</email-address>
      <member-of-organization>11111111-2222-4000-8000-004000000001</member-of-organization>
    </party>    
    <responsible-party role-id="system-owner">
        <party-uuid>11111111-2222-4000-8000-004000000010</party-uuid>
    </responsible-party>
  </metadata>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}


## Information System Security Officer

In the FedRAMP SSP template, a CSP must identify the information system security officer (ISSO) assigned responsibility for the system like the image below.

{{< figure src="/img/ssp-figure-13.png" title="Assignment of Responsibility" alt="Screenshot of the SSP template's assignment of responsibility information." >}}

A FedRAMP OSCAL SSP encodes the security officer responsible for the system like the example below.

{{< tabs YAML JSON XML >}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  uuid: 11111111-2222-4000-8000-000000000000
  metadata:
    parties:
    - short-name: CSP Acronym/Short Name
      location-uuids:
      - 11111111-2222-4000-8000-003000000001
      type: organization
      name: Cloud Service Provider (CSP) Name
      uuid: 11111111-2222-4000-8000-004000000001
    - member-of-organizations:
      - 11111111-2222-4000-8000-004000000001
      email-addresses:
      - name@example.com
      type: person
      name: "[SAMPLE]Person Name 2"
      uuid: 11111111-2222-4000-8000-004000000011
    roles:
    - id: information-system-security-officer
    responsible-parties:
    - party-uuids:
      - 11111111-2222-4000-8000-004000000011
      role-id: information-system-security-officer
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "uuid": "11111111-2222-4000-8000-000000000000",
    "metadata": {
      "responsible-parties": [
        {
          "role-id": "information-system-security-officer",
          "party-uuids": [
            "11111111-2222-4000-8000-004000000011"
          ]
        }
      ],
      "parties": [
        {
          "name": "Cloud Service Provider (CSP) Name",
          "uuid": "11111111-2222-4000-8000-004000000001",
          "short-name": "CSP Acronym/Short Name",
          "location-uuids": [
            "11111111-2222-4000-8000-003000000001"
          ],
          "type": "organization"
        },
        {
          "name": "[SAMPLE]Person Name 2",
          "uuid": "11111111-2222-4000-8000-004000000011",
          "member-of-organizations": [
            "11111111-2222-4000-8000-004000000001"
          ],
          "email-addresses": [
            "name@example.com"
          ],
          "type": "person"
        }
      ],
      "roles": [
        {
          "id": "information-system-security-officer"
        }
      ]
    }
  }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan xmlns="http://csrc.nist.gov/ns/oscal/1.0"
  uuid="11111111-2222-4000-8000-000000000000">
  <metadata>
    <role id="information-system-security-officer"/>
    <party uuid="11111111-2222-4000-8000-004000000001" type="organization">
      <name>Cloud Service Provider (CSP) Name</name>
      <short-name>CSP Acronym/Short Name</short-name>
      <location-uuid>11111111-2222-4000-8000-003000000001</location-uuid>
    </party>
    <party uuid="11111111-2222-4000-8000-004000000011" type="person">
      <name>[SAMPLE]Person Name 2</name>
      <email-address>name@example.com</email-address>
      <member-of-organization>11111111-2222-4000-8000-004000000001</member-of-organization>
    </party>
    <responsible-party role-id="information-system-security-officer">
        <party-uuid>11111111-2222-4000-8000-004000000011</party-uuid>
    </responsible-party>
  </metadata>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}

## Authorizing Official

In the FedRAMP SSP template, a CSP and customer agency must identify the agency's authorizing official for its use of the cloud service offering like the example below.

{{< figure src="/img/ssp-figure-13.png" title="FedRAMP SSP template federal authorizing officials." alt="Screenshot of the federal authorizing official information in the FedRAMP SSP template." >}}

A FedRAMP OSCAL SSP encodes the customer agency's authorizing official like the example below.

{{< tabs YAML JSON XML >}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  uuid: 11111111-2222-4000-8000-000000000000
  metadata:
    parties:
    - short-name: GAN
      uuid: 11111111-2222-4000-8000-004000000005
      name: Government Agency Name
      type: organization
    - email-addresses:
      - name@gan.gov
      member-of-organizations:
      - 11111111-2222-4000-8000-004000000005
      uuid: 11111111-2222-4000-8000-004000000012
      name: "[SAMPLE]Person Name 3"
      type: person
    responsible-parties:
    - party-uuids:
      - 11111111-2222-4000-8000-004000000012
      role-id: authorizing-official
    roles:
    - id: authorizing-official
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "uuid": "11111111-2222-4000-8000-000000000000",
    "metadata": {
      "roles": [
        {
          "id": "authorizing-official"
        }
      ],
      "responsible-parties": [
        {
          "role-id": "authorizing-official",
          "party-uuids": [
            "11111111-2222-4000-8000-004000000012"
          ]
        }
      ],
      "parties": [
        {
          "type": "organization",
          "name": "Government Agency Name",
          "uuid": "11111111-2222-4000-8000-004000000005",
          "short-name": "GAN"
        },
        {
          "type": "person",
          "name": "[SAMPLE]Person Name 3",
          "uuid": "11111111-2222-4000-8000-004000000012",
          "member-of-organizations": [
            "11111111-2222-4000-8000-004000000005"
          ],
          "email-addresses": [
            "name@gan.gov"
          ]
        }
      ]
    }
  }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan xmlns="http://csrc.nist.gov/ns/oscal/1.0"
  uuid="11111111-2222-4000-8000-000000000000">
  <metadata>
    <role id="authorizing-official"/>
    <party uuid="11111111-2222-4000-8000-004000000005" type="organization">
      <name>Government Agency Name</name>
      <short-name>GAN</short-name>
    </party>
    <party uuid="11111111-2222-4000-8000-004000000012" type="person">
      <name>[SAMPLE]Person Name 3</name>
      <email-address>name@gan.gov</email-address>
      <member-of-organization>11111111-2222-4000-8000-004000000005</member-of-organization>
    </party>   
    <responsible-party role-id="authorizing-official">
        <party-uuid>11111111-2222-4000-8000-004000000012</party-uuid>
    </responsible-party>
  </metadata> 
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}


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

{{< tabs YAML JSON XML >}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  system-characteristics:
    props:
    - ns: http://fedramp.gov/ns/oscal
      name: authorization-type
      value: fedramp-jab
  metadata:
    responsible-parties:
    - role-id: authorizing-official
      party-uuids:
      - 11111111-2222-4000-8000-004000000012
    roles:
    - id: authorizing-official
    parties:
    - short-name: GAN
      uuid: 11111111-2222-4000-8000-004000000005
      name: Government Agency Name
      type: organization
    - member-of-organizations:
      - 11111111-2222-4000-8000-004000000005
      uuid: 11111111-2222-4000-8000-004000000012
      name: "[SAMPLE]Person Name 3"
      type: person
      email-addresses:
      - name@gan.gov
    - short-name: FedRAMP JAB
      uuid: 11111111-2222-4000-8000-004000000003
      name: "Federal Risk and Authorization Management Program: Joint Authorization Board"
      type: organization
  uuid: 11111111-2222-4000-8000-000000000000
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "uuid": "11111111-2222-4000-8000-000000000000",
    "metadata": {
      "roles": [
        {
          "id": "authorizing-official"
        }
      ],
      "responsible-parties": [
        {
          "role-id": "authorizing-official",
          "party-uuids": [
            "11111111-2222-4000-8000-004000000012"
          ]
        }
      ],
      "parties": [
        {
          "type": "organization",
          "name": "Government Agency Name",
          "uuid": "11111111-2222-4000-8000-004000000005",
          "short-name": "GAN"
        },
        {
          "type": "person",
          "name": "[SAMPLE]Person Name 3",
          "uuid": "11111111-2222-4000-8000-004000000012",
          "member-of-organizations": [
            "11111111-2222-4000-8000-004000000005"
          ],
          "email-addresses": [
            "name@gan.gov"
          ]
        }
      ]
    }
  }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan xmlns="http://csrc.nist.gov/ns/oscal/1.0"
  uuid="11111111-2222-4000-8000-000000000000">
  <metadata>
    <role id="authorizing-official"/>
    <party uuid="11111111-2222-4000-8000-004000000005" type="organization">
      <name>Government Agency Name</name>
      <short-name>GAN</short-name>
    </party>
    <party uuid="11111111-2222-4000-8000-004000000012" type="person">
      <name>[SAMPLE]Person Name 3</name>
      <email-address>name@gan.gov</email-address>
      <member-of-organization>11111111-2222-4000-8000-004000000005</member-of-organization>
    </party>
    <party uuid="11111111-2222-4000-8000-004000000003" type="organization">
      <name>Federal Risk and Authorization Management Program: Joint Authorization Board</name>
      <short-name>FedRAMP JAB</short-name>
    </party>    
    <responsible-party role-id="authorizing-official">
        <party-uuid>11111111-2222-4000-8000-004000000012</party-uuid>
    </responsible-party>
  </metadata>
  <system-characteristics>
    <prop ns="http://fedramp.gov/ns/oscal" name="authorization-type" value="fedramp-jab"/>
  </system-characteristics>  
</system-security-plan>
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

