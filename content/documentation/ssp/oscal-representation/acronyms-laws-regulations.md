---
title: Acronyms, Laws and Regulations
weight: 343
---
# Acronyms, Laws and Regulations

## Acronyms
The FedRAMP PMO no longer maintains/publishes the FedRAMP Master Acronym and Glossary. As such, there is no requirement for reference to this document.

## FedRAMP Citations

The FedRAMP MS Word-based SSP, SAP and SAR templates included links to the FedRAMP Laws and Regulations file.

These are already included in the OSCAL-based FedRAMP templates as resources. The `resource` linking to the FedRAMP citations file is identified with links from the property type, "fedramp-citations". 

The `fedramp-citations` resource MUST have:
- title
- a `type` property with an `@value` attribute set to "citation" and an `@class` attribute set to "fedramp-citations"
- an rlink with an `@href` that links to the appropriate [artifact](https://www.fedramp.gov/assets/resources/templates/FedRAMP-Laws-Regulations-Standards-and-Guidance-Reference.xlsx) on fedramp.gov. 

#### Representation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
 "system-security-plan" : {
   "system-characteristics" : { },
   "uuid" : "12345678-1234-4321-8765-123456789012",
   "metadata" : {
     "parties" : [ {
       "name" : "FedRAMP: Program Management Office",
       "uuid" : "77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d",
       "short-name" : "FedRAMP PMO",
       "links" : [ {
         "href" : "#985475ee-d4d6-4581-8fdf-d84d3d8caa48",
         "rel" : "reference"
       }, {
         "href" : "#1a23a771-d481-4594-9a1a-71d584fa4123",
         "rel" : "reference"
       } ],
       "type" : "organization"
     } ]
   },
   "back-matter" : {
     "resources" : [ {
       "props" : [ {
         "name" : "type",
         "ns" : "http://fedramp.gov/ns/oscal",
         "value" : "fedramp-citations"
       } ],
       "uuid" : "985475ee-d4d6-4581-8fdf-d84d3d8caa48",
       "rlinks" : [ {
         "href" : "https://-cut-/SSP-A12-FedRAMP-Laws-and-Regulations-Template.xlsx"
       } ],
       "title" : "FedRAMP Applicable Laws and Regulations"
     } ]
   }
 }
}
{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
   <metadata>
   <!-- cut -->
       <party uuid="77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d" type="organization">
           <name>FedRAMP: Program Management Office</name>
           <short-name>FedRAMP PMO</short-name>
           <link href="#985475ee-d4d6-4581-8fdf-d84d3d8caa48" rel="reference" />
           <link href="#1a23a771-d481-4594-9a1a-71d584fa4123" rel="reference" />
       </party>
   </metadata>
   <system-characteristics>
       <!-- cut -->
   </system-characteristics>
   <back-matter>
       <resource uuid="985475ee-d4d6-4581-8fdf-d84d3d8caa48">
           <title>FedRAMP Applicable Laws and Regulations</title>
           <prop ns="http://fedramp.gov/ns/oscal" name="type" value="fedramp-citations"/>
           <rlink href="https://-cut-/SSP-A12-FedRAMP-Laws-and-Regulations-Template.xlsx"/>
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
   resources:
   - rlinks:
     - href: https://-cut-/SSP-A12-FedRAMP-Laws-and-Regulations-Template.xlsx
     title: FedRAMP Applicable Laws and Regulations
     props:
     - name: type
       ns: http://fedramp.gov/ns/oscal
       value: fedramp-citations
     uuid: 985475ee-d4d6-4581-8fdf-d84d3d8caa48
 system-characteristics: {}
 uuid: 12345678-1234-4321-8765-123456789012
 metadata:
   parties:
   - name: "FedRAMP: Program Management Office"
     uuid: 77e0e2c8-2560-4fe9-ac78-c3ff4ffc9f6d
     short-name: FedRAMP PMO
     links:
     - rel: reference
       href: "#985475ee-d4d6-4581-8fdf-d84d3d8caa48"
     - rel: reference
       href: "#1a23a771-d481-4594-9a1a-71d584fa4123"
     type: organization
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
Link to FedRAMP Applicable Laws and Regulations:
    /*/back-matter/resource/prop[@name='type'][string(.)='fedramp-citations']/../rlink/@href
Link to FedRAMP Acronyms and Glossary:
    /*/back-matter/resource/prop[@name='type'][string(.)='fedramp-acronyms']/../rlink/@href
{{</ highlight >}}

## Additional Laws, Regulations, Standards or Guidance

{{< figure src="/img/content-figure-11.png" title="FedRAMP template laws and regulations." alt="Screenshot of laws, regulations, standards, and guidance information in the FedRAMP template." >}}

Additional citations must be represented as additional `resource` assemblies with one `resource` assembly per citation. This applies to applicable laws, regulations, standards, or guidance beyond FedRAMP's predefined set.

Each must have a type defined. The value of the `type` filed must be set to "law", "regulation", "standard", or "guidance" as appropriate. There may be more than one type defined. FedRAMP tools use the `type` property to differentiate these resource assemblies from others.

#### Representation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
 "system-security-plan" : {
   "back-matter" : {
     "resources" : [ {
       "title" : "\\[SAMPLE\\]Name or Title of Cited Law",
       "rlinks" : [ {
         "href" : "https://domain.example/path/to/document.pdf"
       } ],
       "uuid" : "d45612a9-cf25-4ef6-b2dd-69e38ba2967a",
       "props" : [ {
         "value" : "law",
         "name" : "type"
       }, {
         "value" : "Document Date",
         "name" : "publication"
       }, {
         "value" : "Document Version",
         "name" : "version"
       } ]
     }, {
       "title" : "\\[SAMPLE\\]Name or Title of Cited Law",
       "rlinks" : [ {
         "href" : "https://domain.example/path/to/document.pdf"
       } ],
       "uuid" : "a8a0cc81-800f-479f-93d3-8b8743d9b98d",
       "props" : [ {
         "value" : "regulation",
         "name" : "type"
       }, {
         "value" : "Document Date",
         "name" : "publication"
       }, {
         "value" : "Document Version",
         "name" : "version"
       } ]
     } ]
   },
   "uuid" : "12345678-1234-4321-8765-123456789012"
 }
}

{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
    <back-matter>
       <resource uuid="d45612a9-cf25-4ef6-b2dd-69e38ba2967a">
           <title>[SAMPLE]Name or Title of Cited Law</title>
           <prop name="type" value="law"/>
           <prop name="publication" value="Document Date"/>
           <prop name="version" value="Document Version"/>
           <rlink href="https://domain.example/path/to/document.pdf"> </rlink>
           <doc-id type="doi">Identification Number</doc-id>
       </resource>
       <resource uuid="a8a0cc81-800f-479f-93d3-8b8743d9b98d">
           <title>[SAMPLE]Name or Title of Cited Law</title>
           <prop name="type" value="regulation"/>
           <prop name="publication" value="Document Date"/>
           <prop name="version" value="Document Version"/>
           <rlink href="https://domain.example/path/to/document.pdf"> </rlink>
           <doc-id type="doi">Identification Number</doc-id>
       </resource>
  </back-matter>
</system-security-plan>

{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
 uuid: 12345678-1234-4321-8765-123456789012
 back-matter:
   resources:
   - props:
     - value: law
       name: type
     - value: Document Date
       name: publication
     - value: Document Version
       name: version
     title: "\\[SAMPLE\\]Name or Title of Cited Law"
     rlinks:
     - href: https://domain.example/path/to/document.pdf
     uuid: d45612a9-cf25-4ef6-b2dd-69e38ba2967a
   - props:
     - value: regulation
       name: type
     - value: Document Date
       name: publication
     - value: Document Version
       name: version
     title: "\\[SAMPLE\\]Name or Title of Cited Law"
     rlinks:
     - href: https://domain.example/path/to/document.pdf
     uuid: a8a0cc81-800f-479f-93d3-8b8743d9b98d

{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}


<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

#### XPath Queries

- Number of Laws and Regulations (integer): `count(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])`
- Laws and Regulations: Identification Number: `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../doc-id`
- Laws and Regulations: Title: `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../title`
- Laws and Regulations: Date: `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../prop[@name="publication"]`
- Laws and Regulations: Link: `(/*/back-matter/resource/prop[@name="type"][(string(.) = "law") or (string(.)="regulation")])[1]/../rlink/@href`

NOTE: For Standards and Guidance replace "law" with "standard" and "regulation" with "guidance" in the above queries to generate the Standards and Guidance tables.

