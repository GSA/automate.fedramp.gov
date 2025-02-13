---
title: FedRAMP Baselines
weight: 173
---

# OSCAL-Based FedRAMP Baselines

OSCAL catalogs are designed to be the primary source of control definition
information from a framework publisher.

Typically, catalogs are published only by organizations such as NIST for NIST SP 800-53 or ISO/IEC
for standards such as their 27000 series. If an organization has unique
control definitions that fall outside an applicable framework, the
organization must create a catalog, containing unique control definitions.

Profiles are the primary means of defining a baseline of
controls. An OSCAL profile may identify and modify controls from
one or more catalogs and from other profiles. This approach ensures
control additions, modifications, or removal are fully traceable back to
the source of the modification.

{{< figure src="/img/content-figure-13.png" title="FedRAMP baseline." alt="Figure showing how the FedRAMP uses OSCAL profiles to define its baselines." >}}


## Baseline Representation

FedRAMP's baselines are represented as OSCAL profiles. The correct
profile must be selected from the SSP based on the system's identified
security categorization level. This can be checked using the XPath syntax below.

{{< highlight xml "linenos=table" >}}
  (SSP) Security Categorization Level:
  /*/system-characteristics/security-sensitivity-level
{{</ highlight >}}

This determines which URL should be entered for the `import-profile` field
in an OSCAL-based FedRAMP SSP. 

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    // metadata
    // The import-profile href flag must point to the appropriate FedRAMP Baseline.
    "import-profile": {
        "href": "https://path/to/FedRAMP_MODERATE-baseline_profile.xml"
    },
    // system-characteristics
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  # metadata
  # The import-profile href flag must point to the appropriate FedRAMP Baseline.
  import-profile:
    href: https://path/to/FedRAMP_MODERATE-baseline_profile.xml
  # system-characteristics
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<!-- metadata -->
<!-- The import-profile href flag must point to the appropriate FedRAMP Baseline. -->
<import-profile href="https://path/to/FedRAMP_MODERATE-baseline_profile.xml"/>
<!-- system-characteristics -->
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

FedRAMP validation tools will compare the identified security
categorization level to the actual FedRAMP baseline specified in the SSP
and raise a warning if a different baseline was used.

| Baseline  | Version                                                                                                                                                                                                                                                                                                        |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| High      | JSON: <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/json/FedRAMP_rev5_HIGH-baseline_profile.json> <br><br>XML: <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/xml/FedRAMP_rev5_HIGH-baseline_profile.xml>         |
| Moderate  | JSON: <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/json/FedRAMP_rev5_MODERATE-baseline_profile.json> <br><br>XML: <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/xml/FedRAMP_rev5_MODERATE-baseline_profile.xml> |
| Low       | JSON: <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/json/FedRAMP_rev5_LOW-baseline_profile.json> <br><br>XML: <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/xml/FedRAMP_rev5_LOW-baseline_profile.xml>           |

**Do not copy and modify the FedRAMP baseline.** FedRAMP will use the
original, published file for validation, ignoring any modified copies.

If you require a modification to the FedRAMP baselines, such as may be
required when directed to do so by an authorizing official, first
contact FedRAMP to coordinate the modification, then follow the
instructions in Appendix B.

When FedRAMP publishes baselines for NIST SP 800-53 Revision 5, they
will be located here:\
<https://github.com/GSA/fedramp-automation/tree/master/dist/content/rev5/baselines>


## FedRAMP Tailored

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

| Baseline                   | Version                                                                                                                                                                                                                                                                                                      |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Low-Impact SaaS (Tailored) | JSON: <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/json/FedRAMP_rev5_LI-SaaS-baseline_profile.json> <br><br>XML: <https://raw.githubusercontent.com/GSA/fedramp-automation/master/dist/content/rev5/baselines/xml/FedRAMP_rev5_LI-SaaS-baseline_profile.xml> |


## Modifying a FedRAMP Baseline

OSCAL is designed to allow modification of controls and baselines, while
maintaining traceability through each layer of modification. This means
you must create a new profile as a means of modifying an existing
profile.

If you require a change to a FedRAMP baseline, you should first
coordinate with FedRAMP. If FedRAMP agrees with the change, to modify the baseline

1.  Create a blank OSCAL profile.

2.  Using the `import` field, point the created profile to the appropriate FedRAMP Baseline.

3.  Using the `include` and `exclude` fields, select controls to include or exclude from the FedRAMP baseline. <br>For example, if you need all but one control, you can specify `include all`, and then `exclude` the one control you do not need.

4.  Organize the controls. <br>FedRAMP prefers that you merge
    `as-is`, using merge fields. This is relevant when resolving
    the profile. <br>For more information, see [Profile Resolution](/documentation/general-concepts/profile-resolution/).

5.  Using the `modify` assembly, edit parameters and control definitions.

{{< callout >}}
*IMPORTANT:* Typically, FedRAMP does not allow modifications to its baselines. The only exceptions are a policy change or unforeseen circumstances.
{{</ callout >}}


## Sample Profile to Modify a FedRAMP Baseline

This section describes a sample profile, which

1. Imports the FedRAMP Moderate baseline.

2. Includes all controls from the Moderate baseline.

3. Removes the `AT-4` control from the baseline.

4. Indicates that if this profile is resolved, the organization of the controls should remain as-is. <br>For more information, see [Profile Resolution](/documentation/general-concepts/profile-resolution/).

5. In the third AC-1 parameter (`ac-1_prm_3`), adds the `at least every six months` constraint. <br>This makes it more restrictive than the default `at least annually` FedRAMP constraint.

6. In the `AU-11` requirement, replaces the FedRAMP `at least 90 days` statement for online retention of audit records with a more restrictive `at least 180 days` statement.

For more information about working with profiles, visit [https://pages.nist.gov/OSCAL](https://pages.nist.gov/OSCAL).

You can find a complete OSCAL profile syntax reference at [https://pages.nist.gov/OSCAL/concepts/layer/control/profile/](https://pages.nist.gov/OSCAL/concepts/layer/control/profile/).

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "profile": {
        "xmlns": "http://csrc.nist.gov/ns/oscal/1.0",
        "uuid": "[UUID-value]",
        "metadata": {
            "title": "Modification to FedRAMP Moderate Baseline",
            "last-modified": "2025-03-06T08:05:30.000Z",
            "version": "fedramp2.0.0-oscal1.0.4",
            "oscal-version": "1.0.4"
        },
        "import": {
            "href": "https://path/to/FedRAMP_MODERATE-baseline_profile.xml",
            // Include every control in the Moderate baseline.
            "include-all": {},
            // Remove the "AT-4" control.
            "exclude-controls": {
                "with-child-controls": "yes",
                "with-id": "at-4"
            }
        },
        "merge": {
            "as-is": "yes"
        },
        "modify": {
            "set-parameter": {
                "id": "ac-1_prm_3",
                // Change the "at least annually" constraint to "at least every six months".
                "constraint": {
                    "description": "at least every six months"
                }
            },
            "alter": {
                "control-id": "au-11",
                "remove": {
                    "by-id": "au-11_fr"
                },
                "add": {
                    "position": "ending",
                    "part": {
                        "id": "au-11_fr",
                        "name": "item",
                        "title": "Modified Requirement",
                        "part": {
                            "id": "au-11_fr_smt.1",
                            "name": "item",
                            "prop": {
                                "name": "label",
                                "#text": "Requirement:"
                            },
                            // Replace the "at least 90 days" statement for online retention of audit records with a more restrictive "at least 180 days" statement.
                            "p": "The service provider retains audit records on-line for at least 180 days and further preserves audit records off-line for a period that is in accordance with NARA requirements."
                        }
                    }
                }
            }
        }
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
profile:
  - xmlns: http://csrc.nist.gov/ns/oscal/1.0
  - uuid: [UUID-value]
  metadata:
    title: Modification to FedRAMP Moderate Baseline
    last-modified: 2025-03-06T08:05:30.000Z
    version: fedramp2.0.0-oscal1.0.4
    oscal-version: 1.0.4
  import:
    - href: https://path/to/FedRAMP_MODERATE-baseline_profile.xml
    # Include every control in the Moderate baseline.
    include-all:
    # Remove the "AT-4" control.
    exclude-controls:
      - with-child-controls: yes
      with-id: at-4
  merge:
    as-is: yes
  modify:
    set-parameter:
      - id: ac-1_prm_3
      # Change the "at least annually" constraint to "at least every six months".
      constraint:
        description: "at least every six months"
    alter:
      - control-id: au-11
      remove:
        - by-id: au-11_fr
      add:
        - position: ending
        part:
          - id: au-11_fr
          - name: item
          title: Modified Requirement
          part:
            - id: au-11_fr_smt.1
            - name: item
            prop:
              - name: label
              "#text": "Requirement:"
            # Replace the "at least 90 days" statement for online retention of audit records with a more restrictive "at least 180 days" statement.
            p: "The service provider retains audit records on-line for at least 180 days and further preserves audit records off-line for a period that is in accordance with NARA requirements."
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<profile xmlns="http://csrc.nist.gov/ns/oscal/1.0" uuid="[UUID-value]">
    <metadata>
        <title>Modification to FedRAMP Moderate Baseline</title>
        <last-modified>2025-03-06T08:05:30.000Z</last-modified>
        <version>fedramp2.0.0-oscal1.0.4</version>
        <oscal-version>1.0.4</oscal-version>
    </metadata>
    <import href="https://path/to/FedRAMP_MODERATE-baseline_profile.xml">
        <!-- Include every control in the Moderate baseline. -->
        <include-all/>
        <!-- Remove the "AT-4" control.  -->
        <exclude-controls with-child-controls="yes">
            <with-id>at-4</with-id> 
        </exclude-controls>
    </import>
    <merge>
        <as-is>yes</as-is>
    </merge>
    <modify>
        <set-parameter id="ac-1_prm_3">
            <!-- Change the "at least annually" constraint to "at least every six months". -->
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
                    <title>Modified Requirement</title>
                    <part id="au-11_fr_smt.1" name="item">
                        <prop name="label">Requirement:</prop>
                        <!-- Replace the "at least 90 days" statement for online retention of audit records with a more restrictive "at least 180 days" statement. -->
                        <p>The service provider retains audit records on-line for at least 180 days and further preserves audit records off-line for a period that is in accordance with NARA requirements.</p>
                    </part>
                </part>
            </add>
        </alter>
    </modify>
</profile>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}
