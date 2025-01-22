---
title: Implementation Status
weight: 115
---

## Implementation Status

FedRAMP only accepts only one of five values for `implementation-status`:
implemented, partial, planned, alternative, and not-applicable. A
control may be marked "partial" and "planned" (using two separate
implementation-status fields). All other choices are mutually exclusive.

**If the implementation-status is partial,** the gap must be explained
in the remarks field.

**If the implementation-status is planned,** a brief description of the
plan to address the gap, including major milestones must be explained in
the `remarks` field. There must also be a prop
(name=\"planned-completion-date\" ns=\"http://fedramp.gov/ns/oscal\")
field containing the intended completion date. With XML, `prop` fields
must appear before other sibling fields (such as `set-parmeter`, `responsible-role`, etc.), even though that sequence is
counter-intuitive in this situation.

**If the implementation-status is alternative,** the alternative
implementation must be summarized in the `remarks` field.

**If the implementation-status is not-applicable,** the N/A
justification must be provided in the `remarks` field.

{{< figure src="/img/ssp-figure-33.png" title="SSP Template Security Control Implementation Status" alt="Screenshot of an SSP template security control implementation status." >}}

##### Representation
{{< highlight xml "linenos=table" >}}
<!-- system-implementation -->
<control-implementation>
    <implemented-requirement uuid="uuid-value" control-id="ac-1">
        <prop name="planned-completion-date" 
            ns="http://fedramp.gov/ns/oscal" value="2021-01-01Z"/>
        <prop name="implementation-status" 
            ns="http://fedramp.gov/ns/oscal" value="implemented" />
        <prop name="implementation-status"
            ns="http://fedramp.gov/ns/oscal" value="partial" />
        <prop name="implementation-status" 
            ns="http://fedramp.gov/ns/oscal" value="planned" />
        <prop name="implementation-status" 
            ns="http://fedramp.gov/ns/oscal" value="not-applicable"/>      
        <!-- responsible-role, statement, by-component -->
    </implemented-requirement>  
</control-implementation>
<!-- back-matter -->

{{</ highlight >}}

##### XPath Queries
{{< highlight xml "linenos=table" >}}
  Implementation Status (may return more than 1 result for a given control) :
    /*/control-implementation/implemented-requirement[@control-id="ac-1"] /prop[@name="implementation-status"]/@value
  Gap Description (If implementation-status="partial"):
    /*/control-implementation/implemented-requirement/prop[@name='implementation-status'][@value="partial"][@ns="http://fedramp.gov/ns/oscal"]/remarks/node()
  Planned Completion Date (If implementation-status="planned"):
    /*/control-implementation/implemented-requirement[@control-id="ac-1"]/prop[@name="planned-completion-date"][@ns="http://fedramp.gov/ns/oscal"]/@value
  Plan for Completion (If implementation-status="planned"):
    /*/control-implementation/implemented-requirement/prop[@name='implementation-status'][@value="planned"][@ns="http://fedramp.gov/ns/oscal"]/remarks/node()
  Not Applicable (N/A) Justification (If implementation-status="na"):
    /*/control-implementation/implemented-requirement/prop[@name='implementation-status'][@value="not-applicable"][@ns="http://fedramp.gov/ns/oscal"]/remarks/node()

{{</ highlight >}}

The FedRAMP `implementation-status` property at the control's
`implemented-requirement` level is a summary of all statement and/or
component level core OSCAL `implementation-status` designations. It must
be set appropriately based on the least value of child statement
or component level `implementation-status` designations. When a statement
and/or component level `implementation-status` designation is not
specified, the FedRAMP `implementation-status` value is assumed.
Individual statements and/or components may override
`implementation-status` locally.

---
