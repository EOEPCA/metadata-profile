# Schemas

This directory contains the EOEPCA Metadata Profile (EMP) source schemas.  The schemas are managed
using JSON Schema (https://json-schema.org/draft/2020-12/schema) and represented
in YAML.

## Generating the JSON schema bundle

[Stoplight Studio](https://stoplight.io/studio) (free and open source) is a full GUI environment (web-based
or desktop) for designing schemas, models and APIs (JSON/YAML/OpenAPI).

To generate the EMP JSON schema, following these steps:

- open Stoplight Studio
- click "Open Existing Folder"
- point to the `schemas/` directory
- ensure schema has no errors ("0 Issues" in the top right pane)
- click "Open"
- on the right hand pane, right-click the file `resource.yaml` and select "Export"
- select the following from the dialogue box:
  - Format: JSON
  - References: Dereferened
  - X-Extensions: unchecked
- click "Save to file"
- save file to `schemas/resource-bundled.json`
- commit changes

A screenshot is shown below:

![Stoplight Studio Export](stoplight-studio-export.png "Stoplight Studio Export")

Note: the above are manual steps to verify and generate the JSON Schema bundle.  Future updates will
include automated workflow via GitHub Actions.

## Validating an EMP record

```bash
# install the check-jsonschema Python package
pip3 install check-jsonschema

# validate an EMP file on the command line
check-jsonschema --schemafile schemas/resource-bundled.json example-record.json
```
