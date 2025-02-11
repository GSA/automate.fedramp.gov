---
title: Specifying the FedRAMP Baseline
weight: 330
---

## Specifying the FedRAMP Baseline

OSCAL is designed for traceability. Because of this, the SSP is designed
to be linked to the FedRAMP baseline. Rather than duplicating content
from the baseline, the SSP is intended to reference the baseline content
itself.

Use the import-profile field to specify an existing OSCAL-based SSP. The
href flag may include any valid uniform resource identifier (URI),
including a relative path, absolute path, or URI fragment.

#### SSP Import Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "import-profile": {
      "href": "path/to/profile.json"
    }
  }
}
// OR
{
  "system-security-plan": {
    "import-profile": {
      "href": "#96445439-6ce1-4e22-beae-aa72cfe173d0"
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
  <import-profile href="path/to/profile.xml" />
  <!-- OR -->
  <import-profile href="#96445439-6ce1-4e22-beae-aa72cfe173d0" />
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  import-profile:
    href: "path/to/profile.yaml"
# OR
---
system-security-plan:
  import-profile:
    href: "#96445439-6ce1-4e22-beae-aa72cfe173d0"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
  (SSP) URI to Baseline:
    /*/import-profile/@href
{{</ highlight >}}

If the value is a URI fragment, such as
#96445439-6ce1-4e22-beae-aa72cfe173d0, the value to the right of the
hashtag (#) is the universally unique identifier (UUID) value of a
resource in the SSP file's back-matter. Refer to the [*Attachments and Embedded Content*](/documentation/general-concepts/4-expressing-common-fedramp-template-elements-in-oscal/#attachments-and-embedded-content) section for guidance on handling.

#### SSP Back Matter Representation
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "back-matter": {
      "resource": {
        "uuid": "11111111-2222-4000-8000-001000000048",
        "title": "FedRAMP Moderate Baseline",
        "prop": {
          "name": "type",
          "value": "baseline"
        },
        "rlink": [
          {
            "media-type": "application/json",
            "href": "./profile.json"
          }
        ]
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
  <back-matter>
    <resource uuid="11111111-2222-4000-8000-001000000048">
      <title>FedRAMP Moderate Baseline</title>
      <prop name="type" value="baseline" />
      <rlink media-type="application/xml" href="./profile.xml" />
    </resource>
  </back-matter>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  back-matter:
    resource:
      uuid: "11111111-2222-4000-8000-001000000048"
      title: "FedRAMP Moderate Baseline"
      prop:
        name: "type"
        value: "baseline"
      rlink:
        - media-type: "application/yaml"
          href: "./profile.yaml"
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
  (SSP) Referenced OSCAL-based FedRAMP Baseline XML: 
    /*/back-matter/resource[@uuid='96445439-6ce1-4e22-beae-aa72cfe173d0'] /rlink[@media-type='application/xml']/@href
  OR JSON:
    /*/back-matter/resource[@uuid='96445439-6ce1-4e22-beae-aa72cfe173d0'] /rlink[@media-type='application/json']/@href
{{</ highlight >}}

Note: Cloud Service Providers must import [FedRAMP profiles or resolved profile catalogs](https://github.com/GSA/fedramp-automation/tree/master/dist/content/rev5/baselines).

## Resolution Resource Prop

FedRAMP will be implementing a separate set of automated SSP validation rules for the rev 5 OSCAL templates. To ensure FedRAMP initiates the appropriate validation rules when processing OSCAL SSPs, SSP authors should add a new prop called `resolution-resource` in the metadata section and include an associated back-matter resource as shown below:

#### SSP Resolution Resource
{{< tabs JSON XML YAML >}}

{{% tab %}}
{{< highlight json "linenos=table" >}}
{
  "system-security-plan": {
    "metadata": {
      "title": "FedRAMP System Security Plan (SSP)",
      "version": "fedramp-3.0.0rc1-oscal-1.1.2",
      "oscal-version": "1.1.3",
      "revisions": {
        "revision": [
          {}
        ]
      },
      "prop": [
        {
          "ns": "http://fedramp.gov/ns/oscal",
          "name": "resolution-resource",
          "value": "ace2963d-ecb4-4be5-bdd0-1f6fd7610f41"
        }
      ]
    },
    "back-matter": {
      "resource": {
        "uuid": "ace2963d-ecb4-4be5-bdd0-1f6fd7610f41",
        "title": "Resolution Resource",
        "prop": [
          {
            "name": "dataset",
            "class": "collection",
            "value": "Special Publication"
          },
          {
            "name": "dataset",
            "class": "name",
            "value": "800-53"
          },
          {
            "name": "dataset",
            "class": "version",
            "value": "5.0.2"
          },
          {
            "name": "dataset",
            "class": "organization",
            "value": "gov.nist.csrc"
          }
        ],
        "remarks": {
          "p": "This \"resolution resource\" is used by FedRAMP as a local, authoritative indicator of what version SSP (rev 4 or rev 5) this OSCAL document is for."
        }
      }
    }
  }
}
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
  <metadata>
    <title>FedRAMP System Security Plan (SSP)</title>
    <!-- cut -->
    <version>fedramp-3.0.0rc1-oscal-1.1.2</version>
    <oscal-version>1.1.3</oscal-version>
    <revisions>
      <revision>
        <!-- cut -->
      </revision>
    </revisions>
    <!-- New rev 5 prop -->
    <prop ns="http://fedramp.gov/ns/oscal" name="resolution-resource" value="ace2963d-ecb4-4be5-bdd0-1f6fd7610f41" />
  </metadata>
  <!-- cut -->
  <back-matter>
    <resource uuid="ace2963d-ecb4-4be5-bdd0-1f6fd7610f41">
      <title>Resolution Resource</title>
      <prop name="dataset" class="collection" value="Special Publication"/>
      <prop name="dataset" class="name" value="800-53"/>
      <prop name="dataset" class="version" value="5.0.2"/>
      <prop name="dataset" class="organization" value="gov.nist.csrc"/>
      <remarks>
        <p>This "resolution resource" is used by FedRAMP as a local, authoritative indicator of what version SSP (rev 4 or rev 5) this OSCAL document is for.</p>
      </remarks>
    </resource>
  </back-matter>
</system-security-plan>
{{< /highlight >}}
{{% /tab %}}

{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
  metadata:
    title: FedRAMP System Security Plan (SSP)
    version: fedramp-3.0.0rc1-oscal-1.1.2
    oscal-version: "1.1.3"
    revisions:
      revision:
        - {}  # cut
    prop:
      - ns: http://fedramp.gov/ns/oscal
        name: resolution-resource
        value: ace2963d-ecb4-4be5-bdd0-1f6fd7610f41
  back-matter:
    resource:
      uuid: ace2963d-ecb4-4be5-bdd0-1f6fd7610f41
      title: Resolution Resource
      prop:
        - name: dataset
          class: collection
          value: "Special Publication"
        - name: dataset
          class: name
          value: "800-53"
        - name: dataset
          class: version
          value: "5.0.2"
        - name: dataset
          class: organization
          value: gov.nist.csrc
      remarks:
        p: 'This "resolution resource" is used by FedRAMP as a local, authoritative indicator of what version SSP (rev 4 or rev 5) this OSCAL document is for.'
{{< /highlight >}}
{{% /tab %}}

{{< /tabs >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
  (SSP) UUID of “resolution-resource”:
    /*/metadata/prop[@name=”resolution-resource”]/@value
  (SSP)Target baseline version:
    /*/back-matter/resource[@uuid=”uuid-of-resolution-resource”]/prop[@name=”dataset” and @class=”version”]/@value
{{</ highlight >}}


If the `resolution-resource` prop is not specified in the metadata section of the SSP, FedRAMP will assume the SSP should be validated using the rev 5 validation rules. If the `resolution-resource` prop is present, FedRAMP will use the validation rules that correspond with the version specified in the back-matter resource.
