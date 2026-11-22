# System Prompt Refiner / Enhancer — Tool Landscape

Assessment date: 2026-11-21

Purpose: identify tools that can diagnose, rewrite, adapt, optimize, test, and manage system prompts. This is a capability map, not an endorsement of every tool.

## A. Direct prompt editing and iteration

### 1. Prompt Optimizer
- Repository: https://github.com/linshenkx/prompt-optimizer
- Online: https://prompt.always200.com
- Type: web / desktop / browser extension / Docker / MCP-enabled prompt optimization workspace.
- Useful capabilities: iterative prompt optimization, system/user prompt modes, variable templates, compare-evaluation, multiple model providers, prompt assets/version history, multi-turn and tool-call tests.
- Best use: hands-on rewrite, inspect alternatives and compare outputs across models.
- Limitation: an optimizer can improve surface structure but does not inherently know which domain rules are immutable. Add a protected-specification step and test cases.

### 2. Arize Phoenix Prompt Playground
- Repository: https://github.com/Arize-ai/phoenix
- Prompt Playground docs: https://arize.com/docs/phoenix/prompt-engineering/overview-prompts/prompt-playground
- Core skill source: https://github.com/Arize-ai/phoenix/blob/main/src/phoenix/server/agents/prompts/skills/playground/SKILL.md
- Type: open-source LLM engineering platform with a prompt IDE.
- Useful capabilities: create/edit/run prompt variants, compare prompt and model settings, template variables, tools/function definitions, repeated runs, dataset-backed experiments, tracing and versioned prompt management.
- Best use: structured prompt refinement with qualitative iteration and dataset-based comparison.
- Important finding: Phoenix separates manual editing from dataset-backed experiments. A single manual output is qualitative feedback; dataset runs with evaluators provide stronger evidence.
- Limitation: heavier platform than a stand-alone prompt editor; requires deployment and model/provider configuration.

## B. Automatic prompt optimization

### 3. GEPA / optimize_anything
- Repository: https://github.com/gepa-ai/gepa
- Agent Skill: https://github.com/gepa-ai/gepa/tree/main/.claude/skills/gepa-optimize-anything
- Type: reflective evolutionary optimization framework.
- Useful capabilities: propose candidate prompt revisions from execution traces and evaluator feedback; Pareto-aware selection; support prompt text, agent scaffolds, code, configs and other text artifacts.
- Best use: optimize prompts with measurable quality signals and held-out validation.
- Limitation: evaluator quality is critical; API/model execution can incur cost. Require bounded budgets, protected invariants and an independent test set.

### 4. DSPy
- Repository: https://github.com/stanfordnlp/dspy
- Type: declarative programming framework for modular LM systems and optimizers.
- Useful capabilities: represent tasks as modules/signatures, compose pipelines and optimize instructions/demonstrations/programs using optimizers including GEPA.
- Best use: when prompt is part of a repeatable multi-stage LLM pipeline, not just a standalone text artifact.
- Limitation: requires Python and an engineering/evaluation harness.

### 5. Microsoft PromptWizard
- Repository: https://github.com/microsoft/PromptWizard
- Type: task-aware prompt optimization framework.
- Useful capabilities: feedback-driven critique/refinement of instructions, generation and optimization of few-shot examples, support for dataset-driven scenarios.
- Best use: learning the joint optimization of instructions and examples.
- Limitation: code-oriented setup and benchmark/data requirements; validate project maintenance and dependency compatibility before adopting.

## C. Evaluation and regression testing

### 6. Promptfoo
- Repository: https://github.com/promptfoo/promptfoo
- Type: CLI/library for LLM evaluation and red-teaming.
- Useful capabilities: compare prompt/model combinations, run evaluation suites, check regressions and security weaknesses, automate checks.
- Best use: acceptance tests and regression gates for generated/refined prompts.
- Limitation: testing layer, not the primary prompt generator.

### 7. Anthropic Skill Creator
- Repository: https://github.com/anthropics/skills/tree/main/skills/skill-creator
- Type: Agent Skill for creating and improving skills.
- Useful capabilities: test prompts, run with-skill and baseline variants, quantitatively grade assertions, compare quality/time/token usage, inspect human feedback, iterate on skill design.
- Best use: engineering a prompt generator/refiner as a reusable Skill and checking whether it improves task performance.
- Limitation: workflow examples are Claude Code/subagent-oriented; adapt to the target runtime rather than copying environment assumptions.

## D. Prompt and skill lifecycle management

### 8. Langfuse
- Repository: https://github.com/langfuse/langfuse
- Type: LLM observability and prompt/skill management platform.
- Useful capabilities: prompt versioning, playground, traces, evaluations, datasets/experiments; Skill Management is beta in the inspected README.
- Best use: storing prompt versions and tracing which version produced which outcome.
- Limitation: lifecycle management and observability, not an autonomous system prompt doctor.

### 9. Agenta
- Repository: https://github.com/Agenta-AI/agenta
- Type: open-source LLMOps platform.
- Useful capabilities: playground, model comparison, human evaluation, LLM-as-judge, prompt management and traces.
- Best use: collaborative prompt iteration and review.
- Limitation: evaluate deployment overhead and workflow fit; not a specialized meta-prompt editor.

## Recommended selection

| Need | Primary choice | Supporting tool |
|---|---|---|
| Diagnose and improve a single system prompt | Upstream System Prompt Doctor + Prompt Engineering Expert | Prompt Optimizer |
| Make controlled changes without breaking original behavior | Feature Editor / Forker | Invariant specification + diff review |
| Optimize by measured task performance | GEPA | DSPy or custom evaluator |
| Test prompt variants on datasets | Phoenix Playground | Promptfoo |
| Engineer reusable prompt/agent Skills | Anthropic Skill Creator | GEPA |
| Track versions and production traces | Langfuse | Phoenix |

## Recommended workflow for reliable prompt enhancement

1. Preserve an immutable copy of the original prompt and record its source/version.
2. Extract a specification: intended behavior, mandatory rules, forbidden changes, inputs, outputs, tool permissions, domain axioms, acceptance criteria.
3. Run a diagnostic review and produce a defect list before rewriting.
4. Classify every proposed change as bug fix, clarification, feature addition, structural refactor, or optional optimization.
5. Generate a revised candidate and a semantic diff, explicitly showing what changed and why.
6. Build tests that cover normal, edge, adversarial, ambiguous, and missing-information cases.
7. Compare original and revised prompts on the same tests/model/settings; use repeated runs for nondeterministic behavior.
8. For systematic optimization, split data into train/validation/test. Never select a winner on the same examples used to generate it.
9. Reject any candidate that violates protected invariants, even if its aggregate score improves.
10. Save as a new version only after acceptance; keep rollback and test results.

## Protected-invariant policy

The refiner must not silently:
- Change a domain's axioms, definitions, calculation rules, source hierarchy or school-specific doctrine.
- Remove uncertainty, provenance or evidence requirements.
- Invent tools, permissions, APIs, data schemas or runtime capabilities.
- Change safety boundaries, privacy constraints or authorization requirements.
- Trade correctness for style, concision, or a higher judge score.
- Rewrite the entire prompt when a localized patch is sufficient.

Treat the evaluator as a potentially imperfect measuring instrument. Combine deterministic assertions, source-grounded checks, domain-expert review and task-level outcome tests.
