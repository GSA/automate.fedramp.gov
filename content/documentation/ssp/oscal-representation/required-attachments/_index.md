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
| **Appendix B: Related Acronyms** | [No](/documentation/ssp/oscal-representation/acronyms-laws-regulations/#acronyms) | Attach using the `back-matter`, `resource` syntax.<br /><br />For Acronyms, resource must include a `prop` with `@ns="http://fedramp.gov/ns/oscal"`, `@name="type"`, and `@value="fedramp-acronyms"`. |
| **Appendix C: Security Policies and Procedures** | [No](/documentation/ssp/oscal-representation/required-attachments/policies-and-procedures) | Attach using the `back-matter`, `resource` syntax.<br /><br />For Policies, resource must include a `prop` with `@name=”type”`, `@value=”policy”`, and `@class=”control-family”`.<br /><br />For Procedures, resource must include a `prop` with `@name=”type”`, `@value=”procedure”`, and `@class=”control-family”`. |
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
The following OSCAL representation of a FedRAMP SSP attachment demonstrates the `back-matter` and `resource` approach that must be implemented for classic SSP attachments that are not machine-readable, such as policies, procedures, plans, guidance, and rules of behavior documents. For each attachment, an SSP should provide a publication date where possible. However, in some cases, a back matter attachment may not have a specific publication date. In that case, an SSP may define a last accessed property with a value of a datetime with a timezone that represents when that resource was last viewed or referenced, with a value that conforms with RFC3339's "full-date" format. 

##### Attachment Representation
{{< highlight xml "linenos=table" >}}
<!-- cut -->
<back-matter>
    <resource uuid="uuid-value-1">
        <title>Document Title</title>
        <description>Policy document</description>
        <prop name="type" ns="http://fedramp.gov/ns/oscal" value="policy"/>
        <!--For this resource, a property of published is used to define the published date-->
        <prop name="published" ns="http://fedramp.gov/ns/oscal" value="2021-01-01Z"/>
        <prop name="version" ns="http://fedramp.gov/ns/oscal" value="1.2"/>
        <!-- Add rlink with relative path or embed with base64 encoding -->
        <base64>00000000</base64>
    </resource>
    <resource uuid="uuid-value-2">
        <title>Document Title</title>
        <description>Policy document</description>
        <prop name="type" ns="http://fedramp.gov/ns/oscal" value="policy"/>
        <!--For this resource, a property of "last-accessed" is defined, with a value of a datetime with a timezone in RFC3339's "full-date" format-->
        <prop name="last-accessed" ns="http://fedramp.gov/ns/oscal" value="2024-12-23T14:30:00-05:00"/>
        <prop name="version" ns="http://fedramp.gov/ns/oscal" value="1.2"/>
        <!-- Add rlink with relative path or embed with base64 encoding -->
        <base64>00000000</base64>
    </resource>
    <!-- cut: policies 3 - 13 -->
    <resource uuid="uuid-value" />
    <resource uuid="uuid-value" />
    <!-- cut: procedure 2 - 13 -->
</back-matter>
{{</ highlight >}}

##### XPath Queries 
{{< highlight xml "linenos=table" >}}
  The Number of Policies Attached:
    count(/*/back-matter/resource/prop[@name="type"][@ns="http://fedramp.gov/ns/oscal"][string(./@value)="policy"])
  Attachment (Embedded Base64 encoded):
    /*/back-matter/resource[@id="att-policy-1"]/base64
  OR (Relative Link):
    /*/back-matter/resource[@id="att-policy-1"]/rlink/@href
  Title of First Policy Document:
    /*/back-matter/resource/prop[@name="type"][@ns="http://fedramp.gov/ns/oscal"][string(.)="policy"][1]/../prop[@name="title"][@ns="http://fedramp.gov/ns/oscal"]
{{</ highlight >}}

---