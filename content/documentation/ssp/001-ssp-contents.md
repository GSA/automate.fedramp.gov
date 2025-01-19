---
title: Contents
weight: 103
---
# FedRAMP SSP Contents

For SSP-specific content, each main section of the SSP is represented in this section, along with OSCAL code snippets for representing the information in OSCAL syntax. There is also XPath syntax for querying the code in an OSCAL-based FedRAMP SSP represented in XML format.

Content that is common across OSCAL file types is described in the *[FedRAMP OSCAL Documentation](/documentation).* This includes the following:

- [**Title Page**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#title-page)
- [**Prepared By/For**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#prepared-by-third-party)
- [**Record of Template Changes**](/documentation/general-concepts/oscal-file-concepts/#oscal-syntax-versions)
- [**Revision History**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#document-revision-history)
- [**How to Contact Us**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#how-to-contact-us)
- [**Document Approvers**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#document-approvals)
- [**Acronyms and Glossary**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#fedramp-standard-attachments-acronyms-lawsregulations)
- [**Laws, Regulations, Standards and Guidance**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#additional-laws-regulations-standards-or-guidance)
- [**Attachments and Citations**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#attachments-and-embedded-content)

It is not necessary to represent the following sections of the SSP template in OSCAL; however, tools should present users with this content where it is appropriate:

-   Any blue-text instructions found in the SSP template where the instructions are related to the content itself

-   Table of contents

-   Introductory and instructive content in section 1, such as references to NIST SP 800-60, Guide to Mapping Types and the definitions from FIPS Pub 199

-   The control origination definitions are in appendix A of the SSP template; however, please note that hybrid and shared are represented in OSCAL by specifying more than one control origination.

The OSCAL syntax in this documentation may be used to represent the High, Moderate, Low and LI-SaaS FedRAMP SSP Templates. Simply ensure the correct FedRAMP baseline is referenced using the `import-profile` statement.

**NOTE: The FedRAMP SSP template screenshots in the sections that follow vary slightly from the most current version of the FedRAMP rev 5 SSP template.**


