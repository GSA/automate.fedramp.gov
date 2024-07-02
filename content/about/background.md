---
title: Background
weight: 20
toc:
  enabled: true
---
# Background

A *risk* is the potential that something might happen that will negatively impact a person or organization. The severity of a risk reflects the likelihood of the risk occurring and the consequence, or impact, caused when it occurs. Risk impact is often measured in terms of financial or reputation loss, but in extreme cases a severe risk may result in loss of life or an impact to national security. The process of *risk management* is used to identify, monitor, and manage risks to avoid or reduce the impact of a risk event or the likelihood that a risk might occur.

Information systems (systems) represent the use of technology, specifically a combination of hardware, software, and services, to create, manage, provide access to, and dispose of information. A *security control* represents a specific policy, procedure, or mechanism that is put in place for a system to achieve a specific security outcome that reduces a related risk.

Examples of security controls include (with SP 800-53 control identifiers):
* **SC-8, SC-13:** Protecting information that is exchanged with and within a system using cryptographic methods that obscure the exchanged data or ensure that data has not been tampered with.
* **RA-5:** Ensuring that software used within a system is up-to-date and free of known errors that may allow a malicious actor to bypass another security control.
* **AT-1:** Defining a policy and procedure for training staff on current security risks.
* **RA-3, RA-7:** Ensuring that new security risks are identified and managed on an ongoing basis.

Security experts select appropriate security controls as part of a risk management approach that considers: 1) the likelihood that a malicious actor might exploit an unprotected aspect of the system, and 2) the harm that an accidental or malicious action may cause to the owner of the information or the organization operating the system. Organizations document these risks and the security controls selected to manage them in a *system security plan (SSP)*. A system security plan provides a shared understanding of the expected security outcomes provided by the system.

Modern systems have become highly complex, consisting of hardware, software, and services that are provided by multiple organizations with different risk considerations. Systems are often packaged as services that provide a common set of features that can be used by multiple organizations. Organizations and systems use these services, creating a web of dependencies and associated risks that need to be understood to provide adequate protections.

Traditionally, an SSP is a document containing hundreds of pages written by humans. The sheer volume and technical nature of this documentation is difficult and time-consuming to produce and equally difficult and time-consuming to read and understand.

OSCAL provides a means to represent this information in a way that computers can more easily parse and use, allowing for automated processing of this information in a way that saves humans a considerable amount of time in understanding the security outcomes provided by the related system.
