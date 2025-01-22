---
title: Control Definitions
weight: 100
---

## Control Definitions

{{< figure src="/img/ssp-figure-31.png" title="SSP Template Security Control Definition" alt="Screenshot of an SSP template security control definition." >}}

All control definition information is imported from the appropriate
FedRAMP baseline (OSCAL profile).  This includes the original NIST control definition and parameter labels as well as any FedRAMP control guidance and parameter constraints.

Interpreting and presenting profile content is out of the scope of this
documentation. Please refer to the NIST OSCAL Profile and Catalog schema references for more information:

-   [Profile Model](https://pages.nist.gov/OSCAL/concepts/layer/control/profile/)

-   [Catalog Reference](https://pages.nist.gov/OSCAL/concepts/layer/control/catalog/)

Only the control implementation information is present within an
OSCAL-based SSP. Each control in the FedRAMP baseline must have a
corresponding `implemented-requirement` assembly in the
`control-implementation` assembly.

##### Representation
{{< highlight xml "linenos=table" >}}
    <!-- metadata -->
    <import-profile href="https://path/to/xml/FedRAMP_MODERATE-baseline_profile.xml"/>
    <!-- system-characteristics -->
    <!-- system-implementation -->
    <control-implementation>
        <description>
            <p>This field required by OSCAL, but may be left blank.</p>
            <p>FedRAMP requires no specific content here.</p>
        </description>
        
        <!-- one implemented-requirement assembly for each required control -->
        <implemented-requirement uuid="uuid-value" control-id="ac-1">
            <!-- Control content cut - See next pages for detail -->
        </implemented-requirement>
        <implemented-requirement uuid="uuid-value" control-id="ac-2">
        <!-- Control content cut - See next pages for detail -->
        </implemented-requirement>
        <implemented-requirement uuid="uuid-value" control-id="ac-2.1">
        <!-- Control content cut - See next pages for detail -->
        </implemented-requirement>
        
    </control-implementation>
    <!-- back-matter -->

{{</ highlight >}}

##### XPath Queries
{{< highlight xml "linenos=table" >}}
  URI to Profile:
    /*/import-profile/@href
  CSP's Control Implementation Information
    /*/control-implementation/implemented-requirement[@control-id="ac-1"]

{{</ highlight >}}

**NOTE:** FedRAMP tools check to ensure there is one
implemented-requirement assembly for each control identified in the
applicable FedRAMP baseline.

---
