---
title: OSCAL Layers of Validation
weight: 110
---
# Multiple Layers of Validation

There are several layers at which an OSCAL file can be considered
valid.
**OSCAL-based FedRAMP files must be valid at all layers.**

|**Layer**|**Description**|
| :-- | :-- |
|**Well-Formed**|The XML or JSON file follows the rules defined for that format. <br /> Any tool that processes the format will recognize it as "well-formed," which means the tool can proceed with processing the XML or JSON. <br /> XML: [https://www.w3.org/TR/REC-xml/](https://www.w3.org/TR/REC-xml/) <br /> JSON: [https://json.org/](https://json.org/)|
|**OSCAL Syntax**|The XML or JSON file only uses names and values defined by NIST for OSCAL.  NIST publishes schema validation tools to verify syntax compliance based on the following standards: <br /> XML Syntax Validation: [XML Schema Definition Language (XSD) 1.1](https://www.w3.org/TR/xmlschema11-1/) <br /> JSON Syntax Validation: [JSON Schema, draft 07](https://json-schema.org/)|
|**OSCAL Content**| For certain OSCAL fields, the NIST syntax validation tools also enforce content - allowing only a pre-defined set of values to be used in certain fields. <br /><br /> For example, Within the SSP model, impact levels within the information type assemblies only allow the following values: `fips-199-low`, `fips-199-moderate`, and `fips-199-high`. Any other value will cause an error when validating the file. <br /><br /> In the future, NIST intends to publish more robust content enforcement mechanisms, such as [Schematron](http://schematron.com/). This enables more complex rules such as, "If field A is marked 'true', field B must have a value." FedRAMP is also exploring the use of Schematron for enhanced validation and may publish these in the future.|
|**FedRAMP Syntax Extensions**    | NIST designed OSCAL to represents the commonality of most cybersecurity frameworks and provided the ability to extend the language for framework-specific needs. FedRAMP makes use of these extensions. <br /><br />NIST provides `prop` fields throughout most of its assemblies, always with a `name`, `class`, and `ns` (namespace) flag: <br /> `<prop name="" class="" ns="">Data</prop>` <br /><br /> In the core OSCAL syntax, the `ns` flag is never used. Where FedRAMP extends OSCAL, the value for `ns` is always: <br /><br />`https://fedramp.gov/ns/oscal` (case sensitive). <br /><br /> When `ns='https://fedramp.gov/ns/oscal'` the `name` flag is as defined by FedRAMP. If the `class` flag is present, that is also defined by FedRAMP.|
|**FedRAMP Content**| Today, FedRAMP content is enforced programmatically. FedRAMP intends to publish automated validation rules, which may be adopted by tool developers to verify OSCAL-based FedRAMP content is acceptable before submission. <br /><br />Initial validation rules ensure a package has all required elements and will evolve to perform more detailed validation. Separate details will be published about this in the near future.|

