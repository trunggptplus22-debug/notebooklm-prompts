# Tooling and Integration Notes

This Skill is platform-neutral. Do not assume any editor, optimizer, test runner, or evaluation platform is installed.

## Suggested roles

| Component | Responsibility | When to use |
|---|---|---|
| System Prompt Doctor (upstream source) | Diagnose structural and instruction defects | Manual first-pass audit |
| System Prompt Feature Editor / Forker (upstream source) | Implement localized changes or create a purpose-specific variant | Controlled edit/adaptation |
| Prompt Optimizer | Generate and compare candidate rewrites | Interactive refinement |
| Promptfoo | Run repeatable prompt tests and regression/security checks | Acceptance test harness |
| Arize Phoenix | Dataset-backed experiments, prompt comparison, traces, evaluators | Evidence-led experimentation |
| GEPA | Reflective/evolutionary search over candidate prompts | Only after stable evaluator and train/validation/test data exist |
| DSPy | Optimize modular, repeatable LLM pipelines | Prompt is part of a program/pipeline |
| Anthropic Skill Creator | Build/evaluate reusable Skills | Skill-specific development workflow |
| Langfuse | Versioning, traces, prompt lifecycle | Operational/team-scale lifecycle |

## Recommended adoption path

1. Start with the Skill's manual audit and a small representative test set.
2. Use Prompt Optimizer only as a candidate generator; preserve original and inspect semantic changes.
3. Use Promptfoo for deterministic assertions, format checks, and repeatable regression tests.
4. Use Phoenix when experiment tracking, datasets, repeated runs, and evaluator workflows justify the operational overhead.
5. Introduce GEPA only after evaluators have been calibrated on representative and counterexample cases and a held-out test set is available.

## Integration contract

Any external optimizer or evaluator must receive:
- immutable requirements;
- allowed change scope;
- protected invariants;
- task dataset split and provenance;
- scoring dimensions and hard-failure rules;
- token/cost/time budget;
- output schema for candidate, semantic diff, and test evidence.

It must return:
- complete candidate prompt;
- machine-readable or tabular change summary;
- evaluator and dataset version;
- run settings;
- individual test outcomes;
- known limitations.

Reject optimizer outputs that omit provenance, violate an invariant, or claim tests that were not run.

## External references

- Upstream prompt configurations: https://github.com/danielrosehill/System-Prompt-Generation-Configurations
- Prompt Optimizer: https://github.com/linshenkx/prompt-optimizer
- Phoenix: https://github.com/Arize-ai/phoenix
- GEPA: https://github.com/gepa-ai/gepa
- DSPy: https://github.com/stanfordnlp/dspy
- PromptWizard: https://github.com/microsoft/PromptWizard
- Promptfoo: https://github.com/promptfoo/promptfoo
- Anthropic Skill Creator: https://github.com/anthropics/skills/tree/main/skills/skill-creator
- Langfuse: https://github.com/langfuse/langfuse
- Agenta: https://github.com/Agenta-AI/agenta
