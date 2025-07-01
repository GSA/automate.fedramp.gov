---
title: Required Attachments
weight: 339
---
# FedRAMP Appendices and Required Attachments

Classic FedRAMP attachments include a mix of items. Some lend well to
machine-readable format, while others do not. Machine-readable content
is typically addressed within the OSCAL-based FedRAMP SSP syntax, while
policies, procedures, plans, guidance, and the rules of behavior
documents are all treated as classic attachments, as described in the
[*Attachments and Embedded Content*](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#attachments-and-embedded-content) section.
The resource's title and description must be used to provide a
human-readable indicator of what attachment is being referenced;
however, OSCAL extensions must also be provided when applicable for
machine readability. The following table describes how each attachment
is handled:

|**Appendix Name**|**Machine Readable**|**How to Handle in OSCAL**|
| :-- | :-- | :-- |
| **Appendix A: FedRAMP Security Controls** | [Yes](/documentation/ssp/oscal-representation/security-controls/) | This can be generated from the content in the [Security Controls section](/documentation/ssp/oscal-representation/security-controls/) and does not need to be maintained separately or attached. |
| **Appendix B: Related Acronyms** | [No](/documentation/ssp/oscal-representation/acronyms-laws-regulations/#acronyms) | Attach using the `back-matter`, `resource` syntax.<br /><br />For Acronyms, resource must include a `prop` with `@name="type"`, `@value="citation"`, and `@class="acronyms"`. |
| **Appendix C: Security Policies and Procedures** | [No](/documentation/ssp/oscal-representation/required-attachments/policies-and-procedures) | Attach using the `back-matter`, `resource` syntax.  These back matter resources must be referenced from `component`s of type "policy" or "process-procedure" using component `link` with `rel` set to either "policy" or "procedure".<br /><br />For Policies, resource must include a `prop` with `@name=”type”` and `@value=”policy”`.<br /><br />For Procedures, resource must include a `prop` with `@name=”type”` and `@value=”procedure”`.<br /><br /> |
| **Appendix D: User Guide** | [No](/documentation/ssp/oscal-representation/required-attachments/user-guide) | Attach using the `back-matter`, `resource` syntax.<br /><br />For User Guides, resource must include a `prop` with `@name=”type”` and `@value=”users-guide”`. |
| **Appendix E: Digital Identity Worksheet** | [Yes](/documentation/ssp/oscal-representation/digital-identity/) | See the [Digital Identity Determination](/documentation/ssp/oscal-representation/digital-identity/) section. |
| **Appendix F: Rules of Behavior** | [No](/documentation/ssp/oscal-representation/required-attachments/rules-of-behavior) | Attach using the `back-matter`, `resource` syntax.<br /><br />For Rules of Behavior, resource must include a prop with `@name=”type”` and `@value="rules-of-behavior"`. |
| **Appendix G: Information System Contingency Plan (ISCP)** | [No](/documentation/ssp/oscal-representation/required-attachments/iscp) | Attach using the `back-matter`, `resource` syntax.<br /><br />For ISCP, resource must include a `prop` with `@name=”type”`, `@value="plan"`, and `@class="information-system-contingency-plan"`. |
| **Appendix H: Configuration Management Plan (CMP)** | [No](/documentation/ssp/oscal-representation/required-attachments/cmp) | Attach using the `back-matter`, `resource` syntax.<br /><br />For CMP, resource must include a `prop` with `@name=”type”`, `@value="plan"`, and `@class="configuration-management-plan"`. |
| **Appendix I: Incident Response Plan (IRP)** | [No](/documentation/ssp/oscal-representation/required-attachments/irp) | Attach using the `back-matter`, `resource` syntax.<br /><br />For IRP, resource must include a `prop` with `@name=”type”`, `@value="plan"`, and `@class="incident-response-plan"`. |
| **Appendix J: CIS and CRM Workbook** | [Yes](/documentation/ssp/generated-content/#generating-content-from-oscal-based-ssp) | This can be generated from the content in the Security Controls section and does not need to be maintained separately or attached. |
| **Appendix K: FIPS 199 Worksheet** | [Yes](/documentation/ssp/oscal-representation/fips-199-categorization/) | See the [System Sensitivity Level (FIPS-199)](/documentation/ssp/oscal-representation/fips-199-categorization/) section. |
| **Appendix L: CSO-Specific Required Laws and Regulations** | [No](/documentation/ssp/oscal-representation/acronyms-laws-regulations/#laws-and-regulations) | Attach using the `back-matter`, `resource` syntax.<br /><br />For CSO-Specific Required Laws and Regulations, resource must include a `prop` with `@name=”type”` and `@value=”law”`. |
| **Appendix M: Integrated Inventory Workbook** | [Yes](/documentation/ssp/oscal-representation/inventory/)  | See the [System Inventory](/documentation/ssp/oscal-representation/inventory/) section. |
| **Appendix N: Continuous Monitoring Plan** | [No](/documentation/ssp/oscal-representation/required-attachments/conmon-plan) | Attach using the `back-matter`, `resource` syntax.<br /><br />For ConMon, resource must include a `prop` with `@name=”type”`, `@value="plan"`, and `@class="continuous-monitoring-plan"`. |
| **Appendix O: POA&M** | [Yes](/documentation/poam/) | This is maintained separately in an OSCAL POA&M but can be attached using the `back-matter`, `resource` syntax.<br /><br />For POA&M, resource must include a `prop` with `@name=”type”`, `@value="plan"`, and `@class="poam"`. |
| **Appendix P: Supply Chain Risk Management Plan (SCRMP)** | [No](/documentation/ssp/oscal-representation/required-attachments/scrmp) | Attach using the `back-matter`, `resource` syntax.<br /><br />For SCRMP, resource must include a `prop` with `@name=”type”`, `@value="plan"`, and `@class="scrmp"`. |
| **Appendix Q: Cryptographic Module Table** | [Yes](/documentation/ssp/oscal-representation/cryptographic-modules/) | See the [Cryptographic Modules](/documentation/ssp/oscal-representation/cryptographic-modules/) section dealing with components. |

---
### Attachments
The following OSCAL representation of a FedRAMP SSP attachment demonstrates the `back-matter` and `resource` approach that must be implemented for classic SSP attachments that are not machine-readable, such as policies, procedures, plans, guidance, and rules of behavior documents. For each attachment, an SSP should provide a publication date `published` where possible. However, in some cases, a back matter attachment may not have a specific publication date. In that case, an SSP may define a last accessed property with a value of a datetime with a timezone that represents when that resource was last viewed or referenced, with a value that conforms with RFC3339's "full-date" format. 

##### Attachment Representation
{{< tabs JSON XML YAML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "system-security-plan": {
        "uuid": "11111111-2222-4000-8000-000000000000",
        "back-matter": {
            "resources": [
                {
                    "uuid": "11111111-2222-4000-8000-001000000038",
                    "title": "System and Communications Protection Procedure Title",
                    "description": "SC Procedure document",
                    "props": [
                        {
                            "name": "type",
                            "value": "procedure"
                        },
                        {
                            "name": "published",
                            "value": "2023-01-01T00:00:00Z"
                        },
                        {
                            "name": "version",
                            "value": "Document Version"
                        }
                    ],
                    "rlinks": [
                        {"href": "./attachments/policies/sample_SC_procedure.pdf"}
                    ],
                    "base64": {
                        "filename": "sample_procedure.pdf",
                        "media-type": "application/pdf",
                        "value": "00000000"
                    },
                    "remarks": "Table 12-1 Attachments: Procedure Attachment\n\nMay use `rlink` with a relative path, or embedded as `base64`."
                },
                {
                    "uuid": "11111111-2222-4000-8000-001000000039",
                    "title": "System and Information Integrity Procedure Title",
                    "description": "SI Procedure document",
                    "props": [
                        {
                            "name": "type",
                            "value": "procedure"
                        },
                        {
                            "name": "published",
                            "value": "2023-01-01T00:00:00Z"
                        },
                        {
                            "name": "version",
                            "value": "Document Version"
                        }
                    ],
                    "rlinks": [
                        {"href": "./attachments/policies/sample_SI_procedure.pdf"}
                    ],
                    "base64": {
                        "filename": "sample_procedure.pdf",
                        "media-type": "application/pdf",
                        "value": "00000000"
                    },
                    "remarks": "Table 12-1 Attachments: Procedure Attachment\n\nMay use `rlink` with a relative path, or embedded as `base64`."
                }                
            ]
        }
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan uuid="11111111-2222-4000-8000-000000000000">
  <back-matter>
    <resource uuid="11111111-2222-4000-8000-001000000038">
      <title>System and Communications Protection Procedure Title</title>
      <description>
        <p>SC Procedure document</p>
      </description>
      <prop name="type" value="procedure"/>
      <prop name="published" value="2023-01-01T00:00:00Z"/>
      <prop name="version" value="Document Version"/>
      <rlink href="./attachments/policies/sample_SC_procedure.pdf"/>
      <base64 filename="sample_procedure.pdf" media-type="application/pdf">00000000</base64>
      <remarks>
        <p>Table 12-1 Attachments: Procedure Attachment</p>
        <p>May use <code>rlink</code> with a relative path, or embedded as <code>base64</code>.</p>
      </remarks>
    </resource>
    <resource uuid="11111111-2222-4000-8000-001000000039">
      <title>System and Information Integrity Procedure Title</title>
      <description>
        <p>SI Procedure document</p>
      </description>
      <prop name="type" value="procedure"/>
      <prop name="published" value="2023-01-01T00:00:00Z"/>
      <prop name="version" value="Document Version"/>
      <rlink href="./attachments/policies/sample_SI_procedure.pdf"/>
      <base64 filename="sample_procedure.pdf" media-type="application/pdf">00000000</base64>
      <remarks>
        <p>Table 12-1 Attachments: Procedure Attachment</p>
        <p>May use <code>rlink</code> with a relative path, or embedded as <code>base64</code>.</p>
      </remarks>
    </resource>
  </back-matter>
</system-security-plan>
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
system-security-plan:
  uuid: 11111111-2222-4000-8000-000000000000
  back-matter:
    resources:
    - uuid: 11111111-2222-4000-8000-001000000038
      title: System and Communications Protection Procedure Title
      description: SC Procedure document
      props:
      - name: type
        value: procedure
      - name: published
        value: '2023-01-01T00:00:00Z'
      - name: version
        value: Document Version
      rlinks:
      - href: ./attachments/policies/sample_SC_procedure.pdf
      base64:
        filename: sample_procedure.pdf
        media-type: application/pdf
        value: '00000000'
      remarks: |-
        Table 12-1 Attachments: Procedure Attachment

        May use `rlink` with a relative path, or embedded as `base64`.
    - uuid: 11111111-2222-4000-8000-001000000039
      title: System and Information Integrity Procedure Title
      description: SI Procedure document
      props:
      - name: type
        value: procedure
      - name: published
        value: '2023-01-01T00:00:00Z'
      - name: version
        value: Document Version
      rlinks:
      - href: ./attachments/policies/sample_SI_procedure.pdf
      base64:
        filename: sample_procedure.pdf
        media-type: application/pdf
        value: '00000000'
      remarks: |-
        Table 12-1 Attachments: Procedure Attachment

        May use `rlink` with a relative path, or embedded as `base64`.

{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

##### XPath Queries 
{{< highlight xml "linenos=table" >}}
  The Number of Procedures Attached:
    count(/*/back-matter/resource[prop[@name="type" and @value="procedure"]])
  Example Attachments (Embedded Base64 encoded):
    /*/back-matter/resource[@uuid="11111111-2222-4000-8000-001000000038"]/base64
    /*/back-matter/resource[@uuid="11111111-2222-4000-8000-001000000039"]/base64
  OR (Relative Link):
    /*/back-matter/resource[@uuid="11111111-2222-4000-8000-001000000038"]/rlink/@href
    /*/back-matter/resource[@uuid="11111111-2222-4000-8000-001000000039"]/rlink/@href
  Title of First Procedure Document:
    /*/back-matter/resource[prop[@name="type" and @value="procedure"]][1]/title
{{</ highlight >}}
