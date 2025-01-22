---
title: Inheritence and Customer Responsibilities
weight: 145
---
### Response: Identifying Inheritable Controls and Customer Responsibilities

For systems that may be leveraged, OSCAL enables a robust mechanism for
providing both inheritance details as well as customer responsibilities
(referred to as consumer responsibilities by NIST). OSCAL is designed to
enable leveraged and leveraging system SSP details to be linked by tools
for validation.

Within the appropriate `by-component` assembly, include an export
assembly. Use `provided` to identify a capability that may be inherited by a leveraging system. Use `responsibility` to identify a `customer responsibility`. If a `responsibility` must be satisfied to achieve inheritance, add the
`provided-uuid` flag to the `responsibility` field.

##### Representation
{{< highlight xml "linenos=table" >}}
<!-- system-implementation -->
<control-implementation><!-- cut -->
    <implemented-requirement uuid="uuid-value" control-id="ac-2">
        <statement uuid="uuid-value" statement-id="ac-2_smt.a">
            <by-component uuid="uuid-value" component-uuid="uuid-of-this-system-component">
                <description>
                    <p>Describe how the system - as a whole - is satisfying this statement.</p>
                </description>
                <export>
                    <responsibility uuid="uuid-value">
                        <description>
                            <p>Leveraging system's responsibilities in satisfaction of AC-2.</p>
                            <p>Not linked to inheritance, so this is always required.</p>
                        </description>
                        <responsible-role role-id="customer" />
                    </responsibility>
                </export>
            </by-component>            
            <by-component uuid="uuid-value" component-uuid="uuid-of-software-component">
                <description>
                    <p>Describe how the software is satisfying this statement.</p>
                </description>
                <export>
                    <provided uuid="uuid-value">
                        <description>
                            <p>Customer appropriate description of what may be inherited.</p>
                        </description>
                        <responsible-role role-id="poc-for-customers" />
                    </provided>
                    
                    <responsibility uuid="uuid-value" provided-uuid="uuid-of-provided">
                        <description>
                            <p>Customer responsibilities if inheriting this capability.</p>
                        </description>
                        <responsible-role role-id="customer" />
                    </responsibility>
                </export>
            </by-component>
        </statement>
    </implemented-requirement>
</control-implementation>

{{</ highlight >}}

**See the [*XPath Queries for Control Implementation Descriptions*](#xpath-queries-for-control-implementation-descriptions) section.**

**See the [NIST OSCAL Leveraged Authorization Presentation](https://pages.nist.gov/OSCAL/presentations/oscal-leveraged-authorizations-v6a.pdf) for more information.**

---
## Leveraged Authorization Response: Inheriting Controls, Satisfying Responsibilities

When the current system is inheriting a control from or meeting customer
responsibilities defined by an underlying authorization, the leveraged
system must first be defined as described in the [*Response: Identifying Inheritable Controls and Customer Responsibilities*](#response-identifying-inheritable-controls-and-customer-responsibilities) section, and documented a `component` int the leveraging system SSP before it may be referenced in a control response. The `by-component` assembly references these components.

IMPORTANT: The leveraged system may provide a single `component`
representing the entire leveraged system\
or may provide individual system components as well. In either case, the
`inherited-uuid` property in the `component` must have the `value` flag set to the UUID of the leveraged system or component.

{{< figure src="/img/ssp-figure-41.png" title="SSP Template Control Description" alt="Screenshot of a security control description in the SSP template." >}}

##### Representation
{{< highlight xml "linenos=table" >}}
<system-implementation>
    <component uuid="uuid-value" type="this-system"><!-- cut --></component>
    <component uuid="uuid-value" type="system">
        <title><b>LEVERAGED SYSTEM as a whole (IaaS)</b></title>
        <prop name="leveraged-authorization-uuid" value="uuid-of-LA-in-this-SSP" />
        <prop name="inherited-uuid" value="uuid-of-component-in-leveraged-SSP" />
    </component>
    <component uuid="uuid-value" type="service">
        <title>Service Provided by Leveraged System</title>
        <prop name="leveraged-authorization-uuid" value="uuid-of-LA-in-this-SSP" />
        <prop name="inherited-uuid" value="uuid-of-component-in-leveraged-SSP" />
    </component>
</system-implementation>        
<control-implementation>
    <implemented-requirement uuid="uuid-value" control-id="ac-2">
        <statement uuid="uuid-value" statement-id="ac-2_smt.a">            
            <by-component uuid="uuid-value" component-uuid="uuid-of-this-system-component">
                <description><p>Describe what is satisfied by this system.</p></description>
            </by-component>
            
            <by-component uuid="uuid-value" component-uuid="uuid-leveraged-system-component">
                <description>
                    <p>Describe what is inherited from the leveraged system in satisfaction
                        of this control statement.</p>
                </description>
                
                <inherited provided-uuid="uuid-of-provided" uuid="uuid-value">
                    <description>
                        <p>Optional: Information provided by leveraged system.</p>
                    </description>
                </inherited>
                
                <satisfied responsibility-uuid="uuid-of-responsibility" uuid="uuid-value" >
                    <description>
                        <p>Description of how the responsibility was satisfied.</p>
                    </description>
                </satisfied>
            </by-component>
        </statement>
        <!-- repeat statement assembly for statement part (b, c, etc.) as needed. -->
    </implemented-requirement>
</control-implementation>
<!-- back-matter -->

{{</ highlight >}}

**See the [XPath Queries for Control Implementation Descriptions](#xpath-queries-for-control-implementation-descriptions) section**

**See the [NIST OSCAL Leveraged Authorization Presentation](https://pages.nist.gov/OSCAL/presentations/oscal-leveraged-authorizations-v6a.pdf) for more information.**

---
### XPath Queries for Control Implementation Descriptions

Use the following XPath queries to retrieve basic control response
information. For any given control response part, tools should list the
name of each component cited by a `by-component` assembly, as well as the
description.

{{< figure src="/img/ssp-figure-41.png" title="SSP Template Control Description" alt="Screenshot of a security control description in the SSP template." >}}

##### Representation
{{< highlight xml "linenos=table" >}}
  Number of cited components for AC-2, part a (Integer):
    count(/*/control-implementation/implemented-requirement[@control-id="ac-2"]/statement[@statement-id="ac-2_smt.a"]/by-component)
  Name of first component related to AC-2, part a:
    /*/system-implementation/component[@uuid=/*/control-implementation/implemented-requirement[@control-id="ac-2"]/statement[@statement-id="ac-2_smt.a"]/by-component[1]/@component-uuid]/title
  "What is the solution and how is it implemented?" for AC-2, Part (a), first component:
    /*/control-implementation/implemented-requirement[@control-id="ac-2"]/statement[@statement-id="ac-2_smt.a"]/by-component[1]/description/node()
  Is there a customer responsibility for the first component in AC-2, part a? (true/false):
    boolean(/*/control-implementation/implemented-requirement[@control-id="ac-2"]/statement[@statement-id="ac-2_smt.a"]/by-component[1] /prop[@name='responsibility'][@value='customer'])
  Customer responsibility statement for the first component in AC-2, part a:
    /*/control-implementation/implemented-requirement[@control-id="ac-2"]/statement[@statement-id="ac-2_smt.a"]/by-component[1]/prop[@name='responsibility'][@value='customer']/remarks/node()     

{{</ highlight >}}


**NOTES:**

-   Replace "ac-2" with target `control-id`.
-   Replace "ac-2_smt.a" with target control `statement-id`.
-   Replace "\[1\]" with "\[2\]", "\[3\]", etc. as needed to reference
    `by-component` `statement`.
