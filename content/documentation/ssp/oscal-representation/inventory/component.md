---
title: System Inventory - Component Approach
weight: 105
---
## System Inventory: Component Approach


{{< figure src="/img/ssp-figure-26.png" title="FedRAMP OSCAL component-based inventory approach." alt="Figure illustrating the 'component-based' inventory approach where common information is captured once in a component, and each instance of that component has its own inventory-item." >}}

With the **component-based approach**, common information is captured once in a component assembly. Each instance of that component has its own inventory-item assembly, which cites the relevant component and only includes information unique to that instance.

For example, if the same Linux operating system is used as the platform for all database and web servers, most of the details about the Linux operating system can be captured once as a component. This includes information such as vendor name, version number, and patch level. If four Linux instances are used, each instance is an inventory item with a unique IP address and MAC address. Only those unique pieces are captured at the inventory level. All four inventory-items point back to the component for vendor name, version number, and patch level.

{{< figure src="/img/ssp-figure-24.png" title="FedRAMP SSP template Integrated Inventory Workbook." alt="Screenshot of the Integrated Inventory Workbook in the FedRAMP SSP template." >}}


#### Component-based Approach

##### Component-based Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "system-implementation": {
      "component": {
        "uuid": "11111111-2222-4000-8000-009001200003",
        "type": "software",
        "prop": [
          {
            "name": "virtual",
            "value": "no"
          },
          {
            "name": "software-name",
            "value": "software-name"
          },
          {
            "name": "version",
            "value": "V 0.0.0"
          },
          {
            "name": "asset-type",
            "value": "operating-system"
          },
          {
            "name": "vendor-name",
            "value": "Vendor Name"
          },
          {
            "name": "model",
            "value": "Model Number"
          },
          {
            "name": "patch-level",
            "value": "Patch-Level"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "scan-type",
            "value": "infrastructure"
          },
          {
            "name": "allows-authenticated-scan",
            "value": "no",
            "remarks": {
              "p": "If no, explain why. If yes, omit remarks field."
            }
          },
          {
            "name": "baseline-configuration-name",
            "value": "Baseline Config. Name"
          },
          {
            "name": "function",
            "value": "Required brief, text-based description.",
            "remarks": {
              "p": "Optional, longer, formatted description."
            }
          }
        ],
        "link": {
          "rel": "validation",
          "href": "#11111111-2222-4000-8000-009001200001"
        },
        "status": {
          "state": "operational"
        },
        "responsible-party": [
          {
            "role-id": "asset-owner",
            "party-id": "person-7"
          },
          {
            "role-id": "asset-administrator",
            "party-id": "it-dept"
          }
        ]
      },
      "system-inventory": {
        "inventory-item": {
          "uuid": "11111111-2222-4000-8000-011000000002",
          "description": {
            "p": "If needed, describe this instance."
          },
          "prop": [
            {
              "name": "ipv4-address",
              "value": "0.0.0.0"
            },
            {
              "name": "asset-id",
              "value": "unique-asset-ID-02"
            },
            {
              "name": "public",
              "value": "no"
            },
            {
              "name": "fqdn",
              "value": "example.com"
            },
            {
              "name": "uri",
              "value": "https://example/query?key=value#anchor"
            },
            {
              "name": "mac-address",
              "value": ">00:00:00:00:00:00"
            },
            {
              "name": "serial-number",
              "value": "Serial #"
            },
            {
              "name": "vlan-id",
              "value": "VLAN Identifier"
            },
            {
              "name": "network-id",
              "value": "Network Identifier"
            },
            {
              "name": "is-scanned",
              "value": "yes"
            }
          ],
          "implemented-component": {
            "component-uuid": "11111111-2222-4000-8000-009001200003"
          },
          "remarks": {
            "p": "COMMENTS: Additional information about this item."
          }
        }
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
    <component uuid="11111111-2222-4000-8000-009001200003" type="software">
      <prop name="virtual" value="no"/>
      <prop name="software-name" value="software-name"/>
      <prop name="version" value="V 0.0.0"/>
      <prop name="asset-type" value="operating-system"/>
      <prop name="vendor-name" value="Vendor Name"/>
      <prop name="model" value="Model Number"/>
      <prop name="patch-level" value="Patch-Level"/>
      <prop name="scan-type" ns="https://fedramp.gov/ns/oscal" value="infrastructure"/>
      <prop name="allows-authenticated-scan" value="no">
        <remarks>
          <p>If no, explain why. If yes, omit remarks field.</p>
        </remarks>
      </prop>
      <prop name="baseline-configuration-name" value="Baseline Config. Name"/>
      <prop name="function" value="Required brief, text-based description.">
        <remarks>
          <p>Optional, longer, formatted description.</p>
        </remarks>
      </prop>
      <link rel="validation" href="#11111111-2222-4000-8000-009001200001"/>
      <status state="operational"/>
      <responsible-party role-id="asset-owner">
        <party-id>person-7</party-id>
      </responsible-party>
      <responsible-party role-id="asset-administrator">
        <party-id>it-dept</party-id>
      </responsible-party>
    </component>
    <system-inventory>
      <inventory-item uuid="11111111-2222-4000-8000-011000000002">
        <description>
          <p>If needed, describe this instance.</p>
        </description>
        <prop name="asset-id" value="unique-asset-ID-02"/>
        <prop name="ipv4-address" value="0.0.0.0"/>
        <prop name="public" value="no"/>
        <prop name="fqdn" value="example.com"/>
        <prop name="uri" value="https://example/query?key=value#anchor"/>
        <prop name="mac-address" value=">00:00:00:00:00:00"/>
        <prop name="serial-number" value="Serial #"/>
        <prop name="vlan-id" value="VLAN Identifier"/>
        <prop name="network-id" value="Network Identifier"/>
        <prop name="is-scanned" value="yes"/>
        <implemented-component component-uuid="11111111-2222-4000-8000-009001200003"/>
        <remarks>
          <p>COMMENTS: Additional information about this item.</p>
        </remarks>
      </inventory-item>
    </system-inventory>
  </system-implementation>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  system-implementation:
    component:
      uuid: 11111111-2222-4000-8000-009001200003
      type: software
      prop:
        - name: virtual
          value: 'no'
        - name: software-name
          value: software-name
        - name: version
          value: V 0.0.0
        - name: asset-type
          value: operating-system
        - name: vendor-name
          value: Vendor Name
        - name: model
          value: Model Number
        - name: patch-level
          value: Patch-Level
        - ns: 'https://fedramp.gov/ns/oscal'
          name: scan-type
          value: infrastructure
        - name: allows-authenticated-scan
          value: 'no'
          remarks:
            p: 'If no, explain why. If yes, omit remarks field.'
        - name: baseline-configuration-name
          value: Baseline Config. Name
        - name: function
          value: 'Required brief, text-based description.'
          remarks:
            p: 'Optional, longer, formatted description.'
    link:
      rel: validation
      href: '#11111111-2222-4000-8000-009001200001'
    status:
      state: operational
    responsible-party:
      - role-id: asset-owner
        party-id: person-7
      - role-id: asset-administrator
        party-id: it-dept
    system-inventory:
      inventory-item:
        uuid: 11111111-2222-4000-8000-011000000002
        description:
          p: 'If needed, describe this instance.'
        prop:
          - name: ipv4-address
            value: 0.0.0.0
          - name: asset-id
            value: unique-asset-ID-02
          - name: public
            value: 'no'
          - name: fqdn
            value: example.com
          - name: uri
            value: 'https://example/query?key=value#anchor'
          - name: mac-address
            value: '>00:00:00:00:00:00'
          - name: serial-number
            value: 'Serial #'
          - name: vlan-id
            value: VLAN Identifier
          - name: network-id
            value: Network Identifier
          - name: is-scanned
            value: 'yes'
        implemented-component:
          component-uuid: 11111111-2222-4000-8000-009001200003
        remarks:
          p: 'COMMENTS: Additional information about this item.'
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

**Notes:**

-   If component-sample is an image of a Linux virtual machine (VM), and 10 instances of that VM are in use, there would be one (1) component assembly and ten (10) inventory-item assemblies, all referencing the same component.

---
#### Inventory Data Locations and XPath Queries

The following queries are intended to show where to find each piece of information within the system inventory template.

{{< figure src="/img/ssp-figure-26.1.png" title="All Inventory." alt="Figure describing guidance, valid values, requirements, cardinality, data location and other notes on fields that apply to all inventory items." >}}

{{< figure src="/img/ssp-figure-26.2.png" title="OS Infrastructure Inventory." alt="Figure describing guidance, valid values, requirements, cardinality, data location and other notes on fields that apply to OS infrastructure inventory items." >}}

{{< figure src="/img/ssp-figure-26.3.png" title="Software and Database Inventory." alt="Figure describing guidance, valid values, requirements, cardinality, data location and other notes on fields that apply to software and database inventory items." >}}

{{< figure src="/img/ssp-figure-26.4.png" title="Any Inventory." alt="Figure describing guidance, valid values, requirements, cardinality, data location and other notes on fields that apply to any inventory item." >}}

##### XPath Queries
{{< highlight xml "linenos=table" >}}
  Number of Inventory Items:
    count(/*/system-implementation/system-inventory/inventory-item)
  Number of Hardware Components:
    count(/*/system-implementation/component[@type="hardware"])
  Number of Software Components:
    count(/*/system-implementation/component[@type="software"])
  In Latest Scan?:
    /*/system-implementation/system-inventory/inventory-item[1]/prop[@name="is-scanned"]/@value

  List Inventory Items Not Scanned:
    /*/system-implementation/system-inventory/inventory-item/prop[@name="is-scanned"][@value='no']/../prop[@name='ipv4-address']
  List of Reasons Inventory Items Were Not Scanned:
    /*/system-implementation/system-inventory/inventory-item/prop[@name="is-scanned"][@value='no']/remarks/node()
{{</ highlight >}}

Unlike most XPath 2.0 queries in this
document, the following queries cannot be easily converted to XPath 1.0.
If working with XPath 1.0, it may be necessary to perform each search
with two separate queries. These queries will list all the IPv4
addresses for each scan type (infrastructure, web, and database),
whether using the flat-file inventory approach or the component-based
approach.

##### XPath Queries
{{< highlight xml "linenos=table" >}}
  IPv4 Address of All Inventory Items Identified for Infrastructure Scanning:
    distinct-values( (let $key:=/*/system-implementation/component[prop [@name='scan-type'] [@ns='https://fedramp.gov/ns/oscal']='infrastructure']/@uuid return /*/system-implementation/system-inventory/inventory-item [implemented-component/@component-uuid=$key]/ prop[@name='ipv4-address']) | (/*/system-implementation/system-inventory/inventory-item/prop[@name='ipv4-address'][../prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']  [string(.)='infrastructure']]) )
  IPv4 Address of All Inventory Items Identified for Web Scanning: 
    distinct-values( (let $key:=/*/system-implementation/component[prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']='web']/@uuid return /*/system-implementation/system-inventory/inventory-item [implemented-component/@component-uuid=$key]/prop[@name='ipv4-address']) | (/*/system-implementation/system-inventory/inventory-item/prop[@name='ipv4-address'][../prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal'][string(.)='web']]))
  IPv4 Address of All Inventory Items Identified for Database Scanning: 
    distinct-values( (let $key:=/*/system-implementation/component[prop [@name='scan-type'] [@ns='https://fedramp.gov/ns/oscal']='database']/@uuid return /*/system-implementation/system-inventory/inventory-item [implemented-component/@component-uuid=$key]/prop[@name='ipv4-address']) | (/*/system-implementation/system-inventory/inventory-item/prop[@name='ipv4-address'][../prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal'][string(.)='database']]))
  IPv4 Address of All Items Where an Authenticated Scan is Possible:
    distinct-values( (/*/system-implementation/system-inventory/inventory-item/prop [@name='ipv4-address'][../prop[@name="allows-authenticated-scan"][@value='yes']] ) | (let $key:=/*/system-implementation/component[prop [@name='allows-authenticated-scan'][@value='yes']]/@uuid return /*/system-implementation/system-inventory/inventory-item [implemented-component/@component-uuid=$key]/prop[@name='ipv4-address']))
  IPv4 Address of All Items Where an Authenticated Scan is Not Possible:
    distinct-values( (/*/system-implementation/system-inventory/inventory-item/prop[@name='ipv4-address'][../prop[@name="allows-authenticated-scan"][@value='no']] ) | ( let $key:=/*/system-implementation/component[prop [@name='allows-authenticated-scan'][@value='no']]/@uuid return /*/system-implementation/system-inventory/inventory-item [implemented-component/@component-uuid=$key]/prop[@name='ipv4-address']) )
  Authenticated Scan Justification (if Authenticate Scan is "no"):
    /*/system-implementation/system-inventory/inventory-item/prop[@name="allows-authenticated-scan"][@value="no"]/remarks/node()
  OR
    /*/system-implementation/component/prop[@name="allows-authenticated-scan"] [@value="no"]/remarks/node()
{{</ highlight >}}