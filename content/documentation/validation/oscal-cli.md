---
title: The OSCAL CLI
weight: 230
---
# The OSCAL Command Line Interface (CLI)

OSCAL-CLI is a command-line tool, developed by FedRAMP’s Experience Branch, that allows users to determine whether or not their OSCAL content is valid under FedRAMP’s expectations. The tool checks whether or not OSCAL artifacts, such as System Security Plans (SSPs), meet FedRAMP's requirements before the formal review process, and further provides feedback for correcting invalid FedRAMP OSCAL content. 
Our development efforts involve developing constraints that determine automatically whether packages provide enough information, in the correct format, and in a way that meets FedRAMP’s preliminary expectations. The current release of OSCAL-CLI can fully ingest and validate OSCAL System Security Plans. More extensive validation checks are under development. 
The oscal-cli is intended for use by FedRAMP OSCAL implementers and practitioners, Cloud Service Providers (CSPs), OSCAL tool developers, 3rd Party Assessment Organizations (3PAOs), and federal agencies. Our goal with this tooling is to empower our stakeholders to ensure all preliminary FedRAMP OSCAL requirements are met prior to submission. Use of this tooling will have the added benefit of reducing the number of review passbacks due to incomplete or invalid packages, as customers will be able to address those issues proactively, prior to submission. . 
The current release of OSCAL-CLI as well as continued development efforts to expand the coverage of our tooling and further automate the review of security artifacts can be viewed in our [fedramp-automation github](https://github.com/GSA/fedramp-automation). We welcome any and all feedback.

