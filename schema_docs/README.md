# Experience Notation JSON Schema

This directory contains the **official JSON Schema** for Experience Notation (`.expn`) documents. The schema is critical for ensuring the structural correctness of your Experience Notation files and for enabling robust integration with development tools.

---

## File Overview

* **`experience-notation.schema.json`**: The core JSON Schema definition, conforming to **Draft 2020-12**.

---

## Purpose of the JSON Schema

The JSON Schema serves several key purposes:

* **Validation**: Defines the precise structure, data types, and constraints for valid Experience Notation documents. This allows you to programmatically validate `.expn` files (once converted to JSON) to ensure they comply with the DSL's rules.
* **IDE Auto-completion & Real-time Validation**: Many Integrated Development Environments (IDEs) and text editors can leverage JSON Schemas to provide intelligent auto-completion, syntax highlighting, and real-time validation as you edit JSON.
* **Code Generation**: In advanced use cases, the schema can be used to automatically generate data models or interfaces in various programming languages, streamlining the development of parsers, converters, and applications that interact with Experience Notation data.
* **Documentation**: The schema itself acts as formal, machine-readable documentation of the Experience Notation data structure.

---

## How to Use the JSON Schema

### 1. Validating Experience Notation Documents (as JSON)

Once you have converted an `.expn` script into its JSON representation (handled by the official parser/converter libraries), you can validate that JSON against the schema.

#### a) JavaScript (using Ajv)

First, install **Ajv**:

```bash
npm install ajv
```

Then, in your JavaScript code:

```javascript
const Ajv = require("ajv");
const ajv = new Ajv(); // Options can be passed here, e.g., { allErrors: true }

// Load your schema
const schema = require('./experience-notation.schema.json');

// Compile the schema
const validate = ajv.compile(schema);

// Your Experience Notation document as a JSON object
const expnDocument = {
  "ebnfVersion": "1.1", 
  "syntaxVersion": "1.0",
  "journeyTitle": "Simple User Onboarding",
  "journeyDescription": "A basic journey for new user registration and first login.",
  "events": [
    {
      "event": "Account Creation",
      "id": "EVT-001",
      "steps": [
        {
          "step": "User Registration",
          "user": "New User",
          "action": "Fills out registration form",
          "uiElement": "Registration Page"
        }
      ],
      "personas": [
        {
          "persona": "Referenced Persona",
          "externalSource": "https://example.com/personas/referenced-user-v1.json"
        }
      ]
    }
  ],
  "personas": [
    {
      "persona": "Global User Type A",
      "id": "P-001",
      "externalSource": "https://external-persona-repo.com/user-type-a"
    }
  ]
};

const isValid = validate(expnDocument);

if (isValid) {
  console.log("Experience Notation document is valid!");
} else {
  console.error("Experience Notation document is NOT valid:");
  console.error(validate.errors);
}
```

#### b) Python (using `jsonschema`)

First, install the **jsonschema** library:

```bash
pip install jsonschema
```

Then, in your Python code:

```python
import json
from jsonschema import validate, ValidationError

# Load your schema
with open('experience-notation.schema.json', 'r') as f:
    schema = json.load(f)

# Your Experience Notation document as a Python dictionary
expn_document = {
    "ebnfVersion": "1.1",  # Updated EBNF Version
    "syntaxVersion": "1.0",
    "journeyTitle": "Simple User Onboarding",
    "journeyDescription": "A basic journey for new user registration and first login.",
    "events": [
        {
            "event": "Account Creation",
            "id": "EVT-001",
            "steps": [
                {
                    "step": "User Registration",
                    "user": "New User",
                    "action": "Fills out registration form",
                    "uiElement": "Registration Page"
                }
            ],
            "personas": [
                {
                    "persona": "Referenced Persona",
                    "externalSource": "https://example.com/personas/referenced-user-v1.json"
                }
            ]
        }
    ],
    "personas": [
        {
            "persona": "Global User Type A",
            "id": "P-001",
            "externalSource": "https://external-persona-repo.com/user-type-a"
        }
    ]
}

try:
    validate(instance=expn_document, schema=schema)
    print("Experience Notation document is valid!")
except ValidationError as e:
    print("Experience Notation document is NOT valid:")
    print(e)
```

---

### 2. IDE Integration

Many modern IDEs and text editors provide built-in or plugin-based support for JSON Schema, enabling features such as auto-completion and real-time validation.

#### VS Code

VS Code has excellent built-in support for JSON Schema. You can associate the `experience-notation.schema.json` file with your JSON files (e.g., `.expn.json`) by adding a `$schema` property to the root of your JSON document:

```json
{
  "$schema": "./schema/experience-notation.schema.json",
  "ebnfVersion": "1.1",
  "syntaxVersion": "1.0",
  "journeyTitle": "My Journey"
  // ... rest of your document
}
```

Alternatively, you can configure VS Code’s `settings.json` to apply the schema automatically:

```json
{
  "json.schemas": [
    {
      "fileMatch": ["*.expn.json"],
      "url": "./schema/experience-notation.schema.json"
    }
  ]
}
```

#### Other Editors (e.g., JetBrains IDEs, Sublime Text)

Refer to your editor’s documentation for instructions on configuring JSON Schema validation and auto-completion. This typically involves setting the schema file path or URL for files matching a given pattern.

---

## Summary

By following these practices, developers can fully leverage the **Experience Notation JSON Schema** to guarantee the **quality, structure, and consistency** of their user journey definitions across teams, tools, and workflows.

