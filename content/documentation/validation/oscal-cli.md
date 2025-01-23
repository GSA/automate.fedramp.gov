---
title: The OSCAL CLI
weight: 230
---
# The OSCAL Command Line Interface (CLI)

The [oscal-cli command-line tool](https://github.com/metaschema-framework/oscal-cli) allows users to easily convert, validate, and process OSCAL data for a variety of use cases.  When using [FedRAMP's OSCAL Constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints#what-are-they) with oscal-cli, users can easily and efficiently check if their OSCAL content is valid under FedRAMP’s requirements. The tool checks whether [Digital Authorization Package data](https://www.fedramp.gov/updates/pilots/digital-authorization-package/), such as System Security Plans (SSPs), meet FedRAMP's requirements before the formal review process, and further provides precise feedback for correcting invalid FedRAMP OSCAL content. 
Our development efforts involve developing constraints that determine automatically whether packages provide enough information, in the correct format, and in a way that meets FedRAMP’s preliminary expectations. The current release of OSCAL-CLI can fully ingest and validate OSCAL System Security Plans. More extensive validation checks are under development. 
The oscal-cli is intended for use by FedRAMP OSCAL implementers and practitioners, Cloud Service Providers (CSPs), OSCAL tool developers, 3rd Party Assessment Organizations (3PAOs), and federal agencies. Our goal with this tooling is to empower our stakeholders to ensure all preliminary FedRAMP OSCAL requirements are met prior to submission. Use of this tooling will have the added benefit of reducing the number of review passbacks due to incomplete or invalid packages, as customers will be able to address those issues proactively, prior to submission. . 
The current release of OSCAL-CLI as well as continued development efforts to expand the coverage of our tooling and further automate the review of security artifacts can be viewed in our [fedramp-automation github](https://github.com/GSA/fedramp-automation). We welcome any and all feedback.

