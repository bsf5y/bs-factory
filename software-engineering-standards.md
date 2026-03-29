# Software Engineering Standards

An overview of process standards, quality frameworks, and vocabulary standards for software and systems engineering. Standards help define a shared operating language where terms are clearly defined across teams, vendors, and stakeholders.

---

## Origins and Lineage

Modern software engineering standards trace back to two parallel efforts in the late 1980s and early 1990s. The U.S. Department of Defense funded the Capability Maturity Model (CMM) at Carnegie Mellon University, which evolved into CMMI. In parallel, the European Union funded the SPICE initiative (Software Process Improvement and Capability Evaluation), which became the international standard ISO/IEC 15504 and later the modernized ISO/IEC 33000 series.

These two lineages — CMMI and ISO/IEC 33000 — remain the dominant foundations for process assessment worldwide. Industry-specific adaptations have emerged from both, tailored to the safety, regulatory, and supply chain needs of individual domains.

**Key lineage:**

- CMM (1986) → CMMI (2002, 2018) — Dominant in U.S. and defense sectors
- SPICE (1993) → ISO/IEC 15504 (2003) → ISO/IEC 33000 (current) — International standard; basis for domain-specific adaptations

---

## Process Standards

### ISO/IEC 12207 — Software Lifecycle Processes

The foundational international standard defining all processes required for developing and maintaining software — acquisition, supply, development, operation, maintenance, and disposal. Deliberately lifecycle-agnostic: it does not prescribe waterfall, iterative, or agile approaches.

- **Current version:** ISO/IEC/IEEE 12207:2017
- **Agile support:** Annex H provides guidance on agile application
- **Future:** Draft revision (DIS 12207:2027) targets native alignment with Agile, DevOps, and cloud-native paradigms
- **Adoption:** Widely referenced across industries as the baseline for software process definition; serves as the foundation that domain-specific standards extend

### ISO/IEC 15288 — Systems Engineering Lifecycle Processes

The systems engineering counterpart to ISO 12207. Covers lifecycle processes where system elements include hardware, software, data, humans, processes, services, procedures, facilities, and materials.

- **Current version:** ISO/IEC/IEEE 15288:2023
- **Best for:** Multi-disciplinary projects spanning beyond pure software
- **Key improvements in 2023 edition:** Business/mission analysis, system architecture definition, risk management, configuration management

### ISO/IEC 33000 Series — Process Assessment Framework

The family of standards providing a comprehensive framework for assessing process capability and organizational maturity. Supersedes the earlier ISO/IEC 15504 series.

- **ISO/IEC 33001:2015** — Terminology and overall concepts
- **ISO/IEC 33002:2015** — Minimum requirements for performing assessments (objectivity, consistency, repeatability)
- **ISO/IEC 33003** — Measurement frameworks
- **ISO/IEC 33004** — Reference models
- **ISO/IEC 33020** — Capability maturity frameworks
- **Adoption:** Forms the assessment backbone for multiple domain-specific standards; any organization can use this series to evaluate its own process capability or assess suppliers

### CMMI — Capability Maturity Model Integration

A process improvement framework developed at Carnegie Mellon University, now administered by ISACA/CMMI Institute. One of the most widely adopted maturity frameworks globally, with particularly strong presence in the U.S., defense, and government sectors.

**Maturity Levels (1–5):**

1. **Initial** — Unpredictable, ad hoc
2. **Managed** — Project management discipline
3. **Defined** — Process standardization
4. **Quantitatively Managed** — Process measurement and control
5. **Optimizing** — Continuous improvement focus

- **Structure:** 22 process areas grouped by maturity level
- **CMMI 2.0 (2018):** Replaced process areas with "practice areas" containing agile/Scrum-specific sections; merged DEV, ACQ, and SVC into a single model
- **Agile coverage:** Over 70% of CMMI-appraised organizations report using agile approaches, though research shows only ~41% alignment of agile artifacts at maturity levels 2–3

### ISO/IEC 29110 — Lifecycle Profiles for Very Small Entities (VSEs)

Tailored framework for software organizations with up to 25 people. Addresses the gap between small organizations' limited resources and the overhead of standards like ISO 12207 or CMMI.

- **Scope:** Requirements, design, development, testing, maintenance
- **Lifecycle agnostic:** Supports waterfall, iterative, incremental, evolutionary, and agile
- **Best for:** Small teams that need process discipline without enterprise overhead

---

## Quality Standards

### ISO/IEC 25010 — Software Quality Model (SQuaRE)

Part of the ISO/IEC 25000 "SQuaRE" (System and Software Quality Requirements and Evaluation) family. Addresses product quality outcomes rather than process maturity — complementary to any process standard.

**Eight Product Quality Characteristics:**

1. Functional suitability
2. Performance efficiency
3. Compatibility
4. Usability
5. Reliability
6. Security
7. Maintainability
8. Portability

**Five Quality-in-Use Characteristics:** Effectiveness, Efficiency, Satisfaction, Freedom from risk, Context coverage

- **Purpose:** Enables requirements specification and evaluation throughout the software lifecycle by developers, acquirers, QA staff, and independent evaluators

---

## Standards for Shared Terminology and Operating Language

### ISO/IEC 24765 — Systems and Software Engineering Vocabulary

The primary international standard providing common vocabulary across all systems and software engineering work. IEEE maintains a public database called **SEVOCAB** at [computer.org/sevocab](https://www.computer.org/sevocab).

- **Current version:** 2017
- **Purpose:** Standardize definitions, serve as reference for IT professionals, encourage aligned terminology across ISO and liaison organizations (IEEE, PMI)
- **Adoption:** The authoritative reference for resolving terminology disputes across organizations and contracts

### IEEE 610 — Glossary of Software Engineering Terminology

The classic glossary containing 1000+ software engineering term definitions. Establishes baseline vocabulary across the discipline.

### IEEE 830 — Software Requirements Specifications

Describes content and qualities of good software requirements specifications (SRS). Provides sample SRS outlines and applies to both custom development and commercial software selection.

### IEEE 1012 — Software Verification and Validation

Standard for V&V processes. Verification: building the product correctly. Validation: building the right product.

### Practical Terminology Approach

Research on project communication best practices recommends a multi-level approach:

- **Corporate-level terminology standards** across all projects
- **Project-specific glossaries** tailored to domain terms
- **Vendor/stakeholder alignment** ensuring external partners share the same definitions
- **Coordination** from a Project Support Organization (PMO, Quality, Governance) to ensure consistency

---

## Safety-Critical Standards by Domain

### IEC 61508 — Functional Safety (Cross-Industry Baseline)

The foundational international standard for functional safety applicable across all industries. Four Safety Integrity Levels (SIL 1–4) corresponding to risk reduction requirements. Most domain-specific safety standards derive from or reference IEC 61508.

### DO-178C — Aerospace (Civil Aviation)

The primary standard referenced by the FAA, EASA, and Transport Canada for certifying commercial software-based avionics. Five assurance levels (A–E) corresponding to criticality.

- **Publisher:** RTCA and EUROCAE
- **Scope:** Complete software lifecycle — planning, development, and integral processes
- **Adoption:** Mandatory for civil aviation software certification; one of the most mature safety-critical software standards

### IEC 62304 — Medical Device Software

International standard specifying lifecycle requirements for medical device software development. FDA accepts ANSI/AAMI/IEC 62304 as evidence of acceptable design standards.

**Safety Classifications:**

- **Class A** — Safety impact negligible
- **Class B** — Potential serious injury or death possible
- **Class C** — Safety-critical; death or serious injury is possible

### ISO 26262 — Automotive Functional Safety

Automotive functional safety standard defining ASILs (Automotive Safety Integrity Levels A–D) for risk classification. Derived from IEC 61508 for road vehicles.

### Automotive SPICE (ASPICE) — Automotive Software Process Maturity

Domain-specific adaptation of the ISO/IEC 33000 (SPICE) framework for automotive software development. Widely adopted across automotive supply chains as a process capability and maturity assessment model. Developed by the Automotive Special Interest Group (AUTOSIG) with backing from major OEMs. See [aspice-references.md](aspice-references.md) for additional detail.

### EN 50128 — Railway Software

European standard for safety-related railway software; specialization of IEC 61508 for railway control, protection, and signaling systems.

- **Related standards:** EN 50126 (RAMS), EN 50129 (formal safety assurance), EN 50716:2023 (merges EN 50128 and EN 50657, adds cybersecurity)

---

## SPICE Domain Adaptations

The ISO/IEC 33000 (SPICE) framework's flexibility has produced domain-specific adaptations beyond the general standard:

| Variant | Domain | Notes |
|---------|--------|-------|
| **Automotive SPICE 4.0** | Automotive software | Widely adopted across automotive supply chains; incorporates safety, security, and agile |
| **Mechanical SPICE v2.1** | Mechanical engineering | Bridges software process assessment with mechanical design processes |
| **Agile SPICE** | Cross-domain | Maps agile practices to SPICE process definitions; created by iNTACS |
| **Test SPICE V4** | Testing / QA | Focused assessment of testing and quality assurance processes |
| **Aerospace SPICE** | Aerospace | Published by JAXA in Japanese and English |
| **Medical Device SPICE (VDI 5702)** | Medical devices | Incorporates medical safety and regulatory requirements |

---

## Agile and Standards: The Convergence

Most process standards predate agile's dominance, but convergence is underway:

- **ISO 12207:2017** added Annex H with agile guidance; the 2027 revision targets native Agile/DevOps alignment
- **CMMI 2.0** restructured with practice areas containing agile/Scrum-specific sections
- **SAFe + CMMI** are increasingly used together — SAFe for organizational scaling (program increments, value streams) and CMMI for engineering rigor (risk management, decision analysis, process measurement)
- **Agile SPICE** provides explicit mappings between agile ceremonies/artifacts and SPICE process definitions

The inherent tension: higher maturity levels (4–5) emphasize quantitative process management that doesn't always map cleanly to agile's empirical approach. Most organizations customize rather than adopt any single framework rigidly.

---

## How Standards Layer Together

Standards form a natural hierarchy that collectively define a project's operating language:

1. **Vocabulary standards** (ISO 24765, IEEE 610) — Foundational definitions eliminating ambiguity
2. **Process standards** (ISO 12207, ISO 15288) — Taxonomy of activities and lifecycle stages
3. **Assessment standards** (ISO 33000, CMMI) — Consistent language for evaluating capability
4. **Quality standards** (ISO 25010) — Shared terminology for product attributes
5. **Domain safety standards** (IEC 61508, DO-178C, IEC 62304, ISO 26262, EN 50128) — Industry-specific safety and assurance language

Each layer builds on those below it, creating a coherent vocabulary from foundational definitions up through domain-specific specialization.

---

## Quick Reference

| Standard / Framework | Primary Purpose | Shared Language Role | Adoption |
|----------------------|-----------------|----------------------|----------|
| **ISO/IEC 24765** | Vocabulary baseline | Foundational definitions | International standard |
| **IEEE 610** | Glossary (1000+ terms) | Discipline vocabulary | Widely referenced |
| **ISO/IEC 12207** | Software lifecycle processes | Process taxonomy | International standard; broadly adopted |
| **ISO/IEC 15288** | Systems lifecycle processes | Systems engineering vocabulary | International standard |
| **ISO/IEC 33000** | Process assessment framework | Maturity/capability language | International standard; basis for domain adaptations |
| **CMMI** | General maturity framework | Organizational capability language | Dominant in U.S., defense, government |
| **ISO/IEC 25010** | Product quality model | Quality characteristics language | International standard |
| **ISO/IEC 29110** | Small entity lifecycle | Lightweight process language | Growing adoption in VSEs |
| **IEC 61508** | Functional safety baseline | Industrial safety language | Cross-industry foundation |
| **DO-178C** | Aerospace safety assurance | Aerospace safety language | Mandatory for civil aviation |
| **IEC 62304** | Medical device software | Medical device safety language | FDA-recognized |
| **ISO 26262** | Automotive functional safety | Automotive safety language | Automotive industry standard |
| **[ASPICE](aspice-references.md)** | Automotive process maturity | Automotive process language | Widely adopted across automotive supply chains |
| **EN 50128** | Railway safety software | Railway-specific safety language | European railway standard |
| **SAFe** | Scaled agile framework | Agile program language | Widely adopted for scaled agile |
