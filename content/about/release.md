---
title: Release Strategy and Versioning
menu:
  primary:
    name: Release Strategy / Versioning
    parent: About
    weight: 40
toc:
  enabled: true
---

# Release Strategy and Versioning

There are a number of resources used by FedRAMP partners in efforts to get authorized, stay authorized, or use authorized cloud services. These resources include:

- NIST Special Publication (SP) 800-53 catalog revisions
- NIST SP 800-53B baseline revisions
- NIST SP 800-53A assessment procedure revisions
- NIST OSCAL releases
- FedRAMP baseline revisions
- FedRAMP OSCAL guide updates
- NIST and FedRAMP OSCAL validations
- A variety of FedRAMP guides and templates

There is a need to coordinate each set of changes across these resources using a unified versioning approach that aggregates these changes into a single *FedRAMP version*. A FedRAMP version will provide a stable revision that can be identified in FedRAMP packages, continuous monitoring data, and tools that support the creation and maintenance of these data sets. 

This FedRAMP versioning strategy will:

- Allow versioned resources to move as a unit within a given release.
- Support incremental change over time in versioned resources.
- Provide content and semantic compatibility tied to a specific version, allowing version-based data to be used by different tools.
- Minimize disruption for tool maintainers by indicating when a major change is compatibility breaking.

[SemVer](https://semver.org/), which is short for semantic versioning, is used as a common practice to version software. Using SemVer, version numbers convey meaning around the degree of compatibility resulting from modifications made to the underlying code or tool.

A SemVer is the combination of *MAJOR*.*MINOR*.*PATCH* as follows:

- Incrementing the **MAJOR** version indicates significant incompatible changes.
- Incrementing the **MINOR** version adds functionality in a backward-compatible manner.
- Incrementing the **PATCH** version indicates backward-compatible bug fixes.

## Versioning Examples

Examples of FedRAMP using SemVer in a sequence:

- `3.0.0` (MAJOR: 3, MINOR: 0, PATCH : 0) indicates the MAJOR release 3.
- `3.0.1` (MAJOR: 3, MINOR: 0, PATCH : 1) indicates the first PATCH release for MAJOR release 3.
- `3.1.0` (MAJOR: 3, MINOR: 1, PATCH : 0) indicates the first MINOR release for MAJOR release 3.

The following illustrates some drivers that will motivate specific version changes.

### PATCH

A PATCH is used to indicate when a defect is identified that prevents the creation or use of data.

Incrementing the PATCH segment will occur in the following cases:

- **SP 800-53 catalog:** Editorial corrections to the text of an SP 800-53 control that do not change the control's meaning.
- **NIST OSCAL:** An OSCAL PATCH release.
- **FedRAMP OSCAL Guides:** Corrections to a guide that do not change the meaning of a requirement, such as fixing an obvious error or improving understanding.
- **NIST and FedRAMP OSCAL validations:** Corrections to address validation false positives.

### MINOR

A MINOR version change is used to signal the addition of a new, optional data feature. 

Incrementing the MINOR segment will occur in the following cases:

- **SP 800-53 catalog:** The addition of a new control or control enhancement.
- **SP 800-53B or FedRAMP baseline:** The addition or removal of a control from a baseline.
- **NIST OSCAL:** An OSCAL MINOR release.
- **FedRAMP OSCAL Guides:** The addition of new guidance that does not change a requirement.
- **NIST and FedRAMP OSCAL validations:** Changes to validations that do not change a requirement.

### MAJOR

A MAJOR version change is used to signal backwards incompatibility.

Incrementing the MAJOR segment will occur in the following cases:

- **SP 800-53 catalog:** Removal of a control or control enhancement, or a change to the meaning of a control or control enhancement.
- **NIST OSCAL:** An OSCAL MAJOR release.
- **FedRAMP OSCAL Guides:** Changes to a guide that change a requirement or that fix a non-obvious error.
- **NIST and FedRAMP OSCAL validations:** Changes to validations that change a requirement.
