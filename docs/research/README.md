# Research Documents

Guidelines for creating and maintaining research reports in this directory.

---

## Document Purpose

Each research document is a landscape overview of a specific domain — tools, standards, frameworks, or methodologies — written to inform decision-making for the bs-factory project. These are reference documents, not specifications or proposals.

---

## File Naming

Use lowercase kebab-case: `<topic>.md`

Examples: `software-engineering-standards.md`, `ai-orchestration-models.md`

---

## Document Structure

Every research document follows this canonical structure:

```
# Title
Opening description.

---

## Background

## [Core Sections]

## Selection Guide

## Industry Trends
```

### Title

A short noun phrase as an H1 heading. No colons, subtitles, or ampersands.

```markdown
# Software Engineering Standards
# AI-Driven Workflow Orchestration Models
# Requirements and Test Tracking
```

### Opening Description

One to two sentences immediately after the title. States what the document covers and its purpose or audience. No heading — just a paragraph.

```markdown
A survey of established and emerging orchestration models for AI-driven
software development workflows. Covers architecture, maturity, adoption,
and common requirements to inform a build-vs-buy decision.
```

### Background

An `## Background` section follows the opening description, separated by a horizontal rule (`---`). Provides historical context, motivation, or framing for why the domain matters. Keep it concise — typically one to three paragraphs.

### Core Sections

The middle of the document contains domain-specific content organized into H2 sections. These vary by topic but should follow consistent formatting for individual entries (see Entry Format below).

### Selection Guide

An `## Selection Guide` section near the end of the document. Contains a recommendation table or decision matrix mapping use cases or organization profiles to recommended tools, standards, or approaches.

### Industry Trends

An `## Industry Trends` section closes the document. Covers market direction, adoption patterns, and emerging developments. Use a bulleted list where each item leads with a bolded trend name.

```markdown
- **Trend name** — description of the trend and its implications.
```

---

## Entry Format

Individual tools, standards, or frameworks are formatted as heading-level entries with a consistent set of metadata fields.

### Heading Level

- Entries directly under an H2 section use `###`.
- Entries under an H3 subsection (e.g., "Enterprise Solutions", "Open-Source Options") use `####`.

### Entry Structure

```markdown
### Tool or Standard Name

Description paragraph. One to three sentences covering what it is, what it does, and any distinguishing characteristics.

- **Website:** [example.com](https://example.com/)
- **Best for:** One-line statement of ideal use case or audience
```

For tools with a source repository rather than a product page, use **Repository:** instead of **Website:**.

### Metadata Fields

Use only fields that are relevant. Not every entry needs every field. The following fields are available, listed in preferred order:

| Field | Use when |
|-------|----------|
| **Website:** | The tool has a product or project page |
| **Repository:** | The tool is open-source with a primary repo |
| **License:** | Relevant for open-source tools |
| **Current version:** | Relevant for versioned standards |
| **Maturity:** | Useful for comparing tools at different stages |
| **Deployment:** | The tool has distinct deployment options (Cloud, on-premises, both) |
| **Industries:** | The tool or standard has specific industry adoption |
| **Best for:** | Always include when possible — the single most useful field for readers |
| **Limitation:** | Notable constraints worth flagging |

### Links

Include URLs in entries when available. Use inline markdown links with descriptive text:

```markdown
- **Website:** [example.com](https://example.com/)
```

---

## Tables

Use markdown tables for comparison matrices and reference summaries. Align content for readability in source. Tables appear in two contexts:

- **Within core sections** — for compact comparisons (e.g., SPICE domain adaptations).
- **In the Selection Guide** — mapping use cases to recommendations.

---

## Horizontal Rules

Use `---` on its own line to separate H2 sections. Every H2 section boundary should have a horizontal rule above it.

---

## Style Notes

- Write in plain, direct prose. Avoid marketing language.
- Use em dashes (`—`) rather than parenthetical asides where possible.
- Bold field labels in metadata lists: `- **Field:** value`.
- Do not include cross-reference links between research documents. Each document should stand on its own.
- Do not include a table of contents. The heading structure serves as the navigational aid.
