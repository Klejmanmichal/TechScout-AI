# TechScout AI — Core Use Cases

| Field | Value |
|---|---|
| Document | Core Use Cases |
| Project phase | Phase 1 — Product Definition |
| Status | Living document (in progress) |
| Related documents | [PRODUCT_DEFINITION.md](PRODUCT_DEFINITION.md), [CORE_USER_JOURNEY.md](CORE_USER_JOURNEY.md) |

> **Status labels used in this document** (consistent with [PRODUCT_DEFINITION.md](PRODUCT_DEFINITION.md) and [CORE_USER_JOURNEY.md](CORE_USER_JOURNEY.md))
>
> - **ACCEPTED** — Agreed for product definition.
> - **DRAFT** — Working text under development; content may still change.
> - **PROPOSED** — Concepts suggested for consideration that have **not** been approved.
> - **OPEN ITEM** — Unresolved question, deliberately left undecided.
>
> The **7 core use cases** are **ACCEPTED** as the core use case set for product definition. They are not yet recorded in the [PRODUCT_DEFINITION.md](PRODUCT_DEFINITION.md#17-current-status) decision log. Detailed content within each use case (research elements, expected outcomes, considerations) is **DRAFT** unless labeled otherwise.

---

## Table of Contents

1. [Purpose](#1-purpose)
2. [Scope and Principles](#2-scope-and-principles)
3. [Use Case Classification](#3-use-case-classification)
4. [Detailed Use Cases](#4-detailed-use-cases)
5. [Use Case Relationships](#5-use-case-relationships)
6. [Cross-Cutting Requirements](#6-cross-cutting-requirements)
7. [Open Questions and Future Refinement](#7-open-questions-and-future-refinement)

---

## 1. Purpose

This document defines the **core use cases** of TechScout AI: the principal research objectives that its target users want to achieve with the product.

It addresses Next Step 3 in [PRODUCT_DEFINITION.md, Section 18](PRODUCT_DEFINITION.md#18-next-steps) ("Define the primary use cases") and is intended as a reference for:

- MVP scope refinement,
- functional and non-functional requirements,
- acceptance criteria and evaluation,
- later technical design.

The document describes **what** users want to achieve. It does **not** describe **how** the application will technically implement it.

---

## 2. Scope and Principles

### 2.1 Scope

> **Important:**
>
> - This document describes the core use cases of the **intended product**. It does **not** define the finalized MVP scope, which remains **PROPOSED** (see [PRODUCT_DEFINITION.md, Section 14](PRODUCT_DEFINITION.md#14-mvp-direction--proposed)).
> - Which use cases, and to what depth, are included in the MVP will be determined during **MVP scope refinement**.
> - Use cases describe user objectives, not software features, modules, or architecture.

### 2.2 Target Users

All use cases are designed for the confirmed target users (D6): **highly technical professionals and qualified specialists**, including R&D professionals, researchers, engineers, innovation managers, and technology managers. Users are assumed to be technically literate and able to critically evaluate evidence.

### 2.3 Guiding Principles

- **Amplify, do not replace, expertise (D7):**

  > *"TechScout AI should not replace technical expertise. It should amplify it."*

- **Research tool, not a chatbot:** Every use case results in structured, evidence-supported research outcomes, with the **Technology Scouting Report** as the core output (D5).
- **On-demand research (D4):** Use cases are initiated by a user research request; continuous monitoring is not part of the initial MVP direction.
- **Hybrid AI interaction (DECIDED):** All use cases follow the hybrid interaction model defined in [CORE_USER_JOURNEY.md, Section 3](CORE_USER_JOURNEY.md#3-hybrid-interaction-principles--decided): the AI asks only questions that materially improve the research outcome; otherwise it makes reasonable assumptions, discloses them, and proceeds.
- **Common journey:** All use cases follow the same 7-stage core user journey (see [CORE_USER_JOURNEY.md](CORE_USER_JOURNEY.md)). Use cases differ in research objective and emphasis, not in the fundamental journey.

---

## 3. Use Case Classification

The use cases are grouped into three categories by the nature of the user's objective.

> **Note:** These categories are **organizational groupings only**. They do **not** represent final software modules, product features, menus, or system architecture.

| Group | Focus | Use Cases |
|---|---|---|
| **A. Discovery & Exploration** | Finding what exists or what could be possible | UC01 — Technology Discovery<br>UC06 — Technology Opportunity Scouting |
| **B. Investigation & Intelligence** | Understanding a technology or field in depth | UC02 — Deep Technical Investigation<br>UC05 — Patent & Research Landscape |
| **C. Decision Support & Assessment** | Supporting technical evaluation and decisions | UC03 — Technology Comparison & Benchmarking<br>UC04 — Technology Substitution<br>UC07 — Technical Feasibility Assessment |

Use case numbering reflects identification order, not priority. MVP prioritization is an **OPEN ITEM** (see [Section 7](#7-open-questions-and-future-refinement)).

---

## 4. Detailed Use Cases

Each use case is described using the same structure:

- **Purpose** — the user objective.
- **Typical research requests** — illustrative examples only; not an exhaustive or approved list.
- **Research may include** — the elements the research may cover, as relevant to the request.
- **Expected outcome** — what the user should gain.
- **Key considerations** — quality risks and principles specific to the use case.

The elements listed under "Research may include" are **not mandatory checklists**; their relevance depends on the request and on available evidence.

---

### UC01 — Technology Discovery

| Field | Value |
|---|---|
| Group | A. Discovery & Exploration |
| Status | ACCEPTED |

#### Purpose

Discover new, emerging, promising, breakthrough, or potentially disruptive technologies within a specified domain, problem area, industry, or field of interest.

The AI helps identify relevant technologies the user may not already know, summarizes their fundamental concepts, explains why they are of interest, and provides supporting evidence and sources.

#### Typical Research Requests (illustrative)

- "What emerging technologies exist for low-temperature hydrogen storage?"
- "Identify promising new approaches to recycling composite materials."

#### Research May Include

- Identification of relevant technologies within the specified area
- Fundamental concept and operating principle of each technology
- Reasons why each technology is of interest (e.g., novelty, potential impact, differentiators)
- Indicative development and maturity stage
- Key organizations, research groups, or companies involved
- Supporting evidence and sources

#### Expected Outcome

A structured overview of the technology landscape in the specified area, enabling the user to recognize relevant technologies — including ones previously unknown to them — and to select candidates for further investigation.

#### Key Considerations

- **Relevance over volume:** Results should be filtered for relevance to the user's objective rather than maximizing the number of technologies listed.
- **Novelty claims:** Descriptions such as "breakthrough" or "disruptive" are AI interpretations and must be justified with evidence, not adopted from promotional sources.
- **Discovery bias:** Well-publicized technologies may be over-represented; less visible but relevant developments should not be systematically missed.

---

### UC02 — Deep Technical Investigation

| Field | Value |
|---|---|
| Group | B. Investigation & Intelligence |
| Status | ACCEPTED |

#### Purpose

Conduct a detailed investigation of a specific technology, material, process, scientific concept, or technical solution, at a depth appropriate for technical professionals rather than general audiences.

#### Typical Research Requests (illustrative)

- "Investigate solid-state electrolytes based on sulfide compounds: mechanisms, performance, and challenges."
- "Explain in technical depth how a specific additive manufacturing process works and where its limitations are."

#### Research May Include

- Operating principles and mechanisms
- Material composition or technical structure, where relevant
- Properties and performance characteristics
- Advantages and limitations
- Technical challenges
- Current development status
- Applications
- Scientific and industrial evidence
- Research gaps and unresolved questions

#### Expected Outcome

An in-depth, evidence-supported technical understanding of the subject, including what is established, what is claimed but not verified, and what remains unknown.

#### Key Considerations

- **Expert-level depth:** Explanations should not be simplified for general audiences unless the user requests it.
- **Claim scrutiny:** Reported performance must be presented with its source type and test conditions; vendor or self-reported claims must not be presented as verified.
- **Explicit gaps:** Unresolved questions and research gaps are part of the result, not omissions to be hidden.

---

### UC03 — Technology Comparison & Benchmarking

| Field | Value |
|---|---|
| Group | C. Decision Support & Assessment |
| Status | ACCEPTED |

#### Purpose

Compare technologies, materials, processes, or solutions using structured and relevant criteria to support technical understanding and decision-making.

#### Comparison Modes (ACCEPTED)

| Mode | Description |
|---|---|
| **Mode A — User-Directed Comparison** | The user explicitly identifies the technologies or solutions to compare. |
| **Mode B — AI-Discovered Comparison** | The AI independently identifies relevant competing, alternative, similar, or potentially superior technologies and proposes them for comparison. |

Mode B follows the hybrid interaction model: candidates within the scope of the user's objective may be included autonomously with disclosure (R5); candidates representing a major new direction are proposed to the user (R6).

> **OPEN ITEM:** Whether AI-discovered candidates in Mode B are compared immediately or first proposed to the user for confirmation has not been defined beyond the general hybrid interaction rules.

#### Typical Research Requests (illustrative)

- Mode A: "Compare PEM and solid oxide electrolysis for industrial hydrogen production."
- Mode B: "Compare our current coating process with the most relevant alternatives."

#### Research May Include

Potential comparison criteria, selected according to relevance:

- Operating mechanism
- Technical properties
- Performance
- Advantages and disadvantages
- Limitations
- Technology maturity
- Scalability
- Cost, when reliable information is available
- Industrial applicability
- Technical trade-offs

#### Expected Outcome

A structured, evidence-supported comparison that clarifies the relative strengths, weaknesses, and trade-offs of the options, together with conclusions and identified information gaps.

#### Key Considerations

- **Comparable conditions:** The AI must account for differences in test conditions and methodologies and flag values that are not directly comparable.
- **No misleading comparisons:** Options must not appear superior merely because more or more favorable information is available about them.
- **Information gaps:** Missing data for one option must be identified as a gap, not treated as a disadvantage.
- **Cost data:** Cost should be included only where reliable information is available, with its source and limitations disclosed.
- **Provisional scoring:** Any scoring or ranking used in comparisons remains provisional (see [PRODUCT_DEFINITION.md, Section 12](PRODUCT_DEFINITION.md#12-technology-assessment--proposed)).

---

### UC04 — Technology Substitution

| Field | Value |
|---|---|
| Group | C. Decision Support & Assessment |
| Status | ACCEPTED |

#### Purpose

Identify alternative technologies, materials, processes, or solutions that could replace an existing technology or solve a specific technical problem. This may include unconventional or non-obvious alternatives, not only direct replacements.

#### Typical Research Requests (illustrative)

- "Find alternatives to a fluorinated surface treatment that meet the same water-repellency requirements."
- "What could replace a rare-earth permanent magnet in this type of motor application?"

#### Research May Include

- The existing technology and its requirements
- Potential alternatives
- Functional equivalence
- Performance differences
- Advantages and disadvantages
- Compatibility
- Implementation barriers
- Risks
- Maturity
- Potential transition or implementation pathways

#### Expected Outcome

A set of evidence-supported substitution candidates, each assessed against the requirements of the existing technology, with barriers, risks, and potential pathways identified.

#### Key Considerations

- **Requirements first:** Substitution is only meaningful relative to the requirements the existing technology fulfills. Where these are unclear and materially affect the outcome, they are an important ambiguity under the hybrid interaction rules (R3).
- **Partial equivalence:** Alternatives may satisfy some but not all requirements; this must be stated explicitly rather than implying full equivalence.
- **Non-obvious alternatives:** Unconventional candidates should be clearly identified as such, with the supporting reasoning and evidence level stated.

---

### UC05 — Patent & Research Landscape

| Field | Value |
|---|---|
| Group | B. Investigation & Intelligence |
| Status | ACCEPTED |

#### Purpose

Explore the scientific, technological, and intellectual property landscape related to a topic.

#### Typical Research Requests (illustrative)

- "Map the research and patent activity in biodegradable packaging films over recent years."
- "Who are the key research institutions and companies working on perovskite solar cell stability?"

#### Research May Include

- Scientific publications
- Patents and patent applications
- Key organizations and research institutions
- Industrial players
- Research directions
- Emerging concepts
- Development activity
- Potential white spaces or gaps

#### Expected Outcome

A structured view of who is active in the field, which directions are being pursued, how activity is developing, and where potential gaps may exist.

#### Key Considerations

- **Evidence vs. interpretation:** The AI must distinguish established evidence (e.g., that a publication or patent exists) from interpretations about research activity, technological direction, or potential opportunities.
- **White spaces are hypotheses:** An apparent gap may reflect limited source coverage rather than a true absence of activity, and must be presented as an interpretation.
- **Source coverage:** Results depend on accessible sources. A massive proprietary patent database is not planned for the initial MVP (see [PRODUCT_DEFINITION.md, Section 14](PRODUCT_DEFINITION.md#14-mvp-direction--proposed)); coverage limitations must be disclosed.
- **Not legal advice:** Landscape insights are research support; they do not constitute legal assessments such as freedom-to-operate or patent validity opinions.

---

### UC06 — Technology Opportunity Scouting

| Field | Value |
|---|---|
| Group | A. Discovery & Exploration |
| Status | ACCEPTED |

#### Purpose

Identify potentially valuable technological opportunities, applications, combinations, or innovation directions.

#### Typical Research Requests (illustrative)

- "What new applications could exist for graphene-based sensors outside consumer electronics?"
- "Which technologies from other industries could address heat management in our battery packs?"

#### Research May Include

The AI may:

- Identify overlooked applications
- Connect technologies from different domains
- Explore cross-industry opportunities
- Identify potential use cases
- Suggest unconventional innovation directions
- Identify potential technical problems that a technology could solve
- Develop evidence-supported hypotheses for further exploration

#### Expected Outcome

A set of potential opportunities and innovation directions, each with its supporting evidence, reasoning, and level of speculation made explicit, enabling the user to decide which deserve further exploration.

#### Key Considerations

- **Documented vs. hypothetical:** The AI must clearly distinguish documented applications from AI-generated hypotheses and speculative opportunities.
- **Hypotheses are starting points:** Opportunities are proposals for further investigation, not validated conclusions.
- **Expert judgment:** This use case relies especially on the user's expertise to evaluate the plausibility and value of AI-generated hypotheses.

---

### UC07 — Technical Feasibility Assessment

| Field | Value |
|---|---|
| Group | C. Decision Support & Assessment |
| Status | ACCEPTED |

#### Purpose

Provide an initial structured assessment of whether a technology, concept, material, process, or solution could be technically feasible for a specified application or requirement.

#### Typical Research Requests (illustrative)

- "Could a bio-based resin meet the temperature and durability requirements of an automotive interior component?"
- "Assess whether this sensor technology could realistically operate in a high-vibration industrial environment."

#### Research May Include

- Technical requirements
- Relevant technology capabilities
- Evidence of demonstrated performance
- Maturity
- Key barriers
- Critical unknowns
- Risks
- Required development work
- Potential implementation pathway
- Areas requiring experimental validation

#### Expected Outcome

An initial, evidence-supported view of technical feasibility, identifying what supports it, what stands against it, what is unknown, and what would need to be validated.

#### Key Considerations

- **Not proof of feasibility:** The AI must not present an initial assessment as proof of feasibility.
- **Explicit uncertainty:** Uncertainty, assumptions, missing information, and required validation must be clearly identified.
- **Requirement clarity:** Feasibility depends on the specified application and requirements; where these are unclear and materially affect the result, they are an important ambiguity (R3).
- **Maturity framework:** Whether a standard maturity framework (e.g., Technology Readiness Levels) is used remains an **OPEN ITEM** (see [CORE_USER_JOURNEY.md](CORE_USER_JOURNEY.md#14-open-items)).

---

## 5. Use Case Relationships

The seven use cases represent **distinct user objectives**, but they naturally overlap. A single research request may involve several use cases, and a follow-up request (journey Stage 7) may shift the emphasis from one use case to another.

Use cases are therefore best understood as **research objectives that can be combined**, not as separate, mutually exclusive workflows.

### Example: Combined Research Request

> *"Identify sustainable alternatives to polycarbonate for manufacturing secure identity documents."*

This single request could involve the following use cases:

| Use Case | Role in the Request |
|---|---|
| **UC01 — Technology Discovery** | Discover candidate sustainable materials that could be relevant for identity document manufacturing. |
| **UC05 — Patent & Research Landscape** | Investigate scientific literature and patents on sustainable materials for secure documents and related applications. |
| **UC02 — Deep Technical Investigation** | Investigate promising candidates in depth (e.g., properties, processing behavior, durability, compatibility with security features). |
| **UC03 — Technology Comparison & Benchmarking** | Compare candidates against polycarbonate using relevant criteria, accounting for differences in test conditions. |
| **UC04 — Technology Substitution** | Identify which candidates could realistically replace polycarbonate, considering functional equivalence, compatibility, and implementation barriers. |
| **UC07 — Technical Feasibility Assessment** | Provide an initial assessment of whether leading candidates could be technically feasible for the intended application and its requirements. |
| **UC06 — Technology Opportunity Scouting** | Identify unconventional candidates, cross-domain solutions, or new solution directions beyond direct material replacement. |

In practice, the primary objective of this request is **substitution (UC04)**, supported by the other use cases. The hybrid interaction rules apply: for example, if the relevant requirements (e.g., durability, security feature integration, lifecycle) are unclear and would materially change the outcome, the AI asks targeted questions; otherwise it states its assumptions and proceeds.

> **OPEN ITEM:** Whether the product explicitly identifies or labels a request's primary use case, and how combined use cases are reflected in the report structure, is not yet defined.

---

## 6. Cross-Cutting Requirements

The following principles apply to **all** use cases. They are consistent with [PRODUCT_DEFINITION.md, Section 12](PRODUCT_DEFINITION.md#12-technology-assessment--proposed) and [CORE_USER_JOURNEY.md, Section 12](CORE_USER_JOURNEY.md#12-facts-interpretation-assumptions--uncertainty).

| # | Requirement | Description |
|---|---|---|
| CC1 | **Evidence-based research** | Findings and conclusions are grounded in evidence from identified sources. |
| CC2 | **Traceable sources** | Significant statements can be traced back to their supporting sources. |
| CC3 | **Facts vs. AI interpretation** | Sourced claims and verified evidence are clearly distinguished from AI-generated interpretations, assessments, and hypotheses. |
| CC4 | **Explicit assumptions** | Assumptions made by the AI are disclosed and can be corrected by the user. |
| CC5 | **Transparent uncertainty** | Uncertainties, conflicting evidence, and confidence limitations are stated explicitly. |
| CC6 | **Recognition of source limitations** | Limitations in source accessibility, coverage, and reliability are acknowledged. |
| CC7 | **Identification of missing data** | Information gaps are identified and reported as part of the result. |
| CC8 | **No misleading comparisons** | Comparisons account for differing conditions and methodologies and do not imply false equivalence or false precision. |
| CC9 | **Appropriate technical depth** | Depth and terminology are appropriate for highly technical professionals and qualified specialists. |
| CC10 | **Preserved research context** | Research context is preserved across follow-up interactions within the ongoing research. |

> **Principle:** Missing information must **not** automatically be interpreted as negative evidence. Absence of evidence is reported as a knowledge gap, not as a weakness of a technology.

> **Terminology note:** In line with [CORE_USER_JOURNEY.md, Section 12](CORE_USER_JOURNEY.md#12-facts-interpretation-assumptions--uncertainty), "facts" refers to **sourced claims** and **verified evidence**; a statement in a source is not automatically treated as proven.

---

## 7. Open Questions and Future Refinement

The following areas are **not finalized** and require further definition. No decisions are assumed in this document.

| Area | Open Question | Status |
|---|---|---|
| Acceptance criteria | What criteria define a successful outcome for each use case? | OPEN ITEM |
| Research depth | How deep should research go per use case, and how is sufficient depth determined? | OPEN ITEM (see also research stopping criteria in [CORE_USER_JOURNEY.md](CORE_USER_JOURNEY.md#14-open-items)) |
| Output requirements | Does each use case require specific report sections or outputs within the (PROPOSED) report structure? | OPEN ITEM |
| Evaluation criteria | How will output quality be evaluated per use case (e.g., relevance, accuracy, traceability)? | OPEN ITEM — related to success metrics (to be defined) |
| MVP prioritization | Which use cases, and to what depth, are included in the MVP? | OPEN ITEM — part of MVP scope refinement |
| Use case boundaries | Where exactly are the boundaries between overlapping use cases (e.g., UC01 vs. UC06, UC03 vs. UC04)? | OPEN ITEM |
| Combined requests | How are requests spanning multiple use cases identified and reflected in outputs? | OPEN ITEM |
| UC03 Mode B behavior | Are AI-discovered comparison candidates compared immediately or proposed first? | OPEN ITEM |
| Maturity framework | Is a standard maturity framework (e.g., TRL) used in UC02, UC03, UC04, and UC07? | OPEN ITEM |
| Additional use cases | Further use cases may be identified during product development and evaluation. | Future refinement |
| Decision log | Recording the accepted use case set in the PRODUCT_DEFINITION.md decision log. | Recommended |
