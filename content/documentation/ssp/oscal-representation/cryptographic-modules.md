---
title: Cryptographic Modules
weight: 342
---
## Cryptographic Modules

## Cryptographic Modules Implemented for Data-in-Transit (DIT) 

OSCAL's component model treats independent validation of products and services as if that validation were a separate component. This means when using components with FIPS 140 validated cryptographic modules, there must be two component assemblies:

-   **The Validation Definition**: A component that provides details about the validation.

-   **The Product Definition**: A component that describes the hardware or software product.

The validation definition is a component that provides details about the independent validation. Its type must have a value of "validation". In the case of FIPS 140 validation, this must include a link field with a rel value set to "validation-details". This link must point to the cryptographic module's entry in the NIST Computer Security
Resource Center (CSRC) [Cryptographic Module Validation Program Database](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search).

The product definition is a product with a cryptographic module. It must contain all of the typical component information suitable for reference by inventory-items and control statements. It must also include a link field with a rel value set to "validation" and an href value containing
a URI fragment. The fragment must start with a hashtag (#) and include the UUID value of the validation component. This links the two together.

{{< figure src="/img/ssp-figure-21.png" title="FedRAMP SSP template cryptographic modules table (data-in-transit)." alt="Screenshot of the cryptographic modules table (data-in-transit) in the FedRAMP SSP template." >}}

##### Component Representation: Example Product with FIPS 140-2 Validation
{{< highlight xml "linenos=table" >}}
<!-- system-characteristics -->
<system-implementation>
    <!-- user -->
    <!-- Minimum Required Components -->
    
    <!-- FIPS 140-2 Validation Certificate Information -->
    <!-- Include a separate component for each relevant certificate -->
    <component uuid="uuid-value" type="validation">
        <title>Module Name</title>
        <description><p>FIPS 140-2 Validated Module</p></description>
        <prop ns="https://fedramp.gov/ns/oscal" name="asset-type" 
              value="cryptographic-module" />
        <prop ns="https://fedramp.gov/ns/oscal" name="vendor-name" 
              value="CM Vendor"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="cryptographic-module-usage" 
              value="data-in-transit"/>
        <prop name="validation-type" value="fips-140-2"/>
        <prop name="validation-reference" value="0000"/>
        <link href="https://csrc.nist.gov/projects/cryptographic-module-validation-program/Certificate/0000" rel="validation-details" />
        <status state="operational" />
    </component>
    
    <!-- FIPS 140-2 Validated Product -->
    <component uuid="uuid-value" type="software" >
        <title>Product Name</title>
        <description><p>A product with a cryptographic module.</p></description>
        <link href="#uuid-of-validation-component" rel="validation" />
        <status state="operational" />
    </component>
    
    <!-- service -->
</system-implementation>
<!-- control-implementation -->
{{</ highlight >}}

---
## Cryptographic Modules Implemented for Data-at-Rest (DAR)

The approach is the same as in the [*cryptographic module data-in-transit*](#cryptographic-modules-implemented-for-data-in-transit-dit) section.

{{< figure src="/img/ssp-figure-22.png" title="FedRAMP SSP template cryptographic modules table (data-at-rest)." alt="Screenshot of the cryptographic modules table (data-at-rest) in the FedRAMP SSP template." >}}

##### Component Representation: Example Product with FIPS 140-2 Validation
{{< highlight xml "linenos=table" >}}
<!-- system-characteristics -->
<system-implementation>
    <!-- user -->
    <!-- Minimum Required Components -->
    
    <!-- FIPS 140-2 Validation Certificate Information -->
    <!-- Include a separate component for each relevant certificate -->
    <component uuid="uuid-value" type="validation">
        <title>Module Name</title>
        <description><p>FIPS 140-2 Validated Module</p></description>
        <prop ns="https://fedramp.gov/ns/oscal" name="asset-type" 
              value="cryptographic-module" />
        <prop ns="https://fedramp.gov/ns/oscal" name="vendor-name" 
              value="CM Vendor"/>
        <prop ns="https://fedramp.gov/ns/oscal" name="cryptographic-module-usage" 
              value="data-at-rest"/>
        <prop name="validation-type" value="fips-140-2"/>
        <prop name="validation-reference" value="0000"/>
        <link href="https://csrc.nist.gov/projects/cryptographic-module-validation-program/Certificate/0000" rel="validation-details" />
        <status state="operational" />
    </component>
    
    <!-- FIPS 140-2 Validated Product -->
    <component uuid="uuid-value" type="software" >
        <title>Product Name</title>
        <description><p>A product with a cryptographic module.</p></description>
        <link href="#uuid-of-validation-component" rel="validation" />
        <status state="operational" />
    </component>
    
    <!-- service -->
</system-implementation>
<!-- control-implementation -->
{{</ highlight >}}

