---
title: Title Page
weight: 302
---

# Title Page

FedRAMP OSCAL templates include document title page. The screen shot below shows the title page of the FedRAMP SSP template.

{{< figure src="/img/content-figure-5.png" height="500px" title="FedRAMP SSP template title page" alt="Screenshot of the FedRAMP SSP template title page." >}}


## FedRAMP logo

The FedRAMP logo is a resource in the `back-matter` section of an OSCAL-based FedRAMP template. You can reference the logo, using the following XPath expression:

`/*/metadata/party[@uuid=../responsible-party[@role-id='fedramp-pmo']/party-uuid]/link[@rel='logo']/@href`

As with any `href` value, you may use either a relative or an absolute URI external to the OSCAL file. The `href` value may contain a URI fragment, 
pointing to a resource inside the OSCAL file itself or other OSCAL files.

If the XPath expression returns an `href` value that begins with a hashtag (for example, `#a2381e87-3d04-4108-a30b-b4d2f36d001f`), the value after 
the hashtag is the UUID of the FedRAMP logo resource (for example, `a2381e87-3d04-4108-a30b-b4d2f36d001f`). 

To locate the resource represented by the UUID value, use the following XPath expressions:

- `/*/back-matter/resource[@uuid='[UUID-value-returned-above]']/rlink/@href`

- `/*/back-matter/resource[@uuid='[UUID-value-returned-above]']/base64`


## Representation

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
    "system-security-plan": {
        "metadata": {
            "title": "FedRAMP System Security Plan (SSP)",
            "published": "2022-06-01T00:00:00.000Z",
            "last-modified": "2023-03-03T00:00:00.000Z ",
            "version": 0,
            "oscal-version": "1.1.2",
            "props": [
                {
                    "name": "fedramp-version",
                    "ns": "http://fedramp.gov/ns/oscal",
                    "value": "3.0.0-rc1"
                },
                {
                    "name": "marking",
                    "value": "cui"
                }
            ],
            "roles": [
                {
                    "id": "fedramp-pmo",
                    "title": "FedRAMP PMO",
                    "description": "Description"
                },
            ],
            // The "location" assemblies.
            "parties": [
                {
                    "uuid": "77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d",
                    "type": "organization",
                    "name": "FedRAMP: Program Management Office",
                    "short-name": "FedRAMP PMO",
                    "link": {
                        "href": "#a2381e87-3d04-4108-a30b-b4d2f36d001f",
                        "rel": "logo"
                    }
                },
            ],
            "responsible-parties": [
                {
                    "role-id": "fedramp-pmo",
                    "party-id": "77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d"
                },
            ],
        },
        // OSCAL file body.
        "back-matter": {
            "resources": [
                {
                    "uuid": "a2381e87-3d04-4108-a30b-b4d2f36d001f",
                    "description": {"p": "FedRAMP Logo"},
                    "prop": {
                        "name": "type",
                        "value": "logo"
                    },
                    "rlink": {"href": "https://www.fedramp.gov/assets/img/logo-main-fedramp.png"},
                    "base64": {
                        "filename": "FedRAMP_LOGO.png",
                        "#text": // Base64-encoded logo."00000000"
                    }
                }
            ]
        }
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  metadata:
    title: FedRAMP System Security Plan (SSP)
    published: '2022-06-01T00:00:00.000Z'
    last-modified: '2023-03-03T00:00:00.000Z '
    version: 0
    oscal-version: 1.1.2
    prop:
    - name: fedramp-version
      ns: http://fedramp.gov/ns/oscal
      value: 3.0.0-rc1
    - name: marking
      value: cui
    role:
      id: fedramp-pmo
      title: FedRAMP PMO
      description: "Description."
    # The "location" assemblies.
    party:
      uuid: 77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d
      type: organization
      name: 'FedRAMP: Program Management Office'
      short-name: FedRAMP PMO
      link:
        href: '#a2381e87-3d04-4108-a30b-b4d2f36d001f'
        rel: logo
    responsible-party:
      role-id: fedramp-pmo
      party-id: 77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d
  # OSCAL file body.
  back-matter:
    resource:
      uuid: a2381e87-3d04-4108-a30b-b4d2f36d001f
      description:
        p: FedRAMP Logo
      prop:
        name: type
        value: logo
      rlink:
        href: https://www.fedramp.gov/assets/img/logo-main-fedramp.png
      base64:
        filename: FedRAMP_LOGO.png
        '#text': # Base64-encoded logo."00000000"
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
    <metadata>
        <title>FedRAMP System Security Plan (SSP)</title>
        <published>2022-06-01T00:00:00.000Z</published>
        <last-modified>2023-03-03T00:00:00.000Z </last-modified>
        <version>0.0</version>
        <oscal-version>1.1.2</oscal-version>
        <prop name="fedramp-version" ns="http://fedramp.gov/ns/oscal" value="3.0.0-rc1"/>
        <prop name="marking" value="cui"/>
        <role id="fedramp-pmo">
            <title>FedRAMP PMO</title>
            <description><p>Description</p></description>
        </role>
        <!-- The "location" assemblies. -->
        <party uuid="77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d" type="organization">
            <name>FedRAMP: Program Management Office</name>
            <short-name>FedRAMP PMO</short-name>
            <link href="#a2381e87-3d04-4108-a30b-b4d2f36d001f" rel="logo"/>
        </party>
        <responsible-party role-id="fedramp-pmo">
            <party-id>77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d</party-id>
        </responsible-party>
    </metadata>
    <!-- OSCAL file body. -->
    <back-matter>
        <resource uuid="a2381e87-3d04-4108-a30b-b4d2f36d001f">
            <description><p>FedRAMP Logo</p></description>
            <prop name="type" value="logo" />
            <rlink href="https://www.fedramp.gov/assets/img/logo-main-fedramp.png"/>
            <base64 filename="FedRAMP_LOGO.png">
                <!-- Base64-encoded logo. -->00000000
            </base64>
        </resource>
    </back-matter>
</system-security-plan>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}

<br>
{{<callout>}}
FedRAMP Allowed Value\
Required Role ID: `fedramp-pmo`
{{</callout>}}
<br>

## XPath Queries
- Document Title: `/*/metadata/title`
- Document Published Version #: `/*/metadata/version`
- Document Published Date (will need to convert data for presentation): `/*/metadata/published`
- FedRAMP's Logo: `/*/metadata/party[@uuid=../responsible-party[@role-id='fedramp-pmo']/party-uuid]/link[@rel='logo']/@href`
- Document Sensitivity Label (If more than one, tools should present all): `/*/metadata/prop[@name="marking"]`
  {{<callout>}}
  *Note:* If needed, you may specify more than one Document Sensitivity Label (the `marking` name flag). The only required value is Controlled 
  Unclassified Information (the `cui` value flag). Your tools should display or notify users of all sensitivity markings.
  {{</callout>}}

