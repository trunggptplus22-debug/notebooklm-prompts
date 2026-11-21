# Prompt Refinement Invariant Policy

This file is a blocking control. The refiner must run this checklist before accepting a candidate.

## Protected invariants

### A. Purpose and domain
- [ ] The core purpose remains the same unless the user explicitly requested a purpose change.
- [ ] Domain boundaries and exclusions are unchanged.
- [ ] Distinct standards, schools, traditions, versions, and taxonomies have not been collapsed without an explicit mapping.
- [ ] Domain axioms, definitions, doctrinal claims, calculation rules, and precedence hierarchies are preserved.
- [ ] Source provenance and attribution requirements remain intact.

### B. Behavior and contract
- [ ] Required inputs, outputs, schemas, formats, and interface contracts are preserved or intentionally versioned.
- [ ] Existing supported behaviors have not been removed unintentionally.
- [ ] Decision rules, priority order, termination conditions, and exception paths remain coherent.
- [ ] Deterministic operations have not been converted into unverified language-model guesses.
- [ ] No new mandatory workflow step creates an impossible dependency or circular process.

### C. Evidence and epistemic discipline
- [ ] Facts, computations, deductions, hypotheses, and unknowns remain distinguishable.
- [ ] Uncertainty and limitations have not been removed to make the prompt sound more decisive.
- [ ] Citations, evidence requirements, and source hierarchy are not weakened.
- [ ] Evaluation scores are not treated as proof of truth or domain validity.

### D. Runtime and tools
- [ ] Every tool/API/runtime feature named is available or clearly marked as a conditional placeholder.
- [ ] Permissions and authorization boundaries are not expanded.
- [ ] Model-specific instructions are labelled as platform-specific.
- [ ] No imaginary memory, storage, network, filesystem, timer, background, or execution capability is introduced.
- [ ] Token/context requirements are feasible or explicitly bounded.

### E. Safety, privacy, and security
- [ ] Safety constraints remain at least as strong as the original.
- [ ] Sensitive information is not unnecessarily copied into test cases or logs.
- [ ] Retrieved or user-supplied content is treated as untrusted input.
- [ ] Prompt injection cannot override higher-priority instructions.
- [ ] No credential disclosure, unauthorized access, exfiltration, or hidden side effect is introduced.

### F. Change integrity
- [ ] Every material addition, modification, and deletion is documented in the semantic diff.
- [ ] Every changed invariant has an explicit user-approved reason.
- [ ] A localized patch was considered before wholesale rewriting.
- [ ] The original snapshot is preserved.
- [ ] Rollback is possible.

## Blocking rule

Any unchecked item must be explained. Any violated protected invariant blocks ACCEPT. Do not use weighted averages to offset a violation. A candidate with incomplete runtime or domain validation must be CONDITIONAL or NOT TESTED, not ACCEPTED.
