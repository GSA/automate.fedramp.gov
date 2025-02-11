---
title: External Systems and Services
weight: 335
---
## External Systems and Services Not Having FedRAMP Authorization

FedRAMP authorized services should be used, whenever possible, since their risk is defined.  However, there are instances where CSOs have external systems or services that are not FedRAMP authorized.  In OSCAL, these external systems and services must be identified using `component` assemblies with additional FedRAMP namespace and class properties as shown in the OSCAL representation below.  

{{< figure src="/img/ssp-figure-17.png" title="FedRAMP SSP template external systems (not FedRAMP authorized)." alt="Screenshot of the external system information for non-FedRAMP authorized services in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "system-implementation": {
      "component": {
        "uuid": "11111111-2222-4000-8000-009000200001",
        "type": "interconnection",
        "title": "[EXAMPLE]External System / Service Name",
        "description": {
          "p": "Briefly describe the interconnection details."
        },
        "prop": [
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "service-processor",
            "value": "[SAMPLE] Telco Name"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "interconnection-type",
            "value": "1"
          },
          {
            "name": "direction",
            "value": "incoming"
          },
          {
            "name": "direction",
            "value": "outgoing"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "nature-of-agreement",
            "value": "contract"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "still-supported",
            "value": "yes"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "class": "fedramp",
            "name": "interconnection-data-type",
            "value": "C.3.5.1"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "class": "fedramp",
            "name": "interconnection-data-type",
            "value": "C.3.5.8"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "class": "C.3.5.1",
            "name": "interconnection-data-categorization",
            "value": "low"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "class": "C.3.5.8",
            "name": "interconnection-data-categorization",
            "value": "moderate"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "authorized-users",
            "value": "SecOps engineers"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "class": "fedramp",
            "name": "interconnection-compliance",
            "value": "PCI SOC 2"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "class": "fedramp",
            "name": "interconnection-compliance",
            "value": "ISO/IEC 27001"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "interconnection-hosting-environment",
            "value": "PaaS"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "interconnection-risk",
            "value": "None"
          },
          {
            "name": "isa-title",
            "value": "system interconnection agreement"
          },
          {
            "name": "isa-date",
            "value": "2023-01-01T00:00:00Z"
          },
          {
            "name": "ipv4-address",
            "class": "local",
            "value": "10.1.1.1"
          },
          {
            "name": "ipv4-address",
            "class": "remote",
            "value": "10.2.2.2"
          },
          {
            "name": "ipv6-address",
            "value": "::ffff:10.2.2.2"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "information",
            "value": "Describe the information being transmitted."
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "port",
            "class": "remote",
            "value": "80"
          },
          {
            "ns": "https://fedramp.gov/ns/oscal",
            "name": "interconnection-security",
            "value": "ipsec",
            "link": [
              {
                "href": "#uuid-of-ICA-resource-in-back-matter",
                "rel": "isa-agreement"
              }
            ]
          }
        ]
      }
    },
    "back-matter": {
      "resource": {
        "uuid": "11111111-2222-4000-8000-001000000050",
        "title": "[SAMPLE]Interconnection Security Agreement Title",
        "prop": {
          "name": "version",
          "value": "Document Version"
        },
        "rlink": {
          "href": "./documents/ISAs/ISA-1.docx"
        },
        "citation": {}
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
  <system-implementation>
    <component uuid="11111111-2222-4000-8000-009000200001" type="interconnection">
      <title>[EXAMPLE]External System / Service Name</title>
      <description>
        <p>Briefly describe the interconnection details.</p>
      </description>
      <!-- Props for table 7.1 columns -->
      <prop ns="https://fedramp.gov/ns/oscal" name="service-processor" value="[SAMPLE] Telco Name"/>
      <prop ns="https://fedramp.gov/ns/oscal" name="interconnection-type" value="1" />
      <prop name="direction" value="incoming"/>
      <prop name="direction" value="outgoing"/>
      <prop ns="https://fedramp.gov/ns/oscal" name="nature-of-agreement" value="contract" />
      <prop ns="https://fedramp.gov/ns/oscal" name="still-supported" value="yes" />
      <prop ns="https://fedramp.gov/ns/oscal" class="fedramp" name="interconnection-data-type" value="C.3.5.1" />
      <prop ns="https://fedramp.gov/ns/oscal" class="fedramp" name="interconnection-data-type" value="C.3.5.8" />
      <prop ns="https://fedramp.gov/ns/oscal" class="C.3.5.1" name="interconnection-data-categorization" value="low" />
      <prop ns="https://fedramp.gov/ns/oscal" class="C.3.5.8" name="interconnection-data-categorization" value="moderate" />
      <prop ns="https://fedramp.gov/ns/oscal" name="authorized-users" value="SecOps engineers" />
      <prop ns="https://fedramp.gov/ns/oscal" class="fedramp" name="interconnection-compliance" value="PCI SOC 2" />
      <prop ns="https://fedramp.gov/ns/oscal" class="fedramp" name="interconnection-compliance" value="ISO/IEC 27001" />
      <prop ns="https://fedramp.gov/ns/oscal" name="interconnection-hosting-environment" value="PaaS" />
      <prop ns="https://fedramp.gov/ns/oscal" name="interconnection-risk" value="None" />
      <prop name="isa-title" value="system interconnection agreement"/>
      <prop name="isa-date" value="2023-01-01T00:00:00Z"/>
      <prop name="ipv4-address" class="local" value="10.1.1.1"/>
      <prop name="ipv4-address" class="remote" value="10.2.2.2"/>
      <prop name="ipv6-address" value="::ffff:10.2.2.2"/>
      <prop ns="https://fedramp.gov/ns/oscal" name="information" value="Describe the information being transmitted."/>
      <prop ns="https://fedramp.gov/ns/oscal" name="port" class="remote" value="80"/>
      <prop ns="https://fedramp.gov/ns/oscal" name="interconnection-security" value="ipsec">
        <!-- cut ports, protocols -->
        <link href="#uuid-of-ICA-resource-in-back-matter" rel="isa-agreement" />
        <!-- cut repeat responsible-party assembly for each required ICA role id -->
      </prop>
    </component>
  </system-implementation>
  <back-matter>
    <resource uuid="11111111-2222-4000-8000-001000000050">
      <title>[SAMPLE]Interconnection Security Agreement Title</title>
      <prop name="version" value="Document Version"/>
      <rlink href="./documents/ISAs/ISA-1.docx"/>
      <citation><!-- cut --></citation>
    </resource>
    <!-- repeat citation assembly for each ICA -->
  </back-matter>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  system-implementation:
    component:
      uuid: 11111111-2222-4000-8000-009000200001
      type: interconnection
      title: "[EXAMPLE]External System / Service Name"
      description:
        p: "Briefly describe the interconnection details."
      prop:
        - ns: "https://fedramp.gov/ns/oscal"
          name: service-processor
          value: "[SAMPLE] Telco Name"
        - ns: "https://fedramp.gov/ns/oscal"
          name: interconnection-type
          value: "1"
        - name: direction
          value: incoming
        - name: direction
          value: outgoing
        - ns: "https://fedramp.gov/ns/oscal"
          name: nature-of-agreement
          value: contract
        - ns: "https://fedramp.gov/ns/oscal"
          name: still-supported
          value: yes
        - ns: "https://fedramp.gov/ns/oscal"
          class: fedramp
          name: interconnection-data-type
          value: "C.3.5.1"
        - ns: "https://fedramp.gov/ns/oscal"
          class: fedramp
          name: interconnection-data-type
          value: "C.3.5.8"
        - ns: "https://fedramp.gov/ns/oscal"
          class: "C.3.5.1"
          name: interconnection-data-categorization
          value: low
        - ns: "https://fedramp.gov/ns/oscal"
          class: "C.3.5.8"
          name: interconnection-data-categorization
          value: moderate
        - ns: "https://fedramp.gov/ns/oscal"
          name: authorized-users
          value: "SecOps engineers"
        - ns: "https://fedramp.gov/ns/oscal"
          class: fedramp
          name: interconnection-compliance
          value: "PCI SOC 2"
        - ns: "https://fedramp.gov/ns/oscal"
          class: fedramp
          name: interconnection-compliance
          value: "ISO/IEC 27001"
        - ns: "https://fedramp.gov/ns/oscal"
          name: interconnection-hosting-environment
          value: PaaS
        - ns: "https://fedramp.gov/ns/oscal"
          name: interconnection-risk
          value: None
        - name: isa-title
          value: "system interconnection agreement"
        - name: isa-date
          value: "2023-01-01T00:00:00Z"
        - name: ipv4-address
          class: local
          value: "10.1.1.1"
        - name: ipv4-address
          class: remote
          value: "10.2.2.2"
        - name: ipv6-address
          value: "::ffff:10.2.2.2"
        - ns: "https://fedramp.gov/ns/oscal"
          name: information
          value: "Describe the information being transmitted."
        - ns: "https://fedramp.gov/ns/oscal"
          name: port
          class: remote
          value: "80"
        - ns: "https://fedramp.gov/ns/oscal"
          name: interconnection-security
          value: ipsec
          link:
            - href: "#uuid-of-ICA-resource-in-back-matter"
              rel: isa-agreement
  back-matter:
    resource:
      uuid: "11111111-2222-4000-8000-001000000050"
      title: "[SAMPLE]Interconnection Security Agreement Title"
      prop:
        name: version
        value: "Document Version"
      rlink:
        href: "./documents/ISAs/ISA-1.docx"
      citation: {}
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

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
