---
title: FedRAMP OSCAL Documentation
menu:
  primary:
    name: Documentation
    weight: 100
cascade:
  suppresstopiclist: true
  toc:
    display: true
  sidenav:
    activerenderdepth: 2
    inactiverenderdepth: 1
---
# FedRAMP OSCAL Documentation

## Who Should Use This Documentation?

This documentation is intended for technical staff and tool developers implementing solutions for importing, exporting, and processing OSCAL-based FedRAMP content.

It provides guidance and examples intended to guide an organization in the production and use of OSCAL-based FedRAMP-compliant documents. Our goal is to enable your organization to develop tools that will seamlessly ensure these standards are met so your security practitioners can focus on authorization package content and accuracy rather than formatting and presentation.

## Basic Terminology

XML and JSON use different terminology. Instead of repeatedly clarifying format-specific terminology, this document uses the following format-agnostic terminology through the document. 

|**OSCAL<br />TERM**|**XML EQUIVALENT**|**JSON EQUIVALENT**|
| :-: | :- | :- |
|**Field**|An atomic xml element that can contain a value.<br/>An OSCAL field may have OSCAL Flags (XML attributes) associated with it. | An atomic JSON object that can contain a value.<br /> An OSCAL field may have OSCAL Flags (atomic JSON child objects) associated with it. |
|**Flag**| An XML Attribute | An atomic JSON child object |
|**Assembly**|A collection of related XML elements under a parent element.|A collection of related JSON objects under a parent object.|

These terms are used by the National Institute of Standards and Technology (NIST) in the definition of OSCAL syntax.

Throughout this document, the following words are used to differentiate between requirements, recommendations, and options.

|**TERM**|**MEANING**|
| :- | :- |
|**MUST**|Indicates a required action.|
|**MUST NOT**|Indicates a prohibited action.|
|**SHOULD**|Indicates an action that is very important and strongly recommended, but is not required.|
|**SHOULD NOT**|Indicates an action that carries risks, and avoidance is strongly recommended; however, the action is not strictly prohibited.|
|**MAY**|Indicates an optional action.|


## XML, JSON and YAML Formats

The examples provided here are in XML; however, FedRAMP accepts XML, JSON or YAML formatted OSCAL content. OSCAL offers the ability to convert OSCAL-files between XML, JSON, and YAML in either direction without data loss.

You may submit your SSP, SAP, SAR, and POA&M to FedRAMP using XML, JSON, or YAML. If necessary, FedRAMP's tools will convert the files for processing.

{{<callout>}}
_For more information on converting OSCAL files between FORMATS, see [NIST OSCAL Tools - Data conversion](https://pages.nist.gov/OSCAL/resources/tools/#data-conversion) page._
{{</callout>}}

## OSCAL-based FedRAMP Templates

FedRAMP offers [OSCAL-based templates](https://github.com/GSA/fedramp-automation/tree/master/dist/content/rev5/templates) in both XML and JSON formats for
the SSP, SAP, SAR, and POA&M. These templates are partially filled with
sample content serving as placeholders to help get you started. This
documentation is intended to work in concert with those templates. The
OSCAL-based FedRAMP templates are available here:

## XML and JSON Technology Standards

For OSCAL compliance, mechanisms that interpret or generate OSCAL
content must honor the core syntax described at
[https://pages.nist.gov/OSCAL/concepts/layer/](https://pages.nist.gov/OSCAL/concepts/layer/).

While not mandatory, organizations adopting OSCAL are strongly
encouraged to use the [oscal-cli](https://github.com/usnistgov/oscal-cli) for validation and translation
mechanisms. The validation mechanism ensures XML and JSON files are
using OSCAL-compliant syntax, while the translation mechanism converts
OSCAL content from either format to the other. NIST has an automated
governance process, which ensures these mechanisms remain aligned with
the latest OSCAL syntax.

{{<callout>}}
_TIP: There are comments in the XML versions of the FedRAMP Templates. Unfortunately, JSON does not formally support comments. JSON users may wish to review the comments in the equivalent sections of the XML files._
{{</callout>}}

### NIST OSCAL Syntax Validation Mechanisms

Validating XML-based OSCAL files using the OSCAL-published schema
validation requires: [XML Schema Definition Language (XSD) 1.1](https://www.w3.org/TR/xmlschema11-1/)

Validating JSON-based OSCAL files using the OSCAL-published schema
validation requires: [JSON Schema, draft-07](https://json-schema.org/specification-links#23draft-7)

The [NIST OSCAL tools](https://pages.nist.gov/OSCAL/resources/tools/#validation) provide a mechanism for validating OSCAL XML and JSON content. There are several open-source and commercial tools that will process XSD 1.1 or JSON Schema, draft-07, either as standalone capabilities or as programming libraries. FedRAMP and NIST are unable to endorse specific products.

### NIST OSCAL Format Conversion Mechanisms

The [NIST OSCAL tools](https://pages.nist.gov/OSCAL/resources/tools/#data-conversion) also provide a mechanism for converting OSCAL XML and JSON content.

For more information on converting OSCAL files between supported
formats, please see the [OSCAL Converters](https://pages.nist.gov/OSCAL/concepts/layer/overview/#oscal-converters) documentation.

## XPath Queries and References

XPath is a standard query language for XML files, and libraries for
using it are available in many programming languages. Even if you do not
use XPath to query OSCAL data files, the XPath queries provide a concise
and non-ambiguous way to communicate where the data is located within
the file.

Except where noted, all XPath queries in this document are based on
XPath 2.0. Most modern programming languages make XPath 1.0 available by
default. XPath 2.0 can typically be added with third-party libraries or
calls to external command-line utilities.

{{<callout>}}
_JSON Users: There are several JSON query technologies available, such as [JSONPath](https://restfulapi.net/json-jsonpath/); however, no one technology has emerged as a clear standard as of this publication._
{{</callout>}}

Most XPath queries in this document are absolute paths from the root of
the document. In other words, it is clear from the XPath query which of
the major file sections are being referenced,
and where the field is located within the section.

{{<callout>}}
_**Database Users**: Some tool developers prefer to manage OSCAL data by first importing it into a database, which is a perfectly acceptable approach. Any OSCAL file generated from the database must still follow the OSCAL syntax. If the file is intended for delivery to FedRAMP, it must also follow the guidance in these guides._

_There are also database-like XML servers, such as the open-source tool [BaseX](https://basex.org/), which allow OSCAL files to remain in their native format yet be queried more like a traditional database. These XML databases typically optimize queries for better performance. Some will handle both XML and JSON files._
{{</callout>}}
