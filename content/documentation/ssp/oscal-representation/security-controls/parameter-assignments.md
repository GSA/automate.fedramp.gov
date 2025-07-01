---
title: Parameter Assignments
weight: 110
---
## Parameter Assignments

With the `implemented-requirement` assembly, there must be one `set-parameter` statement for each of the control's parameters, as specified in the FedRAMP baseline and illustrated in the example representation below. This is a critical requirement for FedRAMP automated completeness checks - every parameter defined in the FedRAMP baseline must be explicitly addressed with a `set-parameter` statement. No parameters may be omitted. 

The only exception to this is with nested parameters. Some select parameters contain an assignment parameter within a selection parameter, such as appears in AC-7 (b). In these instances, only the final selected value must be provided. The nested assignment parameter may be ignored.

{{< callout >}}
**Organizational Defined Parameters (ODPs) and Aggregate Parameters**

The FedRAMP baselines define all of the ODP constraints that CSPs must provide responses for (e.g., ac-02_odp.01). The resolved profile catalogs will include aggregate parameters such as ac-1_prm_1, however, in those cases, the OSCAL SSP must provide responses for the aggregated ODP parameters (e.g., ac-01_odp.01 and ac-01_odp.02).  

{{</ callout >}}

OSCAL also supports parameter setting at the component level, within a `by-component` assembly. However, all baseline parameters must still be addressed at the control level through `set-parameter` statements in the `implemented-requirement` assembly.

**IMPORTANT:** FedRAMP does not use aggregated parameters on individual controls. Each control must have its own explicit parameter assignments.

{{< figure src="/img/ssp-figure-32.png" title="SSP Template Security Control Parameter Assignments" alt="Screenshot of an SSP template security control parameter assignments." >}}

##### Representation

## Example Implementation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "control-implementation": {
        "implemented-requirement": {
            "uuid": "11111111-2222-4000-8000-012000020000",
            "control-id": "ac-2",
            "set-parameter": [
                {
                    "param-id": "ac-02_odp.01",
                    "value": "System Manager, System Architect, ISSO"
                }
            ]
        }
    }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<control-implementation>
    <implemented-requirement uuid="11111111-2222-4000-8000-012000020000" control-id="ac-2">
        <set-parameter param-id="ac-02_odp.01">
            <value>System Manager, System Architect, ISSO</value>
        </set-parameter>
        <!-- Additional parameters as needed -->
    </implemented-requirement>
</control-implementation>
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
control-implementation:
  implemented-requirement:
    uuid: 11111111-2222-4000-8000-012000020000
    control-id: ac-2
    set-parameter:
      - param-id: ac-02_odp.01
        value: System Manager, System Architect, ISSO
{{< /highlight >}}
{{% /tab %}}
{{% /tabs %}}


##### XPath Queries
{{< highlight xml "linenos=table" >}}
  Parameter Value:
    /*/control-implementation/implemented-requirement[@control-id="ac-2"]/set-parameter[@param-id="ac-02_odp.01"]/value
{{</ highlight >}}
