---
title: Metaschema Validation
weight: 220
---
# Metaschema Validation

Maintainers of [the core OSCAL models](https://github.com/usnistgov/OSCAL/tree/main/src/metaschema) and the [FedRAMP OSCAL Constraints](https://github.com/GSA/fedramp-automation/tree/develop/src/validations/constraints) use Metaschema. The Metaschema Information Modeling Framework [has several capabilities](https://framework.metaschema.dev/specification/overview/), including validating the OSCAL data models in JSON, XML, or YAML formats with a unified framework to ease maintenance for maintainers and community adopters.

The use of Metaschmea for OSCAL modeling allows for developers to use [Metaschema constraints](https://framework.metaschema.dev/specification/syntax/constraints/). Metaschema constraints are a robust mechanism to declaratively describe requirements for OSCAL data elements, be it in JSON, XML, or YAML, independently or in relation to one another. Developers may also use variables in constraints to cache important data for one or more constraints to facilitate [DRY constraint code and not repeat yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself).

There are currently [six types of constraints](https://framework.metaschema.dev/specification/syntax/constraints/#constraint-types), `allowed-values`; `expect`; `has-cardinality`; `index`; `index-has-key`; `is-unique`; and `matches`, to address different use cases and common patterns of requirement definition. Each constraint type has a similar structure.
