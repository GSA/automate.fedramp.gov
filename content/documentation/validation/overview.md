---
title: Validation Overview
weight: 210
---
# OSCAL Content Validation Overview

There are several layers at which an OSCAL file can be considered
valid.
**OSCAL-based FedRAMP files must be valid at all layers.**

|**Layer**|**Description**|
| :-- | :-- |
|**Well-Formed / (_File Format Valid_)**|The XML, JSON, or YAML file follows the rules defined for that format. <br /> Any tool that processes the format will recognize it as "well-formed," which means the tool can proceed with processing the XML, JSON, or YAML.|
|**OSCAL Syntax / (_OSCAL Schema Valid_)**|The XML, JSON, YAML file, which has already been confirmed as _well-formed_,  only uses names and values defined by OSCAL.  For more information on OSCAL syntax validation, see NIST OSCAL documentation on [valid OSCAL documents and schemas for OSCAL models](https://pages.nist.gov/OSCAL/resources/concepts/validation/#what-is-a-valid-oscal-document)|
|**Core OSCAL / (_OSCAL Metaschema Valid_)**| Core OSCAL uses [Metaschema](https://github.com/usnistgov/OSCAL/blob/b123c11bd12c8b8f1bcc8bf85763e5775c0423e9/src/metaschema/readme.md) to define the model structures, and [Metaschema constraints](https://pages.nist.gov/metaschema/specification/syntax/constraints/) to validate core OSCAL data within and between document instances.|
|**FedRAMP OSCAL / (_FedRAMP Metaschema Valid_)**| Finally, FedRAMP content is enforced programmatically through its own overlay of [Metaschema-based constraints](https://github.com/GSA/fedramp-automation/tree/fc633b33e6e4ea3af9107216bf12f8d3ac4ef0cd/src/validations/constraints). For more information, see the FedRAMP [Metaschema Validation](metaschema-validation.md) and [OSCAL CLI](oscal-cli.md) documentation sections. |
