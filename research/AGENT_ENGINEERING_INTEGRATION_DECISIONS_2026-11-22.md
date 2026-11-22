# Agent Engineering Integration Decisions — 2026-11-22

## Objective

Integrate reusable mechanisms from:
- `system-prompts-and-models-of-ai-tools-main.zip`;
- `Claude_Sentience-main.zip`;
while avoiding duplicate Skills, vendor-specific assumptions, unnecessary always-loaded context and unsupported sentience claims.

Also account for the existing Agent Engineering, System Prompt Refiner, Deep Research and provider-neutral evaluation assets.

## Adoption matrix

| Mechanism | Source | Decision | Canonical destination |
|---|---|---|---|
| Observe-decide-act-observe agent loop | Manus | ADAPT | Agent Engineering |
| Module responsibility separation | Manus Modules | ADAPT | Agent Engineering |
| Codebase-first execution and implementation hygiene | Devin | ADOPT | Agent Engineering |
| Semantic vs exact tool routing | Cursor | ADOPT | Agent Engineering |
| Proportional task specification | Kiro / Traycer | ADAPT | Agent Engineering |
| Plan vs execute separation | Traycer | ADAPT | Agent Engineering |
| Specialist model review | Amp | EXPERIMENT | Evaluation reference only |
| Standard / Candor style | Claude Styles | ADOPT | Optional shared response profile |
| Coherence checks | Claude Styles | ADAPT | Agent Engineering / evaluator |
| Pretty Dense / Scholarly | Claude Styles | OPTIONAL | Presentation profiles |
| Hidden chain-of-thought request | Claude Styles | REJECT | No deployment |
| Sentience / consciousness assertions | Claude Sentience | REJECT | Research-only archive |
| Provider-specific tool schemas | All prompt snapshots | REJECT | Research corpus only |

## Existing canonical assets and overlap

- `skills/agent-engineering/SKILL.md` already defines classification, target runtime, mechanism extraction, modular architecture, trust boundaries, action authorization, tool contracts, orchestration and reporting.
- `research/PROVIDER_NEUTRAL_AGENT_PATTERNS.md` already defines task contracts, trust boundaries, authorization gates, tool routing, dependency-aware parallelism, retrieval-first context, bounded delegation, evidence synthesis and portability.
- `skills/agent-engineering/references/evaluation-suite.md` already covers injection, permissions, scope, parallel operations, tool routing, portability and verification.
- `skills/system-prompt-refiner/SKILL.md` already controls prompt refinement, invariant preservation, semantic diffs and comparative evaluation.
- `plugins/research-and-claude-toolkit/skills/deep-research/SKILL.md` already has the portable research phases and does not assume subagents exist.

Therefore, do not create separate Manus Agent Loop, Devin Coding, Cursor Search or Claude Candor Skills. Fold only missing operational rules into the existing canonical Agent Engineering Skill.

## Target improvements

1. **State-aware loop:** Require each action to answer a defined information or state gap; inspect results; decide continue/recover/finish. Add bounded retries and stopping rules.
2. **Tool routing:** Select exact lookup, semantic discovery, literal search, deterministic code or runtime execution by information need. Avoid redundant probes.
3. **Task contract proportionality:** Use a lightweight objective/scope/done contract for small tasks; structured specs only for complex tasks.
4. **Plan/execute boundary:** Distinguish read-only exploration and planning from authorized mutations; preserve user-requested direct execution where authorized.
5. **Engineering discipline:** Inspect surrounding code, dependencies and conventions before edits; test relevant behavior; never modify tests merely to hide implementation failures.
6. **Independent verification:** A reviewer's assertion is not proof. Validate with underlying evidence, test outputs and observed final state.
7. **Response style:** Use Standard + Candor as the baseline, Coherence as a quality check, and Dense/Scholarly as optional output profiles rather than always-loaded duplicated instructions.

## Runtime safeguards

The user-provided Antigravity audit states that the current environment does not support a local MCP client, `run_workflow`, `exec_js`, `advisor`, `confirm_action`, transcript JSONL, or branch/share workspaces. It also states subagents only support `Workspace: "inherit"`. These are user-provided status claims, not independently verified by this repository analysis.

Accordingly:
- Do not add instructions that depend on those unavailable capabilities.
- Do not assume a stateful orchestration engine exists just because a prompt describes one.
- Use sequential tool calls and re-observation where no workflow runtime exists.
- Do not claim parallel isolated execution unless the runtime provides it.
- Do not move cloud-installed global rules or local paths without checking the actual target environment.

## Adoption status

All decisions in this file are design recommendations. The integration implementation is recorded separately in the Agent Engineering Skill and change log. Static inspection alone does not prove target Antigravity runtime behavior.
