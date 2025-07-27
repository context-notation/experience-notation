
# Experience Notation (.xnote)

**Structured User Journey Definition for Design, Analysis, and Simulation**

![Version](https://img.shields.io/badge/version-1.1.0-blue)
![License](https://img.shields.io/badge/license-Apache%202.0-brightgreen)
![EBNF](https://img.shields.io/badge/EBNF-Supported-blue)
![JSON Schema](https://img.shields.io/badge/JSON--Schema-Draft%202020--12-lightgrey)
![Last Updated](https://img.shields.io/badge/last%20updated-July%202025-informational)

---

## Overview

**Experience Notation (.xnote)** is a novel, human-readable, and machine-processable Domain Specific Language (DSL) designed for defining user journeys. It provides a structured, standardised method for documenting user experiences, bridging the gap between qualitative journey mapping and quantitative analysis or simulation.

By formalising the elements of a user journey, Experience Notation enables a new level of precision, consistency, and automation in customer experience (CX) design, product management, software development and behavioural analysis.

---

## Motivation: Solving the Journey Mapping Challenge

Traditional user journey mapping, while invaluable, often suffers from limitations that hinder its full potential:

* **Lack of Standardisation**: Maps vary widely in format and level of detail, making comparison and collaboration difficult across teams and projects.
* **Qualitative Bias**: Although rich in insight, traditional maps are often purely qualitative, making it difficult to derive quantifiable metrics or simulate scenarios.
* **Limited Machine Readability**: The free-form nature of many maps prevents direct integration with automated tools for validation, analysis, or simulation.
* **Disconnection from Development**: A common gap exists between journey maps and the actual product development process, leading to misinterpretation and inefficiency.

**Experience Notation** addresses these issues by providing a formal, structured, and machine-readable format for user journeys, enabling seamless integration into design, development, and analytical workflows.

---

## Key Features & Concepts

Experience Notation is built around a core set of elements that enable comprehensive and structured journey definitions:

* **Events**: Major checkpoints or distinct phases in a user's journey, providing high-level structure.
* **Steps**: Granular actions, interactions, and system responses occurring within an event, detailing user progression.
* **Personas**: Detailed profiles of users, including their experiences, interactions, adaptations, metrics, and metadata. Personas can be defined globally for reuse or inline for contextual insights.
* **External Persona References**: Ability to link persona definitions to external sources (e.g., a centralised persona management system) using a URI or identifier.
* **Conditional Logic**: Allows for the definition of branching paths and decision points using `IF... THEN... [ELSE...]` constructs.
* **Metrics**: Supports the inclusion of quantifiable data points (numbers, text, booleans) associated with personas, events, or steps for data-driven analysis.
* **Metadata & Tags**: Enables the use of flexible key-value pairs (`Meta:`) and categorical labels (`Tag:`) for added context, categorisation, and filtering.
* **References (`Ref:`)**: Permits linking to other elements by their unique IDs within the journey, promoting modularity and clarity.
* **Environmental Factors & Disruption**: Dedicated elements for describing contextual influences and potential interruptions during an event.

---

## Getting Started: A Quick Example

Below is a minimal example of an Experience Notation (`.xnote`) file:

```
EBNF-Version: 1.1
Syntax-Version: 1.0
Journey-Title: Simple User Onboarding
Journey-Description: A basic journey for new user registration and first login.

Event: Account Creation
  ID: EVT-001
  Step: User Registration
    User: New User
    Action: Fills out registration form
    UI-Element: Registration Page
  Step: Email Verification
    User: New User
    Action: Clicks verification link in email
    UI-Element: Email Client, Verification Page
  Persona: Referenced Persona
    External-Source: https://example.com/personas/referenced-user-v1.json

Event: First Login
  ID: EVT-002
  Step: Initial Login
    User: Registered User
    Action: Enters credentials
    UI-Element: Login Page
  Persona: Excited New User
    Experience: Feels welcomed and guided.
    Metrics: {"satisfaction": 8, "easeOfUse": "High"}
```

---

## Why Use Experience Notation? (Benefits)

* **Improved CX Design**: Create clearer, more consistent, and easily shareable journey maps.
* **Enhanced Collaboration**: Foster a common language and understanding across design, product, and engineering teams.
* **Data-Driven Insights**: Embed quantifiable metrics directly into journey definitions, enabling deeper and more accurate analysis.
* **Automated Validation**: Use the JSON Schema to validate journey documents and ensure structural correctness.
* **Machine Readability**: The structured format supports programmatic parsing and automation workflows.
* **Better Decision-Making**: Simulate journey variations (using future tools) to evaluate potential outcomes.
* **Standardisation**: Establish a consistent, organisation-wide framework for user journey documentation.

---

## LLM Integration & AI-Powered Workflows

Experience Notation documents are not solely intended for human readability and traditional tooling—they are also perfectly structured for integration with **Large Language Models (LLMs)** and other **AI-powered workflows**.

### Structured Prompting

The clear, hierarchical, and keyword-driven format of `.xnote` files makes them ideal for structured prompting of LLMs. You can provide an `.xnote` document and instruct an LLM to:

* **Summarise the User Journey**
  Generate a natural language narrative describing the journey, its events, and key steps.

* **Generate User Stories or Scenarios**
  Create detailed user stories or specific usage scenarios based on the defined journey paths and persona attributes.

* **Identify Pain Points or Opportunities**
  Analyse the journey for potential friction points or areas for improvement—especially when used alongside defined metrics or disruption elements.

* **Role-Play Personas**
  Direct the LLM to *"act as"* a specific persona from the document and describe their experience during a given event or step.

* **Schema-Guided Generation**
  By supplying the LLM with the Experience Notation EBNF or JSON Schema, you can guide it to generate syntactically correct and structurally valid `.xnote` content. This enables AI-assisted creation or expansion of journey documents while ensuring adherence to your DSL’s rules.

---

## Roadmap (High-Level)

Experience Notation is a new DSL with ambitious goals, and we are actively building the surrounding ecosystem to **maximise its effectiveness and adoption**.

Our immediate priorities and current progress include:

* **Official Parser & Converter Libraries**
  We are developing robust libraries in popular programming languages to convert `.xnote` scripts into machine-readable JSON documents, fully aligned with the Experience Notation JSON Schema. These libraries are currently undergoing **final testing prior to their initial release**, with a strong focus on robustness and consistency.

* **Experience Notation-Powered Simulation Service**
  Experience Notation **powers our commercial platform, [demoscope.ai](https://demoscope.ai)**, which delivers synthetic user insights and behavioural simulations. Interested users are encouraged to explore its capabilities via the site.

We remain committed to building a comprehensive, standards-driven ecosystem around Experience Notation to support a wide range of design, development, and analysis use cases.

---

## Contributing

We welcome contributions from the community! Whether you're reporting a bug or suggesting a feature your input is greatly appreciated.

Please refer to our `CONTRIBUTING.md` for detailed contribution guidelines.

---

## Licence

The Experience Notation DSL and its accompanying JSON Schema are released under the **Apache 2.0 Licence**.

See the `LICENSE` file for the full text.

---

### Maintainer

The schema was authored by **Nikolaos Maniatis** and is maintained and distributed by **The Cato Bot Company Limited**.

For questions, support, or to report issues, please use the **[GitHub Issues](https://github.com/context-notation/experience-notation-schema/issues/new)** section of this repository.

For commercial enquiries, long-term support, or integration partnerships, please contact:
📧 **[schemas@context-notation.com](mailto:schemas@context-notation.com)**

---

## Citation

If you use the Experience Notation DSL in academic work, please cite:

**Nikolaos Maniatis.** *Experience Notation (v1.1.0)*.  
https://schemas.experience-notation.com/experience-notation.schema@v1.1.0  
Available at: https://github.com/context-notation/experience-notation  
Licensed under Apache 2.0. Maintained by The Cato Bot Company Limited.

**APA:**  
Maniatis, N. (2025). *Experience Notation (v1.1.0)*. https://github.com/context-notation/experience-notation

**BibTeX:**
```bibtex
@misc{maniatis2025experience,
  author       = {Nikolaos Maniatis},
  title        = {Experience Notation (v1.1.0)},
  year         = {2025},
  howpublished = {\url{https://github.com/context-notation/experience-notation}},
  note         = {Available at: https://schemas.experience-notation.com/experience-notation.schema@v1.1.0. Licensed under Apache 2.0. Maintained by The Cato Bot Company Limited.}
}
```



