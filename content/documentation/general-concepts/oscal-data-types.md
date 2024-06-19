---
title: OSCAL Data Types
weight: 117
---
# Handling of OSCAL Data Types

OSCAL fields and flags have data types assigned to them. NIST provides
important information about these data types here:
[[https://pages.nist.gov/OSCAL/reference/datatypes/]](https://pages.nist.gov/OSCAL/reference/datatypes/)

The following sections describe special handling considerations for data
types that directly impact FedRAMP content in OSCAL.

## Date and Time in OSCAL Files

Except where noted, all dates and times in the OSCAL-based content must
be in an OSCAL
`dateTime-with-timezone` format as documented here:

[[https://pages.nist.gov/OSCAL/reference/datatypes/#datetime-with-timezone]](https://pages.nist.gov/OSCAL/reference/datatypes/#datetime-with-timezone)

This means all dates and times must be represented in the OSCAL file
using following format, unless otherwise noted:

`"Y-m-dTH:i:s.uP"` (See
[HERE](https://www.php.net/manual/en/class.datetime.php) for formatting
codes.)

For example, a publication date of 5:30 pm EST, January 10, 2020 must
appear as
2020-01-10T17:30:00.00-05:00

This includes:

-   Numeric Year: Four-digits

-   A dash

-   Numeric Month: Two-digit, zero-padded

-   A dash

-   Numeric Day: Two digit, zero padded

-   The capital letter "T" (Do not use lower case)

-   Hour: Two digit, zero-padded, 24-hour clock (Use 18 for 6:00 pm)

-   A colon

-   Minute: Two digit, zero-padded

-   A colon

-   Seconds: Two digit, zero-padded

-   A decimal point

-   Fractions of a second: two or three digits, zero padded

Followed by either:

-   A capital letter Z to indicate the time is expressed in Coordinated
    Universal Time (UTC)

OR:

-   A plus or minus representing the offset from UTC

-   Hour Offset: Difference from UTC, two-digit, padded

-   A colon

-   Minutes Offset: Difference from UTC, two-digit, padded

This is only for *storing* dates in the OSCAL file. NIST syntax
verification tools will generate an error if this format is not found.

Tool developers are encouraged to *present* dates as they have
historically appeared in FedRAMP documents. In other words, tools should
convert `"2020-03-04T00:00:00.00-05:00"` to `"March 4, 2020"` when
presenting the publication date to the user.

Please use the appropriate UTC offset in your region. If you are storing
a date and padding the time with zeros, you may also pad the UTC offset
with zeros.

## UUID Datatypes

Any place a UUID flag or UUID reference exits, NIST requires UUID
version 4, as defined by
[RFC-4122](https://tools.ietf.org/html/rfc4122). See here for more
information: <https://pages.nist.gov/OSCAL/reference/datatypes/#uuid>

Version 4 UUIDs are 128-bit numbers, represented as 32 hexadecimal
(base-16) digits in the pattern:

`xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

All alphabetic characters (a-f) representing hexadecimal values must be
lower case.

Strictly following the RFC ensures the probability of generating an
unintended duplicate UUID value is so close to zero it may be ignored.
As calculated on
[Wikipedia](https://en.wikipedia.org/wiki/Universally_unique_identifier),
after generating 103 trillion version 4 UUIDs, there is a one in a
billion chance of a duplicate.

There are several open-source algorithms and built-in functions for
generating UUID. It is important to use one that is known to be fully
compliant. Unintended duplicate UUIDs become more likely when using
non-compliant or erroneous algorithms.

**For more information about the use of UUIDs in OSCAL, see *Section*
*2.5,* *Assigning Identifiers*.**

## ID Datatypes

NIST typically uses ID flags in OSCAL where the identifier is intended
to be canonical, such as the identifiers for `role` IDs or NIST SP 800-53
controls.

Any place an ID flag or ID reference exits, the datatype is
[token](https://pages.nist.gov/OSCAL/reference/datatypes/#token). It is
similar to the [NCName](https://www.w3.org/TR/xmlschema-2/#NCName) as
defined by the World Wide Web Consortium (W3C), but does not allow
spaces. The allowable values of an NCName are limited as follows:

-   The first character must be alphabetic [a-z or A-Z], or an
    underscore [_].

-   The remaining characters must be alphabetic [a-z or A-Z], numeric
    [0-9], an underscore [_], period [.], or dash [-].

-   Spaces are not allowed.

`Token` values are case sensitive. `"This"` does not match `"this"` in searches.

A tool developer may wish to assign UUID values to ID flags. UUIDs may
start with a numeric character, which is invalid for NCName. To ensure a
valid datatype when using a UUID value in an ID field, consider
prepending "uuid-" to the UUID value.

**For more information about the use of IDs in OSCAL, see *Section*
*2.5,* *Assigning Identifiers*.**

## Working With href Flags

All OSCAL-based `href` flags are URIs formatted according to [section 4.1
of RFC3986](https://tools.ietf.org/html/rfc3986#section-4.1). When
assembling or processing an OSCAL-based FedRAMP file, please consider
the following:

**Absolute Paths**: When using an absolute path within a FedRAMP OSCAL
file, the path must be publicly accessible from any location on the
Internet, to ensure agency and FedRAMP reviewers can reach the
information.

Tool developers are encouraged to validate paths before storing or using
them in OSCAL files and raise issues to users if paths are not
reachable.

**Relative Paths**: All relative paths are assumed to be based on the
location of the OSCAL file, unless tools are explicit as to other
handling. Sensitive external documents should travel with the OSCAL file
and be linked using a relative path.

**Internal Locations**: These URI fragments appear as just a hashtag (#)
followed by a name, such as `#a3e9f988-2db7-4a14-9859-0a0f5b0eebee`. This
notation points to a location internal to the OSCAL content. Typically,
this references to a `resource` assembly, but may reference to any field
or assembly with a unique ID or UUID.

If only a URI fragment (internal location) is present, the OSCAL tool
must strip the hashtag (#) and treat the remaining string as a UUID
reference to a resource. The resource may exist in the current OSCAL
file, or one of the imported OSCAL files in the stack as described in
*Section 2.1, File Content Concepts*.

For example, the following OSCAL content contains a `href` flag with a URI
fragment:

### URI Fragment Example
 {{< highlight xml "linenos=table" >}}
 <system-characteristics>
  <authorization-boundary>
  <diagram uuid="a04b5a0c-6111-420c-9ea3-613629599213">
  <link href="#a3e9f988-2db7-4a14-9859-0a0f5b0eebee"/>
  <caption>Authorization Boundary Diagram</caption>
  </diagram>
  </authorization-boundary>
 </system-characteristics>
 {{< /highlight >}}

When a tool processes the above example, it should look inside the
document for a field or assembly with a UUID of
`"a3e9f988-2db7-4a14-9859-0a0f5b0eebee"`. This can be accomplished with
the following XPath query:
{{< highlight xml "linenos=table" >}}
//*[@uuid="a3e9f988-2db7-4a14-9859-0a0f5b0eebee"]
{{< /highlight >}}
If this is found to point to a resource assembly, see the *Attachments
and Embedded Content in OSCAL Files* section for additional handling.

The name of the field or assembly referenced by the above URI fragment
can be determined using the following XPath 2.0 query:
{{< highlight xml "linenos=table" >}}
//*[@uuid="uri-fragment" | @id="uri-fragment"]/name()
{{< /highlight >}}
To express this in XPath 1.0, you must use the following:
{{< highlight xml "linenos=table" >}}
name(//*[@uuid="uri-fragment" | @id="uri-fragment"])
{{< /highlight >}}
The above query will return "resource", if the URI Fragment references
the UUID of a `resource` assembly.

## Markup-line and Markup-multiline Fields in OSCAL

As with most machine-readable formats, most of OSCAL's fields are
intended to capture short, discrete pieces of information; however,
sometimes users require content to be formatted using features such
bold, underline, and italics.
{{<callout>}}
_For markup-line and markup-multi-line, a subset of HTML is used to format XML-based OSCAL files, while Markdown is used to format JSON-based OSCAL files._
{{</callout>}}

OSCAL provides two types of fields for this purpose:

-   **markup-line**: Allows some formatting within a single line of
    text.

-   **Markup-multiline**: Allows all the markup-line formatting, plus
    allows multiple lines, ordered/ unordered lists, and tables.

In OSCAL-based XML files, markup-line and -multiline uses a subset of
HTML.

In OSCAL-based JSON files, markup-line and -multiline uses a subset of
markdown.

**NIST has implemented only a subset of formatting tags from these
standards.** This is to ensure formatted content converts completely and
consistently between XML and JSON in either direction.

Both *markup-line* and *markup-multiline* support:

-   emphasis and important text

-   inline code and quoted text

-   sub/super-script

-   images and links

*Markup-multiline* also supports:

-   Paragraphs

-   Headings (Levels 1-6)

-   Preformatted text

-   Ordered and Unordered Lists

-   Tables

For a complete list of markup-line and markup-multiline features, please
visit:
[[https://pages.nist.gov/OSCAL/reference/datatypes/#markup-data-types]](https://pages.nist.gov/OSCAL/reference/datatypes/#markup-data-types)

## Working with Markup-multiline Content

In JSON, markup-multiline is based on Markdown syntax and requires no
special handling. XML-based markup-multiline fields require all content
to be enclosed in one of the following tags: `<p>`, `<h1>` - `<h6>`,
`<ol>`, `<ul>`, `<pre>`, or `<table>`. At least one of these tags must
be present. More than one may be present. All text must be enclosed
within one of these tags.

The example below is a common misuse of markup-multiline. The
description contains text, but the text is not enclosed in one of the
required tags. This will produce an error when checked with the OSCAL
schema.


### Incorrect Markup-multiline Representation
{{< highlight xml "linenos=table" >}}
  <system-characteristics>
    <!-- cut -->
    <description>The xyz system performs ...</description>
  </system-characteristics>
{{< /highlight >}}
  

The simplest way to correct the error is to enclose the text in
`<p></p>` tags, within the `description` field.

### Correct Markup-multiline Representation
{{< highlight xml "linenos=table" >}}
  <system-characteristics>
    <!-- cut -->
    <description>
        <p>The xyz system performs ...</p>
    </description>
  </system-characteristics>
{{< /highlight >}}
  

The example below demonstrates a correct use of markup-multiline in XML.
Please note, the inclusion of a `<p />` tag on a line by itself inserts
an empty paragraph. Within XML and HTML, this is treated as a shortcut,
and is interpreted as `"<p></p>"`.

### Correct Markup-multiline Representation
{{< highlight xml "linenos=table" >}}
  <system-characteristics>
    <!-- cut -->
    <description>
        <p>The <b>xyz system</b> performs ... </p>
        <p>The xyz system further supports ... as follows:</p>
        <table>
            <tr>
                <td>Cell A1</td>
                <td>Cell B1</td>
            </tr>
            <tr>
                <td>Cell A2</td>
                <td>Cell B2</td>
            </tr>
        </table>
        <h1>Big Header</h1>
        <p>More detail</p>
        <p><img alt="alt text" src="url" title="title text"/></p>
    </description>
  </system-characteristics>
{{< /highlight >}}

For more information, please visit:
[https://pages.nist.gov/OSCAL/reference/datatypes/#markup-data-types](https://pages.nist.gov/OSCAL/reference/datatypes/#markup-data-types)

## Special Characters in OSCAL

While OSCAL itself does not directly impose special character handling
requirements, XML and JSON do. Characters, such as ampersand (&),
greater than (>), less than (<), and quotes (") require special
treatment in OSCAL files, depending on the format. For a complete list
of special characters and the appropriate treatment for each format,
please visit:

[https://pages.nist.gov/OSCAL/reference/datatypes/#specialized-character-mapping](https://pages.nist.gov/OSCAL/reference/datatypes/#specialized-character-mapping)

