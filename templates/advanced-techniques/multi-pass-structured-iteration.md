# Multi-Pass Research and Model Refinement

## Objective
Iteratively transform a problem statement into a tested, implementation-ready model without skipping uncertainty or verification.

## Inputs
- Problem: [INSERT]
- Current model / solution: [INSERT OR NONE]
- Data, sources, code: [INSERT OR NONE]
- Constraints: [INSERT]

## Pass 1 — Formalize
Lock the object, scope, terminology, assumptions, inputs, outputs, and success criteria. Separate facts, deductions, hypotheses, and unknowns.

## Pass 2 — Decompose
Identify entities, variables, states, relations, transformations, dependencies, invariants, constraints, and boundary conditions. Represent the structure in a table or graph where useful.

## Pass 3 — Generate Alternatives
Develop at least three materially different approaches when feasible: rule-based, mathematical/formal, and computational or hybrid. Explain the mechanism and trade-offs of each.

## Pass 4 — Attack
Search for contradictions, counterexamples, edge cases, hidden assumptions, non-termination, data leakage, and unsupported parameters. Identify what would falsify each approach.

## Pass 5 — Select and Specify
Choose the best-supported option under explicit criteria. Specify algorithm steps, data contracts, exceptions, tests, and observable acceptance criteria.

## Final Output
Provide a concise decision record, unresolved risks, and the smallest decisive next experiment. Do not repeat unchanged findings between passes.