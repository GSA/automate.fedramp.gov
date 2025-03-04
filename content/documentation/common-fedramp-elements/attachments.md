---
title: Attachments
weight: 320
---
# Attachments to FedRAMP Content

Attachments, such as policies and procedures, provide additional information, supplementing FedRAMP requirements.  

Tools creating OSCAL content should
- For all `rlink` and `base64` fields, include the `media-type` flag 
- For all `base64` fields, include the `filename` flag

Tools should process `rlink` and `base64` content with or without these fields.
When present, the `rlink` and `base64` fields should be used during validation or rendering of the linked or embedded content.


## FedRAMP Standard Attachments

FedRAMP standard attachments refer to laws and regulations.

The FedRAMP MS Word-based SSP, SAP and SAR templates include links to the FedRAMP **Laws and Regulations** file.
Laws and regulations are specified in the OSCAL-based FedRAMP templates as resources.

Linking to the FedRAMP citations' file is established in the back-matter `resource` field with the `type` property field's `class` flag
set to `fedramp-citations`. See JSON, YAML, and XML examples in the **Representation** section below.


### Representation

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
"metadata": {
    "parties": [
        {
            "uuid": "6221a18b-06d0-4f0c-9606-8a1710cb44b2",
            "type": "organization",
            "name": "Federal Risk and Authorization Management Program: Program Management Office",
            "short-name": "FedRAMP PMO",
            "links": [
                {
                    "href": "#8b7b9208-767b-4c19-876a-06d9af3ab66f",
                    "rel": "reference"
                }
            ]
        }
    ]
},

"back-matter": {
    "resources": [
        {
            "uuid": "8b7b9208-767b-4c19-876a-06d9af3ab66f",
            "title": "FedRAMP Applicable Laws and Regulations",
            "props": [
                {
                    "name": "type",
                    "class": "fedramp-citations",
                    "value": "citation"
                }
            ],
            "rlinks": [
                {"href": "https://www.fedramp.gov/assets/resources/templates/FedRAMP-Laws-Regulations-Standards-and-Guidance-Reference.xlsx"}
            ]
        }
    ]
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
metadata:
  parties:
  - uuid: 6221a18b-06d0-4f0c-9606-8a1710cb44b2
    type: organization
    name: 'Federal Risk and Authorization Management Program: Program Management Office'
    short-name: 'FedRAMP PMO'
    links:
    - href: '#8b7b9208-767b-4c19-876a-06d9af3ab66f'
      rel: reference

back-matter:
  resources:
  - uuid: 8b7b9208-767b-4c19-876a-06d9af3ab66f
    title: 'FedRAMP Applicable Laws and Regulations'
    props:
    - name: type
      class: fedramp-citations
      value: citation
    rlinks:
    - href: https://www.fedramp.gov/assets/resources/templates/FedRAMP-Laws-Regulations-Standards-and-Guidance-Reference.xlsx
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <party uuid="6221a18b-06d0-4f0c-9606-8a1710cb44b2" type="organization">
       <name>Federal Risk and Authorization Management Program: Program Management Office</name>
       <short-name>FedRAMP PMO</short-name>
       <link href="#8b7b9208-767b-4c19-876a-06d9af3ab66f" rel="reference"/>
    </party>  
<metadata>

<back-matter>
    <resource uuid="8b7b9208-767b-4c19-876a-06d9af3ab66f">
        <title>FedRAMP Applicable Laws and Regulations</title>
        <prop name="type" class="fedramp-citations" value="citation"/>
        <rlink href="https://www.fedramp.gov/assets/resources/templates/FedRAMP-Laws-Regulations-Standards-and-Guidance-Reference.xlsx"/>
    </resource>
</back-matter>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


### XPath Queries

| Item                                    | XPath&nbsp;query                                                                           |
| --------------------------------------- | ------------------------------------------------------------------------------------------ |
| FedRAMP Applicable Laws and Regulations | `/*/back-matter/resource/prop[@name="type"][string(.)="fedramp-citations"]/../rlink/@href` |


## Additional Laws, Regulations, Standards, and Guidance

The screen shot below shows the **Laws and Regulations** section in the FedRAMP SSP template.

{{< figure src="/img/content-figure-11.png" title="Laws and regulations in the FedRAMP SSP template" alt="Screenshot of laws, regulations, standards, and guidance information in the FedRAMP template." >}}

Additional citations must be represented as `resource` assemblies with one `resource` assembly per citation. 
This applies to applicable laws, regulations, standards, or guidance beyond FedRAMP's predefined set.

Each citation must have a `type` field defined. The value of the `type` field must be set to one of the following values as applicable:
- `law`
- `regulation`
- `standard`
- `guidance` 

FedRAMP tools use the `type` field to differentiate these `resource` assemblies.

{{<callout>}}
*Note:* You may define more than one `type` field.
{{</callout>}}


### Representation

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "back-matter": {
        "resources": [
            {
                "uuid": "19f41902-192e-4611-ba5f-0b4c50166232",
                "title": "Title of Cited Law",
                "props": [
                    {
                        "name": "type",
                        "value": "law"
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
                "document-ids": [
                    {
                        "scheme": "https://www.doi.org/",
                        "identifier": "Identification Number"
                    }
                ],
                "rlinks": [
                    {"href": "https://example.com/path/to/document.pdf"}
                ],
                "base64": {
                    "filename": "document.pdf",
                    "media-type": "application/pdf",
                    "value": "00000000"
                },
            },
            {
                "uuid": "a8a0cc81-800f-479f-93d3-8b8743d9b98d",
                "title": "Title of Cited Regulation",
                "props": [
                    {
                        "name": "type",
                        "value": "regulation"
                    },
                    {
                        "name": "published",
                        "value": "2025-02-15T00:00:00Z"
                    },
                    {
                        "name": "version",
                        "value": "2.0"
                    }
                ],
                "document-ids": [
                    {
                        "scheme": "https://www.doi.org/",
                        "identifier": "Identification Number"
                    }
                ],
                "rlinks": [
                    {"href": "https://example.com/path/to/document.pdf"}
                ],
                "base64": {
                    "filename": "document.pdf",
                    "media-type": "application/pdf",
                    "value": "00000000"
                }
            }
        ]
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
back-matter:
  resources:
  - uuid: 19f41902-192e-4611-ba5f-0b4c50166232
    title: Title of Cited Law
    props:
    - name: type
      value: law
    - name: published
      value: '2025-01-01T00:00:00Z'
    - name: version
      value: 1.2
    document-ids:
    - scheme: https://www.doi.org/
      identifier: Identification Number
    rlinks:
    - href: https://example.com/path/to/document.pdf
    base64:
      filename: document.pdf
      media-type: application/pdf
      value: '00000000'
  - uuid: a8a0cc81-800f-479f-93d3-8b8743d9b98d
    title: Title of Cited Regulation
    props:
    - name: type
      value: regulation
    - name: published
      value: '2025-02-15T00:00:00Z'
    - name: version
      value: 2.0
    document-ids:
    - scheme: https://www.doi.org/
      identifier: Identification Number
    rlinks:
    - href: https://example.com/path/to/document.pdf
    base64:
      filename: document.pdf
      media-type: application/pdf
      value: '00000000'
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<back-matter>
    <resource uuid="19f41902-192e-4611-ba5f-0b4c50166232">
        <title>Title of Cited Law</title>
        <prop name="type" value="law"/>
        <prop name="published" value="2025-01-01T00:00:00Z"/>
        <prop name="version" value="1.2"/>
        <document-id scheme="https://www.doi.org/">Identification Number</document-id>
        <rlink href="https://example.com/path/to/document.pdf"/>
        <base64 filename="document.pdf" media-type="application/pdf">00000000</base64>
    </resource>
    <resource uuid="a8a0cc81-800f-479f-93d3-8b8743d9b98d">
        <title>Title of Cited Regulation</title>
        <prop name="type" value="regulation"/>
        <prop name="published" value="2025-02-15T00:00:00Z"/>
        <prop name="version" value="2.0"/>
        <document-id scheme="https://www.doi.org/">Identification Number</document-id>
        <rlink href="https://example.com/path/to/document.pdf"/>
        <base64 filename="document.pdf" media-type="application/pdf">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


### XPath Queries

{{<callout>}}
*Note:* In XPath queries below
- For consecutive items, replace the XPath predicate `[1]` with `[2]`, `[3]`, and so on.
- For standards and guidance, replace
    - `law` with `standard`, and
    -  `regulation` with `guidance`.
{{</callout>}}

| Item                                  | XPath&nbsp;query                                                                                                                |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Total number of laws and regulations  | `count(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])`                            |
| Identification number                 | `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../doc-id`                    |
| Title                                 | `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../title`                     |
| Date                                  | `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../prop[@name="publication"]` |
| Link                                  | `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../rlink/@href`               |


## Attachments and Embedded Content

There are several attachments in a classic
FedRAMP MS Word based SSP, SAP, SAR document or Deviation Request (DR)
form. Some lend well to machine-readable format, while others do not.

The attachments that are easily modeled in machine-readable format are typically addressed in the OSCAL syntax. Other documents (for example, policies,
procedures, plans, guides, and rules of behavior) are also treated as attachments in OSCAL.

Diagrams and images that normally appear in documents (for example, the authorization boundary diagram) are attached in the `back-matter` assembly and referenced from the body of an OSCAL file.

The screen shot below shows the list of required attachments in the FedRAMP SSP template.

{{< figure src="/img/content-figure-12.png" title="Attachments and embedded content in the FedRAMP SSP template" alt="Screenshot of attachments and embedded content information in the FedRAMP template." >}}


### Representation

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "back-matter": {
        "resources": [
            {
                "uuid": "99ed6b22-42c1-4ba4-9110-2b0c619767b6",
                "title": "Procedure Title",
                "props": [
                    {
                        "name": "type",
                        "value": "procedure"
                    },
                    {
                        "name": "published",
                        "value": "2025-01-01T00:00:00Z"
                    },
                    {
                        "name": "version",
                        "value": "2.0"
                    }
                ],
                "rlinks": [
                    {
                        "media-type": "application/pdf",
                        "href": "./attachments/procedures/sample_procedure.pdf"
                    }
                ],
                "base64": {
                    "filename": "sample_procedure.pdf",
                    "media-type": "application/pdf",
                    "value": "00000000"
                }
            },
            {
                "uuid": "11111111-2222-4000-8000-001000000054",
                "title": "Boundary Diagram",
                "description": "The primary authorization boundary diagram.",
                "props": [
                    {
                        "name": "type",
                        "value": "image",
                        "class": "authorization-boundary"
                    }
                ],
                "rlinks": [
                    {"href": "./attachments/diagrams/boundary.png"}
                ],
                "base64": {
                    "filename": "boundary.png",
                    "media-type": "image/png",
                    "value": "00000000"
                }
            }
        ]
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
back-matter:
  resources:
    - uuid: 99ed6b22-42c1-4ba4-9110-2b0c619767b6
      title: Procedure Title
      props:
      - name: type
        value: procedure
      - name: published
        value: '2025-01-01T00:00:00Z'
      - name: version
        value: 2.0
      rlinks:
      - media-type: application/pdf
        href: ./attachments/procedures/sample_procedure.pdf
      base64:
        filename: sample_procedure.pdf
        media-type: application/pdf
        value: '00000000'
  - uuid: bae3aee5-5786-431f-aae0-6f0644c60999
      title: Boundary Diagram
      description: The primary authorization boundary diagram.
      props:
      - name: type
        value: image
        class: authorization-boundary
      rlinks:
      - href: ./attachments/diagrams/boundary.png
      base64:
        filename: boundary.png
        media-type: image/png
        value: '00000000'
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<back-matter>
    <resource uuid="99ed6b22-42c1-4ba4-9110-2b0c619767b6">
        <title>Procedure Title</title>
        <prop name="type" value="procedure"/>
        <prop name="published" value="2025-01-01T00:00:00Z"/>
        <prop name="version" value="2.0"/>
        <rlink media-type="application/pdf" href="./attachments/procedures/sample_procedure.pdf"/>
        <base64 filename="sample_procedure.pdf" media-type="application/pdf">00000000</base64>
    </resource>
    <resource uuid="bae3aee5-5786-431f-aae0-6f0644c60999">
        <title>Boundary Diagram</title>
        <description>
            <p>The primary authorization boundary diagram.</p>
        </description>
        <prop name="type" value="image" class="authorization-boundary"/>
        <rlink href="./attachments/diagrams/boundary.png"/>
        <base64 filename="boundary.png" media-type="image/png">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


### XPath Queries

{{<callout>}}
*Note:* For each attachment type, replace `policy` with `plan`, `rob`, and so on. 
{{</callout>}}


| Item                                     | XPath&nbsp;query                                                                                                                |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Embedded base64-encoded PIA attachment   | `/*/back-matter/resource/prop[@name='type'][string(.)='privacy-impact-assessment']/../base64` |
| Relative link of a PIA attachment        | `/*/back-matter/resource/prop[@name=type][string(.)='privacy-impact-assessment']/../rlink/@href` |
| PIA publication date                     | `/*/back-matter/resource/prop[@name=type][string(.)='privacy-impact-assessment']/../prop[@name="publication"]` |




