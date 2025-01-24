---
title: Illustrated Architecture and Narratives
weight: 120
---

## Illustrated Architecture and Narratives

### Authorization Boundary

The OSCAL approach to this type of diagram is to treat the image data as either a linked or base64-encoded `resource` in the `back-matter` section of the OSCAL file, then reference the diagram using the `link` field in the `diagram` assembly. The narrative describing the system architecture must be provided in the `description` field of the `authorization-boundary` assembly.

{{< figure src="/img/ssp-figure-19.png" title="FedRAMP SSP template authorization boundary sections." alt="Screenshot of the authorization boundary information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-characteristics>
    <!-- Section 8 - Illustrated Architecture and Narrative -->
    <authorization-boundary>
      <!-- Section 8.2 Narrative (boundary) -->
      <description>
        <p>A holistic, top-level explanation of the FedRAMP authorization boundary.</p>
      </description>
      <!-- Section 8.1 Illustrated Architecture (boundary diagram) -->
      <diagram uuid="11111111-2222-4000-8000-007000000001">
        <description>
          <p>A diagram-specific explanation.</p>
        </description>
        <link href="#11111111-2222-4000-8000-001000000054" rel="diagram"/>
        <caption>Authorization Boundary Diagram</caption>
      </diagram>
    </authorization-boundary>
    <!-- network-architecture -->
</system-characteristics>

<!-- cut -->

<back-matter>
    <!-- Section 8.1 - SSP Diagrams -->
    <resource uuid="11111111-2222-4000-8000-001000000054">
      <title>Boundary Diagram</title>
      <description>
        <p>The primary authorization boundary diagram.</p>
      </description>
      <prop name="type" value="image" class="authorization-boundary"/>
      <rlink href="./attachments/diagrams/boundary.png"/>
      <base64 filename="logo.png" media-type="image/png">00000000</base64>
      <remarks>
        <p>Section 8.1, Figure 8-1 Authorization Boundary Diagram (graphic)</p>
        <p>This should be referenced in the 
system-characteristics/authorization-boundary/diagram/link/@href flag using a value
of "#11111111-2222-4000-8000-001000000054"</p>
        <p>May use <code>rlink</code> with a relative path, or embedded as
          <code>base64</code>.
        </p>
        <p>FedRAMP prefers <code>base64</code> for images and diagrams.</p>
        <p>Images must be in sufficient resolution to read all detail when rendered in 
a browser via HTML5.</p>
      </remarks>
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

<br/>
{{<callout>}}

**Additional Notes:**

Replace XPath predicate "[1]" with "[2]", "[3]", etc.

Core OSCAL requires that the following field exist:

- `//system-characteristics/authorization-boundary/description`

The following is optional under core OSCAL, but required by FedRAMP and enforced with constraints:

- `//system-characteristics/authorization-boundary/diagram/link/@href`

The following is required by FedRAMP and enforced with constraints:

- All `//diagram/link/@href` must have valid and accessible `resource` targets in the `back-matter`.
- The diagram `resource` assemblies must have a `base64` or `rlink` field.

{{</callout>}}

---
### Network Architecture

Consistent with the [*Authorization Boundary*](#authorization-boundary) guidance, the OSCAL approach to network architecture diagrams is to treat image data as either a linked or base64-encoded `resource` in the `back-matter` section of the OSCAL file, then reference the diagram using the `link` field. The narrative describing the network architecture must be provided in the `description` field of the `network-architecture` assembly.

{{< figure src="/img/ssp-figure-19.png" title="FedRAMP SSP template network architecture." alt="Screenshot of the network architecture information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-characteristics>
    <!-- authorization-boundary omitted -->
    <network-architecture>
      <!-- Section 8.2 Narrative (network) -->
      <description>
        <p>A holistic, top-level explanation of the network architecture.</p>
      </description>
      <!-- Section 8.1 Illustrated Architecture (network diagram) -->
      <diagram uuid="11111111-2222-4000-8000-007000000002">
        <description>
          <p>A diagram-specific explanation.</p>
        </description>
        <link href="#11111111-2222-4000-8000-001000000055" rel="diagram"/>
        <caption>Network Diagram</caption>
      </diagram>
    </network-architecture>
    <!-- data-flow omitted -->
</system-characteristics>

<!-- cut -->

<back-matter>
    <!-- Section 8.1 - SSP Diagrams -->
    <resource uuid="11111111-2222-4000-8000-001000000055">
      <title>Network Diagram</title>
      <description>
        <p>The primary network diagram.</p>
      </description>
      <prop name="type" value="image" class="network-architecture"/>
      <!-- Use rlink and/or base64 -->
      <rlink href="./attachments/diagrams/network.png"/>
      <base64 filename="network.png" media-type="image/png">00000000</base64>
      <remarks>
        <p>Section 8.1, Figure 8-2 Network Diagram (graphic)</p>
        <p>This should be referenced in the
system-characteristics/network-architecture/diagram/link/@href flag using a value of
"#11111111-2222-4000-8000-001000000055"</p>
        <p>May use <code>rlink</code> with a relative path, or embedded as
          <code>base64</code>.
        </p>
        <p>FedRAMP prefers <code>base64</code> for images and diagrams.</p>
        <p>Images must be in sufficient resolution to read all detail when rendered in a browser
via HTML5.</p>
      </remarks>
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

<br/>
{{<callout>}}

**Additional Notes:**

Replace XPath predicate "[1]" with "[2]", "[3]", etc.

Core OSCAL requires that the following field exist:

- `//system-characteristics/network-architecture/description`

The following is optional under core OSCAL, but required by FedRAMP and enforced with constraints:

- `//system-characteristics/network-architecture/diagram/link/@href`

The following is required by FedRAMP and enforced with constraints:

- All `//diagram/link/@href` must have valid and accessible `resource` targets in the `back-matter`.
- The diagram `resource` assemblies must have a `base64` or `rlink` field.

{{</callout>}}

---
### Data Flow

Consistent with the [*Authorization Boundary*](#authorization-boundary) guidance, the OSCAL approach to data flow diagrams is to treat image data as either a linked or base64-encoded `resource` in the `back-matter` section of the OSCAL file, then reference the diagram using the `link` field. The narrative describing the data flows must be provided in the `description` field of the `data-flow` assembly.

{{< figure src="/img/ssp-figure-19.png" title="FedRAMP SSP template data flow." alt="Screenshot of data flow information in the FedRAMP SSP template." >}}

#### OSCAL Representation
{{< highlight xml "linenos=table" >}}
<system-characteristics>
    <!-- authorization-boundary omitted -->
    <!-- network-architecture omitted -->
    <data-flow>
      <!-- Section 8.2 Narrative (data flows) -->
      <description>
        <p>A holistic, top-level explanation of the system's data flows.</p>
      </description>
      <!-- Section 8.1 Illustrated Architecture (data flows) -->
      <diagram uuid="11111111-2222-4000-8000-007000000003">
        <description>
          <p>A diagram-specific explanation.</p>
        </description>
        <link href="#11111111-2222-4000-8000-001000000056" rel="diagram"/>
        <caption>Data Flow Diagram</caption>
      </diagram>
    </data-flow>
</system-characteristics>

<!-- cut -->

<back-matter>
    <!-- Section 8.1 - SSP Diagrams -->
    <resource uuid="11111111-2222-4000-8000-001000000056">
      <title>Data Flow Diagram</title>
      <description>
        <p>The primary data flow diagram.</p>
      </description>
      <prop name="type" value="image" class="data-flow"/>
      <rlink href="./attachments/diagrams/dataflow.png"/>
      <base64 filename="dataflow.png" media-type="image/png">00000000</base64>
      <remarks>
        <p>Section 8.1, Figure 8-3 Data Flow Diagram (graphic)</p>
        <p>This should be referenced in the system-characteristics/data-flow/diagram/link/@href
flag using a value of "#11111111-2222-4000-8000-001000000056"</p>
        <p>May use <code>rlink</code> with a relative path, or embedded as
          <code>base64</code>.
        </p>
        <p>FedRAMP prefers <code>base64</code> for images and diagrams.</p>
        <p>Images must be in sufficient resolution to read all detail when rendered in a browser
via HTML5.</p>
      </remarks>
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

**Additional Notes:**

Replace XPath predicate "[1]" with "[2]", "[3]", etc.

Core OSCAL requires that the following field exist:

- `//system-characteristics/data-flow/description`

The following is optional under core OSCAL, but required by FedRAMP and enforced with constraints:

- `//system-characteristics/data-flow/diagram/link/@href`

The following is required by FedRAMP and enforced with constraints:

- All `//diagram/link/@href` must have valid and accessible `resource` targets in the `back-matter`.
- The diagram `resource` assemblies must have a `base64` or `rlink` field.

{{</callout>}}

---


