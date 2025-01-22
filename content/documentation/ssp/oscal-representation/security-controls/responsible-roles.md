---
title: Responsible Roles
weight: 105
---

## Responsible Roles and Parameter Assignments

Every applicable control must have at least one `responsible-role`
defined. There must be a separate `responsible-role` assembly for each
responsible role. OSCAL requires the specified `role-id` to be valid in
the defined list of roles in the `metadata`. Controls with a FedRAMP
`implementation-status` property value of "non-applicable" (see the [*Implementation Status*](#implementation-status) section)
do not require a `responsible-role`. FedRAMP further requires that the
specified `role-id` must also have been referenced in the `system-implementation` `user` assembly. This equates to the FedRAMP requirement of all responsible roles appearing in the Personnel Roles and Privileges table.

{{< figure src="/img/ssp-figure-32.png" title="SSP Template Security Control Parameter Assignments" alt="Screenshot of an SSP template security control parameter assignments." >}}

With the `implemented-requirement` assembly, there must be one `set-parameter` statement for each of the control's parameters, as specified in the FedRAMP baseline and illustrated in the example representation below. The only exception to this is with nested parameters. Some select parameters contain an assignment parameter within a selection parameter, such as appears in AC-7 (b). In these instances, only the final selected value must be provided. The nested assignment parameter may be ignored.

OSCAL also supports parameter setting at the component level, within a
`by-component` assembly.

##### Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <role id="admin-unix">
        <title>Unix Administrator</title>
    </role>
</metadata>
<!-- Fragment: -->
<system-implementation>
    <user uuid="uuid-value">
        <role-id>admin-unix</role-id>
    </user>
</system-implementation >
<!-- system-implementation -->
<control-implementation>
    <implemented-requirement uuid="uuid-value" control-id="ac-2">
        <!-- cut -->
        <responsible-role role-id="admin-unix" />
        <set-parameter param-id="ac-2_prm_1">
            <value>System Manager, System Architect, ISSO</value>
        </set-parameter >
        <!-- cut -->
    </implemented-requirement>
</control-implementation>
<!-- back-matter -->

{{</ highlight >}}

##### XPath Queries
{{< highlight xml "linenos=table" >}}
  Number of specified Responsible Roles:
    count(/*/control-implementation/implemented-requirement[@control-id="ac-2"]/responsible-role)
  Responsible Role:
    /*/metadata/role[@id=/*/control-implementation/implemented-requirement[@control-id="ac-2"]/responsible-role[1]/@role-id]/title
  Check for existence in Personnel Roles and Privileges (Should return a number > 0)
    count(/*/system-implementation/user/role-id[string(.)=/*/control-implementation/implemented-requirement[@control-id="ac-2"]/responsible-role/@role-id])
  Parameter Value:
    /*/control-implementation/implemented-requirement[@control-id="ac-2"]/set-parameter [@param-id="ac-2_prm_1"]/value

{{</ highlight >}}

---
