# Hybrid System Architecture Decision Analysis

## Objective
Evaluate architectures for a research or computational engine, including LLM–deterministic hybrid designs.

## Inputs
- System objective: [INSERT]
- Functional requirements: [INSERT]
- Data and rule characteristics: [INSERT]
- Runtime / deployment constraints: [INSERT]
- Candidate architectures: [INSERT OR GENERATE]

## Analysis Dimensions
Assess module boundaries, data contracts, state ownership, deterministic versus probabilistic responsibilities, rule execution, provenance, validation, error handling, observability, reproducibility, versioning, extensibility, latency, cost, and testability.

For symbolic domains, preserve doctrine-specific rules as explicit versioned rule sets. Keep astronomical or numeric calculations deterministic where exact computation is required. Use LLMs for interpretation, research synthesis, explanation, and controlled orchestration—not as an unverified calculator.

## Deliverables
- Context and component diagrams in Mermaid where useful.
- Responsibility matrix for each module.
- Data-flow and control-flow description.
- Interface and schema proposals.
- Trade-off matrix with evidence and assumptions.
- Failure modes and mitigations.
- Architecture decision record with rejected alternatives.
- Proof-of-concept plan and acceptance tests.

Do not claim an architecture is scalable or reliable without specifying how that claim will be tested.