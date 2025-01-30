---
title: FIPS-199 Categorization
weight: 337
---
## FIPS-199 Categorization

A FedRAMP SSP identifies the system categorization [per FIPS-199](https://doi.org/10.6028/NIST.FIPS.199) as illustrated below.

{{< figure src="/img/ssp-figure-9.png" title="FedRAMP SSP template system sensitivity level." alt="Screenshot of the FIPS 199 system sensitivity level in the FedRAMP SSP template." >}}

An OSCAL-based FedRAMP SSP can express a system categorization using FIPS-199 through the core OSCAL property named "security-sensitivity-level", as illustrated below. 

__Note that "security-sensitivity-level" is not defined as a "prop" element with an attribute of "name", but rather as its own element.__

#### OSCAL Representation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
 "system-security-plan" : {
   "uuid" : "12345678-1234-4321-8765-123456789012",
   "system-characteristics" : {
     "system-name-short" : "System's Short Name or Acronym",
     "system-ids" : [ {
       "id" : "F00000000",
       "identifier-type" : "http://fedramp.gov"
     } ],
     "security-sensitivity-level" : "fips-199-moderate",
     "system-name" : "System's Full Name"
   },
   "metadata" : { }
 }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
    <metadata>
        <!-- cut CSP Name -->
    </metadata>
    <system-characteristics>
        <!-- System Name & Abbreviation -->
        <system-name>System's Full Name</system-name>
        <system-name-short>System's Short Name or Acronym</system-name-short>        
        <!-- FedRAMP Unique Identifier -->
        <system-id identifier-type="http://fedramp.gov">F00000000</system-id>
        <!-- cut Service Model -->
        <!-- cut Deployment Model -->
        <!-- cut DIL Determination -->

        <!-- FIPS PUB 199 Level (SSP Attachment 10) -->
        <security-sensitivity-level>fips-199-moderate</security-sensitivity-level>              
         
        <!--  cut -->        
    </system-characteristics>
    <!--  cut -->     
</system-security-plan>

{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
 uuid: 12345678-1234-4321-8765-123456789012
 system-characteristics:
   system-name-short: System's Short Name or Acronym
   system-ids:
   - id: F00000000
     identifier-type: http://fedramp.gov
   security-sensitivity-level: fips-199-moderate
   system-name: System's Full Name
 metadata: {}

{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}


<br />
{{<callout>}}

**OSCAL Allowed Values**

Valid values for security-sensitivity-level:
- fips-199-low
- fips-199-moderate
- fips-199-high

{{</callout>}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    System Sensitivity Level:
        /*/system-characteristics/security-sensitivity-level
{{</ highlight >}}

**NOTES:**

-   The identified System Sensitivity Level governs which FedRAMP baseline applies. See the [*Importing the FedRAMP Baseline*](/documentation/ssp/3-working-with-oscal-files/#importing-the-fedramp-baseline) section for more information about importing the appropriate FedRAMP baseline.


