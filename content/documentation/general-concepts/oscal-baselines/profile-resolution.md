---
title: Profile Resolution
weight: 177
---
# Profile Resolution

Profiles are intended to identify upstream sources of control definition
information and show only the changes to those upstream sources. This
enables humans and computers to trace control definition changes back to
their source framework.

{{< callout >}}
Profile resolution flattens or merges a profile and its imported catalog(s) and profiles into a single OSCAL file using the catalog syntax.
{{</ callout >}}

While this ensures traceability of selected controls and modified
content, it can also be resource intensive.

{{< figure src="/img/content-figure-14.png" title="Profile Resolution." alt="Figure showing how profile resolution flattens or merges a profile and its imported catalog(s) and profiles into a single OSCAL file using the catalog syntax." >}}

This single file is essentially a pre-processed result of the profile
import and modification content. A resolved profile catalog is useful
for the FedRAMP baselines, given their static nature. Any tool that would
normally open an OSCAL-based FedRAMP profile and process it against the
NIST SP 800-53 catalog can instead simply use the resolved-profile
catalog.

Each FedRAMP XML and JSON baseline profile has a resolved profile
catalog in the same location as the pre-processed profile. Where
available, these may be used by tools to save processing time.

The `merge` assembly within an OSCAL profile offers a profile resolver
control over how the final file is organized. To maintain the same
organization as within the catalog, simply use the `as-is` field and set
it to `"yes"`.

The complete profile syntax is available here:

<https://pages.nist.gov/OSCAL/concepts/layer/control/profile/>

## Resolved Profile Catalogs

The resolved profile catalog for each FedRAMP baseline is
pre-processing the profile and catalog to produce the resulting data.
This reduces overhead for tools by eliminating the need to open and
follow references from the profile to the catalog. It also includes only
the catalog information relevant to the baseline, reducing the overhead
of opening a larger catalog.

Where available, tool developers have the option of following the links
from the profile to the catalog as described above or using the resolved
profile catalog.

Developers should be aware that at this time, catalogs and profiles
remain relatively static. As OSCAL gains wider adoption, there is a risk
that profiles and catalogs will become more dynamic, and a resolved
profile catalog becomes more likely to be out of date. Early adopters
may wish to start with the resolved profile catalog now, and plan to add
functionality for the separate profile and catalog handling later
in their product roadmap.

## NIST's Profile Resolution Tool

NIST created a profile resolution specification, and built a profile
resolution capability based on that specification. The specification can
be found here:

<https://github.com/usnistgov/OSCAL/tree/main/src/specifications/profile-resolution>

The actual tool can be found here:

<https://github.com/usnistgov/OSCAL/tree/v1.1.2/src/utils/resolver-pipeline>

Currently the tool requires the profile and all imported catalogs and
profiles to be in XML format. For now, JSON content must be converted to
XML before using this tool.

The tool requires an XSLT 3.1 processor, which is the same requirement
for XML to JSON and JSON to XML conversions.

All XSL files provided at the link above must be in the same directory.
Only oscal-profile-RESOLVE.xsl must be identified to the XSLT processor.
All other files are called by this file as part of processing.

It is also possible to run the scripts directly from the NIST OSCAL
repository by supplying the following URL directly to the XSLT
processor:

<https://github.com/usnistgov/OSCAL/blob/v1.1.2/src/utils/resolver-pipeline/oscal-profile-RESOLVE.xsl>

This is a new capability provided by OSCAL and leveraged by FedRAMP.
Please report bugs or provide feedback related to this tool directly to
NIST at <oscal@nist.gov> or by submitting an issue here:

<https://github.com/usnistgov/OSCAL/issues>
