---
title: Digital Identity Worksheet
weight: 336
---

## Digital Identity Level (DIL) Determination

The Digital Identity Level, as defined in [NIST SP 800-63](https://doi.org/10.6028/NIST.SP.800-63-3), is identified in the FedRAMP SSP template document as illustrated in the figure below with values of "Low", "Moderate", and "High".

{{< figure src="/img/ssp-figure-8.png" title="FedRAMP SSP template DIL determination." alt="Screenshot of the DIL determination in the FedRAMP SSP template." >}}

The Digital Identity Level can be expressed through the OSCAL properties named "identity-assurance-level", "authenticator-assurance-level", and "federation-assurance-level", as represented below.

#### OSCAL Representation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan" : {
    "system-characteristics" : {
      "system-ids" : [ {
        "identifier-type" : "http://fedramp.gov/ns/oscal",
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

    <system-characteristics>
        <system-id identifier-type="http://fedramp.gov/ns/oscal">F00000000</system-id>
        <system-name>System's Full Name</system-name>
        <system-name-short>System's Short Name or Acronym</system-name-short>
        <description>
        <p>[Insert CSO Name] is delivered as [a/an] [insert based on the Service Model above] offering
            using a multi-tenant [insert based on the Deployment Model above] cloud computing
            environment. It is available to [Insert scope of customers in accordance with instructions
            above (for example, the public, federal, state, local, and tribal governments, as well as
            research institutions, federal contractors, government contractors etc.)].</p>
        <p>NOTE: Additional description, including the purpose and functions of this system may be
            added here. This includes any narrative text usually included in section 9.1 of the SSP.</p>
        <p>NOTE: The description is expected to be at least 32 words in length.</p>
        </description>
        <prop name="cloud-service-model" value="saas">
            <remarks>
                <p>Remarks are required if service model is "other". Optional otherwise.</p>
            </remarks>
        </prop>
        <prop name="cloud-deployment-model" value="government-only-cloud">
            <remarks>
                <p>Remarks are required if deployment model is "hybrid-cloud" or "other". Optional
                otherwise.</p>
            </remarks>
        </prop>
        <prop name="identity-assurance-level" value="2"/>
        <prop name="authenticator-assurance-level" value="2"/>
        <prop name="federation-assurance-level" value="2"/>

    </system-characteristics>

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
      identifier-type: http://fedramp.gov/ns/oscal
    system-name-short: System's Short Name or Acronym
  uuid: 12345678-1234-4321-8765-123456789012
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}

<br />
{{<callout>}}

**OSCAL Allowed Values**

Valid IAL, AAL, and FAL values (as defined by [NIST SP 800-63](https://doi.org/10.6028/NIST.SP.800-63-3)):
- 1 (Low)
- 2 (Moderate)
- 3 (High)

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

