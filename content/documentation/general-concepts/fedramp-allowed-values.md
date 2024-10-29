---
title: FedRAMP Allowed Values 
weight: 150
---
# FedRAMP Allowed Values

To facilitate consistent processing, the value for property names,
annotation names, and some field values is limited to a list of
*case-sensitive* allowed values. In many instances, OSCAL defines allowed
values, which are enforced by OSCAL-based syntax validation mechanisms.

In some cases, FedRAMP defines or adds allowed values specific to
FedRAMP ATO processing. Where defined, only these values are recognized
by FedRAMP processing tools.

For example, every control requires an implementation status. FedRAMP
only accepts one of five possible responses for this status, which must
be provided using one of the specified choices.

## Allowed Value Constraints 

FedRAMP allowed values are cited in relevant portions of the online documentation and summarized in these sub-sections:
- [SSP Allowed Values](#ssp-allowed-values)
- [SAP Allowed Values](#sap-allowed-values)
- [SAR Allowed Values](#sar-allowed-values)
- [POA&amp;M Allowed Values](#poam-allowed-values)
- [Other Allowed Values](#other-allowed-values)

### SSP Allowed Values

#### /System Security Plan/Back Matter/Resource/Citation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/back-matter/resource/citation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Back Matter/Resource/Citation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/back-matter/resource/citation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Back Matter/Resource/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/back-matter/resource/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /System Security Plan/Back Matter/Resource/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>version</li><li>published</li></ul> | False | builtin |
| [Location](/system-security-plan/back-matter/resource/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Back Matter/Resource/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| attachment-type | [Location](/system-security-plan) | back-matter/resource/prop[@name='type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>law</li><li>regulation</li><li>standard</li><li>guidance</li><li>policy</li><li>procedure</li><li>guide</li><li>rules-of-behavior</li><li>plan</li><li>system-security-plan</li><li>artifact</li><li>evidence</li><li>screen-shot</li><li>image</li><li>tool-report</li><li>raw-tool-output</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>fedramp-citations</li><li>fedramp-acronyms</li><li>fedramp-logo</li><li>separation-of-duties-matrix</li><li>logo</li><li>personally-identifiable-information</li><li>agreement</li><li>isa-agreement</li><li>incident-response-plan</li><li>information-security-policies-and-procedures</li><li>users-guide</li><li>privacy-impact-assessment</li><li>information-system-contingency-plan</li><li>configuration-management-plan</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/system-security-plan/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>logo</li><li>image</li><li>screen-shot</li><li>law</li><li>regulation</li><li>standard</li><li>external-guidance</li><li>acronyms</li><li>citation</li><li>policy</li><li>procedure</li><li>system-guide</li><li>users-guide</li><li>administrators-guide</li><li>rules-of-behavior</li><li>plan</li><li>artifact</li><li>evidence</li><li>tool-output</li><li>raw-data</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>agreement</li></ul> | False | builtin |

#### /System Security Plan/Back Matter/Resource/Rlink/Hash/@Algorithm

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/back-matter/resource/rlink/hash/@algorithm) | . | <ul><li>SHA-224</li><li>SHA-256</li><li>SHA-384</li><li>SHA-512</li><li>SHA3-224</li><li>SHA3-256</li><li>SHA3-384</li><li>SHA3-512</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Provided/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/provided/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Provided/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/provided/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Provided/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Provided/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/provided/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Provided/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/provided/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Responsibility/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/responsibility/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Responsibility/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/responsibility/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Responsibility/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Responsibility/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/responsibility/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Export/Responsibility/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/export/responsibility/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Implementation Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/implementation-status/@state) | . | <ul><li>implemented</li><li>partial</li><li>planned</li><li>alternative</li><li>not-applicable</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Inherited/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/inherited/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Inherited/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/inherited/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Inherited/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Inherited/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/inherited/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Inherited/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/inherited/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component) | link/@rel | <ul><li>imported-from</li></ul> | True | builtin |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component) | link/@rel | <ul><li>provided-by</li></ul> | True | builtin |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement) | (.|statement|.//by-component)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>control-origination</li></ul> | False | builtin |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| control-implementation-status | [Location](/system-security-plan) | control-implementation/implemented-requirement/by-component/prop[@name='implementation-status']/@value | <ul><li>implemented</li><li>partial</li><li>planned</li><li>alternative</li><li>not-applicable</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/system-security-plan/control-implementation/implemented-requirement) | (.|statement|.//by-component)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='control-origination']/@value | <ul><li>organization</li><li>system-specific</li><li>customer-configured</li><li>customer-provided</li><li>inherited</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Satisfied/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/satisfied/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Satisfied/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/satisfied/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Satisfied/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Satisfied/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/satisfied/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/By Component/Satisfied/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/by-component/satisfied/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement) | (.|statement|.//by-component)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>control-origination</li></ul> | False | builtin |
| [Location](/system-security-plan/control-implementation/implemented-requirement/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement) | (.|statement|.//by-component)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='control-origination']/@value | <ul><li>organization</li><li>system-specific</li><li>customer-configured</li><li>customer-provided</li><li>inherited</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement) | responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Provided/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/provided/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Provided/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/provided/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Provided/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Provided/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/provided/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Provided/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/provided/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Responsibility/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/responsibility/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Responsibility/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/responsibility/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Responsibility/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Responsibility/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/responsibility/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Export/Responsibility/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/export/responsibility/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Implementation Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/implementation-status/@state) | . | <ul><li>implemented</li><li>partial</li><li>planned</li><li>alternative</li><li>not-applicable</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Inherited/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/inherited/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Inherited/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/inherited/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Inherited/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Inherited/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/inherited/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Inherited/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/inherited/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component) | link/@rel | <ul><li>imported-from</li></ul> | True | builtin |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component) | link/@rel | <ul><li>provided-by</li></ul> | True | builtin |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement) | (.|statement|.//by-component)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>control-origination</li></ul> | False | builtin |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement) | (.|statement|.//by-component)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='control-origination']/@value | <ul><li>organization</li><li>system-specific</li><li>customer-configured</li><li>customer-provided</li><li>inherited</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Satisfied/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/satisfied/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Satisfied/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/satisfied/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Satisfied/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component) | [Target](.//responsible-role/@role-id) | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Satisfied/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/satisfied/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/By Component/Satisfied/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/by-component/satisfied/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement) | (.|statement|.//by-component)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>control-origination</li></ul> | False | builtin |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement) | (.|statement|.//by-component)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='control-origination']/@value | <ul><li>organization</li><li>system-specific</li><li>customer-configured</li><li>customer-provided</li><li>inherited</li></ul> | False | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement) | responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Control Implementation/Implemented Requirement/Statement/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/control-implementation/implemented-requirement/statement/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Action/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/action/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Action/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/action/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Action/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/action/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Action/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/action/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>latest-version</li><li>predecessor-version</li><li>successor-version</li></ul> | True | builtin |
| [Location](/system-security-plan/metadata/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Location/Address/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/location/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Location/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/location/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Location/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type' and @value='data-center']/@class | <ul><li>primary</li><li>alternate</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Location/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/system-security-plan/metadata/location/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Location/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>data-center</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Location/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/location/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Party/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/party/@type) | . | <ul><li>person</li><li>organization</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Party/Address/@Type

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| address-type | [Location](/system-security-plan) | metadata/party/address/@type | <ul><li>work</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/system-security-plan/metadata/party/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Party/External Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/party/external-id/@scheme) | . | <ul><li>http://orcid.org/</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/party) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>mail-stop</li><li>office</li><li>job-title</li></ul> | False | builtin |
| [Location](/system-security-plan/metadata/party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Party/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/party/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>keywords</li></ul> | False | builtin |
| [Location](/system-security-plan/metadata/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Responsible Party/@Role Id

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| allowed-metadata-responsibe-party-role-ids | [Location](/system-security-plan/metadata) | responsible-party/@role-id | <ul><li>creator</li><li>prepared-by</li><li>prepared-for</li><li>content-approver</li><li>contact</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Revision/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/revision) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>predecessor-version</li><li>successor-version</li><li>version-history</li></ul> | True | builtin |
| [Location](/system-security-plan/metadata/revision/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Revision/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/revision/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/Metadata/Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/Metadata/Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/metadata/role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Authorization Boundary/Diagram/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/authorization-boundary/diagram) | link/@rel | <ul><li>diagram</li></ul> | True | builtin |
| [Location](/system-security-plan/system-characteristics/authorization-boundary/diagram/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/Authorization Boundary/Diagram/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/authorization-boundary/diagram/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Authorization Boundary/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/authorization-boundary/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/Authorization Boundary/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/authorization-boundary/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Data Flow/Diagram/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/data-flow/diagram) | link/@rel | <ul><li>diagram</li></ul> | True | builtin |
| [Location](/system-security-plan/system-characteristics/data-flow/diagram/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/Data Flow/Diagram/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/data-flow/diagram/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Data Flow/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/data-flow/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/Data Flow/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/data-flow/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/Network Architecture/Diagram/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/network-architecture/diagram) | link/@rel | <ul><li>diagram</li></ul> | True | builtin |
| [Location](/system-security-plan/system-characteristics/network-architecture/diagram/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/Network Architecture/Diagram/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/network-architecture/diagram/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Network Architecture/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/network-architecture/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/Network Architecture/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/network-architecture/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>identity-assurance-level</li><li>authenticator-assurance-level</li><li>federation-assurance-level</li></ul> | False | builtin |
| [Location](/system-security-plan/system-characteristics) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>cloud-deployment-model</li><li>cloud-service-model</li></ul> | False | builtin |
| [Location](/system-security-plan/system-characteristics/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| authorization-type | [Location](/system-security-plan) | system-characteristics/prop[@name='authorization-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>fedramp-jab</li><li>fedramp-agency</li><li>fedramp-li-saas</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
| deployment-model | [Location](/system-security-plan) | system-characteristics/prop[@name='cloud-deployment-model'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>public-cloud</li><li>private-cloud</li><li>government-only-cloud</li><li>hybrid-cloud</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
| authorization-type | [Location](/system-security-plan) | system-characteristics/prop[@name='authorization-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>fedramp-jab</li><li>fedramp-agency</li><li>fedramp-li-saas</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
| cloud-service-model | [Location](/system-security-plan) | system-characteristics/prop[@name='cloud-service-model'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>iaas</li><li>paas</li><li>saas</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/system-security-plan/system-characteristics) | prop[@name=('identity-assurance-level','authenticator-assurance-level','federation-assurance-level')]/@value | <ul><li>1</li><li>2</li><li>3</li></ul> | False | builtin |
|  | [Location](/system-security-plan/system-characteristics) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='cloud-deployment-model']/@value | <ul><li>public-cloud</li><li>private-cloud</li><li>community-cloud</li><li>hybrid-cloud</li><li>government-only-cloud</li><li>other</li></ul> | False | builtin |
|  | [Location](/system-security-plan/system-characteristics) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='cloud-service-model']/@value | <ul><li>saas</li><li>paas</li><li>iaas</li><li>other</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Responsible Party/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics) | responsible-party/@role-id | <ul><li>authorizing-official</li><li>authorizing-official-poc</li><li>system-owner</li><li>system-poc-management</li><li>system-poc-technical</li><li>system-poc-other</li><li>information-system-security-officer</li><li>privacy-poc</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/status/@state) | . | <ul><li>operational</li><li>under-development</li><li>under-major-modification</li><li>disposition</li><li>other</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/System Id/@Identifier Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-id/@identifier-type) | . | <ul><li>https://fedramp.gov</li><li>http://fedramp.gov/ns/oscal</li><li>https://ietf.org/rfc/rfc4122</li><li>http://ietf.org/rfc/rfc4122</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Availability Impact/Base

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information) | information-type/(confidentiality-impact|integrity-impact|availability-impact)/(base|selected) | <ul><li>fips-199-low</li><li>fips-199-moderate</li><li>fips-199-high</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Availability Impact/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information/information-type/availability-impact/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Availability Impact/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information/information-type/availability-impact/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Availability Impact/Selected

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information) | information-type/(confidentiality-impact|integrity-impact|availability-impact)/(base|selected) | <ul><li>fips-199-low</li><li>fips-199-moderate</li><li>fips-199-high</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Categorization/@System

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| information-type-system | [Location](/system-security-plan) | system-characteristics/system-information/information-type/categorization/@system | <ul><li>https://doi.org/10.6028/NIST.SP.800-60v2r1</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/system-security-plan/system-characteristics/system-information/information-type/categorization/@system) | . | <ul><li>http://doi.org/10.6028/NIST.SP.800-60v2r1</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Confidentiality Impact/Base

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information) | information-type/(confidentiality-impact|integrity-impact|availability-impact)/(base|selected) | <ul><li>fips-199-low</li><li>fips-199-moderate</li><li>fips-199-high</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Confidentiality Impact/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information/information-type/confidentiality-impact/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Confidentiality Impact/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information/information-type/confidentiality-impact/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Confidentiality Impact/Selected

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information) | information-type/(confidentiality-impact|integrity-impact|availability-impact)/(base|selected) | <ul><li>fips-199-low</li><li>fips-199-moderate</li><li>fips-199-high</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Integrity Impact/Base

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information) | information-type/(confidentiality-impact|integrity-impact|availability-impact)/(base|selected) | <ul><li>fips-199-low</li><li>fips-199-moderate</li><li>fips-199-high</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Integrity Impact/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information/information-type/integrity-impact/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Integrity Impact/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information/information-type/integrity-impact/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Integrity Impact/Selected

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information) | information-type/(confidentiality-impact|integrity-impact|availability-impact)/(base|selected) | <ul><li>fips-199-low</li><li>fips-199-moderate</li><li>fips-199-high</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information/information-type/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Information Type/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information/information-type/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/System Information/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information) | link/@rel | <ul><li>privacy-impact-assessment</li></ul> | True | builtin |
| [Location](/system-security-plan/system-characteristics/system-information/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Characteristics/System Information/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>privacy-designation</li></ul> | False | builtin |
| [Location](/system-security-plan/system-characteristics/system-information/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Characteristics/System Information/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-characteristics/system-information) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='privacy-designation']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Component/@Type

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| component-type | [Location](/system-security-plan) | system-implementation/component/@type | <ul><li>interconnection</li><li>software</li><li>hardware</li><li>service</li><li>policy</li><li>physical</li><li>process-procedure</li><li>plan</li><li>guidance</li><li>standard</li><li>validation</li><li>this-system</li><li>system</li><li>network</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/system-security-plan/system-implementation/component/@type) | . | <ul><li>this-system</li><li>system</li><li>interconnection</li><li>software</li><li>hardware</li><li>service</li><li>policy</li><li>physical</li><li>process-procedure</li><li>plan</li><li>guidance</li><li>standard</li><li>validation</li><li>network</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/component) | link/@rel | <ul><li>depends-on</li><li>validation</li><li>proof-of-compliance</li><li>baseline-template</li><li>uses-service</li><li>system-security-plan</li><li>uses-network</li><li>imported-from</li></ul> | True | builtin |
| [Location](/system-security-plan/system-implementation/component) | (.)[@type='validation']/link/@rel | <ul><li>validation-details</li></ul> | True | builtin |
| [Location](/system-security-plan/system-implementation/component) | (.)[@type='service']/link/@rel | <ul><li>provided-by</li><li>used-by</li></ul> | True | builtin |
| [Location](/system-security-plan/system-implementation/component) | (.)[@type='interconnection']/link/@rel | <ul><li>isa-agreement</li></ul> | True | builtin |
| [Location](/system-security-plan/system-implementation/component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Component/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('ipv4-address','ipv6-address')]/@class | <ul><li>local</li><li>remote</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>implementation-point</li><li>leveraged-authorization-uuid</li><li>inherited-uuid</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li></ul> | False | builtin |
| [Location](/system-security-plan/system-implementation/component) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/system-security-plan/system-implementation/component) | (.)[@type='software']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>software-identifier</li></ul> | False | builtin |
| [Location](/system-security-plan/system-implementation/component) | (.)[@type='interconnection']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>isa-title</li><li>isa-date</li><li>isa-remote-system-name</li><li>ipv4-address</li><li>ipv6-address</li><li>direction</li></ul> | False | builtin |
| [Location](/system-security-plan/system-implementation/component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Component/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| interconnection-direction | [Location](/system-security-plan) | system-implementation/component[@type='interconnection']/prop[@name='interconnection-direction'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>in</li><li>out</li><li>in/out</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
| interconnection-security | [Location](/system-security-plan) | system-implementation/component[@type='interconnection']/prop[@name='interconnection-security'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>ipsec</li><li>vpn</li><li>tls</li><li>dtls</li><li>certificate</li><li>secure-file-transfer</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
| scan-type | [Location](/system-security-plan) | system-implementation//prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>infrastructure</li><li>database</li><li>web</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/system-security-plan/system-implementation) | (component | inventory-item)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
|  | [Location](/system-security-plan/system-implementation/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
|  | [Location](/system-security-plan/system-implementation/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
|  | [Location](/system-security-plan/system-implementation/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='public']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
|  | [Location](/system-security-plan/system-implementation/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='virtual']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
|  | [Location](/system-security-plan/system-implementation/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='implementation-point']/@value | <ul><li>internal</li><li>external</li></ul> | False | builtin |
|  | [Location](/system-security-plan/system-implementation/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='direction']/@value | <ul><li>incoming</li><li>outgoing</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Component/Protocol/Port Range/@Transport

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/component/protocol/port-range/@transport) | . | <ul><li>TCP</li><li>UDP</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/component) | responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |
| [Location](/system-security-plan/system-implementation/component) | (.)[@type='interconnection']/responsible-role/@role-id | <ul><li>isa-poc-local</li><li>isa-poc-remote</li><li>isa-authorizing-official-local</li><li>isa-authorizing-official-remote</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Component/Responsible Role/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| scan-type | [Location](/system-security-plan) | system-implementation//prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>infrastructure</li><li>database</li><li>web</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |

#### /System Security Plan/System Implementation/Component/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/component/status/@state) | . | <ul><li>under-development</li><li>operational</li><li>disposition</li><li>other</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Implemented Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item/implemented-component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Implemented Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item/implemented-component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li></ul> | False | builtin |
| [Location](/system-security-plan/system-implementation/inventory-item/implemented-component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Implemented Component/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| scan-type | [Location](/system-security-plan) | system-implementation//prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>infrastructure</li><li>database</li><li>web</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |

#### /System Security Plan/System Implementation/Inventory Item/Implemented Component/Responsible Party/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item/implemented-component) | responsible-party/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Implemented Component/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item/implemented-component/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Implemented Component/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item/implemented-component/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Implemented Component/Responsible Party/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| scan-type | [Location](/system-security-plan) | system-implementation//prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>infrastructure</li><li>database</li><li>web</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |

#### /System Security Plan/System Implementation/Inventory Item/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item) | link/@rel | <ul><li>baseline-template</li></ul> | True | builtin |
| [Location](/system-security-plan/system-implementation/inventory-item/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>ipv4-address</li><li>ipv6-address</li><li>fqdn</li><li>uri</li><li>serial-number</li><li>netbios-name</li><li>mac-address</li><li>physical-location</li><li>is-scanned</li><li>hardware-model</li><li>os-name</li><li>os-version</li><li>software-name</li><li>software-version</li><li>software-patch-level</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li></ul> | False | builtin |
| [Location](/system-security-plan/system-implementation/inventory-item) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/system-security-plan/system-implementation/inventory-item/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| scan-type | [Location](/system-security-plan) | system-implementation//prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>infrastructure</li><li>database</li><li>web</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/system-security-plan/system-implementation) | (component | inventory-item)/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
|  | [Location](/system-security-plan/system-implementation/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
|  | [Location](/system-security-plan/system-implementation/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='is-scanned']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Responsible Party/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item) | responsible-party/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/inventory-item/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Inventory Item/Responsible Party/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| scan-type | [Location](/system-security-plan) | system-implementation//prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>infrastructure</li><li>database</li><li>web</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |

#### /System Security Plan/System Implementation/Leveraged Authorization/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/leveraged-authorization) | link/@rel | <ul><li>system-security-plan</li></ul> | True | builtin |
| [Location](/system-security-plan/system-implementation/leveraged-authorization/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Leveraged Authorization/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/leveraged-authorization/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Leveraged Authorization/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| scan-type | [Location](/system-security-plan) | system-implementation//prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>infrastructure</li><li>database</li><li>web</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |

#### /System Security Plan/System Implementation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| scan-type | [Location](/system-security-plan) | system-implementation//prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>infrastructure</li><li>database</li><li>web</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |

#### /System Security Plan/System Implementation/User/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/user/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /System Security Plan/System Implementation/User/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/user) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>privilege-level</li></ul> | False | builtin |
| [Location](/system-security-plan/system-implementation/user/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/User/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| scan-type | [Location](/system-security-plan) | system-implementation//prop[@name='scan-type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>infrastructure</li><li>database</li><li>web</li><li>other</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
| user-type | [Location](/system-security-plan) | system-implementation/user/prop[@name='type']/@value | <ul><li>internal</li><li>external</li><li>privileged</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
| privilege-level | [Location](/system-security-plan) | system-implementation/user/prop[@name='privilege-level']/@value | <ul><li>read</li><li>read-write</li><li>write</li><li>no-access</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/system-security-plan/system-implementation/user) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>internal</li><li>external</li><li>general-public</li></ul> | False | builtin |
|  | [Location](/system-security-plan/system-implementation/user) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='privilege-level']/@value | <ul><li>privileged</li><li>non-privileged</li><li>no-logical-access</li></ul> | False | builtin |

#### /System Security Plan/System Implementation/User/Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/system-security-plan/system-implementation/user) | role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li></ul> | True | builtin |

---

### SAP Allowed Values

#### /Assessment Plan/Assessment Assets/Assessment Platform/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/assessment-platform/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Assets/Assessment Platform/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/assessment-platform/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Assets/Assessment Platform/Uses Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/assessment-platform/uses-component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Assets/Assessment Platform/Uses Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/assessment-platform/uses-component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Assets/Assessment Platform/Uses Component/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/assessment-platform/uses-component/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Assets/Assessment Platform/Uses Component/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/assessment-platform/uses-component/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Assets/Component/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component/@type) | . | <ul><li>this-system</li><li>system</li><li>interconnection</li><li>software</li><li>hardware</li><li>service</li><li>policy</li><li>physical</li><li>process-procedure</li><li>plan</li><li>guidance</li><li>standard</li><li>validation</li><li>network</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Assets/Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component) | link/@rel | <ul><li>depends-on</li><li>validation</li><li>proof-of-compliance</li><li>baseline-template</li><li>uses-service</li><li>system-security-plan</li><li>uses-network</li><li>imported-from</li></ul> | True | builtin |
| [Location](/assessment-plan/assessment-assets/component) | (.)[@type='validation']/link/@rel | <ul><li>validation-details</li></ul> | True | builtin |
| [Location](/assessment-plan/assessment-assets/component) | (.)[@type='service']/link/@rel | <ul><li>provided-by</li><li>used-by</li></ul> | True | builtin |
| [Location](/assessment-plan/assessment-assets/component) | (.)[@type='interconnection']/link/@rel | <ul><li>isa-agreement</li></ul> | True | builtin |
| [Location](/assessment-plan/assessment-assets/component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Assets/Component/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('ipv4-address','ipv6-address')]/@class | <ul><li>local</li><li>remote</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Assets/Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>implementation-point</li><li>leveraged-authorization-uuid</li><li>inherited-uuid</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li></ul> | False | builtin |
| [Location](/assessment-plan/assessment-assets/component) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/assessment-plan/assessment-assets/component) | (.)[@type='software']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>software-identifier</li></ul> | False | builtin |
| [Location](/assessment-plan/assessment-assets/component) | (.)[@type='interconnection']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>isa-title</li><li>isa-date</li><li>isa-remote-system-name</li><li>ipv4-address</li><li>ipv6-address</li><li>direction</li></ul> | False | builtin |
| [Location](/assessment-plan/assessment-assets/component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Assets/Component/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/assessment-plan/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-plan/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='public']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-plan/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='virtual']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-plan/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='implementation-point']/@value | <ul><li>internal</li><li>external</li></ul> | False | builtin |
| [Location](/assessment-plan/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='direction']/@value | <ul><li>incoming</li><li>outgoing</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Assets/Component/Protocol/Port Range/@Transport

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component/protocol/port-range/@transport) | . | <ul><li>TCP</li><li>UDP</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Assets/Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component) | responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |
| [Location](/assessment-plan/assessment-assets/component) | (.)[@type='interconnection']/responsible-role/@role-id | <ul><li>isa-poc-local</li><li>isa-poc-remote</li><li>isa-authorizing-official-local</li><li>isa-authorizing-official-remote</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Assets/Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Assets/Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Assets/Component/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-assets/component/status/@state) | . | <ul><li>under-development</li><li>operational</li><li>disposition</li><li>other</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Assessment Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Assessment Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/assessment-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Back Matter/Resource/Citation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/back-matter/resource/citation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Back Matter/Resource/Citation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/back-matter/resource/citation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Back Matter/Resource/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/back-matter/resource/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Assessment Plan/Back Matter/Resource/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>version</li><li>published</li></ul> | False | builtin |
| [Location](/assessment-plan/back-matter/resource/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Back Matter/Resource/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| attachment-type | [Location](/assessment-plan) | back-matter/resource/prop[@name='type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>law</li><li>regulation</li><li>standard</li><li>guidance</li><li>policy</li><li>procedure</li><li>guide</li><li>rules-of-behavior</li><li>plan</li><li>system-security-plan</li><li>artifact</li><li>evidence</li><li>screen-shot</li><li>image</li><li>tool-report</li><li>raw-tool-output</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>fedramp-citations</li><li>fedramp-acronyms</li><li>fedramp-logo</li><li>separation-of-duties-matrix</li><li>logo</li><li>personally-identifiable-information</li><li>agreement</li><li>isa-agreement</li><li>incident-response-plan</li><li>information-security-policies-and-procedures</li><li>users-guide</li><li>privacy-impact-assessment</li><li>information-system-contingency-plan</li><li>configuration-management-plan</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/assessment-plan/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>logo</li><li>image</li><li>screen-shot</li><li>law</li><li>regulation</li><li>standard</li><li>external-guidance</li><li>acronyms</li><li>citation</li><li>policy</li><li>procedure</li><li>system-guide</li><li>users-guide</li><li>administrators-guide</li><li>rules-of-behavior</li><li>plan</li><li>artifact</li><li>evidence</li><li>tool-output</li><li>raw-data</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>agreement</li></ul> | False | builtin |

#### /Assessment Plan/Back Matter/Resource/Rlink/Hash/@Algorithm

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/back-matter/resource/rlink/hash/@algorithm) | . | <ul><li>SHA-224</li><li>SHA-256</li><li>SHA-384</li><li>SHA-512</li><li>SHA3-224</li><li>SHA3-256</li><li>SHA3-384</li><li>SHA3-512</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/activity/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Related Controls/Control Objective Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/related-controls/control-objective-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Related Controls/Control Objective Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/related-controls/control-objective-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Related Controls/Control Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/related-controls/control-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Related Controls/Control Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/related-controls/control-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Related Controls/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/related-controls/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Related Controls/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/related-controls/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Reviewed Controls/Control Objective Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/reviewed-controls/control-objective-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Reviewed Controls/Control Objective Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/reviewed-controls/control-objective-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Reviewed Controls/Control Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/reviewed-controls/control-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Reviewed Controls/Control Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/reviewed-controls/control-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Reviewed Controls/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/reviewed-controls/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Activity/Step/Reviewed Controls/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/activity/step/reviewed-controls/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Component/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component/@type) | . | <ul><li>this-system</li><li>system</li><li>interconnection</li><li>software</li><li>hardware</li><li>service</li><li>policy</li><li>physical</li><li>process-procedure</li><li>plan</li><li>guidance</li><li>standard</li><li>validation</li><li>network</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component) | link/@rel | <ul><li>depends-on</li><li>validation</li><li>proof-of-compliance</li><li>baseline-template</li><li>uses-service</li><li>system-security-plan</li><li>uses-network</li><li>imported-from</li></ul> | True | builtin |
| [Location](/assessment-plan/local-definitions/component) | (.)[@type='validation']/link/@rel | <ul><li>validation-details</li></ul> | True | builtin |
| [Location](/assessment-plan/local-definitions/component) | (.)[@type='service']/link/@rel | <ul><li>provided-by</li><li>used-by</li></ul> | True | builtin |
| [Location](/assessment-plan/local-definitions/component) | (.)[@type='interconnection']/link/@rel | <ul><li>isa-agreement</li></ul> | True | builtin |
| [Location](/assessment-plan/local-definitions/component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Component/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('ipv4-address','ipv6-address')]/@class | <ul><li>local</li><li>remote</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>implementation-point</li><li>leveraged-authorization-uuid</li><li>inherited-uuid</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/component) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/component) | (.)[@type='software']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>software-identifier</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/component) | (.)[@type='interconnection']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>isa-title</li><li>isa-date</li><li>isa-remote-system-name</li><li>ipv4-address</li><li>ipv6-address</li><li>direction</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Component/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/assessment-plan/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='public']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='virtual']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='implementation-point']/@value | <ul><li>internal</li><li>external</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='direction']/@value | <ul><li>incoming</li><li>outgoing</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Component/Protocol/Port Range/@Transport

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component/protocol/port-range/@transport) | . | <ul><li>TCP</li><li>UDP</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component) | responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |
| [Location](/assessment-plan/local-definitions/component) | (.)[@type='interconnection']/responsible-role/@role-id | <ul><li>isa-poc-local</li><li>isa-poc-remote</li><li>isa-authorizing-official-local</li><li>isa-authorizing-official-remote</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Component/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/component/status/@state) | . | <ul><li>under-development</li><li>operational</li><li>disposition</li><li>other</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Implemented Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item/implemented-component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Implemented Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item/implemented-component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/inventory-item/implemented-component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Implemented Component/Responsible Party/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item/implemented-component) | responsible-party/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Implemented Component/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item/implemented-component/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Implemented Component/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item/implemented-component/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item) | link/@rel | <ul><li>baseline-template</li></ul> | True | builtin |
| [Location](/assessment-plan/local-definitions/inventory-item/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>ipv4-address</li><li>ipv6-address</li><li>fqdn</li><li>uri</li><li>serial-number</li><li>netbios-name</li><li>mac-address</li><li>physical-location</li><li>is-scanned</li><li>hardware-model</li><li>os-name</li><li>os-version</li><li>software-name</li><li>software-version</li><li>software-patch-level</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/inventory-item) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/inventory-item/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/assessment-plan/local-definitions/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='is-scanned']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Responsible Party/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item) | responsible-party/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Inventory Item/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/inventory-item/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Objectives And Methods/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/objectives-and-methods/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Objectives And Methods/Part/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/objectives-and-methods) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>objective</li><li>assessment</li><li>assessment-objective</li><li>assessment-method</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Objectives And Methods/Part/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/objectives-and-methods/part/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/Objectives And Methods/Part/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/objectives-and-methods/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/objectives-and-methods/part/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/objectives-and-methods/part/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/Objectives And Methods/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/objectives-and-methods/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/User/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/user/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Local Definitions/User/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/user) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>privilege-level</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/user/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/User/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/user) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>internal</li><li>external</li><li>general-public</li></ul> | False | builtin |
| [Location](/assessment-plan/local-definitions/user) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='privilege-level']/@value | <ul><li>privileged</li><li>non-privileged</li><li>no-logical-access</li></ul> | False | builtin |

#### /Assessment Plan/Local Definitions/User/Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/local-definitions/user) | role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Action/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/action/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Action/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/action/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Action/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/action/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Action/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/action/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>latest-version</li><li>predecessor-version</li><li>successor-version</li></ul> | True | builtin |
| [Location](/assessment-plan/metadata/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Location/Address/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/location/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Location/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/location/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Location/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type' and @value='data-center']/@class | <ul><li>primary</li><li>alternate</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Location/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/assessment-plan/metadata/location/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Location/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>data-center</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Location/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/location/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Party/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/party/@type) | . | <ul><li>person</li><li>organization</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Party/Address/@Type

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| address-type | [Location](/assessment-plan) | metadata/party/address/@type | <ul><li>work</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/assessment-plan/metadata/party/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Party/External Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/party/external-id/@scheme) | . | <ul><li>http://orcid.org/</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/party) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>mail-stop</li><li>office</li><li>job-title</li></ul> | False | builtin |
| [Location](/assessment-plan/metadata/party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Party/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/party/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>keywords</li></ul> | False | builtin |
| [Location](/assessment-plan/metadata/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Responsible Party/@Role Id

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| allowed-metadata-responsibe-party-role-ids | [Location](/assessment-plan/metadata) | responsible-party/@role-id | <ul><li>creator</li><li>prepared-by</li><li>prepared-for</li><li>content-approver</li><li>contact</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Revision/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/revision) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>predecessor-version</li><li>successor-version</li><li>version-history</li></ul> | True | builtin |
| [Location](/assessment-plan/metadata/revision/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Revision/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/revision/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Metadata/Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Metadata/Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/metadata/role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Reviewed Controls/Control Objective Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/reviewed-controls/control-objective-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Reviewed Controls/Control Objective Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/reviewed-controls/control-objective-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Reviewed Controls/Control Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/reviewed-controls/control-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Reviewed Controls/Control Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/reviewed-controls/control-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Reviewed Controls/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/reviewed-controls/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Reviewed Controls/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/reviewed-controls/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/@type) | . | <ul><li>milestone</li><li>action</li></ul> | True | builtin |

#### /Assessment Plan/Task/Associated Activity/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Associated Activity/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Associated Activity/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Associated Activity/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Associated Activity/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Plan/Task/Associated Activity/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Plan/Task/Associated Activity/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Associated Activity/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Associated Activity/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Plan/Task/Associated Activity/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Associated Activity/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Associated Activity/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Associated Activity/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/associated-activity/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Plan/Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Plan/Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Plan/Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Plan/Task/Timing/At Frequency/@Unit

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/task/timing/at-frequency/@unit) | . | <ul><li>seconds</li><li>minutes</li><li>hours</li><li>days</li><li>months</li><li>years</li></ul> | False | builtin |

#### /Assessment Plan/Terms And Conditions/Part/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/terms-and-conditions) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>rules-of-engagement</li><li>disclosures</li><li>assessment-inclusions</li><li>assessment-exclusions</li><li>results-delivery</li><li>assumptions</li><li>methodology</li></ul> | False | builtin |
| [Location](/assessment-plan/terms-and-conditions/part/@name) | . | <ul><li>asset</li><li>method</li><li>objective</li></ul> | True | builtin |

#### /Assessment Plan/Terms And Conditions/Part/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/terms-and-conditions/part/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Plan/Terms And Conditions/Part/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/terms-and-conditions/part) | .[@name='objective']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/assessment-plan/terms-and-conditions/part/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/assessment-plan/terms-and-conditions/part/part) | .[@name='objective']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |

#### /Assessment Plan/Terms And Conditions/Part/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-plan/terms-and-conditions/part) | .[@name='objective']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |
| [Location](/assessment-plan/terms-and-conditions/part/part) | .[@name='objective']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |

---

### SAR Allowed Values

#### /Assessment Results/Back Matter/Resource/Citation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/back-matter/resource/citation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Back Matter/Resource/Citation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/back-matter/resource/citation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Back Matter/Resource/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/back-matter/resource/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Assessment Results/Back Matter/Resource/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>version</li><li>published</li></ul> | False | builtin |
| [Location](/assessment-results/back-matter/resource/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Back Matter/Resource/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| attachment-type | [Location](/assessment-results) | back-matter/resource/prop[@name='type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>law</li><li>regulation</li><li>standard</li><li>guidance</li><li>policy</li><li>procedure</li><li>guide</li><li>rules-of-behavior</li><li>plan</li><li>system-security-plan</li><li>artifact</li><li>evidence</li><li>screen-shot</li><li>image</li><li>tool-report</li><li>raw-tool-output</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>fedramp-citations</li><li>fedramp-acronyms</li><li>fedramp-logo</li><li>separation-of-duties-matrix</li><li>logo</li><li>personally-identifiable-information</li><li>agreement</li><li>isa-agreement</li><li>incident-response-plan</li><li>information-security-policies-and-procedures</li><li>users-guide</li><li>privacy-impact-assessment</li><li>information-system-contingency-plan</li><li>configuration-management-plan</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/assessment-results/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>logo</li><li>image</li><li>screen-shot</li><li>law</li><li>regulation</li><li>standard</li><li>external-guidance</li><li>acronyms</li><li>citation</li><li>policy</li><li>procedure</li><li>system-guide</li><li>users-guide</li><li>administrators-guide</li><li>rules-of-behavior</li><li>plan</li><li>artifact</li><li>evidence</li><li>tool-output</li><li>raw-data</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>agreement</li></ul> | False | builtin |

#### /Assessment Results/Back Matter/Resource/Rlink/Hash/@Algorithm

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/back-matter/resource/rlink/hash/@algorithm) | . | <ul><li>SHA-224</li><li>SHA-256</li><li>SHA-384</li><li>SHA-512</li><li>SHA3-224</li><li>SHA3-256</li><li>SHA3-384</li><li>SHA3-512</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/assessment-results/local-definitions/activity/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Related Controls/Control Objective Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/related-controls/control-objective-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Related Controls/Control Objective Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/related-controls/control-objective-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Related Controls/Control Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/related-controls/control-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Related Controls/Control Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/related-controls/control-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Related Controls/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/related-controls/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Related Controls/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/related-controls/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Reviewed Controls/Control Objective Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/reviewed-controls/control-objective-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Reviewed Controls/Control Objective Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/reviewed-controls/control-objective-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Reviewed Controls/Control Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/reviewed-controls/control-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Reviewed Controls/Control Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/reviewed-controls/control-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Reviewed Controls/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/reviewed-controls/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Activity/Step/Reviewed Controls/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/activity/step/reviewed-controls/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Objectives And Methods/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/objectives-and-methods/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Objectives And Methods/Part/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/objectives-and-methods) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>objective</li><li>assessment</li><li>assessment-objective</li><li>assessment-method</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Objectives And Methods/Part/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/objectives-and-methods/part/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Local Definitions/Objectives And Methods/Part/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/objectives-and-methods/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/assessment-results/local-definitions/objectives-and-methods/part/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/assessment-results/local-definitions/objectives-and-methods/part/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |

#### /Assessment Results/Local Definitions/Objectives And Methods/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/local-definitions/objectives-and-methods/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Action/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/action/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Action/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/action/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Action/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/action/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Action/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/action/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>latest-version</li><li>predecessor-version</li><li>successor-version</li></ul> | True | builtin |
| [Location](/assessment-results/metadata/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Location/Address/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/location/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Location/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/location/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Location/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type' and @value='data-center']/@class | <ul><li>primary</li><li>alternate</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Location/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/assessment-results/metadata/location/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Location/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>data-center</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Location/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/location/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Party/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/party/@type) | . | <ul><li>person</li><li>organization</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Party/Address/@Type

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| address-type | [Location](/assessment-results) | metadata/party/address/@type | <ul><li>work</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/assessment-results/metadata/party/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Party/External Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/party/external-id/@scheme) | . | <ul><li>http://orcid.org/</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/party) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>mail-stop</li><li>office</li><li>job-title</li></ul> | False | builtin |
| [Location](/assessment-results/metadata/party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Party/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/party/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>keywords</li></ul> | False | builtin |
| [Location](/assessment-results/metadata/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Responsible Party/@Role Id

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| allowed-metadata-responsibe-party-role-ids | [Location](/assessment-results/metadata) | responsible-party/@role-id | <ul><li>creator</li><li>prepared-by</li><li>prepared-for</li><li>content-approver</li><li>contact</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Revision/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/revision) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>predecessor-version</li><li>successor-version</li><li>version-history</li></ul> | True | builtin |
| [Location](/assessment-results/metadata/revision/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Revision/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/revision/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Metadata/Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Metadata/Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/metadata/role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Assessment Log/Entry/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/assessment-log/entry/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Attestation/Part/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/attestation/part/@name) | . | <ul><li>asset</li><li>method</li><li>objective</li></ul> | True | builtin |

#### /Assessment Results/Result/Attestation/Part/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/attestation/part/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Attestation/Part/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/attestation/part) | .[@name='objective']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/assessment-results/result/attestation/part/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/assessment-results/result/attestation/part/part) | .[@name='objective']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |

#### /Assessment Results/Result/Attestation/Part/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/attestation/part) | .[@name='objective']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |
| [Location](/assessment-results/result/attestation/part/part) | .[@name='objective']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |

#### /Assessment Results/Result/Attestation/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/attestation/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Attestation/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/attestation/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Target/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/target/@type) | . | <ul><li>statement-id</li><li>objective-id</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Target/Implementation Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/target/implementation-status/@state) | . | <ul><li>implemented</li><li>partial</li><li>planned</li><li>alternative</li><li>not-applicable</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Target/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/target/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Target/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/target/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Finding/Target/Status/@Reason

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/target/status/@reason) | . | <ul><li>pass</li><li>fail</li><li>other</li></ul> | True | builtin |

#### /Assessment Results/Result/Finding/Target/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/finding/target/status/@state) | . | <ul><li>satisfied</li><li>not-satisfied</li></ul> | False | builtin |

#### /Assessment Results/Result/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Assessment Platform/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/assessment-platform/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Assessment Platform/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/assessment-platform/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Assessment Platform/Uses Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/assessment-platform/uses-component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Assessment Platform/Uses Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/assessment-platform/uses-component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Assessment Platform/Uses Component/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/assessment-platform/uses-component/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Assessment Platform/Uses Component/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/assessment-platform/uses-component/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component/@type) | . | <ul><li>this-system</li><li>system</li><li>interconnection</li><li>software</li><li>hardware</li><li>service</li><li>policy</li><li>physical</li><li>process-procedure</li><li>plan</li><li>guidance</li><li>standard</li><li>validation</li><li>network</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | link/@rel | <ul><li>depends-on</li><li>validation</li><li>proof-of-compliance</li><li>baseline-template</li><li>uses-service</li><li>system-security-plan</li><li>uses-network</li><li>imported-from</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | (.)[@type='validation']/link/@rel | <ul><li>validation-details</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | (.)[@type='service']/link/@rel | <ul><li>provided-by</li><li>used-by</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | (.)[@type='interconnection']/link/@rel | <ul><li>isa-agreement</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('ipv4-address','ipv6-address')]/@class | <ul><li>local</li><li>remote</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>implementation-point</li><li>leveraged-authorization-uuid</li><li>inherited-uuid</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | (.)[@type='software']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>software-identifier</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | (.)[@type='interconnection']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>isa-title</li><li>isa-date</li><li>isa-remote-system-name</li><li>ipv4-address</li><li>ipv6-address</li><li>direction</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='public']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='virtual']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='implementation-point']/@value | <ul><li>internal</li><li>external</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='direction']/@value | <ul><li>incoming</li><li>outgoing</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/Protocol/Port Range/@Transport

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component/protocol/port-range/@transport) | . | <ul><li>TCP</li><li>UDP</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component) | (.)[@type='interconnection']/responsible-role/@role-id | <ul><li>isa-poc-local</li><li>isa-poc-remote</li><li>isa-authorizing-official-local</li><li>isa-authorizing-official-remote</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Assets/Component/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-assets/component/status/@state) | . | <ul><li>under-development</li><li>operational</li><li>disposition</li><li>other</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/@type) | . | <ul><li>milestone</li><li>action</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Associated Activity/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/associated-activity/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Assessment Task/Timing/At Frequency/@Unit

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/assessment-task/timing/at-frequency/@unit) | . | <ul><li>seconds</li><li>minutes</li><li>hours</li><li>days</li><li>months</li><li>years</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Component/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component/@type) | . | <ul><li>this-system</li><li>system</li><li>interconnection</li><li>software</li><li>hardware</li><li>service</li><li>policy</li><li>physical</li><li>process-procedure</li><li>plan</li><li>guidance</li><li>standard</li><li>validation</li><li>network</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component) | link/@rel | <ul><li>depends-on</li><li>validation</li><li>proof-of-compliance</li><li>baseline-template</li><li>uses-service</li><li>system-security-plan</li><li>uses-network</li><li>imported-from</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/component) | (.)[@type='validation']/link/@rel | <ul><li>validation-details</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/component) | (.)[@type='service']/link/@rel | <ul><li>provided-by</li><li>used-by</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/component) | (.)[@type='interconnection']/link/@rel | <ul><li>isa-agreement</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Component/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('ipv4-address','ipv6-address')]/@class | <ul><li>local</li><li>remote</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>implementation-point</li><li>leveraged-authorization-uuid</li><li>inherited-uuid</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/component) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/component) | (.)[@type='software']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>software-identifier</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/component) | (.)[@type='interconnection']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>isa-title</li><li>isa-date</li><li>isa-remote-system-name</li><li>ipv4-address</li><li>ipv6-address</li><li>direction</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Component/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='public']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='virtual']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='implementation-point']/@value | <ul><li>internal</li><li>external</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='direction']/@value | <ul><li>incoming</li><li>outgoing</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Component/Protocol/Port Range/@Transport

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component/protocol/port-range/@transport) | . | <ul><li>TCP</li><li>UDP</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component) | responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/component) | (.)[@type='interconnection']/responsible-role/@role-id | <ul><li>isa-poc-local</li><li>isa-poc-remote</li><li>isa-authorizing-official-local</li><li>isa-authorizing-official-remote</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Component/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/component/status/@state) | . | <ul><li>under-development</li><li>operational</li><li>disposition</li><li>other</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Implemented Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item/implemented-component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Implemented Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item/implemented-component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/inventory-item/implemented-component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Implemented Component/Responsible Party/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item/implemented-component) | responsible-party/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Implemented Component/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item/implemented-component/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Implemented Component/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item/implemented-component/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item) | link/@rel | <ul><li>baseline-template</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/inventory-item/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>ipv4-address</li><li>ipv6-address</li><li>fqdn</li><li>uri</li><li>serial-number</li><li>netbios-name</li><li>mac-address</li><li>physical-location</li><li>is-scanned</li><li>hardware-model</li><li>os-name</li><li>os-version</li><li>software-name</li><li>software-version</li><li>software-patch-level</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/inventory-item) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/inventory-item/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/assessment-results/result/local-definitions/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='is-scanned']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Responsible Party/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item) | responsible-party/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/Inventory Item/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/inventory-item/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/User/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/user/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Local Definitions/User/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/user) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>privilege-level</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/user/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/User/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/user) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>internal</li><li>external</li><li>general-public</li></ul> | False | builtin |
| [Location](/assessment-results/result/local-definitions/user) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='privilege-level']/@value | <ul><li>privileged</li><li>non-privileged</li><li>no-logical-access</li></ul> | False | builtin |

#### /Assessment Results/Result/Local Definitions/User/Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/local-definitions/user) | role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Method

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/method) | . | <ul><li>EXAMINE</li><li>INTERVIEW</li><li>TEST</li><li>UNKNOWN</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Relevant Evidence/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/relevant-evidence/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Relevant Evidence/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/relevant-evidence/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Observation/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Observation/Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/observation/type) | . | <ul><li>ssp-statement-issue</li><li>control-objective</li><li>mitigation</li><li>finding</li><li>historic</li></ul> | True | builtin |

#### /Assessment Results/Result/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Reviewed Controls/Control Objective Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/reviewed-controls/control-objective-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Reviewed Controls/Control Objective Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/reviewed-controls/control-objective-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Reviewed Controls/Control Selection/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/reviewed-controls/control-selection/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Reviewed Controls/Control Selection/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/reviewed-controls/control-selection/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Reviewed Controls/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/reviewed-controls/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Reviewed Controls/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/reviewed-controls/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Facet/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://csrc.nist.gov/ns/oscal']/@name | <ul><li>likelihood</li><li>impact</li><li>risk</li><li>severity</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://fedramp.gov','http://fedramp.gov/ns/oscal')]/@name | <ul><li>likelihood</li><li>impact</li><li>risk</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://cve.mitre.org']/@name | <ul><li>cve-id</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0']/@name | <ul><li>access-vector</li><li>access-complexity</li><li>authentication</li><li>confidentiality-impact</li><li>integrity-impact</li><li>availability-impact</li><li>exploitability</li><li>remediation-level</li><li>report-confidence</li><li>collateral-damage-potential</li><li>target-distribution</li><li>confidentiality-requirement</li><li>integrity-requirement</li><li>availability-requirement</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1')]/@name | <ul><li>attack-vector</li><li>access-complexity</li><li>privileges-required</li><li>user-interaction</li><li>scope</li><li>confidentiality-impact</li><li>integrity-impact</li><li>availability-impact</li><li>exploit-code-maturity</li><li>remediation-level</li><li>report-confidence</li><li>modified-attack-vector</li><li>modified-attack-complexity</li><li>modified-privileges-required</li><li>modified-user-interaction</li><li>modified-scope</li><li>modified-confidentiality</li><li>modified-integrity</li><li>modified-availability</li><li>confidentiality-requirement</li><li>integrity-requirement</li><li>availability-requirement</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Facet/@System

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/facet/@system) | . | <ul><li>http://fedramp.gov</li><li>http://fedramp.gov/ns/oscal</li><li>http://csrc.nist.gov/ns/oscal</li><li>http://csrc.nist.gov/ns/oscal/unknown</li><li>http://cve.mitre.org</li><li>http://www.first.org/cvss/v2.0</li><li>http://www.first.org/cvss/v3.0</li><li>http://www.first.org/cvss/v3.1</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Facet/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='access-vector']/@value | <ul><li>local</li><li>adjacent-network</li><li>network</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='access-complexity']/@value | <ul><li>high</li><li>medium</li><li>low</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='authentication']/@value | <ul><li>multiple</li><li>single</li><li>none</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name=('confidentiality-impact', 'integrity-impact', 'availability-impact')]/@value | <ul><li>none</li><li>partial</li><li>complete</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='exploitability']/@value | <ul><li>unproven</li><li>proof-of-concept</li><li>functional</li><li>high</li><li>not-defined</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='remediation-level']/@value | <ul><li>official-fix</li><li>temporary-fix</li><li>workaround</li><li>unavailable</li><li>not-defined</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='report-confidence']/@value | <ul><li>unconfirmed</li><li>uncorroborated</li><li>confirmed</li><li>not-defined</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='collateral-damage-potential']/@value | <ul><li>none</li><li>low</li><li>low-medium</li><li>medium-high</li><li>high</li><li>not-defined</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name=('target-distribution', 'confidentiality-requirement', 'integrity-requirement', 'availability-requirement')]/@value | <ul><li>none</li><li>low</li><li>medium</li><li>high</li><li>not-defined</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='access-vector']/@value | <ul><li>network</li><li>adjacent</li><li>local</li><li>physical</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='access-complexity']/@value | <ul><li>high</li><li>low</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name=('privileges-required', 'confidentiality-impact', 'integrity-impact', 'availability-impact')]/@value | <ul><li>none</li><li>low</li><li>high</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='user-interaction']/@value | <ul><li>none</li><li>required</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='scope']/@value | <ul><li>unchanged</li><li>changed</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='exploit-code-maturity']/@value | <ul><li>not-defined</li><li>unproven</li><li>proof-of-concept</li><li>functional</li><li>high</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='remediation-level']/@value | <ul><li>not-defined</li><li>official-fix</li><li>temporary-fix</li><li>workaround</li><li>unavailable</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='report-confidence']/@value | <ul><li>not-defined</li><li>unknown</li><li>reasonable</li><li>confirmed</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name=('confidentiality-requirement', 'integrity-requirement', 'availability-requirement')]/@value | <ul><li>not-defined</li><li>low</li><li>medium</li><li>high</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='modified-attack-vector']/@value | <ul><li>not-defined</li><li>network</li><li>adjacent</li><li>local</li><li>physical</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='modified-attack-complexity']/@value | <ul><li>not-defined</li><li>high</li><li>low</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name=('modified-privileges-required', 'modified-confidentiality', 'modified-integrity', 'modified-availability')]/@value | <ul><li>not-defined</li><li>none</li><li>low</li><li>high</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='modified-user-interaction']/@value | <ul><li>not-defined</li><li>none</li><li>required</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='modified-scope']/@value | <ul><li>not-defined</li><li>unchanged</li><li>changed</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Facet/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/facet/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Facet/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/facet) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>state</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/characterization/facet/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Facet/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/facet) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='state']/@value | <ul><li>initial</li><li>adjusted</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Characterization/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Characterization/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/characterization/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Mitigating Factor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/mitigating-factor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Mitigating Factor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/mitigating-factor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Mitigating Factor/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/mitigating-factor/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Mitigating Factor/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/mitigating-factor/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Mitigating Factor/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/mitigating-factor/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>false-positive</li><li>accepted</li><li>risk-adjusted</li><li>priority</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/@Lifecycle

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/@lifecycle) | . | <ul><li>recommendation</li><li>planned</li><li>completed</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/response/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>avoid</li><li>mitigate</li><li>transfer</li><li>accept</li><li>share</li><li>contingency</li><li>none</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Required Asset/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/required-asset/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Required Asset/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/required-asset/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Required Asset/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/required-asset/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Required Asset/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/required-asset/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Required Asset/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/required-asset/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/@type) | . | <ul><li>milestone</li><li>action</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Associated Activity/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/associated-activity/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Response/Task/Timing/At Frequency/@Unit

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/response/task/timing/at-frequency/@unit) | . | <ul><li>seconds</li><li>minutes</li><li>hours</li><li>days</li><li>months</li><li>years</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/assessment-results/result/risk/risk-log/entry/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>vendor-check-in</li><li>status-update</li><li>milestone-complete</li><li>mitigation</li><li>remediated</li><li>closed</li><li>dr-submission</li><li>dr-updated</li><li>dr-approved</li><li>dr-rejected</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/related-response/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Assessment Results/Result/Risk/Risk Log/Entry/Status Change

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/risk-log/entry/status-change) | . | <ul><li>open</li><li>investigating</li><li>remediating</li><li>deviation-requested</li><li>deviation-approved</li><li>closed</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Status

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/status) | . | <ul><li>open</li><li>investigating</li><li>remediating</li><li>deviation-requested</li><li>deviation-approved</li><li>closed</li></ul> | True | builtin |

#### /Assessment Results/Result/Risk/Threat Id/@System

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/assessment-results/result/risk/threat-id/@system) | . | <ul><li>http://fedramp.gov</li><li>http://fedramp.gov/ns/oscal</li></ul> | True | builtin |

### POA&amp;M Allowed Values

#### /Plan Of Action And Milestones/Back Matter/Resource/Citation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/back-matter/resource/citation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Back Matter/Resource/Citation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/back-matter/resource/citation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

---

#### /Plan Of Action And Milestones/Back Matter/Resource/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/back-matter/resource/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Back Matter/Resource/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>version</li><li>published</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/back-matter/resource/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Back Matter/Resource/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| attachment-type | [Location](/plan-of-action-and-milestones) | back-matter/resource/prop[@name='type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>law</li><li>regulation</li><li>standard</li><li>guidance</li><li>policy</li><li>procedure</li><li>guide</li><li>rules-of-behavior</li><li>plan</li><li>system-security-plan</li><li>artifact</li><li>evidence</li><li>screen-shot</li><li>image</li><li>tool-report</li><li>raw-tool-output</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>fedramp-citations</li><li>fedramp-acronyms</li><li>fedramp-logo</li><li>separation-of-duties-matrix</li><li>logo</li><li>personally-identifiable-information</li><li>agreement</li><li>isa-agreement</li><li>incident-response-plan</li><li>information-security-policies-and-procedures</li><li>users-guide</li><li>privacy-impact-assessment</li><li>information-system-contingency-plan</li><li>configuration-management-plan</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/plan-of-action-and-milestones/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>logo</li><li>image</li><li>screen-shot</li><li>law</li><li>regulation</li><li>standard</li><li>external-guidance</li><li>acronyms</li><li>citation</li><li>policy</li><li>procedure</li><li>system-guide</li><li>users-guide</li><li>administrators-guide</li><li>rules-of-behavior</li><li>plan</li><li>artifact</li><li>evidence</li><li>tool-output</li><li>raw-data</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>agreement</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Back Matter/Resource/Rlink/Hash/@Algorithm

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/back-matter/resource/rlink/hash/@algorithm) | . | <ul><li>SHA-224</li><li>SHA-256</li><li>SHA-384</li><li>SHA-512</li><li>SHA3-224</li><li>SHA3-256</li><li>SHA3-384</li><li>SHA3-512</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Target/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/target/@type) | . | <ul><li>statement-id</li><li>objective-id</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Target/Implementation Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/target/implementation-status/@state) | . | <ul><li>implemented</li><li>partial</li><li>planned</li><li>alternative</li><li>not-applicable</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Target/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/target/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Target/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/target/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Finding/Target/Status/@Reason

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/target/status/@reason) | . | <ul><li>pass</li><li>fail</li><li>other</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Finding/Target/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/finding/target/status/@state) | . | <ul><li>satisfied</li><li>not-satisfied</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Assessment Platform/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/assessment-platform/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Assessment Platform/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/assessment-platform/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Assessment Platform/Uses Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/assessment-platform/uses-component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Assessment Platform/Uses Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/assessment-platform/uses-component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Assessment Platform/Uses Component/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/assessment-platform/uses-component/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Assessment Platform/Uses Component/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/assessment-platform/uses-component/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component/@type) | . | <ul><li>this-system</li><li>system</li><li>interconnection</li><li>software</li><li>hardware</li><li>service</li><li>policy</li><li>physical</li><li>process-procedure</li><li>plan</li><li>guidance</li><li>standard</li><li>validation</li><li>network</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | link/@rel | <ul><li>depends-on</li><li>validation</li><li>proof-of-compliance</li><li>baseline-template</li><li>uses-service</li><li>system-security-plan</li><li>uses-network</li><li>imported-from</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | (.)[@type='validation']/link/@rel | <ul><li>validation-details</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | (.)[@type='service']/link/@rel | <ul><li>provided-by</li><li>used-by</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | (.)[@type='interconnection']/link/@rel | <ul><li>isa-agreement</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('ipv4-address','ipv6-address')]/@class | <ul><li>local</li><li>remote</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>implementation-point</li><li>leveraged-authorization-uuid</li><li>inherited-uuid</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | (.)[@type='software']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>software-identifier</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | (.)[@type='interconnection']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>isa-title</li><li>isa-date</li><li>isa-remote-system-name</li><li>ipv4-address</li><li>ipv6-address</li><li>direction</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='public']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='virtual']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='implementation-point']/@value | <ul><li>internal</li><li>external</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='direction']/@value | <ul><li>incoming</li><li>outgoing</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/Protocol/Port Range/@Transport

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component/protocol/port-range/@transport) | . | <ul><li>TCP</li><li>UDP</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component) | (.)[@type='interconnection']/responsible-role/@role-id | <ul><li>isa-poc-local</li><li>isa-poc-remote</li><li>isa-authorizing-official-local</li><li>isa-authorizing-official-remote</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Assessment Assets/Component/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/assessment-assets/component/status/@state) | . | <ul><li>under-development</li><li>operational</li><li>disposition</li><li>other</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component/@type) | . | <ul><li>this-system</li><li>system</li><li>interconnection</li><li>software</li><li>hardware</li><li>service</li><li>policy</li><li>physical</li><li>process-procedure</li><li>plan</li><li>guidance</li><li>standard</li><li>validation</li><li>network</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | link/@rel | <ul><li>depends-on</li><li>validation</li><li>proof-of-compliance</li><li>baseline-template</li><li>uses-service</li><li>system-security-plan</li><li>uses-network</li><li>imported-from</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | (.)[@type='validation']/link/@rel | <ul><li>validation-details</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | (.)[@type='service']/link/@rel | <ul><li>provided-by</li><li>used-by</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | (.)[@type='interconnection']/link/@rel | <ul><li>isa-agreement</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('ipv4-address','ipv6-address')]/@class | <ul><li>local</li><li>remote</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>implementation-point</li><li>leveraged-authorization-uuid</li><li>inherited-uuid</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | (.)[@type='software']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>software-identifier</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | (.)[@type='interconnection']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>isa-title</li><li>isa-date</li><li>isa-remote-system-name</li><li>ipv4-address</li><li>ipv6-address</li><li>direction</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='public']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='virtual']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='implementation-point']/@value | <ul><li>internal</li><li>external</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='direction']/@value | <ul><li>incoming</li><li>outgoing</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/Protocol/Port Range/@Transport

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component/protocol/port-range/@transport) | . | <ul><li>TCP</li><li>UDP</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/component) | (.)[@type='interconnection']/responsible-role/@role-id | <ul><li>isa-poc-local</li><li>isa-poc-remote</li><li>isa-authorizing-official-local</li><li>isa-authorizing-official-remote</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Component/Status/@State

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/component/status/@state) | . | <ul><li>under-development</li><li>operational</li><li>disposition</li><li>other</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Implemented Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/implemented-component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Implemented Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/implemented-component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/implemented-component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Implemented Component/Responsible Party/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/implemented-component) | responsible-party/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Implemented Component/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/implemented-component/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Implemented Component/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/implemented-component/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item) | link/@rel | <ul><li>baseline-template</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>ipv4-address</li><li>ipv6-address</li><li>fqdn</li><li>uri</li><li>serial-number</li><li>netbios-name</li><li>mac-address</li><li>physical-location</li><li>is-scanned</li><li>hardware-model</li><li>os-name</li><li>os-version</li><li>software-name</li><li>software-version</li><li>software-patch-level</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item) | (.)[@type=('software', 'hardware', 'service')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>vendor-name</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='is-scanned']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Responsible Party/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item) | responsible-party/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Local Definitions/Inventory Item/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/local-definitions/inventory-item/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Action/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/action/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Action/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/action/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Action/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/action/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Action/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/action/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>latest-version</li><li>predecessor-version</li><li>successor-version</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/metadata/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Location/Address/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/location/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Location/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/location/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Location/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type' and @value='data-center']/@class | <ul><li>primary</li><li>alternate</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Location/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/metadata/location/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Location/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>data-center</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Location/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/location/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Party/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/party/@type) | . | <ul><li>person</li><li>organization</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Party/Address/@Type

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| address-type | [Location](/plan-of-action-and-milestones) | metadata/party/address/@type | <ul><li>work</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/plan-of-action-and-milestones/metadata/party/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Party/External Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/party/external-id/@scheme) | . | <ul><li>http://orcid.org/</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/party) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>mail-stop</li><li>office</li><li>job-title</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/metadata/party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Party/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/party/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>keywords</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/metadata/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Responsible Party/@Role Id

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| allowed-metadata-responsibe-party-role-ids | [Location](/plan-of-action-and-milestones/metadata) | responsible-party/@role-id | <ul><li>creator</li><li>prepared-by</li><li>prepared-for</li><li>content-approver</li><li>contact</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Revision/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/revision) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>predecessor-version</li><li>successor-version</li><li>version-history</li></ul> | True | builtin |
| [Location](/plan-of-action-and-milestones/metadata/revision/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Revision/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/revision/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Metadata/Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Metadata/Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/metadata/role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Method

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/method) | . | <ul><li>EXAMINE</li><li>INTERVIEW</li><li>TEST</li><li>UNKNOWN</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Relevant Evidence/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/relevant-evidence/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Relevant Evidence/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/relevant-evidence/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Observation/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Observation/Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/observation/type) | . | <ul><li>ssp-statement-issue</li><li>control-objective</li><li>mitigation</li><li>finding</li><li>historic</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Poam Item/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/poam-item/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Poam Item/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/poam-item/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Poam Item/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/poam-item/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Poam Item/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/poam-item/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Poam Item/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/poam-item/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Facet/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://csrc.nist.gov/ns/oscal']/@name | <ul><li>likelihood</li><li>impact</li><li>risk</li><li>severity</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://fedramp.gov','http://fedramp.gov/ns/oscal')]/@name | <ul><li>likelihood</li><li>impact</li><li>risk</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://cve.mitre.org']/@name | <ul><li>cve-id</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0']/@name | <ul><li>access-vector</li><li>access-complexity</li><li>authentication</li><li>confidentiality-impact</li><li>integrity-impact</li><li>availability-impact</li><li>exploitability</li><li>remediation-level</li><li>report-confidence</li><li>collateral-damage-potential</li><li>target-distribution</li><li>confidentiality-requirement</li><li>integrity-requirement</li><li>availability-requirement</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1')]/@name | <ul><li>attack-vector</li><li>access-complexity</li><li>privileges-required</li><li>user-interaction</li><li>scope</li><li>confidentiality-impact</li><li>integrity-impact</li><li>availability-impact</li><li>exploit-code-maturity</li><li>remediation-level</li><li>report-confidence</li><li>modified-attack-vector</li><li>modified-attack-complexity</li><li>modified-privileges-required</li><li>modified-user-interaction</li><li>modified-scope</li><li>modified-confidentiality</li><li>modified-integrity</li><li>modified-availability</li><li>confidentiality-requirement</li><li>integrity-requirement</li><li>availability-requirement</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Facet/@System

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet/@system) | . | <ul><li>http://fedramp.gov</li><li>http://fedramp.gov/ns/oscal</li><li>http://csrc.nist.gov/ns/oscal</li><li>http://csrc.nist.gov/ns/oscal/unknown</li><li>http://cve.mitre.org</li><li>http://www.first.org/cvss/v2.0</li><li>http://www.first.org/cvss/v3.0</li><li>http://www.first.org/cvss/v3.1</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Facet/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='access-vector']/@value | <ul><li>local</li><li>adjacent-network</li><li>network</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='access-complexity']/@value | <ul><li>high</li><li>medium</li><li>low</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='authentication']/@value | <ul><li>multiple</li><li>single</li><li>none</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name=('confidentiality-impact', 'integrity-impact', 'availability-impact')]/@value | <ul><li>none</li><li>partial</li><li>complete</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='exploitability']/@value | <ul><li>unproven</li><li>proof-of-concept</li><li>functional</li><li>high</li><li>not-defined</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='remediation-level']/@value | <ul><li>official-fix</li><li>temporary-fix</li><li>workaround</li><li>unavailable</li><li>not-defined</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='report-confidence']/@value | <ul><li>unconfirmed</li><li>uncorroborated</li><li>confirmed</li><li>not-defined</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name='collateral-damage-potential']/@value | <ul><li>none</li><li>low</li><li>low-medium</li><li>medium-high</li><li>high</li><li>not-defined</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system='http://www.first.org/cvss/v2.0' and @name=('target-distribution', 'confidentiality-requirement', 'integrity-requirement', 'availability-requirement')]/@value | <ul><li>none</li><li>low</li><li>medium</li><li>high</li><li>not-defined</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='access-vector']/@value | <ul><li>network</li><li>adjacent</li><li>local</li><li>physical</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='access-complexity']/@value | <ul><li>high</li><li>low</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name=('privileges-required', 'confidentiality-impact', 'integrity-impact', 'availability-impact')]/@value | <ul><li>none</li><li>low</li><li>high</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='user-interaction']/@value | <ul><li>none</li><li>required</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='scope']/@value | <ul><li>unchanged</li><li>changed</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='exploit-code-maturity']/@value | <ul><li>not-defined</li><li>unproven</li><li>proof-of-concept</li><li>functional</li><li>high</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='remediation-level']/@value | <ul><li>not-defined</li><li>official-fix</li><li>temporary-fix</li><li>workaround</li><li>unavailable</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='report-confidence']/@value | <ul><li>not-defined</li><li>unknown</li><li>reasonable</li><li>confirmed</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name=('confidentiality-requirement', 'integrity-requirement', 'availability-requirement')]/@value | <ul><li>not-defined</li><li>low</li><li>medium</li><li>high</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='modified-attack-vector']/@value | <ul><li>not-defined</li><li>network</li><li>adjacent</li><li>local</li><li>physical</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='modified-attack-complexity']/@value | <ul><li>not-defined</li><li>high</li><li>low</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name=('modified-privileges-required', 'modified-confidentiality', 'modified-integrity', 'modified-availability')]/@value | <ul><li>not-defined</li><li>none</li><li>low</li><li>high</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='modified-user-interaction']/@value | <ul><li>not-defined</li><li>none</li><li>required</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | (.)[@system=('http://www.first.org/cvss/v3.0', 'http://www.first.org/cvss/v3.1') and @name='modified-scope']/@value | <ul><li>not-defined</li><li>unchanged</li><li>changed</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Facet/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Facet/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>state</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Facet/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/facet) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='state']/@value | <ul><li>initial</li><li>adjusted</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Characterization/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/characterization/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Mitigating Factor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/mitigating-factor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Mitigating Factor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/mitigating-factor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Mitigating Factor/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/mitigating-factor/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Mitigating Factor/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/mitigating-factor/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Mitigating Factor/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/mitigating-factor/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>false-positive</li><li>accepted</li><li>risk-adjusted</li><li>priority</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/@Lifecycle

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/@lifecycle) | . | <ul><li>recommendation</li><li>planned</li><li>completed</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Actor/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/actor/@type) | . | <ul><li>tool</li><li>assessment-platform</li><li>party</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Actor/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/actor/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Actor/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/actor/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Origin/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/origin/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/response/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>avoid</li><li>mitigate</li><li>transfer</li><li>accept</li><li>share</li><li>contingency</li><li>none</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Required Asset/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/required-asset/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Required Asset/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/required-asset/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Required Asset/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/required-asset/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Required Asset/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/required-asset/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Required Asset/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/required-asset/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/@type) | . | <ul><li>milestone</li><li>action</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Associated Activity/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/associated-activity/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Response/Task/Timing/At Frequency/@Unit

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/response/task/timing/at-frequency/@unit) | . | <ul><li>seconds</li><li>minutes</li><li>hours</li><li>days</li><li>months</li><li>years</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>vendor-check-in</li><li>status-update</li><li>milestone-complete</li><li>mitigation</li><li>remediated</li><li>closed</li><li>dr-submission</li><li>dr-updated</li><li>dr-approved</li><li>dr-rejected</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/identified-subject/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/identified-subject/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/identified-subject/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/identified-subject/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/identified-subject/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/identified-subject/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/identified-subject/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/identified-subject/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Identified Subject/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/identified-subject/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Exclude Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/subject/exclude-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Exclude Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/subject/exclude-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Exclude Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/subject/exclude-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Include Subject/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/subject/include-subject/@type) | . | <ul><li>component</li><li>inventory-item</li><li>location</li><li>party</li><li>user</li><li>resource</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Include Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/subject/include-subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Include Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/subject/include-subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/subject/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Related Response/Related Task/Subject/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/related-response/related-task/subject/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Plan Of Action And Milestones/Risk/Risk Log/Entry/Status Change

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/risk-log/entry/status-change) | . | <ul><li>open</li><li>investigating</li><li>remediating</li><li>deviation-requested</li><li>deviation-approved</li><li>closed</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Status

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/status) | . | <ul><li>open</li><li>investigating</li><li>remediating</li><li>deviation-requested</li><li>deviation-approved</li><li>closed</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/Risk/Threat Id/@System

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/risk/threat-id/@system) | . | <ul><li>http://fedramp.gov</li><li>http://fedramp.gov/ns/oscal</li></ul> | True | builtin |

#### /Plan Of Action And Milestones/System Id/@Identifier Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/plan-of-action-and-milestones/system-id/@identifier-type) | . | <ul><li>https://fedramp.gov</li><li>http://fedramp.gov/ns/oscal</li><li>https://ietf.org/rfc/rfc4122</li><li>http://ietf.org/rfc/rfc4122</li></ul> | True | builtin |

---

### Other Allowed Values

#### /Catalog/Back Matter/Resource/Citation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/back-matter/resource/citation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Back Matter/Resource/Citation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/back-matter/resource/citation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Back Matter/Resource/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/back-matter/resource/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Catalog/Back Matter/Resource/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>version</li><li>published</li></ul> | False | builtin |
| [Location](/catalog/back-matter/resource/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Back Matter/Resource/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| attachment-type | [Location](/catalog) | back-matter/resource/prop[@name='type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>law</li><li>regulation</li><li>standard</li><li>guidance</li><li>policy</li><li>procedure</li><li>guide</li><li>rules-of-behavior</li><li>plan</li><li>system-security-plan</li><li>artifact</li><li>evidence</li><li>screen-shot</li><li>image</li><li>tool-report</li><li>raw-tool-output</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>fedramp-citations</li><li>fedramp-acronyms</li><li>fedramp-logo</li><li>separation-of-duties-matrix</li><li>logo</li><li>personally-identifiable-information</li><li>agreement</li><li>isa-agreement</li><li>incident-response-plan</li><li>information-security-policies-and-procedures</li><li>users-guide</li><li>privacy-impact-assessment</li><li>information-system-contingency-plan</li><li>configuration-management-plan</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/catalog/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>logo</li><li>image</li><li>screen-shot</li><li>law</li><li>regulation</li><li>standard</li><li>external-guidance</li><li>acronyms</li><li>citation</li><li>policy</li><li>procedure</li><li>system-guide</li><li>users-guide</li><li>administrators-guide</li><li>rules-of-behavior</li><li>plan</li><li>artifact</li><li>evidence</li><li>tool-output</li><li>raw-data</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>agreement</li></ul> | False | builtin |

#### /Catalog/Back Matter/Resource/Rlink/Hash/@Algorithm

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/back-matter/resource/rlink/hash/@algorithm) | . | <ul><li>SHA-224</li><li>SHA-256</li><li>SHA-384</li><li>SHA-512</li><li>SHA3-224</li><li>SHA3-256</li><li>SHA3-384</li><li>SHA3-512</li></ul> | True | builtin |

#### /Catalog/Control/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control) | link/@rel | <ul><li>reference</li><li>related</li><li>required</li><li>incorporated-into</li><li>moved-to</li></ul> | True | builtin |
| [Location](/catalog/control/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |
| [Location](/catalog/control/control) | link/@rel | <ul><li>reference</li><li>related</li><li>required</li><li>incorporated-into</li><li>moved-to</li></ul> | True | builtin |

#### /Catalog/Control/Param/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control/param/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Control/Param/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>alt-label</li></ul> | False | builtin |
| [Location](/catalog/control/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>aggregates</li></ul> | False | builtin |
| [Location](/catalog/control/param/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Control/Param/Select/@How Many

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control/param/select/@how-many) | . | <ul><li>one</li><li>one-or-more</li></ul> | False | builtin |

#### /Catalog/Control/Part/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>overview</li><li>statement</li><li>guidance</li><li>example</li><li>assessment</li><li>assessment-method</li></ul> | False | builtin |
| [Location](/catalog/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='statement']//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>item</li></ul> | False | builtin |
| [Location](/catalog/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='statement']//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>item</li></ul> | False | builtin |
| [Location](/catalog/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>objects</li><li>assessment-objects</li></ul> | False | builtin |
| [Location](/catalog/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>overview</li><li>statement</li><li>guidance</li><li>example</li><li>assessment</li><li>assessment-method</li></ul> | False | builtin |
| [Location](/catalog/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='statement']//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>item</li></ul> | False | builtin |
| [Location](/catalog/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='statement']//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>item</li></ul> | False | builtin |
| [Location](/catalog/control/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>objects</li><li>assessment-objects</li></ul> | False | builtin |

#### /Catalog/Control/Part/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control/part/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Control/Part/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/catalog/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/catalog/control/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/catalog/control/part/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/catalog/control/part/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/catalog/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/catalog/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>method</li></ul> | False | builtin |

#### /Catalog/Control/Part/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace(('http://csrc.nist.gov/ns/oscal','http://csrc.nist.gov/ns/rmf')) and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |
| [Location](/catalog/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace(('http://csrc.nist.gov/ns/oscal','http://csrc.nist.gov/ns/rmf')) and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |

#### /Catalog/Control/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>status</li></ul> | False | builtin |
| [Location](/catalog/control/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/catalog/control/control) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>status</li></ul> | False | builtin |

#### /Catalog/Control/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/control) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='status']/@value | <ul><li>withdrawn</li><li>Withdrawn</li></ul> | False | builtin |
| [Location](/catalog/control/control) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='status']/@value | <ul><li>withdrawn</li><li>Withdrawn</li></ul> | False | builtin |

#### /Catalog/Group/Control/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control) | link/@rel | <ul><li>reference</li><li>related</li><li>required</li><li>incorporated-into</li><li>moved-to</li></ul> | True | builtin |
| [Location](/catalog/group/control/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |
| [Location](/catalog/group/control/control) | link/@rel | <ul><li>reference</li><li>related</li><li>required</li><li>incorporated-into</li><li>moved-to</li></ul> | True | builtin |

#### /Catalog/Group/Control/Param/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control/param/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Group/Control/Param/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>alt-label</li></ul> | False | builtin |
| [Location](/catalog/group/control/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>aggregates</li></ul> | False | builtin |
| [Location](/catalog/group/control/param/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Group/Control/Param/Select/@How Many

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control/param/select/@how-many) | . | <ul><li>one</li><li>one-or-more</li></ul> | False | builtin |

#### /Catalog/Group/Control/Part/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>overview</li><li>statement</li><li>guidance</li><li>example</li><li>assessment</li><li>assessment-method</li></ul> | False | builtin |
| [Location](/catalog/group/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='statement']//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>item</li></ul> | False | builtin |
| [Location](/catalog/group/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='statement']//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>item</li></ul> | False | builtin |
| [Location](/catalog/group/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/group/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/group/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/group/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/group/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>objects</li><li>assessment-objects</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>overview</li><li>statement</li><li>guidance</li><li>example</li><li>assessment</li><li>assessment-method</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='statement']//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>item</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='statement']//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>item</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | [Target](.//part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name) | <ul><li>objective</li><li>assessment-objective</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>objects</li><li>assessment-objects</li></ul> | False | builtin |

#### /Catalog/Group/Control/Part/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control/part/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Group/Control/Part/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/catalog/group/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/catalog/group/control/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/catalog/group/control/part/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/catalog/group/control/part/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>method</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>method</li></ul> | False | builtin |

#### /Catalog/Group/Control/Part/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace(('http://csrc.nist.gov/ns/oscal','http://csrc.nist.gov/ns/rmf')) and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name=('assessment','assessment-method')]/prop[has-oscal-namespace(('http://csrc.nist.gov/ns/oscal','http://csrc.nist.gov/ns/rmf')) and @name='method']/@value | <ul><li>INTERVIEW</li><li>EXAMINE</li><li>TEST</li></ul> | False | builtin |

#### /Catalog/Group/Control/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>status</li></ul> | False | builtin |
| [Location](/catalog/group/control/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>status</li></ul> | False | builtin |

#### /Catalog/Group/Control/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/control) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='status']/@value | <ul><li>withdrawn</li><li>Withdrawn</li></ul> | False | builtin |
| [Location](/catalog/group/control/control) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='status']/@value | <ul><li>withdrawn</li><li>Withdrawn</li></ul> | False | builtin |

#### /Catalog/Group/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Group/Param/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/param/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Group/Param/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>alt-label</li></ul> | False | builtin |
| [Location](/catalog/group/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>aggregates</li></ul> | False | builtin |
| [Location](/catalog/group/param/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Group/Param/Select/@How Many

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/param/select/@how-many) | . | <ul><li>one</li><li>one-or-more</li></ul> | False | builtin |

#### /Catalog/Group/Part/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>overview</li><li>instruction</li></ul> | False | builtin |
| [Location](/catalog/group/group) | part[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>overview</li><li>instruction</li></ul> | False | builtin |

#### /Catalog/Group/Part/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/part/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Group/Part/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/catalog/group/part/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/catalog/group/part/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |

#### /Catalog/Group/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/group) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/catalog/group/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/catalog/group/group) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |

#### /Catalog/Metadata/Action/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/action/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Metadata/Action/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/action/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Metadata/Action/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/action/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Metadata/Action/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/action/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Metadata/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Catalog/Metadata/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog) | metadata/link/@rel | <ul><li>source-profile</li><li>source-profile-uuid</li></ul> | True | builtin |
| [Location](/catalog/metadata) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>latest-version</li><li>predecessor-version</li><li>successor-version</li></ul> | True | builtin |
| [Location](/catalog/metadata/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Metadata/Location/Address/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/location/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Catalog/Metadata/Location/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/location/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Metadata/Location/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type' and @value='data-center']/@class | <ul><li>primary</li><li>alternate</li></ul> | False | builtin |

#### /Catalog/Metadata/Location/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/catalog/metadata/location/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Metadata/Location/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>data-center</li></ul> | False | builtin |

#### /Catalog/Metadata/Location/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/location/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Catalog/Metadata/Party/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/party/@type) | . | <ul><li>person</li><li>organization</li></ul> | False | builtin |

#### /Catalog/Metadata/Party/Address/@Type

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| address-type | [Location](/catalog) | metadata/party/address/@type | <ul><li>work</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/catalog/metadata/party/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Catalog/Metadata/Party/External Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/party/external-id/@scheme) | . | <ul><li>http://orcid.org/</li></ul> | True | builtin |

#### /Catalog/Metadata/Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Metadata/Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/party) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>mail-stop</li><li>office</li><li>job-title</li></ul> | False | builtin |
| [Location](/catalog/metadata/party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Metadata/Party/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/party/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Catalog/Metadata/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog) | metadata/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>resolution-tool</li><li>source-profile-uuid</li></ul> | False | builtin |
| [Location](/catalog/metadata) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>keywords</li></ul> | False | builtin |
| [Location](/catalog/metadata/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Metadata/Responsible Party/@Role Id

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| allowed-metadata-responsibe-party-role-ids | [Location](/catalog/metadata) | responsible-party/@role-id | <ul><li>creator</li><li>prepared-by</li><li>prepared-for</li><li>content-approver</li><li>contact</li></ul> | True | builtin |

#### /Catalog/Metadata/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Metadata/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Metadata/Revision/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/revision) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>predecessor-version</li><li>successor-version</li><li>version-history</li></ul> | True | builtin |
| [Location](/catalog/metadata/revision/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Metadata/Revision/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/revision/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Metadata/Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Metadata/Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/metadata/role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Param/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/param/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Catalog/Param/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>alt-label</li></ul> | False | builtin |
| [Location](/catalog/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>aggregates</li></ul> | False | builtin |
| [Location](/catalog/param/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Catalog/Param/Select/@How Many

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/catalog/param/select/@how-many) | . | <ul><li>one</li><li>one-or-more</li></ul> | False | builtin |

---

#### /Component Definition/Back Matter/Resource/Citation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/back-matter/resource/citation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Back Matter/Resource/Citation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/back-matter/resource/citation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Back Matter/Resource/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/back-matter/resource/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Component Definition/Back Matter/Resource/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>version</li><li>published</li></ul> | False | builtin |
| [Location](/component-definition/back-matter/resource/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Back Matter/Resource/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| attachment-type | [Location](/component-definition) | back-matter/resource/prop[@name='type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>law</li><li>regulation</li><li>standard</li><li>guidance</li><li>policy</li><li>procedure</li><li>guide</li><li>rules-of-behavior</li><li>plan</li><li>system-security-plan</li><li>artifact</li><li>evidence</li><li>screen-shot</li><li>image</li><li>tool-report</li><li>raw-tool-output</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>fedramp-citations</li><li>fedramp-acronyms</li><li>fedramp-logo</li><li>separation-of-duties-matrix</li><li>logo</li><li>personally-identifiable-information</li><li>agreement</li><li>isa-agreement</li><li>incident-response-plan</li><li>information-security-policies-and-procedures</li><li>users-guide</li><li>privacy-impact-assessment</li><li>information-system-contingency-plan</li><li>configuration-management-plan</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/component-definition/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>logo</li><li>image</li><li>screen-shot</li><li>law</li><li>regulation</li><li>standard</li><li>external-guidance</li><li>acronyms</li><li>citation</li><li>policy</li><li>procedure</li><li>system-guide</li><li>users-guide</li><li>administrators-guide</li><li>rules-of-behavior</li><li>plan</li><li>artifact</li><li>evidence</li><li>tool-output</li><li>raw-data</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>agreement</li></ul> | False | builtin |

#### /Component Definition/Back Matter/Resource/Rlink/Hash/@Algorithm

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/back-matter/resource/rlink/hash/@algorithm) | . | <ul><li>SHA-224</li><li>SHA-256</li><li>SHA-384</li><li>SHA-512</li><li>SHA3-224</li><li>SHA3-256</li><li>SHA3-384</li><li>SHA3-512</li></ul> | True | builtin |

#### /Component Definition/Capability/Control Implementation/Implemented Requirement/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/implemented-requirement/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Capability/Control Implementation/Implemented Requirement/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/implemented-requirement/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Capability/Control Implementation/Implemented Requirement/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/implemented-requirement/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Capability/Control Implementation/Implemented Requirement/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/implemented-requirement/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Capability/Control Implementation/Implemented Requirement/Statement/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/implemented-requirement/statement/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Capability/Control Implementation/Implemented Requirement/Statement/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/implemented-requirement/statement/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Capability/Control Implementation/Implemented Requirement/Statement/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/implemented-requirement/statement/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Capability/Control Implementation/Implemented Requirement/Statement/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/implemented-requirement/statement/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Capability/Control Implementation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Capability/Control Implementation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/control-implementation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Capability/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Capability/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/capability/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Component/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/@type) | . | <ul><li>interconnection</li><li>software</li><li>hardware</li><li>service</li><li>policy</li><li>physical</li><li>process-procedure</li><li>plan</li><li>guidance</li><li>standard</li><li>validation</li></ul> | True | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/implemented-requirement/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/implemented-requirement/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component) | responsible-role/@role-id|control-implementation/implemented-requirement/responsible-role/@role-id|control-implementation/implemented-requirement/statement/responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/implemented-requirement/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/implemented-requirement/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Statement/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/implemented-requirement/statement/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Statement/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/implemented-requirement/statement/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Statement/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component) | responsible-role/@role-id|control-implementation/implemented-requirement/responsible-role/@role-id|control-implementation/implemented-requirement/statement/responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Statement/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/implemented-requirement/statement/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Component/Control Implementation/Implemented Requirement/Statement/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/implemented-requirement/statement/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Component/Control Implementation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Component/Control Implementation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/control-implementation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Component/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component) | link/@rel | <ul><li>depends-on</li><li>validation</li><li>proof-of-compliance</li><li>baseline-template</li><li>uses-service</li><li>system-security-plan</li><li>uses-network</li></ul> | True | builtin |
| [Location](/component-definition/component) | (.)[@type='service']/link/@rel | <ul><li>provided-by</li><li>used-by</li></ul> | True | builtin |
| [Location](/component-definition/component/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Component/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>version</li><li>patch-level</li><li>model</li><li>release-date</li><li>validation-type</li><li>validation-reference</li><li>asset-type</li><li>asset-id</li><li>asset-tag</li><li>public</li><li>virtual</li><li>vlan-id</li><li>network-id</li><li>label</li><li>sort-id</li><li>baseline-configuration-name</li><li>allows-authenticated-scan</li><li>function</li></ul> | False | builtin |
| [Location](/component-definition/component) | (.)[@type='software']/prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>software-identifier</li></ul> | False | builtin |
| [Location](/component-definition/component/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Component/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='asset-type']/@value | <ul><li>operating-system</li><li>database</li><li>web-server</li><li>dns-server</li><li>email-server</li><li>directory-server</li><li>pbx</li><li>firewall</li><li>router</li><li>switch</li><li>storage-array</li><li>appliance</li></ul> | True | builtin |
| [Location](/component-definition/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='allows-authenticated-scan']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/component-definition/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='virtual']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/component-definition/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='public']/@value | <ul><li>yes</li><li>no</li></ul> | False | builtin |
| [Location](/component-definition/component) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='implementation-point']/@value | <ul><li>internal</li><li>external</li></ul> | False | builtin |

#### /Component Definition/Component/Protocol/Port Range/@Transport

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/protocol/port-range/@transport) | . | <ul><li>TCP</li><li>UDP</li></ul> | False | builtin |

#### /Component Definition/Component/Responsible Role/@Role Id

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component) | responsible-role/@role-id|control-implementation/implemented-requirement/responsible-role/@role-id|control-implementation/implemented-requirement/statement/responsible-role/@role-id | <ul><li>asset-owner</li><li>asset-administrator</li><li>security-operations</li><li>network-operations</li><li>incident-response</li><li>help-desk</li><li>configuration-management</li><li>maintainer</li><li>provider</li></ul> | True | builtin |

#### /Component Definition/Component/Responsible Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/responsible-role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Component/Responsible Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/component/responsible-role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Metadata/Action/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/action/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Metadata/Action/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/action/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Metadata/Action/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/action/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Metadata/Action/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/action/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Metadata/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Component Definition/Metadata/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>latest-version</li><li>predecessor-version</li><li>successor-version</li></ul> | True | builtin |
| [Location](/component-definition/metadata/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Metadata/Location/Address/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/location/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Component Definition/Metadata/Location/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/location/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Metadata/Location/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type' and @value='data-center']/@class | <ul><li>primary</li><li>alternate</li></ul> | False | builtin |

#### /Component Definition/Metadata/Location/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/component-definition/metadata/location/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Metadata/Location/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>data-center</li></ul> | False | builtin |

#### /Component Definition/Metadata/Location/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/location/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Component Definition/Metadata/Party/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/party/@type) | . | <ul><li>person</li><li>organization</li></ul> | False | builtin |

#### /Component Definition/Metadata/Party/Address/@Type

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| address-type | [Location](/component-definition) | metadata/party/address/@type | <ul><li>work</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/component-definition/metadata/party/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Component Definition/Metadata/Party/External Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/party/external-id/@scheme) | . | <ul><li>http://orcid.org/</li></ul> | True | builtin |

#### /Component Definition/Metadata/Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Metadata/Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/party) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>mail-stop</li><li>office</li><li>job-title</li></ul> | False | builtin |
| [Location](/component-definition/metadata/party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Metadata/Party/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/party/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Component Definition/Metadata/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>keywords</li></ul> | False | builtin |
| [Location](/component-definition/metadata/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Metadata/Responsible Party/@Role Id

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| allowed-metadata-responsibe-party-role-ids | [Location](/component-definition/metadata) | responsible-party/@role-id | <ul><li>creator</li><li>prepared-by</li><li>prepared-for</li><li>content-approver</li><li>contact</li></ul> | True | builtin |

#### /Component Definition/Metadata/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Metadata/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Metadata/Revision/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/revision) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>predecessor-version</li><li>successor-version</li><li>version-history</li></ul> | True | builtin |
| [Location](/component-definition/metadata/revision/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Metadata/Revision/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/revision/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Component Definition/Metadata/Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Component Definition/Metadata/Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/component-definition/metadata/role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

---

#### /Profile/Back Matter/Resource/Citation/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/back-matter/resource/citation/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Back Matter/Resource/Citation/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/back-matter/resource/citation/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Back Matter/Resource/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/back-matter/resource/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Profile/Back Matter/Resource/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li><li>version</li><li>published</li></ul> | False | builtin |
| [Location](/profile/back-matter/resource/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Back Matter/Resource/Prop/@Value

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| attachment-type | [Location](/profile) | back-matter/resource/prop[@name='type'][@ns='https://fedramp.gov/ns/oscal']/@value | <ul><li>law</li><li>regulation</li><li>standard</li><li>guidance</li><li>policy</li><li>procedure</li><li>guide</li><li>rules-of-behavior</li><li>plan</li><li>system-security-plan</li><li>artifact</li><li>evidence</li><li>screen-shot</li><li>image</li><li>tool-report</li><li>raw-tool-output</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>fedramp-citations</li><li>fedramp-acronyms</li><li>fedramp-logo</li><li>separation-of-duties-matrix</li><li>logo</li><li>personally-identifiable-information</li><li>agreement</li><li>isa-agreement</li><li>incident-response-plan</li><li>information-security-policies-and-procedures</li><li>users-guide</li><li>privacy-impact-assessment</li><li>information-system-contingency-plan</li><li>configuration-management-plan</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/profile/back-matter/resource) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>logo</li><li>image</li><li>screen-shot</li><li>law</li><li>regulation</li><li>standard</li><li>external-guidance</li><li>acronyms</li><li>citation</li><li>policy</li><li>procedure</li><li>system-guide</li><li>users-guide</li><li>administrators-guide</li><li>rules-of-behavior</li><li>plan</li><li>artifact</li><li>evidence</li><li>tool-output</li><li>raw-data</li><li>interview-notes</li><li>questionnaire</li><li>report</li><li>agreement</li></ul> | False | builtin |

#### /Profile/Back Matter/Resource/Rlink/Hash/@Algorithm

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/back-matter/resource/rlink/hash/@algorithm) | . | <ul><li>SHA-224</li><li>SHA-256</li><li>SHA-384</li><li>SHA-512</li><li>SHA3-224</li><li>SHA3-256</li><li>SHA3-384</li><li>SHA3-512</li></ul> | True | builtin |

#### /Profile/Import/Exclude Controls/@With Child Controls

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/import/exclude-controls/@with-child-controls) | . | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /Profile/Import/Include Controls/@With Child Controls

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/import/include-controls/@with-child-controls) | . | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /Profile/Merge/Combine/@Method

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/combine/@method) | . | <ul><li>use-first</li><li>merge</li><li>keep</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Group/Insert Controls/@Order

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/insert-controls/@order) | . | <ul><li>keep</li><li>ascending</li><li>descending</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Group/Insert Controls/Exclude Controls/@With Child Controls

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/insert-controls/exclude-controls/@with-child-controls) | . | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Group/Insert Controls/Include Controls/@With Child Controls

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/insert-controls/include-controls/@with-child-controls) | . | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Group/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Merge/Custom/Group/Param/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/param/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Merge/Custom/Group/Param/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>alt-label</li></ul> | False | builtin |
| [Location](/profile/merge/custom/group/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>aggregates</li></ul> | False | builtin |
| [Location](/profile/merge/custom/group/param/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Group/Param/Select/@How Many

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/param/select/@how-many) | . | <ul><li>one</li><li>one-or-more</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Group/Part/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/part/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Merge/Custom/Group/Part/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/profile/merge/custom/group/part/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/profile/merge/custom/group/part/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Group/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/group/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Insert Controls/@Order

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/insert-controls/@order) | . | <ul><li>keep</li><li>ascending</li><li>descending</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Insert Controls/Exclude Controls/@With Child Controls

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/insert-controls/exclude-controls/@with-child-controls) | . | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /Profile/Merge/Custom/Insert Controls/Include Controls/@With Child Controls

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/merge/custom/insert-controls/include-controls/@with-child-controls) | . | <ul><li>yes</li><li>no</li></ul> | False | builtin |

#### /Profile/Metadata/Action/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/action/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Metadata/Action/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/action/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Metadata/Action/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/action/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Metadata/Action/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/action/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Metadata/Document Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/document-id/@scheme) | . | <ul><li>http://www.doi.org/</li></ul> | True | builtin |

#### /Profile/Metadata/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>latest-version</li><li>predecessor-version</li><li>successor-version</li></ul> | True | builtin |
| [Location](/profile/metadata/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Metadata/Location/Address/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/location/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Profile/Metadata/Location/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/location/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Metadata/Location/Prop/@Class

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type' and @value='data-center']/@class | <ul><li>primary</li><li>alternate</li></ul> | False | builtin |

#### /Profile/Metadata/Location/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>type</li></ul> | False | builtin |
| [Location](/profile/metadata/location/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Metadata/Location/Prop/@Value

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/location) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal') and @name='type']/@value | <ul><li>data-center</li></ul> | False | builtin |

#### /Profile/Metadata/Location/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/location/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Profile/Metadata/Party/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/party/@type) | . | <ul><li>person</li><li>organization</li></ul> | False | builtin |

#### /Profile/Metadata/Party/Address/@Type

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| address-type | [Location](/profile) | metadata/party/address/@type | <ul><li>work</li></ul> | False | [FedRAMP constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) |
|  | [Location](/profile/metadata/party/address/@type) | . | <ul><li>home</li><li>work</li></ul> | True | builtin |

#### /Profile/Metadata/Party/External Id/@Scheme

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/party/external-id/@scheme) | . | <ul><li>http://orcid.org/</li></ul> | True | builtin |

#### /Profile/Metadata/Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Metadata/Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/party) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>mail-stop</li><li>office</li><li>job-title</li></ul> | False | builtin |
| [Location](/profile/metadata/party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Metadata/Party/Telephone Number/@Type

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/party/telephone-number/@type) | . | <ul><li>home</li><li>office</li><li>mobile</li></ul> | True | builtin |

#### /Profile/Metadata/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>keywords</li></ul> | False | builtin |
| [Location](/profile/metadata/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Metadata/Responsible Party/@Role Id

| Identifier | Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- | --- |
| allowed-metadata-responsibe-party-role-ids | [Location](/profile/metadata) | responsible-party/@role-id | <ul><li>creator</li><li>prepared-by</li><li>prepared-for</li><li>content-approver</li><li>contact</li></ul> | True | builtin |

#### /Profile/Metadata/Responsible Party/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/responsible-party/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Metadata/Responsible Party/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/responsible-party/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Metadata/Revision/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/revision) | link/@rel | <ul><li>canonical</li><li>alternate</li><li>predecessor-version</li><li>successor-version</li><li>version-history</li></ul> | True | builtin |
| [Location](/profile/metadata/revision/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Metadata/Revision/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/revision/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Metadata/Role/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/role/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Metadata/Role/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/metadata/role/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Modify/Alter/Add/@Position

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/alter/add/@position) | . | <ul><li>before</li><li>after</li><li>starting</li><li>ending</li></ul> | False | builtin |

#### /Profile/Modify/Alter/Add/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/alter/add/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Modify/Alter/Add/Param/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/alter/add/param/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Modify/Alter/Add/Param/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/alter/add/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li><li>alt-label</li></ul> | False | builtin |
| [Location](/profile/modify/alter/add/param) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/rmf')]/@name | <ul><li>aggregates</li></ul> | False | builtin |
| [Location](/profile/modify/alter/add/param/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Modify/Alter/Add/Param/Select/@How Many

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/alter/add/param/select/@how-many) | . | <ul><li>one</li><li>one-or-more</li></ul> | False | builtin |

#### /Profile/Modify/Alter/Add/Part/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/alter/add/part/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Modify/Alter/Add/Part/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/alter/add/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/profile/modify/alter/add/part/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |
| [Location](/profile/modify/alter/add/part/part) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |

#### /Profile/Modify/Alter/Add/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/alter/add) | prop[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>label</li><li>sort-id</li><li>alt-identifier</li></ul> | False | builtin |
| [Location](/profile/modify/alter/add/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Modify/Alter/Remove/@By Item Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/alter/remove/@by-item-name) | . | <ul><li>param</li><li>prop</li><li>link</li><li>part</li><li>mapping</li><li>map</li></ul> | False | builtin |

#### /Profile/Modify/Set Parameter/Link/@Rel

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/set-parameter/link/@rel) | . | <ul><li>reference</li></ul> | True | builtin |

#### /Profile/Modify/Set Parameter/Prop/@Name

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/set-parameter/prop) | .[has-oscal-namespace('http://csrc.nist.gov/ns/oscal')]/@name | <ul><li>marking</li></ul> | False | builtin |

#### /Profile/Modify/Set Parameter/Select/@How Many

| Location | Target | Values | Allow Other | Source |
| --- | --- | --- | --- | --- |
| [Location](/profile/modify/set-parameter/select/@how-many) | . | <ul><li>one</li><li>one-or-more</li></ul> | False | builtin |
