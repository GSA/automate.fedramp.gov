---
title: FedRAMP Extensions 
weight: 150
---
# FedRAMP Extensions 

The core OSCAL syntax is designed to represent cybersecurity
information that is common to any organization and compliance framework.
They recognized that each framework and organization may have unique
needs. Instead of trying to provide a language that meets each of those
unique needs, OSCAL provides organizations the ability to tailor OSCAL to
address specific needs.

{{<callout>}}
_A summary of the FedRAMP extensions and accepted values appears in the FedRAMP OSCAL Registry._
{{</callout>}}

FedRAMP has tailored OSCAL by specifying:

-   **Extensions**: allow FedRAMP's OSCAL-based content to capture
    information that is not available in the core OSCAL syntax.

-   **Accepted Values**: For many fields, FedRAMP specifies a
    case-sensitive set of accepted values. Only these values are
    recognized by FedRAMP processing tools.

## FedRAMP Extensions

There are several pieces of information required in FedRAMP templates
that cannot be modeled using the OSCAL core syntax. NIST wanted to limit
the core OSCAL syntax to those elements that are universal across most
cybersecurity frameworks. They designed OSCAL to be extended where
unique needs existed.

{{<callout>}}
_All FedRAMP extensions include a namespace (ns) flag set to `https://fedramp.gov/ns/oscal`._
{{</callout>}}

NIST allows organizations to extend OSCAL anyplace `prop` fields or `part`
assemblies exist in the core syntax. (Please note, there are currently
no part assemblies in the SSP, SAP, SAR, or POA&M.) There are two
fundamental requirements for extending OSCAL:

-   The organization must establish a unique namespace (`ns`) identifier,
    such as (`ns="http://domain.tld/ns/oscal"`), and use it to
    consistently tag all `prop` and `part` extensions from that
    organization.

-   The organization is responsible for defining, managing, and
    communicating all names (`name="scan-type"`) defined and tagged with
    the above namespace identifier.

OSCAL's core `prop` assemblies have no `ns` flag. If an `ns` flag is
present, it is an organization-defined extension. This allows each
industry standards body or organization to create their own extensions
in their own name space without concern for overlapping names. The above
approach ensures two different organizations can create their
own extensions without concern for reusing the same name values.

All FedRAMP extensions must have a namespace (`ns`) flag set to `https://fedramp.gov/ns/oscal`.

For example, if the core OSCAL syntax has a `status` field, but both
FedRAMP and the payment card industry (PCI) require their own
framework-specific status field, each may define an extension with the
`name="status"` and assign their own `ns` flag. This results in three
possible status fields as follows:

#### OSCAL User Representation

{{< highlight xml "linenos=table" >}}
  <!-- There is no @ns, so this is core OSCAL syntax -->
  <prop name="status" value="active" />
{{< /highlight >}}

#### XPath Query
{{< highlight xml "linenos=table" >}}
  //prop[@name="status"][not(@ns)]
{{< /highlight >}}

**When searching an OSCAL file for a prop or prop extension that is
part of the core OSCAL syntax, developers must filter out any with an ns
flag using the syntax above.**

#### FedRAMP Status Representation                                           
{{< highlight xml "linenos=table" >}}
  <prop name="status" ns="https://fedramp.gov/ns/oscal" value="FedRAMP Status" /> 
{{< /highlight >}}

#### XPath Query
{{< highlight xml "linenos=table" >}}
  //prop[@name="status"][@ns="https://fedramp.gov/ns/oscal"]
{{< /highlight >}}

#### (Possible) PCI Status Representation
{{< highlight xml "linenos=table" >}}
  <prop name="status" ns="https://pcisecuritystandards.org/ns/oscal"  value="PCI Status" />
{{< /highlight >}}

#### XPath Query
{{< highlight xml "linenos=table" >}}
  //prop[@name="status"][@ns="https://pcisecuritystandards.org/ns/oscal"]
{{< /highlight >}}

This is an example, and is not intended to represent an actual PCI
extension.

Tool developers must always refer to extensions using **both** the `name`
and `ns` flags as a pair.

All FedRAMP extensions will appear as:
{{< highlight xml "linenos=table" >}}
  <prop name="____" ns="https://fedramp.gov/ns/oscal" value="Value"/>
{{< /highlight >}}

**NOTE:** The catalog and profile OSCAL models also allow the `part`
assembly to be used for extensions. This is not currently the case for
the OSCAL SSP, SAP, SAR, or POA&M.

---

## Summary of FedRAMP Extensions

FedRAMP extensions are cited in relevant portions of this documentation site and
summarized below.

### Assessment Type

|  |  |
|----|----|
| ID | assessment-type |
| Description | The type of assessment (e.g., initial authorization, annual assessment, assessment for a significant change, or another type of assessment). |
| Allowed Values | "initial","annual","significant-change", and "other" |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Asset Type

|  |  |
|----|----|
| ID | asset-type |
| Description | Identifies the type of asset. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. The value may be locally defined using the "http://csrc.nist.gov/ns/oscal" namespace values for this prop. |

### Authentication Method

|  |  |
|----|----|
| ID | authentication-method |
| Description | The authentication method(s) for users of a leveraged service or external interconnection. Refer to for authentication methods NIST 800-63B (https://pages.nist.gov/800-63-3/sp800-63b.html) for authentication methods |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Authorization Date

|  |  |
|----|----|
| ID | authorization-date |
| Description | The date the system was authorized. Omit or leave blank for an initial authorization. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. This information should be obtained from the imported SSP's date-authorized. |

### Authorization Recommendation

|  |  |
|----|----|
| ID | authorization-recommendation |
| Description | Indicates whether the assessor recommends the system be authorized by the authorizing official. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. Use "recommend-authorization" FedRAMP extension prop instead. |

### Authorization Type

|                |                                                     |
|----------------|-----------------------------------------------------|
| ID             | authorization-type                                  |
| Description    | Identifies the FedRAMP authorization type.          |
| Allowed Values | "fedramp-agency"                                    |
| Status         | Active                                              |
| Remarks        | The "fedramp-jab" authorization type is deprecated. |

### Authorized Users

|  |  |
|----|----|
| ID | authorized-users |
| Description | The users or roles that can access the leveraged service or external interconnection. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Circuit Service Processor

|  |  |
|----|----|
| ID | circuit |
| Description | A circuit used for the communication. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | E.g., a circuit ID. To provide a general reference for a service processor, use the "service-processor" FedRAMP extension instead. |

### Control Implementation Status

|  |  |
|----|----|
| ID | control-implementation-status |
| Description | Indicates the implementation status of the control. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. Use "http://csrc.nist.gov/ns/oscal" namespace values prop instead. |

### Objective Implementation Status

|  |  |
|----|----|
| ID | control-objective-implementation-status |
| Description | Indicates the implementation status of the control objective. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. Use "http://csrc.nist.gov/ns/oscal" namespace values prop instead. |

### Control Origination

|  |  |
|----|----|
| ID | control-origination |
| Description | The point(s) from which the control satisfaction originates. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. Use "http://csrc.nist.gov/ns/oscal" namespace values prop instead. |

### Core Control

|  |  |
|----|----|
| ID | CORE |
| Description | Identifies a control that must be included in every FedRAMP assessment. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Core controls must be assessed every year, and are often subject to additional scrutiny by assessors and adjudication reviewers. |

### Cryptographic Module Usage

|  |  |
|----|----|
| ID | cryptographic-module-usage |
| Description | The cryptographic module is used for data at rest (DAT) or data in transit (DIT). |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### CSP Validated

|  |  |
|----|----|
| ID | csp-validated |
| Description | The CSP ensured the independent assessor team roles are appropriately filled. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Description

|                |                                    |
|----------------|------------------------------------|
| ID             | description                        |
| Description    | A brief description of the system. |
| Allowed Values | Unrestricted                       |
| Status         | Deprecated in version 1.0.2        |
| Remarks        | Deprecated.                        |

### Discrepancies

|  |  |
|----|----|
| ID | discrepancies |
| Description | Any discrepancies between inventory that was in scope for the planned assessment and the assets in the assessment results. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Discrepancies Reason

|  |  |
|----|----|
| ID | discrepencies-reason |
| Description | The justification or reason for any discrepancies between inventory that was in scope for the planned assessment and the assets in the assessment results. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### False Positive

|                |                                                   |
|----------------|---------------------------------------------------|
| ID             | false-positive                                    |
| Description    | The risk was found to be a false positive report. |
| Allowed Values | Unrestricted                                      |
| Status         | Active                                            |
| Remarks        | No remarks                                        |

### Fully Operational Date

|  |  |
|----|----|
| ID | fully-operational-date |
| Description | The date when security control implementations for the appropriate control baseline was completed. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. “Fully operational” means there are no “gaps” in the security control baseline implementations for the system. The CSP attests that the security controls are implemented correctly, operating as intended, and producing the desired outcome with respect to meeting established security requirements. |

### IA Manual Review

|  |  |
|----|----|
| ID | ia-manual-review |
| Description | Confirmation that the independent assessor performed a manual review of (scan) configuration files to analyze for existing vulnerabilities. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### IA Validated

|  |  |
|----|----|
| ID | ia-validated |
| Description | The independent assessor ensured the assessment team roles are appropriately filled. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Impact Level

|  |  |
|----|----|
| ID | impact-level |
| Description | The impact level of a leveraged authorization. |
| Allowed Values | "fips-199-high", "fips-199-moderate", and "fips-199-low". |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Information Transmitted

|  |  |
|----|----|
| ID | information |
| Description | Describes the information transmitted over the interconnection. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | No remarks |

### Interconnection Compliance

|  |  |
|----|----|
| ID | interconnection-compliance |
| Description | Any (security) compliance certifications the third party external service has (e.g., PCI SOC 2, CSA STAR Level 2, etc.). |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Interconnection Data Categorization

|  |  |
|----|----|
| ID | interconnection-data-categorization |
| Description | The security impact level of the data (Low, Moderate, High), processed by or stored in the external service, in accordance with FIPS 199 & NIST 800-60 Vol. 2. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Interconnection Data Type

|  |  |
|----|----|
| ID | interconnection-data-type |
| Description | The type of data / information processed by or stored in the external service, in accordance with NIST 800-60 Vol. 2. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Interconnection Direction

|  |  |
|----|----|
| ID | interconnection-direction |
| Description | Identifies the direction of information flow for the interconnection. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. Use core OSCAL "direction" prop instead. |

### Interconnection Hosting Environment

|  |  |
|----|----|
| ID | interconnection-hosting-environment |
| Description | A description of the hosting environment (e.g., corporate network, IaaS, or self-hosted) for the external service. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Interconnection Risk

|  |  |
|----|----|
| ID | interconnection-risk |
| Description | A description of the potential risks introduced by the external system/service and impact to the CSO or federal data if the confidentiality, integrity, and availability (CIA) of the system/service is compromised. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Interconnection Security

|  |  |
|----|----|
| ID | interconnection-security |
| Description | Identifies the mechanisms/protocol(s) used to secure the communication. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Renamed from "connection-security" to "interconnection-security". |

### Interconnection Type

|  |  |
|----|----|
| ID | interconnection-type |
| Description | Numeric indicator of the type of interconnection, where 1 = Non-FedRAMP Authorized Cloud Services, 2 = Corporate Shared Services, and 3 = Update Services for In-Boundary Software/Services. |
| Allowed Values | "1", "2", or "3" |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. May specify "4" if none of the other types apply. |

### Inventory Item State.

|  |  |
|----|----|
| ID | inventory-item-state |
| Description | Different states of inventory items: public, private, et cetera |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. |

### IPv4 Address

|  |  |
|----|----|
| ID | ipv4-address |
| Description | The IP address of a component, inventory item, or other asset. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. Core OSCAL has an "ipv4-address" prop which can be used for specific component types and for inventory items. This extension can be used instead, and is also applicable for other assemblies such as assessment-platform. |

### IPv4 Subnet

|  |  |
|----|----|
| ID | ipv4-subnet |
| Description | The subnet for a component of inventory item. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### ISO/IEC 17020 Identifier

|  |  |
|----|----|
| ID | iso-iec-17020-identifier |
| Description | The ISO/IEC-17020 identifier assigned to the assessor related to their status as an A2LA Accredited Third Party Assessment Organization. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | No remarks |

### KEV Catalog

|  |  |
|----|----|
| ID | kev-catalog |
| Description | Indicates if this vulnerability is on the CISA Known Exploited Vulnerabilities (KEV) Catalog. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. In accordance with Binding Operational Directive (BOD) 22-01, CSPs must track their vulnerabilities against the KEV catalog. |

### KEV Due Date

|  |  |
|----|----|
| ID | kev-due-date |
| Description | The KEV catalog specified due date by which the vulnerability must be remediated. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. In accordance with Binding Operational Directive (BOD) 22-01, CSPs must track their vulnerabilities against the KEV catalog. |

### Label - Test ID

|  |  |
|----|----|
| ID | label |
| Description | The test ID for the manual test method. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Leveraged Authorization

|  |  |
|----|----|
| ID | leveraged-authorization |
| Description | Indicates a leveraged authorization used for this control. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | This is for legacy SSP conversion to OSCAL. The preferred approach is to specify the leveraged system as a component and reference it in the control using by-component. |

### Leveraged System Identifier

|  |  |
|----|----|
| ID | leveraged-system-identifier |
| Description | The identifier corresponding to the FedRAMP package ID. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Likelihood

|                |                              |
|----------------|------------------------------|
| ID             | likelihood                   |
| Description    | The likelihood of a risk.    |
| Allowed Values | "high", "moderate", or "low" |
| Status         | Active                       |
| Remarks        | No remarks                   |

### Login ID

|                |                                                       |
|----------------|-------------------------------------------------------|
| ID             | login-id                                              |
| Description    | The login ID used to assess the web application.      |
| Allowed Values | Unrestricted                                          |
| Status         | Active                                                |
| Remarks        | Extension renamed from "task-login-id" to "login-id". |

### Login URL

|                |                                                         |
|----------------|---------------------------------------------------------|
| ID             | login-url                                               |
| Description    | The login URL for a web application.                    |
| Allowed Values | Unrestricted                                            |
| Status         | Active                                                  |
| Remarks        | Extension renamed from "task-login-url" to "login-url". |

### Name

|  |  |
|----|----|
| ID | name |
| Description | The product or tool name for a component or inventory item. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. For local defi |

### Nature of Agreement

|  |  |
|----|----|
| ID | nature-of-agreement |
| Description | Any type of agreement between a CSP and the leveraged CSP vendors who support products (e.g., End User Licensing Agreement (EULA), Service-Level Agreement (SLA), App License Agreement, Contract, etc.). |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Referenced Authorization Date

|                |                                                         |
|----------------|---------------------------------------------------------|
| ID             | no-oscal-ssp-authorization-date                         |
| Description    | The date of the system's initial FedRAMP authorization. |
| Allowed Values | Unrestricted                                            |
| Status         | Active                                                  |
| Remarks        | No remarks                                              |

### Relevant Baseline

|  |  |
|----|----|
| ID | no-oscal-ssp-import-profile |
| Description | Identifies the relevant OSCAL baseline. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | As with all URIs in OSCAL, this may contain a URI fragment, which identifies the local resource containing the relevant profile. Only use when an OSCAL SSP cannot be referenced. |

### Short System Name

|                |                                         |
|----------------|-----------------------------------------|
| ID             | no-oscal-ssp-purpose                    |
| Description    | The FedRAMP-assigned system identifier. |
| Allowed Values | Unrestricted                            |
| Status         | Active                                  |
| Remarks        | No remarks                              |

### Short System Name

|                |                                         |
|----------------|-----------------------------------------|
| ID             | no-oscal-ssp-system-id                  |
| Description    | The FedRAMP-assigned system identifier. |
| Allowed Values | Unrestricted                            |
| Status         | Active                                  |
| Remarks        | No remarks                              |

### Short System Name

|                |                                                          |
|----------------|----------------------------------------------------------|
| ID             | no-oscal-ssp-title-short                                 |
| Description    | The abbreviated name for the system, such as an acronym. |
| Allowed Values | Unrestricted                                             |
| Status         | Active                                                   |
| Remarks        | No remarks                                               |

### Operational Requirement

|  |  |
|----|----|
| ID | operational-requirement |
| Description | Use to indicate that risk cannot be remediated without impact to the system and must be accepted. |
| Allowed Values | "investigating", "pending", "approved" |
| Status | Active |
| Remarks | No remarks |

### Planned Completion Date

|  |  |
|----|----|
| ID | planned-completion-date |
| Description | Provides the date the control expects to be implemented. Must be present when Implementation Status is "Planned" |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | No remarks |

### Plugin Identifier

|  |  |
|----|----|
| ID | plugin-identifier |
| Description | A tool assigned Plugin ID. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Some vulnerability scanners provide a plug-in ID for a given vulnerability, which should be reported in the POA&M. |

### POA&M ID

|                |                                  |
|----------------|----------------------------------|
| ID             | poam-id                          |
| Description    | A CSP-assigned POA&M identifier. |
| Allowed Values | Unrestricted                     |
| Status         | Active                           |
| Remarks        | No remarks                       |

### Impacted Control

|  |  |
|----|----|
| ID | poam-impacted-control |
| Description | A control impacted by this POA&M item. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Impacted control is required in the POA&M and optional in the SAR. It is allowed in the SAR in anticipation of duplicating open risks from the SAR to the POA&M. |

### Privacy Designation

|                |                                                     |
|----------------|-----------------------------------------------------|
| ID             | privacy-designation                                 |
| Description    | Indicates whether this system is privacy sensitive. |
| Allowed Values | Unrestricted                                        |
| Status         | Deprecated in version 1.0.2                         |
| Remarks        | Deprecated.                                         |

### Privacy Threshold Analysis Q1

|  |  |
|----|----|
| ID | privacy-threshold-analysis-q1 |
| Description | Does the ISA collect, maintain, or share PII in any identifiable form? |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. |

### Privacy Threshold Analysis Q2

|  |  |
|----|----|
| ID | privacy-threshold-analysis-q2 |
| Description | Does the ISA collect, maintain, or share PII from or about the public? |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. |

### Privacy Threshold Analysis Q3

|  |  |
|----|----|
| ID | privacy-threshold-analysis-q3 |
| Description | Has a Privacy Impact Assessment (PIA) ever been performed for the ISA? |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. |

### Privacy Threshold Analysis Q4

|  |  |
|----|----|
| ID | privacy-threshold-analysis-q4 |
| Description | Is there a Privacy Act System of Records Notice (SORN) for this ISA system? |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. |

### Purpose

|                |                                                    |
|----------------|----------------------------------------------------|
| ID             | purpose                                            |
| Description    | Explains the system's purpose.                     |
| Allowed Values | Unrestricted                                       |
| Status         | Active                                             |
| Remarks        | May be used to provide prose for the SAP or POA&M. |

### Assessor's Authorization Recommendation

|  |  |
|----|----|
| ID | recommend-authorization |
| Description | Indicates the assessor's recommendation for initial or continued authorization. |
| Allowed Values | "yes" or "no" |
| Status | Active |
| Remarks | No remarks |

### Resolution Resource

|  |  |
|----|----|
| ID | resolution-resource |
| Description | The back-matter resource reference used to determine which FedRAMP validation rule sets apply. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Response Point

|  |  |
|----|----|
| ID | response-point |
| Description | A property whose presence indicates its parent part is a required point of response for FedRAMP stakeholders. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | This appears in FedRAMP profiles and resolved profile catalogs. For control statements, it signals to the CSP which statements require a response in the SSP. For control objectives, it signals to the assessor which control objectives must appear in the assessment results, which aligns with the FedRAMP test case workbook. |

### Party Identifier

|                |                                                  |
|----------------|--------------------------------------------------|
| ID             | revision-history-party-uuid                      |
| Description    | Identifies the party who authored this revision. |
| Allowed Values | Unrestricted                                     |
| Status         | Active                                           |
| Remarks        | No remarks                                       |

### Risk Adjustment

|  |  |
|----|----|
| ID | risk-adjustment |
| Description | Use to indicate that mitigating factors were identified or implemented, reducing the likelihood or impact of the risk. |
| Allowed Values | "investigating", "pending", "approved" |
| Status | Active |
| Remarks | No remarks |

### Sampling

|  |  |
|----|----|
| ID | sampling |
| Description | Indicates whether a sampling methodology was used instead of assessing the entire system. |
| Allowed Values | "yes" or "no" |
| Status | Active |
| Remarks | No remarks |

### Risk Priority

|  |  |
|----|----|
| ID | sar-risk-priority |
| Description | Assessor's recommended risk priority. Lower numbers are higher priority. One (1) is highest priority. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | No remarks |

### Scan Percentage

|  |  |
|----|----|
| ID | scan-percentage |
| Description | The scan coverage |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Scan Type

|  |  |
|----|----|
| ID | scan-type |
| Description | Identifies the type(s) of scans to be performed on this inventory-item or component. |
| Allowed Values | "infrastructure", "database", "web", or "other" |
| Status | Active |
| Remarks | No remarks |

### eAuth Level (OVERALL)

|  |  |
|----|----|
| ID | security-cia-level |
| Description | The overall electronic authentication (eAuth) level applied to the system. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. |

### Service Processor

|                |                                                |
|----------------|------------------------------------------------|
| ID             | service-processor                              |
| Description    | Name of the interconnection service processor. |
| Allowed Values | Unrestricted                                   |
| Status         | Active                                         |
| Remarks        | No remarks                                     |

### Service Used By

|                |                                   |
|----------------|-----------------------------------|
| ID             | service-used-by                   |
| Description    | Identifies what uses the service. |
| Allowed Values | Unrestricted                      |
| Status         | Deprecated in version 1.0.2       |
| Remarks        | Use rel set to "used-by" instead. |

### Significant Changes Scope

|  |  |
|----|----|
| ID | significant-changes-scope |
| Description | The general quantity of significant change(s) in scope. |
| Allowed Values | "none", "one" or "many" |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### SORN ID

|  |  |
|----|----|
| ID | sorn-id |
| Description | An assigned System of Records Notice (SORN) identifier for this system. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Deprecated. |

### Sort ID

|  |  |
|----|----|
| ID | sort-id |
| Description | Identifier for sort ordering content. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Core OSCAL has a "sort-id" prop, however this "sort-id" extension can be applied to any assembly that provided information which may need to be rendered in a specific order. The step assembly is an example of this. |

### Still Supported

|  |  |
|----|----|
| ID | still-supported |
| Description | Specify if the product / component is still supported by the vendor / manufacturer. |
| Allowed Values | "yes" or "no" |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### System Identifier

|                |                                                            |
|----------------|------------------------------------------------------------|
| ID             | system-id                                                  |
| Description    | The FedRAMP-assigned identifier for this system.           |
| Allowed Values | Unrestricted                                               |
| Status         | Active                                                     |
| Remarks        | Use this extension when an OSCAL SSP cannot be referenced. |

### Test Type

|                |                                                     |
|----------------|-----------------------------------------------------|
| ID             | task-test-type                                      |
| Description    | Indicates the type of test represented by the task. |
| Allowed Values | Unrestricted                                        |
| Status         | Active                                              |
| Remarks        | No remarks                                          |

### User Identifier

|                |                                                     |
|----------------|-----------------------------------------------------|
| ID             | task-user-uuid                                      |
| Description    | Cites the SSP defined user role to use for testing. |
| Allowed Values | Unrestricted                                        |
| Status         | Active                                              |
| Remarks        | No remarks                                          |

### Short Title

|                |                                                            |
|----------------|------------------------------------------------------------|
| ID             | title-short                                                |
| Description    | The short name for the system represented in the resource. |
| Allowed Values | Unrestricted                                               |
| Status         | Active                                                     |
| Remarks        | No remarks                                                 |

### Type

|  |  |
|----|----|
| ID | type |
| Description | The "type" of back-matter resource. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. For locally defined resource types. |

### User Sensitivity Level

|  |  |
|----|----|
| ID | user-sensitivity-level |
| Description | Defines the sensitivity level of the identified user type. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | Values are as required by FedRAMP for packages based on NIST 800-53, Revision 4. Authoritative source: OPM Position Designation (Page 18). |

### External Users

|                |                                                           |
|----------------|-----------------------------------------------------------|
| ID             | users-external                                            |
| Description    | The current number of users external to the organization. |
| Allowed Values | Unrestricted                                              |
| Status         | Deprecated in version 1.0.2                               |
| Remarks        | No remarks                                                |

### Future External Users

|  |  |
|----|----|
| ID | users-external-future |
| Description | The anticipated number of users external to the organization in one year. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | No remarks |

### Internal Users

|                |                                                           |
|----------------|-----------------------------------------------------------|
| ID             | users-internal                                            |
| Description    | The current number of users internal to the organization. |
| Allowed Values | Unrestricted                                              |
| Status         | Deprecated in version 1.0.2                               |
| Remarks        | No remarks                                                |

### Future Internal Users

|  |  |
|----|----|
| ID | users-internal-future |
| Description | The anticipated number of users internal to the organization in one year. |
| Allowed Values | Unrestricted |
| Status | Deprecated in version 1.0.2 |
| Remarks | No remarks |

### Vendor Dependency

|                |                                                        |
|----------------|--------------------------------------------------------|
| ID             | vendor-dependency                                      |
| Description    | A vendor resolution is pending, but not yet available. |
| Allowed Values | "investigating", "pending", "approved"                 |
| Status         | Active                                                 |
| Remarks        | No remarks                                             |

### Vendor Name

|  |  |
|----|----|
| ID | vendor-name |
| Description | The vendor or manufacturer of a component or inventory item. |
| Allowed Values | Unrestricted |
| Status | Active |
| Remarks | Extension added to align with information in FedRAMP rev 5 templates. |

### Vulnerability Identifier

|                |                                   |
|----------------|-----------------------------------|
| ID             | vulnerability-identifier          |
| Description    | A tool assigned vulnerability ID. |
| Allowed Values | Unrestricted                      |
| Status         | Active                            |
| Remarks        | No remarks                        |




