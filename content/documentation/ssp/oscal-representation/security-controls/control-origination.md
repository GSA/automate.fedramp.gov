---
title: Control Origination
weight: 120
---

## Control Origination

FedRAMP accepts only one of five values for `control-origination`:
sp-corporate, sp-system, customer-configured, customer-provided, and
inherited. Hybrid choices are expressed by identifying more than one
`control-origination`, each in a separate prop field.\
For controls with a control-id ending in \"-1\", FedRAMP only accepts
sp-corporate and sp-system.

**If the control origination is inherited,** there must also be a
FedRAMP extension (prop name=\"leveraged-authorization-uuid\"
ns=\"http://fedramp.gov/ns/oscal\") field containing the UUID of the
leveraged authorization as it appears in the
/\*/system-implementation/leveraged-authorization assembly.

{{< figure src="/img/ssp-figure-34.png" title="SSP Template Security Control Origination" alt="Screenshot of an SSP template security control origination." >}}

##### Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "system-implementation": {
      "leveraged-authorization": {
        "uuid": "uuid-of-leveraged-authorization"
      }
    },
    "control-implementation": {
      "implemented-requirement": {
        "uuid": "11111111-2222-4000-8000-012000020000",
        "control-id": "ac-2",
        "prop": [
          {
            "name": "leveraged-authorization-uuid",
            "value": "11111111-2222-4000-8000-019000000001"
          },
          {
            "ns": "http://fedramp.gov/ns/oscal",
            "name": "control-origination",
            "value": "sp-corporate"
          },
          {
            "ns": "http://fedramp.gov/ns/oscal",
            "name": "control-origination",
            "value": "sp-system"
          },
          {
            "ns": "http://fedramp.gov/ns/oscal",
            "name": "control-origination",
            "value": "customer-configured"
          },
          {
            "ns": "http://fedramp.gov/ns/oscal",
            "name": "control-origination",
            "value": "inherited"
          }
        ]
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
  <system-implementation>
    <!-- status -->
    <leveraged-authorization uuid="11111111-2222-4000-8000-019000000001">
      <!-- details cut - see Leveraged Authorizations Section -->
    </leveraged-authorization>
  </system-implementation>
  <control-implementation>
    <implemented-requirement uuid="11111111-2222-4000-8000-012000020000" control-id="ac-2">
      <prop name="leveraged-authorization-uuid" value="11111111-2222-4000-8000-019000000001"/>
      <prop ns="http://fedramp.gov/ns/oscal" name="control-origination" value="sp-corporate"/>
      <prop ns="http://fedramp.gov/ns/oscal" name="control-origination" value="sp-system"/>
      <prop ns="http://fedramp.gov/ns/oscal" name="control-origination" value="customer-configured"/>
      <prop ns="http://fedramp.gov/ns/oscal" name="control-origination" value="inherited"/>
      <!-- responsible-role -->
    </implemented-requirement>
  </control-implementation>
  <!-- back-matter -->
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  system-implementation:
    leveraged-authorization:
      uuid: "uuid-of-leveraged-authorization"
      # details cut - see Leveraged Authorizations Section
  control-implementation:
    implemented-requirement:
      uuid: "11111111-2222-4000-8000-012000020000"
      control-id: "ac-2"
      prop:
        - name: "leveraged-authorization-uuid"
          value: "11111111-2222-4000-8000-019000000001"
        - ns: "http://fedramp.gov/ns/oscal"
          name: "control-origination"
          value: "sp-corporate"
        - ns: "http://fedramp.gov/ns/oscal"
          name: "control-origination"
          value: "sp-system"
        - ns: "http://fedramp.gov/ns/oscal"
          name: "control-origination"
          value: "customer-configured"
        - ns: "http://fedramp.gov/ns/oscal"
          name: "control-origination"
          value: "inherited"
      # responsible-role (cut)
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

##### XPath Queries
{{< highlight xml "linenos=table" >}}
  Number of Control Originations:
    count(/*/control-implementation/implemented-requirement[@control-id="ac-2"]/prop[@name="control-origination"][@ns="http://fedramp.gov/ns/oscal"])
  Control Origination(could return more than 1 result):
    /*/control-implementation/implemented-requirement[@control-id="ac-2"]/prop[@name="control-origination"][@ns="http://fedramp.gov/ns/oscal"][1]/@value
  Inherited From: System Name (If control-origination="inherited"):
    /*/system-implementation/leveraged-authorization[@uuid=/*/control-implementation/implemented-requirement[@control-id="ac-2"]/prop[@name="leveraged-authorization-uuid"]]/title
  Inherited From: Authorization Date (If control-origination="inherited"):
    /*/system-implementation/leveraged-authorization[@uuid=/*/control-implementation/implemented-requirement[@control-id="ac-2"]/prop[@name="leveraged-authorization-uuid"]]/date-authorized

{{</ highlight >}}

---
