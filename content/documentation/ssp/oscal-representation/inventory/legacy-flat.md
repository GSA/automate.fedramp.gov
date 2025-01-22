---
title: System Inventory - Legacy/Flat Approach
weight: 100
---
## System Inventory: Legacy/Flat Approach

{{< figure src="/img/ssp-figure-25.png" title="FedRAMP OSCAL flat-file inventory approach." alt="Figure illustrating the 'legacy/flat' inventory approach where each inventory spreadsheet row is represented as a single OSCAL inventory-item." >}}

With the **legacy/flat approach**, all content on a spreadsheet row appears in a single OSCAL inventory-item assembly. This results in a great deal of redundant information but is a simple transition from the current spreadsheet approach.

{{< figure src="/img/ssp-figure-24.png" title="FedRAMP SSP template Integrated Inventory Workbook." alt="Screenshot of the Integrated Inventory Workbook in the FedRAMP SSP template." >}}


##### Flat-File Representation
{{< highlight xml "linenos=table" >}}
<!-- cut -->
<system-implementation>
    <!-- interconnection -->
    <system-inventory>
        <inventory-item uuid="uuid-value" asset-id="unique-asset-id">
            <description><p>Flat-File Example (No implemented-component).</p></description>
            <prop name="ipv4-address" value="0.0.0.0"/>
            <prop name="ipv6-address" value="0000:0000:0000:0000"/>
            <prop name="virtual" value="no"/>
            <prop name="public" value="no"/>
            <prop name="fqdn" value="example.com"/>
            <prop name="uri" value="https://example/query?key=value#anchor"/>
            <prop name="netbios-name" value="netbios-name"/>
            <prop name="mac-address" value="00:00:00:00:00:00"/>
            <prop name="software-name" value="software-name"/>
            <prop name="version" value="V 0.0.0"/>
            <prop name="asset-type" value="os"/>
            <prop name="vendor-name" value="Vendor Name"/>
            <prop name="model" value="Model Number"/>
            <prop name="patch-level" value="Patch-Level"/>
            <prop name="serial-number" value="Serial #"/>
            <prop name="asset-tag" value="Asset Tag"/>
            <prop name="vlan-id" value="VLAN Identifier"/>
            <prop name="network-id" value="Network Identifier"/>
            <prop name="scan-type" ns="https://fedramp.gov/ns/oscal" value="infrastructure"/>
            <prop name="allows-authenticated-scan"  value="no">
                <remarks><p>If no, explain why. If yes, omit remarks field.</p></remarks>
            </prop>
            <prop name="baseline-configuration-name" value="Baseline Config. Name" />
            <prop name="physical-location" value="Physical location of Asset" />
            <prop name="is-scanned" value="yes"/>
            <prop name="function" value="Required brief, text-based description."/>
            <link rel="validation" href="#uuid-of-validation-component" />
            <status state="operational"/>
            <responsible-party role-id="asset-owner">
                <party-id>person-7</party-id>
            </responsible-party>
            <responsible-party role-id="asset-administrator">
                <party-id>it-dept</party-id>
            </responsible-party>
            <implemented-component component-uuid="component-uuid-value " />
            <remarks><p>COMMENTS: Additional information about this item.</p></remarks>
        </inventory-item>
        <!-- Repeat the inventory-item assembly for each item in the inventory -->
    </system-inventory>
    <!-- system-implementation remarks -->
</system-implementation>
{{</ highlight >}}

**Notes:**

The value of asset-type determines whether the identified
asset-administrator is managing a system or an application. Currently, any FedRAMP-defined asset-type implies the management of a system, and therefore, is to be scanned as infrastructure.

---
