---
title: Digital Identity Worksheet
weight: 336
---

## Digital Identity Level (DIL) Determination

The digital identity level, as defined in [NIST SP 800-63](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-3.pdf), is identified in the FedRAMP SSP template document as illustrated in the figure below with values of "low", "moderate", and "high".

{{< figure src="/img/ssp-figure-8.png" title="FedRAMP SSP template DIL determination." alt="Screenshot of the DIL determination in the FedRAMP SSP template." >}}

The digital identity level can be expressed through the OSCAL properties of "identity-assurance-level", "authenticator-assurance-level", and "federation-assurance-level", as represented below.

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=14-17" >}}
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
{{</ highlight >}}

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

