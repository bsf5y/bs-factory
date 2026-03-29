# ASPICE 4.0 and ISO/IEC/IEEE Process Standards Integration Analysis

A comparative analysis of Automotive SPICE 4.0 against the five ISO/IEC/IEEE lifecycle standards selected for the project's process governance, with a proposed MVP process solution for achieving ASPICE compliance on non-safety-critical hardware-plus-software products using the ISO standards as a foundation.

---

## Background

Automotive SPICE (ASPICE) is the de facto process assessment model for the automotive industry, maintained by the VDA Quality Management Center. Version 4.0 — released in late 2023 — restructured the model significantly, adding hardware engineering, machine learning engineering, and a standalone validation process while trimming legacy acquisition and supporting processes. ASPICE is built on the ISO/IEC 33000 series of process assessment standards and draws its process architecture from the same ISO/IEC/IEEE 15288 and 12207 tradition that underpins the project's selected lifecycle governance standards. This shared lineage creates a natural integration path, but ASPICE 4.0 also introduces automotive-specific concerns — safety-critical development, supplier monitoring, V-model traceability, and ML data management — that the generic ISO standards do not address directly. Understanding where the two systems align and where they diverge is essential to building a unified process framework that satisfies ASPICE assessors while remaining grounded in internationally recognized lifecycle standards.

---

## ASPICE 4.0 Process Model Overview

ASPICE 4.0 defines 32 processes organized into 3 categories and 11 groups. The model operates on two dimensions: a process dimension (what to do) and a capability dimension (how well it is done, rated on a six-level scale from 0 — Incomplete to 5 — Innovating).

### Process Categories and Groups

**Primary Life Cycle Processes** encompass seven groups covering the engineering and commercial spine of product development.

Acquisition (ACQ) retains a single process — ACQ.4 Supplier Monitoring — down from fifteen in version 3.1. Supply (SPL) retains SPL.2 Product Release. System Engineering (SYS) comprises five processes: SYS.1 Requirements Elicitation, SYS.2 System Requirements Analysis, SYS.3 System Architectural Design, SYS.4 System Integration and Integration Test, and SYS.5 System Qualification Test. Software Engineering (SWE) comprises six processes following the classic V-model: SWE.1 Software Requirements Analysis, SWE.2 Software Architectural Design, SWE.3 Software Detailed Design and Unit Construction, SWE.4 Software Unit Verification, SWE.5 Software Integration and Integration Verification, and SWE.6 Software Verification. Validation (VAL) is new in 4.0 with a single process VAL.1 ensuring overall system performance against stakeholder expectations. Hardware Engineering (HWE), also new, adds four processes — HWE.1 through HWE.4 — covering requirements analysis, architectural design, detailed design, and verification of electrical/electronic hardware. Machine Learning Engineering (MLE), the third new group, adds MLE.1 through MLE.4 covering ML requirements analysis, ML architecture, ML training, and ML deployment and monitoring.

**Organizational Life Cycle Processes** comprise three groups. Management (MAN) includes MAN.3 Project Management, MAN.5 Risk Management, and MAN.6 Measurement Management. Process Improvement (PIM) contains PIM.3 Process Improvement. Reuse (REU) contains REU.2 Reuse Program Management.

**Supporting Life Cycle Processes** contain a single group (SUP) reduced from eleven to five processes: SUP.1 Quality Assurance, SUP.8 Configuration Management, SUP.9 Problem Resolution Management, SUP.10 Change Request Management, and SUP.11 Machine Learning Data Management (new in 4.0).

### Capability Dimension

Processes are assessed against six capability levels. Level 0 (Incomplete) means the process is not implemented or fails its purpose. Level 1 (Performed) requires that base practices achieve the process purpose. Level 2 (Managed) adds performance management and work product management — processes are planned, monitored, and their outputs controlled. Level 3 (Established) requires a defined, documented process deployed consistently across the organization. Levels 4 (Predictable) and 5 (Innovating) add statistical process control and continuous improvement respectively. Each level is assessed through process attributes rated on a four-point scale: Not achieved (0–15%), Partially achieved (15–50%), Largely achieved (50–85%), and Fully achieved (85–100%). To achieve a given level, all lower-level attributes must be Fully achieved and the current level's attributes must be at least Largely achieved.

### Key Changes from ASPICE 3.1

ASPICE 4.0 introduces a terminology shift from "work products" to "information items," reflecting tool-agnostic, information-centric documentation practices. Strategy documents are now required starting at Capability Level 2 rather than Level 1. The model adds nine new processes (HWE.1–4, MLE.1–4, VAL.1, SUP.11) and removes several legacy processes (SUP.2 Verification, SUP.4 Joint Review, SUP.7 Documentation, and most acquisition/supply processes). Safety and cybersecurity integration is strengthened throughout, aligning with ISO 26262 and ISO/SAE 21434.

---

## Structural Comparison with ISO/IEC/IEEE Standards

### Process Architecture Alignment

The five ISO standards and ASPICE 4.0 share a common ancestry. ISO/IEC/IEEE 15288:2023 and 12207:2026 define 30 processes each in four to five groups — Agreement, Organizational Project-Enabling, Technical Management, and Technical. ASPICE 4.0's 32 processes in 11 groups are a domain-specific subset and extension of this architecture. The relationship is one of selective derivation: ASPICE cherry-picks processes from 15288/12207, renames and refines them for automotive context, and adds domain-specific engineering disciplines.

| Dimension | ISO 15288/12207 | ASPICE 4.0 |
|---|---|---|
| Total processes | 30 each | 32 |
| Process groups | 4–5 generic groups | 11 automotive-specific groups |
| Engineering disciplines | Generic "Technical Processes" | Separate SYS, SWE, HWE, MLE groups |
| Assessment framework | Not built-in; assessed via ISO 33000 | PAM built-in, conformant to ISO 33000 |
| Capability levels | Defined by ISO 33000 (0–5) | Same 0–5 scale, automotive indicators |
| Lifecycle model | Methodology-agnostic | V-model emphasis, methodology-flexible |
| Domain scope | All industries | Automotive embedded systems |

### Process-Level Mapping

The following mapping traces each ASPICE 4.0 process to its closest ISO 15288/12207 counterpart and identifies the gap.

**System Engineering (SYS) ↔ ISO 15288 Technical Processes.** SYS.1 Requirements Elicitation maps to the Stakeholder Needs and Requirements Definition process in 15288, with IEEE 29148's StRS artifact providing the documentation structure. SYS.2 System Requirements Analysis maps to System Requirements Definition in 15288, with the SyRS artifact from IEEE 29148. SYS.3 System Architectural Design maps to System Architecture Definition and System Design Definition in 15288. SYS.4 and SYS.5 map to System Integration, System Verification, and System Validation respectively. The ISO processes are more granular — 15288 separates integration, verification, and validation into three distinct processes, while ASPICE bundles integration with integration test (SYS.4) and uses a separate qualification test (SYS.5) plus the new VAL.1.

**Software Engineering (SWE) ↔ ISO 12207 Technical Processes.** SWE.1 maps to System/Software Requirements Analysis in 12207 (and IEEE 29148's SRS). SWE.2 maps to Architectural Design. SWE.3 maps to Design and Implementation (Construction). SWE.4 through SWE.6 map to Verification, with ASPICE being more granular — it separates unit verification, integration verification, and overall software verification, while 12207 has a single Verification process. This granularity reflects ASPICE's V-model traceability requirements.

**Hardware Engineering (HWE) — No Direct ISO Counterpart.** ISO 15288 covers hardware as a system element type within its generic processes, but provides no hardware-specific engineering processes. HWE.1–4 are entirely automotive-specific. Organizations implementing both systems must treat HWE processes as ASPICE extensions layered on top of the ISO framework.

**Machine Learning Engineering (MLE) — No Direct ISO Counterpart.** Neither 15288 nor 12207 addresses machine learning as a distinct engineering discipline. MLE.1–4 and SUP.11 are ASPICE innovations that have no ISO mapping. These processes represent an area where ASPICE is ahead of the international standards.

**Validation (VAL.1) ↔ ISO 15288 System Validation.** VAL.1 maps directly to the System Validation process in 15288 and the Validation process in 12207. The ASPICE version emphasizes real-world, end-to-end system-level validation, consistent with the ISO definition.

**Management (MAN) ↔ ISO 15288/12207 Technical Management Processes.** MAN.3 Project Management maps to Project Planning and Project Assessment and Control in 15288/12207. MAN.5 Risk Management maps directly to the Risk Management process. MAN.6 Measurement Management maps to the Measurement process. The ISO standards provide additional management processes — Decision Management, Information Management — that ASPICE does not explicitly include as named processes but expects as organizational capability.

**Supporting (SUP) ↔ ISO 15288/12207.** SUP.1 Quality Assurance maps to Quality Management in the ISO organizational processes. SUP.8 Configuration Management maps directly. SUP.9 and SUP.10 (Problem Resolution and Change Request Management) map to aspects of Configuration Management and the Request information item type in 15289. SUP.11 ML Data Management has no ISO counterpart.

**Organizational (PIM, REU) ↔ ISO 15288/12207.** PIM.3 Process Improvement maps to Life Cycle Model Management. REU.2 Reuse Program Management maps to aspects of Knowledge Management. These processes appear in the ASPICE Extended Process Set and are typically required only at Capability Level 3.

### Documentation and Artifact Alignment

ASPICE 4.0's information items align well with the artifact hierarchy defined across IEEE 29148 and ISO/IEC/IEEE 15289. IEEE 29148's BRS → StRS → SyRS → SRS hierarchy maps directly to the requirements artifacts expected across SYS.1, SYS.2, and SWE.1. The RTM and VCRM from 29148 satisfy ASPICE's bidirectional traceability expectations. ISO 15289's seven generic information item types — Description, Plan, Policy, Procedure, Report, Request, Specification — provide a content framework that covers every ASPICE information item category. The ASPICE shift to "information items" in 4.0 actually moves the model closer to 15289's approach, which has always focused on content requirements rather than prescriptive document formats.

### VSE Profile Applicability

ISO/IEC 29110 profiles provide a scaled-down implementation path that can serve as a stepping stone toward ASPICE compliance. The Basic profile's two-process model (Project Management + Software Implementation) aligns with a minimal subset of ASPICE: MAN.3 for project management and a collapsed version of SWE.1–6 for software implementation. The Intermediate profile adds multi-project management and measurement, moving closer to ASPICE's MAN.5 and MAN.6. However, 29110 does not address system engineering, hardware engineering, or machine learning — its utility as an ASPICE on-ramp is limited to software-only projects.

---

## Key Differences and Gaps

### Where ASPICE Exceeds the ISO Standards

**V-model traceability granularity.** ASPICE enforces explicit bidirectional traceability at every V-model level — from system requirements through architectural design, detailed design, unit test, integration test, software verification, and system qualification test. The ISO standards define traceability as a process outcome but do not prescribe the same level of granular, level-by-level linkage.

**Verification decomposition.** ASPICE separates verification into three distinct levels (SWE.4 unit, SWE.5 integration, SWE.6 software) plus system-level qualification (SYS.5). ISO 12207 defines a single Verification process. This ASPICE granularity is essential for automotive safety demonstration.

**Hardware and ML engineering.** ASPICE 4.0's HWE and MLE groups address engineering disciplines that the ISO lifecycle standards treat only generically. Organizations doing mechatronic or AI-enabled automotive development need these ASPICE processes and cannot derive equivalent guidance from 15288/12207 alone.

**Supplier monitoring.** ACQ.4 provides specific practices for monitoring supplier process capability and product quality in an automotive supply chain context. The ISO Acquisition process is broader but less operationally specific.

**Capability assessment framework.** While the ISO 33000 series defines the assessment methodology, ASPICE 4.0 provides a ready-made, automotive-calibrated PAM with specific base practices, information items, and information item characteristics for every process. The ISO standards require organizations to build their own PAM or adopt one.

### Where the ISO Standards Exceed ASPICE

**Process completeness.** ISO 15288/12207 define 30 processes covering areas ASPICE deliberately excludes — Business or Mission Analysis, Stakeholder Needs and Requirements Definition (as a standalone process separate from system requirements), Portfolio Management, Human Resource Management, Knowledge Management, Infrastructure Management, System Operation, System Maintenance, System Disposal, and System Transition. Organizations need these processes for a complete lifecycle but will not be assessed against them in an ASPICE audit.

**Documentation content guidance.** ISO 15289 provides detailed content specifications for every information item type — minimum content, structural guidance, and lifecycle management. ASPICE defines information item characteristics but does not provide the same depth of content architecture.

**Requirements engineering rigor.** IEEE 29148 provides substantially more detailed guidance on requirements quality attributes, artifact hierarchies, and traceability structures than ASPICE's SYS.1/SYS.2/SWE.1 base practices. Using 29148 to implement the requirements processes will exceed ASPICE expectations.

**VSE scalability.** ISO 29110's profile-based scaling has no ASPICE equivalent. ASPICE applies the same process model regardless of organization size, though the capability level targeted can serve as an informal scaling mechanism.

**Methodology neutrality.** ISO 15288/12207 are explicitly methodology-agnostic and provide guidance for agile, DevOps, and hybrid approaches. ASPICE 4.0 is methodology-flexible but retains a V-model structural emphasis that shapes how processes are grouped and assessed.

---

## Selection Guide

| Organization Profile | Recommended Approach | Rationale |
|---|---|---|
| Automotive Tier-1 supplier, full mechatronic scope (SW + HW + ML) | ASPICE 4.0 full scope, ISO 15288 + 15289 + 29148 as implementation foundation | ASPICE assessment is mandatory; ISO standards provide process completeness and documentation depth beyond what ASPICE alone requires |
| Automotive software supplier, software-only scope | ASPICE SWE + SYS + SUP + MAN processes, ISO 12207 + 29148 as implementation backbone | Focused scope; ISO 12207 provides the lifecycle framework, IEEE 29148 ensures requirements quality |
| VSE entering automotive supply chain | ISO 29110 Basic profile as starting point, progressively adopt ASPICE SWE + MAN.3 processes | Achieves baseline process maturity before committing to full ASPICE compliance |
| Organization with existing ISO 15288/12207 processes seeking ASPICE certification | Gap analysis against ASPICE PAM 4.0, add V-model traceability granularity, HWE/MLE processes, and automotive-specific base practices | Existing ISO processes cover 60–70% of ASPICE requirements; focus on the gaps |
| AI/ML-enabled automotive product development | ASPICE MLE + SUP.11 processes overlaid on ISO 15288/12207 lifecycle framework | No ISO equivalent for ML engineering; ASPICE MLE group is the only structured guidance available |

---

## MVP Process Integration Proposal

This section proposes a minimum viable process framework that achieves ASPICE Capability Level 2 compliance for hardware-plus-software product engineering while using the ISO standards as the foundational architecture. The MVP targets an organization developing non-safety-critical embedded products that contain both electrical/electronic hardware and software as system elements. Because the products are not classified as safety-critical, ISO 26262 functional safety processes are out of scope — though the process architecture is designed to accommodate safety extension later if product classification changes.

### Target Scope

The assessment scope for a hardware-plus-software product encompasses the ASPICE Basic Process Set extended with the HWE group: SYS.1, SYS.2, SYS.3, SYS.4, SYS.5 (system engineering); SWE.1, SWE.2, SWE.3, SWE.4, SWE.5, SWE.6 (software engineering); HWE.1, HWE.2, HWE.3, HWE.4 (hardware engineering); VAL.1 (validation); MAN.3 (project management); SUP.1, SUP.8, SUP.9, SUP.10 (supporting processes). This MVP addresses all twenty-one processes. Machine learning processes (MLE.1–4, SUP.11) are excluded — these can be added later if product scope evolves to include ML-based features.

### Architectural Principle

Use ISO/IEC/IEEE 15288:2023 as the master process architecture. 15288 is the systems engineering standard and treats hardware, software, data, and human elements as peers within its process framework — making it the natural backbone for a joint HW+SW product. Map each ASPICE process to its 15288 counterpart, implement using 15288's process descriptions as the structural foundation, and augment with ASPICE-specific base practices and information item characteristics where the ISO process description is insufficient. Use ISO/IEC/IEEE 12207:2026 alongside 15288 for software-specific process detail. Use IEEE 29148:2018 to implement all requirements processes across both disciplines (SYS.1, SYS.2, SWE.1, HWE.1). Use ISO/IEC/IEEE 15289:2019 to define information item content for all processes. Use ISO/IEC 29110 Intermediate profile concepts for multi-discipline project coordination where applicable.

### System Architecture as the Integration Point

In a HW+SW product, the system architecture (SYS.3) is the critical integration point where hardware and software responsibilities are allocated. The system architectural design decomposes the product into system elements — some realized as software components (governed by SWE processes), others as hardware components (governed by HWE processes), and potentially some as purchased or reused elements. Every downstream engineering process on both the HW and SW branches traces back to SYS.3 allocation decisions. This means the system architecture must explicitly define hardware-software interfaces, allocation of functional requirements to HW or SW elements, shared resource constraints (memory, bus bandwidth, timing budgets, power), and integration strategy across disciplines. ISO 15288's System Architecture Definition and System Design Definition processes provide the structural framework; ASPICE's SYS.3 base practices add the automotive expectation that allocation rationale and interface specifications are formally documented and traceable.

### Process Implementation Map

**Requirements Tier — SYS.1, SYS.2, SWE.1, HWE.1.** Implement using IEEE 29148 as the primary guide across all four processes. Produce a StRS (satisfying SYS.1 elicitation outcomes), a SyRS (satisfying SYS.2 analysis outcomes), an SRS (satisfying SWE.1 analysis outcomes), and an HRS — Hardware Requirements Specification (satisfying HWE.1 analysis outcomes). The SRS and HRS are derived from the SyRS through the allocation decisions made in SYS.3. Establish the RTM from 29148 to maintain bidirectional traceability across all four levels: stakeholder needs → system requirements → software requirements and hardware requirements. Apply 29148's requirements quality attributes (unambiguous, complete, verifiable, singular, traceable) as review criteria for both HW and SW requirements. Content structure per ISO 15289 Specification type. ASPICE augmentation: ensure each requirement is individually identifiable and traceable to its parent and to downstream design and verification artifacts. For hardware requirements specifically, include electrical, thermal, mechanical, and environmental constraints alongside functional requirements. Interface requirements between HW and SW elements — signal definitions, timing constraints, communication protocols, power sequencing — must be captured in both the SRS and HRS with cross-references.

**Architecture and Design Tier — SYS.3, SWE.2, SWE.3, HWE.2, HWE.3.** Implement using 15288's System Architecture Definition and System Design Definition processes as the common framework. The system architecture (SYS.3) defines the product decomposition and HW/SW allocation. Software architecture (SWE.2) and hardware architecture (HWE.2) are developed in parallel, constrained by the system architecture's interface and resource allocation decisions.

For software: SWE.2 requires both static aspects (module structure, interfaces, dependencies) and dynamic aspects (timing, state machines, messaging). SWE.3 requires detailed design sufficient for code generation and unit test derivation. Produce architecture and design descriptions following 15289's Description information item type.

For hardware: HWE.2 covers schematic-level architectural design including block diagrams, component topology, bus architecture, and dynamic aspects such as timing and signal integrity. HWE.3 covers detailed design — PCB layout, component selection, manufacturing data (gerbers, BOMs, assembly drawings), and design-for-test provisions. Produce hardware design descriptions following 15289's Description type, supplemented with industry-standard EDA tool outputs.

Document rationale for architectural decisions, technology selections, and interface definitions on both sides. Maintain a single system-level interface specification that both the SW and HW teams reference — this satisfies both ISO 15288's architecture process outcomes and ASPICE's information item characteristics for cross-discipline consistency.

**Verification Tier — SWE.4, SWE.5, SWE.6, HWE.4, SYS.4, SYS.5, VAL.1.** This is where the HW+SW product requires careful orchestration across disciplines. Implement a multi-level verification strategy spanning both engineering branches, converging at system integration.

Software verification follows three levels: SWE.4 (unit verification) with test specifications derived from SWE.3 detailed design and code coverage metrics; SWE.5 (integration verification) with test specifications derived from SWE.2 architectural design, verifying inter-component interfaces; SWE.6 (software verification) with comprehensive testing against SWE.1 requirements, establishing requirements-to-test traceability via the VCRM from IEEE 29148.

Hardware verification (HWE.4) covers electrical verification (schematic review, simulation), physical verification (prototype testing against HWE.1 requirements), environmental testing where applicable (thermal, EMC, vibration — scoped to product risk rather than safety-critical rigor), and design rule compliance. Because the products are non-safety-critical, hardware verification focuses on functional correctness and reliability rather than the exhaustive failure mode analysis that ISO 26262 would require.

System integration and test (SYS.4) brings verified software and verified hardware together. Integration test specifications are derived from SYS.3 architecture, with particular attention to HW/SW interface verification — confirming that software correctly drives hardware interfaces, timing constraints are met, shared resources behave as allocated, and the integrated system handles boundary conditions. System qualification test (SYS.5) tests the integrated product against SYS.2 system requirements. Validation (VAL.1) performs end-to-end validation against SYS.1 stakeholder requirements in conditions representative of the intended operating environment.

Use ISO 15289's Report and Plan information item types for test plans, test reports, and verification/validation reports across all levels and disciplines.

**Management Tier — MAN.3.** Implement using 15288's Project Planning and Project Assessment and Control processes. For a HW+SW product, project management must coordinate across engineering disciplines with different development cadences — hardware prototyping cycles are typically longer than software iterations. The project plan must define the integration strategy early: when hardware prototypes will be available for software integration, what simulation or emulation environments bridge the gap, and how HW and SW milestones align. Produce a Project Management Plan per ISO 15289 Plan type. ASPICE augmentation: ensure the plan covers work breakdown across both disciplines, schedule with explicit HW/SW synchronization points, resource allocation, risk identification (including cross-discipline risks such as late hardware availability), and defined review/decision points. At Capability Level 2, the project must demonstrate that MAN.3 is planned, monitored, and adjusted — not merely performed.

**Supporting Tier — SUP.1, SUP.8, SUP.9, SUP.10.** These processes span both engineering disciplines and must be implemented as unified organizational capabilities rather than discipline-specific silos.

SUP.1 Quality Assurance: implement using 15288's Quality Management process. QA must independently verify process adherence and work product quality across both HW and SW activities. Produce QA plans and audit reports per ISO 15289 Plan and Report types. ASPICE augmentation: QA audits should cover both SW process compliance (code reviews, test coverage) and HW process compliance (design reviews, verification test adequacy).

SUP.8 Configuration Management: implement using 15288's Configuration Management process. This is particularly important in HW+SW products where software versions must be tracked against specific hardware revisions. The CM system must manage SW source code, build artifacts, HW design files (schematics, PCB layouts, BOMs), firmware images, and the mappings between compatible HW/SW versions. Produce a CM plan per ISO 15289 Plan type, establish baselines that encompass both disciplines, and control changes with impact analysis that considers cross-discipline effects.

SUP.9 and SUP.10 Problem Resolution and Change Request Management: implement using ISO 15289's Request and Report information item types. A single problem resolution and change management process serves both disciplines. ASPICE augmentation: ensure problem reports and change requests are individually tracked, analyzed for cross-discipline impact (a hardware change may invalidate software assumptions and vice versa), and linked to affected baselines and requirements in both the SRS and HRS.

### Capability Level 2 Overlay

Achieving Capability Level 2 requires two process attributes beyond Level 1's base practice execution. PA 2.1 Performance Management requires that each process is planned with defined objectives, monitored against the plan, and adjusted when deviations occur. PA 2.2 Work Product Management requires that information items are identified, documented, controlled, reviewed, and maintained under configuration management. To satisfy these attributes across all twenty-one processes, implement the following organizational infrastructure.

**Process planning templates.** For each process, maintain a brief process plan (or a section within the project management plan) that states objectives, inputs, outputs, responsible roles, and review criteria. ISO 15289's Plan information item type provides the content framework. For HWE processes, include hardware-specific planning elements: prototype build schedules, EDA tool configurations, component procurement lead times, and test equipment availability.

**Work product identification and control.** Maintain a master information item register listing every artifact, its owning process, its baseline status, and its review/approval state. This register must span both SW and HW artifacts and track cross-discipline dependencies (for example, an interface specification referenced by both SWE.2 and HWE.2). The register, combined with version control (SUP.8) and the RTM (IEEE 29148), provides the evidence trail that assessors require.

**Review and approval gates.** Define review criteria for each information item type. At minimum: requirements reviews (SYS.1, SYS.2, SWE.1, HWE.1), system architecture review (SYS.3 — with both HW and SW stakeholders), software design reviews (SWE.2, SWE.3), hardware design reviews (HWE.2, HWE.3), test readiness reviews (SWE.4–6, HWE.4, SYS.4–5), and validation reviews (VAL.1). The system architecture review and system integration reviews are particularly critical — these are the gates where HW/SW alignment is verified. Document review results as Report information items per ISO 15289.

### Non-Safety-Critical Scope Implications

Because the target products are not safety-critical, several process simplifications apply compared to a full ISO 26262-aligned development. There is no requirement for an ASIL decomposition or safety case. Hardware verification (HWE.4) focuses on functional correctness and reliability testing rather than FMEA/FMEDA failure rate analysis. Software verification does not require ASIL-dependent code coverage targets (e.g., MC/DC coverage). Validation (VAL.1) tests against stakeholder requirements and intended use but does not need to demonstrate freedom from interference or safe state transitions. Risk management (MAN.5, part of the ASPICE Extended Process Set) is recommended but not required for the Capability Level 2 Basic Process Set — however, maintaining a lightweight risk register is good practice and prepares the organization for future safety-critical work. If the product classification changes, the existing process architecture can be extended with safety processes by adding ISO 26262 safety management on top of the ASPICE/ISO framework without restructuring the core engineering processes.

### Implementation Phases

**Phase 1 — Foundation (Months 1–2).** Adopt ISO 15288 as the master process framework. Establish configuration management (SUP.8) infrastructure that handles both SW and HW artifacts — version control for code and design files, baseline management, HW/SW compatibility tracking. Establish project management (MAN.3) infrastructure with cross-discipline coordination mechanisms. Define information item templates using ISO 15289 content guidance. Set up the RTM structure per IEEE 29148, including the four-level hierarchy (stakeholder → system → software/hardware).

**Phase 2 — Engineering Processes (Months 2–5).** Implement the requirements tier (SYS.1, SYS.2, SWE.1, HWE.1) using IEEE 29148, with explicit HW/SW interface requirements. Implement the system architecture process (SYS.3) with formal HW/SW allocation and interface specification. Implement software architecture and design (SWE.2, SWE.3) and hardware architecture and design (HWE.2, HWE.3) in parallel, coordinated through SYS.3 interface specifications. Implement the multi-level verification strategy: software verification (SWE.4–6), hardware verification (HWE.4), system integration and qualification (SYS.4–5), and validation (VAL.1).

**Phase 3 — Supporting and Assessment Readiness (Months 5–7).** Implement QA (SUP.1) covering both disciplines, problem resolution (SUP.9), and change management (SUP.10) with cross-discipline impact analysis. Establish Capability Level 2 overlay — process plans, work product registers, review gates. Conduct internal trial assessment against ASPICE PAM 4.0 with HWE scope included. Address gaps identified in trial assessment.

### Tooling Considerations

The MVP does not prescribe specific tools, but the process framework assumes: a version control system capable of managing both software source code and hardware design files (satisfying SUP.8 across disciplines); a requirements management tool supporting bidirectional traceability across the four-level hierarchy — stakeholder, system, software, and hardware requirements (satisfying IEEE 29148 RTM/VCRM and ASPICE traceability expectations); a test management tool supporting requirements-to-test linkage for both SW and HW verification (satisfying the verification tier); an issue/change tracking system with cross-discipline linking (satisfying SUP.9 and SUP.10); and an EDA toolchain for hardware design, simulation, and manufacturing data generation (satisfying HWE.2 and HWE.3 design process needs). These five tool categories, combined with a document repository structured around ISO 15289 information item types, form the minimum tooling infrastructure for ASPICE Capability Level 2 on a HW+SW product.

---

## Industry Trends

- **ASPICE 4.0 adoption acceleration** — The automotive industry is migrating from ASPICE 3.1 to 4.0, with most OEMs requiring 4.0-based assessments for new programs starting in 2025–2026. The transition is non-trivial due to structural changes in process groups, terminology shifts, and new engineering disciplines.

- **ISO/ASPICE convergence** — ASPICE 4.0's move toward "information items" and its continued alignment with ISO/IEC 33000 narrows the gap between ASPICE and the ISO lifecycle standards. Organizations already ISO-compliant face a shorter path to ASPICE readiness than in previous versions.

- **ML and AI process standardization** — ASPICE 4.0's MLE group is the first widely adopted process framework for automotive ML engineering. ISO/IEC is developing standards in this space (notably ISO/IEC 5338 for AI lifecycle management), but ASPICE currently leads in automotive-specific ML process guidance.

- **Hardware-software co-engineering** — The addition of HWE processes reflects the industry's shift toward integrated mechatronic development. Organizations can no longer treat software and hardware processes as independent silos — ASPICE 4.0 expects coordinated V-model traceability across SYS, SWE, and HWE.

- **Agile-ASPICE reconciliation** — While ASPICE retains V-model structural emphasis, the 4.0 revision's methodology flexibility and information-centric approach make it more compatible with iterative and agile workflows. The challenge is demonstrating traceability and review evidence in continuous-delivery environments — an area where ISO 12207:2026's enhanced agile/DevOps guidance can complement ASPICE implementation.

- **Cybersecurity process integration** — Alignment with ISO/SAE 21434 is becoming a de facto expectation in ASPICE assessments, even though cybersecurity processes are not formally part of the ASPICE PAM. Organizations should plan for joint ASPICE + cybersecurity process assessments.

---

## References

### ASPICE 4.0 Sources

- **VDA Quality Management Center — Official Automotive SPICE Home:** <https://vda-qmc.de/en/automotive-spice/>
- **Automotive SPICE PAM 4.0 Process Assessment Model:** <https://vda-qmc.de/wp-content/uploads/2023/12/Automotive-SPICE-PAM-v40.pdf>
- **Automotive SPICE PRM 4.5 Process Reference Model:** <https://automotivespice.com/fileadmin/software-download/automotiveSIG_PRM_v45.pdf>
- **UL Solutions — Automotive SPICE 4.0 Pocket Guide:** <https://www.ul.com/sites/default/files/2024-10/Automotive_Spice_Pocket_Guide.pdf>
- **Expleo — Automotive SPICE 4.0 Process Guide and Workbook:** <https://expleo.com/global/en/wp-content/documents/ASPICE%20BOOKLET_DIGI%204.0.pdf>
- **SPKAA — A Comprehensive Guide to Automotive SPICE:** <https://www.spkaa.com/wp-content/uploads/2023/12/A-Comprehensive-Guide-to-Automotive-SPICE.pdf>
- **SPICE Booklet 2024, 8th Edition:** <https://cdn.prod.website-files.com/664c628bfa8d7e605ce041ef/669f76d2ae3fc71a0805672a_SPICE-BOOKLET-2024-8th-Edition.pdf>
- **UL Solutions / Kugler Maag — Automotive SPICE 4.0 What Is New:** <https://process-insights.org/wp-content/uploads/2023/09/Kugler%20Maag%20by%20UL%20Solutions%20-%20Automotive%20SPICE%204.0.%20What%20is%20new.pdf>
- **Promwad — What's New in ASPICE 4.0:** <https://promwad.com/news/aspice-4.0>
- **Eclipse SCORE — ASPICE 4.0 Process Documentation:** <https://eclipse-score.github.io/score/main/process/standards/aspice_40/aspice.html>
- **UL Solutions — Automotive SPICE Machine Learning Engineering:** <https://www.ul.com/sis/resources/automotive-spice-machine-learning-engineering-mle>

### ISO/IEC/IEEE Standards

- **ISO/IEC/IEEE 15288:2023** — *Systems and software engineering — System life cycle processes*, 2nd ed. <https://www.iso.org/standard/81702.html>
- **ISO/IEC/IEEE 12207:2026** — *Systems and software engineering — Software life cycle processes*, 2nd ed. <https://standards.ieee.org/ieee/12207/11416/>
- **ISO/IEC 29110-1-1:2024** — *Systems and software engineering — Lifecycle profiles for Very Small Entities (VSEs) — Part 1-1: Overview*. <https://www.iso.org/standard/85337.html>
- **IEEE 29148:2018** — *Systems and software engineering — Life cycle processes — Requirements engineering*. <https://standards.ieee.org/standard/29148-2018.html>
- **ISO/IEC/IEEE 15289:2019** — *Systems and software engineering — Content of life-cycle information items (documentation)*. <https://www.iso.org/standard/74909.html>

### Assessment Framework Standards

- **ISO/IEC 33001:2015** — *Information technology — Process assessment — Concepts and terminology*
- **ISO/IEC 33002:2015** — *Information technology — Process assessment — Requirements for performing process assessment*
- **ISO/IEC 33004:2015** — *Information technology — Process assessment — Requirements for process reference, process assessment and maturity models*
- **ISO/IEC 33020:2015** — *Information technology — Process assessment — Process measurement framework for assessment of process capability*

### Related Automotive Standards

- **ISO 26262** — *Road vehicles — Functional safety*
- **ISO/SAE 21434** — *Road vehicles — Cybersecurity engineering*
- **IATF 16949** — *Quality management system requirements for automotive production and relevant service parts organizations*

---

## Appendix A — CMMI V3.0 Overlap and Gap Analysis

This appendix summarizes CMMI V3.0 (released April 2023, the current version as of early 2026) and analyzes its overlap and gaps relative to ASPICE 4.0 and the five ISO/IEC/IEEE lifecycle standards covered in this report. CMMI V3.0 is maintained by ISACA (formerly the CMMI Institute). It is a general-purpose process improvement framework — not automotive-specific — but it is widely used by organizations that also face ASPICE or ISO compliance requirements, and understanding the relationships helps avoid duplicate process implementation effort.

### CMMI V3.0 Model Summary

CMMI V3.0 organizes approximately 25 practice areas into four category areas: Doing (core engineering and delivery), Managing (project and performance management), Enabling (organizational infrastructure and support), and Improving (continuous process improvement). The model operates on two representational dimensions. In the continuous representation, individual practice areas are rated on capability levels 0 through 5 (Incomplete, Performed, Managed, Defined, Quantitatively Managed, Optimizing). In the staged representation, the organization as a whole is rated on maturity levels 1 through 5 (Initial, Managed, Defined, Quantitatively Managed, Optimizing).

CMMI V3.0 superseded V2.2 (retired June 2024) and introduced three new practice areas — Data Management, Data Quality, and Workforce Empowerment — along with a "Managing Data" capability area. It also renamed Enabling Virtual Solution Delivery to Enabling Virtual Work. The model now provides context-specific guidance across eight integrated domains: Data, Development, People, Safety, Security, Services, Suppliers, and Virtual. The earlier separate "constellations" (CMMI-DEV, CMMI-SVC, CMMI-ACQ) were unified into a single model starting with V2.0; V3.0 continues this unified approach with domain-specific practice selections.

Appraisals are conducted using the SCAMPI (Standard CMMI Appraisal Method for Process Improvement) methodology in three classes: SCAMPI A (formal, provides official ratings), SCAMPI B (moderate, gap analysis), and SCAMPI C (lightweight, diagnostic). Only SCAMPI A provides recognized maturity or capability level ratings.

### Practice Area Mapping to ASPICE 4.0 and ISO Standards

The following table maps CMMI V3.0 practice areas to their closest ASPICE 4.0 processes and ISO/IEC/IEEE standard counterparts, identifying the degree of overlap.

| CMMI V3.0 Practice Area | Category | ASPICE 4.0 Mapping | ISO 15288/12207 Mapping | Overlap Degree |
|---|---|---|---|---|
| Requirements Development & Management (RDM) | Doing | SYS.1, SYS.2, SWE.1, HWE.1 | Stakeholder Needs & Reqts Definition, System Reqts Definition; IEEE 29148 | Strong |
| Technical Solution (TS) | Doing | SYS.3, SWE.2, SWE.3, HWE.2, HWE.3 | Architecture Definition, Design Definition | Strong |
| Product Integration (PI) | Doing | SYS.4, SWE.5 | System Integration | Strong |
| Verification & Validation (VV) | Doing | SWE.4, SWE.5, SWE.6, HWE.4, SYS.5, VAL.1 | Verification, Validation | Moderate — CMMI bundles V&V as one PA; ASPICE separates into six processes |
| Configuration Management (CM) | Doing | SUP.8 | Configuration Management | Strong |
| Planning (PLAN) | Managing | MAN.3 (planning aspect) | Project Planning | Strong |
| Monitor & Control (M&C) | Managing | MAN.3 (monitoring aspect) | Project Assessment and Control | Strong |
| Estimating (EST) | Managing | MAN.3 (embedded in project planning) | Project Planning (estimation activities) | Moderate — CMMI separates estimation; ASPICE embeds it in MAN.3 |
| Risk & Opportunity Management (ROM) | Managing | MAN.5 | Risk Management | Strong |
| Managing Performance & Measurement (MPM) | Managing | MAN.6 | Measurement | Strong |
| Governance (GOV) | Managing | No direct mapping | Portfolio Management, Life Cycle Model Management | Partial — CMMI governance is broader than ASPICE scope |
| Agreement Management (AM) | Managing | ACQ.4 (partial) | Acquisition | Moderate |
| Supplier Agreement Management (SAM) | Managing | ACQ.4, SPL.2 | Acquisition, Supply | Moderate |
| Process Quality Assurance (PQA) | Improving | SUP.1 | Quality Management | Strong |
| Causal Analysis & Resolution (CAR) | Improving | SUP.9 (partial) | No direct counterpart | Moderate — CMMI CAR is more structured than ASPICE problem resolution |
| Decision Analysis & Resolution (DAR) | Improving | No direct mapping | Decision Management | Strong (ISO); gap in ASPICE |
| Peer Reviews (PR) | Improving | Embedded in engineering process base practices | Embedded in Verification | Moderate — CMMI makes peer review explicit; ASPICE and ISO embed it |
| Process Asset Development (PAD) | Enabling | PIM.3 (partial) | Life Cycle Model Management | Moderate |
| Organizational Training (OT) | Enabling | No direct mapping | Human Resource Management | Partial — ASPICE does not address training |
| Implementation Infrastructure (II) | Enabling | No direct mapping | Infrastructure Management | Partial — ASPICE does not address infrastructure |
| Process Management (PM) | Enabling | PIM.3 | Life Cycle Model Management | Strong |
| Data Management (DM) | Enabling | SUP.11 (ML Data Management only) | Information Management | Partial — CMMI is general data; ASPICE only ML data |
| Data Quality (DQ) | Enabling | SUP.11 (partial) | No direct counterpart | Weak — CMMI DQ is general; ASPICE covers only ML data quality |
| Workforce Empowerment (WE) | Enabling | No mapping | Human Resource Management | Gap — ASPICE has no workforce practice |
| Enabling Virtual Work (EVW) | Enabling | No mapping | No direct counterpart | Gap — unique to CMMI V3.0 |

### Where CMMI Exceeds ASPICE and the ISO Standards

**Organizational maturity framework.** CMMI's staged representation provides a holistic organizational maturity assessment (Levels 1–5) that neither ASPICE nor the ISO lifecycle standards offer. ASPICE assesses process capability per-process but does not aggregate to an organizational maturity rating. ISO 33000 defines capability levels for individual processes but does not prescribe organizational maturity. Organizations seeking an enterprise-wide maturity benchmark need CMMI or an equivalent.

**People and workforce practices.** CMMI V3.0's Organizational Training (OT) and Workforce Empowerment (WE) practice areas address human capability development and team effectiveness — areas that ASPICE deliberately excludes from its process model and that the ISO lifecycle standards cover only through the generic Human Resource Management process in 15288/12207.

**Data management beyond ML.** CMMI V3.0's Data Management and Data Quality practice areas cover general organizational data governance. ASPICE's SUP.11 addresses only ML data management. ISO 15288/12207's Information Management process is narrower than CMMI's data-focused PAs. For organizations managing significant non-ML data assets (telemetry, fleet data, manufacturing data), CMMI provides governance structure that ASPICE lacks.

**Decision analysis.** CMMI's Decision Analysis & Resolution (DAR) practice area provides structured guidance for formal evaluation of alternatives — a practice that ASPICE does not name as a distinct process. ISO 15288/12207 include a Decision Management process, so DAR maps well to the ISO side but represents a gap relative to ASPICE.

**Estimation as a distinct practice.** CMMI separates Estimating (EST) from project planning, providing more detailed guidance on estimation methods, basis of estimates, and estimation accuracy tracking. ASPICE and the ISO standards embed estimation within project planning activities.

**Virtual and distributed work.** CMMI V3.0's Enabling Virtual Work practice area addresses challenges of distributed and remote teams — a topic neither ASPICE nor the ISO lifecycle standards cover.

### Where ASPICE and the ISO Standards Exceed CMMI

**Engineering process granularity.** ASPICE's separation of verification into unit (SWE.4), integration (SWE.5), and software-level (SWE.6) processes — plus separate system integration test (SYS.4) and qualification test (SYS.5) — provides far more granular engineering process guidance than CMMI's single Verification & Validation practice area. For a HW+SW product, this granularity is essential.

**V-model traceability.** ASPICE enforces explicit bidirectional traceability at every V-model level. CMMI's Requirements Development & Management covers traceability but does not prescribe the same level-by-level linkage structure. IEEE 29148's RTM and VCRM provide traceability mechanisms that exceed CMMI's guidance.

**Hardware engineering.** ASPICE 4.0's HWE.1–4 processes provide structured hardware engineering guidance with no CMMI equivalent. CMMI's Technical Solution practice area is generic across all engineering disciplines and does not address hardware-specific concerns such as schematic design, PCB layout, manufacturing data generation, or electrical verification.

**Machine learning engineering.** ASPICE 4.0's MLE.1–4 processes and SUP.11 provide automotive-specific ML engineering guidance. CMMI V3.0 has an AI working group developing future content but currently offers no ML-specific practice areas.

**Documentation content architecture.** ISO 15289's seven generic information item types and detailed content specifications provide a documentation framework that neither CMMI nor ASPICE match. CMMI expects work products but does not define their content structure. ASPICE's information item characteristics are more detailed than CMMI's work product expectations but less structured than 15289.

**Requirements engineering depth.** IEEE 29148 provides substantially more detailed requirements quality attributes, artifact hierarchies, and traceability structures than CMMI's RDM practice area. Organizations using 29148 will exceed CMMI expectations for requirements processes.

**Process assessment framework rigor.** ASPICE's PAM, built on ISO/IEC 33000, provides a calibrated, industry-specific assessment model with defined base practices, information items, and information item characteristics for every process. CMMI's SCAMPI methodology is rigorous but assesses against more generic practice descriptions.

### Dual Compliance Considerations

Organizations operating in the automotive supply chain that also maintain CMMI certification face a dual compliance challenge. The two frameworks are complementary but not interchangeable — CMMI compliance does not guarantee ASPICE compliance, and vice versa. The practical approach is to use one framework as the primary process architecture and map the other's requirements as a verification overlay.

For the HW+SW product MVP proposed in this report, the recommended approach is to use the ISO 15288 + ASPICE architecture as the primary framework (since ASPICE assessment is typically a contractual requirement in the automotive supply chain) and treat CMMI as an optional organizational maturity overlay. The ISO/ASPICE architecture already satisfies the majority of CMMI's Doing and Managing practice areas. The primary CMMI-unique value adds for consideration are: Governance (GOV) for organizational-level oversight, Organizational Training (OT) for systematic competency development, Decision Analysis & Resolution (DAR) for formal alternative evaluation at key decision points, and the Data Management/Data Quality practice areas if general data governance is needed beyond ML scope.

An organization at ASPICE Capability Level 2 across the 21-process HW+SW scope will approximately correspond to CMMI Maturity Level 2 (Managed) for the Development domain, with some Level 3 practices partially satisfied. Achieving CMMI Level 3 (Defined) requires organizational standard processes and process tailoring — concepts that align with ASPICE Capability Level 3's Established Process requirements and ISO 15288's Life Cycle Model Management process.

### CMMI V3.0 References

- **ISACA / CMMI Institute — CMMI Content Release:** <https://cmmiinstitute.com/products/cmmi/content-release>
- **ISACA — CMMI Updates Take Performance Improvements to the Next Level (2023):** <https://www.isaca.org/resources/news-and-trends/isaca-now-blog/2023/cmmi-updates-take-performance-improvements-to-the-next-level>
- **ISACA / CMMI Institute — CMMI Levels of Capability and Performance:** <https://cmmiinstitute.com/learning/appraisals/levels>
- **Process Group — Changes in CMMI V3:** <https://processgroup.com/changes-in-cmmi-v3/>
- **Core Business Solutions — CMMI V3 Update Explained:** <https://www.thecoresolution.com/cmmi-v3-update-explained>
- **Theoris — CMMI V3.0 Guide to Excellence in Organizational Processes:** <https://www.theoris.com/cmmi-v3-0-a-guide-to-excellence-in-organizational-processes/>
