---
title: Implementation Statements - Overview 
weight: 125
---
## Control Implementation Descriptions

{{< figure src="/img/ssp-figure-35.png" title="SSP Template Security Control Implementation" alt="Screenshot of an SSP template security control implementation description." >}}

Within the OSCAL-based FedRAMP baselines, control statements and control
objectives are tagged with a response-point FedRAMP Extension. Every
control statement designated as a response-point in the baseline must
have a statement with the control's `implemented-requirement` assembly.
Please note that control objective response points are used for the SAP and
SAR.

When using a **FedRAMP Resolved Profile Catalog**, the following query
will identify the response points for a given control.

##### XPath Query
{{< highlight xml "linenos=table" >}}
  Response Points for AC-1:
    //control[@id='ac-1']/part[@name='statement']//prop[@name='response-point'][@ns='http://fedramp.gov/ns/oscal']/../@id

{{</ highlight >}}

---
### Organization: Policy and Procedure Statements

For each of the -1 controls, such as AC-1, there must be exactly four
statement assemblies: Part (a)(1), Part (a)(2), Part (b)(1), and Part
(b)(2).

##### Policy and Procedure Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "control-implementation": {
      "implemented-requirement": {
        "uuid": "11111111-2222-4000-8000-012000010000",
        "control-id": "ac-1",
        "statement": [
          {
            "statement-id": "ac-1_smt.a.1",
            "_comment": "cut"
          },
          {
            "statement-id": "ac-1_smt.a.2",
            "_comment": "cut"
          },
          {
            "statement-id": "ac-1_smt.b.1",
            "_comment": "cut"
          },
          {
            "statement-id": "ac-1_smt.b.2",
            "_comment": "cut"
          }
        ]
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
    <!-- system-implementation -->
    <control-implementation>
        <!-- cut -->
        <implemented-requirement uuid="11111111-2222-4000-8000-012000010000" control-id="ac-1">
            <statement statement-id="ac-1_smt.a.1"><!-- cut --></statement>
            <statement statement-id="ac-1_smt.a.2"><!-- cut --></statement>
            <statement statement-id="ac-1_smt.b.1"><!-- cut --></statement>
            <statement statement-id="ac-1_smt.b.2"><!-- cut --></statement>
        </implemented-requirement>
    </control-implementation>
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
      statement:
        - statement-id: "ac-1_smt.a.1"
          _comment: "cut"
        - statement-id: "ac-1_smt.a.2"
          _comment: "cut"
        - statement-id: "ac-1_smt.b.1"
          _comment: "cut"
        - statement-id: "ac-1_smt.b.2"
          _comment: "cut"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

---
### Organization: Multi-Part Statements 

There must be one statement assembly for each lettered part, such as
with AC-2, parts a, b, c, etc.

##### Multi-Part Statement Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "control-implementation": {
      "implemented-requirement": {
        "uuid": "11111111-2222-4000-8000-012000020000",
        "control-id": "ac-2",
        "statement": [
          {
            "statement-id": "ac-2_smt.a",
            "_comment": "cut"
          },
          {
            "statement-id": "ac-2_smt.k",
            "_comment": "cut"
          }
        ]
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
    <!-- system-implementation -->
    <control-implementation>
        <!-- cut -->
        <implemented-requirement uuid="11111111-2222-4000-8000-012000020000" control-id="ac-2">
            <statement statement-id="ac-2_smt.a"><!-- cut --></statement>
            <!-- repeat for b, c, d, e, f, g, h, i, j -->
            <statement statement-id="ac-2_smt.k"><!-- cut --></statement>
        </implemented-requirement>
    </control-implementation>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  control-implementation:
    implemented-requirement:
      uuid: "11111111-2222-4000-8000-012000020000"
      control-id: "ac-2"
      statement:
        - statement-id: "ac-2_smt.a"
          _comment: "cut"
        - statement-id: "ac-2_smt.k"
          _comment: "cut"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

---
### Organization: Single Statement

If there are no lettered parts in the control definition, such as with
AC-2 (1), there must be exactly one statement assembly.

##### Single-Statement Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "control-implementation": {
      "implemented-requirement": {
        "control-id": "ac-2.1",
        "statement": {
          "statement-id": "ac-2.1_smt",
          "_comment": "cut"
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
    <!-- system-implementation -->
    <control-implementation>
        <!-- cut -->
        <implemented-requirement control-id="ac-2.1">
            <statement statement-id="ac-2.1_smt"><!-- cut --></statement>
        </implemented-requirement>
    </control-implementation>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  control-implementation:
    implemented-requirement:
      control-id: "ac-2.1"
      statement:
        statement-id: "ac-2.1_smt"
        _comment: "cut"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

---
### Response: Overview

Within each `statement` assembly, all responses must be provided within
one or more `by-component` assemblies. There must always be a component
defined in the `system-implementation` representing the system as a whole
(**"THIS SYSTEM"**), even if individual components are defined that
comprise the system. **See the [*Working with Components*](/documentation/ssp/7-generated-content/#working-with-components) section for more information.**

An OSCAL-based FedRAMP SSP should define individual components of the
system. Components are not just hardware and software. Policies,
processes, FIPS 140 validation information, interconnections, services,
and underlying systems (leveraged authorizations) are all components.

With OSCAL, the content in the cell next to *Part a* must be broken down
into its individual components and responded to separately.

{{< figure src="/img/ssp-figure-36.png" title="SSP Template Security Control Description" alt="Screenshot of an SSP template security control description." >}}

- For **Part a**
    - Component - This System
        - Describes how *part a* is satisfied holistically, or where the description does not fit with a defined component.
    - Component - Platform
        - Describes how *part a* is satisfied by the platform.
    - Component - Web-Server
        - Describes how *part a* is satisfied by the web server.
    - Component - Process
        - Describes how *part a* is satisfied by an identified process within this organization.
    - Component - Inherited
        - Describes what is inherited from the underlying Infrastructure as a Service (IaaS) provider to satisfy *part a*.
- For **Part b**
    - Component - This System
        - Describes how *part b* is satisfied holistically, or where the description does not fit with a defined component.
    - Component - Platform
        - Describes how *part b* is satisfied by the platform.
    - Component - Web-Server
        - Describes how *part b* is satisfied by the web server.
    - Component - Process
        - Describes how *part b* is satisfied by an identified process within this organization.
    - Component - Inherited
        - Describes what is inherited from the underlying Infrastructure as a Service (IaaS) provider to satisfy *part b*.


**The following are examples.**

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
          "uuid": "11111111-2222-4000-8000-009000300100",
          "type": "software",
          "title": "Component Title",
          "description": "Description of the component.",
          "status": {
            "state": "implemented"
          }
        },
        {
          "uuid": "11111111-2222-4000-8000-009000800002",
          "type": "process-procedure",
          "title": "Process Title",
          "description": "Description of the component.",
          "status": {
            "state": "implemented"
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
              "uuid": "11111111-2222-4000-8000-009000800001",
              "component-uuid": "uuid-of-software-component",
              "description": "Describe how the software component is satisfying the control."
            },
            {
              "uuid": "11111111-2222-4000-8000-009000800002",
              "component-uuid": "uuid-of-process-component",
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
        <component uuid="11111111-2222-4000-8000-009000300100" type="software">
            <title>Component Title</title>
            <description>
                <p>Description of the component.</p>
            </description>
            <status state="implemented"/>
        </component>
        <component uuid="11111111-2222-4000-8000-009000800002" type="process-procedure">
            <title>Process Title</title>
            <description>
                <p>Description of the component.</p>
            </description>
            <status state="implemented"/>
            <responsible-role role-id="admin-unix">
                <party-uuid>3360e343-9860-4bda-9dfc-ff427c3dfab6</party-uuid>
            </responsible-role>
        </component>
    </system-implementation>
    <control-implementation>
        <!-- cut -->
        <implemented-requirement uuid="11111111-2222-4000-8000-012000020000" control-id="ac-2">
            <statement uuid="11111111-2222-4000-8000-012000020100" statement-id="ac-2_smt.a">
                <by-component uuid="11111111-2222-4000-8000-009000800001" component-uuid="uuid-of-software-component">
                    <description>
                        <p>Describe how the software component is satisfying the control.</p>
                    </description>
                </by-component>
                <by-component uuid="11111111-2222-4000-8000-009000800002" component-uuid="uuid-of-process-component">
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
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  system-implementation:
    component:
      - uuid: "11111111-2222-4000-8000-009000300100"
        type: "software"
        title: "Component Title"
        description: "Description of the component."
        status:
          state: "implemented"
      - uuid: "11111111-2222-4000-8000-009000800002"
        type: "process-procedure"
        title: "Process Title"
        description: "Description of the component."
        status:
          state: "implemented"
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
          - uuid: "11111111-2222-4000-8000-009000800001"
            component-uuid: "uuid-of-software-component"
            description: "Describe how the software component is satisfying the control."
          - uuid: "11111111-2222-4000-8000-009000800002"
            component-uuid: "uuid-of-process-component"
            description: "Describe how the process satisfies the control."
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

**NOTES:**

-   All `statement-id` values must be cited as they appear in the NIST SP
    800-53, Revision 4 or Revision 5 OSCAL catalogs:\
    <https://github.com/usnistgov/oscal-content/tree/master/nist.gov/SP800-53>

---
### Response: "This System" Component

There must always be a **"This System"** component in the SSP. This is used in several ways:

-   **Holistic Overview**: The SSP author may wish to provide a more
    holistic overview of how several components work together, even if
    details are provided individually in other `by-component` assemblies.

-   **Catch-all**: Any control response that does not cleanly align with
    another system component may be described in the **"This System"**
    component.

-   **Legacy SSP Conversion**: When converting a legacy SSP to OSCAL,
    the legacy control response statements may initially be associated
    with the **"This System"** component until the SSP author is able
    to provide responses for individual components.

{{< figure src="/img/ssp-figure-38.png" title="SSP Template Security Control Response" alt="Figure illustrating how legacy SSP template control response is broad and should apply to the 'this-system' component in OSCAL." >}}

##### Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "system-implementation": {
      "component": {
        "uuid": "11111111-2222-4000-8000-009000000000",
        "type": "this-system",
        "title": "This System",
        "description": "Description of the component.",
        "status": {
          "state": "implemented"
        }
      }
    },
    "control-implementation": {
      "implemented-requirement": {
        "uuid": "11111111-2222-4000-8000-012000020000",
        "control-id": "ac-2",
        "statement": {
          "uuid": "11111111-2222-4000-8000-012000020100",
          "statement-id": "ac-2_smt.a",
          "by-component": {
            "uuid": "11111111-2222-4000-8000-012000020102",
            "component-uuid": "11111111-2222-4000-8000-009000000000",
            "description": "Describe how individual components are working together. Describe how the system - as a whole - is satisfying this statement. This can include policy, procedures, hardware, software, etc."
          }
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
        <component uuid="11111111-2222-4000-8000-009000000000" type="this-system">
            <title>This System</title>
            <description>
                <p>Description of the component.</p>
            </description>
            <status state="implemented"/>
        </component>
    </system-implementation>
    <control-implementation>
        <!-- cut -->
        <implemented-requirement uuid="11111111-2222-4000-8000-012000020000" control-id="ac-2">
            <statement uuid="11111111-2222-4000-8000-012000020100" statement-id="ac-2_smt.a">
                <by-component uuid="11111111-2222-4000-8000-012000020102" component-uuid="11111111-2222-4000-8000-009000000000">
                    <description>
                        <p>Describe how individual components are working together.</p>
                        <p>Describe how the system - as a whole - is satisfying this statement.</p>
                        <p>This can include policy, procedures, hardware, software, etc.</p>
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
      uuid: "11111111-2222-4000-8000-009000000000"
      type: "this-system"
      title: "This System"
      description: "Description of the component."
      status:
        state: "implemented"
  control-implementation:
    implemented-requirement:
      uuid: "11111111-2222-4000-8000-012000020000"
      control-id: "ac-2"
      statement:
        uuid: "11111111-2222-4000-8000-012000020100"
        statement-id: "ac-2_smt.a"
        by-component:
          uuid: "11111111-2222-4000-8000-012000020102"
          component-uuid: "11111111-2222-4000-8000-009000000000"
          description: |
            Describe how individual components are working together.
            Describe how the system - as a whole - is satisfying this statement.
            This can include policy, procedures, hardware, software, etc.
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

**NOTES:**

-   Although the name of the component is **"This System"**,
    non-technical solutions may also be discussed here, such as policies
    and procedures.

---
### Linking to Artifacts

Any time policies, procedures, plans, and similar documentation are
cited in a control response, they must be linked.

For the legacy approach, when responding within the `by-component`
assembly for **"this system"**, the link must be within the same `by-component` assembly where the artifact is cited.

{{< figure src="/img/ssp-figure-39.png" title="SSP Template Security Control Response" alt="Figure illustrating how legacy SSP template control response should link to the appropriate artifact." >}}

##### Representation: Legacy Approach Example - No Policy Component
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "control-implementation": {
      "implemented-requirement": {
        "uuid": "11111111-2222-4000-8000-012000010000",
        "control-id": "ac-1",
        "statement": {
          "uuid": "11111111-2222-4000-8000-012000010100",
          "statement-id": "ac-1_smt.a",
          "by-component": {
            "component-uuid": "11111111-2222-4000-8000-009000000000",
            "uuid": "11111111-2222-4000-8000-012000020102",
            "description": "Describe how Part a is satisfied within the system.",
            "link": {
              "href": "#11111111-2222-4000-8000-001000000005",
              "rel": "policy"
            }
          }
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
    <control-implementation>
        <implemented-requirement uuid="11111111-2222-4000-8000-012000010000" control-id="ac-1">
            <statement uuid="11111111-2222-4000-8000-012000010100" statement-id="ac-1_smt.a">
                <by-component component-uuid="11111111-2222-4000-8000-009000000000" uuid="11111111-2222-4000-8000-012000020102">
                    <description>
                        <p>Describe how Part a is satisfied within the system.</p>
                    </description>
                    <link href="#11111111-2222-4000-8000-001000000005" rel="policy" />
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
      statement:
        uuid: "11111111-2222-4000-8000-012000010100"
        statement-id: "ac-1_smt.a"
        by-component:
          component-uuid: "11111111-2222-4000-8000-009000000000"
          uuid: "11111111-2222-4000-8000-012000020102"
          description: "Describe how Part a is satisfied within the system."
          link:
            href: "#11111111-2222-4000-8000-001000000005"
            rel: "policy"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

For the component approach, use the component representing the policy.
The link should be in the component, but may be added directly to the
`by-component` as well.

##### Representation: Component Approach Example
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "system-implementation": {
      "component": {
        "uuid": "11111111-2222-4000-8000-009000600001",
        "type": "policy",
        "title": "Access Control and Identity Management Policy",
        "description": "An example component representing a policy.",
        "link": {
          "href": "#11111111-2222-4000-8000-001000000005",
          "rel": "policy"
        },
        "status": {
          "state": "implemented"
        }
      }
    },
    "control-implementation": {
      "implemented-requirement": {
        "uuid": "11111111-2222-4000-8000-012000010000",
        "control-id": "ac-1",
        "statement": {
          "uuid": "11111111-2222-4000-8000-012000010100",
          "statement-id": "ac-1_smt.a",
          "by-component": {
            "component-uuid": "11111111-2222-4000-8000-009000600001",
            "uuid": "11111111-2222-4000-8000-012000010101",
            "description": "Describe how this policy satisfies Part a."
          }
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
        <component uuid="11111111-2222-4000-8000-009000600001" type="policy">
            <title>Access Control and Identity Management Policy</title>
            <description>
                <p>An example component representing a policy.</p>
            </description>
            <link href="#11111111-2222-4000-8000-001000000005" rel="policy" />
            <status state="implemented"/>
        </component>
    </system-implementation>
    <control-implementation>
        <implemented-requirement uuid="11111111-2222-4000-8000-012000010000" control-id="ac-1">
            <statement uuid="11111111-2222-4000-8000-012000010100" statement-id="ac-1_smt.a">
                <by-component component-uuid="11111111-2222-4000-8000-009000600001" uuid="11111111-2222-4000-8000-012000010101">
                    <description>
                        <p>Describe how this policy satisfies Part a.</p>
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
      uuid: "11111111-2222-4000-8000-009000600001"
      type: "policy"
      title: "Access Control and Identity Management Policy"
      description: "An example component representing a policy."
      link:
        href: "#11111111-2222-4000-8000-001000000005"
        rel: "policy"
      status:
        state: "implemented"
  control-implementation:
    implemented-requirement:
      uuid: "11111111-2222-4000-8000-012000010000"
      control-id: "ac-1"
      statement:
        uuid: "11111111-2222-4000-8000-012000010100"
        statement-id: "ac-1_smt.a"
        by-component:
          component-uuid: "11111111-2222-4000-8000-009000600001"
          uuid: "11111111-2222-4000-8000-012000010101"
          description: "Describe how this policy satisfies Part a."
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

For either example above, the policy must be present as a `resource` in `back-matter`.

##### In Back Matter
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "back-matter": {
    "resource": {
      "uuid": "11111111-2222-4000-8000-001000000005",
      "title": "Access Control and Identity Management Policy",
      "rlink": {
        "media-type": "application/pdf",
        "href": "./documents/policies/sample_policy.pdf"
      },
      "base64": {
        "filename": "sample_policy.pdf",
        "media-type": "application/pdf",
        "value": "00000000"
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<back-matter>
    <resource uuid="11111111-2222-4000-8000-001000000005">
        <title>Access Control and Identity Management Policy</title>
        <rlink media-type="application/pdf" href="./documents/policies/sample_policy.pdf" />
        <base64 filename="sample_policy.pdf" media-type="application/pdf">00000000</base64>
    </resource>
</back-matter>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
back-matter:
  resource:
    uuid: "11111111-2222-4000-8000-001000000005"
    title: "Access Control and Identity Management Policy"
    rlink:
      media-type: "application/pdf"
      href: "./documents/policies/sample_policy.pdf"
    base64:
      filename: "sample_policy.pdf"
      media-type: "application/pdf"
      value: "00000000"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

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
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "control-implementation": {
      "implemented-requirement": {
        "uuid": "11111111-2222-4000-8000-012000020000",
        "control-id": "ac-2",
        "statement": {
          "uuid": "11111111-2222-4000-8000-012000020100",
          "statement-id": "ac-2_smt.a",
          "by-component": [
            {
              "uuid": "11111111-2222-4000-8000-012000010101",
              "component-uuid": "11111111-2222-4000-8000-009000000000",
              "description": "Describe how the system - as a whole - is satisfying this statement.",
              "export": {
                "responsibility": {
                  "uuid": "11111111-2222-4000-8000-016000000001",
                  "provided-uuid": "11111111-2222-4000-8000-015000000001",
                  "description": "Leveraging system's responsibilities in satisfaction of AC-2. Not linked to inheritance, so this is always required.",
                  "responsible-role": {
                    "role-id": "customer"
                  }
                }
              }
            },
            {
              "uuid": "11111111-2222-4000-8000-012000010102",
              "component-uuid": "11111111-2222-4000-8000-009000300001",
              "description": "Describe how the software is satisfying this statement.",
              "export": {
                "provided": {
                  "uuid": "11111111-2222-4000-8000-015000000001",
                  "description": "Customer appropriate description of what may be inherited.",
                  "responsible-role": {
                    "role-id": "poc-for-customers"
                  }
                },
                "responsibility": {
                  "uuid": "11111111-2222-4000-8000-016000000001",
                  "provided-uuid": "11111111-2222-4000-8000-015000000001",
                  "description": "Customer responsibilities if inheriting this capability.",
                  "responsible-role": {
                    "role-id": "customer"
                  }
                }
              }
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
    <control-implementation>
        <implemented-requirement uuid="11111111-2222-4000-8000-012000020000" control-id="ac-2">
            <statement uuid="11111111-2222-4000-8000-012000020100" statement-id="ac-2_smt.a">
                <by-component uuid="11111111-2222-4000-8000-012000010101" component-uuid="11111111-2222-4000-8000-009000000000">
                    <description>
                        <p>Describe how the system - as a whole - is satisfying this statement.</p>
                    </description>
                    <export>
                        <responsibility uuid="11111111-2222-4000-8000-016000000001" provided-uuid="11111111-2222-4000-8000-015000000001">
                            <description>
                                <p>Leveraging system's responsibilities in satisfaction of AC-2.</p>
                                <p>Not linked to inheritance, so this is always required.</p>
                            </description>
                            <responsible-role role-id="customer" />
                        </responsibility>
                    </export>
                </by-component>
                <by-component uuid="11111111-2222-4000-8000-012000010102" component-uuid="11111111-2222-4000-8000-009000300001">
                    <description>
                        <p>Describe how the software is satisfying this statement.</p>
                    </description>
                    <export>
                        <provided uuid="11111111-2222-4000-8000-015000000001">
                            <description>
                                <p>Customer appropriate description of what may be inherited.</p>
                            </description>
                            <responsible-role role-id="poc-for-customers" />
                        </provided>
                        <responsibility uuid="11111111-2222-4000-8000-016000000001" provided-uuid="11111111-2222-4000-8000-015000000001">
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
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  control-implementation:
    implemented-requirement:
      uuid: "11111111-2222-4000-8000-012000020000"
      control-id: "ac-2"
      statement:
        uuid: "11111111-2222-4000-8000-012000020100"
        statement-id: "ac-2_smt.a"
        by-component:
          - uuid: "11111111-2222-4000-8000-012000010101"
            component-uuid: "11111111-2222-4000-8000-009000000000"
            description: "Describe how the system - as a whole - is satisfying this statement."
            export:
              responsibility:
                uuid: "11111111-2222-4000-8000-016000000001"
                provided-uuid: "11111111-2222-4000-8000-015000000001"
                description: |
                  Leveraging system's responsibilities in satisfaction of AC-2.
                  Not linked to inheritance, so this is always required.
                responsible-role:
                  role-id: "customer"
          - uuid: "11111111-2222-4000-8000-012000010102"
            component-uuid: "11111111-2222-4000-8000-009000300001"
            description: "Describe how the software is satisfying this statement."
            export:
              provided:
                uuid: "11111111-2222-4000-8000-015000000001"
                description: "Customer appropriate description of what may be inherited."
                responsible-role:
                  role-id: "poc-for-customers"
              responsibility:
                uuid: "11111111-2222-4000-8000-016000000001"
                provided-uuid: "11111111-2222-4000-8000-015000000001"
                description: "Customer responsibilities if inheriting this capability."
                responsible-role:
                  role-id: "customer"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

**See the [*XPath Queries for Control Implementation Descriptions*](#xpath-queries-for-control-implementation-descriptions) section.**

**See the [NIST OSCAL Leveraged Authorization Presentation](https://pages.nist.gov/OSCAL/presentations/oscal-leveraged-authorizations-v6a.pdf) for more information.**

---
