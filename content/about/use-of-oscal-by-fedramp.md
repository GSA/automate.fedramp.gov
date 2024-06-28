---
title: Use of OSCAL by FedRAMP
weight: 22
toc:
  enabled: true
---
# Use of OSCAL by FedRAMP

## FedRAMP

FedRAMP is responsible for ensuring that security risks are properly identified, monitored, and managed for services that are hosted by third-party cloud service providers used by the Federal Government. Cloud computing is the practice of providing hosted services using remote, internet-accessible computer systems that store, maintain, manage, and process information.

FedRAMP is responsible for coordinating the activities of many stakeholder groups to ensure that the Federal Government can safely and easily take advantage of cloud services to meet agency mission objectives.

## NIST

The National Institute of Standards and Technology (NIST) is responsible for maintaining a catalog of security and privacy controls, which is published as NIST Special Publication (SP) 800-53. NIST also publishes related baselines and assessment procedures based on the SP 800-53 controls. The OSCAL catalog and profile models provide NIST with a means to publish this control information in a way that computers can easily access and process. This allows tools to quickly adopt changes to SP 800-53 and related publications as NIST makes changes.

## CSPs

Cloud service providers (CSPs) offer and manage cloud-based information systems that are used by federal agencies. CSPs are able to use OSCAL SSPs to document the control implementations for their systems providing cloud services. CSPs can also use the OSCAL assessment plan and assessment results models to document plans and results for their own assessments, supporting initial and ongoing assessment, the latter of which supports reporting to FedRAMP identified flaws and misconfigurations in the hardware and software they use. Through these activities, CSPs can use automated methods to keep their SSPs up-to-date.

## 3PAOs

Third-party assessors, who independently verify the implementation of controls in CSP and agency systems, can use the OSCAL SSP, assessment plan, and assessment results models to plan and document the assessments they perform. When reviewing these assessments, other parties can determine what exactly was and was not assessed, and what findings and risks were identified during the assessment process.

FedRAMP is making investments into tooling that will allow it to automatically receive SSPs, assessment plans, and assessment results from CSPs and third-party assessors supporting the initial authorization and continuous assessment processes they regularly perform. In initial authorization, FedRAMP reviews the SSP and assessment results to determine if the implemented security controls meet desired security outcomes, ensuring core security requirements are met. For ongoing assessment, FedRAMP continuously monitors cloud-based systems to ensure that controls remain effective, identified flaws and misconfigurations in hardware and software are remedied, and new risks are identified and managed as the CSP systems are changed over time to incorporate new features needed by the government.

Visibility into the web of leveraged systems provides FedRAMP, agencies, and CSPs reusing other cloud services with insight into risks that span multiple cloud systems. This visibility allows FedRAMP to develop metrics and to proactively manage risk at a government- and cloud-wide scale that has not been possible previously. The visibility needed to do this is only possible using the rich contextual information provided by the OSCAL SSP and assessment models, and the automation afforded by OSCAL-based data exchanges providing this data directly to FedRAMP.

## Federal Agencies 

Federal agencies can use OSCAL SSPs and information derived from OSCAL assessment plans and results to ensure that agency risks are properly managed, and that the systems agencies build and operate using cloud services meet security expectations. The OSCAL SSP can be used to understand agency responsibilities for implementing security controls needed to securely use cloud-based services. Agencies can also use the SSP model to document their own security control implementations as part of fulfilling these responsibilities.

## Tool Providers

Finally, OSCAL can be put to use by tool providers, such as those providing governance, risk, and compliance (GRC) tools that support all of the stakeholders in the FedRAMP ecosystem. Advancement of OSCAL-based capabilities in GRC tools is essential to supporting the OSCAL-based data exchanges described above.