---
title: Illustrated Architecture and Narratives
weight: 120
---

## Illustrated Architecture and Narratives

### Authorization Boundary

The OSCAL approach to this type of diagram is to treat the image data as either a linked or base64-encoded `resource` in the `back-matter` section of the OSCAL file, then reference the diagram using the `link` field. The narrative describing the system architecture must be provided in the `description` field of the `authorization-boundary` assembly.

{{< figure src="/img/ssp-figure-19.png" title="FedRAMP SSP template authorization boundary sections." alt="Screenshot of the authorization boundary information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-characteristics>
    <!-- leveraged-authorization -->
    <authorization-boundary>
        <!-- 8.2 Narrative (Boundary) -->
        <description>
            <p>A holistic, top-level explanation of the FedRAMP authorization boundary.</p>
        </description>
        <!-- 8.1 Illustrated Architecture (Boundary) -->
        <diagram uuid="uuid-value">
            <description><p>A diagram-specific explanation.</p></description>
            <link href="#uuid-of-boundary-diagram-1" rel="diagram" />
            <caption>Authorization Boundary Diagram</caption>
        </diagram>
        <!-- repeat diagram assembly for each additional boundary diagram -->
    </authorization-boundary>
    <!-- network-architecture -->
</system-characteristics>

<!-- cut -->

<back-matter>
    <resource uuid="uuid-of-boundary-diagram-1">
        <description><p>The primary authorization boundary diagram.</p></description>
        <base64 filename="architecture-main.png" media-type="image/png">00000000</base64>
    </resource>
</back-matter>
{{</ highlight >}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Overall Description:
        /*/system-characteristics/authorization-boundary/description/node()
    Count the Number of Diagrams (There should be at least 1):
        count(/*/system-characteristics/authorization-boundary/diagram)
    Link to First Diagram:
        /*/system-characteristics/authorization-boundary/diagram[1]/link/@href


    If the diagram link points to a resource within the OSCAL file:
        /*/back-matter/resource[@uuid="uuid-of-boundary-diagram"]/base64
    OR:
        /*/back-matter/resource[@uuid="uuid-of-boundary-diagram-1"]/rlink/@href
    Diagram-specific Description:
        /*/system-characteristics/authorization-boundary/diagram[1]/description/node()
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---
### Network Architecture

Consistent with the [*Authorization Boundary*](#authorization-boundary) guidance, the OSCAL approach to network architecture diagrams is to treat image data as either a linked or base64-encoded `resource` in the `back-matter` section of the OSCAL file, then reference the diagram using the `link` field. The narrative describing the network architecture must be provided in the `description` field of the `network-architecture` assembly.

{{< figure src="/img/ssp-figure-19.png" title="FedRAMP SSP template network architecture." alt="Screenshot of the network architecture information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-characteristics>
    <!-- authorization-boundary -->
    <network-architecture>
        <!-- 8.2 Narrative (Network) -->
        <description>
            <p>A holistic, top-level explanation of the system's network.</p>
        </description>
        <!-- 8.1 Illustrated Architecture (Network) -->
        <diagram uuid="uuid-value">
            <description><p>A diagram-specific explanation.</p></description>
            <link href="#uuid-of-network-diagram-1" rel="diagram" />
            <caption>Network Diagram</caption>
        </diagram>
        <!-- repeat diagram assembly for each additional network diagram -->
    </network-architecture>
    <!-- data-flow -->
</system-characteristics>


<!-- cut -->


<back-matter>
    <!-- citation -->
    <resource uuid=" uuid-of-network-diagram-1">
        <description><p>The primary network architecture diagram.</p></description>
        <rlink href="./diagrams/network.png" media-type="image/png"/>
    </resource>
</back-matter>
{{</ highlight >}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Overall Description:
        /*/system-characteristics/network-architecture/description/node()
    Count the Number of Diagrams (There should be at least 1):
        count(/*/system-characteristics/network-architecture/diagram)
    Link to First Diagram:
        /*/system-characteristics/network-architecture/diagram[1]/link/@href


    If the diagram link points to a resource within the OSCAL file:
        /*/back-matter/resource[@uuid="uuid-of-network-diagram-1"]/base64
    OR:
        /*/back-matter/resource[@uuid="uuid-of-network-diagram-1"]/rlink/@href
    First Diagram Description:
        /*/system-characteristics/network-architecture/diagram[1]/description/node()
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---
### Data Flow

Consistent with the [*Authorization Boundary*](#authorization-boundary) guidance, the OSCAL approach to data flow diagrams is to treat image data as either a linked or base64-encoded `resource` in the `back-matter` section of the OSCAL file, then reference the diagram using the `link` field. The narrative describing the data flows must be provided in the `description` field of the `data-flow` assembly.

{{< figure src="/img/ssp-figure-19.png" title="FedRAMP SSP template data flow." alt="Screenshot of data flow information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-characteristics>
    <!-- data-flow -->
    <data-flow>
        <!-- 8.2 Narrative (Data Flow) -->
        <description>
            <p>A holistic, top-level explanation of the system's data flows.</p>
        </description>
        <!-- 8.1 Illustrated Architecture (Data Flow) -->
        <diagram uuid="uuid-value">
            <description><p>A diagram-specific explanation.</p></description>
            <link href="#uuid-of-dataflow-diagram-1" rel="diagram" />
            <caption>Data Flow Diagram</caption>
        </diagram>
        <!-- repeat diagram assembly for each additional data flow diagram -->
    </data-flow>
    <!-- network-architecture -->
</system-characteristics>   

<!-- cut -->

<back-matter>
    <!-- citation -->
    <resource uuid="uuid-of-dataflow-diagram-1">
        <description><p>The primary data flow diagram.</p></description>
        <base64 filename="data-flow-1.png" media-type="image/png">
            0000<!-- base64 cut -->0000
        </base64>
    </resource>
</back-matter>
{{</ highlight >}}


#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Overall Description:
        /*/system-characteristics/data-flow/description/node()
    Count the Number of Diagrams (There should be at least 1):
        count(/*/system-characteristics/data-flow/diagram)
    Link to First Diagram:
        /*/system-characteristics/data-flow/diagram[1]/link/@href

    If the diagram link points to a resource within the OSCAL file:
        /*/back-matter/resource[@uuid="uuid-of-dataflow-diagram-1"]/base64
    OR:
        /*/back-matter/resource[@uuid="uuid-of-dataflow-diagram-1"]/rlink/@href
    First Diagram Description:
        /*/system-characteristics/data-flow/diagram[1]/description/node()
{{</ highlight >}}

<br />
{{<callout>}}
Replace XPath predicate "[1]" with "[2]", "[3]", etc.
{{</callout>}}

---


