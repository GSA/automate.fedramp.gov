---
title: Contents
weight: 103
---
# FedRAMP SSP Contents

For SSP-specific content, each main section of the SSP is represented in this section, along with OSCAL code snippets for representing the information in OSCAL syntax. There is also XPath syntax for querying the code in an OSCAL-based FedRAMP SSP represented in XML format.

Content that is common across OSCAL file types is described in the *[FedRAMP OSCAL Documentation](/documentation).* This includes the following:

- [**Title Page**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#title-page)
- [**Prepared By/For**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#prepared-by-third-party)
- [**Record of Template Changes**](/documentation/general-concepts/oscal-file-concepts/#oscal-syntax-versions)
- [**Revision History**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#document-revision-history)
- [**How to Contact Us**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#how-to-contact-us)
- [**Document Approvers**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#document-approvals)
- [**Acronyms and Glossary**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#fedramp-standard-attachments-acronyms-lawsregulations)
- [**Laws, Regulations, Standards and Guidance**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#additional-laws-regulations-standards-or-guidance)
- [**Attachments and Citations**](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#attachments-and-embedded-content)

It is not necessary to represent the following sections of the SSP template in OSCAL; however, tools should present users with this content where it is appropriate:

-   Any blue-text instructions found in the SSP template where the instructions are related to the content itself

-   Table of contents

-   Introductory and instructive content in section 1, such as references to NIST SP 800-60, Guide to Mapping Types and the definitions from FIPS Pub 199

-   The control origination definitions are in appendix A of the SSP template; however, please note that hybrid and shared are represented in OSCAL by specifying more than one control origination.

The OSCAL syntax in this documentation may be used to represent the High, Moderate, Low and LI-SaaS FedRAMP SSP Templates. Simply ensure the correct FedRAMP baseline is referenced using the `import-profile` statement.

**NOTE: The FedRAMP SSP template screenshots in the sections that follow vary slightly from the most current version of the FedRAMP rev 5 SSP template.**


---
## System Information

### Cloud Service Provider (CSP) Name

The cloud service provider (CSP) must be provided as one of the party assemblies within the metadata.

{{< figure src="/img/ssp-figure-4.png" title="FedRAMP SSP template CSP Name" alt="Screenshot of the CSP name in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=5" >}}
<system-security-plan>
    <metadata>
        <!-- CSP Name -->
        <party uuid=”uuid-of-csp” type=”organization”>
            <name>Cloud Service Provider (CSP) Name</name>
        </party>
    </metadata>
</system-security-plan>
{{</ highlight >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
Cloud Service Provider (CSP) Name:
    /*/metadata/party[@uuid='uuid-of-csp']/name
{{</ highlight >}}

---
### System Name, Abbreviation, and FedRAMP Unique Identifier

The remainder of the system information is provided in the
system-characteristics assembly.

The FedRAMP-assigned application number is the unique ID for a FedRAMP system. OSCAL supports several system identifiers, which may be assigned by different organizations.

For this reason, OSCAL requires the identifier-type flag be present and have a value that uniquely identifies the issuing organization. FedRAMP requires its value to be "https://fedramp.gov" for all FedRAMP-issued application numbers.

{{< figure src="/img/ssp-figure-5.png" title="FedRAMP SSP template System Name and Package ID" alt="Screenshot of the system name, and package ID in the FedRAMP SSP template." >}}

This assembly defines the full name of the system and its short name. A FedRAMP OSCAL SSP must define the system name and its short name.

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=9-13" >}}
<system-security-plan>
    <metadata>
        <!-- CSP Name -->
        <party uuid="uuid-of-csp" type="organization">
            <name>Cloud Service Provider (CSP) Name</name>
        </party>
    </metadata>
    <system-characteristics>
        <!-- System Name & Abbreviation -->
        <system-name>System's Full Name</system-name>
        <system-name-short>System's Short Name or Acronym</system-name-short>        
        <!-- FedRAMP Unique Identifier -->
        <system-id identifier-type="http://fedramp.gov">F00000000</system-id>        
        <!--  cut -->        
    </system-characteristics>
    <!--  cut -->
</system-security-plan>
{{</ highlight >}}

<br />
{{<callout>}}

**FedRAMP Allowed Value** 

Required Identifier Type:
- identifier-type="https://fedramp.gov"

{{</callout>}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Information System Name:
        /*/system-characteristics/system-name
    Information System Abbreviation:
        /*/system-characteristics/system-name-short
    FedRAMP Unique Identifier:
        /*/system-characteristics/system-id[@identifier-type="https://fedramp.gov"]
{{</ highlight >}}

---
### Service Model

The core-OSCAL system-characteristics assembly has a property for the cloud service model.

{{< figure src="/img/ssp-figure-6.png" title="FedRAMP SSP template cloud service model" alt="Screenshot of the cloud service model in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=14-19" >}}
<system-security-plan>
    <metadata>
        <!-- CSP Name -->
        <party uuid="uuid-of-csp" type="organization">
            <name>Cloud Service Provider (CSP) Name</name>
        </party>
    </metadata>
    <system-characteristics>
        <!-- System Name & Abbreviation -->
        <system-name>System's Full Name</system-name>
        <system-name-short>System's Short Name or Acronym</system-name-short>        
        <!-- FedRAMP Unique Identifier -->
        <system-id identifier-type="http://fedramp.gov">F00000000</system-id>
        <!-- Service Model -->
        <prop name="cloud-service-model" value="saas">
            <remarks>
                <p>Remarks are required if service model is "other". Optional otherwise.</p>
            </remarks>
        </prop>

        <!--  cut -->        
    </system-characteristics>
    <!--  cut -->     
</system-security-plan>
{{</ highlight >}}

<br />
{{<callout>}}

**OSCAL Allowed Values** 

Valid Service Model values:
- saas
- paas
- iaas
- other

{{</callout>}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Service Model:
        /*/system-characteristics/prop[@name="cloud-service-model"]/@value
    Remarks on System's Service Model:
        /*/system-characteristics/prop[@name="cloud-service-model"]/remarks/node()
{{</ highlight >}}

**NOTE:**

-   A cloud service provider may define two or more cloud service models for the cloud service offering defined in the system security plan if applicable for customer use (IaaS and PaaS; IaaS and PaaS and SaaS; PaaS and SaaS). Cloud service providers may use a "cloud-service-model" prop for each applicable cloud service model.
-   If the service model is "other", the remarks field is required. Otherwise, it is optional.

---
### Deployment Model

The core-OSCAL system-characteristics assembly has a property for the cloud deployment model.

{{< figure src="/img/ssp-figure-7.png" title="FedRAMP SSP template cloud deployment model" alt="Screenshot of the cloud deployment model in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=20-25" >}}
<system-security-plan>
    <metadata>
        <!-- CSP Name -->
        <party uuid="uuid-of-csp" type="organization">
            <name>Cloud Service Provider (CSP) Name</name>
        </party>
    </metadata>
    <system-characteristics>
        <!-- System Name & Abbreviation -->
        <system-name>System's Full Name</system-name>
        <system-name-short>System's Short Name or Acronym</system-name-short>        
        <!-- FedRAMP Unique Identifier -->
        <system-id identifier-type="http://fedramp.gov">F00000000</system-id>
        <!-- Service Model -->
        <prop name="cloud-service-model" value="saas">
            <remarks>
                <p>Remarks are required if service model is "other". Optional otherwise.</p>
            </remarks>
        </prop>
        <!-- Deployment Model -->
        <prop name="cloud-deployment-model" value="public-cloud">
            <remarks>
                <p>Remarks are required if deployment model is "hybrid". Optional otherwise.</p>
            </remarks>
        </prop>      
        <!--  cut -->        
    </system-characteristics>
    <!--  cut -->     
</system-security-plan>
{{</ highlight >}}

<br />
{{<callout>}}

**FedRAMP Accepted Values**
- name="cloud-deployment-model"

    Valid: public-cloud, private-cloud, government-only-cloud, hybrid-cloud, other

{{</callout>}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Deployment Model:
        /*/system-characteristics/prop[@name="cloud-deployment-model"]/@value
    Remarks on System's Deployment Model:
        /*/system-characteristics/prop[@name="cloud-deployment-model"]/remarks/node()
{{</ highlight >}}

**NOTE:**

-   A cloud service provider may define one and only one cloud deployment model in the system security plan for a cloud service offering.

-   OSCAL 1.0.0 permits a cloud-deployment-model of value community-cloud, but FedRAMP does not permit such a deployment model for cloud service offerings and is not permitted for a FedRAMP OSCAL-based system security plan.
-   If the deployment model is \"hybrid\", the remarks field is required. Otherwise, it is optional.

---
### Digital Identity Level (DIL) Determination

The digital identity level identified in the FedRAMP SSP template document, illustrated in the figure below, isexpressed through the following core OSCAL properties.

{{< figure src="/img/ssp-figure-8.png" title="FedRAMP SSP template DIL determination." alt="Screenshot of the DIL determination in the FedRAMP SSP template." >}}

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

Valid IAL, AAL, and FAL values (as defined by NIST SP 800-63):
- 1
- 2
- 3

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

---
### System Sensitivity Level 

The system sensitivity level in the FedRAMP SSP template document, illustrated in the figure below, is expressed through the `security-sensitivity-level` assembly.  It is the designated overall information system [FIPS-199](https://doi.org/10.6028/NIST.FIPS.199) categorization based on the system information types, and the corresponding system security impact levels.

{{< figure src="/img/ssp-figure-9.png" title="FedRAMP SSP template system sensitivity level." alt="Screenshot of the FIPS 199 system sensitivity level in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=15-16" >}}
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

        <!-- cut system-information -->
        <!-- cut security-impact-level -->             
         
        <!--  cut -->        
    </system-characteristics>
    <!--  cut -->     
</system-security-plan>
{{</ highlight >}}

<br />
{{<callout>}}

**OSCAL Allowed Values**

Valid values for `security-sensitivity-level`:
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

-   The System Sensitivity Level is generally set based on the [impact levels of the information types](#security-impact-level) and the [impact levels of the security objectives](#security-impact-level). 
-   The identified System Sensitivity Level governs which FedRAMP baseline applies. See the [*Importing the FedRAMP Baseline*](/documentation/ssp/3-working-with-oscal-files/#importing-the-fedramp-baseline) section for more information about importing the appropriate FedRAMP baseline.

---

### System Information and Information Types

The `system-information` assembly and its defined `information-type` assemblies are used to document all of the information types that are either stored, processed, or transmitted by the system.  The information must be based on a formal standard, such as [NIST SP 800-60](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-60v2r1.pdf). 

The `categorization` assembly captures the set of defined information types (e.g., from [NIST SP 800-60](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-60v2r1.pdf)) that apply, using the appropriate `information-type-id` as unique identifier(s).  The referenced standard that defines the information types must be specified using the `system` attribute of the `information-type` assembly. 

Each information type has confidentiality, integrity, and availability security impact prescribed by the referenced information type standard.  This is documented by setting a FIPS-199 level in the `base`field.  However, this may be adjusted by specifying a different FIPS-199 level in the `selected` field.  The `adjustment-justification` field must be used for justification any time the `selected` FIPS-199 level is not the same as the `base`.

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=18-50" >}}
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

        <!-- system-information -->
        <system-information>
            <information-type uuid="06ecba4f-db96-4491-a3a2-7febfa227435">
                <title>Information Type Name</title>
                <description>
                    <p>A description of the information.</p>
                </description>
                <categorization system="https://doi.org/10.6028/NIST.SP.800-60v2r1">
                    <information-type-id>C.2.4.1</information-type-id>
                </categorization>
                <confidentiality-impact>
                    <base>fips-199-moderate</base>
                    <selected>fips-199-moderate</selected>
                    <adjustment-justification>
                        <p>Required if the base and selected values do not match.</p>
                    </adjustment-justification>
                </confidentiality-impact>
                <integrity-impact>
                    <base>fips-199-moderate</base>
                    <selected>fips-199-moderate</selected>
                    <adjustment-justification>
                        <p>Required if the base and selected values do not match.</p>
                    </adjustment-justification>
                </integrity-impact>
                <availability-impact>
                    <base>fips-199-moderate</base>
                    <selected>fips-199-moderate</selected>
                    <adjustment-justification>
                        <p>Required if the base and selected values do not match.</p>
                    </adjustment-justification>
                </availability-impact>
            </information-type>
        </system-information>

        <!-- cut security-impact-level -->        
         
        <!--  cut -->        
    </system-characteristics>
    <!--  cut -->     
</system-security-plan>
{{</ highlight >}}

<br />
{{<callout>}}

**OSCAL Allowed Values**

Valid values for `confidentiality-impact`, `integrity-impact`, and `availability-impact` (`base` and `selected` fields):
- fips-199-low
- fips-199-moderate
- fips-199-high

{{</callout>}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    System Information:
        /*/system-characteristics/system-information
    System Information Types:
        /*/system-characteristics/system-information/information-type
    Information Categorization:
        /*/system-characteristics/system-information/information-type/categorization
    Information Categorization System (URI reference to standard used to categorize information types):
        /*/system-characteristics/system-information/information-type/categorization/@system 
    System Information Type Unique IDs:
        /*/system-characteristics/system-information/information-type/categorization/information-type-id
    Confidentiality Impact (base):
        /*/system-characteristics/system-information/information-type/confidentiality-impact/base
    Confidentiality Impact (selected):
        /*/system-characteristics/system-information/information-type/confidentiality-impact/selected
    Confidentiality Impact (adjustment justification):
        /*/system-characteristics/system-information/information-type/confidentiality-impact/adjustment-justification
    Integrity Impact (base):
        /*/system-characteristics/system-information/information-type/integrity-impact/base
    Integrity Impact (selected):
        /*/system-characteristics/system-information/information-type/integrity-impact/selected
    Integrity Impact (adjustment justification):
        /*/system-characteristics/system-information/information-type/integrity-impact/adjustment-justification
    Availability Impact (base):
        /*/system-characteristics/system-information/information-type/availability-impact/base
    Availability Impact (selected):
        /*/system-characteristics/system-information/information-type/availability-impact/selected
    Availability Impact (adjustment justification):
        /*/system-characteristics/system-information/information-type/availability-impact/adjustment-justification
{{</ highlight >}}

---

### Security Impact Level

The security impact level describes the expected impact resulting from unauthorized disclosure, modification, or loss of access to information.  It is documented in the `system-impact-level` assembly derived from the confidentiality, integrity, and availability security objectives for the system, which considers the sensitivity of information within the system.  

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=52-57" >}}
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

        <!-- system-information -->
        <system-information>
            <information-type uuid="06ecba4f-db96-4491-a3a2-7febfa227435">
                <title>Information Type Name</title>
                <description>
                    <p>A description of the information.</p>
                </description>
                <categorization system="https://doi.org/10.6028/NIST.SP.800-60v2r1">
                    <information-type-id>C.2.4.1</information-type-id>
                </categorization>
                <confidentiality-impact>
                    <base>fips-199-moderate</base>
                    <selected>fips-199-moderate</selected>
                    <adjustment-justification>
                        <p>Required if the base and selected values do not match.</p>
                    </adjustment-justification>
                </confidentiality-impact>
                <integrity-impact>
                    <base>fips-199-moderate</base>
                    <selected>fips-199-moderate</selected>
                    <adjustment-justification>
                        <p>Required if the base and selected values do not match.</p>
                    </adjustment-justification>
                </integrity-impact>
                <availability-impact>
                    <base>fips-199-moderate</base>
                    <selected>fips-199-moderate</selected>
                    <adjustment-justification>
                        <p>Required if the base and selected values do not match.</p>
                    </adjustment-justification>
                </availability-impact>
            </information-type>
        </system-information>

        <!-- Security Impact Level -->
        <security-impact-level>
            <security-objective-confidentiality>fips-199-moderate</security-objective-confidentiality>
            <security-objective-integrity>fips-199-moderate</security-objective-integrity>
            <security-objective-availability>fips-199-moderate</security-objective-availability>
        </security-impact-level>              
         
        <!--  cut -->        
    </system-characteristics>
    <!--  cut -->     
</system-security-plan>
{{</ highlight >}}

<br />
{{<callout>}}

**OSCAL Allowed Values**

Valid values for `security-objective-confidentiality`, `security-objective-integrity`, and `security-objective-availability`:
- fips-199-low
- fips-199-moderate
- fips-199-high

{{</callout>}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Confidentiality Security Objective:
        /*/system-characteristics/security-impact-level/security-objective-confidentiality
    Integrity Security Objective:
        /*/system-characteristics/security-impact-level/security-objective-integrity
    Availability Security Objective:
        /*/system-characteristics/security-impact-level/security-objective-availability
{{</ highlight >}}

---

### System Status

The system status in the FedRAMP SSP template document is specified in the "Fully Operational as of" table cell illustrated in the figure below.  OSCAL has a `status` assembly that is used to describe the operational status of the system.  In addition, FedRAMP has defined an extension that must be used to provide the date when the system became operational.

{{< figure src="/img/ssp-figure-10.png" title="FedRAMP SSP template system status." alt="Screenshot of the system status information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=18-24" >}}
<system-security-plan>
    <metadata>
        <!-- cut CSP Name -->
    </metadata>
    <system-characteristics>
        <!-- System Name & Abbreviation -->
        <system-name>System's Full Name</system-name>
        <system-name-short>System's Short Name or Acronym</system-name-short>        
        <!-- FedRAMP Unique Identifier -->
        <system-id identifier-type=“http://fedramp.gov/ns/oscal”>F00000000</system-id>
        <!-- cut Service Model -->
        <!-- cut Deployment Model -->
        <!-- cut DIL Determination -->

        <!-- FIPS PUB 199 Level (SSP Attachment 10) -->
        <security-sensitivity-level>fips-199-moderate</security-sensitivity-level>                   
        <!-- Fully Operational as of -->
        <status state="operational">
            <remarks>
                <p>If the status is “other”, the remarks field is required.</p>
                <p>Otherwise, it is optional.</p>
            </remarks>
        </status>
        <prop ns="https://fedramp.gov/ns/oscal" name="fully-operational-date" value="mm/dd/yyyy"/>        
        <!--  cut -->        
    </system-characteristics>
    <!--  cut -->     
</system-security-plan>
{{</ highlight >}}

<br />
{{<callout>}}

**OSCAL Allowed Values**

FedRAMP only accepts those in bold:
- **operational**
- under-development
- **under-major-modification**
- disposition
- **other**

{{</callout>}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    System's Operational Status:
        /*/system-characteristics/status/@state
    Remarks on System's Operational Status:
        /*/system-characteristics/status/remarks/node()
    Fully Operational As Of Date:
        /*/system-characteristics/prop[@name="fully-operational-date"][@ns="https://fedramp.gov/ns/oscal"]/@value
{{</ highlight >}}

**NOTE:**

-   If the status is "other", the remarks field is required. Otherwise, it is optional.

-   While under-development and disposition are valid OSCAL values, systems with either of these operational status values are not eligible for a FedRAMP Authorization.

---
### System Functionality

The system functionality in the FedRAMP SSP template document is specified in the “General System Description” table cell illustrated in the figure below. OSCAL has a `description` field within the `system-characteristics` assembly that is used to describe the system and its functionality.

{{< figure src="/img/ssp-figure-11.png" title="FedRAMP SSP template general system description." alt="Screenshot of the general system description information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table, hl_lines=19-24" >}}
<system-security-plan>
    <metadata>
        <!-- cut CSP Name -->
    </metadata>
    <system-characteristics>
        <!-- System Name & Abbreviation -->
        <system-name>System's Full Name</system-name>
        <system-name-short>System's Short Name or Acronym</system-name-short>        
        <!-- FedRAMP Unique Identifier -->
        <system-id identifier-type=“http://fedramp.gov/ns/oscal”>F00000000</system-id>
        <!-- cut Service Model -->
        <!-- cut Deployment Model -->
        <!-- cut DIL Determination -->

        <!-- FIPS PUB 199 Level (SSP Attachment 10) -->
        <security-sensitivity-level>fips-199-moderate</security-sensitivity-level>                   
        <!-- cut Fully Operational as of -->

        <!-- system functionality -->
        <description>
            <p>Describe the purpose and functions of this system here.</p>
            <!-- list of services/features in scope -->
            <!-– (use paragraph, list item, or table) -->          
        </description>

    </system-characteristics>
    <!--  cut -->     
</system-security-plan>
{{</ highlight >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    System Function or Purpose: First paragraph in description
        /*/system-characteristics/description/node()

{{</ highlight >}}

---
## Information System Owner

A role with an ID value of \"system-owner\" is required. Use the responsible-party assembly to associate this role with the party assembly containing the System Owner's information.

{{< figure src="/img/ssp-figure-12.png" title="FedRAMP SSP template information system owner." alt="Screenshot of the system owner  information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- cut -->
    <role id="system-owner"><!-- cut --></role>
    <location uuid="uuid-of-hq-location">
        <title>CSP HQ</title>
        <address type="work">
            <addr-line>1234 Some Street</addr-line>
            <city>Haven</city>
            <state>ME</state>
            <postal-code>00000</postal-code>
        </address>
    </location>
    <party uuid="uuid-of-csp" type="organization">
        <name>Cloud Service Provider (CSP) Name</name>
    </party>
    <party uuid="uuid-of-person-1" type="person">
        <name>[SAMPLE]Person Name 1</name>
        <prop name="job-title" value="Individual's Title"/> 
            <prop name="mail-stop" value="A-1"/>
                <email-address>name@example.com</email-address>
                <telephone-number>202-000-0000</telephone-number>
                <location-uuid>uuid-of-hq-location</location-uuid>
                <member-of-organization>uuid-of-csp</member-of-organization>
    </party>
    <responsible-party role-id="system-owner">
        <party-uuid>uuid-of-person-1</party-uuid>
    </responsible-party>
</metadata>
{{</ highlight >}}

<br />
{{<callout>}}

**OSCAL Allowed Values**

Required role ID:
- system-owner

{{</callout>}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    System Owner's Name:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id="system-owner"]/party-uuid]]/name
    NOTE: Replace "name" with "email-address" or "telephone-number" above as needed.
    System Owner’s Address:
        /*/metadata/location[@uuid=/*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="system-owner"]/party-uuid]]/location-uuid]/address/addr-line
    NOTE: Replace "addr-line" with "city", "state", or "postal-code" above as needed.
    System Owner's Title:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id="system-owner"]/party-uuid]]/prop[@name='job-title']/@value
    Company/Organization:
        /*/metadata/party[@uuid=/*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id="system-owner"]/party-uuid]]/member-of-organization]/name
{{</ highlight >}}

**NOTE:**

If no country is provided, FedRAMP tools will assume a US address.

---
## Federal Authorizing Officials

A role with an ID value of "authorizing-official" is required. Use the responsible-party assembly to associate this role with the party assembly containing the Authorizing Official's information.

{{< figure src="/img/ssp-figure-13.png" title="FedRAMP SSP template federal authorizing officials." alt="Screenshot of the federal authorizing official information in the FedRAMP SSP template." >}}

##### Federal Agency Authorization Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <role id="authorizing-official">
        <title>Authorizing Official</title>
    </role>
    <party uuid="uuid-of-agency" type="organization">
        <name>Agency Name</name>
    </party>
    <party uuid="uuid-of-person-6" type="person">
        <name>[SAMPLE]Person Name 6</name>
        <prop name="job-title" value="Individual's Title"/>
            <email-address>name@example.com</email-address>
            <telephone-number>202-000-0000</telephone-number>
            <member-of-organization>uuid-of-agency</member-of-organization>
    </party>
    <responsible-party role-id="authorizing-official">
        <party-uuid>uuid-of-person-6</party-uuid>
    </responsible-party>
</metadata>
<!-- import -->
<system-characteristics>
    <!-- description -->
    <prop name="authorization-type" 
          ns="https://fedramp.gov/ns/oscal" 
          value="fedramp-agency" />
    <!-- prop -->
</system-characteristics>
{{</ highlight >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    FedRAMP Authorization Type:
        /*/system-characteristics/prop[@name="authorization-type"][@ns="https://fedramp.gov/ns/oscal"]/@value
    Authorizing Official’s Name:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="authorizing-official"]/party-uuid]]/name
    NOTE: Replace "name" with "email-address" or "telephone-number" above as needed.
    Authorizing Official’s Title:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="authorizing-official"]/party-uuid]]/prop[@name='job-title']
    Authorizing Official's Agency:
        /*/metadata/party[@uuid=/*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="authorizing-official"]/party-uuid]]/member-of-organization]/name
{{</ highlight >}}

**NOTE:**

If the authorization-type field is "fedramp-jab", the responsible-party/party-uuid field must be the uuid value for the FedRAMP JAB.

---
#### Federal JAB P-ATO Authorization Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- cut -->
    <role id="authorizing-official">
        <title>Authorizing Official</title>
        <desc>The government executive(s) who authorize this system.</desc>
    </role>
    <!-- cut -->
    <party uuid="uuid-of-fedramp-jab" type="organization">
        <name>FedRAMP: Joint Authorization Board</name>
        <short-name>FedRAMP JAB</short-name>
    </party>
    <!-- cut -->
    <responsible-party role-id="authorizing-official">
        <party-uuid>uuid-of-fedramp-jab</party-uuid>
    </responsible-party>
</metadata>
<!-- import -->
<system-characteristics>
    <!-- description -->
    <prop name="authorization-type" 
          ns="https://fedramp.gov/ns/oscal">fedramp-jab</prop>
    <!-- prop -->
</system-characteristics>
{{</ highlight >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Authorizing Official’s Name:
        //metadata/party[@uuid=[//metadata/responsible-party[@role-id="authorizing-official"]/party-uuid]]/name
{{</ highlight >}}

<br />
{{<callout>}}

**FedRAMP Extension:**

prop (ns="https://fedramp.gov/ns/oscal")
- name="authorization-type" 

**FedRAMP Allowed Values**
- fedramp-jab
- fedramp-agency
- fedramp-li-saas

**OSCAL Allowed Value**

Required Role ID:
- authorizing-official

{{</callout>}}


---
## Assignment of Security Responsibilities

A role with an ID value of "information-system-security-officer" is
required. Use the responsible-party assembly to associate this role with the party assembly containing the Information 
System Security Officer's information.

{{< figure src="/img/ssp-figure-14.png" title="FedRAMP SSP template security point of contact." alt="Screenshot of the security point of contact information (e.g., ISSO) in the FedRAMP SSP template." >}}

<br />
{{<callout>}}
**NOTES ON ADDRESSES**

**Preferred Approach:** When multiple parties share the same address, such as multiple staff members at a company HQ, define the location once as a location assembly, then use the location-uuid field within each party assembly to identify the location of that individual or team.

**Alternate Approach:** If the address is unique to this individual, it may be included in the party assembly itself. 

**Hybrid Approach:** It is possible to include both a location-uuid and an address assembly within a party assembly. This may be used where multiple staff are in the same building but have different office numbers or mail stops. Use the location-uuid to identify the shared building, and only include a single addr-line field within the party's address assembly.

A tool developer may elect to always create a location assembly, even when only used once; however, tools must recognize and handle all of the approaches above when processing OSCAL files.

{{</callout>}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- cut -->
    <role id="information-system-security-officer"><!-- cut -->
        <title>Information System Security Officer (or Equivalent)</title>
    </role>
    <location uuid="uuid-of-hq-location">
        <title>CSP HQ</title>
        <address type="work">
            <addr-line>1234 Some Street</addr-line>
            <city>Haven</city>
            <state>ME</state>
            <postal-code>00000</postal-code>
        </address>
    </location>
    <party uuid="uuid-of-csp" type="organization">
        <name>Cloud Service Provider (CSP) Name</name>
    </party>
    <party uuid="uuid-of-person-10" type="person">
        <name>[SAMPLE]Person Name 10</name>
        <prop name="job-title" value="Individual's Title"/>
        <email-address>name@org.domain</email-address>
        <telephone-number>202-000-0000</telephone-number>
        <location-uuid>uuid-of-hq-location</location-uuid>
        <member-of-organization>uuid-of-csp</member-of-organization>
    </party>
    <!-- repeat party assembly for each person -->
    <responsible-party role-id="system-poc-technical">
        <party-uuid>uuid-of-person-7</party-uuid>
    </responsible-party>
</metadata>
{{</ highlight >}}

<br />
{{<callout>}}

**OSCAL Allowed Value**

Required Role ID:
- information-system-security-officer

{{</callout>}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    ISSO POC Name:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id="information-system-security-officer"]/party-uuid]]/name
    NOTE: Replace "name" with "email-address" or "telephone-number" above as needed.
    ISSO POC’s Address:
        /*/metadata/location[@uuid=/*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="information-system-security-officer"]/party-uuid]]/location-uuid]/address/addr-line
    NOTE: Replace "addr-line" with "city", "state", or "postal-code" above as needed.
    ISSO POC's Title:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id="information-system-security-officer"]/party-uuid]]/prop[@name='job-title']
    Company/Organization:
        /*/metadata/party[@uuid=/*/metadata/party[@uuid=[/*/metadata/responsible-party[@role-id="information-system-security-officer"]/party-uuid]]/member-of-organization]/name
{{</ highlight >}}

---
## Leveraged FedRAMP-authorized Services

If this system is leveraging the authorization of one or more systems, such as a SaaS running on an IaaS, each leveraged system must be represented within the system-implementation assembly. There must be one leveraged-authorization assembly and one matching component assembly for each leveraged authorization.

The leveraged-authorization assembly includes the leveraged system's name, point of contact (POC), and authorization date. The component assembly must be linked to the leveraged-authorization assembly using a property (prop) field with the name leveraged-authorization-uuid and the
UUID value of its associated leveraged-authorization assembly. The component assembly enables controls to reference it with the by-component responses described in the [*Control Implementation Descriptions*](/documentation/ssp/6-security-controls/#control-implementation-descriptions) section. The implementation-point property value must be set to "external".

If the leveraged system owner provides a UUID for their system, such as in an OSCAL-based Inheritance and Responsibility document (similar to a CRM), it should be provided as the inherited-uuid property value.

{{< figure src="/img/ssp-figure-15.png" title="FedRAMP SSP template leveraged FedRAMP-authorized services." alt="Screenshot of the leveraged FedRAMP-authorized service information in the FedRAMP SSP template." >}}

<br />
{{<callout>}}

**IMPORTANT FOR LEVERAGED SYSTEMS:**

While a leveraged system has no need to represent content here, its SSP must include special inheritance and responsibility information in the individual controls. See the [*Response: Identifying Inheritable Controls and Customer Responsibilities*](/documentation/ssp/6-security-controls/#response-identifying-inheritable-controls-and-customer-responsibilities) section for more information.

{{</callout>}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- CSP name -->
    <party uuid="uuid-value">
        <name>Example IaaS Provider</name>
        <short-name>E.I.P.</short-name>
    </party>
</metadata>
<!-- cut import-profile, system-characteristics -->
<system-implementation>
    <leveraged-authorization uuid="uuid-value" >
        <title>Name of Underlying System</title>
        <!-- FedRAMP Package ID -->
        <prop name="leveraged-system-identifier" 
            ns="https://fedramp.gov/ns/oscal" 
            value="Package_ID value" />
        <prop ns="https://fedramp.gov/ns/oscal" name="authorization-type" 
              value="fedramp-agency"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="impact-level" value="moderate"/>
        <link href="//path/to/leveraged_system_legacy_crm.xslt" />
        <link href="//path/to/leveraged_system_responsibility_and_inheritance.xml" />
        <party-uuid>uuid-of-leveraged-system-poc</party-uuid>
        <date-authorized>2015-01-01</date-authorized>
    </leveraged-authorization>
    <!-- CSO name & service description -->
    <component uuid="uuid-of-leveraged-system" type="leveraged-system">
        <title>Name of Leveraged System</title>
        <description>
            <p>Briefly describe leveraged system.</p>
        </description>
        <prop name="leveraged-authorization-uuid" 
              value="5a9c98ab-8e5e-433d-a7bd-515c07cd1497" />
        <prop name="inherited-uuid" value="11111111-0000-4000-9001-000000000001" />
        <prop name="implementation-point" value="external"/>
        <!-- FedRAMP prop extensions for table 6.1 columns -->
        <status state="operational"/>
    </component>
</system-implementation>
{{</ highlight >}}

<br />
{{<callout>}}

The title field must match an existing [FedRAMP authorized Cloud_Service_Provider_Package](https://raw.githubusercontent.com/18F/fedramp-data/master/data/data.json) property value.

A leveraged-system-identifier property must be provided within each leveraged-authorization field.  The value of this property must be from the same Cloud Service Provider as identified in the title field.


{{</callout>}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Name of first leveraged system:
        /*/system-implementation/leveraged-authorization[1]/title
    Name of first leveraged system CSO service (component):
        (//*/component/prop[@name="leveraged-authorization-uuid" and @value="uuid-of-leveraged-system"]/parent::component/title)[1]
    Description of first leveraged system CSO service (component):
        (//*/component/prop[@name="leveraged-authorization-uuid" and @value="uuid-of-leveraged-system"]/parent::component/description)[1]
    Authorization type of first leveraged system:
        /system-security-plan/system-implementation[1]/leveraged-authorization[1]/prop[@ns="https://fedramp.gov/ns/oscal" and @name="authorization-type"]/@value
    FedRAMP package ID# of the first leveraged system:
        /system-security-plan/system-implementation[1]/leveraged-authorization[1]/prop[@ns="https://fedramp.gov/ns/oscal" and @name="leveraged-system-identifier"]/@value
    Nature of Agreement for first leveraged system:
        (//*/component/prop[@name="leveraged-authorization-uuid" and @value="uuid-of-leveraged-system"]/parent::component/prop[@ns="https://fedramp.gov/ns/oscal" and @name="nature-of-agreement"]/@value)[1]
    FedRAMP impact level of the first leveraged system:
        /system-security-plan/system-implementation[1]/leveraged-authorization[1]/prop[@ns="https://fedramp.gov/ns/oscal" and @name="impact-level"]/@value
    Data Types transmitted to, stored or processed by the first leveraged system CSO:
        (//*/component/prop[@name="leveraged-authorization-uuid" and @value="uuid-of-leveraged-system"]/parent::component/prop[@ns="https://fedramp.gov/ns/oscal" and @name="interconnection-data-type"]/@value)
    Authorized Users of the first leveraged system CSO:
        //system-security-plan/system-implementation/user[@uuid="uuid-of-user"]
    Corresponding Access Level:
        //system-security-plan/system-implementation/user[@uuid="uuid-of-user"]/prop[@name="privilege-level"]/@value
    Corresponding Authentication method:
        //system-security-plan/system-implementation/user[@uuid="uuid-of-user"]/prop[@ns="https://fedramp.gov/ns/oscal" and @name="authentication-method"]/@value
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---
## External Systems and Services Not Having FedRAMP Authorization

FedRAMP authorized services should be used, whenever possible, since their risk is defined.  However, there are instances where CSOs have external systems or services that are not FedRAMP authorized.  In OSCAL, these external systems and services must be identified using `component` assemblies with additional FedRAMP namespace and class properties as shown in the OSCAL representation below.  

{{< figure src="/img/ssp-figure-17.png" title="FedRAMP SSP template external systems (not FedRAMP authorized)." alt="Screenshot of the external system information for non-FedRAMP authorized services in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<!-- list any external connections as components in the system-characteristics -->
<component uuid="uuid-value" type="interconnection">
    <title>[EXAMPLE]External System / Service Name</title>
    <description>
        <p>Briefly describe the interconnection details.</p>
    </description>
    <!-- Props for table 7.1 columns -->
    <prop ns="https://fedramp.gov/ns/oscal" name="service-processor" 
            value="[SAMPLE] Telco Name"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="interconnection-type" value="1" />
        <prop name="direction" value="incoming"/>
        <prop name="direction" value="outgoing"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="nature-of-agreement" 
            value="contract" />
        <prop ns="https://fedramp.gov/ns/oscal" name="still-supported" value="yes" />
        <prop ns="https://fedramp.gov/ns/oscal" class="fedramp" 
            name="interconnection-data-type" value="C.3.5.1" />
        <prop ns="https://fedramp.gov/ns/oscal" class="fedramp" 
            name="interconnection-data-type" value="C.3.5.8" /> 
        <prop ns="https://fedramp.gov/ns/oscal" class="C.3.5.1" 
            name="interconnection-data-categorization" value="low" />
        <prop ns="https://fedramp.gov/ns/oscal" class="C.3.5.8" 
            name="interconnection-data-categorization" value="moderate" /> 
        <prop ns="https://fedramp.gov/ns/oscal" name="authorized-users" 
            value="SecOps engineers" />
        <prop ns="https://fedramp.gov/ns/oscal" class="fedramp" 
            name="interconnection-compliance" value="PCI SOC 2" />
        <prop ns="https://fedramp.gov/ns/oscal" class="fedramp" 
            name="interconnection-compliance" value="ISO/IEC 27001" />
        <prop ns="https://fedramp.gov/ns/oscal" name="interconnection-hosting-environment" 
            value="PaaS" />
        <prop ns="https://fedramp.gov/ns/oscal" name="interconnection-risk" value="None" />
        <prop name="isa-title" value="system interconnection agreement"/>
        <prop name="isa-date" value="2023-01-01T00:00:00Z"/>
        <prop name="ipv4-address" class="local" value="10.1.1.1"/>
        <prop name="ipv4-address" class="remote" value="10.2.2.2"/>
        <prop name="ipv6-address" value="::ffff:10.2.2.2"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="information" 
            value="Describe the information being transmitted."/>
        <prop ns="https://fedramp.gov/ns/oscal" name="port" class="remote" value="80"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="interconnection-security" 
            value="ipsec">
                <!-- cut ports, protocols -->
    <link href="#uuid-of-ICA-resource-in-back-matter" rel="isa-agreement" />                                    
    <!-- cut repeat responsible-party assembly for each required ICA role id -->
</component>
<!-- cut …. -->
<back-matter>
    <resource uuid="uuid-value">
        <title>[SAMPLE]Interconnection Security Agreement Title</title>
        <prop name="version" value="Document Version"/>
        <rlink href="./documents/ISAs/ISA-1.docx"/>
        <citation><!-- cut --></citation>
    </resource>
    <!-- repeat citation assembly for each ICA -->
</back-matter>
{{</ highlight >}}

### External System and Services (Queries)

Refer to the XPath queries below and corresponding notes for guidance on what targets in an OSCAL SSP should be used to represent each column of the "External Systems and Services Not Having FedRAMP Authorization" table in the legacy SSP template.

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Interconnection # for first external system:
        /*/system-implementation/component[@type='interconnection'][1]/ prop[@ns="https://fedramp.gov/ns/oscal" and @name="interconnection-type"]/@value
    System/Service/API/CLI Name:
        /*/system-implementation/component[@type='interconnection']/title
    Connection Details:
        /*/system-implementation/component[@type='interconnection'][1]/prop[@name="direction"]/@value
    Nature of Agreement for first external system:
        /*/system-implementation/component[@type='interconnection'][1]/ prop[@ns="https://fedramp.gov/ns/oscal" and @name="nature-of-agreement"]/@value
    Still Supported (Y/N):
        /*/system-implementation/component[@type='interconnection'][1]/ prop[@ns="https://fedramp.gov/ns/oscal" and @name="still-supported"]/@value
    Data Types:
        /*/system-implementation/component[@type='interconnection'][1]/prop[@ns="https://fedramp.gov/ns/oscal" and @name="interconnection-data-type"]/@value
    Data Categorization:
        /*/system-implementation/component[@type='interconnection'][1]/prop[@ns="https://fedramp.gov/ns/oscal" and @name="interconnection-data-categorization"]/@value
    Authorized Users:
        //system-security-plan/system-implementation/user[@uuid="uuid-of-user"]
    Corresponding Access Level:
        //system-security-plan/system-implementation/user[@uuid="uuid-of-user"]/prop @name="privilege-level"]/@value
    Other Compliance Programs:
        /*/system-implementation/component[@type='interconnection'][1]/prop[@ns="https://fedramp.gov/ns/oscal" and @name="interconnection-compliance"]/@value
    Description:
        /*/system-implementation/component[@type='interconnection'][1]/description
    Hosting Environment: 
        /*/system-implementation/component[@type='interconnection'][1]/prop[@ns="https://fedramp.gov/ns/oscal" and @name="interconnection-hosting-environment"]/@value
    Risk/Impact/Mitigation: 
        /*/system-implementation/component[@type='interconnection'][1]/prop[@ns="https://fedramp.gov/ns/oscal" and @name="interconnection-risk"]/@value
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---
## Illustrated Architecture and Narratives

### Authorization Boundary

The OSCAL approach to this type of diagram is to treat the image data as either a linked or base64-encoded `resource` in the `back-matter` section of the OSCAL file, then reference the diagram using the `link` field. The narrative describing the system architecture must be provided in the `description` field of the `authorization-boundary` assembly.

{{< figure src="/img/ssp-figure-19.png" title="FedRAMP SSP template authorization boundary sections." alt="Screenshot of the authorization boundary information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-characteristics>
    <!-- leveraged-authorization -->
    <authorization-boundary>
        <!-- 8.2 Narrative (Boundary) -->
        <description>
            <p>A holistic, top-level explanation of the FedRAMP authorization boundary.</p>
        </description>
        <!-- 8.1 Illustrated Architecture (Boundary) -->
        <diagram uuid="uuid-value">
            <description><p>A diagram-specific explanation.</p></description>
            <link href="#uuid-of-boundary-diagram-1" rel="diagram" />
            <caption>Authorization Boundary Diagram</caption>
        </diagram>
        <!-- repeat diagram assembly for each additional boundary diagram -->
    </authorization-boundary>
    <!-- network-architecture -->
</system-characteristics>

<!-- cut -->

<back-matter>
    <resource uuid="uuid-of-boundary-diagram-1">
        <description><p>The primary authorization boundary diagram.</p></description>
        <base64 filename="architecture-main.png" media-type="image/png">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Overall Description:
        /*/system-characteristics/authorization-boundary/description/node()
    Count the Number of Diagrams (There should be at least 1):
        count(/*/system-characteristics/authorization-boundary/diagram)
    Link to First Diagram:
        /*/system-characteristics/authorization-boundary/diagram[1]/link/@href


    If the diagram link points to a resource within the OSCAL file:
        /*/back-matter/resource[@uuid="uuid-of-boundary-diagram"]/base64
    OR:
        /*/back-matter/resource[@uuid="uuid-of-boundary-diagram-1"]/rlink/@href
    Diagram-specific Description:
        /*/system-characteristics/authorization-boundary/diagram[1]/description/node()
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---
### Network Architecture

Consistent with the [*Authorization Boundary*](#authorization-boundary) guidance, the OSCAL approach to network architecture diagrams is to treat image data as either a linked or base64-encoded `resource` in the `back-matter` section of the OSCAL file, then reference the diagram using the `link` field. The narrative describing the network architecture must be provided in the `description` field of the `network-architecture` assembly.

{{< figure src="/img/ssp-figure-19.png" title="FedRAMP SSP template network architecture." alt="Screenshot of the network architecture information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-characteristics>
    <!-- authorization-boundary -->
    <network-architecture>
        <!-- 8.2 Narrative (Network) -->
        <description>
            <p>A holistic, top-level explanation of the system's network.</p>
        </description>
        <!-- 8.1 Illustrated Architecture (Network) -->
        <diagram uuid="uuid-value">
            <description><p>A diagram-specific explanation.</p></description>
            <link href="#uuid-of-network-diagram-1" rel="diagram" />
            <caption>Network Diagram</caption>
        </diagram>
        <!-- repeat diagram assembly for each additional network diagram -->
    </network-architecture>
    <!-- data-flow -->
</system-characteristics>


<!-- cut -->


<back-matter>
    <!-- citation -->
    <resource uuid=" uuid-of-network-diagram-1">
        <description><p>The primary network architecture diagram.</p></description>
        <rlink href="./diagrams/network.png" media-type="image/png"/>
    </resource>
</back-matter>
{{</ highlight >}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Overall Description:
        /*/system-characteristics/network-architecture/description/node()
    Count the Number of Diagrams (There should be at least 1):
        count(/*/system-characteristics/network-architecture/diagram)
    Link to First Diagram:
        /*/system-characteristics/network-architecture/diagram[1]/link/@href


    If the diagram link points to a resource within the OSCAL file:
        /*/back-matter/resource[@uuid="uuid-of-network-diagram-1"]/base64
    OR:
        /*/back-matter/resource[@uuid="uuid-of-network-diagram-1"]/rlink/@href
    First Diagram Description:
        /*/system-characteristics/network-architecture/diagram[1]/description/node()
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---
### Data Flow

Consistent with the [*Authorization Boundary*](#authorization-boundary) guidance, the OSCAL approach to data flow diagrams is to treat image data as either a linked or base64-encoded `resource` in the `back-matter` section of the OSCAL file, then reference the diagram using the `link` field. The narrative describing the data flows must be provided in the `description` field of the `data-flow` assembly.

{{< figure src="/img/ssp-figure-19.png" title="FedRAMP SSP template data flow." alt="Screenshot of data flow information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-characteristics>
    <!-- data-flow -->
    <data-flow>
        <!-- 8.2 Narrative (Data Flow) -->
        <description>
            <p>A holistic, top-level explanation of the system's data flows.</p>
        </description>
        <!-- 8.1 Illustrated Architecture (Data Flow) -->
        <diagram uuid="uuid-value">
            <description><p>A diagram-specific explanation.</p></description>
            <link href="#uuid-of-dataflow-diagram-1" rel="diagram" />
            <caption>Data Flow Diagram</caption>
        </diagram>
        <!-- repeat diagram assembly for each additional data flow diagram -->
    </data-flow>
    <!-- network-architecture -->
</system-characteristics>   

<!-- cut -->

<back-matter>
    <!-- citation -->
    <resource uuid="uuid-of-dataflow-diagram-1">
        <description><p>The primary data flow diagram.</p></description>
        <base64 filename="data-flow-1.png" media-type="image/png">
            0000<!-- base64 cut -->0000
        </base64>
    </resource>
</back-matter>
{{</ highlight >}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Overall Description:
        /*/system-characteristics/data-flow/description/node()
    Count the Number of Diagrams (There should be at least 1):
        count(/*/system-characteristics/data-flow/diagram)
    Link to First Diagram:
        /*/system-characteristics/data-flow/diagram[1]/link/@href

    If the diagram link points to a resource within the OSCAL file:
        /*/back-matter/resource[@uuid="uuid-of-dataflow-diagram-1"]/base64
    OR:
        /*/back-matter/resource[@uuid="uuid-of-dataflow-diagram-1"]/rlink/@href
    First Diagram Description:
        /*/system-characteristics/data-flow/diagram[1]/description/node()
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---
## Ports, Protocols and Services

Entries in the ports, protocols, and services table are represented as component assemblies, with the component-type flag set to "service". Use a protocol assembly for each protocol associated with the service. For a single port, set the port-range start flag and end flag to the same value.

{{< figure src="/img/ssp-figure-20.png" title="FedRAMP SSP template ports, protocols, and services." alt="Screenshot of the ports, protocols, and services information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-implementation>
    <!-- user -->
    <component uuid="uuid-of-service" type="service">
        <title>[SAMPLE]Service Name</title>
        <description><p>Describe the service</p></description>
        <purpose>Describe the purpose for which the service is needed.</purpose>
        <link href="uuid-of-component-used-by" rel="used-by" />
        <link href="uuid-of-component-provided-by" rel="provided-by" />
        <status state="operational" />
        <protocol name="http">
            <port-range start="80" end="80" transport="TCP"/>
        </protocol>
        <protocol name="https">
            <port-range start="443" end="443" transport="TCP"/>
        </protocol>
    </component>
    <!-- Repeat the component assembly for each row in Table 9.1 -->
    <!-- system-inventory -->
</system-implementation>
{{</ highlight >}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Service (1st service):
        /*/system-implementation/component[@type='service'][1]/title
    Ports: Start (1st service, 1st protocol, 1st port range):
        /*/system-implementation/component[@type='service'][1]/protocol[1]/port-range[1]/@start
    Ports: End (1st service, 1st protocol, 1st port range):
        /*/system-implementation/component[@type='service'][1]/protocol[1]/port-range[1]/@end
    Ports: Transport (1st service, 1st protocol, 1st port range):
        /*/system-implementation/component[@type='service'][1]/protocol[1]/port-range[1]/@transport
    Protocol (1st service, 1st protocol):
        /*/system-implementation/component[@type='service'][1]/protocol[1]/@name
    Purpose (1st service):
        /*/system-implementation/component[@type='service'][1]/purpose
    Used By (1st service):
        /*/system-implementation/component[@uuid='uuid-of-component-used-by']/title
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---
## Cryptographic Modules Implemented for Data-in-Transit (DIT) 

OSCAL's component model treats independent validation of products and services as if that validation were a separate component. This means when using components with FIPS 140 validated cryptographic modules, there must be two component assemblies:

-   **The Validation Definition**: A component that provides details about the validation.

-   **The Product Definition**: A component that describes the hardware or software product.

The validation definition is a component that provides details about the independent validation. Its type must have a value of "validation". In the case of FIPS 140 validation, this must include a link field with a rel value set to "validation-details". This link must point to the cryptographic module's entry in the NIST Computer Security
Resource Center (CSRC) [Cryptographic Module Validation Program Database](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search).

The product definition is a product with a cryptographic module. It must contain all of the typical component information suitable for reference by inventory-items and control statements. It must also include a link field with a rel value set to "validation" and an href value containing
a URI fragment. The fragment must start with a hashtag (#) and include the UUID value of the validation component. This links the two together.

{{< figure src="/img/ssp-figure-21.png" title="FedRAMP SSP template cryptographic modules table (data-in-transit)." alt="Screenshot of the cryptographic modules table (data-in-transit) in the FedRAMP SSP template." >}}

##### Component Representation: Example Product with FIPS 140-2 Validation
{{< highlight xml "linenos=table" >}}
<!-- system-characteristics -->
<system-implementation>
    <!-- user -->
    <!-- Minimum Required Components -->
    
    <!-- FIPS 140-2 Validation Certificate Information -->
    <!-- Include a separate component for each relevant certificate -->
    <component uuid="uuid-value" type="validation">
        <title>Module Name</title>
        <description><p>FIPS 140-2 Validated Module</p></description>
        <prop ns="https://fedramp.gov/ns/oscal" name="asset-type" 
              value="cryptographic-module" />
        <prop ns="https://fedramp.gov/ns/oscal" name="vendor-name" 
              value="CM Vendor"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="cryptographic-module-usage" 
              value="data-in-transit"/>
        <prop name="validation-type" value="fips-140-2"/>
        <prop name="validation-reference" value="0000"/>
        <link href="https://csrc.nist.gov/projects/cryptographic-module-validation-program/Certificate/0000" rel="validation-details" />
        <status state="operational" />
    </component>
    
    <!-- FIPS 140-2 Validated Product -->
    <component uuid="uuid-value" type="software" >
        <title>Product Name</title>
        <description><p>A product with a cryptographic module.</p></description>
        <link href="#uuid-of-validation-component" rel="validation" />
        <status state="operational" />
    </component>
    
    <!-- service -->
</system-implementation>
<!-- control-implementation -->
{{</ highlight >}}

---
## Cryptographic Modules Implemented for Data-at-Rest (DAR)

The approach is the same as in the [*cryptographic module data-in-transit*](#cryptographic-modules-implemented-for-data-in-transit-dit) section.

{{< figure src="/img/ssp-figure-22.png" title="FedRAMP SSP template cryptographic modules table (data-at-rest)." alt="Screenshot of the cryptographic modules table (data-at-rest) in the FedRAMP SSP template." >}}

##### Component Representation: Example Product with FIPS 140-2 Validation
{{< highlight xml "linenos=table" >}}
<!-- system-characteristics -->
<system-implementation>
    <!-- user -->
    <!-- Minimum Required Components -->
    
    <!-- FIPS 140-2 Validation Certificate Information -->
    <!-- Include a separate component for each relevant certificate -->
    <component uuid="uuid-value" type="validation">
        <title>Module Name</title>
        <description><p>FIPS 140-2 Validated Module</p></description>
        <prop ns="https://fedramp.gov/ns/oscal" name="asset-type" 
              value="cryptographic-module" />
        <prop ns="https://fedramp.gov/ns/oscal" name="vendor-name" 
              value="CM Vendor"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="cryptographic-module-usage" 
              value="data-at-rest"/>
        <prop name="validation-type" value="fips-140-2"/>
        <prop name="validation-reference" value="0000"/>
        <link href="https://csrc.nist.gov/projects/cryptographic-module-validation-program/Certificate/0000" rel="validation-details" />
        <status state="operational" />
    </component>
    
    <!-- FIPS 140-2 Validated Product -->
    <component uuid="uuid-value" type="software" >
        <title>Product Name</title>
        <description><p>A product with a cryptographic module.</p></description>
        <link href="#uuid-of-validation-component" rel="validation" />
        <status state="operational" />
    </component>
    
    <!-- service -->
</system-implementation>
<!-- control-implementation -->
{{</ highlight >}}
