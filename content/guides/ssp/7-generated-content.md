---
title: Generated Content
weight: 106
---

The following artifacts are historically generated by hand to summarize content found in other portions of the FedRAMP SSP. When using OSCAL, these artifacts can be generated from content found elsewhere in this document. This includes the:

-   **Control Information Summary (CIS)**
-   **Customer Responsibility Matrix (CRM)**

If delivering SSP content in OSCAL, CSPs are no longer required to manually generate and maintain these artifacts, provided the content in their OSCAL-based FedRAMP SSP remains accurate.

**Tool developers are encouraged to develop their own solutions to generating this content.**

## 7.1. Generating the Control Information Summary (CIS)

There are many ways a tool developer can generate the CIS. FedRAMP is developing an Extensible Stylesheet Language Transformation (XSLT) file to generate the FedRAMP CIS. When ready, FedRAMP will make this freely available to the public here:

<https://github.com/GSA/fedramp-automation/tree/master/dist/content/rev5/resources>

## 7.2. Generating the Customer Responsibility Matrix (CRM)

There are many ways a tool developer can generate the CRM. FedRAMP is
developing\
an XSLT file to generate the FedRAMP CRM. When ready, FedRAMP will make
this freely available to the public here:

[https://github.com/GSA/fedramp-automation/tree/master/dist/content/resources](https://github.com/GSA/fedramp-automation/tree/master/dist/content/resources)

#### Useful CRM XPath Queries 
{{< highlight xml "linenos=table" >}}
  Flat-File CRM Query:
    //control-implementation/implemented-requirement/prop[@name="control-origination"][@ns="https://fedramp.gov/ns/oscal"][@value="customer-configured" or @value="customer-provided"]/remarks/node()
  Component-based CRM Query:
    //control-implementation/implemented-requirement/statement/by-component[@component-id="customer"]/description

{{</ highlight >}}


## 7.3. Working with Components

NIST designed OSCAL such that a system architect can express all aspects
of the system as components. A component is anything that can satisfy a control requirement. This includes hardware, software, services, and underlying service providers, as well as policies, plans, and procedures. There are several ways to use components in an OSCAL-based SSP. The following defines FedRAMP\'s minimum initial use.

This section will likely be updated as NIST continues to evolve its approach to components in OSCAL, and as FedRAMP receives feedback from stakeholders.

**FedRAMP-defined component identifiers are cited in relevant portions of this document and summarized in the FedRAMP OSCAL Registry.**

### 7.3.1. Minimum Required Components

There must be a component that represents the entire system itself. It should be the only component with the component-type set to "system".

The following is an example of defined components.

#### Minimum Required Component Representation
{{< highlight xml "linenos=table" >}}
<!-- system-characteristics -->
<system-implementation>
    <!-- user -->
    
    <!-- This System -->
    <component uuid="uuid-value" type="this-system" >
        <title>This System</title>
        <description><p>
            The entire system as depicted in the system authorization boundary.
        </p></description>
        <status state="operational" />
    </component>
    
</system-implementation>

{{</ highlight >}}

### 7.3.2. Common Additional Components

For each FIPS 140 validated module, there must be a component that represents the validation certificate itself. For more information about this, see the *FIPS 140 Validated Components* Section.

#### Common Additional Component Representation
{{< highlight xml "linenos=table" >}}
<!-- system-characteristics -->
<system-implementation>
    <!-- user -->
    <!-- System Component -->
    
    <!-- Ports, Protocols and Services Entry -->
    <component uuid="uuid-of-service" type="service">
        <title>[SAMPLE]Service Name</title>
        <description><p>Describe the service</p></description>
        <purpose>Describe the purpose the service is needed.</purpose>
        <prop name="used-by" value="What uses this service?"/>
        <status state="operational" />
        <protocol name="http">
            <port-range start="80" end="80" transport="TCP"/>
        </protocol>
        <protocol name="https">
            <port-range start="443" end="443" transport="TCP"/>
        </protocol>
    </component>
    
    <!-- FIPS 140 Validation Certificate Information -->
    <!-- Include a separate component for each relevant certificate -->
    <component uuid="uuid-value" type="validation">
        <title>Module Name</title>
        <description><p>FIPS 140 Validated Module</p></description>
        <prop name="validation-type" value="fips-140-2"/>
            <prop name="validation-reference" value="0000"/>
            <link href="https://csrc.nist.gov/projects/cryptographic-module-validation-program/Certificate/0000" />
            <status state="operational" />
    </component>
    
    <!-- service -->
</system-implementation>
<!-- control-implementation -->

{{</ highlight >}}

### 7.3.3. Components as a Basis for System Inventory

NIST\'s approach to component-based system modeling is to reduce redundancy of information and increase flexibility. NIST accomplishes this with separate component and inventory item modeling.

This is a one-to-many relationship. One component to many inventory item instances.

For example, if an open-source operating system (OS) is used in many places throughout the system, it is defined once as a component. All information about the product, vendor, and support are modeled within the component detail. If the OS is used four times within the system, each use is an inventory item, with details about that specific information, such as IP address.

![Components and Inventory](/img/ssp-figure-42.png)\
*Relationship of Components and Inventory*

FedRAMP requires a component assembly for each model of infrastructure device used, and each version of software and database used within the system. FedRAMP is not asking for more detail than provided in the legacy inventory workbook. Only that the information is organized differently.

As NIST continues to evolve its component approach, FedRAMP will re-evaluate its approach to system inventory representation.

## 7.4. Converting a Legacy SSP to OSCAL

NIST designed OSCAL such that a system architect can express all aspects of the system as components. A component is anything that can satisfy a control
requirement. This includes hardware, software, services, and underlying service providers, as well as policies, plans, and procedures.

OSCAL is also designed to support legacy conversion of SSPs without individual components defined and enables an SSP author to migrate to the component approach gradually over time. In this instance, only a single component is initially required, representing the system as a whole and designated with the special component type, "this-system". The following provides an example of FedRAMP\'s minimum required component approach:

#### Example control for legacy SSP conversion
{{< highlight xml "linenos=table" >}}
<!-- system-characteristics -->
<system-implementation>
    <!-- Include a separate component for each relevant certificate -->
    <component uuid="uuid-value" type="this-system">
        <title>System Name</title>
        <description>
            <p>Component representing the entire system.</p>
        </description>
    </component>
</system-implementation>
<control-implementation>
    <description><p>FedRAMP SSP Template Section 13</p></description>
    <implemented-requirement control-id="ac-1" uuid="uuid-value">
        <statement statement-id="ac-1_stmt.a" uuid="uuid-value">
            <by-component component-uuid="Component-uuid-value" uuid="uuid-value">
                <description>
                    <p>Describe how Part a is satisfied within the system.</p>
                </description>
            </by-component>
        </statement>
        <statement statement-id="ac-1_stmt.b.1" uuid="uuid-value">
            <by-component component-uuid="Component-uuid-value" uuid="uuid-value">
                <description>
                    <p>Describe how Part b 1 is satisfied within the system.</p>
                </description>
            </by-component>
        </statement>
        <statement statement-id="ac-1_stmt.b.2" uuid="uuid-value">
            <by-component component-uuid="Component-uuid-value" uuid="uuid-value">
                <description>
                    <p>Describe how Part b 2 is satisfied within the system.</p>
                </description>
            </by-component>
        </statement>
    </implemented-requirement>
</control-implementation>

{{</ highlight >}}
