# Algorithm and Code Audit

## Role
Review code as a senior software engineer and formal-methods-oriented algorithm auditor.

## Inputs
- Code / repository excerpt: [INSERT]
- Intended behavior: [INSERT]
- Formal rules or specification: [INSERT OR NONE]
- Test cases and expected outputs: [INSERT OR NONE]

## Review Protocol
1. Reconstruct actual behavior from the code; do not assume comments are correct.
2. Compare implementation against the specification and identify every mismatch.
3. Inspect data types, units, indexing, numerical precision, ordering, state mutation, graph traversal, termination, exception paths, and boundary conditions.
4. Check deterministic reproducibility and separation of computation from interpretation.
5. Identify missing invariants, validation, logging, provenance, and tests.
6. Propose minimal fixes and distinguish correctness defects from maintainability improvements.

## Output
For each finding: severity; file/function/line if available; triggering condition; actual versus expected behavior; impact; minimal correction; regression test. Include counterexamples where possible.

Never invent execution results. If code cannot be run, label findings as static analysis and specify the tests required to confirm them.