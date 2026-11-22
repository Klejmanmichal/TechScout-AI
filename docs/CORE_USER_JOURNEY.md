# TechScout AI — Core User Journey

| Field | Value |
|---|---|
| Document | Core User Journey |
| Project phase | Phase 1 — Product Definition |
| Status | Living document (in progress) |
| Related documents | [PRODUCT_DEFINITION.md](PRODUCT_DEFINITION.md), [USE_CASES.md](USE_CASES.md), [MVP_SCOPE.md](MVP_SCOPE.md) |

> **Status labels used in this document** (consistent with [PRODUCT_DEFINITION.md](PRODUCT_DEFINITION.md))
>
> - **APPROVED / DECIDED** — Decisions already made.
> - **DRAFT** — Working text under development; content may still change.
> - **PROPOSED** — Concepts suggested for consideration that have **not** been approved.
> - **DEFERRED** — Planned for future product development, not the initial MVP.
> - **FUTURE** — Possible later capabilities, explicitly outside the current scope.
> - **OPEN ITEM** — Unresolved design question, deliberately left undecided.
>
> **Decision status:**
>
> - The **hybrid AI interaction model** is a confirmed design decision (**DECIDED**).
> - The **7-stage journey structure** is an **agreed working model** for product definition.
> - Both are recorded in the [PRODUCT_DEFINITION.md](PRODUCT_DEFINITION.md#17-current-status) decision log (D8 and D9).
> - Detailed behaviors within each stage are **DRAFT** unless labeled otherwise.
>
> This document describes product behavior from the user's perspective; it is **not** a technical architecture specification.

---

## Table of Contents

1. [Purpose of This Document](#1-purpose-of-this-document)
2. [Journey Overview](#2-journey-overview)
3. [Hybrid Interaction Principles — DECIDED](#3-hybrid-interaction-principles--decided)
4. [Stage 1 — Research Request](#4-stage-1--research-request)
5. [Stage 2 — Request Interpretation & Research Planning](#5-stage-2--request-interpretation--research-planning)
6. [Stage 3 — Deep Research & Discovery](#6-stage-3--deep-research--discovery)
7. [Stage 4 — Technical Analysis](#7-stage-4--technical-analysis)
8. [Stage 5 — Synthesis & Evaluation](#8-stage-5--synthesis--evaluation)
9. [Stage 6 — Research Report Generation](#9-stage-6--research-report-generation)
10. [Stage 7 — Expert Review & Follow-up](#10-stage-7--expert-review--follow-up)
11. [Iterative Research & Feedback Loops](#11-iterative-research--feedback-loops)
12. [Facts, Interpretation, Assumptions & Uncertainty](#12-facts-interpretation-assumptions--uncertainty)
13. [End-to-End Workflow Summary](#13-end-to-end-workflow-summary)
14. [Open Items](#14-open-items)

---

## 1. Purpose of This Document

This document defines the **core user journey** of TechScout AI: the path from a user's initial research request to a structured, evidence-supported **Technology Scouting Report** and subsequent follow-up research.

It fulfills the product definition activity "Define the core user journey", now listed as completed in [PRODUCT_DEFINITION.md, Section 18](PRODUCT_DEFINITION.md#18-next-steps). It informed MVP scoping and use case definition, and remains a reference for functional requirements and technical design.

### Document Scope

> **Important:** This document describes the **intended target user journey** for TechScout AI. It does **not** itself define the MVP scope.
>
> - The MVP scope is **APPROVED** and defined in [MVP_SCOPE.md](MVP_SCOPE.md), the authoritative reference for which capabilities are included and at which implementation level (see also [PRODUCT_DEFINITION.md, Section 14](PRODUCT_DEFINITION.md#14-mvp-scope--approved)).
> - Some behaviors described here are **proposed or future capabilities** rather than MVP functionality; see MVP_SCOPE.md for Deferred items and exclusions.
> - Inclusion of a behavior in this journey does not by itself imply that it is part of the MVP.

### Related Decisions

It builds on the following confirmed decisions from the Product Definition:

- **D4** — The MVP researches **on demand**; it does not continuously monitor.
- **D5** — A **structured, evidence-based report** is the core product output.
- **D6** — Target users are **highly technical professionals and qualified specialists**.
- **D7** — TechScout AI **amplifies technical expertise**; it is not a general-purpose chatbot.

It also defines:

- **D8 — Hybrid AI interaction** (DECIDED) — The AI operates autonomously when possible while remaining consultative and transparent (see [Section 3](#3-hybrid-interaction-principles--decided)).
- **D9 — 7-stage core user journey** (agreed working model) — see [Section 2](#2-journey-overview).

---

## 2. Journey Overview

The core journey consists of **seven stages**. Stages 1–6 form the primary research cycle; Stage 7 closes the loop by returning the user's expert judgment into further research.

```
 ┌──────────────────────┐
 │ 1. Research Request  │  User describes problem, objective, or area of interest
 └──────────┬───────────┘
            ▼
 ┌──────────────────────────────────────────┐
 │ 2. Request Interpretation & Planning     │  Scope, directions, ambiguities;
 │    (hybrid interaction rules applied)    │  questions or plan only if needed
 └──────────┬───────────────────────────────┘
            ▼
 ┌──────────────────────────────────────────┐
 │ 3. Deep Research & Discovery             │◄──┐  Iterative searching
 └──────────┬───────────────────────────────┘   │  and scope expansion
            ▼                                    │
 ┌──────────────────────────────────────────┐   │
 │ 4. Technical Analysis                    │───┘  Gaps may trigger more research
 └──────────┬───────────────────────────────┘
            ▼
 ┌──────────────────────────────────────────┐
 │ 5. Synthesis & Evaluation                │  Compare, prioritize, identify gaps
 └──────────┬───────────────────────────────┘
            ▼
 ┌──────────────────────────────────────────┐
 │ 6. Research Report Generation            │  Structured, traceable report
 └──────────┬───────────────────────────────┘
            ▼
 ┌──────────────────────────────────────────┐
 │ 7. Expert Review & Follow-up             │──► Deeper dives, comparisons,
 └──────────────────────────────────────────┘    corrections, new directions
                                                 (context preserved → Stage 2/3)
```

### Journey Characteristics

| Characteristic | Description |
|---|---|
| Expert-centered | The user is a qualified specialist who critically evaluates results; the AI supports, not replaces, their judgment. |
| Autonomous by default | The AI proceeds without unnecessary questions when the request is clear. |
| Consultative when it matters | The AI asks questions only when doing so materially improves the outcome; for complex research, it presents a research plan for approval before main research begins. |
| Transparent | Assumptions, scope changes, evidence quality, and uncertainty are disclosed. |
| Iterative | Research is not strictly linear; discovery and analysis can loop, and follow-ups build on prior context. |
| Report-oriented | The primary output is a structured Technology Scouting Report, not a chat answer. |

---

## 3. Hybrid Interaction Principles — DECIDED

> **Status: DECIDED** — Confirmed design decision.

### Core Principle

> **"AI should ask only questions that materially improve the research outcome. Otherwise, it should make reasonable assumptions, disclose them, and proceed."**

### Interaction Rules

| # | Situation | AI Behavior |
|---|---|---|
| R1 | **Clear request** | Begin research immediately, without unnecessary questions. |
| R2 | **Minor gaps** | Make reasonable assumptions, disclose them, and proceed. |
| R3 | **Important ambiguities** | Ask **1–3 targeted questions** before proceeding. |
| R4 | **Very broad or complex research** | Develop a **research plan**, present it for user review and approval, and **wait for approval** before beginning the main research execution. After approval, perform the research autonomously, expanding it dynamically under R5 and R6. This approval gate applies to complex research only. |
| R5 | **Interesting findings within scope** | Autonomously expand research when justified, and disclose the expansion. |
| R6 | **Major new directions outside the original scope** | Notify the user and **propose** additional research rather than pursuing it unilaterally. |
| R7 | **Follow-up questions** | Continue research while preserving the context of the ongoing research. |

### Interpretation Guidance — DRAFT

- **Minor gap vs. important ambiguity:** A gap is *minor* if any reasonable interpretation leads to a broadly similar research outcome (e.g., an unspecified time window for publications). An ambiguity is *important* if different interpretations would lead to materially different research directions, sources, or conclusions (e.g., "battery recycling" could mean hydrometallurgical processes, direct recycling, or business models).
- **Questions must be targeted:** Questions should be specific, answerable quickly, and ideally offer options. Open-ended questionnaires are to be avoided.
- **Within scope vs. outside scope:** An expansion is *within scope* if it directly serves the user's stated objective (e.g., an adjacent variant of a technology being investigated). It is *outside scope* if it would shift the objective, domain, or question (e.g., a different application area or a different technology class).
- **Expert users:** Because users are technical specialists, the AI should assume technical literacy and avoid simplifying questions or explanations unless asked.

> **OPEN ITEM:** Precise thresholds for "broad or complex" research (R4) and for justified autonomous expansion (R5) are not yet defined and should be refined through testing. Further open clarification behaviors (plan rejection, non-response, pausing, combined R3/R4 cases) are listed in [Section 14](#14-open-items).

---

## 4. Stage 1 — Research Request

### Purpose

Capture the user's research need in their own words, with as much or as little detail as they choose to provide.

### User Input

A natural-language description of one or more of:

- a **research problem** (e.g., a technical challenge to be solved),
- a **research objective** (e.g., identify candidate technologies for a purpose),
- a **specific question** (e.g., how a technology compares to alternatives),
- an **area of interest** (e.g., an emerging technology field to be explored).

The user may optionally include context such as application domain, constraints, performance requirements, preferred source types, time horizon, or intended use of the results.

### AI Activities

- Receive the user's research request.
- No research is performed at this stage; interpretation begins in Stage 2.

### Expected Output

- A research request ready for interpretation.

### User Interaction

- Free-form input. The user is **not** required to fill in a structured form.

> **PROPOSED:** Optional structured fields or templates (e.g., domain, constraints, target maturity) could help users specify requests, but must not be mandatory.

### Considerations

- Requests from expert users may be highly specialized, terse, or rich in domain terminology. The system must handle both very brief and very detailed requests.
- A request may implicitly contain multiple questions; these should be identified in Stage 2.

---

## 5. Stage 2 — Request Interpretation & Research Planning

### Purpose

Understand what the user actually needs and decide how to proceed — immediately, with disclosed assumptions, with clarifying questions, or with a research plan — according to the hybrid interaction rules.

### User Input

- The research request from Stage 1.
- Answers to clarifying questions or plan feedback, if requested.

### AI Activities

1. **Interpret the objective:** Determine the underlying goal, the type of request (problem, objective, question, or area of interest), and the intended use of the results where inferable.
2. **Define scope:** Identify the technology domain(s), boundaries, and what is explicitly or implicitly out of scope.
3. **Identify research directions:** Determine the main lines of inquiry (e.g., candidate technology classes, alternative approaches).
4. **Derive search vocabulary:** Identify keywords, synonyms, technical terms, and relevant categories or classifications.
5. **Identify relevant source types:** E.g., scientific publications, patents, technical documentation, company and product information, institutional sources.
6. **Detect gaps and ambiguities:** Classify each as minor or important.
7. **Apply the hybrid interaction rules:**
   - Clear request → proceed (R1).
   - Minor gaps → state assumptions and proceed (R2).
   - Important ambiguities → ask 1–3 targeted questions (R3).
   - Very broad or complex request → develop a research plan and present it for approval; main research begins only after approval (R4).

### Expected Output

Depending on the case:

| Case | Output |
|---|---|
| Clear request | Brief statement of interpreted objective and scope; research begins. |
| Minor gaps | Interpreted objective, scope, and **disclosed assumptions**; research begins. |
| Important ambiguities | **1–3 targeted questions**. Whether research pauses until answers are received or continues on provisional assumptions is an **OPEN ITEM**. |
| Broad / complex request | A **research plan** for review and approval. Main research execution begins only after approval (R4). |
| Outside product scope | See [Out-of-Scope Requests — PROPOSED](#out-of-scope-requests--proposed) below. |

A research plan, when produced, should typically describe — **DRAFT**:

- interpreted objective,
- scope and boundaries,
- planned research directions,
- intended source types,
- key assumptions,
- expected report focus.

### User Interaction

- **Often none:** For clear requests, the user is informed but not asked anything.
- **Optional correction:** The user may correct disclosed assumptions at any time.
- **Required response:** Only for important ambiguities (answers) or complex research (plan approval, modification, or rejection).

> **OPEN ITEMS:** Behavior when the user rejects a proposed plan, does not respond to clarification questions, or submits a request that is both ambiguous (R3) and very broad (R4) is not yet defined (see [Section 14](#14-open-items)).

### Out-of-Scope Requests — PROPOSED

> **Status: PROPOSED** — Not yet decided.

Some requests may fall outside TechScout AI's technology scouting and technical research purpose (e.g., casual conversation, non-technical general questions, or tasks unrelated to technology research). Consistent with positioning decision D7, TechScout AI should not behave as a general-purpose chatbot. Possible behavior:

- Recognize that the request is outside the product's purpose.
- Briefly and transparently state this to the user.
- Where a technology research angle plausibly exists, suggest how the request could be reformulated as a technology scouting or technical research question.
- Not attempt to fulfill unrelated general-purpose tasks.

> **OPEN ITEM:** The boundary between in-scope and out-of-scope requests, and how strictly it is applied, is not yet defined.

### Potential Failure Points & Considerations

- **Over-questioning:** Asking unnecessary questions undermines autonomy and frustrates expert users.
- **Under-questioning:** Proceeding on a wrong interpretation of an important ambiguity wastes research effort and produces an irrelevant report.
- **Hidden assumptions:** Assumptions that are made but not disclosed violate transparency.
- **Scope too narrow or too broad:** Overly narrow scope can miss relevant alternatives; overly broad scope can dilute analytical depth.
- **Terminology mismatch:** Different fields use different terms for similar concepts; search vocabulary must account for this.

---

## 6. Stage 3 — Deep Research & Discovery

### Purpose

Find relevant technologies, innovations, and supporting technical evidence from accessible sources.

### User Input

- None required. The user may be informed of progress or of proposed scope changes.

### AI Activities

- Search relevant **accessible sources** according to the interpreted scope and research directions.
- Discover and collect information on:
  - technologies and innovations,
  - scientific publications,
  - patents,
  - products,
  - companies, research institutions, and other organizations,
  - technical evidence (e.g., reported performance data, test results, technical documentation).
- Filter irrelevant or low-quality results.
- **Iterate:** refine search terms, follow references, and explore new leads as understanding improves.
- Apply hybrid rules during discovery:
  - **R5** — Expand within scope autonomously when justified, and disclose the expansion.
  - **R6** — Notify the user and propose additional research when a major out-of-scope direction emerges.
- Record source information for every relevant finding to enable later traceability.

### Expected Output

- A collected, filtered body of findings with associated sources, organized by candidate technology or research direction.
- A record of any autonomous scope expansions and any proposed out-of-scope directions.

### User Interaction

- Generally autonomous.
- The user is notified of out-of-scope opportunities and decides whether to pursue them.

> **PROPOSED:** Visible progress updates during research (e.g., directions being investigated, number of sources reviewed).

### Potential Failure Points & Considerations

- **Source accessibility:** Some relevant sources (e.g., paywalled publications, commercial patent databases) may not be accessible. A massive proprietary patent database is **not planned** for the initial MVP. Limits of source coverage must be disclosed rather than hidden.
- **Coverage bias:** Results may over-represent well-publicized technologies or certain regions, languages, or source types.
- **Source quality variation:** Marketing material, press releases, and peer-reviewed work differ in reliability and must not be treated equally.
- **Recency:** The newest developments may be underrepresented in accessible sources.
- **Uncontrolled scope creep:** Autonomous expansion must remain justified and disclosed.
- **Missing evidence:** Absence of information found is not evidence that a technology is weak or immature (consistent with the assessment principles in the Product Definition).
- **Low or insufficient evidence:** Research may find little, weak, or no credible evidence. See [Low-Evidence Research Path — PROPOSED](#low-evidence-research-path--proposed).
- **Stopping research:** The stopping principle is approved; the precise criteria for deciding that sufficient research has been completed are an **OPEN ITEM** (see [Section 11](#11-iterative-research--feedback-loops)).

---

## 7. Stage 4 — Technical Analysis

### Purpose

Develop a technically deep and critical understanding of each relevant technology, appropriate for expert users.

> **Analytical layers — APPROVED:** Technical Analysis, Comparative Analysis, and Technology Assessment are **distinct analytical layers**, even when they are combined within a single capability or journey stage (see [MVP_SCOPE.md, Section 4.1](MVP_SCOPE.md#41-capability-summary)). Journey stages do not map one-to-one to these layers: this stage includes some assessment-related analysis (e.g., maturity, feasibility), and Stage 5 includes comparison and assessment. The layers remain distinguishable in the report (Detailed Technology Analysis, Comparative Analysis, Assessment & Opportunities).

### User Input

- None required.

### AI Activities

For each relevant technology, analyze where evidence allows:

- **Technical principles and mechanisms** — how it works.
- **Differentiators** — what distinguishes it from alternatives.
- **Applications** — current and potential use cases.
- **Performance** — reported metrics and the conditions under which they were obtained.
- **Maturity** — development stage based on available evidence.
- **Feasibility** — technical and practical feasibility.
- **Advantages and limitations.**
- **Risks and trade-offs.**
- **Evidence quality** — strength, independence, and consistency of supporting sources; critical examination of claims.

Throughout, **clearly distinguish sourced claims and evidence from AI-generated interpretation** (see [Section 12](#12-facts-interpretation-assumptions--uncertainty)).

If analysis reveals critical evidence gaps, return to Stage 3 for targeted additional research.

### Expected Output

- Analyzed technology information that can populate technology profiles.

> The Technology Profile is an approved report element ([MVP_SCOPE.md, C7](MVP_SCOPE.md#c7--evidence-synthesis--report-generation)); its fields remain **PROPOSED** (see [PRODUCT_DEFINITION.md, Section 11](PRODUCT_DEFINITION.md#11-technology-profile--approved-fields-proposed)).

### User Interaction

- Generally autonomous; results are presented in later stages.
- If analysis reveals a major new direction outside the original scope (e.g., an unexpected application area or technology class), the AI notifies the user and proposes additional research rather than pursuing it unilaterally (**R6**).

### Potential Failure Points & Considerations

- **Uncritical acceptance of claims:** Vendor or self-reported performance claims must be identified as such and not presented as independently verified.
- **Incomparable metrics:** Performance figures reported under different test conditions may not be directly comparable; this must be flagged.
- **Superficial analysis:** Expert users require technical depth, not generic summaries.
- **Interpretation presented as fact:** The most important transparency risk at this stage.
- **Inconsistent maturity judgments:** Without an agreed maturity framework, maturity statements must be justified with evidence.

> **Maturity — partially decided:** For the MVP, Technology Readiness Levels (TRL) may be used when relevant and evidence-supported (**APPROVED**, see [MVP_SCOPE.md, C6](MVP_SCOPE.md#c6--technology-assessment--evaluation)).
>
> **OPEN ITEM:** The broader maturity framework, including how maturity is expressed where TRL is not relevant, has not been defined.

---

## 8. Stage 5 — Synthesis & Evaluation

### Purpose

Turn individual analyses into an integrated view of the technology landscape that supports the user's decisions.

### User Input

- None required.

### AI Activities

- **Organize findings** into a coherent structure (e.g., by technology class, approach, or application).
- **Compare technologies** across relevant technical and practical dimensions.
- **Identify the most promising candidates** relative to the user's objective, with justification.
- **Identify opportunities** and **patterns** (e.g., converging approaches, recurring limitations).
- **Identify knowledge gaps** — what is unknown, unverified, or under-researched.
- **Assess potential** of technologies relative to the user's objective.

### Scoring and Assessment Constraint

> **Status: PROPOSED / DRAFT** — Any scoring or rating framework, including the Technology Potential Score described in [PRODUCT_DEFINITION.md, Section 12](PRODUCT_DEFINITION.md#12-technology-assessment--approved-potential-score-draft), is **provisional** and must **not** be presented as finalized. Universal scoring is excluded from the MVP, and a formal weighted scoring model is **DEFERRED** (see [MVP_SCOPE.md, C6](MVP_SCOPE.md#c6--technology-assessment--evaluation)).

Any assessment produced must follow the agreed assessment principles:

- accompanied by justification and supporting evidence,
- presented as an AI assessment, not an objective fact,
- with uncertainties disclosed,
- without treating missing data as negative evidence.

### Expected Output

- A comparative, prioritized synthesis with justified conclusions, identified opportunities, and explicit knowledge gaps.

### User Interaction

- Generally autonomous; results are presented in the report.
- If synthesis reveals a major opportunity or pattern outside the original scope, the AI notifies the user and proposes additional research (**R6**), typically within the report's recommendations or research gaps.

### Potential Failure Points & Considerations

- **False precision:** Numerical scores may suggest more certainty than the evidence supports.
- **Uneven evidence:** Technologies with more published information may appear more promising simply because they are better documented.
- **Objective misalignment:** Prioritization must reflect the user's stated objective, not generic popularity.
- **Premature conclusions:** Where evidence is insufficient, the synthesis should say so rather than force a ranking.

---

## 9. Stage 6 — Research Report Generation

### Purpose

Deliver the research outcome as a **structured, evidence-supported Technology Scouting Report** — the core product output (D5).

### User Input

- None required.

### AI Activities

- Compile findings, analysis, and synthesis into a structured report.
- Ensure **source traceability**: key statements are linked to their supporting sources.
- Clearly mark sourced claims, evidence, AI interpretations, assumptions, and uncertainties.

#### Report Structure — APPROVED

The report follows the adaptive 9-section structure defined in [MVP_SCOPE.md, C7](MVP_SCOPE.md#c7--evidence-synthesis--report-generation) (see also [PRODUCT_DEFINITION.md, Section 10](PRODUCT_DEFINITION.md#10-standard-research-report--approved)). Not every section must appear in every report.

#### Expected Report Contents — PROPOSED

> **Status: PROPOSED** — The following list describes the content the report is expected to cover; it is **not** an approved mandatory minimum.

- conclusions,
- comparisons — **where relevant** to the user's research question (not mandatory in every report, e.g., when a single technology is investigated),
- recommendations,
- uncertainties,
- research gaps and evidence gaps,
- source coverage limitations (e.g., source types or databases that were inaccessible or not searched),
- disclosed assumptions and scope decisions, including autonomous expansions.

When evidence is insufficient, the report follows the [Low-Evidence Research Path — PROPOSED](#low-evidence-research-path--proposed).

### Expected Output

- A Technology Scouting Report that an expert can critically review, verify against sources, and use as a basis for decisions.

### User Interaction

- The user receives and reads the report, then moves to Stage 7.

> **Presentation — APPROVED:** The report is presented within the application, with initially limited export capability ([MVP_SCOPE.md, C7](MVP_SCOPE.md#c7--evidence-synthesis--report-generation)).
>
> **OPEN ITEM:** Specific export formats and report length options have not been defined.

### Potential Failure Points & Considerations

- **Broken or vague traceability:** Statements without verifiable sources undermine trust for expert users.
- **Fabricated or inaccurate citations:** Every cited source must correspond to a real, accessed source; this is a critical quality requirement.
- **Overlong or unfocused reports:** Depth must not come at the expense of clarity and decision-usefulness.
- **Recommendations stated too strongly:** Recommendations must reflect evidence strength and remain clearly AI-generated.

---

## 10. Stage 7 — Expert Review & Follow-up

### Purpose

Enable the user to apply their own expertise to the results and direct further research, embodying the principle: *"TechScout AI should not replace technical expertise. It should amplify it."*

### User Input

The user reviews the report and may:

- **select technologies** for deeper investigation,
- **request comparisons** between specific technologies,
- **request further research** on aspects or gaps,
- **submit corrections** (e.g., challenge a claim, interpretation, or assumption based on their expertise),
- **propose new directions**,
- ask **follow-up questions**.

### AI Activities

- **Retain the context** of the ongoing research: original objective, scope, assumptions, findings, sources, and previous follow-ups (R7).
- Interpret the follow-up request and apply the hybrid interaction rules again (re-entering Stage 2 at an appropriate level of detail).
- Perform additional research and analysis as needed (Stages 3–5).
- Incorporate user corrections and clearly reflect them in subsequent outputs.
- Deliver updated or additional results.

### Expected Output

Depending on the request — **DRAFT**:

- a focused answer to a follow-up question,
- a deeper investigation of selected technologies,
- a comparison,
- an updated or extended report.

> **Follow-up and report updates — APPROVED:** Exploratory follow-up research does not automatically modify the main report. The main report is updated when the user requests an update ([MVP_SCOPE.md, C8](MVP_SCOPE.md#c8--interactive-research--follow-up)).
>
> **OPEN ITEM:** The exact format of a requested report update (e.g., revised version of the report vs. separate supplement) is **not yet decided**.

### User Interaction

- The user leads this stage. The AI responds and may propose further research but does not decide the direction on the user's behalf.

### Potential Failure Points & Considerations

- **Context loss:** Forgetting earlier scope, assumptions, or corrections forces users to repeat themselves.
- **Ignoring expert corrections:** User corrections must be respected and propagated.
- **Corrections conflicting with strong evidence — PROPOSED:** If a user correction conflicts with strong evidence, the AI could transparently present the conflicting evidence rather than silently comply or dismiss it. *Not yet approved; how such conflicts are handled remains an open design question.*
- **Context drift — PROPOSED:** Over many follow-ups, the research context may diverge from the original objective. The AI could recognize when a follow-up effectively constitutes a new research request. *Not yet approved; whether and how this detection occurs, and what happens next, remains an open design question.*

> **FUTURE:** Saving, reopening, and managing research projects across sessions, and long-term research history, are not defined for the MVP.

---

## 11. Iterative Research & Feedback Loops

The journey is presented as sequential stages, but research is **iterative**. The following loops are part of the intended behavior:

| Loop | From → To | Trigger | Who initiates |
|---|---|---|---|
| Clarification loop | Stage 2 ↔ User | Important ambiguity or complex request requiring plan approval | AI (R3, R4) |
| Discovery loop | Stage 3 → Stage 3 | New leads, refined terminology, references to follow | AI |
| Evidence gap loop | Stage 4/5 → Stage 3 | Analysis or synthesis reveals critical missing evidence | AI |
| Within-scope expansion | Stage 3 → Stage 3 | Interesting finding that serves the objective | AI, disclosed (R5) |
| Out-of-scope proposal | Stage 3/4/5 → User | Major new direction outside original scope | AI proposes, user decides (R6) |
| Expert follow-up loop | Stage 7 → Stage 2/3 | User requests deeper research, comparisons, corrections, or new directions | User (R7) |

### Loop Principles

> **Iterative research and stopping principle — APPROVED:** Research is iterative and autonomous. The agent stops when further research is no longer sufficiently valuable or when adequate coverage has been achieved ([MVP_SCOPE.md, C3](MVP_SCOPE.md#c3--deep-research--investigation)). The precise stopping criteria and thresholds remain **OPEN** (see below).

Further loop principles — **DRAFT**:

- **Transparency:** Significant iterations, scope expansions, and their reasons should be visible in the output.
- **User control over direction:** The AI may autonomously deepen research within scope, but changes to the research objective remain the user's decision.
- **Context continuity:** Each loop builds on what is already known rather than restarting.

> **OPEN ITEMS:**
>
> - **Research stopping criteria:** How the AI decides that sufficient research has been completed, and when it should stop searching and move on to synthesis, is not yet defined. No thresholds are assumed.
> - **Research effort limits:** Limits on research depth, duration, or effort per request (e.g., time or cost constraints) are not yet defined.
> - **Waiting during R6 proposals:** Whether in-scope research pauses or continues while an out-of-scope proposal awaits the user's decision is not yet defined.

### Low-Evidence Research Path — PROPOSED

> **Status: PROPOSED** — Not yet decided.

Research may find little, weak, or no credible evidence (e.g., a very new field, a niche topic, or limited source accessibility). This is a legitimate research outcome, not a failure to be hidden. Possible behavior:

- **Report insufficiency transparently:** State clearly that the available evidence is insufficient to support firm conclusions.
- **Explain what was searched:** Describe the research directions, search vocabulary, and source types covered, and the potential coverage limitations.
- **Avoid unsupported conclusions:** Do not fill gaps with speculation presented as findings; any tentative interpretation must be clearly labeled as such.
- **Do not treat missing data as negative evidence:** Lack of evidence is reported as a knowledge gap, not as a weakness of the technology.
- **Suggest next steps:** Propose alternative search directions, adjacent terminology, or a reformulation of the research question.

> **OPEN ITEM:** Whether a low-evidence outcome still produces a full report, a shortened report, or an interim notice to the user before report generation is not yet defined.

---

## 12. Facts, Interpretation, Assumptions & Uncertainty

Distinguishing types of information is fundamental to trust and to the product's role of amplifying expert judgment. It applies across Stages 2–7 and especially in Stages 4–6.

### Terminology

This document aligns with the "sourced facts" principle in [PRODUCT_DEFINITION.md, Section 12](PRODUCT_DEFINITION.md#12-technology-assessment--approved-potential-score-draft). To avoid implying that everything stated in a source is objectively proven, it uses the term **sourced claim** for any statement attributable to an identified source, and reserves **verified evidence** for claims with stronger support.

| Category | Definition | Examples | Required handling |
|---|---|---|---|
| **Sourced claim** | A statement attributable to an identified source, regardless of whether it has been independently confirmed. | A performance value reported by a manufacturer; an efficiency figure in a single publication; a company's announced product capability. | Linked to its source. The source type is indicated (e.g., peer-reviewed publication, patent, technical documentation, vendor material, press). Not presented as proven. |
| **Verified evidence** | A sourced claim with stronger support, e.g., corroborated by multiple independent credible sources or established in authoritative records. | A result replicated by independent research groups; a patent's filing date and assignee from patent records. | Linked to its supporting sources. Basis of verification indicated. |
| **AI interpretation** | Analysis, inference, comparison, assessment, or recommendation generated by the AI from the evidence. | Maturity judgment; ranking of candidates; identified trend; potential assessment. | Clearly labeled as AI-generated; justified with reference to the evidence it is based on. |
| **Assumption** | A premise adopted by the AI to proceed where information was missing. | Assumed time window; assumed application context; assumed interpretation of a term. | Disclosed explicitly, ideally at the point where it affects the research and summarized in the report; correctable by the user. |
| **Uncertainty** | A recognized limitation in knowledge or evidence. | Conflicting sources; single unverified source; inaccessible data; extrapolated performance. | Disclosed explicitly; where possible, its cause and effect on conclusions are stated. |

### Principles

- A **sourced claim is not automatically verified evidence**: the reliability and independence of the source matter. A vendor claim establishes *that the vendor claims something*, not that the claim is true.
- **Missing data is not negative evidence**: lack of information must be reported as a gap, not as a weakness of the technology.
- **Confidence should reflect evidence**: conclusions supported by multiple independent, high-quality sources warrant higher confidence than those based on a single or self-reported source.
- **Users must be able to verify**: expert users should be able to trace any significant statement back to its source or recognize it as AI interpretation.

> **OPEN ITEM:** The criteria for treating a sourced claim as verified evidence are not yet defined.
>
> **OPEN ITEM:** How these categories are visually or structurally marked in the report (e.g., labels, confidence indicators, citation format) is not yet defined. A per-technology "confidence level and evidence quality" field is **PROPOSED** in the Technology Profile.

---

## 13. End-to-End Workflow Summary

| # | Stage | User | AI | Output |
|---|---|---|---|---|
| 1 | Research Request | Describes problem, objective, question, or area of interest in natural language | Receives request | Research request |
| 2 | Interpretation & Planning | Answers questions / approves plan **only if needed** (plan approval required for complex research) | Interprets objective, scope, directions, vocabulary, sources, ambiguities; applies hybrid rules | Interpretation + assumptions, **or** 1–3 questions, **or** research plan awaiting approval |
| 3 | Deep Research & Discovery | Decides on proposed out-of-scope directions | Searches accessible sources; discovers technologies and evidence; iterates; expands within scope | Sourced body of findings |
| 4 | Technical Analysis | — | Analyzes mechanisms, performance, maturity, feasibility, limitations, risks, evidence quality; separates sourced claims and evidence from interpretation | Analyzed technology information |
| 5 | Synthesis & Evaluation | — | Organizes, compares, prioritizes; identifies opportunities, patterns, gaps; provisional assessment only | Comparative, justified synthesis |
| 6 | Report Generation | Reads report | Compiles traceable, structured report with conclusions, comparisons (where relevant), recommendations, uncertainties, gaps, coverage limitations | Technology Scouting Report |
| 7 | Expert Review & Follow-up | Reviews; selects, compares, corrects, redirects | Retains context; re-applies hybrid rules; researches further | Follow-up results / updated outputs |

**In one sentence:** The user states a research need; the AI interprets it, asks only what materially matters, researches and critically analyzes the evidence, and delivers a traceable Technology Scouting Report — then continues the research under the user's expert direction.

> This summary describes the target journey, not the MVP scope, which is defined in [MVP_SCOPE.md](MVP_SCOPE.md) (see [Document Scope](#document-scope)).

---

## 14. Open Items

The following items are **not finalized** and were not assumed in this document. Approved decisions referenced for context are labeled as such. MVP-relevant open items are also listed in [MVP_SCOPE.md, Section 9](MVP_SCOPE.md#9-open-items).

### Clarification & Interaction Behavior

| Item | Status |
|---|---|
| Thresholds for "broad or complex" requests (R4) and justified autonomous expansion (R5) | OPEN ITEM |
| Behavior when the user rejects a proposed research plan | OPEN ITEM |
| Behavior when the user does not respond to clarification questions | OPEN ITEM |
| Whether research pauses while awaiting answers, or continues on provisional assumptions | OPEN ITEM |
| Handling of requests that are both ambiguous (R3) and very broad (R4) | OPEN ITEM |
| Whether research pauses or continues while an out-of-scope (R6) proposal awaits a decision | OPEN ITEM |
| Out-of-scope request handling and the in-scope/out-of-scope boundary | PROPOSED / OPEN ITEM |
| Handling of user corrections that conflict with strong evidence | PROPOSED |
| Detection of follow-ups that effectively become new research requests (context drift) | PROPOSED |

### Research & Evidence

| Item | Status |
|---|---|
| Research stopping criteria (when to stop searching and move to synthesis) | OPEN ITEM — stopping principle APPROVED ([Section 11](#11-iterative-research--feedback-loops)); criteria and thresholds not defined; no thresholds assumed |
| Low-evidence research path | PROPOSED |
| Output form for low-evidence outcomes (full report, shortened report, interim notice) | OPEN ITEM |
| Criteria for treating a sourced claim as verified evidence | OPEN ITEM |

### Outputs & Other

| Item | Status |
|---|---|
| Research plan format | DRAFT |
| Technology Potential Score / any scoring framework | DRAFT — provisional only; universal scoring excluded from the MVP; formal weighted scoring model DEFERRED |
| Broader maturity framework | OPEN ITEM — TRL may be used when relevant and evidence-supported (APPROVED, [MVP_SCOPE.md, C6](MVP_SCOPE.md#c6--technology-assessment--evaluation)) |
| Expected report contents (detailed section content) | PROPOSED — report structure itself APPROVED ([Section 9](#9-stage-6--research-report-generation)) |
| Technology profile fields | PROPOSED (Technology Profile as a report element APPROVED) |
| Marking of facts, interpretation, assumptions, uncertainty in outputs | To be defined |
| Format of requested report updates (revised report vs. supplement) | OPEN ITEM — exploratory follow-up does not modify the main report; updates on user request (APPROVED, [MVP_SCOPE.md, C8](MVP_SCOPE.md#c8--interactive-research--follow-up)) |
| Specific information sources and source access strategy | To be defined (Phase 2) |
| Progress visibility during research | PROPOSED |
| Optional structured request input | PROPOSED |
| Research depth / effort limits per request | To be defined |
| Specific export formats and report length options | OPEN ITEM — in-app presentation and initially limited export capability APPROVED |
| Saved research projects and history across sessions | FUTURE |
| Continuous monitoring | OUT OF SCOPE for the MVP ([MVP_SCOPE.md, Section 7](MVP_SCOPE.md#7-mvp-exclusions--out-of-scope)); long-term vision only |
