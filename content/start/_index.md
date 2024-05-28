---
title: Getting Started
heading: Creating OSCAL-Based Content
menu:
  primary:
    name: Getting Started
    weight: 10
toc:
  enabled: true
---

Open Security Controls Assessment Language (OSCAL) is a standardized format developed by NIST to facilitate the exchange and processing of security control information. For developers new to OSCAL, here is a step-by-step guide to help you get started.

### 1. Understand the Basics of OSCAL

Before diving into implementation, it's essential to grasp what OSCAL is and its purpose. OSCAL is designed to standardize the format for documenting, sharing, and assessing security controls. It uses XML, JSON, and YAML formats to define and automate security controls and assessment data.

#### Key Components of OSCAL

- **Catalogs**: Define security controls.
- **Profiles**: Tailor controls to specific needs.
- **System Security Plans (SSPs)**: Document how controls are implemented.
- **Assessment Plans (SAPs)**: Define how assessments are conducted.
- **Assessment Results (SARs)**: Document the outcomes of assessments.
- **Plan of Action and Milestones (POA&M)**: Track issues and remediation plans.
---

### 2. Set Up Your Development Environment

To work with OSCAL, you’ll need tools for handling XML, JSON, and YAML. Here’s a basic setup:

#### Required Tools

- **XML/JSON/YAML Editors**: Tools like VSCode, Sublime Text, or IntelliJ IDEA.
- **Format Validation Tools**: Validators or tools like xmllint (for XML), jq (for JSON), and yamllint (for YAML).
- **Version Control**: Use Git to manage versions of your OSCAL documents.
- **Programming Language**: Programming languages such as Java, JavaScript/TypeScript, Python, or other languages with libraries to manipulate these formats, if you need to develop custom tools or integrations.

#### Recommended Tools

- **Governance Risk and Compliance (GRC) Platforms**: Use of an OSCAL-capable GRC can greatly simplify creation and management of your OSCAL documents.
- **Document Database**: May provide desired features for easier storage and querying of OSCAL data.
---

### 3. Explore the FedRAMP Automation Repository

Clone or download the FedRAMP Automation repository for access to FedRAMP OSCAL models, examples, documentation and more.

#### Steps

1. **Clone the OSCAL repository**:
  {{< highlight bash "linenos=table" >}}
    git clone https://github.com/GSA/fedramp-automation.git
  {{</ highlight >}}

2. **Explore the directory structure** to familiarize yourself with the contents.  Key directories include:
  - **dist/content**: Contains FedRAMP OSCAL baselines (profiles and resolved profile catalogs), FedRAMP OSCAL templates (SSP, SAP, SAR, and POA&M), and other resources.
  - **documents**: Contains the FedRAMP OSCAL Guides. NOTE - these guides are replaced by the documentation and guidance provided by this website.
  - **presentations**: Contains presentations from its OSCAL Data Bites monthly community meetings.
  - **src**: Contains the source files for FedRAMP OSCAL content (baselines and templates) and examples (e.g., validation).
---

### 4. Create Your First OSCAL Document

Start by creating a simplified version of an FedRAMP OSCAL SSP document. Use the examples in the **dist/content** repository folders as a reference.

**Example: Creating a FedRAMP SSP**
1. Copy [template SSP](https://github.com/GSA/fedramp-automation/tree/master/dist/content/rev5/templates/ssp) from the repository.
2. Modify the copied file to include your system characteristics, system implementation details, and control implementations.
3. Validate the modified SSP (e.g., using one of the available open-source [validation tools](https://pages.nist.gov/OSCAL/resources/tools/)).
---

### 5. Automate and Integrate

For large scale implementations, you'll likely need to automate the creation, validation and processing of your OSCAL documents.  Consider using OSCAL-aware scripts and tools (open-source and/or commercial) that integrate with your existing systems.

---

### 6. Join the FedRAMP Automation Community

Engage with other OSCAL users and developers to share knowledge and to get assistance.  Participate in our discussion forums.

**Resources:**
- Explore [OSCAL resources](/resources/).
- Attend a FedRAMP [OSCAL Data Bites session](/resources/#data-bites).
- Ask questions at [https://github.com/GSA/fedramp-automation/issues](https://github.com/GSA/fedramp-automation/issues).
- Email us at oscal@fedramp.gov.