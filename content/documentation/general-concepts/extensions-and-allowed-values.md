---
title: FedRAMP Extensions and Allowed Values
weight: 160
---

# FedRAMP Extensions and Allowed Values

Core OSCAL syntax is designed to represent cybersecurity
information that is common to any organization and compliance framework.
However, each framework and organization may have unique
needs and requirements. 

Instead of trying to provide a language that meets each of those
unique needs, OSCAL provides organizations the ability to customize OSCAL to
address specific needs.

{{<callout>}}
_Note:_ A summary of FedRAMP extensions and allowed values resides in the FedRAMP OSCAL Registry.
{{</callout>}}

The table below describes FedRAMP OSCAL customization approaches.

| OSCAL&nbsp;customization | Description                                                                                                                              |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Extensions               | Extensions enable FedRAMP's OSCAL-based content to capture information that is not available in the core OSCAL syntax.                   |
| Allowed&nbsp;values      | For many fields, FedRAMP specifies a case-sensitive set of allowed values. Only these values are recognized by FedRAMP processing tools. |


## FedRAMP Extensions

There are several pieces of information required in FedRAMP templates
that cannot be modeled using the OSCAL core syntax. NIST wanted to limit
the core OSCAL syntax to those elements that are universal across most
cybersecurity frameworks. They designed OSCAL to be extended where
unique needs existed.

{{<callout>}}
_Note:_ All FedRAMP extensions include the `ns` namespace flag set to `http://fedramp.gov/ns/oscal`.
{{</callout>}}

NIST allows organizations to extend OSCAL anyplace `prop` fields or `part` assemblies exist in the core syntax. 

{{<callout>}}
_Note:_ Currently, there are no `part` assemblies in the SSP, SAP, SAR, or POA&M.
{{</callout>}}

There are two fundamental requirements for extending OSCAL:

1. The organization must establish a unique namespace (`ns`) identifier,
    such as (`ns="http://domain.tld/ns/oscal"`), and use it to
    consistently tag all `prop` and `part` extensions from that
    organization.

2. The organization is responsible for defining, managing, and
    communicating all names (`name="scan-type"`) defined and tagged with
    the above namespace identifier.

OSCAL's core `prop` assemblies have no `ns` flag. If an `ns` flag is
present, it is an organization-defined extension. This allows each
industry standards body or organization to create their own extensions
in their own name space without concern for overlapping names. The above
approach ensures two different organizations can create their
own extensions without concern for reusing the same name values.

To refer to FedRAMP and custom extensions, tool developers must always use both the `name` and `ns` flags as a pair.

{{<callout>}}
_Note:_ FedRAMP extensions are cited in relevant portions of this document and are summarized in the FedRAMP OSCAL Registry.
{{</callout>}}

{{<callout>}}
_Note:_ The catalog and profile OSCAL models also allow the `part`
assembly to be used for extensions. This is not currently the case for
the OSCAL SSP, SAP, SAR, or POA&M.
{{</callout>}}

For example, if the core OSCAL syntax has a `status` field, but both
FedRAMP and the imaginary Payment Card Industry (PCI) organization require their own
framework-specific status field, each may define an extension with the
`name="status"` and assign their own `ns` flag. This results in three
possible `status` fields.


<br>

### Option 1: Core OSCAL

In the following example, since there is no `ns` flag, it represents the core OSCAL syntax.

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "props": [
        {
            "name": "status",
            "value": "active"
        }
    ],
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  props:
  - name: status
    value: active
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<prop name="status" value="active"/>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

XPath query:
{{< highlight xml "linenos=table" >}}
//prop[@name="status"][not(@ns)]
{{< /highlight >}}

When searching an OSCAL file for a prop or prop extension that is
part of the core OSCAL syntax, developers must filter out any with the `ns`
flag using the syntax above.


<br>

### Option 2: FedRAMP OSCAL

All FedRAMP extensions must have the `ns` flag set to `http://fedramp.gov/ns/oscal`, as demonstrated in the example below.

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "props": [
        {
            "name": "status",
            "ns": "http://fedramp.gov/ns/oscal",
            "value": "active"
        }
    ],
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  props:
  - name: status
    ns: http://fedramp.gov/ns/oscal
    value: active
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<prop name="status" ns="http://fedramp.gov/ns/oscal" value="active"/>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

XPath query:
{{< highlight xml "linenos=table" >}}
//prop[@name="status"][@ns="http://fedramp.gov/ns/oscal"]
{{< /highlight >}}


<br>

### Option 3: Custom OSCAL

The example below contains the `ns` flag with the `https://pcisecuritystandards.org/ns/oscal` value, representing the custom OSCAL syntax for the imaginary PCI organization.

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "props": [
        {
            "name": "status",
            "ns": "https://pcisecuritystandards.org/ns/oscal",
            "value": "custom-pci-status"
        }
    ],
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  props:
  - name: status
    ns: https://pcisecuritystandards.org/ns/oscal
    value: custom-pci-status
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<prop name="status" ns="https://pcisecuritystandards.org/ns/oscal"  value="custom-pci-status"/>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

XPath query:
{{< highlight xml "linenos=table" >}}
//prop[@name="status"][@ns="https://pcisecuritystandards.org/ns/oscal"]
{{< /highlight >}}


## OSCAL and FedRAMP Allowed Values

To facilitate consistent processing, the value for property names,
annotation names, and some field values is limited to a list of
case-sensitive allowed values.

In many instances, OSCAL defines allowed values, which are enforced by OSCAL-based syntax validation mechanisms.

In some cases, FedRAMP defines or adds allowed values specific to
FedRAMP ATO processing. Where defined, only these values are recognized
by FedRAMP processing tools.

For example, every control requires an implementation status. FedRAMP
only accepts one of five possible responses for this status, which must
be provided using one of the specified choices.

{{<callout>}}
_Note:_ FedRAMP allowed values are cited in relevant portions of each topic.
{{</callout>}}

