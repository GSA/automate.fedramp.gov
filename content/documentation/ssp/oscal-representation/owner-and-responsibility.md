---
title: System Owner and Assignment of Responsibility
weight: 110
---
# System Owner and Assignment of Responsibility

Explanatory content

## System Owner

Explanatory content

<ul class="usa-card-group">
  <li class="usa-card tablet-lg:grid-col-8 widescreen:grid-col-6 usa-card--header-first">
    <div class="usa-card__container">
      <div class="usa-card__header">
        <h4 class="usa-card__heading">FedRAMP Template Representation</h4>
      </div>
      <div class="usa-card__media usa-card__media--exdent">
        <div class="usa-card__img">
            {{< figure src="/img/ssp-figure-12.png" title="System Owner Information" alt="Screenshot of the SSP template's system owner information." >}}
        </div>
      </div>
      <div class="usa-card__body">
        <p>
          Caption
        </p>
      </div>
      <div class="usa-card__footer">
      </div>
    </div>
  </li>
  <li class="usa-card tablet-lg:grid-col-8 widescreen:grid-col-6">
    <div class="usa-card__container">
      <div class="usa-card__header">
        <h4 class="usa-card__heading">FedRAMP OSCAL Representation</h4>
      </div>
      <div class="usa-card__body">
        <p>
          Description of OSCAL
        </p>

<h4>Sample OSCAL Content</hr>
{{< highlight xml "linenos=table" >}}
<profile xmlns="http://csrc.nist.gov/ns/oscal/1.0"
    uuid="-UUID-value-cut-">

</profile>
{{</ highlight >}}
      </div>
    </div>
  </li>
</ul>

## Assignment of Responsibility

More explanatory content


<ul class="usa-card-group">
  <li class="usa-card tablet-lg:grid-col-8 widescreen:grid-col-6 usa-card--header-first">
    <div class="usa-card__container">
      <div class="usa-card__header">
        <h4 class="usa-card__heading">FedRAMP Template Representation</h4>
      </div>
      <div class="usa-card__media usa-card__media--exdent">
        <div class="usa-card__img">
            {{< figure src="/img/ssp-figure-13.png" title="Assignment of Responsibility" alt="Screenshot of the SSP template's assignment of responsibility information." >}}
        </div>
      </div>
      <div class="usa-card__body">
        <p>
          Caption
        </p>
      </div>
      <div class="usa-card__footer">
      </div>
    </div>
  </li>
  <li class="usa-card tablet-lg:grid-col-8 widescreen:grid-col-6">
    <div class="usa-card__container">
      <div class="usa-card__header">
        <h4 class="usa-card__heading">FedRAMP OSCAL Representation</h4>
      </div>
      <div class="usa-card__body">
        <p>
          Description of OSCAL
        </p>

<h4>Sample OSCAL Content</hr>
{{< highlight xml "linenos=table" >}}
<profile xmlns="http://csrc.nist.gov/ns/oscal/1.0"
    uuid="-UUID-value-cut-">

</profile>
{{</ highlight >}}
      </div>
    </div>
  </li>
</ul>

Closing content

## Federal Authorizing Officials

A role with an ID value of "authorizing-official" is required. Use the responsible-party assembly to associate this role with the party assembly containing the Authorizing Official's information.

{{< figure src="/img/ssp-figure-13.png" title="FedRAMP SSP template federal authorizing officials." alt="Screenshot of the federal authorizing official information in the FedRAMP SSP template." >}}

##### Federal Agency Authorization Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <role id="authorizing-official">
        <title>Authorizing Official</title>
    </role>
    <party uuid="uuid-of-agency" type="organization">
        <name>Agency Name</name>
    </party>
    <party uuid="uuid-of-person-6" type="person">
        <name>[SAMPLE]Person Name 6</name>
        <prop name="job-title" value="Individual's Title"/>
            <email-address>name@example.com</email-address>
            <telephone-number>202-000-0000</telephone-number>
            <member-of-organization>uuid-of-agency</member-of-organization>
    </party>
    <responsible-party role-id="authorizing-official">
        <party-uuid>uuid-of-person-6</party-uuid>
    </responsible-party>
</metadata>
<!-- import -->
<system-characteristics>
    <!-- description -->
    <prop name="authorization-type" 
          ns="https://fedramp.gov/ns/oscal" 
          value="fedramp-agency" />
    <!-- prop -->
</system-characteristics>
{{</ highlight >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    FedRAMP Authorization Type:
        /*/system-characteristics/prop[@name="authorization-type"][@ns="https://fedramp.gov/ns/oscal"]/@value
    Authorizing Official’s Name:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="authorizing-official"]/party-uuid]]/name
    NOTE: Replace "name" with "email-address" or "telephone-number" above as needed.
    Authorizing Official’s Title:
        /*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="authorizing-official"]/party-uuid]]/prop[@name='job-title']
    Authorizing Official's Agency:
        /*/metadata/party[@uuid=/*/metadata/party[@uuid=[/*/metadata/responsible-party [@role-id="authorizing-official"]/party-uuid]]/member-of-organization]/name
{{</ highlight >}}

**NOTE:**

If the authorization-type field is "fedramp-jab", the responsible-party/party-uuid field must be the uuid value for the FedRAMP JAB.

---
#### Federal JAB P-ATO Authorization Representation
{{< highlight xml "linenos=table" >}}
<metadata>
    <!-- cut -->
    <role id="authorizing-official">
        <title>Authorizing Official</title>
        <desc>The government executive(s) who authorize this system.</desc>
    </role>
    <!-- cut -->
    <party uuid="uuid-of-fedramp-jab" type="organization">
        <name>FedRAMP: Joint Authorization Board</name>
        <short-name>FedRAMP JAB</short-name>
    </party>
    <!-- cut -->
    <responsible-party role-id="authorizing-official">
        <party-uuid>uuid-of-fedramp-jab</party-uuid>
    </responsible-party>
</metadata>
<!-- import -->
<system-characteristics>
    <!-- description -->
    <prop name="authorization-type" 
          ns="https://fedramp.gov/ns/oscal">fedramp-jab</prop>
    <!-- prop -->
</system-characteristics>
{{</ highlight >}}

#### XPath Queries
{{< highlight xml "linenos=table" >}}
    Authorizing Official’s Name:
        //metadata/party[@uuid=[//metadata/responsible-party[@role-id="authorizing-official"]/party-uuid]]/name
{{</ highlight >}}

<br />
{{<callout>}}

**FedRAMP Extension:**

prop (ns="https://fedramp.gov/ns/oscal")
- name="authorization-type" 

**FedRAMP Allowed Values**
- fedramp-jab
- fedramp-agency
- fedramp-li-saas

**OSCAL Allowed Value**

Required Role ID:
- authorizing-official

{{</callout>}}


---

