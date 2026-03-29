# Architecture and Requirements Lifecycles

A comparison of how architecture knowledge and requirements knowledge evolve through their respective lifecycles — where they overlap, where they diverge, which standards address each, and whether projects need both.

---

## Background

Architecture documentation and requirements documentation are often treated as separate disciplines with separate tooling, separate teams, and separate standards. In practice, however, they describe the same system from different angles and advance through similar stages of maturity — from informal stakeholder input through to verified, normative artifacts. The question of whether these two lifecycles are genuinely distinct or merely two views of the same underlying knowledge progression has practical consequences for how teams organize their documentation, choose their tools, and structure their governance.

---

## The Requirements Lifecycle

Requirements knowledge typically progresses through stages defined by IEEE 29148 [1] and elaborated across the systems engineering literature. The lifecycle is primarily concerned with capturing *what* a system must do and *how well* it must do it.

| Stage | Activity | Key Artifact |
|-------|----------|--------------|
| **Elicitation** | Gather needs from stakeholders through interviews, workshops, observation, and domain analysis | Stakeholder needs statements, user stories [^userstories], use cases [^usecases] |
| **Analysis** | Decompose, classify, and prioritize needs; identify conflicts and gaps; establish feasibility | Needs analysis report, priority rankings, feasibility assessments |
| **Specification** | Express requirements in a structured, verifiable form with clear acceptance criteria | System Requirements Specification (SyRS) [1, §6.4], Software Requirements Specification (SRS) [1, §6.5] |
| **Validation** | Confirm that specified requirements actually reflect stakeholder intent — "are we building the right thing?" | Validation reviews, prototypes, stakeholder sign-off |
| **Verification planning** | Define how each requirement will be tested or demonstrated | Verification cross-reference matrix [1, §6.6], test plans |
| **Management** | Track requirements through changes, maintain traceability, handle baselines and versions | Requirements Traceability Matrix (RTM) [1, §6.7], change requests, impact analyses |

The requirements lifecycle is iterative — later stages feed back into earlier ones as understanding deepens. IEEE 29148 [1] explicitly describes this as recursive application across lifecycle stages.

[^userstories]: User stories originated in Extreme Programming (XP). See: Mike Cohn, *User Stories Applied: For Agile Software Development* (Boston: Addison-Wesley, 2004).

[^usecases]: Use cases were formalized in: Ivar Jacobson, "Object-Oriented Software Engineering: A Use Case Driven Approach" (Wokingham: Addison-Wesley, 1992). The UML representation is standardized in OMG Unified Modeling Language, v2.5.1 (2017), https://www.omg.org/spec/UML/2.5.1.

---

## The Architecture Lifecycle

Architecture knowledge progresses through a different set of stages, moving from stakeholder context through design elaboration to verified structural conformance. Where requirements focus on *what* and *how well*, architecture focuses on *how* and *why this way*.

| Stage | Activity | Key Artifact |
|-------|----------|--------------|
| **Context** | Capture the initial need, constraint, or opportunity in the stakeholder's language | Context statement — a few sentences describing who needs what and why |
| **Exploration** | Open the idea to broader input; surface trade-offs, alternatives, and structural risks | RFC (Request for Comments) [^rfc] — problem framing, proposed approaches, open questions |
| **Decision** | Commit to a direction and record the rationale | ADR (Architecture Decision Record) [8] — context, decision, consequences |
| **Design** | Elaborate the decided approach into components, interfaces, and interactions | Design document — C4 diagrams [9], sequence diagrams [^umlseq], data models, interface contracts |
| **Specification** | Define the normative structural contract — precise enough to enforce in code | Architecture specification — formal component boundaries, dependency rules, behavioral constraints |
| **Verification** | Validate that the running system matches the documented architecture | Architecture tests (ArchUnit [10], PyTestArch [11]), conformance reviews, drift detection |
| **Maintenance** | Keep all upstream artifacts in sync as the system evolves | Living documentation — CI/CD-generated diagrams, scheduled review cycles, deprecation notices |

[^rfc]: In architecture practice, "RFC" refers to a lightweight internal document for soliciting feedback on a proposed change — distinct from IETF RFCs. The practice is widely adopted in engineering organizations; see the Oxide RFD process for a well-documented example: https://rfd.shared.oxide.computer/.

[^umlseq]: Sequence diagrams are defined in OMG Unified Modeling Language, v2.5.1 (2017), §17, https://www.omg.org/spec/UML/2.5.1.

---

## Where They Overlap

The two lifecycles share more structure than their separate standards and tooling traditions suggest.

**Common origin.** Both begin with stakeholder input. A stakeholder says "we need the system to handle 10,000 concurrent users" — that is simultaneously a performance requirement and an architectural constraint. The same sentence spawns artifacts in both lifecycles.

**Parallel maturation.** Both move from informal, loosely structured knowledge toward formal, verifiable artifacts. A context statement and a stakeholder need are doing similar work at different levels of abstraction. A requirements specification and an architecture specification both define normative contracts — one for behavior, one for structure.

**Shared verification.** Both culminate in verification against the running system. Requirements are verified through acceptance tests; architecture is verified through conformance tests. In many cases the same test exercises both — an integration test that validates an API contract is simultaneously verifying a requirement and an architectural boundary.

**Bidirectional traceability.** Both depend on traceability to remain coherent. Requirements trace forward to tests and backward to stakeholder needs. Architecture artifacts trace forward to enforcement tests and backward to the context statements and ADRs [8] that justified them.

---

## Where They Diverge

Despite the structural parallels, the two lifecycles serve different purposes and the differences matter.

**Scope of concern.** Requirements describe the system's externally observable behavior — what it does, how fast, how reliably. Architecture describes the system's internal organization — how responsibilities are distributed, how components interact, where boundaries are drawn. A requirement like "the system shall respond within 200ms" says nothing about whether that response comes from a monolith or a microservice mesh. The architecture does.

**Decision emphasis.** The requirements lifecycle is primarily about capturing and refining *what* is needed. The architecture lifecycle is primarily about choosing *how* to achieve it and recording *why* that approach was selected over alternatives. The RFC and ADR [8] stages have no direct equivalent in the requirements lifecycle — requirements rarely document rejected alternatives or the reasoning behind their structure.

**Rate of change.** Requirements tend to be relatively stable once baselined (with formal change control in regulated environments). Architecture tends to evolve more continuously — new components are introduced, interfaces are refactored, deployment topologies shift. The maintenance burden falls differently on the two artifact chains.

**Audience.** Requirements are written for stakeholders, testers, and regulators — people who need to know what the system promises. Architecture is written for developers, operators, and future maintainers — people who need to understand how the system is built and why.

**Formality gradient.** Requirements engineering has a longer tradition of formal specification (IEEE 830 [2], then IEEE 29148 [1], with extensive guidance on requirement quality attributes). Architecture documentation has historically been less formalized — many organizations have architecture diagrams but no architecture specification in the normative sense. The lifecycle and maturity model described in the architecture documentation tools document is an attempt to close that gap.

---

## Standards That Address Both

No single standard fully governs both lifecycles end-to-end, but several span the boundary.

### ISO/IEC/IEEE 15288 — System Life Cycle Processes [3]

The closest thing to a unified framework. ISO 15288 defines both the Stakeholder Needs and Requirements Definition process and the Architecture Definition process as sibling technical processes within the same lifecycle. The 2023 edition explicitly positions architecture definition as consuming requirements and producing design constraints that feed back into requirements refinement. It treats the two as co-evolving activities rather than sequential phases.

- **Coverage:** Both requirements and architecture as parallel technical processes
- **Relationship model:** Architecture consumes requirements; architectural decisions constrain and refine requirements
- **Limitation:** Defines processes, not artifact formats or lifecycle stages — teams must still choose their own templates and tools

### ISO/IEC/IEEE 42010 — Architecture Description [4]

Primarily an architecture standard, but it explicitly requires that architecture descriptions address stakeholder concerns — which are closely related to (and often derived from) requirements. The 2022 edition expanded scope to include enterprise architecture and strengthened the connection between architectural viewpoints and the concerns they address.

- **Coverage:** Architecture with explicit hooks into stakeholder concerns
- **Relationship to requirements:** Concerns map to requirements; viewpoints are selected to address specific requirement categories

### IEEE 29148 — Requirements Engineering [1]

Primarily a requirements standard, but it defines requirements processes as operating within the lifecycle frameworks of ISO 15288 [3] (systems) and ISO 12207 [5] (software). It acknowledges that requirements analysis involves architectural trade-offs and that system requirements allocation requires architectural decomposition.

- **Coverage:** Requirements with acknowledgment of architectural dependencies
- **Relationship to architecture:** Requirements allocation presupposes an architectural decomposition to allocate *to*

### TOGAF — Architecture Development Method (ADM) [6]

TOGAF's ADM cycle includes a dedicated Requirements Management phase that runs continuously alongside the architecture development phases. Requirements are not a one-time input — they are captured, refined, and re-validated at every ADM phase. This is the most explicit attempt to integrate requirements management into an architecture lifecycle.

- **Coverage:** Architecture lifecycle with integrated requirements management
- **Limitation:** Enterprise-focused; less applicable to software-level architecture

### ISO/IEC 29110 — Lifecycle Profiles for Very Small Entities [16]

A multi-part standard that tailors the processes of ISO 15288 [3] (systems) and ISO 12207 [5] (software) into right-sized profiles for very small entities (VSEs) — organizations, departments, or projects of up to 25 people. Rather than defining new processes, ISO 29110 selects and packages subsets of the requirements and architecture activities from the parent standards into graduated profile groups (Entry, Basic, Intermediate, Advanced), giving small teams a standards-aligned lifecycle without the overhead of full 15288/12207 adoption. The 2024 revision (Part 1-1) updated the overview and alignment with the current editions of the parent standards.

- **Coverage:** Both requirements and architecture, scoped to VSE contexts — includes Software Implementation (which encompasses requirements analysis and architectural design) and Project Management
- **Relationship to other standards:** Profiles draw process elements from ISO 12207 [5] and ISO 15288 [3], and product definitions from ISO/IEC/IEEE 15289
- **Relevance:** Directly addresses the gap between "we should follow standards" and "we are a 6-person team" — the graduated profiles provide a tractable adoption path that covers both requirements and architecture concerns

### INCOSE Systems Engineering Handbook [7]

The INCOSE handbook treats requirements analysis and architecture definition as tightly coupled activities within the systems engineering V-model [^vmodel]. It emphasizes that requirements and architecture co-evolve — architectural decisions reveal new requirements, and requirement changes drive architectural revision.

- **Coverage:** Both, within a systems engineering context
- **Relationship model:** Co-evolution with explicit feedback loops

[^vmodel]: The V-model originated in German federal government software development guidance (V-Modell, 1997) and was adopted broadly in systems engineering. See: Kevin Forsberg and Harold Mooz, "The Relationship of System Engineering to the Project Cycle," *Proceedings of the First Annual Symposium of the National Council on System Engineering* (NCOSE, 1991), pp. 57–65.

---

## Do Projects Need Both?

The short answer is yes — but the degree of formality and separation depends on the project's scale, risk, and regulatory context.

### When separate lifecycles are essential

Safety-critical and regulated domains (automotive, aerospace, medical, railway) typically require explicit, auditable separation. Regulators want to see that requirements exist independently of their architectural realization — that the *what* is defined before and independently of the *how*. The V-model enforces this separation structurally, with requirements on the left side and architecture in the middle, each with their own verification. Automotive SPICE (ASPICE) [12], DO-178C [13], IEC 62304 [14], and similar standards mandate traceable requirements artifacts that are distinct from design and architecture artifacts.

### When a unified approach works

Smaller teams, lower-risk projects, and organizations practicing docs-as-code often benefit from a more integrated approach where requirements and architecture artifacts live in the same repository and reference each other directly. An ADR [8] might simultaneously record an architectural decision and the requirement that motivated it. A design document might include both the component structure and the behavioral requirements each component must satisfy. The artifact boundaries blur, and that is fine — as long as traceability is maintained.

### The practical middle ground

Most projects benefit from maintaining the conceptual distinction (requirements describe what, architecture describes how) while relaxing the organizational separation. Concretely, this means keeping requirements and architecture artifacts in the same version-controlled repository, cross-linking between them using standard metadata headers, allowing a single artifact to address both concerns when the scope is small enough, and splitting into separate artifacts when the scope demands it. The lifecycle and maturity model provides a natural integration point — a context statement captures both the initial requirement and the architectural context, and downstream artifacts (RFC, ADR [8], SPEC) can address both behavioral and structural concerns as needed.

---

## Selection Guide

| Situation | Recommended Approach |
|-----------|---------------------|
| Safety-critical or regulated (ASPICE [12], DO-178C [13], IEC 62304 [14]) | Separate, formally traced lifecycles with distinct artifact chains |
| Enterprise architecture governance | TOGAF ADM [6] with integrated requirements management |
| Systems engineering (hardware + software) | ISO 15288 [3] process framework with co-evolving requirements and architecture |
| Software team with docs-as-code practices | Integrated lifecycle — shared repo, cross-linked artifacts, split when complexity demands it |
| Small team or early-stage project | Unified artifacts — context statements and ADRs [8] that capture both requirements and architectural rationale; ISO 29110 [16] profiles for standards-aligned governance at VSE scale |
| Audit-driven compliance without safety criticality | Maintain traceability matrix linking requirements to architecture decisions, but allow shared artifacts |

---

## Industry Trends

- **Co-evolution over handoff** — the sequential model (requirements first, then architecture) is giving way to recognition that the two knowledge streams develop in parallel and inform each other continuously.
- **Model-based systems engineering (MBSE)** [^mbse] is driving convergence — when requirements and architecture live in the same model, the lifecycle distinction becomes a view-level concern rather than a process-level separation.
- **Docs-as-code integration** — teams storing both requirements and architecture artifacts in the same version-controlled repository are naturally discovering that cross-linking and co-maintenance are easier than maintaining separate artifact chains with separate governance.
- **Regulatory adaptation** — even traditionally conservative domains are beginning to accept integrated approaches, provided traceability is demonstrable. ASPICE 4.0 [12] and updated FDA guidance [15] show movement toward outcome-based rather than artifact-based compliance.
- **AI-assisted traceability** — LLM tools are being applied to automatically detect and suggest links between requirements and architecture artifacts, reducing the manual burden of maintaining bidirectional traceability across both lifecycles.

[^mbse]: For MBSE foundations, see: INCOSE, "Systems Engineering Vision 2035" (San Diego: INCOSE, 2024); and Sanford Friedenthal, Alan Moore, and Rick Steiner, *A Practical Guide to SysML*, 3rd ed. (Burlington, MA: Morgan Kaufmann, 2014).

---

## Bibliography

| Ref | Standard / Source | Full Title | Publisher | URL |
|-----|-------------------|------------|-----------|-----|
| [1] | IEEE 29148:2018 | *Systems and software engineering — Life cycle processes — Requirements engineering* | ISO/IEC/IEEE | https://standards.ieee.org/standard/29148-2018.html |
| [2] | IEEE 830-1998 | *IEEE Recommended Practice for Software Requirements Specifications* (superseded by [1]) | IEEE | https://standards.ieee.org/ieee/830/1222/ |
| [3] | ISO/IEC/IEEE 15288:2023 | *Systems and software engineering — System life cycle processes*, 2nd ed. | ISO/IEC/IEEE | https://www.iso.org/standard/81702.html |
| [4] | ISO/IEC/IEEE 42010:2022 | *Software, systems and enterprise — Architecture description*, 2nd ed. | ISO/IEC/IEEE | https://www.iso.org/standard/74393.html |
| [5] | ISO/IEC/IEEE 12207:2026 | *Systems and software engineering — Software life cycle processes*, 2nd ed. | ISO/IEC/IEEE | https://standards.ieee.org/ieee/12207/11416/ |
| [6] | TOGAF 10 (2022) | *The TOGAF Standard*, 10th ed. | The Open Group | https://www.opengroup.org/togaf |
| [7] | INCOSE SE Handbook, 5th ed. (2023) | *Systems Engineering Handbook*, ed. David D. Walden et al. | Wiley / INCOSE | https://www.incose.org/products-and-publications/se-handbook |
| [8] | Nygard (2011) | Michael Nygard, "Documenting Architecture Decisions" | Cognitect Blog | https://www.cognitect.com/blog/2011/11/15/documenting-architecture-decisions |
| [9] | C4 Model | Simon Brown, *The C4 Model for Visualising Software Architecture* | — | https://c4model.com/ |
| [10] | ArchUnit | *ArchUnit: Unit test your Java architecture* | TNG Technology Consulting | https://www.archunit.org/ |
| [11] | PyTestArch | *PyTestArch: Test framework for software architecture based on imports between modules* | — | https://github.com/zyskarch/pytestarch |
| [12] | Automotive SPICE 4.0 (2023) | *Automotive SPICE Process Assessment / Reference Model*, v4.0 | VDA QMC | https://vda-qmc.de/en/automotive-spice/ |
| [13] | DO-178C (2011) | *Software Considerations in Airborne Systems and Equipment Certification* | RTCA / EUROCAE | https://www.rtca.org/do-178/ |
| [14] | IEC 62304:2006+AMD1:2015 | *Medical device software — Software life cycle processes* | IEC | https://www.iso.org/standard/38421.html |
| [15] | FDA (2026) | *Computer Software Assurance for Production and Quality System Software* (updated guidance) | U.S. FDA | https://www.fda.gov/regulatory-information/search-fda-guidance-documents |
| [16] | ISO/IEC 29110-1-1:2024 | *Systems and software engineering — Lifecycle profiles for Very Small Entities (VSEs) — Part 1-1: Overview* | ISO/IEC | https://www.iso.org/standard/85337.html |

### Additional Resources

- **ADR community resources:** https://adr.github.io/ — templates, tooling, and examples for Architecture Decision Records.
- **Martin Fowler on ADRs:** https://martinfowler.com/bliki/ArchitectureDecisionRecord.html — a concise overview of ADR practice.
- **UML 2.5.1 (2017):** OMG Unified Modeling Language specification, https://www.omg.org/spec/UML/2.5.1 — defines use case diagrams, sequence diagrams, and other notation used in both requirements and architecture artifacts.
