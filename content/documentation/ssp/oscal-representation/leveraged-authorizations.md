---
title: Leveraged Authorizations
weight: 334
---
## Leveraged Authorizations and FedRAMP-authorized Services

If this system is leveraging the authorization of one or more systems, such as a SaaS running on an IaaS, each leveraged system must be represented within the system-implementation assembly. There must be one leveraged-authorization assembly and one matching component assembly for each leveraged authorization.

The leveraged-authorization assembly includes the leveraged system's name, point of contact (POC), and authorization date. The component assembly must be linked to the leveraged-authorization assembly using a property (prop) field with the name leveraged-authorization-uuid and the
UUID value of its associated leveraged-authorization assembly. The component assembly enables controls to reference it with the by-component responses described in the [*Control Implementation Descriptions*](/documentation/ssp/6-security-controls/#control-implementation-descriptions) section. The implementation-point property value must be set to "external".

If the leveraged system owner provides a UUID for their system, such as in an OSCAL-based Inheritance and Responsibility document (similar to a CRM), it should be provided as the inherited-uuid property value.

{{< figure src="/img/ssp-figure-15.png" title="FedRAMP SSP template leveraged FedRAMP-authorized services." alt="Screenshot of the leveraged FedRAMP-authorized service information in the FedRAMP SSP template." >}}

<br />
{{<callout>}}

**IMPORTANT FOR LEVERAGED SYSTEMS:**

While a leveraged system has no need to represent content here, its SSP must include special inheritance and responsibility information in the individual controls. See the [*Response: Identifying Inheritable Controls and Customer Responsibilities*](/documentation/ssp/6-security-controls/#response-identifying-inheritable-controls-and-customer-responsibilities) section for more information.

{{</callout>}}

#### OSCAL Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "metadata": {
    "party": {
      "uuid": "22222222-2222-4000-8000-c0040000000a",
      "name": "Example IaaS Provider",
      "short-name": "E.I.P."
    }
  },
  "system-implementation": {
    "leveraged-authorization": {
      "uuid": "11111111-2222-4000-8000-019000000001",
      "title": "Name of Underlying System",
      "prop": [
        {
          "name": "leveraged-system-identifier",
          "ns": "https://fedramp.gov/ns/oscal",
          "value": "Package_ID value"
        },
        {
          "ns": "https://fedramp.gov/ns/oscal",
          "name": "authorization-type",
          "value": "fedramp-agency"
        },
        {
          "ns": "https://fedramp.gov/ns/oscal",
          "name": "impact-level",
          "value": "moderate"
        }
      ],
      "party-uuid": "11111111-2222-4000-8000-c0040000000a",
      "date-authorized": "2015-01-01"
    },
    "component": {
      "uuid": "uuid-of-leveraged-system",
      "type": "leveraged-system",
      "title": "Name of Leveraged System",
      "description": {
        "p": "Briefly describe leveraged system."
      },
      "prop": [
        {
          "name": "leveraged-authorization-uuid",
          "value": "11111111-2222-4000-8000-019000000001"
        },
        {
          "name": "inherited-uuid",
          "value": "22222222-0000-4000-9001-009000000001"
        },
        {
          "name": "implementation-point",
          "value": "external"
        }
      ],
      "status": {
        "state": "operational"
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- CSP name -->
    <party uuid="22222222-2222-4000-8000-c0040000000a">
        <name>Example IaaS Provider</name>
        <short-name>E.I.P.</short-name>
    </party>
</metadata>
<!-- cut import-profile, system-characteristics -->
<system-implementation>
    <leveraged-authorization uuid="11111111-2222-4000-8000-019000000001">
        <title>Name of Underlying System</title>
        <!-- FedRAMP Package ID -->
        <prop name="leveraged-system-identifier" ns="https://fedramp.gov/ns/oscal" value="Package_ID value" />
        <prop ns="https://fedramp.gov/ns/oscal" name="authorization-type" value="fedramp-agency"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="impact-level" value="moderate"/>
        <party-uuid>11111111-2222-4000-8000-c0040000000a</party-uuid>
        <date-authorized>2015-01-01</date-authorized>
    </leveraged-authorization>
    <!-- CSO name & service description -->
    <component uuid="uuid-of-leveraged-system" type="leveraged-system">
        <title>Name of Leveraged System</title>
        <description>
            <p>Briefly describe leveraged system.</p>
        </description>
        <prop name="leveraged-authorization-uuid" value="11111111-2222-4000-8000-019000000001" />
        <prop name="inherited-uuid" value="22222222-0000-4000-9001-009000000001" />
        <prop name="implementation-point" value="external"/>
        <!-- FedRAMP prop extensions for table 6.1 columns -->
        <status state="operational"/>
    </component>
</system-implementation>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
metadata:
  party:
    uuid: "22222222-2222-4000-8000-c0040000000a"
    name: "Example IaaS Provider"
    short-name: "E.I.P."
system-implementation:
  leveraged-authorization:
    uuid: "11111111-2222-4000-8000-019000000001"
    title: "Name of Underlying System"
    prop:
      - name: leveraged-system-identifier
        ns: "https://fedramp.gov/ns/oscal"
        value: "Package_ID value"
      - ns: "https://fedramp.gov/ns/oscal"
        name: authorization-type
        value: fedramp-agency
      - ns: "https://fedramp.gov/ns/oscal"
        name: impact-level
        value: moderate
    party-uuid: "11111111-2222-4000-8000-c0040000000a"
    date-authorized: "2015-01-01"
  component:
    uuid: "uuid-of-leveraged-system"
    type: leveraged-system
    title: "Name of Leveraged System"
    description:
      p: "Briefly describe leveraged system."
    prop:
      - name: leveraged-authorization-uuid
        value: "11111111-2222-4000-8000-019000000001"
      - name: inherited-uuid
        value: "22222222-0000-4000-9001-009000000001"
      - name: implementation-point
        value: external
    status:
      state: operational
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

<br />
{{<callout>}}

The title field must match an existing [FedRAMP authorized Cloud_Service_Provider_Package](https://raw.githubusercontent.com/18F/fedramp-data/master/data/data.json) property value.

A leveraged-system-identifier property must be provided within each leveraged-authorization field.  The value of this property must be from the same Cloud Service Provider as identified in the title field.

{{</callout>}}
<br />

---
