---
title: FedRAMP Version
weight: 301
---

# FedRAMP Version

All documents in a digital authorization package for FedRAMP must specify the version that identifies which FedRAMP policies, guidance, and 
technical specifications its authors used during the creation and maintenance of the package.

FedRAMP maintains an official list of the versions on the [fedramp-automation releases](https://github.com/GSA/fedramp-automation/releases) page. 
Unless noted otherwise, a valid version is a [published tag name](https://github.com/GSA/fedramp-automation/tags).


## Representation

{{< tabs JSON YAML XML>}}
{{% tab %}}
{{< highlight json "linenos=table, hl_lines=9-12" >}}
{
    "system-security-plan": {
        "metadata": {
            "title": "FedRAMP System Security Plan (SSP)",
            "published": "2024-12-31T23:59:59Z",
            "last-modified": "2025-01-08T04:18:29Z",
            "version": "fedramp-3.0.0rc1-oscal-1.1.2",
            "oscal-version": "1.1.3",
            "prop": {
                "name": "fedramp-version",
                "ns": "http://fedramp.gov/ns/oscal",
                "value": "fedramp-3.0.0rc1-oscal-1.1.2"
            }
        }
    }
}
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table, hl_lines=9-12" >}}
---
system-security-plan:
  metadata:
    title: FedRAMP System Security Plan (SSP)
    published: '2024-12-31T23:59:59Z'
    last-modified: '2025-01-08T04:18:29Z'
    version: 'fedramp-3.0.0rc1-oscal-1.1.2'
    oscal-version: 1.1.3
    prop:
      name: fedramp-version
      ns: http://fedramp.gov/ns/oscal
      value: fedramp-3.0.0rc1-oscal-1.1.2
{{</ highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table, hl_lines=8" >}}
<system-security-plan>
    <metadata>
        <title>FedRAMP System Security Plan (SSP)</title>
        <published>2024-12-31T23:59:59Z</published>
        <last-modified>2025-01-08T04:18:29Z</last-modified>
        <version>fedramp-3.0.0rc1-oscal-1.1.2</version>
        <oscal-version>1.1.3</oscal-version>
        <prop name="fedramp-version" ns="http://fedramp.gov/ns/oscal" value="fedramp-3.0.0rc1-oscal-1.1.2"/>
    </metadata>
</system-security-plan>
{{</ highlight >}}
{{% /tab %}}
{{</ tabs >}}


## XPath Query

`/*/metadata/prop[@name='fedramp-version'][@ns='http://fedramp.gov/ns/oscal']/@value`

