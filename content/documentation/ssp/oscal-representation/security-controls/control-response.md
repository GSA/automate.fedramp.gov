---
title: Implementation Statements - General
weight: 135
---
## Implementation Statements: General



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
