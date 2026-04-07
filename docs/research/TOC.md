# Research Documents — Table of Contents

Documents are ordered from broad foundational context through to applied tooling and implementation concerns.

---

## 1. Standards Landscape

### [Software Engineering Standards](01-software-engineering-standards.md)

The entry point for the knowledge base. Surveys the full landscape of process and quality frameworks — CMMI, ISO/IEC 33000, ASPICE, automotive and aerospace domain adaptations — and traces the two lineages (CMM and SPICE) that underpin nearly everything else. Read this first to understand the terrain.

---

## 2. Selected Standards Framework

### [Process Standards](02-process-standards-summary.md)

Narrows the field to the five ISO/IEC/IEEE standards selected for the project's lifecycle governance: 15288 (systems), 12207 (software), 29110 (VSE profiles), 29148 (requirements engineering), and 15289 (documentation content). Covers scope, document artifacts, and how the standards interrelate.

### [Process Standards — Documentation to Order](03-iso-docs.md)

A procurement reference: full citations, edition details, and source URLs for the selected standards plus supporting safety and electrical standards. An appendix to the standards framework rather than a reading document.

---

## 3. Domain-Specific Adaptation — Automotive SPICE

### [Automotive SPICE — Key References](04-aspice-references.md)

Curated pointer list for the official ASPICE 4.0 materials: VDA home, Process Reference Model PDF, pocket guide, and practitioner workbooks. Use this to locate primary sources.

### [ASPICE 4.0 and ISO/IEC/IEEE Process Standards Integration Analysis](05-aspice-iso-integration-analysis.md)

The deepest document in the standards track. Compares ASPICE 4.0 process-by-process against the selected ISO standards, identifies alignment and gaps, and proposes an MVP process solution for achieving ASPICE compliance on non-safety-critical hardware-plus-software products using ISO as the foundation.

---

## 4. Lifecycle Knowledge

### [Architecture and Requirements Lifecycles](06-architecture-and-requirements-lifecycles.md)

Examines how architecture knowledge and requirements knowledge evolve through their respective lifecycles — where they overlap, where they diverge, which standards govern each, and whether projects need to treat them as separate or unified disciplines.

---

## 5. Tooling

### [Software and System Architecture Documentation Tools](07-architecture-documentation-tools.md)

A landscape survey of tools and frameworks for architecture documentation: diagram-as-code tools, ADR frameworks, C4 model tooling, enterprise architecture platforms, and AI-assisted documentation tools. Includes a documentation lifecycle model and maturity framework for evaluating architectural artifacts.

### [Requirements and Test Tracking](08-requirements-and-test-tracking.md)

Covers methodologies (V-model, requirements-based testing, risk-based testing, traceability) and the full range of tools from enterprise ALM platforms to open-source alternatives. Includes a selection guide mapping organizational profiles to recommended tools.

---

## 6. Applied — AI-Driven Orchestration

### [AI-Driven Workflow Orchestration Models](09-ai-orchestration-models.md)

Surveys orchestration models and platforms for coordinating multiple AI coding agents across a codebase. The most project-specific document — informs the build-vs-buy decision for the bs-factory orchestration layer. Covers Gastown, Intent, and other emerging platforms.

---

## Meta

### [README](README.md)

Guidelines for creating and maintaining research documents in this directory: canonical structure, entry format, metadata fields, style notes, and naming conventions.
