---
title: Metaschema Validation
weight: 220
---

# Metaschema Validation

## Overview

Metaschema validation is a crucial step in ensuring OSCAL documents comply with both the OSCAL schema requirements and FedRAMP-specific constraints. This validation process occurs at two levels:

1. Basic OSCAL schema validation
2. FedRAMP-specific constraints validation

## Basic OSCAL Validation

Basic validation ensures your OSCAL document follows the core OSCAL schema requirements. This validation checks that your document:
- Is well-formed XML/JSON/YAML
- Follows OSCAL schema rules
- Contains required elements and properties
- Uses correct data types

A successful basic validation indicates your document is metaschema-valid according to OSCAL specifications. For detailed information on using the OSCAL CLI for validation, see the [OSCAL CLI documentation](oscal-cli).

## FedRAMP Constraints Validation

While basic validation ensures OSCAL compliance, FedRAMP requires additional validation against specific constraints. These constraints enforce FedRAMP-specific requirements through:
- Allowed values in specific fields
- Required FedRAMP-specific elements
- Proper formatting of FedRAMP-required content
- Relationship rules between elements

The OSCAL CLI supports both basic schema validation and FedRAMP constraints validation. See the [OSCAL CLI documentation](oscal-cli) for detailed command examples and options.

## Understanding Validation Results

### Successful Validation
A successful validation will show no errors and indicate the document is both:
- Metaschema-valid (compliant with OSCAL schemas)
- FedRAMP-compliant (when validated with FedRAMP constraints)

### Common Validation Issues

1. Schema Validation Errors:
   - Missing required elements
   - Invalid data types
   - Malformed XML/JSON/YAML

2. FedRAMP Constraint Violations:
   - Invalid allowed values
   - Missing FedRAMP-required fields
   - Incorrect relationship patterns

## Best Practices

1. Always validate at both levels:
   - Basic OSCAL schema validation
   - FedRAMP constraints validation

2. Use SARIF output for detailed analysis:
   ```bash
   oscal-cli validate path/to/document.xml \
     -c path/to/constraints.xml \
     --sarif-include-pass \
     -o results.sarif.json
   ```

3. Address all warnings, even if they don't cause validation failures

4. Keep constraint files updated with latest FedRAMP requirements

## Development Tool Integration

The validation process can be integrated with development tools through SARIF output. For example, VS Code integration provides:
- Visual error indicators
- Quick navigation to issues
- Detailed error descriptions
- Validation result tracking

For detailed information about validation options and SARIF integration, refer to the [OSCAL CLI documentation](oscal-cli).
