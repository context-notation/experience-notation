# Experience Notation (xnote) Examples

This directory contains a collection of `.xnote` files that demonstrate various features and use cases of the **Experience Notation DSL**. These examples are designed to help you understand the syntax, structure, and capabilities of xnote, serving as practical guides for creating your own journey documents.

Each example file is commented to explain its specific purpose and the DSL elements it showcases.

---

## Example Files Overview

Below is a summary of the example files provided and what each demonstrates:

---

### 1. [`simple-onboarding-journey.xnote`](simple-onboarding-journey.xnote)

* **Purpose**: Introduces the fundamental structure of an Experience Notation document.
* **Features Demonstrated**:

  * Basic `Journey-Title` and `Journey-Description`
  * `Event` definition and sequential `Step`s
  * `User`, `Action`, and `UI-Element`
  * Simple inline `Persona`
* **Learn**: The core building blocks of any xnote journey.

---

### 2. [`user-decision-flow.xnote`](user-decision-flow.xnote)

* **Purpose**: Illustrates how to incorporate conditional branching within a step.
* **Features Demonstrated**:

  * `Conditional:` with `IF... THEN... [ELSE...]` logic
* **Learn**: How to model decision points and non-linear flows in your journeys.

---

### 3. [`persona-showcase-journey.xnote`](persona-showcase-journey.xnote)

* **Purpose**: Highlights the flexibility of persona definitions.
* **Features Demonstrated**:

  * Defining `Persona`s both globally and inline
  * Use of attributes: `Experience`, `Interaction`, `Adaptation`, `Metrics`, and `Meta`
* **Learn**: Different ways to integrate persona insights into your journey.

---

### 4. [`external-persona-linking.xnote`](external-persona-linking.xnote)

* **Purpose**: Demonstrates how to link persona definitions from external URIs.
* **Features Demonstrated**:

  * Use of `External-Source:` to reference external persona data
* **Learn**: Centralised persona management and modularity for large-scale projects.

---

### 5. [`data-rich-journey.xnote`](data-rich-journey.xnote)

* **Purpose**: Shows how to embed quantifiable data.
* **Features Demonstrated**:

  * Use of `Metrics:` and `Meta:` with key-value pairs
  * Support for numerical, textual, and boolean values
* **Learn**: How to enrich journey definitions with analytical and contextual data.

---

### 6. [`contextual-journey.xnote`](contextual-journey.xnote)

* **Purpose**: Adds environmental and disruption data to events.
* **Features Demonstrated**:

  * `Environmental-Factors:` for external context
  * `Disruption:` to represent interruptions or issues
* **Learn**: How to reflect real-world challenges within your journey documents.

---

### 7. [`modular-journey-with-refs.xnote`](modular-journey-with-refs.xnote)

* **Purpose**: Demonstrates modularity and internal linking.
* **Features Demonstrated**:

  * Use of `Tag:` to categorise events and steps
  * Use of `Ref:` to link elements by `ID`
* **Learn**: Best practices for organising complex journeys and improving clarity.

---

### 8. [`comprehensive-customer-support-journey.xnote`](comprehensive-customer-support-journey.xnote)

* **Purpose**: A comprehensive example combining multiple DSL features.
* **Features Demonstrated**:

  * Multiple personas (including external links)
  * Nested conditional logic
  * Extensive use of metrics and metadata
  * Parallel events and cross-referencing
* **Learn**: The full expressive power of Experience Notation for modelling rich, realistic user journeys.

---

## How to Use These Examples

* **Read the `.xnote` files**
  Open each file in a plain text editor. Pay close attention to the inline comments (`#`), which explain the structure and purpose of each section.

* **Validate against the schema**
  Once your parser or converter libraries are in place, convert the `.xnote` files to JSON and validate them against the `experience-notation.schema.json` located in the `schema/` directory.

* **Experiment and extend**
  Modify the examples to explore how changes affect the structure and to deepen your understanding of the DSL.

---
