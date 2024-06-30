---
title: OSCAL Citations and Attachments
weight: 130
---

# Citations and Attachments in OSCAL Files

OSCAL is designed so that all citations and attachments are defined once
at the end of the file as a `resource`, and then referenced as needed
throughout the file. This includes logos, diagrams, policies,
procedures, plans, evidence, and interconnection security agreements
(ISA).

Each `resource` may be referenced from anywhere in the OSCAL file, using
its resource UUID.
{{< highlight xml "linenos=table" >}}
<back-matter>
  <resource uuid="3df7eeea-421b-459d-98cf-3d972bec610a">
      <title>Attachment or Document Title</title>
      <desc>An optional description of the attachment.</desc>
      <rlink href="./relative/path/doc.pdf" media-type="application/pdf"/>
      <rlink href="/absolute/path/doc.pdf" media-type="application/pdf"/>
      <base64 filename="doc.pdf"
        media-type="application/pdf">YSBGZWRSQU1QIGRvY3VtZW50Lg==</base64>
  </resource>
</back-matter>
{{< /highlight >}}

The `media-type` flag should be present and must be set to an [Internet
Assigned Numbers Authority (IANA) Media
Type](http://www.iana.org/assignments/media-types/media-types.xhtml).

## Citations

Citations are for reference. The content is not included with the
authorization package.

Citations use an `rlink` field with an *absolute path* to content that is
accessible by FedRAMP and Agency reviewers from government systems.

Examples include links to publicly available laws such as FISMA, and
applicable standards such as NIST SP 800 series documents.

## Attachments

Unlike citations, attachments are included with the authorization
package when submitted.

Tools may either embed an attachment using the `base64` field, or point to an attachment using an `rlink` field. If no base64 embedded content is
present, at least one `rlink` field must exist with either an *absolute
path* to content that is accessible by FedRAMP and Agency reviewers from
government systems, or a relative path.

If a relative path is used, the attachment must be delivered with the
OSCAL file and packaged such that the attachment exists in the correct
relative location.

Examples include the logo for the CSP or 3PAO, authorization boundary
diagrams, policies, process, plans, raw scanner output, assessment
evidence, and POA&M deviation request evidence.

Tools should embed (base64) or link to (rlink) an attachment once as a
`resource` in `back-matter`, then use URI fragments to reference the
attachment anyplace it is needed within the body of the OSCAL file, as
described in the [*Assigning Identifiers*](/documentation/general-concepts/working-with-identifiers/#assigning-identifiers) and the [*Working With href Flags*](/documentation/general-concepts/oscal-data-types/#working-with-href-flags) sections.

For example, a policy document that satisfies several control families
is attached as a `resource` in the `back-matter`, with a UUID of
`3df7eeea-421b-459d-98cf-3d972bec610a`. Each control satisfied by that
policy links to the policy using a URI fragment as follows:

{{< highlight xml "linenos=false" >}}
<link href="#3df7eeea-421b-459d-98cf-3d972bec610a" rel="policy" />
{{< /highlight >}}

As described in the [*Working With href Flags*](/documentation/general-concepts/oscal-data-types/#working-with-href-flags) sections, when a tool
identifies a URI fragment in an `href` value, the leading hashtag (#) must
be dropped and the remaining value is expected to reference an OSCAL
addressable ID or UUID. This ID/UUID may be either within the OSCAL file
itself, or within other OSCAL documents linked via the `import` field.

The policy's title, version, publication date and other details are
defined once in the resource and are displayed anyplace the policy is
referenced. If a newer policy is published, only the one resource
needs to be updated.

If the policy's location is identified as `./policies/doc.pdf`, the
OSCAL file and the doc.pdf file should be delivered together and
packaged such that the folder containing the OSCAL file includes a
sub-folder named `policies`, which contains the `doc.pdf` file.

When using attachments with relative paths, consider using a technology
such as a ZIP archive to package and deliver attachments while
maintaining their relative position to the OSCAL file.

## Including Multiple rlink and base64 Fields

Within a `resource`, there may be:

- no `rlink` nor `base64` fields;
- one or more `rlink` fields;
- one or more base64-encoded data fields within the OSCAL file; or
- any combination of `rlink` and `base64` fields.

OSCAL allows multiple `rlink` and `base64` fields to exist within the same `resource`. This provides the flexibility to identify multiple locations or multiple formats of the same resource. Some examples of using
multiple `rlink` and/or `base64` fields within the same resource include:

- **Multiple Locations**: Multiple `rlink` fields allow an OSCAL tool to
    include one `rlink` field with an *absolute* path to the authoritative
    location of a policy document within the CSP's intranet. The same
    `resource` could have a second `rlink` field with a *relative* path to
    the same policy document. Having both allows the CSP to maintain the
    link to the authoritative location of the policy when working with the
    OSCAL file internally, while allowing a cached, local copy to travel
    with the OSCAL file when delivered to FedRAMP for review.
- **Multiple Quality Levels**: Multiple `rlink` or `base64` fields allow
    both low-resolution and high-resolution versions of the same image,
    which is sometimes used to boost the performance of web-based
    applications.
- **Multiple Formats**: Multiple `rlink` or `base64` fields allow a
    portable network graphic (PNG) version of an image to be provided
    for presentation by a web application, and a more detailed portable
    document format (PDF) version of the same image for download by
    users.

## Handling Multiple rlink and base64 Fields

OSCAL `resource` assemblies are designed to be flexible and offer
developers the flexibility to implement handling of multiple `rlink` and
`base64` fields on a case-by-case basis.

This section describes FedRAMP's processing of multiple `rlink` and
`base64` fields, which will be used by default unless a compelling
circumstance requires otherwise.

FedRAMP accepts both `base64` and `rlink` option content for diagrams and
graphics. FedRAMP prefers that documents, such as policies and plans, are
attached using `rlink` fields and relative paths.

If the tool is designed to work interactively with a user, the tool
developer should consider designing the tool to make intelligent choices
based on context and circumstances where practical. The tool could also
present valid choices to the user where the correct choice is ambiguous
to the tool.

When more than one `rlink` and/or `base64` field is present in a resource,
FedRAMP's automated processing tools will attempt to find valid content
using the following priority, unless specified otherwise:

1.  FedRAMP tools will look first in `base64` fields.

    a.  Start with the first `base64` field in the resource.

    b.  Check each `base64` field in the sequence in which they appear in
        the `resource`.

    c.  If valid content is found, stop looking and use the content.

    d.  If no valid content is found after checking all `base64` fields in
        the resource, proceed to step #2.
1.  If no valid base64 content is found, look in `rlink` fields.

    a.  Start with the first `rlink` field in the resource.

    b.  Check each `rlink` field in the sequence in which they appear in
        the `resource`.

    c.  If valid content is found, stop looking and use the content.

    d.  If no valid content is found after checking all `rlink` fields,
        treat the resource as invalid, which may include raising a
        warning or error message.

## Citation and Attachment Details

IMPORTANT: As of OSCAL 1.0.0, OSCAL includes `type`, `version`, and `published`
properties as part of core OSCAL, eliminating the requirement to treat
this content as FedRAMP Extensions.

For policies, plans, user guides, and other documents, FedRAMP requires
the document's title, version, and publication date.

The following example demonstrates the inclusion of this content within
a resource.
{{< highlight xml "linenos=table" >}}
<back-matter>
  <resource uuid="3df7eeea-421b-459d-98cf-3d972bec610a">
    <title>Attachment or Document Title</title>
    <prop name="type" value="policy"/>
    <prop name="version" value="2.1"/>
    <prop name="published" value="2018-11-11T00:00:00Z"/>
    <base64>0000000</base64>
    <rlink href="./rel/path/doc.pdf" media-type="application/pdf"/>
    <rlink href="/absolute/path/doc.pdf" media-type="application/pdf"/>
  </resource>
</back-matter>
{{< /highlight >}}

## Citation and Attachment Conformity

IMPORTANT: As of 1.0.0, NIST includes many aspects of OSCAL previously
only possible with conformity tags. For citations and attachments,
FedRAMP now uses a combination of the resource "type" property and
link statements from relevant portions of the OSCAL content.

The following represents an example linking a policy directly to the
control it satisfies. (Legacy approach)

{{< highlight xml "linenos=table" >}}
<control-implementation>
  <implemented-requirement control-id="ac-1" uuid="[uuid-value]">
    <statement>
      <link href="#090ab379-2089-4830-b9fd-26d0729e22e9"
        rel="policy" />
    </statement>
  </implemented-requirement>
</control-implementation>
<back-matter>
  <resource uuid="090ab379-2089-4830-b9fd-26d0729e22e9">
    <title>Access Control and Identity Management Policy</title>
    <description>
    <p>Policy Document.</p>
    </description>
    <prop name="type" value="policy"/>
    <base64 filename="./documents/policies/sample_policy.pdf">QSBzYW1wbGUgcG9saWN5Lg==</base64>
  </resource>
</back-matter>
{{< /highlight >}}

The following represents an example linking a policy to the control it
satisfies via the preferred component-based approach.

{{< highlight xml "linenos=table" >}}
<system-implementation>
  <component uuid="f25e84bf-3e57-48c3-ac0b-7a567b3af79e" type="policy">
    <title>[EXAMPLE]Access Control and Identity Management Policy</title>
    <description>
        <p>[EXAMPLE]An example component representing a policy.</p>
    </description>
    <link href="#090ab379-2089-4830-b9fd-26d0729e22e9" rel="policy"/>
    <status state="operational"/>
  </component>
</system-implementation>

<control-implementation>
  <implemented-requirement control-id="ac-1" uuid="[uuid-value]">
    <statement statement-id="ac-1_smt.a"
        uuid="fb4d039a-dc4f-46f5-9c1f-f6343eaf69bc">
      <by-component
          component-uuid="f25e84bf-3e57-48c3-ac0b-7a567b3af79e">
        <description>
          <p>Describe how the statement is satisfied by this policy.</p>
        </description>
      </by-component>
    </statement>
  </implemented-requirement>
</control-implementation>

<back-matter>
  <resource uuid="090ab379-2089-4830-b9fd-26d0729e22e9">
    <title>Access Control and Identity Management Policy</title>
    <description>
    <p>Policy Document.</p>
    </description>
    <prop name="type">policy</prop>
    <base64 filename="./documents/policies/sample_policy.pdf">QSBzYW1wbGUgcG9saWN5Lg==</base64>
  </resource>
</back-matter>
{{< /highlight >}}
