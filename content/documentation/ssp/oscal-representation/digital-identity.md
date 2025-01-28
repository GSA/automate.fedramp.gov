---
title: Digital Identity Worksheet
weight: 336
---

## Digital Identity Level (DIL) Determination

The Digital Identity Level, as defined in [NIST SP 800-63](https://doi.org/10.6028/NIST.SP.800-63-3), is identified in the FedRAMP SSP template document as illustrated in the figure below with values of "Low", "Moderate", and "High".

{{< figure src="/img/ssp-figure-8.png" title="FedRAMP SSP template DIL determination." alt="Screenshot of the DIL determination in the FedRAMP SSP template." >}}

The digital identity level can be expressed through the OSCAL properties of "identity-assurance-level", "authenticator-assurance-level", and "federation-assurance-level", as represented below.

#### OSCAL Representation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan" : {
    "system-characteristics" : {
      "system-ids" : [ {
        "identifier-type" : "http://fedramp.gov",
        "id" : "F00000000"
      } ],
      "system-name" : "System's Full Name",
      "props" : [ {
        "name" : "identity-assurance-level",
        "value" : "1"
      }, {
        "name" : "authenticator-assurance-level",
        "value" : "1"
      }, {
        "name" : "federation-assurance-level",
        "value" : "1"
      } ],
      "system-name-short" : "System's Short Name or Acronym"
    },
    "metadata" : { },
    "uuid" : "12345678-1234-4321-8765-123456789012"
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

        <!-- DIL Determination -->
        <prop name="identity-assurance-level" value="1"/>
        <prop name="authenticator-assurance-level" value="1"/>
        <prop name="federation-assurance-level" value="1"/>  
              
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
  metadata: {}
  system-characteristics:
    props:
    - value: "1"
      name: identity-assurance-level
    - value: "1"
      name: authenticator-assurance-level
    - value: "1"
      name: federation-assurance-level
    system-name: System's Full Name
    system-ids:
    - id: F00000000
      identifier-type: http://fedramp.gov
    system-name-short: System's Short Name or Acronym
  uuid: 12345678-1234-4321-8765-123456789012
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}

<br />
{{<callout>}}

**OSCAL Allowed Values**

Valid IAL, AAL, and FAL values (as defined by [NIST SP 800-63](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-3.pdf)):
- 1 (low)
- 2 (moderate)
- 3 (high)

{{</callout>}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Identity Assurance Level: 
        /*/system-characteristics/prop[@name="identity-assurance-level"]/@value
    Authenticator Assurance Level: 
        /*/system-characteristics/prop[@name="authenticator-assurance-level"]/@value
    Federation Assurance Level: 
        /*/system-characteristics/prop[@name="federation-assurance-level"]/@value
{{</ highlight >}}

