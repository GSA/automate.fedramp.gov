---
title: General Template Information
weight: 100
aliases:
  - /documentation/ssp/3-working-with-oscal-files/#oscal-based-fedramp-ssp-template
---
# General Template Information

For SSP-specific content, each main section of the SSP is represented in this section, along with OSCAL code snippets for representing the information in OSCAL syntax. There is also XPath syntax for querying the code in an OSCAL-based FedRAMP SSP represented in XML format.

Content that is common across OSCAL file types is described in the *[FedRAMP OSCAL Documentation](/documentation).* This includes the following:

- [**Title Page**](/documentation/common-fedramp-elements/title-page-information)
- [**Prepared By/For**](/documentation/common-fedramp-elements/prepared-by-for)
- [**Revision History**](/documentation/common-fedramp-elements/document-revision-history)
- [**Document Approvers**](/documentation/common-fedramp-elements/document-approvals)
- [**Acronyms and Glossary**](/documentation/common-fedramp-elements/attachments)

It is not necessary to represent the following sections of the SSP template in OSCAL; however, tools SHOULD present users with this content where it is appropriate:

-   Any blue-text instructions found in the SSP template where the instructions are related to the content itself

-   Table of contents

-   Introductory and instructive content in section 1, such as references to NIST SP 800-60, Guide to Mapping Types and the definitions from FIPS Pub 199

-   The control origination definitions are in appendix A of the SSP template; however, please note that hybrid and shared are represented in OSCAL by specifying more than one control origination.

The OSCAL syntax in this documentation may be used to represent the High, Moderate, Low and LI-SaaS FedRAMP SSP Templates. Simply ensure the correct FedRAMP baseline is referenced using the `import-profile` statement.

**NOTE: The FedRAMP SSP template screenshots in the sections that follow vary slightly from the most current version of the FedRAMP rev 5 SSP template.**
