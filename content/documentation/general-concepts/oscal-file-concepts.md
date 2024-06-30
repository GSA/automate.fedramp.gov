---
title: OSCAL Files
weight: 101
---
# OSCAL File  Concepts

This section covers several important concepts and details that apply to
OSCAL-based FedRAMP files.

## File Content 

Unlike the traditional MS Word-based SSP, SAP, and SAR, the OSCAL-based
versions of these files are designed to make information available
through linkages, rather than duplicating information. In OSCAL, these
linkages are established through `import` commands.

{{< figure src="/img/content-figure-1.png" title="Each OSCAL file imports information from the one before it." alt="Figure showing how each OSCAL model is dependent the preceding OSCAL modal." >}}

\
For example, the assessment objectives and actions that appear in a
blank test case workbook (TCW) are defined in the FedRAMP profile, and
simply referenced by the SAP and SAR. Only deviations from the TCW are
captured in the SAP or SAR.

{{< figure src="/img/content-figure-2.png" title="Baseline and SSP information is referenced instead of duplicated." alt="Figure illustrating the OSCAL catalog, profile, SSP, SAP, SAR and POA&M models." >}}

\
For this reason, an OSCAL-based SAP points to the OSCAL-based SSP of the
system being assessed. Instead of duplicating system details, the
OSCAL-based SAP simply points to the SSP content for information such as
system description, boundary, users, locations, and inventory items.

The SAP also inherits the SSP's pointer to the appropriate OSCAL-based
FedRAMP baseline. Through that linkage, the SAP references the
assessment objectives and actions typically identified in the FedRAMP
TCW.

The only reason to include this content in the SAP is when the assessor
documents a deviation from the SSP, baseline, or TCW.

## Hierarchy and Sequence

For both XML and JSON, the hierarchy of syntax is important and must be
followed. For example, the `metadata` assembly must be at the top level of
the OSCAL file, just below its root. If it appears within any other
assembly, it is invalid.

The same field name is interpreted differently in different assemblies.
For example, the `title` field under `metadata` is the document title, while
the `title` field under `role` gives a human-friendly name to that role.

For XML, the sequence of fields and assemblies (elements) is also
important. JSON typically does not require a specific sequence fields
and assemblies (objects). Where sequence is important, OSCAL uses array
objects in JSON.

For example, within the `metadata` assembly, XML must find `title`,
`published`, `last-modified`, `version`, and `oscal-version` in exactly that
order. The `published` field is optional and may be omitted, but if
present, it must be in that position relative to the other fields. When
using JSON, these fields are allowed in any order within the `metadata`
assembly.

Tools must ensure this sequence is maintained when creating or modifying
XML-based OSCAL files. NIST's XML documentation presents the fields and
assemblies in the correct sequence.

Always use the hierarchy found here:

-   SSP ([XML](https://pages.nist.gov/OSCAL-Reference/models/v1.1.2/system-security-plan/xml-outline/) | [JSON](https://pages.nist.gov/OSCAL-Reference/models/v1.1.2/system-security-plan/json-outline/) )

-   SAP ([XML](https://pages.nist.gov/OSCAL-Reference/models/v1.1.2/assessment-plan/xml-outline/) | [JSON](https://pages.nist.gov/OSCAL-Reference/models/v1.1.2/assessment-plan/json-outline/) )

-   SAR ([XML](https://pages.nist.gov/OSCAL-Reference/models/v1.1.2/assessment-results/xml-outline/) | [JSON](https://pages.nist.gov/OSCAL-Reference/models/v1.1.2/assessment-results/json-outline/) )

-   POA&M ([XML](https://pages.nist.gov/OSCAL-Reference/models/v1.1.2/plan-of-action-and-milestones/xml-outline/) | [JSON](https://pages.nist.gov/OSCAL-Reference/models/v1.1.2/plan-of-action-and-milestones/json-outline/) )

### Typical OSCAL Assembly Structure

Most assemblies in OSCAL follow a general pattern as follows:

-   `title` (field): Typically only one `title` is allowed. Sometimes it is
    optional. This is a *markup-line* datatype.

-   `description` (field): Typically only one `description` field is
    allowed. Sometimes it is optional. This is a *markup-multiline*
    datatype.

-   `prop` (fields): There may be many `prop` fields. The `name` flag
    identifies the specific annotation. The `value` flag is a string
    datatype and holds the intended value. The `prop` field includes an
    optional `uuid` flag to give a globally unique identifier, an optional
    `ns` field to allow for namespacing the `prop` and indicate it is
    optional information that is not of core OSCAL syntax, and a `class`
    flag to sub-class one or more instances of the `prop` into specific
    sub-groups.

-   `link` (fields): There may be many `link` fields. The `href` flag allows a
    uniform resource identifier (URI) or URI fragment to a related item.
    Often, `href` fields point to a `resource` in back matter using its UUID
    value in the form of `href="#[uuid-value]"`.

-   ***assembly-specific fields***

-   `remarks` (field): Typically only one `remarks` field is allowed. It is
    always optional. This is a *markup-multiline* datatype.

While this assembly structure pattern is not universal in OSCAL, when any of these fields are
present, they follow this pattern.

The `prop` field is present to allow OSCAL extensions within each
assembly. See the [*FedRAMP Extensions and Accepted Values*](/documentation/general-concepts/3-fedramp-extensions-and-accepted-values/) documentation for more information on FedRAMP's use of OSCAL extensions.

##  OSCAL's Minimum File Requirements

Every OSCAL-based FedRAMP file must have a minimum set of required
fields/assemblies, and must follow the core OSCAL syntax found here:

{{< figure src="/img/content-figure-4.png" title="Anatomy of an OSCAL file." alt="Figure showing the main components of every OSCAL file." >}}

In addition to the core OSCAL syntax, the following FedRAMP-specific
implementation applies:

-   The root element of the file indicates the type of content within
    the body of the file. The recognized OSCAL root element types are as
    follows:

    -   **catalog**: Contains a catalog of control definitions, control
        objectives, and assessment activities, such as NIST SP 800-53
        and 800-53A.

    -   **profile**: Contains a control baseline, such as FedRAMP
        Moderate.

    -   **component**: Contains information about a product, service, or
        other security capability, such as the controls it can satisfy.

    -   **system-security-plan**: Describes a system and its security
        capabilities, including its authorization boundary and a
        description of how each control is satisfied.

    -   **assessment-plan**: Describes the plan for assessing a specific
        system.

    -   **assessment-results**: Describes the actual activities
        performed in the assessment of a specific system, as well as the
        results of those activities.

    -   **plan-of-action-and-milestones**: Describes and tracks known
        risks to a system, as well as the plan for remediation.

-   The Universally Unique ID (UUID) at the root must be changed every
    time the content of the file is modified.

-   Every OSCAL file must have a metadata section and include a title,
    last-modified timestamp, and OSCAL syntax version.

-   The body of an OSCAL file is different for each model.

-   Back matter syntax is identical in all OSCAL models. It is used for
    attachments, citations, and embedded content such as graphics. Tool
    developers and content authors are encouraged to attach content here
    and reference it from within the body of an OSCAL file.

The listing below shows an empty OSCAL file, based purely on the NIST
syntax; however, FedRAMP requires much more in a minimum file. The
latest OSCAL-based FedRAMP template files can be found here in JSON and
XML formats:

[https://github.com/GSA/fedramp-automation/tree/master/dist/content/rev5/templates](https://github.com/GSA/fedramp-automation/tree/master/dist/content/rev5/templates)

#### An Empty OSCAL File Representation
{{< highlight xml "linenos=table" >}}
    <?xml version="1.0" encoding="UTF-8"?>
    <OSCAL-root-element xmlns="http://csrc.nist.gov/ns/oscal/1.0" uuid="[generated-uuid]">
        <metadata>
        <title>Document Title</title>
        <last-modified>2023-03-06T00:00:00.000Z</last-modified>
        <version>0.0</version>
        <oscal-version>1.0.4</oscal-version>
        </metadata>

        <!-- body cut -->

        <back-matter />
    </OSCAL-root-element>
{{< /highlight >}}


### UTF-8 Character Encoding

OSCAL uses UTF-8 character encoding. JSON files are always UTF-8
character encoded.

In XML, the first line in the example above ensures UTF-8 encoding is
used. Other encoding options will create unpredictable results.

### OSCAL Syntax Version

Tools designed to read an OSCAL file must verify the `oscal-version` field
to determine which published syntax is used.

Tools designed to create or manipulate an OSCAL file must specify the
syntax version of OSCAL used in the file in the `oscal-version` field.

NIST ensures backward compatibility of syntax where practical; however,
this is not always possible. Some syntax changes between milestone
releases leading up to OSCAL version 1.0 are unavoidable. NIST intends
to keep all formally published schema validation files available, which
keeps validation and conversion tools available for older versions of
OSCAL. See the [*OSCAL Syntax Versions*](#oscal-syntax-versions) section for more information.
FedRAMP releases indicate, in their trailing half, the earliest version of
OSCAL supported by baselines, templates, documentation, and ancillary
utilities. See [the OSCAL Support and Deprecation Policy in the FedRAMP Automation Github repository](https://github.com/GSA/fedramp-automation/blob/e0bf4d343b8bd06daa52e7817b2215f294aeab6b/README.md#support-and-oscal-deprecation-strategy) for further details.

### Content Change Requirements

Any time a tool changes the contents of an OSCAL file, it must also:

-   update the file's `uuid flag` (`/*/@uuid`) with a new UUID; and

-   update the `last-modified` field (`/*/metadata/last-modified`) with the current date and time. (Using the OSCAL date/time format, as described in the *[Metaschema Data Types](https://pages.nist.gov/metaschema/specification/datatypes/#date-time-with-timezone)* specification)

Tools that open or import OSCAL files should rely on the UUID value
provided by the `uuid` flag and the `last-modified` field as easy methods of
knowing the file has changed.

See the following for more information:
https://pages.nist.gov/OSCAL/documentation/schema/overview/#common-high-level-structure

### Cryptographic Integrity

While tool developers are encouraged to perform their own integrity
checking, it is important to note that cryptographic hash algorithms will
produce a different result for inconsequential file differences, such as
different indentation or a change in the sequence of flags.

### Useful XPath Queries for Document Changes and OSCAL Syntax

Below are a few important queries, which enable a tool to obtain
critical information about any OSCAL file.

#### XPath Queries          
{{< highlight xml "linenos=table" >}} 
    <!-- OSCAL syntax version used in this file: -->
    /*/metadata/oscal-version                                           
                                                                        
    <!-- Last Modified Date/Time: -->                                        
    /*/metadata/last-modified                                           
                                                                        
    <!-- Unique Document ID: -->                                             
    /*/@uuid                                                            
                                                                        
    <!-- Document Title: -->                                                
    /*/metadata/title            

{{< /highlight >}}


### OSCAL Syntax Versions

NIST's approach to OSCAL development ensures the syntax validation and
format conversion tools remain available for new releases of OSCAL.

{{<callout>}}
_NIST makes the latest version of syntax validation and format conversion files available in the main OSCAL repository, including any changes since the last formal release._ 

To ensure stable resources, use a formal OSCAL release. NIST publishes formal OSCAL releases here:
https://github.com/usnistgov/OSCAL/releases
{{</callout>}}
