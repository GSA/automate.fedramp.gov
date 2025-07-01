---
title: Example
weight: 150
---
### Response: Example

Within each of the `statement` assemblies, all responses appear in one or
more `by-component` assemblies. Each `by-component` assembly references a `component` defined in the `system-implementation` assembly.

{{< figure src="/img/ssp-figure-37.png" title="SSP Template Security Control Response" alt="Figure illustrating how component-level control implementation statements are used in OSCAL control implementation statements." >}}

##### Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "system-implementation": {
      "component": [
        {
          "uuid": "11111111-2222-4000-8000-009000300001",
          "type": "software",
          "title": "Component Title",
          "description": "Description of the component.",
          "status": {
            "state": "operational"
          }
        },
        {
          "uuid": "11111111-2222-4000-8000-009000800001",
          "type": "process-procedure",
          "title": "Process Title",
          "description": "Description of the component.",
          "status": {
            "state": "operational"
          },
          "responsible-role": {
            "role-id": "admin-unix",
            "party-uuid": "3360e343-9860-4bda-9dfc-ff427c3dfab6"
          }
        }
      ]
    },
    "control-implementation": {
      "implemented-requirement": {
        "uuid": "11111111-2222-4000-8000-012000020000",
        "control-id": "ac-2",
        "statement": {
          "uuid": "11111111-2222-4000-8000-012000020100",
          "statement-id": "ac-2_smt.a",
          "by-component": [
            {
              "uuid": "11111111-2222-4000-8000-012000020101",
              "component-uuid": "11111111-2222-4000-8000-009000000000",
              "description": "Describe how the software component is satisfying the control."
            },
            {
              "uuid": "11111111-2222-4000-8000-012000020103",
              "component-uuid": "11111111-2222-4000-8000-009000000014",
              "description": "Describe how the process satisfies the control."
            }
          ]
        }
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
    <!-- leveraged-authorization, user -->
    <component uuid="11111111-2222-4000-8000-009000300001" type="software">
      <title>Component Title</title>
      <description>
        <p>Description of the component.</p>
      </description>
      <status state="operational"/>
    </component>
    <component uuid="11111111-2222-4000-8000-009000800001" type="process-procedure">
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
    <implemented-requirement uuid="11111111-2222-4000-8000-012000020000" control-id="ac-2">
      <statement uuid="11111111-2222-4000-8000-012000020100" statement-id="ac-2_smt.a">
        <by-component uuid="11111111-2222-4000-8000-012000020101" component-uuid="11111111-2222-4000-8000-009000000000">
          <description>
            <p>Describe how the software component is satisfying the control.</p>
          </description>
        </by-component>
        <by-component uuid="11111111-2222-4000-8000-012000020103" component-uuid="11111111-2222-4000-8000-009000000014">
          <description>
            <p>Describe how the process satisfies the control.</p>
          </description>
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
  system-implementation:
    component:
      - uuid: "11111111-2222-4000-8000-009000300001"
        type: "software"
        title: "Component Title"
        description: "Description of the component."
        status:
          state: "operational"
      - uuid: "11111111-2222-4000-8000-009000800001"
        type: "process-procedure"
        title: "Process Title"
        description: "Description of the component."
        status:
          state: "operational"
        responsible-role:
          role-id: "admin-unix"
          party-uuid: "3360e343-9860-4bda-9dfc-ff427c3dfab6"
  control-implementation:
    implemented-requirement:
      uuid: "11111111-2222-4000-8000-012000020000"
      control-id: "ac-2"
      statement:
        uuid: "11111111-2222-4000-8000-012000020100"
        statement-id: "ac-2_smt.a"
        by-component:
          - uuid: "11111111-2222-4000-8000-012000020101"
            component-uuid: "11111111-2222-4000-8000-009000000000"
            description: "Describe how the software component is satisfying the control."
          - uuid: "11111111-2222-4000-8000-012000020103"
            component-uuid: "11111111-2222-4000-8000-009000000014"
            description: "Describe how the process satisfies the control."
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

**NOTES:**

-   All `statement-id` values must be cited as they appear in the NIST SP
    800-53, Revision 4 or Revision 5 OSCAL catalogs:\
    <https://github.com/usnistgov/oscal-content/tree/master/nist.gov/SP800-53>

---
