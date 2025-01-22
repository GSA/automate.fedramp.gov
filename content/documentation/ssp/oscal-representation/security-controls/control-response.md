---
title: Implementation Statements - General
weight: 135
---
## Implementation Statements: General



### Organization: Multi-Part Statements 

There must be one statement assembly for each lettered part, such as
with AC-2, parts a, b, c, etc.

##### Multi-Part Statement Representation
{{< highlight xml "linenos=table" >}}
<!-- system-implementation -->
<control-implementation>
    <!-- cut -->
    <implemented-requirement uuid="uuid-value" control-id="ac-2">
        <statement statement-id="ac-2_smt.a"><!-- cut --></statement>
        <!-- repeat for b, c, d, e, f, g, h, i, j -->
        <statement statement-id="ac-2_smt.k"><!-- cut --></statement>
    </implemented-requirement>
</control-implementation>

{{</ highlight >}}

---
### Organization: Single Statement

If there are no lettered parts in the control definition, such as with
AC-2 (1), there must be exactly one statement assembly.

##### Single-Statement Representation
{{< highlight xml "linenos=table" >}}
<!-- system-implementation -->
<control-implementation>
    <!-- cut -->
    <implemented-requirement control-id="ac-2.1">
        <statement statement-id="ac-2.1_smt"><!-- cut --></statement>
    </implemented-requirement>
</control-implementation>

{{</ highlight >}}

---
