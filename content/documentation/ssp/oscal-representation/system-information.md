---
title: System Information
weight: 331
---
## System Information

### Cloud Service Provider (CSP) Name

The cloud service provider (CSP) must be provided as one of the party assemblies within the metadata.

{{< figure src="/img/ssp-figure-4.png" title="FedRAMP SSP template CSP Name" alt="Screenshot of the CSP name in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< tabs XML JSON YAML >}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
    <metadata>
        <!-- CSP Name -->
        <party uuid="11111111-2222-4000-8000-004000000001" type="organization">
            <name>Cloud Service Provider (CSP) Name</name>
        </party>
    </metadata>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "metadata": {
      "party": {
        "uuid": "11111111-2222-4000-8000-004000000001",
        "type": "organization",
        "name": "Cloud Service Provider (CSP) Name"
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  metadata:
    party:
      uuid: "11111111-2222-4000-8000-004000000001"
      type: organization
      name: "Cloud Service Provider (CSP) Name"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

---
### System Name, Abbreviation, and FedRAMP Unique Identifier

The remainder of the system information is provided in the
system-characteristics assembly.

The FedRAMP-assigned application number is the unique ID for a FedRAMP system. OSCAL supports several system identifiers, which may be assigned by different organizations.

For this reason, OSCAL requires the identifier-type flag be present and have a value that uniquely identifies the issuing organization. FedRAMP requires its value to be "https://fedramp.gov" for all FedRAMP-issued application numbers.

{{< figure src="/img/ssp-figure-5.png" title="FedRAMP SSP template System Name and Package ID" alt="Screenshot of the system name, and package ID in the FedRAMP SSP template." >}}

This assembly defines the full name of the system and its short name. A FedRAMP OSCAL SSP must define the system name and its short name.

#### OSCAL Representation
{{< tabs XML JSON YAML >}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
    <metadata>
        <!-- CSP Name -->
        <party uuid="11111111-2222-4000-8000-004000000001" type="organization">
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
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "metadata": {
      "party": {
        "uuid": "11111111-2222-4000-8000-004000000001",
        "type": "organization",
        "name": "Cloud Service Provider (CSP) Name"
      }
    },
    "system-characteristics": {
      "system-name": "System's Full Name",
      "system-name-short": "System's Short Name or Acronym",
      "system-id": {
        "identifier-type": "http://fedramp.gov",
        "value": "F00000000"
      }
      // cut
    }
    // cut
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  metadata:
    party:
      uuid: "11111111-2222-4000-8000-004000000001"
      type: organization
      name: "Cloud Service Provider (CSP) Name"
  system-characteristics:
    system-name: "System's Full Name"
    system-name-short: "System's Short Name or Acronym"
    system-id:
      identifier-type: "http://fedramp.gov"
      value: "F00000000"
    # cut
  # cut
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

<br />
{{<callout>}}

**FedRAMP Allowed Value** 

Required Identifier Type:
- identifier-type="https://fedramp.gov"

{{</callout>}}

---
### Service Model

The core-OSCAL system-characteristics assembly has a property for the cloud service model.

{{< figure src="/img/ssp-figure-6.png" title="FedRAMP SSP template cloud service model" alt="Screenshot of the cloud service model in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< tabs XML JSON YAML >}}

{{% tab %}}
{{< highlight xml "linenos=table, hl_lines=14-19" >}}
<system-security-plan>
    <metadata>
        <!-- CSP Name -->
        <party uuid="11111111-2222-4000-8000-004000000001" type="organization">
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
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight json "linenos=table, hl_lines=17-23" >}}
{
  "system-security-plan": {
    "metadata": {
      "party": {
        "uuid": "11111111-2222-4000-8000-004000000001",
        "type": "organization",
        "name": "Cloud Service Provider (CSP) Name"
      }
    },
    "system-characteristics": {
      "system-name": "System's Full Name",
      "system-name-short": "System's Short Name or Acronym",
      "system-id": {
        "identifier-type": "http://fedramp.gov",
        "value": "F00000000"
      },
      "prop": {
        "name": "cloud-service-model",
        "value": "saas",
        "remarks": {
          "p": "Remarks are required if service model is \"other\". Optional otherwise."
        }
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table, hl_lines=13-17" >}}
---
system-security-plan:
  metadata:
    party:
      uuid: "11111111-2222-4000-8000-004000000001"
      type: organization
      name: "Cloud Service Provider (CSP) Name"
  system-characteristics:
    system-name: "System's Full Name"
    system-name-short: "System's Short Name or Acronym"
    system-id:
      identifier-type: "http://fedramp.gov"
      value: "F00000000"
    prop:
      name: "cloud-service-model"
      value: "saas"
      remarks:
        p: "Remarks are required if service model is \"other\". Optional otherwise."
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

<br />
{{<callout>}}

**OSCAL Allowed Values** 

Valid Service Model values:
- saas
- paas
- iaas
- other

{{</callout>}}

**NOTE:**

-   A cloud service provider may define two or more cloud service models for the cloud service offering defined in the system security plan if applicable for customer use (IaaS and PaaS; IaaS and PaaS and SaaS; PaaS and SaaS). Cloud service providers may use a "cloud-service-model" prop for each applicable cloud service model.
-   If the service model is "other", the remarks field is required. Otherwise, it is optional.

---
### Deployment Model

The core-OSCAL system-characteristics assembly has a property for the cloud deployment model.

{{< figure src="/img/ssp-figure-7.png" title="FedRAMP SSP template cloud deployment model" alt="Screenshot of the cloud deployment model in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< tabs XML JSON YAML >}}

{{% tab %}}
{{< highlight xml "linenos=table, hl_lines=20-25" >}}
<system-security-plan>
    <metadata>
        <!-- CSP Name -->
        <party uuid="11111111-2222-4000-8000-004000000001" type="organization">
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
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight json "linenos=table, hl_lines=25-31" >}}
{
  "system-security-plan": {
    "metadata": {
      "party": {
        "uuid": "11111111-2222-4000-8000-004000000001",
        "type": "organization",
        "name": "Cloud Service Provider (CSP) Name"
      }
    },
    "system-characteristics": {
      "system-name": "System's Full Name",
      "system-name-short": "System's Short Name or Acronym",
      "system-id": {
        "identifier-type": "http://fedramp.gov",
        "value": "F00000000"
      },
      "prop": [
        {
          "name": "cloud-service-model",
          "value": "saas",
          "remarks": {
            "p": "Remarks are required if service model is \"other\". Optional otherwise."
          }
        },
        {
          "name": "cloud-deployment-model",
          "value": "public-cloud",
          "remarks": {
            "p": "Remarks are required if deployment model is \"hybrid\". Optional otherwise."
          }
        }
      ]
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table, hl_lines=18-21" >}}
---
system-security-plan:
  metadata:
    party:
      uuid: "11111111-2222-4000-8000-004000000001"
      type: organization
      name: "Cloud Service Provider (CSP) Name"
  system-characteristics:
    system-name: "System's Full Name"
    system-name-short: "System's Short Name or Acronym"
    system-id:
      identifier-type: "http://fedramp.gov"
      value: "F00000000"
    prop:
      - name: "cloud-service-model"
        value: "saas"
        remarks:
          p: "Remarks are required if service model is \"other\". Optional otherwise."
      - name: "cloud-deployment-model"
        value: "public-cloud"
        remarks:
          p: "Remarks are required if deployment model is \"hybrid\". Optional otherwise."
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

<br />
{{<callout>}}

**FedRAMP Accepted Values**
- name="cloud-deployment-model"

    Valid: public-cloud, private-cloud, government-only-cloud, hybrid-cloud, other

{{</callout>}}

**NOTE:**

-   A cloud service provider may define one and only one cloud deployment model in the system security plan for a cloud service offering.

-   OSCAL 1.0.0 permits a cloud-deployment-model of value community-cloud, but FedRAMP does not permit such a deployment model for cloud service offerings and is not permitted for a FedRAMP OSCAL-based system security plan.
-   If the deployment model is \"hybrid\", the remarks field is required. Otherwise, it is optional.

### System Status

The system status in the FedRAMP SSP template document is specified in the "Fully Operational as of" table cell illustrated in the figure below.  OSCAL has a `status` assembly that is used to describe the operational status of the system.  In addition, FedRAMP has defined an extension that must be used to provide the date when the system became operational.

{{< figure src="/img/ssp-figure-10.png" title="FedRAMP SSP template system status." alt="Screenshot of the system status information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< tabs XML JSON YAML >}}

{{% tab %}}
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
        <system-id identifier-type="http://fedramp.gov/ns/oscal">F00000000</system-id>
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
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight json "linenos=table, hl_lines=12-25" >}}
{
  "system-security-plan": {
    "metadata": {},
    "system-characteristics": {
      "system-name": "System's Full Name",
      "system-name-short": "System's Short Name or Acronym",
      "system-id": {
        "identifier-type": "http://fedramp.gov/ns/oscal",
        "value": "F00000000"
      },
      "security-sensitivity-level": "fips-199-moderate",
      "status": {
        "state": "operational",
        "remarks": {
          "p": [
            "If the status is “other”, the remarks field is required.",
            "Otherwise, it is optional."
          ]
        }
      },
      "prop": {
        "ns": "https://fedramp.gov/ns/oscal",
        "name": "fully-operational-date",
        "value": "mm/dd/yyyy"
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table, hl_lines=10-19" >}}
---
system-security-plan:
  metadata: {}
  system-characteristics:
    system-name: "System's Full Name"
    system-name-short: "System's Short Name or Acronym"
    system-id:
      identifier-type: "http://fedramp.gov/ns/oscal"
      value: "F00000000"
    security-sensitivity-level: "fips-199-moderate"
    status:
      state: operational
      remarks:
        p:
          - "If the status is “other”, the remarks field is required."
          - "Otherwise, it is optional."
    prop:
      ns: "https://fedramp.gov/ns/oscal"
      name: "fully-operational-date"
      value: "mm/dd/yyyy"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

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

**NOTE:**

-   If the status is "other", the remarks field is required. Otherwise, it is optional.

-   While under-development and disposition are valid OSCAL values, systems with either of these operational status values are not eligible for a FedRAMP Authorization.

---
### System Functionality

The system functionality in the FedRAMP SSP template document is specified in the “General System Description” table cell illustrated in the figure below. OSCAL has a `description` field within the `system-characteristics` assembly that is used to describe the system and its functionality.

{{< figure src="/img/ssp-figure-11.png" title="FedRAMP SSP template general system description." alt="Screenshot of the general system description information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< tabs XML JSON YAML >}}

{{% tab %}}
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
        <system-id identifier-type="http://fedramp.gov/ns/oscal">F00000000</system-id>
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
            <!-- (use paragraph, list item, or table) -->          
        </description>

    </system-characteristics>
    <!--  cut -->     
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight json "linenos=table, hl_lines=12-14" >}}
{
  "system-security-plan": {
    "metadata": {},
    "system-characteristics": {
      "system-name": "System's Full Name",
      "system-name-short": "System's Short Name or Acronym",
      "system-id": {
        "identifier-type": "http://fedramp.gov/ns/oscal",
        "value": "F00000000"
      },
      "security-sensitivity-level": "fips-199-moderate",
      "description": {
        "p": "Describe the purpose and functions of this system here."
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table, hl_lines=10-11" >}}
---
system-security-plan:
  metadata: {}
  system-characteristics:
    system-name: "System's Full Name"
    system-name-short: "System's Short Name or Acronym"
    system-id:
      identifier-type: "http://fedramp.gov/ns/oscal"
      value: "F00000000"
    security-sensitivity-level: "fips-199-moderate"
    description:
      p: "Describe the purpose and functions of this system here."
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}
