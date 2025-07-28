# Experience Notation (.xnote)

**Experience Notation** is a structured language for modelling user journeys, decisions, personas, and interactions in a readable and simulation-ready format. It is designed for LLM prompting, human authoring, and machine parsing. Originally developed as part of the [Demoscope.ai](https://demoscope.ai) platform — a commercial service for synthetic user feedback — it is now available as an open-source specification.

---

## Key Concepts

Experience Notation is:

* **Readable** — Uses indentation and labels to keep files accessible.
* **Structured** — Validates via both EBNF and JSON Schema.
* **Expressive** — Captures emotional context, UI interaction, branching.
* **Modular** — Supports external references and journey composition.
* **LLM-compatible** — Can be generated, simulated, and adapted through prompts.

Explore the full [Glossary](https://experience-notation.com/reference/glossary/) for key terms.

---

## Example

```xnote
Journey: simple-onboarding
Title: Simple Onboarding Journey
Personas:
  Persona A: New User
    Traits: { tech_savvy=false }
    Experience: Curious and slightly anxious
Events:
  Event 1: App Launch
    Step 1:
      User: Persona A
      Action: Opens the mobile app
      UI-Element: Splash screen
      Tag: entry
  Event 2: Sign-Up
    Step 1:
      User: Persona A
      Action: Enters email and password
      UI-Element: Registration form
    Step 2:
      User: Persona A
      Action: Taps "Create Account"
      UI-Element: Call-to-action button
      Tag: confirmation
```

---

## Learn More

* Full documentation at: [https://experience-notation.com](https://experience-notation.com)
* Getting started: [Getting Started Guide](https://experience-notation.com/getting-started/what-is-xnote/)
* Browse examples: [`examples/`](./examples)
* Learn to validate: [Validation Guide](https://experience-notation.com/spec/validation/)
* Use with LLMs: [AI Integration](https://experience-notation.com/ai/structured-prompting/)

---

## In Practice

Experience Notation powers [Demoscope.ai](https://demoscope.ai), a commercial platform for synthetic user feedback and behaviour simulation. `.xnote` files are used to structure multi-step journeys and guide persona interactions in production environments.

---

## Schema & Grammar

* [EBNF Syntax](./spec/Experience-Notation.ebnf)
* [JSON Schema](./spec/experience-notation.schema.json)

You can validate `.xnote` files using:

* `$schema` field in supported editors
* `ajv-cli` for JSON structure validation
* Experimental tools (see roadmap)

---

## Citation

If you use Experience Notation in academic work, please cite:

**Nikolaos Maniatis.** *Experience Notation Schema (v1.1)*.
[https://schemas.experience-notation.com/experience-notation.schema@v1.1](https://schemas.experience-notation.com/experience-notation.schema@v1.1)
Available at: [https://github.com/context-notation/experience-notation](https://github.com/context-notation/experience-notation)
Licensed under Apache 2.0. Maintained by The Cato Bot Company Limited.

**APA:**
Maniatis, N. (2025). *Experience Notation Schema (v1.1)*. [https://github.com/context-notation/experience-notation](https://github.com/context-notation/experience-notation)

---

## Roadmap

* [ ] Bidirectional JSON ↔ `.xnote` parser
* [ ] EBNF validation and linting tool
* [ ] Web-based editor / playground
* [ ] SDKs and developer tools

---

## Contributing

We welcome contributions from the community! Whether you're reporting a bug or suggesting a feature your input is greatly appreciated.

📣 [GitHub Discussions](https://github.com/context-notation/experience-notation/discussions)

---

## Licence

The Experience Notation DSL and its accompanying JSON Schema are released under the **Apache 2.0 Licence**.

See the `LICENSE` file for the full text.

---

### Maintainer

The schema was authored by **Nikolaos Maniatis** and is maintained and distributed by **The Cato Bot Company Limited**.

For questions, support, or to report issues, please use the **[GitHub Issues](https://github.com/context-notation/experience-notation-schema/issues/new)** section of this repository.

For commercial enquiries, long-term support, or integration partnerships, please contact:
📧 **[hi@iamcatobot.me](mailto:hi@iamcatobot.me)**

---
