---
title: Example
weight: 150
---
### Response: Example

Within each of the `statement` assemblies, all responses appear in one or
more `by-component` assemblies. Each `by-component` assembly references a `component` defined in the `system-implementation` assembly.

{{< figure src="/img/ssp-figure-37.png" title="SSP Template Security Control Response" alt="Figure illustrating how component-level control implementation statements are used in OSCAL control implementation statements." >}}

##### Representation
{{< highlight xml "linenos=table" >}}
<system-implementation>
    <!-- leveraged-authorization, user -->
    <component uuid="uuid-value" type="software">
        <title>Component Title</title>
        <description>
            <p>Description of the component.</p>
        </description>
        <status state="operational"/>
    </component>
    
    <component uuid="uuid-value" type="process">
        <title>Process Title</title>
        <description>
            <p>Description of the component.</p>
        </description>
        <status state="operational"/>
        <responsible-role role-id="admin-unix">
            <party-uuid>3360e343-9860-4bda-9dfc-ff427c3dfab6</party-uuid>
        </responsible-role>
    </component>
</system-implementation>

<control-implementation>
    <!-- cut -->
    <implemented-requirement uuid="uuid-value" control-id="ac-2">
        <statement uuid="uuid-value" statement-id="ac-2_smt.a">
            
            <by-component uuid="uuid-value" component-uuid="uuid-of-software-component">
                <description>
                    <p>Describe how the software component is satisfying the control.</p>
                </description>
            </by-component>
            <by-component uuid="uuid-value" component-uuid="uuid-of-process-component">
                <description>
                    <p>Describe how the process satisfies the control.</p>
                </description>
            </by-component>
            <!-- repeat by-component assembly for each component related to part a. -->
            
        </statement>
        <!-- repeat statement assembly for statement part (b, c, etc.) as needed. -->
    </implemented-requirement>
</control-implementation>
<!-- back-matter -->

{{</ highlight >}}

**NOTES:**

-   All `statement-id` values must be cited as they appear in the NIST SP
    800-53, Revision 4 or Revision 5 OSCAL catalogs:\
    <https://github.com/usnistgov/oscal-content/tree/master/nist.gov/SP800-53>

---
