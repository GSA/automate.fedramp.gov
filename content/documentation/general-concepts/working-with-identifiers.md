---
title: OSCAL Identifiers
weight: 115
---
# OSCAL Identifiers

## Assigning Identifiers

There are four ways identifiers are typically used in OSCAL:

-   **ID flag**: uniquely identifies a field or assembly.

-   **UUID flag**: An [RFC-4122](https://tools.ietf.org/html/rfc4122)
    compliant universally unique identifier, version 4.

-   **ID/UUID Reference**: a flag or field that points to another field
    or assembly using its unique ID or UUID flag value.

-   **Uniform Resource Identifier (URI) Fragment**: A value in a flag or
    field with a [URI data
    type](https://pages.nist.gov/OSCAL/resources/concepts/uri-use/#oscal-uri-data-types).
    A [URI fragment](https://tools.ietf.org/html/rfc3986#section-3.5)
    starts with a hashtag (#) followed by a unique ID value.

{{<callout>}}
 _Tools must generate [RFC 4122](https://datatracker.ietf.org/doc/html/rfc4122#section-4.1.3) version 4 or 5 UUID values and assign them anyplace a UUID flag exists._
 {{</callout>}}

{{<callout>}}
_UUIDs are intended to be managed by tools "behind the scenes," and should not typically be exposed to users for manipulating SSP, SAP, SAR and POA&M content._
{{</callout>}}

**Identifiers** appear as an "**id**" or "**uuid**" flag to a data
field or assembly. Examples include:

-   `<control id="ac-1">`: Uniquely identifies the control.

-   `<party uuid="8e83458e-dde5-4ee2-88bc-152f8da3fc31">`: Uniquely identifies the party.

**An ID reference** in the OSCAL models typically appears with a name and hyphen in front of
the "id" (name-id) or "uuid" (name-uuid). It is typically a flag where
the relationship is one-to-one, but is sometimes a field when the
relationship is one-to-many. The name of an ID reference flag/field
typically reflects the name of the field or assembly to which it points.

Examples include:

-   `<responsible-party role-id="prepared-by">`: points to a role
    identified by "prepared-by".

-   `<implemented-requirement id="imp-req-01" control-id="ac-2">`: points to the control identified by
    "ac-2".

OSCAL provides some standard identifiers. Where appropriate, FedRAMP has
adopted those and defined additional identifiers as needed. To ensure
consistent processing, FedRAMP encourages content creators to use the
OSCAL and FedRAMP-defined identifiers to the greatest degree practical.
Deviation is likely to result in validation or processing errors.

## Uniqueness of Identifiers

Some role ID values are prescribed by OSCAL, and others by FedRAMP. These
are "reserved" and must not be assigned to other roles for other
reasons. The scope of this requirement goes beyond the current OSCAL
file to all files in the OSCAL stack as a result of import statements,
as described in the [*File Content Concepts*](/documentation/general-concepts/oscal-file-concepts/#file-content) section.

For UUID fields, if using a tool that properly generates version UUID
values, no two will be alike; however, buggy tools have been known to
create unexpected duplicate values. In an abundance of caution, tool
developers are encouraged to check for unintended duplicates whenever
generating new UUID values. At least during the testing phase of your
development lifecycle.

## Searching for Information by ID or UUID Values

When searching for an ID or UUID reference, the tool must look both in
the current OSCAL file, and other files in the OSCAL stack as described
in the [*File Content Concepts*](/documentation/general-concepts/oscal-file-concepts/#file-content) section.

For example, a UUID reference in an OSCAL-based FedRAMP SAR could refer
to a field or assembly in the SAR, SAP, or SSP. XPath and similar
standards only search the current file.

This requires OSCAL tools to search the current file first. If the ID or
UUID is not found, the tool should follow the file's import statement
and search the next file the same way. This must be repeated until
either the ID/UUID is found, or all files in the stack have been
processed however tools should consider approaches to prevent infinite recursion.

### Searching for a Field or Assembly by ID or UUID

In general, searching for an ID or UUID value within an
XML file simply requires an XPath query such as:

{{< highlight xml "linenos=table" >}}
//*[@id='id-value']

<!-- OR  -->

//*[@uuid='uuid-value']
{{< /highlight >}}

Of course, the tool must replace 'id-value' or 'uuid-value' above
with the appropriate reference.

### Ensuring the Field or Assembly Name Matches

Often flags that reference OSCAL information using its ID or UUID will
have a name and context that clarifies the expected target. For example,
a flag may appear as follows:

{{< highlight xml "linenos=table" >}}
<field-name component-uuid='1c23ddee-7001-4512-9de1-e062faa69c0a' />
{{< /highlight >}}

To ensure this UUID value points to a component, use the following XPath
query: 

{{< highlight xml "linenos=table" >}}
boolean(//*[@uuid='1c23ddee-7001-4512-9de1-e062faa69c0a']/name()='component')
{{< /highlight >}}

If the above expression returns true, the UUID points to a component as
intended.

### Limiting Searches by Field or Assembly Name

Another approach is to limit the search only to fields or flags with a
specific name.

The following will only find the UUID value if it is associated with a
component. It would work in the SSP, SAP, SAR and POA&M.
{{< highlight xml "linenos=table" >}}
//component[@uuid='1c23ddee-7001-4512-9de1-e062faa69c0a']
{{< /highlight >}}

The following will only find the UUID value if it is associated with a
component in the system-implementation assembly of the SSP. 
{{< highlight xml "linenos=table" >}}
/*/system-implementation/component[@uuid='1c23ddee-7001-4512-9de1-e062faa69c0a']
{{< /highlight >}}
