---
title: Leveraged Authorizations
weight: 334
---
## Leveraged Authorizations and FedRAMP-authorized Services

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
