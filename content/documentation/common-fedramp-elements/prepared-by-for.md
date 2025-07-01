---
title: Prepared By and Prepared For
weight: 303
---

# Prepared By and Prepared For

This section describes the FedRAMP OSCAL syntax for `prepared-by` and `prepared-for` flags.


## Prepared By - Third Party

The screen shot below shows the **Prepared by** section in the FedRAMP SSP template.

<br/>
{{< figure src="/img/content-figure-6.png" title="The 'Prepared by' section in the FedRAMP SSP template" alt="Screenshot of third party \"prepared by\" information in the FedRAMP template." >}}
<br/>

{{<callout>}}
***Important:*** FedRAMP SAP and SAR documents must always indicate the assessing organization, using the FedRAMP OSCAL `prepared-by` syntax
(see the **Representation** section below).
{{</callout>}}

The `responsible-party` assembly connects the `role` assembly to the `party` assembly and is required for compliance.

If a FedRAMP document was prepared by an organization other than an CSP, that organization's logo should also appear in `back-matter`.

<br/>

### Representation 

{{<callout>}}
*Notes:*
- For the logo, use `rlink` with a relative path or embed the logo as `base64`. FedRAMP prefers `base64` for images and diagrams.
- All images must have sufficient resolution to render all their details in HTML5.
{{</callout>}}

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        "roles": [
            {
                "id": "prepared-by",
                "title": "Prepared By",
                "description": "The organization that prepared the document. If developed in-house, this is the CSP itself."
            }
        ],
        "parties": [
            {
                "uuid": "d865602c-9d3b-49d7-8125-ce3f1ca04231",
                "type": "organization",
                "name": "Name of the person or the organization that prepared the document",
                "address": {
                    "type": "work",
                    "addr-lines": [
                        "Suite 0000",
                        "1234 Some Street"
                    ],
                    "city": "Haven",
                    "state": "ME",
                    "postal-code": "00000",
                    "country": "US"
                },
                "links": [
                    {
                        "href": "#891263fb-a5d6-44db-8d73-51bb8a9a3610",
                        "rel": "logo"
                    }
                ]
            }
        ],
        "responsible-parties": [
            {
                "role-id": "prepared-by",
                "party-uuids": ["d865602c-9d3b-49d7-8125-ce3f1ca04231"]
            }
        ]
    },

    "back-matter": {
        "resources": [
            {
                "uuid": "891263fb-a5d6-44db-8d73-51bb8a9a3610",
                "title": "Logo",
                "description": "Logo of the CSP or the organization that prepared the document.",
                "rlinks": [
                    {
                        "href": "./attachments/img/logo.png",
                        "media-type": "image/png"
                    }
                ],
                "base64": {
                    "filename": "logo.png",
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
metadata:
  roles:
  - id: prepared-by
    title: Prepared By
    description: The organization that prepared the document. If developed in-house, this is the CSP itself.
  parties:
  - uuid: d865602c-9d3b-49d7-8125-ce3f1ca04231
    type: organization
    name: Name of the person or the organization that prepared the document
    address:
      type: work
      addr-lines:
      - Suite 0000
      - 1234 Some Street
      city: Haven
      state: ME
      postal-code: '00000'
      country: US
    links:
    - href: #891263fb-a5d6-44db-8d73-51bb8a9a3610
      rel: logo
  responsible-parties:
  - role-id: prepared-by
    party-uuids:
    - d865602c-9d3b-49d7-8125-ce3f1ca04231

back-matter:
  resources:
  - uuid: 891263fb-a5d6-44db-8d73-51bb8a9a3610
    title: Logo
    description: Logo of the CSP or the organization that prepared the document.
    props:
    - name: type
      value: logo
    rlinks:
    - href: ./attachments/img/logo.png
    base64:
      filename: logo.png
      media-type: image/png
      value: 00000000
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <role id="prepared-by">
        <title>Prepared By</title>
        <description>
            <p>The organization that prepared the document. If developed in-house, this is the CSP itself.</p>
        </description>
    </role>
    <party uuid="d865602c-9d3b-49d7-8125-ce3f1ca04231" type="organization">
        <name>Name of the person or the organization that prepared the document</name>
        <address type="work">
            <addr-line>Suite 0000</addr-line>
            <addr-line>1234 Some Street</addr-line>
            <city>Haven</city>
            <state>ME</state>
            <postal-code>00000</postal-code>
            <country>US</country>
        </address>
        <link href="#891263fb-a5d6-44db-8d73-51bb8a9a3610" rel="logo"/>
    </party>
    <responsible-party role-id="prepared-by">
        <party-uuid>d865602c-9d3b-49d7-8125-ce3f1ca04231</party-uuid>
    </responsible-party>
</metadata>

<back-matter>
    <resource uuid="891263fb-a5d6-44db-8d73-51bb8a9a3610">
        <title>Logo</title>
        <description>
            <p>Logo of the CSP or the organization that prepared the document.</p>
        </description>
        <prop name="type" value="logo"/>
        <rlink href="./attachments/img/logo.png"/>
        <base64 filename="logo.png" media-type="image/png">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

<br/>
{{<callout>}}
**Required role ID** \
`prepared-by`
{{</callout>}}
<br/>

### XPath Queries

| Item                      | XPath&nbsp;query                                                                                                |
| ------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Preparer's&nbsp;name      | `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]/name`                |
| Preparer's street address | `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]/address/addr-line`   |
| Preparer's city           | `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]/address/city`        |
| Preparer's state          | `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]/address/state`       |
| Preparer's ZIP code       | `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]/address/postal-code` |
| Preparer's country        | `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]/address/country`     |


## Prepared By - CSP or Self&#8209;Prepared

This section is applicable when the CSP creates or updates its own SSP or POA&M content. 

{{<callout>}}
***Important:*** A CSP must never prepare the FedRAMP SAP and SAR documents.
{{</callout>}}

The `responsible-party` assembly connects the `role` assembly to the `party` assembly and is required for compliance.

The screen shot below shows the **Prepared by** section in the FedRAMP SSP template.

{{< figure src="/img/content-figure-6.png" title="The 'Prepared by' section in the FedRAMP SSP template" alt="Screenshot of CSP self \"prepared by\" information in the FedRAMP template." >}}


<br/>

### Representation

{{<callout>}}
*Notes:*
- For the logo, use `rlink` with a relative path or embed the logo as `base64`. FedRAMP prefers `base64` for images and diagrams.
- All images must have sufficient resolution to render all their details in HTML5.
{{</callout>}}

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        "roles": [
            {
                "id": "prepared-by",
                "title": "Prepared By",
                "description": "The organization that prepared the document. If developed in-house, this is the CSP itself."
            }
        ],
        "locations": [
            {
                "uuid": "60d612ba-1ab4-49ab-858b-d83b1bcbf006",
                "title": "Name of the organization that prepared the document"
                "address": {
                    "type": "work",
                    "addr-lines": [
                        "Suite 0000",
                        "1234 Some Street"
                    ],
                    "city": "Haven",
                    "state": "ME",
                    "postal-code": "00000",
                    "country": "US"
                }
            }
        ],
        "parties": [
            {
                "uuid": "d865602c-9d3b-49d7-8125-ce3f1ca04231",
                "type": "organization",
                "name": "Name of the person or the organization that prepared the document",
                "location-uuids": ["60d612ba-1ab4-49ab-858b-d83b1bcbf006"],
                "links": [
                    {
                        "href": "#891263fb-a5d6-44db-8d73-51bb8a9a3610",
                        "rel": "logo"
                    }
                ]
            }
        ],
        "responsible-parties": [
            {
                "role-id": "prepared-by",
                "party-uuids": ["d865602c-9d3b-49d7-8125-ce3f1ca04231"]
            }
        ]
    },

    "back-matter": {
        "resources": [
            {
                "uuid": "891263fb-a5d6-44db-8d73-51bb8a9a3610",
                "title": "Logo",
                "description": "Logo of the CSP or the organization that prepared the document.",
                "rlinks": [
                    {
                        "href": "./attachments/img/logo.png",
                        "media-type": "image/png"
                    }
                ],
                "base64": {
                    "filename": "logo.png",
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
metadata:
  roles:
  - id: prepared-by
    title: Prepared By
    description: The organization that prepared the document.
  locations:
  - uuid: 60d612ba-1ab4-49ab-858b-d83b1bcbf006
    title: Name of the organization that prepared the document
    address:
      type: work
      addr-lines:
      - Suite 0000
      - 1234 Some Street
      city: Haven
      state: ME
      postal-code: '00000'
      country: US 
  parties:
  - uuid: d865602c-9d3b-49d7-8125-ce3f1ca04231
    type: organization
    name: Name of the person or the organization that prepared the document
    location-uuids:
    - 60d612ba-1ab4-49ab-858b-d83b1bcbf006
    links:
    - href: #891263fb-a5d6-44db-8d73-51bb8a9a3610
      rel: logo
  responsible-parties:
  - role-id: prepared-by
    party-uuids:
    - d865602c-9d3b-49d7-8125-ce3f1ca04231

back-matter:
  resources:
  - uuid: 891263fb-a5d6-44db-8d73-51bb8a9a3610
    title: Logo
    description: Logo of the organization that prepared the document.
    props:
    - name: type
      value: logo
    rlinks:
    - href: ./attachments/img/logo.png
    base64:
      filename: logo.png
      media-type: image/png
      value: 00000000
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <role id="prepared-by">
        <title>Prepared By</title>
        <description>
            <p>The organization that prepared the document.</p>
        </description>
    </role>
    <location uuid="60d612ba-1ab4-49ab-858b-d83b1bcbf006">
        <title>Name of the organization that prepared the document</title>
        <address type="work">
            <addr-line>Suite 0000</addr-line>
            <addr-line>1234 Some Street</addr-line>
            <city>Haven</city>
            <state>ME</state>
            <postal-code>00000</postal-code>
            <country>US</country>
        </address>
    </location>
    <party uuid="d865602c-9d3b-49d7-8125-ce3f1ca04231" type="organization">
        <name>Name of the person or the organization that prepared the document</name>
        <link href="#891263fb-a5d6-44db-8d73-51bb8a9a3610" rel="logo"/>
        <location-uuid>60d612ba-1ab4-49ab-858b-d83b1bcbf006</location-uuid>
    </party>
    <responsible-party role-id="prepared-by">
        <party-uuid>d865602c-9d3b-49d7-8125-ce3f1ca04231</party-uuid>
    </responsible-party>
</metadata>

<back-matter>
    <resource uuid="891263fb-a5d6-44db-8d73-51bb8a9a3610">
        <title>Logo</title>
        <description>
            <p>Logo of the organization that prepared the document.</p>
        </description>
        <prop name="type" value="logo"/>
        <rlink href="./attachments/img/logo.png"/>
        <base64 filename="logo.png" media-type="image/png">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

<br/>
{{<callout>}}
**Required role ID** \
`prepared-by`
{{</callout>}}
<br/>

### XPath Queries
| Item                      | XPath&nbsp;query                                                                                                                                                                |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Preparer's&nbsp;name      | `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]/name`                                                                                |
| Preparer's street address | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]]/address/addr-line`   |
| Preparer's city           | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]]/address/city`        |
| Preparer's state          | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]]/address/state`       |
| Preparer's ZIP code       | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]]/address/postal-code` |
| Preparer's country        | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-by']/party-uuid]]/address/country`     |


## Prepared For - CSP

In the vast majority of cases, FedRAMP SSP, SAP, SAR, and POA&M documents are prepared for an CSP.

However, unforeseen circumstances may require another party to be named. For this reason, the `prepared-for` assemblies and CSPs have separately defined roles.

The screen shot below shows the **Prepared for** section in the FedRAMP SSP template.

{{< figure src="/img/content-figure-7.png" title="The 'Prepared for' section in the FedRAMP SSP template" alt="Screenshot of \"prepared for\" information in the FedRAMP template." >}}

<br/>

### Representation

{{<callout>}}
*Notes:*
- For the logo, use `rlink` with a relative path or embed the logo as `base64`. FedRAMP prefers `base64` for images and diagrams.
- All images must have sufficient resolution to render all their details in HTML5.
{{</callout>}}


{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "metadata": {
        "roles": [
            {
                "id": "prepared-for",
                "title": "Prepared For",
                "description": "The organization (typically, the CSP) for which the document was prepared."
            },
            {
                "id": "cloud-service-provider",
                "title": "Cloud Service Provider"
            }
        ],
        "locations": [
            {
                "uuid": "60d612ba-1ab4-49ab-858b-d83b1bcbf006",
                "title": "Name of the CSP",
                "address": {
                    "type": "work",
                    "addr-lines": [
                        "Suite 0000",
                        "1234 Some Street"
                    ],
                    "city": "Haven",
                    "state": "ME",
                    "postal-code": "00000",
                    "country": "US"
                }
            }
        ],
        "parties": [
            {
                "uuid": "d865602c-9d3b-49d7-8125-ce3f1ca04231",
                "type": "organization",
                "name": "Cloud Service Provider",
                "links": [
                    {
                        "href": "#891263fb-a5d6-44db-8d73-51bb8a9a3610",
                        "rel": "logo"
                    }
                ],
                "location-uuids": ["60d612ba-1ab4-49ab-858b-d83b1bcbf006"]
            }
        ],
        "responsible-parties": [
            {
                "role-id": "prepared-for",
                "party-uuids": ["d865602c-9d3b-49d7-8125-ce3f1ca04231"]
            }
        ]
    },

    "back-matter": {
        "resources": [
            {
                "uuid": "891263fb-a5d6-44db-8d73-51bb8a9a3610",
                "title": "Logo",
                "description": "Logo of the CSP.",
                "rlinks": [
                    {
                        "href": "./attachments/img/logo.png",
                        "media-type": "image/png"
                    }
                ],
                "base64": {
                    "filename": "logo.png",
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
metadata:
  roles:
  - id: prepared-for
    title: Prepared For
    description: The organization (typically, the CSP) for which the document was prepared.
  - id: cloud-service-provider
    title: Cloud Service Provider
  locations:
  - uuid: 60d612ba-1ab4-49ab-858b-d83b1bcbf006
    title: Name of the CSP
    address:
      type: work
      addr-lines:
      - Suite 0000
      - 1234 Some Street
      city: Haven
      state: ME
      postal-code: '00000'
      country: US 
  parties:
  - uuid: d865602c-9d3b-49d7-8125-ce3f1ca04231
    type: organization
    name: Cloud Service Provider
    links:
    - href: #891263fb-a5d6-44db-8d73-51bb8a9a3610
      rel: logo
    location-uuids:
    - 60d612ba-1ab4-49ab-858b-d83b1bcbf006
  responsible-parties:
  - role-id: prepared-for
    party-uuids:
    - d865602c-9d3b-49d7-8125-ce3f1ca04231

back-matter:
  resources:
  - uuid: 891263fb-a5d6-44db-8d73-51bb8a9a3610
    title: Logo
    description: Logo of the CSP.
    props:
    - name: type
      value: logo
    rlinks:
    - href: ./attachments/img/logo.png
    base64:
      filename: logo.png
      media-type: image/png
      value: 00000000
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<metadata>
    <role id="prepared-for">
        <title>Prepared For</title>
        <description>
            <p>The organization (typically, the CSP) for which the document was prepared.</p>
        </description>
    </role>
    <role id="cloud-service-provider">
        <title>Cloud Service Provider</title>
    </role>
    <location uuid="60d612ba-1ab4-49ab-858b-d83b1bcbf006">
        <title>Name of the CSP</title>
        <address type="work">
            <addr-line>Suite 0000</addr-line>
            <addr-line>1234 Some Street</addr-line>
            <city>Haven</city>
            <state>ME</state>
            <postal-code>00000</postal-code>
            <country>US</country>
        </address>
    </location>
    <party uuid="d865602c-9d3b-49d7-8125-ce3f1ca04231" type="organization">
        <name>Cloud Service Provider</name>
        <link href="#891263fb-a5d6-44db-8d73-51bb8a9a3610" rel="logo"/>
        <location-uuid>60d612ba-1ab4-49ab-858b-d83b1bcbf006</location-uuid>
    </party>
    <responsible-party role-id="prepared-for">
        <party-uuid>d865602c-9d3b-49d7-8125-ce3f1ca04231</party-uuid>
    </responsible-party>
</metadata>

<back-matter>
    <resource uuid="891263fb-a5d6-44db-8d73-51bb8a9a3610">
        <title>Logo</title>
        <description>
            <p>Logo of the CSP.</p>
        </description>
        <prop name="type" value="logo"/>
        <rlink href="./attachments/img/logo.png"/>
        <base64 filename="logo.png" media-type="image/png">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

<br/>
{{<callout>}}
**Required role ID** \
`prepared-for`
{{</callout>}}
<br/>

### XPath Queries

| Item                       | XPath&nbsp;query                                                                                                                                                                 |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Recipient's&nbsp;name      | `/*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-for']/party-uuid]/name`                                                                                |
| Recipient's street address | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-for']/party-uuid]]/address/addr-line`   |
| Recipient's city           | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-for']/party-uuid]]/address/city`        |
| Recipient's state          | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-for']/party-uuid]]/address/state`       |
| Recipient's ZIP code       | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-for']/party-uuid]]/address/postal-code` |
| Recipient's country        | `/*/metadata/location[@uuid=/*/metadata/party/location-uuid and /*/metadata/party[@uuid=/*/metadata/responsible-party[@role-id='prepared-for']/party-uuid]]/address/country`     |

