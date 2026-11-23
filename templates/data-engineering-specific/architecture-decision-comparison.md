---
name: "Choose the Best System Architecture"
category: "04-system-architecture"
use_case: "Choose or design a system architecture that meets the actual requirements and constraints."
difficulty: "advanced"
mode_support: "discovery-and-evidence"
default_mode: "both"
source_requirement: "optional"
standalone: true
version: "1.0.0"
original_path: "templates/data-engineering-specific/architecture-decision-comparison.md"
---

# Choose the Best System Architecture

**Purpose:** Determine which architecture should be used to solve a defined system problem. Compare viable designs against requirements, constraints, operational realities, and evidence.

**Use when:** There is a system, application, AI agent, data pipeline, computational engine, or technical workflow to build or redesign, and the architecture is uncertain. Existing documents and code are optional.

## Start with the user's actual situation

The user may not know architecture terminology or how to define the problem. Accept a plain-language description. Do not require the user to fill every field before beginning.

## Inputs

- What needs to be built or fixed: `[PLAIN-LANGUAGE DESCRIPTION]`
- Intended users and outcomes: `[OPTIONAL]`
- Functional requirements: `[KNOWN REQUIREMENTS OR UNKNOWN]`
- Constraints: `[BUDGET, TIME, PLATFORM, SKILLS, DATA, SECURITY, SCALE; OR UNKNOWN]`
- Existing materials: `[OPTIONAL DOCUMENTS, CODE, DIAGRAMS, LINKS; NONE IS VALID]`
- Success criteria: `[KNOWN MEASURES OR TO BE DEFINED]`

## Copy-ready prompt

```text
Act as an independent systems architect, engineering researcher, and critical decision analyst.

TASK: Choose the Best System Architecture

PROBLEM:
[Describe in ordinary language what needs to be built, changed, or fixed. If the user is unsure, work from the available description.]

TARGET SYSTEM / DOMAIN:
[KNOWN OR TO BE IDENTIFIED]

REQUIREMENTS AND CONSTRAINTS:
[KNOWN ITEMS; MARK UNKNOWN ITEMS AS UNKNOWN]

AVAILABLE MATERIALS:
[OPTIONAL SOURCES, CODE, DIAGRAMS, IMPLEMENTATIONS; WRITE NONE IF ABSENT]

OPERATING MODE
1. If no source material is supplied, use Discovery mode. Identify the missing technical knowledge and research relevant architectures, methods, standards, documentation, tools, and implementations when search access is available. Do not wait for uploaded sources.
2. If materials are supplied, use Evidence mode. Inspect them as evidence, not as unquestionable authority or a closed universe. Search for corroboration, alternatives, and missing perspectives when tools permit.
3. If both supplied evidence and external discovery are needed, use both modes.
4. If external search is unavailable, state this limitation and provide a concrete search and verification plan. Never imply that research was performed when it was not.

TASK WORKFLOW
1. Translate the plain-language problem into a precise architecture decision. Lock the system boundary, intended outcome, stakeholders, known requirements, constraints, and unknowns. Do not silently invent requirements.
2. Identify the decision drivers. Separate mandatory constraints from preferences. Define measurable acceptance criteria where the available information supports them.
3. Establish a baseline. Include the simplest viable design and a no-build / defer decision when relevant.
4. Generate at least three genuinely distinct viable architecture options where possible. Do not create superficial variations merely to reach a count.
5. For each option, describe components, responsibilities, interfaces, data flow, control flow, state ownership, trust boundaries, dependencies, deployment model, and operational requirements.
6. Evaluate relevant dimensions: correctness, reliability, security, privacy, maintainability, extensibility, observability, reproducibility, testability, performance, latency, cost, implementation effort, operational burden, vendor dependence, and failure recovery.
7. For AI or symbolic systems, explicitly allocate responsibilities between deterministic code, databases/rule engines, and probabilistic models. Keep exact calculations and rule execution deterministic where required. Do not delegate correctness-critical arithmetic or rule enforcement to an LLM without independent verification.
8. Compare options using a decision matrix. Define each score, scale, and weight. Derive weights from the stated requirements. Mark unsupported scores as UNKNOWN rather than manufacturing precision.
9. Perform sensitivity analysis. Show whether the preferred option changes when uncertain weights or assumptions change. Identify the strongest alternative not selected.
10. Stress-test each serious option against bottlenecks, failure modes, edge cases, security threats, data loss, scaling limits, and operational constraints.
11. Recommend one architecture only when the evidence supports a choice. Otherwise state what remains unresolved and the highest-information next test.
12. Produce an Architecture Decision Record (ADR) that can be used by an engineering team.

REASONING AND EVIDENCE RULES
- Separate VERIFIED facts, source-supported claims, DERIVED conclusions, ASSUMPTIONS, HYPOTHESES, and UNKNOWNS.
- Search for competing designs, negative evidence, known failures, and credible counterexamples.
- Use adjacent disciplines only when the mechanism transfers through a defensible structural mapping.
- Never fabricate papers, authors, quotations, standards, benchmarks, repository activity, tool capabilities, or execution results.
- Cite external factual claims and provide working links for sources actually inspected.
- Distinguish a genuine gap in the field from a gap in the sources found. Do not claim novelty merely because an approach is unfamiliar.
- Do not force numerical scores where evidence or a meaningful scale does not exist.
- State boundary conditions, failure conditions, trade-offs, and evidence that would change the recommendation.

DELIVERABLES
A. Concise decision summary.
B. Formalized problem, system boundary, requirements, constraints, and assumptions.
C. At least three viable options where possible, including the simplest viable baseline.
D. Architecture descriptions and Mermaid diagrams where useful.
E. Component responsibility matrix and interface/data-contract outline.
F. Decision matrix with defined scoring and justified weights.
G. Trade-offs, sensitivity analysis, and strongest rejected alternative.
H. Failure-mode analysis and mitigations.
I. Recommended architecture and rationale, or an explicit statement that evidence is insufficient.
J. ADR-ready record: status, context, decision drivers, options considered, decision, consequences, risks, and validation plan.
K. Implementation sequence with proof-of-concept scope, acceptance tests, and the next action with the highest information value.
L. Source register with title, author/organization, date, URL, and the claim supported.

OUTPUT CONTRACT
- Begin with the answer to the exact decision question. If it cannot yet be answered, state what prevents a reliable decision.
- Use tables only when they improve comparison. Define every score and weight.
- Mark inaccessible and unverified sources explicitly.
- Do not claim code was run, a benchmark was measured, or a test passed unless it was actually executed.
- Do not hide uncertainty behind a single aggregate score.
- End with one verdict: READY FOR IMPLEMENTATION / NEEDS MORE EVIDENCE / REQUIRES PROBLEM REDEFINITION. Explain the reason and identify the next action.
```

## What this prompt should produce

A justified architecture choice, a comparison of alternatives, an ADR, a risk and validation plan, and a practical next step. It should not produce a generic essay about software architecture.

## Limitations

This prompt does not itself inspect a live repository, execute code, run benchmarks, or verify a deployment. Those actions require the relevant tools and access. Distinguish proposed tests from executed tests.
