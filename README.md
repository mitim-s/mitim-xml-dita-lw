# DITA Lightweight JSON Schema

This repository contains the JSON Schema Draft 2020-12 for DITA Lightweight (DITA-Lw). These schemas are designed to validate DITA Lightweight content, ensuring compliance with the DITA-Lw specification.

## Features

- **Validation**: Provides JSON schemas for validating DITA Lightweight topics, maps, and domains.
- **Extensibility**: Supports customization and extension for specific use cases.
- **Standards Compliance**: Adheres to the DITA Lightweight specification.

## Structure

The repository includes the following schemas:
- `common_xml_schema.js`: Common definitions and reusable components.
- `ditaarch_schema.js`: Schema for DITA architecture.
- `highlightDomain_schema.js`: Schema for the highlight domain.
- `lw-map_schema.js`: Schema for DITA Lightweight maps.
- `lw-topic_schema.js`: Schema for DITA Lightweight topics.

The schema contains additional XML information in 'editor__________node_______schema___` keyword.

## Usage

1. Import the required schema into your project.
2. Use a JSON schema validator to validate your DITA Lightweight content against the schema.

Example:
```javascript
import Ajv from 'ajv';
import { lw_topic } from './json_schema_ditalw/lw-topic_schema.js';

const ajv = new Ajv();
ajv.addKeyword({
    keyword: "editor__________node_______schema___",
    schemaType: "object",  
    validate: function validate() {
        return true;
    },
    errors: false
});

const validate = ajv.compile(lw_topic);

const data = {
  // Your DITA Lightweight topic JSON
};

if (validate(data)) {
  console.log('Validation successful!');
} else {
  console.error('Validation failed:', validate.errors);
}
```

## License

![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)
This project is licensed under the [MIT License](https://opensource.org/licenses/MIT). You are free to use, modify, and distribute the schemas in accordance with the license terms.

## About

The JSON schemas were generated using the MITIM XML Editor (version 1.3.111) and are maintained by MITIM Professional Services DOO. These schemas are based on the JSON Schema 2020-12 release.

For more information about DITA Lightweight, visit the [official DITA website](https://www.oasis-open.org/committees/dita/).
