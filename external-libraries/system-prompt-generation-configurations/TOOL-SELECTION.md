# Recommended Refiner / Enhancer Stack

## Practical recommendation

For a workflow that improves existing system prompts rather than operates a full LLMOps platform, start with:

1. **System Prompt Doctor** from the upstream Daniel Rosehill collection for diagnosis.
2. **Specification-first prompt-engineering review** to extract requirements, platform constraints, protected invariants, and acceptance criteria before editing.
3. **Prompt Optimizer** for practical rewrite and variant testing.
4. **Promptfoo** for repeatable regression and acceptance checks.

The specification-first review is a workflow role, not a separate software product. Add GEPA only when there is a stable evaluator and a representative dataset. Add Phoenix or Langfuse when prompt versioning, traces, experiment records, or team workflows become necessary.

## Why not select one universal tool?

- Prompt editing and prompt optimization are different tasks.
- A language-model rewrite is not evidence of improved behavior.
- A prompt can score better on a small evaluator while violating a non-negotiable domain rule.
- Production-grade refinement needs both semantic preservation and performance measurement.

## Proposed dedicated system prompt refiner

Build a platform-neutral Agent Skill with this sequence:

**Inspect → Specify → Diagnose → Plan → Patch → Diff → Test → Compare → Accept/Reject → Version**

Required outputs:
- Original prompt snapshot
- Structured specification
- Defect report with severity and evidence
- Change plan
- Revised prompt
- Semantic diff (added/removed/modified instructions)
- Invariant-preservation report
- Test matrix and results
- Baseline-versus-candidate comparison
- Final acceptance/rejection decision
- Version changelog and rollback point

The Skill should support two modes:
- **Conservative Refine:** minimal edits, preserve all behavior not explicitly targeted.
- **Deep Enhance:** restructure, add missing modules, improve workflow and introduce validation, while preserving declared invariants.

Do not make a universal prompt optimizer by stacking many meta-prompts. Build one orchestration Skill with specialist reference modules and a fixed validation contract.
