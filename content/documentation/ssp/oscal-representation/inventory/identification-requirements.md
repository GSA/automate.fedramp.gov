---
title: Component Identification Requirements
weight: 120
---
# Component Identification Requirements

**Why Component Identification Matters in FedRAMP**

Proper identification of system components is fundamental to FedRAMP's security assessment process. Clear and consistent component identification enables:

- Accurate tracking of system boundaries and dependencies
- Precise mapping of security controls to components
- Efficient vulnerability management and patching
- Clear communication between CSPs, assessors, and agencies
- Effective supply chain risk management

By maintaining detailed component identification, organizations can better manage their security posture and demonstrate compliance with FedRAMP requirements.

## Vendor Name Requirements

**Description:**  
Every inventory item must have a property named "vendor-name" in the FedRAMP Extensions namespace ("http://fedramp.gov/ns/oscal"). There are two approaches to encode this information in an OSCAL SSP. The SSP can encode this property directly within the inventory item itself. Alternatively, the SSP can encode the property in the component associated with that inventory-item via the implemented-component, reducing redundancy of that identical property. This requirement ensures clear identification of component manufacturers and supports supply chain security.

**Syntax Type:** FedRAMP constraint in the FedRAMP-specific namespace

**XPath Context:** `//inventory-item`  
**XPath Target:** `. | //component[@uuid=./implemented-component/@component-uuid]`  
**XPath Expression:** `count(./prop[@name='vendor-name' @ns='http://fedramp.gov/ns/oscal' ]) >= 1`

## Software/OS Name Requirements

**Description:**  
Every inventory item where the (component) "asset-type" is "software" must have a "software-name" property (preferred) or "os-name" property where appropriate. This information can be specified either within the inventory item itself or within the component associated to that inventory item with its implemented-component.

**Why Two Properties?**
- "software-name" is the preferred property for all software components
- "os-name" is accepted for operating systems to maintain compatibility with existing implementations

**Syntax Type:** FedRAMP constraint in the FedRAMP-specific namespace

**XPath Context:** `//inventory-item`  
**XPath Target:** `. | //component[@uuid=./implemented-component/@component-uuid]`  
**XPath Expression:** `count(./prop[@name=('software-name', 'os-name') ]) >= 1`

## Software/OS Version Requirements

**Description:**  
Every software inventory item must have a "software-version" property (preferred) or "os-version" property where appropriate. Version information is crucial for security assessment, vulnerability management, and supply chain security.

**Why Version Tracking Matters:**
- Enables precise vulnerability matching
- Supports patch management
- Facilitates compliance verification
- Helps identify end-of-life components

**Syntax Type:** FedRAMP constraint in the FedRAMP-specific namespace

**XPath Context:** `//inventory-item`  
**XPath Target:** `. | //component[@uuid=./implemented-component/@component-uuid]`  
**XPath Expression:** `count(./prop[@name=('software-version', 'os-version') ]) >= 1`

## Asset Type and Function Requirements

**Description:**  
Every inventory item must have an "asset-type" property that clearly identifies its role in the system. This property can be specified either within the inventory item itself or within the component linked by the inventory item.

**Important Notes:**
- Mandatory for OS/Infrastructure and Containers
- Should be left blank for Software and Database components
- Helps determine applicable security controls and scanning requirements

**Syntax Type:** Optional core OSCAL syntax

**XPath Context:** `//inventory-item`  
**XPath Target:** `. | //component[@uuid=./implemented-component/@component-uuid]`  
**XPath Expression:** `count(./prop[@name='asset-type' ]) >= 1`

## Hardware Model Requirements

**Description:**  
Inventory items representing hardware devices must have a "hardware-model" property. This requirement ensures proper identification of physical components and supports asset management.

**When Required:**
- For all physical hardware components
- For virtual hardware when applicable
- When hardware specifications are relevant to security controls

**Syntax Type:** Optional core OSCAL syntax

**XPath Context:** `//inventory-item`  
**XPath Target:** `(. | //component[@uuid=./implemented-component/@component-uuid])/prop[@name='asset-type' @value='hardware']`  
**XPath Expression:** `count(./prop[@name='hardware-model' ]) >= 1`

## Diagram Label Requirements

**Description:**  
Every inventory item must have a "diagram-label" FedRAMP Extension to support clear system documentation and visualization. Additionally, all components not linked to inventory items must also have this label.

**Purpose:**
- Provides clear reference points in system diagrams
- Enables traceability between documentation and implementation
- Supports security assessment workflows
- Facilitates communication between stakeholders

**Syntax Type:** Mix of required, optional, and extended syntax

**First Constraint (Inventory Items):**  
**XPath Context:** `//inventory-item`  
**XPath Target:** `. | //component[@uuid=./implemented-component/@component-uuid]`  
**XPath Expression:** `count(./prop[@name='diagram-label' @ns='http://fedramp.gov/ns/oscal']) >= 1`

**Second Constraint (Standalone Components):**  
**XPath Context:** `//component[not(@uuid=//inventory-item/implemented-component/@component-uuid) and @type=('hardware', 'software', 'service', 'interconnection')]`  
**XPath Target:** `.`  
**XPath Expression:** `count(./prop[@name='diagram-label' @ns='http://fedramp.gov/ns/oscal']) = 1`

## Example Implementation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "uuid": "comp-001",
  "type": "software",
  "props": [
    {
      "name": "vendor-name",
      "ns": "http://fedramp.gov/ns/oscal",
      "value": "ExampleCorp Technologies"
    },
    {
      "name": "software-name",
      "value": "SecureApp Platform"
    },
    {
      "name": "software-version",
      "value": "4.2.1"
    },
    {
      "name": "asset-type",
      "value": "application"
    },
    {
      "name": "diagram-label",
      "ns": "http://fedramp.gov/ns/oscal",
      "value": "SA1"
    }
  ],
  "components": [
    {
      "uuid": "comp-002",
      "type": "hardware",
      "props": [
        {
          "name": "vendor-name",
          "ns": "http://fedramp.gov/ns/oscal",
          "value": "NetworkTech Inc"
        },
        {
          "name": "hardware-model",
          "value": "NT-5000"
        },
        {
          "name": "asset-type",
          "value": "network-device"
        },
        {
          "name": "diagram-label",
          "ns": "http://fedramp.gov/ns/oscal",
          "value": "RTR1"
        }
      ]
    },
    {
      "uuid": "comp-003",
      "type": "software",
      "props": [
        {
          "name": "vendor-name",
          "ns": "http://fedramp.gov/ns/oscal",
          "value": "OpenOS Foundation"
        },
        {
          "name": "os-name",
          "value": "OpenOS Enterprise"
        },
        {
          "name": "os-version",
          "value": "8.4 LTS"
        },
        {
          "name": "asset-type",
          "value": "operating-system"
        },
        {
          "name": "diagram-label",
          "ns": "http://fedramp.gov/ns/oscal",
          "value": "OS1"
        }
      ]
    }
  ]
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<component uuid="comp-001" type="software">
    <!-- Basic Component Identification -->
    <prop name="vendor-name" ns="http://fedramp.gov/ns/oscal" value="ExampleCorp Technologies"/>
    <prop name="software-name" value="SecureApp Platform"/>
    <prop name="software-version" value="4.2.1"/>
    <prop name="asset-type" value="application"/>
    <prop name="diagram-label" ns="http://fedramp.gov/ns/oscal" value="SA1"/>
    
    <!-- Hardware Example -->
    <component uuid="comp-002" type="hardware">
        <prop name="vendor-name" ns="http://fedramp.gov/ns/oscal" value="NetworkTech Inc"/>
        <prop name="hardware-model" value="NT-5000"/>
        <prop name="asset-type" value="network-device"/>
        <prop name="diagram-label" ns="http://fedramp.gov/ns/oscal" value="RTR1"/>
    </component>
    
    <!-- Operating System Example -->
    <component uuid="comp-003" type="software">
        <prop name="vendor-name" ns="http://fedramp.gov/ns/oscal" value="OpenOS Foundation"/>
        <prop name="os-name" value="OpenOS Enterprise"/>
        <prop name="os-version" value="8.4 LTS"/>
        <prop name="asset-type" value="operating-system"/>
        <prop name="diagram-label" ns="http://fedramp.gov/ns/oscal" value="OS1"/>
    </component>
</component>
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
uuid: comp-001
type: software
props:
  - name: vendor-name
    ns: http://fedramp.gov/ns/oscal
    value: ExampleCorp Technologies
  
  - name: software-name
    value: SecureApp Platform
  
  - name: software-version
    value: 4.2.1
  
  - name: asset-type
    value: application
  
  - name: diagram-label
    ns: http://fedramp.gov/ns/oscal
    value: SA1

components:
  - uuid: comp-002
    type: hardware
    props:
      - name: vendor-name
        ns: http://fedramp.gov/ns/oscal
        value: NetworkTech Inc
      
      - name: hardware-model
        value: NT-5000
      
      - name: asset-type
        value: network-device
      
      - name: diagram-label
        ns: http://fedramp.gov/ns/oscal
        value: RTR1
  
  - uuid: comp-003
    type: software
    props:
      - name: vendor-name
        ns: http://fedramp.gov/ns/oscal
        value: OpenOS Foundation
      
      - name: os-name
        value: OpenOS Enterprise
      
      - name: os-version
        value: 8.4 LTS
      
      - name: asset-type
        value: operating-system
      
      - name: diagram-label
        ns: http://fedramp.gov/ns/oscal
        value: OS1
{{< /highlight >}}
{{% /tab %}}
{{% /tabs %}}

## Best Practices

1. **Consistent Naming**: Use consistent naming conventions across all components
2. **Version Precision**: Always provide specific version numbers, not ranges or general descriptions
3. **Clear Labels**: Make diagram labels meaningful and easy to reference
4. **Property Placement**: Place common properties at the component level when possible
5. **Documentation**: Maintain clear relationships between components and inventory items
6. **Regular Updates**: Keep component identification information current as systems evolve
7. **Completeness**: Ensure all required properties are provided for each component type
