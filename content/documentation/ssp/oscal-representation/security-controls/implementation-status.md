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
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "control-implementation": {
      "implemented-requirements": [ {
        "uuid": "11111111-2222-4000-8000-012000010000",
        "control-id": "ac-1",
        "statements": [ { 
          "by-components": [ { 
            "props" : [ {
              "ns" : "http://fedramp.gov/ns/oscal",
              "name" : "planned-completion-date",
              "value" : "2025-12-31Z"
            } ],
            "component-uuid" : "11111111-2222-4000-8000-009000000000",
            "description" : "The description",
            "implementation-status" : {
              "state" : "implemented"
            },
            "implementation-status" : {
              "remarks" : "Describe the plan to complete the implementation.",
              "state" : "partial"
            },
            "implementation-status" : {
              "remarks" : "Describe the plan to complete the implementation.",
              "state" : "planned"
            },
            "implementation-status" : {
              "remarks" : "Describe why the control is not applicable.",
              "state" : "not-applicable"
            }
           } ],
          "statement-id" : "ac-1_smt.a",
          "uuid" : "11111111-2222-4000-8000-012000010101"
         } ]
      } ]
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
    <control-implementation>
        <implemented-requirement uuid="11111111-2222-4000-8000-012000010000" control-id="ac-1">      
            <statement statement-id="ac-1_smt.a" uuid="111111111-2222-4000-8000-012000030100">
                <by-component component-uuid="11111111-2222-4000-8000-009000000000"
                    uuid="11111111-2222-4000-8000-012000010101">
                    <description><p>The description</p></description>
                    <prop ns="http://fedramp.gov/ns/oscal" name="planned-completion-date" value="2025-12-31Z" />
                    <implementation-status state="implemented"/>
                    <implementation-status state="partial">
                        <remarks>
                            <p>Describe the plan to complete the implementation.</p>
                        </remarks>
                    </implementation-status>
                    <implementation-status state="planned">
                        <remarks>
                            <p>Describe the plan to complete the implementation.</p>
                        </remarks>
                    </implementation-status>
                    <implementation-status state="not-applicable">
                        <remarks>
                            <p>Describe why the control is not applicable.</p>
                        </remarks>
                    </implementation-status>
                </by-component>
            </statement>
        </implemented-requirement>
    </control-implementation>
    <!-- back-matter -->
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  control-implementation:
    implemented-requirement:
      uuid: "11111111-2222-4000-8000-012000010000"
      control-id: "ac-1"
      statements:
      - by-components:
        - props:
          - ns: http://fedramp.gov/ns/oscal
            name: planned-completion-date
            value: 2025-12-31Z
        - component-uuid: 11111111-2222-4000-8000-009000000000
          description: The description.
          implementation-status:
            state: implemented
          implementation-status:
            remarks: Describe the plan to complete the implementation.
            state: partial
          implementation-status:
            remarks: Describe the plan to complete the implementation.
            state: planned
          implementation-status:
            remarks: Describe the plan to complete the implementation.
            state: not-applicable
          uuid: 11111111-2222-4000-8000-012000010101
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}


{{< callout >}}

**NOTE:**

The example OSCAL representation has multiple `implementation-status` assemblies for illustrative purposes only.  A FedRAMP SSP statement must only have one implementation status specified.

{{</ callout >}}

##### XPath Queries
{{< highlight xml "linenos=table" >}}
  Implementation Status (may return more than 1 result for a given control) :
    /*/control-implementation/implemented-requirement[@control-id="ac-1"]/statement[@statement-id="ac-1_smt.a"]/by-component[@uuid="11111111-2222-4000-8000-012000010101"]/implementation-status/@state
  Gap Description (If implementation-status="partial"):
    /*/control-implementation/implemented-requirement/statement/by-component/implementation-status[@state="partial"]/remarks/node()
  Planned Completion Date (If implementation-status="planned"):
    /*/control-implementation/implemented-requirement[@control-id="ac-1"]/statement/by-component/prop[@name="planned-completion-date"][@ns="http://fedramp.gov/ns/oscal"]/@value
  Plan for Completion (If implementation-status="planned"):
    /*/control-implementation/implemented-requirement/statement/by-component/implementation-status[@state="planned"]/remarks/node()
  Not Applicable (N/A) Justification (If implementation-status="na"):
    /*/control-implementation/implemented-requirement/statement/by-component/implementation-status[@state="not-applicable"]/remarks/node()

{{</ highlight >}}

---
