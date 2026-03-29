# Process Standards

A survey of the five ISO/IEC/IEEE process standards selected for the project's lifecycle governance work, covering scope, document artifacts, and lifecycle models.

---

## Background

Modern systems and software engineering relies on a family of internationally harmonized process standards maintained jointly by ISO, IEC, and IEEE. At the top sit two comprehensive lifecycle frameworks — one for systems, one for software — that define what processes an organization should perform but deliberately leave methodology choice (waterfall, iterative, agile, etc.) to the implementer. Supporting standards fill in the detail: one specifies the content of lifecycle documentation, another operationalizes requirements engineering, and a tailored series scales the frameworks down for very small entities. Together these five standards form an interconnected ecosystem that can be adopted whole or selectively depending on organizational size and project scope.

---

## Standards at a Glance

| Standard | Full Title | Edition | Publisher |
|----------|------------|---------|-----------|
| [ISO/IEC/IEEE 15288:2023](https://www.iso.org/standard/81702.html) | *Systems and software engineering — System life cycle processes* | 2nd ed., 2023 | ISO/IEC/IEEE |
| [ISO/IEC/IEEE 12207:2026](https://standards.ieee.org/ieee/12207/11416/) | *Systems and software engineering — Software life cycle processes* | 2nd ed., 2026 | ISO/IEC/IEEE |
| [ISO/IEC 29110-1-1:2024](https://www.iso.org/standard/85337.html) | *Systems and software engineering — Lifecycle profiles for Very Small Entities (VSEs) — Part 1-1: Overview* | 2024 | ISO/IEC |
| [IEEE 29148:2018](https://standards.ieee.org/standard/29148-2018.html) | *Systems and software engineering — Life cycle processes — Requirements engineering* | 2018 | ISO/IEC/IEEE |
| [ISO/IEC/IEEE 15289:2019](https://www.iso.org/standard/74909.html) | *Systems and software engineering — Content of life-cycle information items (documentation)* | 2019 | ISO/IEC/IEEE |

**[ISO/IEC/IEEE 15288:2023](https://www.iso.org/standard/81702.html)** — Defines the full set of system life cycle processes including Stakeholder Needs and Requirements Definition, Architecture Definition, and Design Definition as sibling technical processes. This is the overarching process framework; the other standards operate within or alongside it. Replaces the 2015 edition.

**[ISO/IEC/IEEE 12207:2026](https://standards.ieee.org/ieee/12207/11416/)** — The software-specific counterpart to 15288, now in its 2nd edition (replacing the 2017 edition). Defines software life cycle processes including requirements analysis, architectural design, and detailed design. IEEE 29148 explicitly references 12207 as one of its parent lifecycle frameworks. Useful when scope is purely software rather than full systems engineering.

**[ISO/IEC 29110-1-1:2024](https://www.iso.org/standard/85337.html)** — Part 1-1 is the overview document for the multi-part 29110 series. Explains the profile structure (Entry, Basic, Intermediate, Advanced) and how profiles are derived from 15288 and 12207. Additional parts to consider depending on needs: Part 4-1:2018 (software engineering profile specifications), Part 5-1-2 (software engineering Basic profile guide), and Part 5-6-3:2019 (systems engineering Intermediate profile guide).

**[IEEE 29148:2018](https://standards.ieee.org/standard/29148-2018.html)** — The primary requirements engineering standard. Defines requirements processes, artifact types (SyRS, SRS, verification cross-reference matrix, RTM), and quality attributes for well-formed requirements. Supersedes IEEE 830-1998, IEEE 1233-1998, and IEEE 1362-1998.

**[ISO/IEC/IEEE 15289:2019](https://www.iso.org/standard/74909.html)** — The companion documentation standard referenced by 15288, 12207, and 29110. Defines the content and structure of life-cycle information items produced by the processes in those standards. Organizes information items into seven generic types: Descriptions, Plans, Policies, Procedures, Reports, Requests, and Specifications.

---

## Standards

### ISO/IEC/IEEE 15288:2023 — System Life Cycle Processes

The overarching systems engineering process framework. Establishes a common set of process descriptions for the life cycle of human-made systems — from conception through retirement. Applies to standalone systems, embedded systems, and systems of systems, where system elements may include hardware, software, data, humans, processes, services, procedures, facilities, and materials. Replaces the 2015 first edition. The standard is methodology-agnostic: it provides a process architecture that can be applied iteratively, concurrently, and recursively across lifecycle stages.

- **Current version:** 2023 (2nd edition)
- **Website:** [iso.org/standard/81702.html](https://www.iso.org/standard/81702.html)
- **Best for:** Organizations needing a full system lifecycle process framework spanning hardware, software, and human elements

#### Process Groups

The standard organizes 30 processes into five groups.

**Agreement Processes (2):** Acquisition, Supply.

**Organizational Project-Enabling Processes (6):** Life Cycle Model Management, Infrastructure Management, Portfolio Management, Human Resource Management, Quality Management, Knowledge Management.

**Technical Management Processes (7):** Project Planning; Project Assessment and Control; Decision Management; Risk Management; Configuration Management; Information Management; Measurement.

**Technical Processes (14):** Business or Mission Analysis; Stakeholder Needs and Requirements Definition; System Requirements Definition; System Architecture Definition; System Design Definition; System Analysis; System Element Implementation; System Integration; System Verification; System Validation; System Transition; System Operation; System Maintenance; System Disposal.

The 2023 revision enhances Business or Mission Analysis, System Architecture Definition, System Analysis, Implementation, Integration, Operations, Maintenance, Risk Management, and Configuration Management. Clause 5 (key concepts) was also updated with improved descriptions of iteration/recursion, systems of systems, and quality characteristics.

#### Document Artifacts

ISO/IEC/IEEE 15288 defines process outcomes generically — for example, that requirements shall be documented or that an architecture shall be defined — without normatively naming specific document types. Annex B provides an informative (non-normative) mapping of example information items to processes. Representative examples include: Concept of Operations (ConOps), Stakeholder Requirements Specification, System Requirements Specification, System Architecture Description, System Design Description, Interface Definition Description, Integration Plan, Test Plan, Test Reports, Verification Reports, Validation Reports, Configuration Management Plan, Risk Management Plan, Project Management Plan, Transition Plan, Maintenance Plan, and Disposal Plan. The actual content structure and minimum content expectations for these artifacts are defined in the companion standard ISO/IEC/IEEE 15289:2019. *[To be confirmed against the procured standard.]*

#### Lifecycle Stages

The standard defines six generic lifecycle stages derived from ISO/IEC TR 24748-1: Concept (identify stakeholder needs and characterize the solution space), Development (refine requirements, design, and build), Production (manufacture, assemble, and quality-assure), Utilization (operate to satisfy users' needs), Support (sustain capability through maintenance), and Retirement (store, archive, or dispose). These stages are not strictly sequential — they may overlap, recur, and be applied recursively to system elements. Individual processes can be invoked across multiple stages.

---

### ISO/IEC/IEEE 12207:2026 — Software Life Cycle Processes

The software-specific counterpart to 15288, now in its 2nd edition (replacing the 2017 third edition). Achieves full structural harmonization with 15288, adopting an identical 30-process model with a single name change — "System Requirements Definition" became "System/Software Requirements Definition." This harmonization allows organizations running joint hardware–software programs to implement one consistent process set. The 2026 edition enhances support for Agile, DevOps, and cloud-native paradigms.

- **Current version:** 2026 (2nd edition)
- **Website:** [standards.ieee.org/ieee/12207/11416/](https://standards.ieee.org/ieee/12207/11416/)
- **Best for:** Organizations whose scope is purely software rather than full systems engineering

#### Process Groups

The standard organizes 30 processes into four groups.

**Agreement Processes (2):** Acquisition, Supply.

**Organizational Project-Enabling Processes (6):** Life Cycle Model Management, Infrastructure Management, Portfolio Management, Human Resource Management, Quality Management, Knowledge Management.

**Technical Management Processes (7):** Project Planning; Project Assessment and Control; Decision Management; Risk Management; Configuration Management; Information Management; Measurement.

**Technical Processes (14):** Stakeholder Requirements Definition; System/Software Requirements Analysis; Architectural Design; Design; Implementation (Construction); Integration; Verification; Transition; Validation; Operation; Maintenance; Disposal; Quality Assurance; Audit.

#### Document Artifacts

Like 15288, ISO/IEC/IEEE 12207 describes process outcomes generically without normatively naming specific document types. Annex B provides an informative (non-normative) list of example artifacts associated with each process. Representative examples include: Software Requirements Specification, Software Architecture Description, Software Design Description, Software Interface Specification, Software Test Plan, Software Test Cases, Software Test Reports, Software Verification Report, Software Validation Report, Software Configuration Management Plan, Software Quality Assurance Plan, Software Integration Plan, source code and code review records, and maintenance and support records. The concrete content structure for these information items is defined in ISO/IEC/IEEE 15289:2019. *[To be confirmed against the procured standard.]*

#### Lifecycle Stages

ISO/IEC/IEEE 12207 does not prescribe a specific lifecycle model or methodology. It distinguishes between *stages* (periods relating to the state of the system, ending at a decision gate) and *processes* (sets of interrelated activities). Illustrative stages from ISO/IEC TS 24748-1 include: Concept/Concept Exploration, Development, Production (if applicable to software packaging/distribution), Utilization, Support/Sustainment, and Retirement. The framework supports waterfall, iterative, incremental, agile, DevOps, and hybrid approaches.

---

### ISO/IEC 29110-1-1:2024 — Lifecycle Profiles for Very Small Entities

The overview document for the multi-part 29110 series, which provides lifecycle profiles tailored for Very Small Entities (VSEs) — enterprises, organizations, departments, or projects with up to 25 people. Rather than defining a new process framework, 29110 subsets and adapts processes from ISO/IEC/IEEE 15288 and ISO/IEC/IEEE 12207 into lightweight, immediately actionable profiles appropriate for resource-constrained organizations.

- **Current version:** 2024
- **Website:** [iso.org/standard/85337.html](https://www.iso.org/standard/85337.html)
- **Best for:** Teams of up to 25 people seeking a progressive, right-sized adoption of lifecycle processes

#### Profile Structure

The standard defines a four-tier progressive maturity path.

**Entry Profile** — For start-ups or projects of ≤6 person-months. Lightweight Project Management and System Definition/Realization. Not applicable to safety-critical development.

**Basic Profile** — For VSEs developing a single application with a single work team. Two core processes: Project Management (PM) and Software Implementation (SI). This is the most widely adopted tier.

**Intermediate Profile** — For VSEs managing multiple concurrent projects with multiple teams. Adds multi-project portfolio management, component reuse, and process measurement/improvement.

**Advanced Profile** — For VSEs seeking sustained competitive growth. Adds business management, strategic alignment, and advanced optimization practices.

#### Document Artifacts

Artifacts are defined per profile level, with the Basic profile being the most fully documented.

Project Management artifacts include: Project Plan (derived from Statement of Work), Project Assessment and Control Records, and Acceptance Record. Software Implementation artifacts include: Software Requirements Specification, Software Design Documentation (architectural and detailed), Source Code/Construction Artifacts, Test Cases and Test Results, Integration Documentation, and Quality Assurance Records.

The standard references ISO/IEC/IEEE 15289 for artifact content definitions. Practical Deployment Packages — containing process descriptions, role definitions, work product templates, checklists, and tool recommendations — are available to help VSEs adopt the profiles incrementally.

#### Lifecycle Model

ISO/IEC 29110 does not mandate a specific lifecycle model. It is explicitly compatible with waterfall, iterative, incremental, evolutionary, and agile approaches. The lifecycle is structured hierarchically: Processes → Activities → Tasks → Steps.

At the Basic profile level, the lifecycle flow covers: Project Planning (elaborate the Project Plan from the Statement of Work), Software Requirements Analysis (analyze and validate customer requirements), Software Design (produce architectural and detailed design), Software Construction (code and implement), Software Integration and Test (integrate components and verify), Software Delivery (deliver the product to the customer), and Project Assessment and Control (monitor progress throughout and take corrective action for deviations). Quality Assurance runs in parallel across all activities.

#### Multi-Part Structure

The 29110 series is organized into several parts: Part 1-1 (Overview) and Part 1-2 (Vocabulary) provide foundational concepts and terminology. Part 2-1 (Framework and Taxonomy) covers profile definition logic and catalogue structure, aimed at standards producers. Part 4-1:2018 (Software Engineering Profile Specifications) provides formal specifications for all Generic Profile Group profiles, selecting elements from ISO 12207. The Part 5-1 series (Software Engineering Guides) covers practical management and engineering guidance per profile level — Entry (5-1-1), Basic (5-1-2), Intermediate (5-1-3), and Advanced (5-1-4). The Part 5-6 series (Systems Engineering Guides) provides a parallel set for systems engineering profiles. Part 5-3 (Service Delivery Guidelines) extends the framework to IT service delivery.

---

### IEEE 29148:2018 — Requirements Engineering

The primary requirements engineering standard for systems and software. Provides comprehensive guidance on requirements processes, artifact types, and quality attributes for well-formed requirements. Supersedes three earlier IEEE standards — IEEE 830-1998, IEEE 1233-1998, and IEEE 1362-1998 — consolidating their guidance into a single unified framework. Designed to be used alongside ISO/IEC/IEEE 15288 and ISO/IEC/IEEE 12207, operationalizing and expanding the requirements-related processes defined in those lifecycle standards.

- **Current version:** 2018
- **Website:** [standards.ieee.org/standard/29148-2018.html](https://standards.ieee.org/standard/29148-2018.html)
- **Best for:** Defining requirements artifacts, traceability, and quality criteria for any systems or software project

#### Document Artifacts

The standard defines a hierarchical set of requirements specifications plus supporting traceability artifacts.

**Business Requirements Specification (BRS)** — Describes the organization's business or mission motivation. Defines business processes, policies, rules, and top-level requirements. Output of the Business or Mission Analysis process. Highest level in the hierarchy.

**Stakeholder Requirements Specification (StRS)** — Defines requirements from each stakeholder class — end users, operators, maintainers, and others — including system functions, performance expectations, and constraints. Translates business requirements into stakeholder-oriented needs.

**System Requirements Specification (SyRS)** — Transforms stakeholder/user views into a technical view of the required solution. Typical sections include system purpose and scope, operational modes and states, operational quality attributes, user requirements, operational concept and scenarios, functional requirements, non-functional/quality requirements, environmental conditions and constraints, design constraints, assumptions and dependencies, and traceability information.

**Software Requirements Specification (SRS)** — Detailed software-specific requirements derived from the SyRS. Lowest level in the hierarchy; drives software design and implementation.

**Requirements Traceability Matrix (RTM)** — Provides bidirectional traceability mapping each requirement to the originating higher-level requirement or stakeholder need, the design elements implementing it, the verification test cases validating it, and any child requirements derived from it.

**Verification Cross-Reference Matrix (VCRM)** — Links requirements to their verification methods and test cases.

#### Requirements Quality Attributes

The standard defines characteristics for individual requirements and for the requirement set as a whole.

Individual requirement attributes: Unambiguous (single interpretation only), Complete (fully defined without additional information), Verifiable (provable through examination, demonstration, test, or analysis), Singular (one requirement per statement, no conjunctions masking multiples), Feasible (technically achievable within constraints), Necessary (addresses a documented stakeholder need), Traceable (linked upward to source, downward to implementation/verification), Affordable (within budget), Bounded (maintains identified scope), and Implementation-Free (states *what*, not *how*).

Set-level completeness requires that all necessary capabilities and constraints are defined, no TBD/TBS/TBR placeholders remain, and no further amplification is required.

#### Lifecycle Model

IEEE 29148 defines three primary requirements engineering processes that map to lifecycle stages: Business or Mission Analysis (define the problem or opportunity, characterize the solution space, produce the BRS), Stakeholder Needs and Requirements Definition (identify stakeholders, elicit needs, formalize requirements, produce the StRS), and System Requirements Definition (transform stakeholder views into technical system requirements, produce the SyRS and design/implementation constraints).

These processes are applied iteratively and recursively throughout the lifecycle — requirements are refined, decomposed, and updated as understanding deepens and development progresses. The artifact flow follows a clear hierarchy: BRS → StRS → SyRS → SRS, with the RTM and VCRM maintaining traceability across all levels. The standard does not define its own lifecycle model but integrates into whatever model the organization has chosen via 15288 or 12207.

---

### ISO/IEC/IEEE 15289:2019 — Content of Life-Cycle Information Items

The companion documentation standard referenced by 15288, 12207, and 29110. Specifies the purpose, content, and recommended structure of the information items — documents, records, and data — produced by the processes defined in those lifecycle standards. Rather than prescribing rigid templates, 15289 defines minimum expected content for each information item type, allowing organizations to tailor format and depth to their context. It replaces the 2017 edition. The standard serves as the bridge between process definitions ("what to do") and documentation practice ("what to record").

- **Current version:** 2019
- **Website:** [iso.org/standard/74909.html](https://www.iso.org/standard/74909.html)
- **Best for:** Understanding required content and structure of lifecycle documentation produced by 15288/12207 processes

#### Document Artifacts

15289 classifies all lifecycle documentation into seven generic information item types.

**Description** — Describes a system, software element, or process in terms of its characteristics, properties, or relationships. Examples: System Architecture Description, Software Design Description, Interface Description, Concept of Operations (ConOps).

**Plan** — Documents the approach, resources, schedule, and procedures for accomplishing a stated objective. Examples: Project Management Plan, Systems Engineering Management Plan, Test Plan, Configuration Management Plan, Quality Assurance Plan, Risk Management Plan, Verification Plan, Validation Plan, Transition Plan, Disposal Plan.

**Policy** — Establishes organizational direction, constraints, or principles. Examples: Quality Policy, Information Security Policy, Life Cycle Model Policy.

**Procedure** — Defines the steps to perform a specific activity or task. Examples: Configuration Management Procedure, Problem Resolution Procedure, Change Control Procedure, Audit Procedure.

**Report** — Documents the results of an activity, study, investigation, or analysis. Examples: Test Report, Verification Report, Validation Report, Audit Report, Risk Assessment Report, Status/Progress Report, Review Report.

**Request** — Proposes or initiates an action, change, or decision. Examples: Change Request, Problem Report, Action Item, Waiver Request.

**Specification** — States requirements to be met by a system, product, or process. Examples: System Requirements Specification (SyRS), Software Requirements Specification (SRS), Stakeholder Requirements Specification (StRS), Interface Requirements Specification.

#### Content Guidance

For each information item type, 15289 provides a purpose statement explaining why the item exists, generic content elements common to all instances of that type, and specific content elements relevant to particular lifecycle processes — a Test Plan has different specific content than a Configuration Management Plan, even though both are Plans. The standard also addresses information item management concerns including versioning, approval, distribution, retention, and disposition.

#### Lifecycle Model

ISO/IEC/IEEE 15289 does not define its own lifecycle model or processes. It is a supporting standard that specifies documentation content for the processes defined in 15288 and 12207. Information items are produced, maintained, and retired in alignment with whatever lifecycle model the organization has adopted through those parent standards.

The standard does recognize that information items have their own lifecycle — they are created, reviewed, baselined, updated through change control, and eventually archived or disposed of. This information item lifecycle runs in parallel with the system or software lifecycle and is governed by the Configuration Management and Information Management processes of 15288/12207.

---

## Selection Guide

| Organization Profile | Recommended Standards | Rationale |
|---|---|---|
| Large organization, full systems engineering (hardware + software + human elements) | 15288 + 15289 + 29148 | Full process framework with documentation content guidance and requirements rigor |
| Large organization, software-only scope | 12207 + 15289 + 29148 | Software-specific process framework with documentation and requirements support |
| Large organization, joint hardware–software programs | 15288 + 12207 + 15289 + 29148 | Both frameworks are structurally harmonized for concurrent use on the same program |
| VSE (≤25 people), single project, single team | 29110 (Basic profile) + 29148 | Lightweight profile with requirements quality guidance; scales up as the organization grows |
| VSE (≤25 people), multiple concurrent projects | 29110 (Intermediate profile) + 29148 | Adds portfolio management and component reuse to the Basic profile |
| Start-up or very small project (≤6 person-months) | 29110 (Entry profile) | Minimum viable process governance; adopt 29148 practices informally |
| Any organization needing documentation templates | Add 15289 to whichever lifecycle standard is in use | 15289 is the universal documentation companion; defines content for all information item types |

---

## Industry Trends

- **Agile and DevOps harmonization** — The forthcoming 12207 revision and ongoing 15288 maintenance are adding explicit guidance for iterative, continuous-delivery, and DevOps workflows, reflecting that most organizations now blend plan-driven and agile approaches.
- **VSE adoption growth** — ISO/IEC 29110 continues to gain traction in developing economies and among start-ups, driven by freely available Deployment Packages and government-backed adoption programs. The 2024–2025 updates across multiple parts indicate active investment in the series.
- **Model-based systems engineering (MBSE)** — Architecture and design processes in 15288 and 12207 are increasingly interpreted through MBSE tooling, where models replace or supplement traditional documents. 15289's flexible content guidance accommodates model-based information items.
- **Continuous compliance** — Organizations are moving from periodic audits toward continuous process compliance verification, using automation to track adherence to 15288/12207 process outcomes and 15289 documentation completeness in real time.
- **Convergence of safety and security standards** — Lifecycle process standards are being aligned with domain-specific safety (IEC 61508, DO-178C) and security (ISO 27001, IEC 62443) frameworks, requiring tighter integration of risk management and verification processes from 15288/12207.
