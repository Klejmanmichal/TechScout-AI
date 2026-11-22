# TechScout AI — MVP Scope

| Field | Value |
|---|---|
| Document | MVP Scope |
| Project phase | Phase 1 — Product Definition |
| Status | Living document — MVP capability scope **APPROVED**; detailed items labeled individually |
| Related documents | [PRODUCT_DEFINITION.md](PRODUCT_DEFINITION.md), [CORE_USER_JOURNEY.md](CORE_USER_JOURNEY.md), [USE_CASES.md](USE_CASES.md) |

> **Status labels used in this document** (consistent with the related documents)
>
> - **APPROVED** — Confirmed product decision. Unless labeled otherwise, all capability content in [Section 5](#5-approved-mvp-capabilities) and all requirements in [Section 6](#6-cross-cutting-requirements--approved) are APPROVED.
> - **PROPOSED** — Suggested for consideration; **not** approved.
> - **DEFERRED** — Part of the capability's long-term direction, but planned for future product development, not the initial MVP.
> - **OUT OF SCOPE** — Explicitly excluded from the initial MVP.
> - **OPEN ITEM** — Unresolved decision, deliberately left undecided.
> - **DRAFT** — Working concept under development; content may still change.
> - **FUTURE** — Possible later capability, explicitly outside the current scope.
> - **DECIDED / ACCEPTED** — Used only when citing the status a decision carries in its source document (e.g., D8 in CORE_USER_JOURNEY.md, the use case set in USE_CASES.md).
>
> **Within each capability, approved content is classified as:**
>
> - **Essential for MVP** — Behavior the MVP must deliver for the capability to fulfill its purpose.
> - **Simplified implementation** — The approved, reduced form in which the capability is delivered in the MVP.
> - **Deferred** — Extensions of the capability planned for future development.
>
> This document defines **what** the MVP must do. It is a reference for Phase 2 (Architecture & Technical Design) but is **not** a technical architecture specification.

---

## Table of Contents

1. [Purpose of This Document](#1-purpose-of-this-document)
2. [Product Context](#2-product-context)
3. [MVP Objective — APPROVED](#3-mvp-objective--approved)
4. [Scope Overview](#4-scope-overview)
5. [Approved MVP Capabilities](#5-approved-mvp-capabilities)
   - [C1 — Research Request Understanding](#c1--research-request-understanding)
   - [C2 — Multi-Source Research & Discovery](#c2--multi-source-research--discovery)
   - [C3 — Deep Research & Investigation](#c3--deep-research--investigation)
   - [C4 — Technology & Solution Discovery](#c4--technology--solution-discovery)
   - [C5 — Technical Analysis & Comparison](#c5--technical-analysis--comparison)
   - [C6 — Technology Assessment & Evaluation](#c6--technology-assessment--evaluation)
   - [C7 — Evidence Synthesis & Report Generation](#c7--evidence-synthesis--report-generation)
   - [C8 — Interactive Research & Follow-up](#c8--interactive-research--follow-up)
6. [Cross-Cutting Requirements — APPROVED](#6-cross-cutting-requirements--approved)
7. [MVP Exclusions — OUT OF SCOPE](#7-mvp-exclusions--out-of-scope)
8. [MVP Success Criteria — PROPOSED](#8-mvp-success-criteria--proposed)
9. [Open Items](#9-open-items)
10. [Alignment with Existing Documents](#10-alignment-with-existing-documents)
11. [Key Terms](#11-key-terms)

---

## 1. Purpose of This Document

This document formalizes the **approved MVP scope** of TechScout AI and is the **authoritative reference for MVP scope** (recorded as D11). It fulfills the product definition activity "Refine and approve the MVP scope", now listed as completed in [PRODUCT_DEFINITION.md, Section 18](PRODUCT_DEFINITION.md#18-next-steps). [PRODUCT_DEFINITION.md, Section 14](PRODUCT_DEFINITION.md#14-mvp-scope--approved) summarizes the approved scope and references this document.

It is intended as the reference for:

- functional and non-functional requirements,
- success metrics and evaluation,
- architecture and technical design (Phase 2),
- backlog definition and iteration planning (Phase 3).

### What This Document Decides

- **APPROVED:** The eight MVP capabilities (C1–C8), their Essential / Simplified / Deferred classification, the cross-cutting requirements, and the MVP exclusions.
- **Not decided here:** Items listed in [Section 9 — Open Items](#9-open-items), and any content explicitly labeled PROPOSED.

---

## 2. Product Context

TechScout AI is an **AI-powered technology and innovation scouting platform** for technical professionals and qualified specialists (D6). It conducts **deep, on-demand research** (D4) into technologies, innovations, scientific developments, digital products, software, AI, engineering, materials, industrial technologies, biotech, deep tech, and other domains.

The product is **domain-agnostic** (D1–D3). Its purpose is to amplify technical expertise, accelerate technology discovery, reduce research effort, and support better-informed technical and innovation decisions.

TechScout AI is **not a generic chatbot** and must **not** be positioned as a replacement for technical experts (D7).

> **Guiding principle:** *"TechScout AI should not replace technical expertise. It should amplify it."*

The MVP builds on the following confirmed foundations:

| Foundation | Source |
|---|---|
| D1–D12 product decisions | [PRODUCT_DEFINITION.md, Section 17](PRODUCT_DEFINITION.md#17-current-status) |
| Hybrid AI interaction model (R1–R7, including the R4 approval gate for complex research) — DECIDED (D8) | [CORE_USER_JOURNEY.md, Section 3](CORE_USER_JOURNEY.md#3-hybrid-interaction-principles--decided) |
| 7-stage core user journey — agreed working model | [CORE_USER_JOURNEY.md, Section 2](CORE_USER_JOURNEY.md#2-journey-overview) |
| 7 core use cases (UC01–UC07) — ACCEPTED | [USE_CASES.md](USE_CASES.md) |
| Cross-cutting requirements CC1–CC10 | [USE_CASES.md, Section 6](USE_CASES.md#6-cross-cutting-requirements) |

---

## 3. MVP Objective — APPROVED

The MVP enables a user to **submit a natural-language research request** and receive **deep, structured, evidence-supported research**.

To do so, the system:

1. understands the research request,
2. discovers relevant information,
3. investigates promising directions,
4. analyzes technologies and solutions,
5. compares alternatives when appropriate,
6. assesses potential and limitations, and
7. generates a structured research report with traceable sources,

— and then supports context-aware follow-up research.

The MVP is **domain-agnostic** and adapts its research methods, criteria, sources, and depth to the subject.

---

## 4. Scope Overview

### 4.1 Capability Summary

All eight capabilities are **APPROVED** as part of the MVP scope. No capability is removed; the MVP reduces *depth of implementation*, not *breadth of capability*.

| ID | Capability | Core question it answers | MVP simplification in brief |
|---|---|---|---|
| C1 | Research Request Understanding | What does the user actually need? | Single natural-language input; AI decides to proceed, clarify, or propose a plan |
| C2 | Multi-Source Research & Discovery | Where is the relevant information? | General web research with shared, adaptive research logic |
| C3 | Deep Research & Investigation | What does the evidence actually say? | Iterative research loop instead of multi-agent architecture |
| C4 | Technology & Solution Discovery | What technologies or solutions are relevant, including non-obvious ones? | Four discovery levels with evidence-backed rationale |
| C5 | Technical Analysis & Comparison | How do they work and how do they compare? | Dynamic criteria and standard comparison tables |
| C6 | Technology Assessment & Evaluation | What is their potential, maturity, and risk? | Primarily qualitative, evidence-backed assessment; no universal scoring |
| C7 | Evidence Synthesis & Report Generation | What is the structured, traceable result? | One adaptive report format with three reading layers |
| C8 | Interactive Research & Follow-up | How does the expert direct further research? | Conversational follow-up within the session context |

> **Analytical layers — APPROVED:** Technical Analysis, Comparative Analysis, and Technology Assessment are **distinct analytical layers**, even when combined within a single capability (C5 covers technical and comparative analysis; C6 covers technology assessment) or a single research workflow stage. They are reflected in separate report sections (Detailed Technology Analysis, Comparative Analysis, Assessment & Opportunities).

### 4.2 Relationship to the Core User Journey

Capabilities are **product capabilities**, not pipeline steps or software modules. The mapping below shows where each capability primarily contributes; it is a traceability aid, not an architectural decision.

| Journey stage ([CORE_USER_JOURNEY.md](CORE_USER_JOURNEY.md)) | Primary capabilities |
|---|---|
| 1 — Research Request | C1 |
| 2 — Request Interpretation & Research Planning | C1 |
| 3 — Deep Research & Discovery | C2, C3, C4 |
| 4 — Technical Analysis | C3, C5 |
| 5 — Synthesis & Evaluation | C5, C6, C7 |
| 6 — Research Report Generation | C7 |
| 7 — Expert Review & Follow-up | C8 (re-uses C1–C7) |

### 4.3 Relationship to Core Use Cases

All seven ACCEPTED use cases are supported by the MVP capability set. Use cases differ in emphasis, not in the capabilities they require.

| Use case ([USE_CASES.md](USE_CASES.md)) | Emphasized capabilities | MVP-specific constraint |
|---|---|---|
| UC01 — Technology Discovery | C2, C4, C7 | — |
| UC02 — Deep Technical Investigation | C3, C5, C6 | — |
| UC03 — Technology Comparison & Benchmarking | C4 (Mode B), C5 | — |
| UC04 — Technology Substitution | C1 (requirements), C4, C5, C6 | — |
| UC05 — Patent & Research Landscape | C2, C3, C4 | Paid patent/scientific databases DEFERRED; coverage limitations must be disclosed |
| UC06 — Technology Opportunity Scouting | C4 (Exploratory, Cross-domain), C6 | Hypotheses must be distinguished from documented findings |
| UC07 — Technical Feasibility Assessment | C1 (requirements), C5, C6 | Assessment is initial and qualitative; not proof of feasibility |

> **Note:** MVP prioritization *among* use cases (USE_CASES.md, Section 7) is not decided by this document. Because all capabilities are in scope, all use cases are supported; whether any receives priority in testing or iteration planning remains an **OPEN ITEM** (see [Section 9](#9-open-items)).

---

## 5. Approved MVP Capabilities

Each capability is described with:

- **Purpose** — what the capability achieves for the user.
- **Essential for MVP** — required behavior.
- **Simplified implementation** — the approved reduced form for the MVP.
- **Deferred** — future development.
- **Notes** — links to related decisions, use cases, and open items.

---

### C1 — Research Request Understanding

**Purpose:** Correctly understand what the user needs — objective, research type, criteria, and constraints — and decide how to proceed, applying the hybrid interaction model (R1–R4).

#### Essential for MVP

- Natural-language request interpretation
- Research intent and goal identification
- Research type identification
- Criteria and constraints extraction
- Missing information detection
- Autonomous assumptions with disclosure
- Targeted clarification when material
- Automatic domain recognition

#### Simplified Implementation

- Single natural-language input (no mandatory structured form)
- The AI decides whether to **proceed autonomously**, **ask for clarification**, or **propose a research plan**
- For complex requests, a research plan is presented for user review and approval; the main research execution begins **after approval** and then proceeds autonomously (approval gate for complex research only)

#### Deferred

- Long-term user preference learning
- Advanced personalization

#### Notes

- Implements hybrid interaction rules R1–R4 ([CORE_USER_JOURNEY.md, Section 3](CORE_USER_JOURNEY.md#3-hybrid-interaction-principles--decided)): clear request → proceed; minor gaps → assume and disclose; important ambiguities → 1–3 targeted questions; very broad or complex → research plan with an approval gate (see Simplified Implementation above); after approval, expansion follows R5 and R6.
- For UC04 and UC07, the requirements of the existing technology or target application are a typical source of important ambiguity (R3).
- Optional structured input fields remain **PROPOSED** (CORE_USER_JOURNEY.md, Stage 1).
- Thresholds for "broad or complex" requests and research plan presentation details are **OPEN ITEMS** (see [Section 9](#9-open-items)).

---

### C2 — Multi-Source Research & Discovery

**Purpose:** Find relevant, credible, and traceable information across diverse accessible sources.

#### Essential for MVP

- Web search
- Multi-source research
- Source type identification
- Source credibility assessment
- Source traceability
- Query expansion
- Iterative searching
- Cross-verification
- Source diversity
- Freshness assessment
- Gap identification
- Primary-source preference where available

#### Simplified Implementation

- General web research capabilities initially
- Shared research logic across different domains
- Adaptive source selection
- Internal representation of sources and findings

#### Deferred

- Paid specialized patent and scientific database integrations
- Private corporate database integrations
- Large-scale proprietary crawling and indexing infrastructure

#### Notes

- Source access limitations must be disclosed, not hidden (CC6). This is especially relevant to UC05, where results depend on accessible sources.
- "Primary-source preference" means preferring original sources (e.g., the publication, patent record, official documentation, repository, or model card) over secondary reporting where these are accessible.
- The specific source access strategy and constraints are an **OPEN ITEM** (see [Section 9](#9-open-items)).

---

### C3 — Deep Research & Investigation

**Purpose:** Go beyond surface-level retrieval to critically analyze content, extract technical substance, and build an evidence-based understanding of the subject.

#### Essential for MVP

- Deep content analysis
- Technical information extraction
- Contextual understanding
- Evidence-based synthesis
- Key finding identification
- Technical mechanism explanation
- Limitations identification
- Contradiction detection
- Knowledge gap identification
- Cross-source linking
- Critical evaluation
- Adaptive research depth

#### Simplified Implementation

- **Iterative research loop** instead of a complex multi-agent architecture
- AI-driven research expansion
- Internal structures for **sources, findings, evidence, and gaps**
- Adaptive stopping criteria

#### Deferred

- Formal knowledge graph
- Persistent cross-research knowledge network
- Complex multi-agent swarm
- Advanced scientific reasoning infrastructure

#### Notes

- Supports the discovery loop and evidence gap loop described in [CORE_USER_JOURNEY.md, Section 11](CORE_USER_JOURNEY.md#11-iterative-research--feedback-loops).
- Research expansion follows R5 (within scope: expand autonomously and disclose) and R6 (outside scope: propose to the user).
- **Stopping principle — APPROVED:** Research is iterative and autonomous; the agent stops when further research is no longer sufficiently valuable or when adequate coverage has been achieved. "Adaptive stopping criteria" is approved as the **approach**; the precise criteria and research depth thresholds remain **OPEN ITEMS** (see [Section 9](#9-open-items)).
- The internal structures for sources, findings, evidence, and gaps are approved as a concept; their design belongs to Phase 2.

---

### C4 — Technology & Solution Discovery

**Purpose:** Identify relevant technologies and solutions — including emerging, alternative, and non-obvious candidates — and explain why each is relevant.

#### Essential for MVP

- Candidate identification
- Emerging technology discovery
- Alternative solution discovery
- Beyond-obvious discovery
- Cross-domain discovery
- Candidate relevance assessment
- Discovery rationale
- Evidence-backed candidates
- Discovery prioritization
- Discovery expansion

#### Simplified Implementation

- **Four discovery levels:** Direct, Adjacent, Exploratory, Cross-domain
- Candidate generation and prioritization
- Evidence-backed rationale for each candidate
- Explicit differentiation between **existing technologies**, **emerging technologies**, and **AI-generated hypotheses**

#### Deferred

- Continuous technology radar
- Persistent trend monitoring
- Automated novelty detection at scale
- Persistent technology database

#### Notes

- The four discovery level **names** are APPROVED. Working descriptions are **PROPOSED**:

  | Level | Working description — PROPOSED |
  |---|---|
  | Direct | Technologies or solutions that directly address the stated request within its domain. |
  | Adjacent | Closely related variants, neighboring approaches, or technologies in a related sub-field. |
  | Exploratory | Less established, emerging, or unconventional candidates with plausible relevance. |
  | Cross-domain | Technologies or principles from other domains or industries that could transfer to the user's problem. |

- Supports UC01, UC03 (Mode B), UC04, and UC06. Relevance takes priority over volume (UC01).
- Exploratory and cross-domain candidates beyond the user's scope are subject to R6 (proposed, not pursued unilaterally).
- Novelty descriptors (e.g., "breakthrough", "disruptive") are AI interpretations and must be justified with evidence (UC01).

---

### C5 — Technical Analysis & Comparison

**Purpose:** Analyze how technologies work and how they perform, and compare alternatives fairly using criteria relevant to the user's context.

#### Essential for MVP

- Technical parameter extraction
- Characteristics analysis
- Mechanism analysis
- Context-aware comparison criteria
- Structured comparison
- Trade-off analysis
- Performance analysis
- Conditions-aware analysis
- Strengths and weaknesses
- Technical differentiation
- Data gap identification
- Fair comparison validation
- Cross-source parameter verification
- Comparative conclusions

#### Simplified Implementation

- Dynamic criteria selection, adapted to the subject and the user's objective
- Standard comparison tables
- Missing data explicitly identified
- Distinction between **measured, reported, estimated, and calculated** values
- Testing conditions considered
- The AI may propose additional comparison criteria

#### Deferred

- Advanced automatic data normalization
- Large-scale automated benchmarking
- Predictive performance modelling

#### Notes

- Comparisons are included **where relevant** to the request, not in every report (CORE_USER_JOURNEY.md, Stage 6).
- Implements CC8 (no misleading comparisons): options must not appear superior merely because more or more favorable information is available about them; values obtained under different conditions must be flagged as not directly comparable.
- Missing data for one option is a gap, not a disadvantage (UC03).
- Cost is compared only where reliable information is available, with source and limitations disclosed (UC03).
- UC03 Mode B behavior (compare immediately vs. propose first) remains an **OPEN ITEM** from USE_CASES.md beyond the general R5/R6 rules.

---

### C6 — Technology Assessment & Evaluation

**Purpose:** Provide an evidence-backed, context-dependent assessment of potential, maturity, feasibility, opportunities, and risks — as an AI assessment that supports, not replaces, expert judgment.

#### Essential for MVP

- Potential assessment
- Maturity assessment
- Feasibility assessment
- Application suitability
- Impact assessment
- Advantages and limitations
- Opportunity assessment
- Risk identification
- Development trajectory assessment
- Context-dependent evaluation
- Evidence-backed assessment
- Confidence and uncertainty disclosure

#### Simplified Implementation

- Primarily **qualitative** assessment
- Context-dependent maturity assessment
- **TRL used when relevant and evidence-supported**
- **No arbitrary universal scoring**
- Assessment rationale and supporting evidence
- Recommended next steps

#### Deferred

- Formal weighted technology scoring model
- Advanced predictive forecasting
- Portfolio-level assessment and optimization

#### Notes

- Follows the assessment principles in [PRODUCT_DEFINITION.md, Section 12](PRODUCT_DEFINITION.md#12-technology-assessment--approved-potential-score-draft): justified with evidence, presented as AI assessment rather than objective fact, uncertainties disclosed, missing data not treated as negative evidence.
- The approval of "no arbitrary universal scoring" and the deferral of a formal weighted scoring model mean the draft **Technology Potential Score** is **not** part of the MVP in its scored form. Whether and how potential is expressed beyond qualitative assessment remains an **OPEN ITEM**.
- TRL use "when relevant and evidence-supported" is approved; the broader maturity framework (e.g., how maturity is expressed where TRL does not fit, such as software or AI models) remains an **OPEN ITEM**.
- Feasibility assessments (UC07) are initial and must not be presented as proof of feasibility.

---

### C7 — Evidence Synthesis & Report Generation

**Purpose:** Deliver the research outcome as a structured, adaptive, evidence-linked **Technology Scouting Report** — the core product output (D5).

#### Essential for MVP

- Evidence-based synthesis
- Key finding identification
- Evidence-linked conclusions
- Structured adaptive report
- Executive summary
- Technical detail preservation
- Source traceability
- Separation of facts and AI interpretation
- Uncertainty and limitations
- Contradiction reporting
- Readability and organization
- Technology Profiles
- Conclusions and recommendations
- Report refinement

#### Simplified Implementation

- **One adaptive report format**
- **Three integrated reading layers:** Executive, Technical, Evidence
- Standard Technology Profile
- Report rendered in the application
- Initially limited export format(s)
- User can request refinement or regeneration

#### Deferred

- Advanced report editor
- Multiple domain-specific templates
- PowerPoint generation
- Advanced report library and management

#### Adaptive Report Structure — APPROVED

> **Status: APPROVED** — The 9-section adaptive report structure was reviewed and accepted during product definition. It replaces the earlier proposed structure and is recorded as D12; [PRODUCT_DEFINITION.md, Section 10](PRODUCT_DEFINITION.md#10-standard-research-report--approved) reflects this structure and references this section. It is **adaptive**: not every section is mandatory for every research request.

| # | Section | Typical content |
|---|---|---|
| 1 | Executive Summary | Key findings, conclusions, and recommendations for fast orientation |
| 2 | Research Scope & Approach | Interpreted objective, scope, assumptions, research directions, source types covered, coverage limitations, autonomous expansions |
| 3 | Technology Landscape & Discovery | Identified candidates by discovery level, with relevance rationale |
| 4 | Detailed Technology Analysis | Technology Profiles; mechanisms, parameters, performance, conditions |
| 5 | Comparative Analysis | Structured comparison, trade-offs, data gaps — where relevant |
| 6 | Assessment & Opportunities | Potential, maturity, feasibility, applications, opportunities |
| 7 | Limitations, Risks & Knowledge Gaps | Technical limitations, risks, contradictions, uncertainties, evidence gaps |
| 8 | Conclusions & Recommendations | Evidence-linked conclusions; recommended next steps |
| 9 | Sources & Supporting Evidence | Traceable sources with source type indication |

The "Typical content" column is **PROPOSED** guidance only.

#### Notes

- The three reading layers are APPROVED as a concept; how they are presented (e.g., sections, expandable detail, linked evidence) is a design question for Phase 2.
- The Standard Technology Profile is APPROVED as an MVP element; its **fields** remain **PROPOSED** (see [PRODUCT_DEFINITION.md, Section 11](PRODUCT_DEFINITION.md#11-technology-profile--approved-fields-proposed)).
- How facts, interpretations, assumptions, and uncertainty are visually or structurally marked remains an **OPEN ITEM** (CORE_USER_JOURNEY.md, Section 12).
- The specific export format(s) and report length options remain an **OPEN ITEM** (see [Section 9](#9-open-items)).

---

### C8 — Interactive Research & Follow-up

**Purpose:** Enable the expert user to direct further research, challenge findings, and refine results, with the research context preserved (R7).

#### Essential for MVP

- Context-aware follow-up
- Research continuation
- Deep dives
- Additional research
- Research direction refinement
- Feedback integration
- Criteria modification
- Hypothesis investigation
- Report refinement
- Session context retention

#### Simplified Implementation

- Conversational interface
- Follow-up uses the existing research context
- Reuse of existing sources and findings
- Additional research only when necessary
- **Exploratory follow-up does not automatically modify the main report**
- **The report is updated when the user requests it**
- Transparent explanation of what changed

#### Deferred

- Persistent cross-session research memory
- Permanent knowledge graph
- Automatic linking of all historical research
- Long-term user research intelligence

#### Notes

- The conversational interface serves research follow-up within the product's purpose; it does not make TechScout AI a general-purpose chatbot (D7).
- Context retention is approved at **session** level. Saving and reopening research across sessions remains **FUTURE** (CORE_USER_JOURNEY.md, Stage 7).
- Exploratory follow-ups produce conversational results, and the main report changes only on request (also reflected in CORE_USER_JOURNEY.md, Stage 7). The exact form of a requested update (revised version vs. supplement) remains an **OPEN ITEM**.
- Handling of user corrections that conflict with strong evidence, and detection of context drift, remain **PROPOSED** (CORE_USER_JOURNEY.md, Stage 7).

---

## 6. Cross-Cutting Requirements — APPROVED

These requirements are **mandatory across all MVP capabilities**. They extend and are consistent with CC1–CC10 in [USE_CASES.md, Section 6](USE_CASES.md#6-cross-cutting-requirements).

### 6.1 Research Reliability & Evidence Integrity

TechScout AI must prioritize **factual reliability and evidence quality over completeness or fluency**.

| # | Requirement | Related |
|---|---|---|
| RI1 | No fabricated technologies, patents, publications, parameters, results, names, or sources. | CC1 |
| RI2 | No invented or unverified links. | CC2 |
| RI3 | Key technical claims are traceable to actual sources. | CC2 |
| RI4 | Facts, AI interpretations, hypotheses, and assumptions are clearly differentiated. | CC3, CC4 |
| RI5 | Uncertainty is explicitly communicated. | CC5 |
| RI6 | Contradictions are identified and investigated. | CC5 |
| RI7 | Weak evidence must not support strong conclusions. | CC5 |
| RI8 | Missing data must not be interpreted as negative evidence. | CC7 |
| RI9 | Source credibility is distinct from evidence strength. | CORE_USER_JOURNEY.md §12 |
| RI10 | Limitations and access restrictions are disclosed. | CC6 |
| RI11 | Marketing claims and unconfirmed statements are appropriately identified. | CORE_USER_JOURNEY.md §12 |

> **Terminology:** As in [CORE_USER_JOURNEY.md, Section 12](CORE_USER_JOURNEY.md#12-facts-interpretation-assumptions--uncertainty), "facts" refers to **sourced claims** and **verified evidence**. A statement in a source is not automatically proven: a credible source can contain a weakly supported claim (RI9), and a vendor claim establishes only that the vendor makes it (RI11).

> **Requirement IDs (RI1–RI11)** are introduced in this document for referencing; they do not change the content of the approved requirements.

### 6.2 Domain Neutrality by Design

The MVP must **not** be limited to materials science or sustainability (D1, D2). It must support, among others:

| Domain group | Examples |
|---|---|
| Physical sciences & materials | Materials science; chemistry and polymers |
| Engineering & industry | Engineering; industrial technologies |
| Digital & AI | AI and LLMs; software and digital products; agent frameworks |
| Life sciences | Biotech |
| Research & frontier technology | Scientific research; deep tech; emerging technologies |

Research methods, criteria, sources, and depth **adapt to the domain**. The domain grouping above is for readability only and is not a product taxonomy.

### 6.3 Adaptive Intelligence

The system must adapt its research approach to the subject. Illustrative examples — **not exhaustive lists or rigid workflows**:

| Subject | Typical research focus |
|---|---|
| LLMs | Model cards, benchmarks, repositories, capabilities, limitations, licensing |
| Materials | Properties, processing, testing, applications, maturity |
| Biotech | Mechanisms, experimental evidence, limitations, applications |
| Software | Architecture, features, repository activity, ecosystem, performance, licensing |

Adaptation applies across capabilities: domain recognition (C1), source selection (C2), research depth (C3), discovery (C4), comparison criteria (C5), and maturity assessment (C6).

### 6.4 User Experience Principles

- Natural-language interface
- Minimal unnecessary questions
- AI takes initiative
- User retains control over material decisions
- Complex research should not require a complex UI
- Context-aware follow-up
- Structured, readable outputs

These principles are consistent with the hybrid interaction model (R1–R7) and the core principle: *"AI should ask only questions that materially improve the research outcome. Otherwise, it should make reasonable assumptions, disclose them, and proceed."*

---

## 7. MVP Exclusions — OUT OF SCOPE

The following are **explicitly out of scope** for the initial MVP:

| # | Exclusion | Related source |
|---|---|---|
| X1 | Continuous technology monitoring | D4; PRODUCT_DEFINITION.md §8 (long-term vision only) |
| X2 | 24/7 autonomous monitoring agents | D4 |
| X3 | Enterprise platform functionality | — |
| X4 | Massive proprietary technology database | PRODUCT_DEFINITION.md §14 |
| X5 | Complex knowledge graph | C3, C8 deferred items |
| X6 | Multi-agent swarm architecture | PRODUCT_DEFINITION.md §14; C3 |
| X7 | Predictive technology forecasting | C6 deferred items |
| X8 | Automated technology radar | C4 deferred items |
| X9 | Advanced portfolio management | C6 deferred items |
| X10 | Complex team collaboration | — |
| X11 | KPI-heavy dashboards | PRODUCT_DEFINITION.md §14 |
| X12 | Training proprietary AI models | PRODUCT_DEFINITION.md §14 |
| X13 | Full integration with paid patent and scientific databases | C2 deferred items |
| X14 | Advanced report editing capabilities | C7 deferred items |

> **Deferred vs. out of scope:** *Deferred* items are future extensions of an approved MVP capability. *Exclusions* are product directions not pursued in the initial MVP at all. Several exclusions correspond to deferred items; listing them here makes the boundary explicit for architecture and backlog work. Neither category is a commitment to future delivery.

---

## 8. MVP Success Criteria — PROPOSED

> **Status: PROPOSED** — These criteria are **not approved product decisions**. They are proposed for review and are intended to be **testable**. No numerical targets or percentages are defined; targets, if any, depend on the MVP evaluation methodology, which remains an **OPEN ITEM**.

Each criterion is phrased as an observable property of the MVP's outputs or behavior and includes a proposed way to verify it.

| # | Area | Proposed criterion | Proposed verification approach |
|---|---|---|---|
| SC1 | Research quality | Reports address the user's actual objective, with key findings that a domain expert judges relevant and technically correct. | Expert review of reports produced for a set of representative requests across use cases and domains. |
| SC2 | Source traceability | Key technical claims link to real, accessible sources that support the stated claim. | Spot-check sampled claims against their cited sources: source exists, link resolves, and source content supports the claim. |
| SC3 | Reliability & hallucination handling | No fabricated technologies, publications, patents, parameters, names, or links are found in evaluated reports. | Verification of all named entities and cited sources in a sample of reports; any fabrication is treated as a critical failure. |
| SC4 | Evidence integrity | Facts, AI interpretations, hypotheses, and assumptions are distinguishable; uncertainty, contradictions, and marketing claims are identified. | Review against RI1–RI11; check whether an expert can tell, for each significant statement, what kind of statement it is. |
| SC5 | Technical depth | Analysis explains mechanisms, parameters, conditions, and limitations at a depth appropriate for specialists (CC9). | Expert review: is the depth comparable to or beyond what the expert would gather in an initial manual review? |
| SC6 | Discovery relevance | Discovered candidates are relevant to the objective, include non-obvious options where they exist, and carry an evidence-backed rationale; hypotheses are labeled as such. | Expert review of candidate lists, including whether relevant candidates known to the expert were missed. |
| SC7 | Comparison quality | Comparisons use context-appropriate criteria, account for testing conditions, distinguish value types, and identify data gaps without treating them as disadvantages. | Review of comparison outputs against CC8 and C5 requirements, including deliberately uneven-evidence test cases. |
| SC8 | Assessment quality | Assessments of maturity, feasibility, and potential are justified with evidence, context-dependent, and accompanied by confidence and uncertainty disclosure. | Review of assessment rationale; check that conclusion strength matches evidence strength (RI7). |
| SC9 | Low-evidence handling | When evidence is weak or absent, the system says so transparently rather than producing unsupported conclusions. | Test requests on very new, niche, or sparsely documented topics. |
| SC10 | Adaptive research behavior | Research approach (sources, criteria, depth) visibly adapts to the domain and request type. | Run comparable requests across different domains (e.g., materials, LLMs, biotech, software) and compare research approaches. |
| SC11 | Interaction behavior | The system proceeds autonomously on clear requests, discloses assumptions, and asks only targeted questions when ambiguity is material (R1–R4). | Test set of clear, minor-gap, ambiguous, and broad requests; review whether behavior matches the hybrid rules. |
| SC12 | Report usefulness | The report is readable, well organized, and usable at executive, technical, and evidence levels. | Expert review of report structure and readability for different reading purposes. |
| SC13 | Follow-up continuity | Follow-ups use the existing research context without the user repeating information; report changes occur only on request and are explained. | Multi-turn test scenarios covering deep dives, corrections, criteria changes, and report update requests. |
| SC14 | User effort reduction | Users judge that the MVP meaningfully reduces the effort of initial technology research compared with their usual approach. | Qualitative user feedback from target-user testing; optional comparison with a manual research baseline. |
| SC15 | Domain neutrality | The MVP produces useful research across multiple domains, not only materials or sustainability. | Include requests from each domain group in [Section 6.2](#62-domain-neutrality-by-design) in the evaluation set. |

> **Note:** SC3 (no fabrication) is proposed as a **gating criterion**: a report that fails it should be considered failed regardless of other strengths, consistent with the priority of reliability over completeness or fluency (Section 6.1). This gating rule is itself PROPOSED.

---

## 9. Open Items

The following decisions are **unresolved**. This document does **not** finalize them.

### 9.1 Open Items Explicitly Carried into This Document

| # | Item | Context | Status |
|---|---|---|---|
| OI1 | **Research depth thresholds** | How deep research should go per request or use case, and how sufficient depth is determined. Adaptive depth is approved; thresholds are not. | OPEN ITEM |
| OI2 | **Research stopping criteria** | The stopping principle (stop when further research is no longer sufficiently valuable or adequate coverage is achieved) and adaptive stopping criteria as the approach are approved (C3); the precise criteria are not defined. No thresholds are assumed. | OPEN ITEM |
| OI3 | **Evidence scoring / calibration** | How evidence strength and source credibility are rated, combined, and calibrated; criteria for treating a sourced claim as verified evidence. | OPEN ITEM |
| OI4 | **Technology maturity framework** | TRL is used when relevant and evidence-supported (approved); how maturity is expressed where TRL does not apply (e.g., software, AI models) is not defined. | OPEN ITEM |
| OI5 | **Technology Potential scoring** | Universal arbitrary scoring is excluded and a formal weighted model is deferred; whether and how potential is expressed beyond qualitative assessment is not defined. | OPEN ITEM (Technology Potential Score remains DRAFT) |
| OI6 | **Research plan presentation details** | The approval gate for complex research is decided (D8, C1). Open: thresholds for when a request is complex enough to require a plan (R4), plan format, and behavior on plan rejection or modification. | OPEN ITEM |
| OI7 | **Report export formats and length options** | In-app presentation and "initially limited export format(s)" are approved; which formats, and any report length options, are not defined. | OPEN ITEM |
| OI8 | **Source access strategy and constraints** | Which sources and search mechanisms are used, access constraints, and handling of paywalled content. | OPEN ITEM (Phase 2) |
| OI9 | **Session context implementation details** | How session context (objective, assumptions, sources, findings, corrections) is retained and used. | OPEN ITEM (Phase 2) |
| OI10 | **MVP evaluation methodology** | How success criteria are evaluated, by whom, with which test requests, and whether targets are set. | OPEN ITEM |

### 9.2 Related Open Items from Existing Documents

These remain unresolved and are relevant to MVP implementation:

| Item | Source | Status |
|---|---|---|
| Thresholds for "broad or complex" requests (R4) and justified autonomous expansion (R5) | CORE_USER_JOURNEY.md §3 | OPEN ITEM |
| Behavior when clarification questions are unanswered; whether research pauses or continues on provisional assumptions | CORE_USER_JOURNEY.md §14 | OPEN ITEM |
| Whether research pauses or continues while an R6 proposal awaits a decision | CORE_USER_JOURNEY.md §11 | OPEN ITEM |
| Out-of-scope request handling and its boundary | CORE_USER_JOURNEY.md §5 | PROPOSED / OPEN ITEM |
| Low-evidence research path and its output form | CORE_USER_JOURNEY.md §11 | PROPOSED / OPEN ITEM |
| Marking of facts, interpretation, assumptions, and uncertainty in outputs | CORE_USER_JOURNEY.md §12 | OPEN ITEM |
| Form of a requested report update after follow-up (revised version vs. supplement) | CORE_USER_JOURNEY.md §10; C8 | OPEN ITEM |
| Handling of user corrections that conflict with strong evidence; context drift detection | CORE_USER_JOURNEY.md §10 | PROPOSED |
| Research effort limits per request (time, cost) | CORE_USER_JOURNEY.md §11 | OPEN ITEM |
| Progress visibility during research | CORE_USER_JOURNEY.md §6 | PROPOSED |
| Technology Profile fields | PRODUCT_DEFINITION.md §11 | PROPOSED |
| Use case prioritization within the MVP; identification of combined requests | USE_CASES.md §7 | OPEN ITEM |
| UC03 Mode B behavior (compare immediately vs. propose first) | USE_CASES.md §4 | OPEN ITEM |
| Working descriptions of the four discovery levels | This document, C4 | PROPOSED |

---

## 10. Alignment with Existing Documents

> **Status:** Recommendations A1–A8 were originally recorded when this document was created. Those fulfilled by the approved documentation alignment are marked **Completed**. Recommendations marked **Not applied** still require a decision and must not be treated as approved.

| # | Document | Recommended update | Status |
|---|---|---|---|
| A1 | PRODUCT_DEFINITION.md §14, §17 | Update "MVP scope" status from PROPOSED to APPROVED and reference this document. | Completed |
| A2 | PRODUCT_DEFINITION.md §17 | Record the approved MVP scope in the decision log, alongside the hybrid interaction (D8) and 7-stage journey (D9) entries recommended in CORE_USER_JOURNEY.md. | Completed — recorded as D8–D12 |
| A3 | PRODUCT_DEFINITION.md §6 | Align the Target Domains list with the Domain Neutrality requirement ([Section 6.2](#62-domain-neutrality-by-design)), including AI/LLMs, software and digital products, agent frameworks, and biotech. | Completed |
| A4 | PRODUCT_DEFINITION.md §12 | Reflect that a formal weighted scoring model is deferred and arbitrary universal scoring is excluded from the MVP. | Completed (Technology Potential Score remains DRAFT) |
| A5 | PRODUCT_DEFINITION.md §14 | "Multi-agent architecture from the beginning" (not planned) is formalized as X6 and the C3 iterative-loop simplification. | Completed — §14 references [Section 7](#7-mvp-exclusions--out-of-scope) |
| A6 | CORE_USER_JOURNEY.md §10, §14 | Note that the follow-up output form is partially resolved by C8 (exploratory follow-up does not modify the main report; updates on request). | Completed (update format remains OPEN) |
| A7 | CORE_USER_JOURNEY.md §7, USE_CASES.md UC07 | Note that TRL use "when relevant and evidence-supported" is approved, while the broader maturity framework remains open (OI4). | Completed |
| A8 | USE_CASES.md §2.1, §7 | Note that all seven use cases are supported by the approved MVP capability set; prioritization remains open. | Completed |
| A9 | PRODUCT_DEFINITION.md §10, §17; CORE_USER_JOURNEY.md §9, §14; USE_CASES.md §7 | Align all report structure references with the approved adaptive 9-section structure (C7), keeping detailed section content PROPOSED. | Completed |
| A10 | CORE_USER_JOURNEY.md §3, §5, §13; USE_CASES.md §2.3; this document C1 | Reflect the R4 approval gate for complex research consistently. | Completed |
| A11 | All product documents | Designate a single canonical open-items register (open items currently appear in CORE_USER_JOURNEY.md §14, USE_CASES.md §7, and [Section 9](#9-open-items)). | Not applied — requires decision |
| A12 | All product documents | Harmonize status vocabulary (DECIDED, ACCEPTED, and APPROVED are currently used for confirmed items in different documents). | Not applied — requires decision |
| A13 | This document §6.1 | Make "context and applicability" of evidence explicit in the reliability requirements. | Not applied — requires decision |

---

## 11. Key Terms

| Term | Meaning in this document |
|---|---|
| **Capability (C1–C8)** | An approved product capability of the MVP. Not a software module or pipeline step. |
| **Essential / Simplified / Deferred** | Classification of approved content within each capability (see the status labels at the top of this document). |
| **Discovery levels** | Direct, Adjacent, Exploratory, Cross-domain (C4). Names APPROVED; working descriptions PROPOSED. |
| **Reading layers** | Executive, Technical, Evidence — three integrated layers of the single adaptive report (C7). |
| **Value types** | Measured, reported, estimated, calculated — distinguished in technical parameters and comparisons (C5). |
| **Sourced claim / verified evidence** | As defined in [CORE_USER_JOURNEY.md, Section 12](CORE_USER_JOURNEY.md#12-facts-interpretation-assumptions--uncertainty). |
| **Session context** | The research context retained within a session: objective, scope, assumptions, sources, findings, corrections, and follow-ups (C8). |
| **Technology Scouting Report** | The core product output (D5), produced in one adaptive format in the MVP. |
| **Technology Profile** | Standard per-technology structure within the report; fields remain PROPOSED. |
