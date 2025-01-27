---
title: Scanning and Security Requirements
weight: 130
---
# Scanning and Security Requirements

**Why Scanning Matters in FedRAMP**

Security scanning is a critical component of FedRAMP's continuous monitoring strategy. Regular scanning helps identify vulnerabilities, misconfigurations, and potential security weaknesses before they can be exploited. By requiring clear documentation of scanning practices for each component:

- Security teams can maintain comprehensive coverage of the system
- Auditors can verify that all components are appropriately monitored
- Organizations can justify and document cases where standard scanning approaches may not be applicable

This structured approach to scanning documentation ensures that no component falls through the cracks in the security monitoring process.

## Scan Inclusion Requirements

**Description:**  
Every software inventory item must have an "is-scanned" property either within the inventory item itself or within the component linked by the inventory item. This property serves as a clear indicator of whether the component is included in security scanning processes.

**Syntax Type:** Optional core OSCAL syntax

**XPath Context:** `//inventory-item`  
**XPath Target:** `. | //component[@uuid=./implemented-component/@component-uuid]`  
**XPath Expression:** `count(./prop[@name='is-scanned']) >= 1`

## Scan Type Requirements

**Description:**  
Every software inventory item must indicate one or more scan types, either within the inventory item itself or within the component linked by the inventory item. This requirement ensures that appropriate scanning methodologies are applied based on the component's nature and function.

**Syntax Type:** FedRAMP constraint in the FedRAMP-specific namespace

**First Constraint:**  
**XPath Context:** `//inventory-item`  
**XPath Target:** `. | //component[@uuid=./implemented-component/@component-uuid]`  
**XPath Expression:** `exists(./prop[@name='scan-type' @ns='http://fedramp.gov/ns/oscal'])`

**Allowed Values:**
- **infrastructure**: Component is scanned with an infrastructure or operating system vulnerability scanner
  - *Used for*: Operating systems, network devices, infrastructure components
- **database**: Component is scanned with a database vulnerability scanner
  - *Used for*: Database servers, database instances, data storage systems
- **web**: Component is scanned with a web vulnerability scanner
  - *Used for*: Web applications, web services, APIs
- **other**: Component is scanned with a non-typical vulnerability scanner
  - *Used for*: Specialized components requiring custom scanning tools
  - *Requires*: Detailed explanation in remarks
- **not-applicable**: Scanning does not apply to this component
  - *Used for*: Components that cannot or should not be scanned
  - *Requires*: Justification in remarks

**Remarks Requirement:**  
If the scan-type is set to 'other' or 'not-applicable', a remarks field must be present explaining why standard scanning methods are not suitable and what alternative security measures are in place.

**XPath Expression for Remarks:** `exists(target=". | //component[@uuid=./implemented-component/@component-uuid]/prop[@name='scan-type' @ns='http://fedramp.gov/ns/oscal' @value=('other', 'not-applicable')]/remarks")`

## Example Implementation

{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "uuid": "comp-001",
  "type": "software",
  "props": [
    {
      "name": "is-scanned",
      "value": "yes"
    },
    {
      "name": "scan-type",
      "ns": "http://fedramp.gov/ns/oscal",
      "value": "web"
    },
    {
      "name": "scan-type",
      "ns": "http://fedramp.gov/ns/oscal",
      "value": "database"
    },
    {
      "name": "scan-type",
      "ns": "http://fedramp.gov/ns/oscal",
      "value": "other",
      "remarks": {
        "paragraphs": [
          "Custom security scanning tool (SecurityScan Pro v3.2) used for specialized application components. This tool provides deep inspection of proprietary protocols and custom configurations specific to our implementation."
        ]
      }
    },
    {
      "name": "scan-type",
      "ns": "http://fedramp.gov/ns/oscal",
      "value": "not-applicable",
      "remarks": {
        "paragraphs": [
          "This is a read-only configuration component that runs in an isolated environment. Security is maintained through strict access controls and continuous configuration validation. Standard vulnerability scanning would not provide meaningful results for this component type."
        ]
      }
    }
  ]
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<component uuid="comp-001" type="software">
    <!-- Basic scan configuration -->
    <prop name="is-scanned" value="yes"/>
    <prop name="scan-type" ns="http://fedramp.gov/ns/oscal" value="web"/>
    
    <!-- Example with multiple scan types -->
    <prop name="scan-type" ns="http://fedramp.gov/ns/oscal" value="database"/>
    
    <!-- Example with 'other' scan type -->
    <prop name="scan-type" ns="http://fedramp.gov/ns/oscal" value="other">
        <remarks>
            <p>Custom security scanning tool (SecurityScan Pro v3.2) used for specialized application components. 
            This tool provides deep inspection of proprietary protocols and custom configurations specific to our implementation.</p>
        </remarks>
    </prop>
    
    <!-- Example with 'not-applicable' -->
    <prop name="scan-type" ns="http://fedramp.gov/ns/oscal" value="not-applicable">
        <remarks>
            <p>This is a read-only configuration component that runs in an isolated environment. 
            Security is maintained through strict access controls and continuous configuration validation.
            Standard vulnerability scanning would not provide meaningful results for this component type.</p>
        </remarks>
    </prop>
</component>
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
uuid: comp-001
type: software
props:
  - name: is-scanned
    value: "yes"
  
  - name: scan-type
    namespace: http://fedramp.gov/ns/oscal
    value: web
  
  - name: scan-type
    namespace: http://fedramp.gov/ns/oscal
    value: database
  
  - name: scan-type
    namespace: http://fedramp.gov/ns/oscal
    value: other
    remarks:
      paragraphs:
        - >-
          Custom security scanning tool (SecurityScan Pro v3.2) used for specialized
          application components. This tool provides deep inspection of proprietary
          protocols and custom configurations specific to our implementation.
  
  - name: scan-type
    ns: http://fedramp.gov/ns/oscal
    value: not-applicable
    remarks:
      paragraphs:
        - >-
          This is a read-only configuration component that runs in an isolated
          environment. Security is maintained through strict access controls and
          continuous configuration validation. Standard vulnerability scanning
          would not provide meaningful results for this component type.    
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}

## Best Practices

1. **Clear Documentation**: Always provide detailed explanations in remarks when using 'other' or 'not-applicable' scan types
2. **Multiple Scan Types**: When a component requires multiple types of scanning, include multiple scan-type properties
3. **Consistency**: Maintain consistent scanning documentation across similar component types
4. **Justification**: Ensure that any deviation from standard scanning approaches is well-justified and documented
5. **Regular Review**: Periodically review scan type assignments to ensure they remain appropriate as the system evolves
