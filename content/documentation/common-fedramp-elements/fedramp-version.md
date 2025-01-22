---
title: FedRAMP Version
weight: 301
---

## FedRAMP Version

All documents in a digital authorization package for FedRAMP must specify the version that identifies which FedRAMP policies, guidance, and technical specifications its authors used during the creation and maintenance of the package.

FedRAMP maintains an official list of the versions on the [fedramp-automation releases](https://github.com/GSA/fedramp-automation/releases) page. Unless noted otherwise, a valid version is a [published tag name](https://github.com/GSA/fedramp-automation/tags).

##### Representation
{{< highlight xml "linenos=table, hl_lines=7" >}}
<metadata>
    <title>FedRAMP System Security Plan (SSP)</title>
    <published>2022-06-01T00:00:00.000Z</published>
    <last-modified>2023-03-03T00:00:00.000Z </last-modified>
    <version>0.0</version>
    <oscal-version>1.1.2</oscal-version>
    <prop name="fedramp-version" ns="http://fedramp.gov/ns/oscal" value="3.0.0-rc1"/>
</metadata>
{{</ highlight >}}

##### XPath Query
`/*/metadata/prop[@name='fedramp-version'][@ns='http://fedramp.gov/ns/oscal']/@value`
