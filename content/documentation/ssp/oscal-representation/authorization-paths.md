---
title: Authorization Types
weight: 109
---
# Authorization Types

Historically, FedRAMP has supported three authorization paths for cloud service offerings:

1. [Agency Authorizations](https://www.fedramp.gov/agency-authorization/) - The cloud service provider works directly with a federal agency, pursuing an Authority to Operate (ATO) from the agency.
2. [Low Impact Software as a Service (LI-SaaS) Authorizations](https://tailored.fedramp.gov/static/FedRAMP%20Tailored%20LI-SaaS%20Requirements.docx) - The cloud service provider works directly with a federal agency through a more efficient ATO process tailored for low-risk use cases. 
3. [Joint Authorization Board (JAB) Authorizations](https://www.fedramp.gov/updates/jab/) - cloud service providers worked with the JAB to receive provisional ATO.  The JAB consisted of the Chief Information Officers of the Department of Defense (DOD), the Department of Homeland Security (DHS), and the General Services Administration (GSA), along with their technical representatives. **The JAB is no longer monitoring cloud services as a unified entity or authorizing new cloud services.**

A FedRAMP SSP must indicate the authorization type with the "authorization-type" extension `prop` as illustrated in the example below.

### Representation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan" : {
    "uuid" : "11111111-2222-4000-8000-000000000000",
    "system-characteristics" : {
      "system-ids" : [ {
        "identifier-type" : "http://fedramp.gov/ns/oscal",
        "id" : "F00000000"
      } ],
      "system-name" : "System's Full Name",
      "system-name-short" : "System's Short Name or Acronym",
      "security-sensitivity-level" : "fips-199-moderate",
      "security-impact-level" : {
        "security-objective-integrity" : "fips-199-moderate",
        "security-objective-availability" : "fips-199-moderate",
        "security-objective-confidentiality" : "fips-199-moderate"
      },
      "props" : [ {
        "name" : "cloud-service-model",
        "value" : "saas",
        "remarks" : "Remarks are required if service model is \"other\". Optional otherwise."
      }, {
        "ns" : "http://fedramp.gov/ns/oscal",
        "name" : "authorization-type",
        "value" : "fedramp-agency"
      } ]
    },
    "import-profile" : {
      "href" : "https://raw.githubusercontent.com/GSA/fedramp-automation/refs/heads/develop/dist/content/rev5/baselines/xml/FedRAMP_rev5_MODERATE-baseline_profile.xml",
      "remarks" : "This example points to the FedRAMP Rev 5 Moderate baseline that is part of the official FedRAMP 3.0.0 release.\n\nMust adjust accordingly for applicable baseline and revision."
    }
  }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan uuid="11111111-2222-4000-8000-000000000000">

    <import-profile href="https://raw.githubusercontent.com/GSA/fedramp-automation/refs/heads/develop/dist/content/rev5/baselines/xml/FedRAMP_rev5_MODERATE-baseline_profile.xml">
        <remarks>
            <p>This example points to the FedRAMP Rev 5 Moderate baseline that is part of the official FedRAMP 3.0.0 release.\n\nMust adjust accordingly for applicable baseline and revision.</p>
        </remarks>
    </import-profile>

    <system-characteristics>
        <system-id identifier-type="http://fedramp.gov/ns/oscal">F00000000</system-id>
        <system-name>System's Full Name</system-name>
        <system-name-short>System's Short Name or Acronym</system-name-short>

        <prop name="cloud-service-model" value="saas">
            <remarks>
                <p>Remarks are required if service model is "other". Optional otherwise.</p>
            </remarks>
        </prop>
        <prop ns="http://fedramp.gov/ns/oscal" name="authorization-type" value="fedramp-agency"/>

        <security-sensitivity-level>fips-199-moderate</security-sensitivity-level>
        
        <security-impact-level>
            <security-objective-confidentiality>fips-199-moderate</security-objective-confidentiality>
            <security-objective-integrity>fips-199-moderate</security-objective-integrity>
            <security-objective-availability>fips-199-moderate</security-objective-availability>
        </security-impact-level>

    </system-characteristics>

</system-security-plan>
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  uuid: 11111111-2222-4000-8000-000000000000
  system-characteristics:
    system-ids:
    - identifier-type: http://fedramp.gov/ns/oscal
      id: F00000000
    system-name: System's Full Name
    system-name-short: System's Short Name or Acronym
    security-sensitivity-level: fips-199-moderate
    security-impact-level:
      security-objective-integrity: fips-199-moderate
      security-objective-availability: fips-199-moderate
      security-objective-confidentiality: fips-199-moderate
    props:
    - name: cloud-service-model
      value: saas
      remarks: Remarks are required if service model is "other". Optional otherwise.
    - ns: http://fedramp.gov/ns/oscal
      name: authorization-type
      value: fedramp-agency
  import-profile:
    remarks: |-
      This example points to the FedRAMP Rev 5 Moderate baseline that is part of the official FedRAMP 3.0.0 release.

      Must adjust accordingly for applicable baseline and revision.
    href: https://raw.githubusercontent.com/GSA/fedramp-automation/refs/heads/develop/dist/content/rev5/baselines/xml/FedRAMP_rev5_MODERATE-baseline_profile.xml
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}

### XPath Queries

{{< highlight xml "linenos=table" >}}
FedRAMP Baseline URL:
    /*/import-profile/@href
Cloud Service Model:
    /*/system-characteristics/prop[@name="cloud-service-model"]/@value
FedRAMP Authorization Type:
    /*/system-characteristics/prop[@name="authorization-type"][@ns="http://fedramp.gov/ns/oscal"]/@value
Security Sensitivity Level:
    /*/system-characteristics/security-sensitivity-level
Security Impact Levels (Confidentiality, Integrity, and Availability):
    /*/system-characteristics/security-impact-level/security-objective-confidentiality
    /*/system-characteristics/security-impact-level/security-objective-integrity
    /*/system-characteristics/security-impact-level/security-objective-availability
{{</ highlight >}}

{{< callout>}}
**NOTE**

**LI-SaaS Authorizations**
- The SSP must import the LI-SaaS baseline (profile or resolved profile catalog)
- The SSP must have the cloud service model set to “saas”.  This is the "cloud-service-model" core OSCAL `prop` within the `system-characteristics` assembly.
- The SSP must have the "authorization-type" FedRAMP extension `prop` set accordingly within the `system-characteristics` assembly:
  - Must be set to "fedramp-li-saas".  
- The SSP must have the security sensitivity level set to “fips-199-low”
- The SSP must have all the security impact levels set to “fips-199-low”

---

**JAB Authorizations**
- "authorization-type" of "fedramp-jab" is deprecated.

{{</ callout >}}


Review the [Authorizing Officials](./owner-and-responsibility.md/#authorizing-official) documentation for details regarding how to specify the authorizing official, in a FedRAMP OSCAL SSP, using `role`, `party`, and `responsible-party` assemblies.