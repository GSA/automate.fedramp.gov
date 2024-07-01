---
title: OSCAL-based FedRAMP Baselines
weight: 135
---
# OSCAL-Based FedRAMP Baselines

NIST designed OSCAL catalogs as the primary source of control definition
information from a framework publisher. Catalogs are typically only
published by organizations such as NIST for NIST SP 800-53, or ISO/IEC
for standards such as their 27000 series. If an organization has unique
control definitions that fall outside an applicable framework, the
organization must create a catalog containing those unique control
definitions.

NIST designed profiles as the primary means of defining a baseline of
controls. An OSCAL profile may identify and even modify controls from
one or more catalogs and even from other profiles. This approach ensures
control additions, modifications, or removal are fully traceable back to
the source of the modification.

{{< figure src="/img/content-figure-13.png" title="FedRAMP baseline." alt="Figure showing how the FedRAMP uses OSCAL profiles to define its baselines." >}}

FedRAMP\'s baselines are represented as OSCAL profiles. The correct
profile must be selected from the SSP based on the system\'s identified
security categorization level. This can be checked using the XPath
syntax below.

### Security Sensitivity Level XPath Query
{{< highlight xml "linenos=table" >}}
  (SSP) Security Categorization Level:
    /*/system-characteristics/security-sensitivity-level
{{</ highlight >}}

This determines which URL should be entered for the `import-profile` field
in an OSCAL-based FedRAMP SSP.

### Baseline Representation
{{< highlight xml "linenos=table" >}}
  <!-- metadata -->
  <!-- This must point to the appropriate FedRAMP Baseline -->
  <import-profile
  href="https://path/to/FedRAMP_MODERATE-baseline_profile.xml"/>
  <!-- system-characteristics -->
{{</ highlight >}}

FedRAMP validation tools will compare the identified security
categorization level to the actual FedRAMP baseline specified in the SSP
and raise a warning if a different baseline was used.

|**High (Rev 5)**|
| :-- |
| **XML Version:** <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/xml/FedRAMP_rev5_HIGH-baseline_profile.xml>|
| **JSON Version:** <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/json/FedRAMP_rev5_HIGH-baseline_profile.json>|

|**Moderate (Rev 5)**|
| :-- |
| **XML Version:** <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/xml/FedRAMP_rev5_MODERATE-baseline_profile.xml>|
| **JSON Version:** <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/json/FedRAMP_rev5_MODERATE-baseline_profile.json>|

|**Low (Rev 5)**|
| :-- |
| **XML Version:** <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/xml/FedRAMP_rev5_LOW-baseline_profile.xml>|
| **JSON Version:** <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/json/FedRAMP_rev5_LOW-baseline_profile.json>|

**Do not copy and modify the FedRAMP baseline.** FedRAMP will use the
original, published file for validation, ignoring any modified copies.

If you require a modification to the FedRAMP baselines, such as may be
required when directed to do so by an authorizing official, first
contact FedRAMP to coordinate the modification, then follow the
instructions in Appendix B.

When FedRAMP publishes baselines for NIST SP 800-53 Revision 5, they
will be located here:\
<https://github.com/GSA/fedramp-automation/tree/master/dist/content/rev5/baselines>

## *FedRAMP Tailored*

FedRAMP Tailored for Low Impact -- Software as a Service (LI-SaaS)
Appendix B merges SSP, SAP, and SAR information into a single document.
The SSP portions of that document may be represented using the same
OSCAL conventions described in this document with only a few minor
differences.

Specific OSCAL-based FedRAMP Tailored guidance will be published at a
later date; however, fully representing Appendix B in OSCAL requires the
SSP, SAP, and SAR syntax, used the same way as they are explained for
FedRAMP Low, Moderate, and High baselines.

For your convenience, FedRAMP has made the FedRAMP Tailored for LI-SaaS
baseline available in both XML and JSON formats as follows:

|**Low-Impact SaaS (Tailored)**|
| :-- |
| **XML Version:** <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/xml/FedRAMP_rev5_LI-SaaS-baseline_profile.xml>|
| **JSON Version:** <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/json/FedRAMP_rev5_LI-SaaS-baseline_profile.json>|

## Modifying a FedRAMP Baseline

OSCAL is designed to allow modification of controls and baselines, while
maintaining traceability through each layer of modification. This means
you must create a new profile as a means of modifying an existing
profile.

If you require a change to a FedRAMP baseline, you should first
coordinate that change with FedRAMP. Assuming FedRAMP
agrees with the change, the correct way to implement the change is as
follows:

1.  **Create a new, blank OSCAL Profile.**

2.  **Point to the FedRAMP Baseline**: Point it to the appropriate
    FedRAMP baseline using an `import` field.

3.  **Select the Relevant Controls**: Use the `include` and `exclude` fields
    to identify the controls to include or exclude from the FedRAMP
    baseline.

    a.  For example, if you need all but one control, you can `include all`, then `exclude` the one.

4.  **Specify How Controls Are Organized**: FedRAMP prefers you merge
    \"as-is\" using those merge fields. This is relevant when resolving
    the profile. See the [*Profile Resolution*](/documentation/general-concepts/profile-resolution/) documentation
    for more information.

5.  **Modify the Selected Controls**: Use the `modify` assembly to make modifications to parameters and control definitions.

{{< callout >}}
Create a new profile, importing to the appropriate FedRAMP profile, then use profile syntax to make necessary changes.

**FedRAMP does not typically allow modifications to its baselines. This capability is present only in the event of a policy change or unforeseen circumstances.**
{{</ callout >}}


Below is an example profile, which accomplishes the
following actions:

-   Imports the FedRAMP Moderate baseline

-   Includes all controls from that baseline

-   Explicitly removes AT-4 from the baseline

-   Indicates that if this profile is resolved, the organization of the
    controls should remain as-is. See the [*Profile Resolution*](/documentation/general-concepts/profile-resolution/) section
    for more information.

-   Adds a constraint to the third parameter of AC-1 (ac-1_prm_3), which
    is more restrictive than the FedRAMP constraint, by changing it
    from \"at least annually\" to \"at least every six months.\"

-   Removes the additional FedRAMP requirement statement in AU-11 and
    replaces it with a more restrictive statement, which requires
    online retention of audit records for at least 180 days instead of
    90 days.

For more information on working with profiles, please visit the NIST
OSCAL site at:\
<https://pages.nist.gov/OSCAL>

A complete OSCAL profile syntax reference is available here:\
[https://pages.nist.gov/OSCAL/concepts/layer/control/profile/](https://pages.nist.gov/OSCAL/concepts/layer/control/profile/)

### Sample Profile to Modify a FedRAMP Baseline
{{< highlight xml "linenos=table" >}}
<profile xmlns="http://csrc.nist.gov/ns/oscal/1.0"
    uuid="-UUID-value-cut-">
    <metadata>
        <title>[XYZ Org] Modification to FedRAMP Moderate Baseline</title>
        <last-modified>2023-03-06T08:05:30.000Z</last-modified>
        <version>fedramp2.0.0-oscal1.0.4</version>
        <oscal-version>1.0.4</oscal-version>
    </metadata>
    <import href="https://path/to/FedRAMP_MODERATE-baseline_profile.xml">
        <!-- Include every control (and child control) in the Moderate baseline -->
        <include-all />
        <exclude-controls with-child-controls="yes">
            <!-- Remove Control AT-4 -->
            <with-id>at-4</with-id> 
        </exclude-controls>
    </import>
    <merge><as-is>yes</as-is></merge>
    <modify>
        <set-parameter id="ac-1_prm_3">
            <!-- Change the constraint from "at least annually" -->
            <constraint>
                <description>
                    <p>at least every six months</p>
                </description>
            </constraint>
        </set-parameter>        
        <alter control-id="au-11">
            <remove by-id="au-11_fr" />
            <add position="ending">
                <part id="au-11_fr" name="item">
                    <title>[XYZ Org]Modified Requirement</title>
                    <part id="au-11_fr_smt.1" name="item">
                        <prop name="label">Requirement:</prop>
                        <p>The service provider retains audit records on-line for at least 180 days and further preserves audit records off-line for a period that is in accordance with NARA requirements.</p>
                    </part>
                </part>
            </add>
        </alter>
    </modify>
</profile>
{{</ highlight >}}
