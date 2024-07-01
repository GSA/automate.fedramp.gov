---
title: What is OSCAL?
weight: 21
toc:
  enabled: true
---
# What is OSCAL?

OSCAL is a collection of data models. These data models define a specific way of representing system security information as structured data that makes it easier for a computer to process.  OSCAL currently provides seven data models described below.

## 1. Catalog

The OSCAL catalog model is used to represent a collection of controls. Controls defined using this model can be easily shared between organizations. This data can be imported into tools to provide up-to-date control information as controls are added, removed, or changed within the catalog.

## 2. Profile

A *profile*, which is often referred to as a *baseline*, is a selection of controls that is intended for a specific purpose. For example, it is common to provide selections of controls that address the relative sensitivity of information contained within a system. More sensitive information requires greater protections from risks. The OSCAL profile model provides a means to represent control selections in a structured form that can be imported into tools to provide up-to-date information about a control baseline. The OSCAL profile references the OSCAL control catalogs and controls used to establish the baseline.

## 3. System Security Plan

The OSCAL SSP model can be used to describe a system in detail. This includes the individual information types, user types, organizational roles, services, software, hardware, policies, and procedures supported by the system. The SSP also provides a means to identify the controls implemented by the system, the controls used by the system that are inherited from other systems, and the controls provided by the system that can be inherited by other systems. This capability, provided by an OSCAL SSP, establishes a shared responsibility approach that makes clear what and who is responsible for managing control implementations that manage risks. An OSCAL SSP also allows control implementations to be described at the system service level, providing for more fine-grained control implementation information, which helps to identify where core security requirements are addressed within the system. An OSCAL SSP references the OSCAL profile that establishes the control baseline for the system.

## 4. Assessment Plan

Assessments of a system are performed to ensure that controls are in place and working effectively to provide the security outcomes as intended. These assessments are performed by either: 1) the organization managing the system, or 2) a trusted third party that can independently analyze the system. The OSCAL assessment plan model provides a means to describe an assessment, the aspects of the system to assess, and the methods used to perform this assessment. An OSCAL assessment plan references the OSCAL SSP for the system the assessment is to be performed on. This supports the ability to reference specific aspects of the system to focus on during the assessment.

## 5. Assessment Results

The OSCAL assessment results model captures the details of an assessment. It provides a means to reference low-level assessment scans, logs, and interview details. Any implementation gaps can be identified as findings, and associated risks can be described using this model. OSCAL assessment results reference the assessment plan that the assessment was based on.

## 6. Plan of Actions and Milestones

When significant findings are identified during an assessment, the OSCAL plan of actions and milestones (POA&M) model can be used to describe and track the status of these findings over time, until the findings are resolved. The OSCAL POA&M model references the OSCAL SSP that describes the current state of the system implementation.

## 7. Component Definition

The OSCAL component definition model provides a means to describe software, hardware, services, processes, procedures, and other related building blocks that can be combined in various ways to form a system. This model serves as a way for providers of these building blocks to describe the possible control implementation details provided, allowing those implementing a system to use these details when documenting the control implementation of a system in an SSP. This OSCAL feature provides for knowledge exchange and potential time savings for people responsible for documenting the expected security outcomes of a system.

Together these models help to support a risk management lifecycle that incorporates a sequence of control selection, documentation, assessment, and after-action management of findings, which then inform another cycle of risk-based control selection, and so on.