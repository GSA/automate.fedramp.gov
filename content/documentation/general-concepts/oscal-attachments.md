---
title: OSCAL Attachments
weight: 150
---

# Attachments in OSCAL Content

OSCAL attachments include the following artifacts:
- Logos
- Diagrams
- Policies
- Procedures
- Plans
- Evidence
- Interconnection security agreements (ISA).

In OSCAL, all citations and attachments are defined once at the end of the file as `resource` assemblies. Once defined, the citations and attachments are referenced throughout the OSCAL file as needed.

Each `resource` may be referenced from anywhere in the OSCAL file, using the resource UUID value.

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "back-matter": {
        "resources": [
            {
                "uuid": "11111111-2222-4000-8000-001000000002",
                "title": "Signed System Security Plan",
                "description": "SSP Signature",
                "props": [
                    {
                        "name": "type",
                        "value": "artifact",
                        "class": "signed-ssp"
                    }
                ],
                "rlinks": [
                    {
                        "href": "./attachments/signed-ssp.pdf",
                        "media-type": "application/pdf"
                    }
                ],
                "base64": {
                    "filename": "ssp.pdf",
                    "media-type": "application/pdf",
                    "value": "00000000"
                },
            },
        ]
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  back-matter:
    resources:
    - uuid: 11111111-2222-4000-8000-001000000002
      title: Signed System Security Plan
      description: SSP Signature
      props:
      - name: type
        value: artifact
        class: signed-ssp
      rlinks:
      - href: ./attachments/signed-ssp.pdf
        media-type: application/pdf
      base64:
        filename: ssp.pdf
        media-type: application/pdf
        value: '00000000'
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<back-matter>
    <resource uuid="11111111-2222-4000-8000-001000000002">
        <title>Signed System Security Plan</title>
        <description>
            <p>SSP Signature</p>
        </description>
        <prop name="type" class="signed-ssp" value="artifact"/>
        <rlink href="./attachments/signed-ssp.pdf" media-type="application/pdf"/>
        <base64 filename="ssp.pdf" media-type="application/pdf">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


The `media-type` flag should be present and must be set according to [Internet
Assigned Numbers Authority (IANA) Media
Type](http://www.iana.org/assignments/media-types/media-types.xhtml).


## Citations

Citations are for reference. The content is not included with the
authorization package.

Citations use an `rlink` field with an **absolute path** to content that is
accessible by FedRAMP and Agency reviewers from government systems.

Citation examples include links to
- Publicly available laws (for example, FISMA), and
- Applicable standards (for example, NIST SP 800 series documents).


## Attachments

Unlike citations, attachments are included with the authorization
package when submitted.

Each attachment should have a title, but it is not required. Tools may either embed an attachment using the `base64` field, or point to an attachment using an `rlink` field.

If no base64 embedded content is
present, at least one `rlink` field must exist, containing one of the following path types:
- An absolute path to content that is accessible by FedRAMP and Agency reviewers from government systems
- A relative path

If a relative path is used, the attachment must be delivered with the
OSCAL file and packaged such that the attachment exists in the correct
relative location.

Examples include the following artifacts:
- The CSP or 3PAO logo 
- Authorization boundary diagrams
- Policies
- Process
- Plans
- Raw scanner output
- Assessment evidence
- POA&M deviation request evidence

Tools should embed (`base64`) or link to (`rlink`) an attachment once as a
`resource` in `back-matter`, then use URI fragments to reference the
attachment anyplace it is needed within the body of the OSCAL file, as
described in the [Assigning Identifiers](/documentation/general-concepts/working-with-identifiers/#assigning-identifiers) and [Working With href Flags](/documentation/general-concepts/oscal-data-types/#working-with-href-flags) sections.

For example, a policy document that satisfies several control families
is attached as a `resource` in the `back-matter`, with a UUID of
`11111111-2222-4000-8000-001000000052`. Each control satisfied by that
policy links to the policy, using the `#11111111-2222-4000-8000-001000000052` URI fragment:

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "links": [
        {
            "href": "#11111111-2222-4000-8000-001000000052",
            "rel": "policy"
        }
    ],
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  links:
  - href: '#11111111-2222-4000-8000-001000000052'
    rel: policy
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
  <link href="#11111111-2222-4000-8000-001000000052" rel="policy"/>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


As described in the [Working With href Flags](/documentation/general-concepts/oscal-data-types/#working-with-href-flags) sections, when a tool
identifies a URI fragment in an `href` value, the leading hashtag (`#`) must
be dropped and the remaining value is expected to reference an OSCAL-addressable ID or UUID. Such ID or UUID may reside either in the OSCAL file
itself or inside other OSCAL documents linked using the `import` field.

The policy's title, version, publication date and other details are
defined once in the resource and are displayed anywhere the policy is
referenced. If a newer policy is published, only one resource
needs to be updated.

If the policy's location is identified as `./policies/doc.pdf`, the
OSCAL file and the doc.pdf file should be delivered together and
packaged so that the folder containing the OSCAL file includes the 
`policies` sub-folder, containing the `doc.pdf` file.

When using attachments with relative paths, consider using a technology
such as a ZIP archive to package and deliver attachments, while
maintaining their relative position to the OSCAL file.


## Including Multiple rlink and base64 Fields

A `resource` assembly may contain
- No `rlink` fields
- Nor `base64` fields
- One or more `rlink` fields
- One or more base64-encoded data fields within the OSCAL file
- Any combination of `rlink` and `base64` fields

OSCAL allows multiple `rlink` and `base64` fields to exist inside the same `resource`. This provides the flexibility to identify multiple locations or multiple formats of the same resource.

The table below demonstrates some examples of using multiple `rlink` and `base64` fields contained in the same `resource` assembly.

| Field&nbsp;type                   | Description |
| --------------------------------- | ----------- |
| Multiple&nbsp;locations           | Multiple `rlink` fields allow an OSCAL tool to include one `rlink` field with an *absolute* path to the authoritative location of a policy document within the CSP's intranet. <br><br> The same `resource` could have a second `rlink` field with a *relative* path to the same policy document. Having both allows the CSP to maintain the link to the authoritative location of the policy when working with the OSCAL file internally, while allowing a cached, local copy to travel with the OSCAL file when delivered to FedRAMP for review. |
| Multiple&nbsp;quality&nbsp;levels | Multiple `rlink` or `base64` fields allow both low-resolution and high-resolution versions of the same image, which is sometimes used to boost the performance of web-based applications. |
| Multiple&nbsp;formats             | Multiple `rlink` or `base64` fields allow a portable network graphic (PNG) version of an image to be provided for presentation by a web application and a more detailed portable document format (PDF) version of the same image for download. |


## Handling Multiple rlink and base64 Fields

OSCAL `resource` assemblies are designed to be flexible and offer
developers the flexibility to implement handling of multiple `rlink` and
`base64` fields on a case-by-case basis.

This section describes how FedRAMP processes multiple `rlink` and `base64` fields, which will be used by default unless a compelling circumstance requires otherwise.

FedRAMP accepts both `base64` and `rlink` option content for diagrams and
graphics. FedRAMP prefers that documents (for example, policies and plans) are
attached using `rlink` fields and relative paths.

If a tool is designed to work interactively with a user, the tool
developer should consider designing the solution to make intelligent choices
based on context and circumstances where practical. The tool could also
present valid choices to users, where the correct choice is ambiguous
to the tool.

When more than one `rlink` and/or `base64` field is present in a resource,
FedRAMP's automated processing tools will attempt to find valid content,
using the following priority, unless specified otherwise:

1.  First look inside the `base64` fields:

    &emsp;&emsp;a.  Start with the first `base64` field in the `resource` assembly.

    &emsp;&emsp;b.  Check each `base64` field in the sequence where they appear in the `resource` assembly.

    &emsp;&emsp;c.  If valid content is found, stop looking and use that content.

    &emsp;&emsp;d.  If no valid content is found after checking all `base64` fields in the resource, proceed to step #2.

2.  If no valid `base64` content is found, look inside the `rlink` fields:

    &emsp;&emsp;a.  Start with the first `rlink` field in the `resource` assembly.

    &emsp;&emsp;b.  Check each `rlink` field in the sequence in which they appear in the `resource`.

    &emsp;&emsp;c.  If valid content is found, stop looking and use the content.

    &emsp;&emsp;d.  If no valid content is found after checking all `rlink` fields, treat the resource as invalid, which may include raising a warning or an error message.


## Citation and Attachment Details

{{<callout>}}
_IMPORTANT:_ As of 1.0.0, OSCAL includes `type`, `version`, and `published`
properties as part of core OSCAL, eliminating the requirement to treat
this content as FedRAMP Extensions.
{{</callout>}}

For policies, plans, user guides, and other documents, FedRAMP requires the following document details:
1. Title
1. Version
1. Publication date

This example demonstrates the inclusion of these document details in a `resource`.

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "back-matter": {
        "resources": [
            {
                "uuid": "11111111-2222-4000-8000-001000000005",
                "title": "Access Control and Identity Management Policy",
                "description": "A single policy that addresses both the AC and IA families.",
                "props": [
                    {
                        "name": "type",
                        "value": "policy"
                    },
                    {
                        "name": "published",
                        "value": "2025-01-01T00:00:00Z"
                    },
                    {
                        "name": "version",
                        "value": "1.2"
                    }
                ],
                "rlinks": [
                    {
                        "href": "./attachments/policies/sample_AC_and_IA_policy.pdf",
                        "media-type": "application/pdf"
                    }
                ],
                "base64": {
                    "filename": "sample_AC_and_IA_policy.pdf",
                    "media-type": "application/pdf",
                    "value": "00000000"
                },
            },
        ],
    },
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  back-matter:
    resources:
    - uuid: 11111111-2222-4000-8000-001000000005
      title: Access Control and Identity Management Policy
      description: A single policy that addresses both the AC and IA families.
      props:
      - name: type
        value: policy
      - name: published
        value: '2025-01-01T00:00:00Z'
      - name: version
        value: '1.2'
      rlinks:
      - href: ./attachments/policies/sample_AC_and_IA_policy.pdf
        media-type: application/pdf
      base64:
        filename: sample_AC_and_IA_policy.pdf
        media-type: application/pdf
        value: '00000000'
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<back-matter>
    <resource uuid="11111111-2222-4000-8000-001000000005">
        <title>Access Control and Identity Management Policy</title>
        <description>
            <p>A single policy that addresses both the AC and IA families.</p>
        </description>
        <prop name="type" value="policy"/>
        <prop name="published" value="2025-01-01T00:00:00Z"/>
        <prop name="version" value="1.2"/>
        <rlink media-type="application/pdf" href="./attachments/policies/sample_AC_and_IA_policy.pdf"/>
        <base64 filename="sample_AC_and_IA_policy.pdf" media-type="application/pdf">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


## Linking Attachments in Components

For citations and attachments, FedRAMP uses a combination of the resource `type` property and link statements from relevant portions of the OSCAL content.

The example below demonstrates the component-based approach for linking the policy to the control it satisfies.

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "system-implementation": {
        "components": [
            {
                "uuid": "11111111-2222-4000-8000-009000000000",
                "type": "policy",
                "title": "Access Control and Identity Management Policy",
                "description": "An example component representing a policy.",
                "links": [
                    {
                        "href": "#11111111-2222-4000-8000-001000000005",
                        "rel": "policy"
                    }
                ],
                "status": {"state": "operational"},
            },
        ],
    },

    "control-implementation": {
        "implemented-requirements": [
            {
                "uuid": "11111111-2222-4000-8000-012000010000",
                "control-id": "ac-1",
                "statements": [
                    {
                        "statement-id": "ac-1_smt.a",
                        "uuid": "11111111-2222-4000-8000-012000010100",
                        "by-components": [
                            {
                                "component-uuid": "11111111-2222-4000-8000-009000000000",
                                "uuid": "11111111-2222-4000-8000-012000010102",
                                "description": "Describe how this policy satisfies part a."
                            },
                        ],
                    },
                ],
            },
        ],
    },

    "back-matter": {
        "resources": [
            {
                "uuid": "11111111-2222-4000-8000-001000000005",
                "title": "Access Control and Identity Management Policy",
                "description": "A single policy that addresses both the AC and IA families.",
                "props": [
                    {
                        "name": "type",
                        "value": "policy"
                    },
                ],
                "base64": {
                    "filename": "sample_AC_and_IA_policy.pdf",
                    "media-type": "application/pdf",
                    "value": "00000000"
                },
            },
        ],
    },
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
  system-implementation:
    components:
    - uuid: 11111111-2222-4000-8000-009000000000
      type: policy
      title: Access Control and Identity Management Policy
      description: An example component representing a policy.
      links:
      - href: '#11111111-2222-4000-8000-001000000005'
        rel: policy
      status:
        state: operational

  control-implementation:
    implemented-requirements:
    - uuid: 11111111-2222-4000-8000-012000010000
      control-id: ac-1
      statements:
      - statement-id: ac-1_smt.a
        uuid: 11111111-2222-4000-8000-012000010100
        by-components:
        - component-uuid: 11111111-2222-4000-8000-009000000000
          uuid: 11111111-2222-4000-8000-012000010102
          description:
            Describe how this policy satisfies part a.

  back-matter:
    resources:
    - uuid: 11111111-2222-4000-8000-001000000005
      title: Access Control and Identity Management Policy
      description: A single policy that addresses both the AC and IA families.
      props:
      - name: type
        value: policy
      base64:
        filename: sample_AC_and_IA_policy.pdf
        media-type: application/pdf
        value: '00000000'
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-implementation>
    <component uuid="11111111-2222-4000-8000-009000000000" type="policy">
        <title>Access Control and Identity Management Policy</title>
        <description>
            <p>An example component representing a policy.</p>
        </description>
        <link href="#11111111-2222-4000-8000-001000000005" rel="policy"/>
        <status state="operational"/>
    </component>
</system-implementation>

<control-implementation>
    <implemented-requirement control-id="ac-1" uuid="11111111-2222-4000-8000-012000010000">
        <statement statement-id="ac-1_smt.a" uuid="11111111-2222-4000-8000-012000010100">
            <by-component component-uuid="11111111-2222-4000-8000-009000000000" uuid="11111111-2222-4000-8000-012000010102">
                <description>
                    <p>Describe how this policy satisfies part &quot;a&quot;.</p>
                </description>
            </by-component>
        </statement>
    </implemented-requirement>
</control-implementation>

<back-matter>
    <resource uuid="11111111-2222-4000-8000-001000000005">
        <title>Access Control and Identity Management Policy</title>
        <description>
            <p>A single policy that addresses both the AC and IA families.</p>
        </description>
        <prop name="type" value="policy"/>
        <base64 filename="sample_AC_and_IA_policy.pdf" media-type="application/pdf">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}



