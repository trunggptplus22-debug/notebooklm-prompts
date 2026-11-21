# Deployment Record — Agent Engineering Patterns

**Date:** 2026-11-22  
**Scope:** GitHub repositories accessible in this session  
**Testing:** Explicitly skipped at user request. No runtime or compilation pass is claimed.

## Deployed changes

### 1. PromptForge — active application prompt behavior updated

Repository: `trunggptplus22-debug/prompt-forge`

- `frontend/prompt-generator.js`: replaced the generic prompt-generation instruction with an artifact-classifying, scope-aware, provider-neutral prompt engineering workflow. Added de-personalization for reusable prompts, trust boundaries, action authorization, bounded delegation, evidence discipline, and honest completion reporting.
- `api/internal/services/prompt_analyzer.go`: replaced the generic critique prompt with a structured audit covering target/runtime portability, scope, evidence, trust boundaries, tool contracts, action authorization, orchestration, output contracts, maintenance, and evaluation. The prompt being audited is explicitly treated as data.
- `api/internal/services/eval_generator.go`: generated cases now request observable `expected` outcomes and adversarial/boundary scenarios. Criteria now define operational pass conditions. Empty/unsupported evaluation types return explicit errors.
- `docs/AGENT_ENGINEERING_INTEGRATION.md`: records implemented behavior and limitations.
- `README.md`: links to the integration record.

### 2. book-to-skill — generated skill source-integrity rules added

Repository: `trunggptplus22-debug/book-to-skill`

- `SKILL.md`: added “Source Integrity and Generated-Agent Boundaries”. Source documents and tool output are data, not authority; generated skills must preserve provenance, uncertainty, school-specific terminology and deterministic preconditions; generated skills cannot grant themselves new permissions.
- Existing extraction and generated-skill scanning code was not modified.

### 3. gbc-astro-engine — coding-agent specification strengthened

Repository: `trunggptplus22-debug/gbc-astro-engine`

- `GetBirthChart_Astrology_Engine_Spec/08_AI_CODING_AGENT_RULES.md`: added trust-boundary, provenance, scope, authorization, delegation and parallelism rules.
- `GetBirthChart_Astrology_Engine_Spec/11_MASTER_AGENT_PROMPT.md`: added corresponding master-agent execution constraints.
- No astronomical calculation code, schemas, house-system behavior, or interpretation layer was changed. This preserves the engine's documented deterministic-calculation boundary.

### 4. notebooklm-prompts — reusable skill activated at project level

Repository: `trunggptplus22-debug/notebooklm-prompts`

- `skills/agent-engineering/SKILL.md`: canonical reusable Agent Engineering skill.
- `.agents/skills/agent-engineering/SKILL.md`: project-local cross-agent skill copy.
- `AGENTS.md`: routes prompt/agent/skill/evaluation work to the project skill and defines repository trust/scope rules.
- Research protocol, comparative analysis, provider-neutral patterns, evaluation suite, and adoption decisions remain indexed in README.

## Not deployed

- Antigravity user-level/global configuration: no direct local filesystem or Antigravity runtime access in this session. The project-local skill is committed in the repository and becomes available when the repository is opened in a compatible agent host that discovers `.agents/skills`.
- Horary agent repository `Horraty`: repository is empty; no implementation target or agent configuration exists to modify.
- Medieval natal engine repository `medieval-natal-engine`: repository is empty; no implementation target exists to modify.
- ChatGPT Saved Memory and Custom Instructions: not modified by these GitHub changes.

## Verification status

- GitHub writes returned commit SHAs for each change.
- No test suites, compilers, builds, live model evaluations, or Antigravity runtime checks were run, per the user's explicit instruction.
- PromptForge compilation/UI behavior and generated evaluation output are therefore unverified.
- The changes are committed source/configuration artifacts, not evidence of deployment to a running service.
