---
title: Services, Ports and Protocols
weight: 338
---


## Services, Ports and Protocols

The services, ports, and protocols table can be seen in the FedRAMP template below. 

{{< figure src="/img/ssp-figure-20.png" title="FedRAMP SSP template ports, protocols, and services." alt="Screenshot of the ports, protocols, and services information in the FedRAMP SSP template." >}}

In OSCAL, entries in the services, ports, and protocols table are represented as `component` assemblies, with the component-type flag set to "service". Use a protocol assembly for each protocol associated with the service. For a single port, set the `port-range` `start` flag and `end` flag to the same value.

#### OSCAL Representation
{{< tabs JSON XML YAML >}}
{{% tab %}}
{{< highlight json "linenos=table" >}}
{
 "system-security-plan" : {
   "uuid" : "12345678-1234-4321-8765-123456789012",
   "system-implementation" : {
     "components" : [ {
       "purpose" : "Describe the purpose for which the service is needed.",
       "uuid" : "77777777-0000-4000-9000-000000000006",
       "description" : "Describe the service",
       "status" : {
         "state" : "operational"
       },
       "links" : [ {
         "rel" : "used-by",
         "href" : "uuid-of-component-used-by"
       }, {
         "rel" : "provided-by",
         "href" : "uuid-of-component-provided-by"
       } ],
       "type" : "service",
       "protocols" : [ {
         "port-ranges" : [ {
           "transport" : "TCP",
           "start" : 80,
           "end" : 80
         } ],
         "name" : "http"
       }, {
         "port-ranges" : [ {
           "transport" : "TCP",
           "start" : 443,
           "end" : 443
         } ],
         "name" : "https"
       } ],
       "title" : "\\[SAMPLE\\]Service Name"
     } ]
   }
 }
}

{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight xml "linenos=table" >}}
<system-security-plan>
   <system-implementation>
       <!-- user -->
       <component uuid="77777777-0000-4000-9000-000000000006" type="service">
           <title>[SAMPLE]Service Name</title>
           <description><p>Describe the service</p></description>
           <purpose>Describe the purpose for which the service is needed.</purpose>
           <link href="uuid-of-component-used-by" rel="used-by" />
           <link href="uuid-of-component-provided-by" rel="provided-by" />
           <status state="operational" />
           <protocol name="http">
               <port-range start="80" end="80" transport="TCP"/>
           </protocol>
           <protocol name="https">
               <port-range start="443" end="443" transport="TCP"/>
           </protocol>
       </component>
       <!-- Repeat the component assembly for each row in Table 9.1 -->
       <!-- system-inventory -->
   </system-implementation>
</system-security-plan>

{{< /highlight >}}
{{% /tab %}}
{{% tab %}}
{{< highlight yaml "linenos=table" >}}
---
system-security-plan:
 system-implementation:
   components:
   - title: "\\[SAMPLE\\]Service Name"
     protocols:
     - port-ranges:
       - end: 80
         start: 80
         transport: TCP
       name: http
     - port-ranges:
       - end: 443
         start: 443
         transport: TCP
       name: https
     type: service
     links:
     - href: uuid-of-component-used-by
       rel: used-by
     - href: uuid-of-component-provided-by
       rel: provided-by
     status:
       state: operational
     description: Describe the service
     uuid: 77777777-0000-4000-9000-000000000006
     purpose: Describe the purpose for which the service is needed.
 uuid: 12345678-1234-4321-8765-123456789012
{{< /highlight >}}
{{% /tab %}}
{{< /tabs >}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Service (1st service):
        /*/system-implementation/component[@type='service'][1]/title
    Ports: Start (1st service, 1st protocol, 1st port range):
        /*/system-implementation/component[@type='service'][1]/protocol[1]/port-range[1]/@start
    Ports: End (1st service, 1st protocol, 1st port range):
        /*/system-implementation/component[@type='service'][1]/protocol[1]/port-range[1]/@end
    Ports: Transport (1st service, 1st protocol, 1st port range):
        /*/system-implementation/component[@type='service'][1]/protocol[1]/port-range[1]/@transport
    Protocol (1st service, 1st protocol):
        /*/system-implementation/component[@type='service'][1]/protocol[1]/@name
    Purpose (1st service):
        /*/system-implementation/component[@type='service'][1]/purpose
    Used By (1st service):
        /*/system-implementation/component[@uuid='uuid-of-component-used-by']/title
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---
