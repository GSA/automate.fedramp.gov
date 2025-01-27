---
title: The OSCAL CLI
weight: 230
---

# OSCAL CLI Documentation for FedRAMP

## Overview

The OSCAL Command Line Interface (CLI) is a tool for validating and processing OSCAL content against FedRAMP requirements.

## Get Started

To learn more about how to use the OSCAL CLI and FedRAMP constraints to validate your FedRAMP OSCAL documents, please see the [FedRAMP OSCAL Constraints](https://github.com/GSA/fedramp-automation/blob/8c9fa7685dee736d3ba17bbb98858ad20fbd194a/src/validations/constraints/README.md) documentation on GitHub.

## Commands

The following are a brief summary of the most commonly used OSCAL CLI commands when working with FedRAMP OSCAL documents.


### Validate
Checks that the specified OSCAL file is well-formed and valid per OSCAL model and any additional specified constraints. 

```bash
oscal-cli validate <file> -c <constraint-file> [options]
```

### Convert  
Converts an OSCAL source file to the specified file format (e.g., XML, JSON, or YAML). 

```bash
oscal-cli metaschema validate <file> -c <style-guide> [options]
```

### Profile Resolution
Creates a new tailored OSCAL catalog by combining baseline imported controls and applying any modifications, as specified in the source profile.

```bash
oscal-cli resolve-profile <profile-file>
```

### Metaschema Validate
Validates that a metaschema file is well-formed and valid per the specified constraint definitions.

```bash
oscal-cli metaschema validate <file> -c <style-guide> [options]
```

## FedRAMP Validation Examples

### Validating SSP Against FedRAMP Constraints

```bash
oscal-cli validate path/to/ssp.xml \
  -c path/to/fedramp-external-allowed-values.xml \
  -c path/to/fedramp-external-constraints.xml
```

## Understanding Validation Errors

### Common Error Messages

1. UUID Warning:
```
[WARNING] [.../protocol[1]] It is a best practice to provide a UUID.
```
**Resolution**: Add a unique UUID to the specified element.

2. Constraint Violations:
- Invalid allowed values
- Missing required fields
- Pattern matching failures

## SARIF Output Integration

SARIF (Static Analysis Results Interchange Format) provides detailed validation results viewable in VS Code.

### Generate SARIF Output

```bash
oscal-cli validate path/to/file.xml \
  -c path/to/constraints.xml \
  --sarif-include-pass \
  -o results.sarif.json
```

### SARIF Features
- Detailed error locations
- Stack traces for debugging
- Pass/fail results for each rule
- VS Code integration for visual feedback

## Best Practices

1. Always validate against both allowed values and external constraints
2. Enable SARIF output for detailed debugging in VS Code
3. Address warnings even if they don't cause validation failures
4. Keep constraint files updated with latest FedRAMP requirements

## Command Options Reference

### Global Options
- `--help`: Display command help
- `-o, --output`: Specify output file
- `--sarif-include-pass`: Include passing results in SARIF output
- `--show-stack-trace`: Display full error stack traces

### Validation Options
- `-c, --constraint`: Specify constraint file (multiple allowed)
- `    --as=<FORMAT>                  `   source format: XML, JSON, or YAML
- ` -c <URL>                          `   additional constraint definitions
- `    --disable-constraint-validation`   do not perform constraint validation
- `    --disable-schema-validation`       do not perform schema validation
- ` -h,--help               `             display help message
- `    --no-color           `             do not colorize output
- ` -o <FILE>               `             write SARIF results to the provided FILE
- ` -q,--quiet              `             minimize output to include only errors
- `    --sarif-include-pass`              include pass results in SARIF
- `    --show-stack-trace `               display the stack trace associated with an error
- `    --version       `                  display the application version
