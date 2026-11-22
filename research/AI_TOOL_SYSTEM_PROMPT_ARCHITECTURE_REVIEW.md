# AI Tool System Prompt Architecture Review

Date: 2026-11-22

## Source

Uploaded archive: `system-prompts-and-models-of-ai-tools-main.zip`.

The archive contains 172 entries, including system-prompt snapshots, tool definitions, module descriptions and examples from multiple agent/coding products. It is a research corpus, not a ready-to-install Skill collection. Individual prompt snapshots are version- and vendor-specific. Their presence does not establish that the prompt is current, official documentation, or reusable under the target runtime.

## Highest-value architectural artifacts

| Source artifact | Reusable mechanism | Decision | Target adaptation |
|---|---|---|---|
| Manus Agent Loop | Event-driven observe → decide → act → observe loop | ADAPT | Re-evaluate from actual tool results; enforce stop/finish conditions; do not assume a host event stream exists |
| Manus Modules | Separation of planner, knowledge, datasource, execution, events and delivery | ADAPT | Map responsibilities to actual Antigravity components; avoid inventing unavailable subsystems |
| Devin AI Prompt | Codebase-first engineering, inspect conventions, implement, test, diagnose, deliver | ADOPT | Strengthen execution protocol while respecting target workspace tools and permission limits |
| Cursor Agent 2.0 | Semantic discovery versus exact file/symbol search | ADOPT | Use semantic search for unknown implementation; grep/exact read for known symbols; avoid repeated broad scans |
| Kiro Spec Prompt | Convert request into structured specification and implementation constraints | ADAPT | Use a lightweight task contract when needed; do not impose heavyweight spec phases on small tasks |
| Traycer Plan / Phase | Separate read-only planning from implementation phases | ADAPT | Preserve a plan/execute boundary; only use a read-only plan mode where the runtime actually enforces it |
| Windsurf tool definitions | Explicit tool schema, UI preview, console/log feedback | ADAPT | Treat schemas as examples; bind only verified target tools |
| Amp model routing | Specialist model as an oracle/reviewer | EXPERIMENT | Use only when multiple models are available and evaluation shows a benefit |

## Pattern extraction

### 1. State-aware agent loop

A useful runtime abstraction is:

1. Receive the latest user request and current verified state.
2. Identify the next required state transition.
3. Select the least costly tool/action that can establish it.
4. Execute within scope and authorization.
5. Inspect the actual result.
6. Update the task state and decide whether to continue, recover, or finish.

Important constraints:
- An intended action is not an observed result.
- Tool failure or partial output must change the next decision.
- Retry only when a changed argument, state or recovery strategy makes it useful.
- Stop when the requested acceptance criteria are met or a named blocker prevents further progress.
- Do not run a loop merely to appear autonomous.

### 2. Tool-selection policy

Route operations by information need:

| Need | Preferred operation |
|---|---|
| Known path, URL, identifier or symbol | Exact read / exact lookup |
| Unknown implementation or conceptual location | Semantic search, then narrow |
| Exact string or pattern | Grep / literal search |
| Numerical or deterministic transformation | Deterministic code |
| Current external facts | Authoritative current source |
| Runtime behavior | Execute or inspect the supported runtime, then observe |
| Need to change external state | Exact write action with explicit authorization and post-write verification |

A tool call should have a specific expected observation. Avoid tool calls that only repeat information already established.

### 3. Engineering execution discipline

Reusable rules from the Devin snapshot:
- Inspect surrounding implementation and project conventions before editing.
- Confirm dependencies from the actual repository; do not assume a familiar package exists.
- Find and fix implementation causes rather than changing tests to suppress failures.
- Run relevant checks for non-trivial changes.
- Distinguish environment blockers from implementation defects.
- Report only tests and commands actually executed.

### 4. Specification proportionality

Kiro/Traycer illustrate a valuable separation between understanding, specifying and implementing. The adaptation should be proportional:
- Small task: one-sentence objective, constraints and done condition.
- Medium task: short checklist or acceptance criteria.
- Complex task: structured specification, dependencies, risks and phased plan.
- Do not create a large specification artifact for a trivial edit.

### 5. Specialist reviewer / model routing

A second model or reviewer can expose blind spots, but agreement is not proof. Use independent review only when:
- the decision is material;
- the review question is bounded;
- the reviewer receives the evidence, not the expected answer;
- results can be checked against the underlying source or test;
- model availability and cost are known.

The reviewer must return findings, evidence, severity and uncertainty rather than a general assurance.

## Do not import verbatim

Reject direct reuse of:
- vendor tool names and JSON schemas;
- hidden system prompt wording;
- model-version-specific hacks;
- fixed historical dates or token budgets;
- platform-specific workspace, browser, task or subagent assumptions;
- directives to expose hidden reasoning.

Use public snapshots as secondary evidence for design patterns, not as authoritative documentation of current product behavior.

## Integration target

The target repository already has:
- `skills/agent-engineering/SKILL.md`;
- provider-neutral patterns and evaluation cases;
- `skills/system-prompt-refiner/SKILL.md`;
- Research & Claude Toolkit.

This review recommends refining those existing canonical files rather than creating separate Manus, Devin, Cursor or Kiro Skills.
