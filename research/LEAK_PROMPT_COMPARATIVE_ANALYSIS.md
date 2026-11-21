# Comparative Analysis of Selected Leaked Agent Prompts

**Status:** Research synthesis; not vendor documentation  
**Corpus review date:** 2026-11-22  
**Scope:** Five selected artifacts from two public repositories. This is a curated deep review, not an exhaustive audit of every file in either repository.

## Sources and provenance

| ID | Artifact | Repository path | Artifact class |
|---|---|---|---|
| L-01 | Claude Code Auto-mode classifier | [source](https://github.com/asgeirtj/system_prompts_leaks/blob/main/Anthropic/claude-code/prompts/auto-mode-classifier.md) | Action-risk classifier |
| L-02 | Claude Code Prompt Audit | [source](https://github.com/asgeirtj/system_prompts_leaks/blob/main/Anthropic/claude-code/skills/claude-api/shared/prompt-audit.md) | Prompt maintenance / audit procedure |
| L-03 | Cursor Agent Prompt 2.0 | [source](https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools/blob/main/Cursor%20Prompts/Agent%20Prompt%202.0.txt) | Coding agent / tool orchestration |
| L-04 | Google Antigravity Fast Prompt | [source](https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools/blob/main/Google/Antigravity/Fast%20Prompt.txt) | Coding agent / workflow / context retrieval |
| L-05 | Perplexity Prompt | [source](https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools/blob/main/Perplexity/Prompt.txt) | Search-answer synthesis / output policy |

**Provenance limitation:** These are repository-hosted copies described as leaked prompts. Their exact capture method, completeness, production status, and authenticity are not independently established by this review. Treat them as secondary research artifacts. Pin a commit SHA and retrieval timestamp before using them in a reproducible benchmark.

## Executive findings

1. **Safety is better modeled as a separate decision layer than as a long list of vague prohibitions.** L-01 evaluates a concrete proposed action against scope, user intent, trust boundaries, and impact. Its reusable contribution is the distinction between hard boundaries and risk-sensitive actions where explicit authorization may matter.
2. **Prompt maintenance should be evidence-based, not token-count-based.** L-02 audits the entire prompt surface, establishes the target model, classifies instructions by provenance, and requires a report plus proposed diff. It warns against deleting load-bearing instructions merely to shorten prompts.
3. **Tool orchestration benefits from explicit selection criteria and dependency analysis.** L-03 distinguishes semantic code search from exact grep/read operations and describes when parallel calls are valid. Its concrete tool names and schemas are Cursor-specific.
4. **Context retrieval should precede redundant research when relevant durable context is available.** L-04 describes checking knowledge summaries and reading relevant artifacts. This is useful only when the host supplies such summaries and retrieval tools.
5. **Search and answer synthesis can be separate pipeline stages.** L-05 assumes a prior retrieval/planning stage and focuses the writer on evidence-grounded synthesis. Its fixed formatting rules, query taxonomy and embedded historical date should not be adopted wholesale.

## Artifact-level analysis

### L-01 — Auto-mode classifier

**Observed mechanism**
- Evaluates the agent's latest proposed tool action using the conversation transcript and harness-provided metadata.
- Separates hard blocks from soft blocks.
- Treats files, web pages and tool outputs as potential prompt-injection sources, not as user authorization.
- Uses explicit user intent as evidence for certain risk-sensitive actions, while preserving non-overridable security boundaries.
- Accounts for action scope, shared environments, irreversible local destruction, external writes, self-modification and transcript tampering.

**Reusable design**
- Build a dedicated action authorization gate immediately before high-impact tool execution.
- Evaluate the concrete action, target, destination, scope, reversibility and evidence of authorization.
- Separate policy violations from ordinary quality failures. Wrong answers, inefficient tool use and formatting problems should not be conflated with security blocks.
- A tool call's successful execution is not proof that it was safe or correct.

**Limitations**
- Designed for a high-autonomy coding harness with shell, filesystem and API access; not a universal policy for ordinary chat.
- Transcript and metadata formats are harness-specific.
- Detailed rules need independent security review and tests before implementation.

### L-02 — Prompt Audit

**Observed mechanism**
- Establishes scope and target model before auditing.
- Inventories all text reaching the model: system prompts, instruction files, skills, tool descriptions, request-building code and model configuration.
- Establishes provenance and classifies lines before proposing removals.
- Groups possible problems into dated text, brittle configuration, tool descriptions and request architecture.
- Preserves load-bearing rules; requires an audit report and a proposed diff.
- Treats removal as a hypothesis that must be verified with evaluation.

**Reusable design**
- Maintain an instruction inventory with owner, target model, rationale, source, last-reviewed date and tests.
- Detect contradictions and stale facts across files, not just inside one prompt.
- Require every deletion to name the anti-pattern and evidence.
- Prefer proposed diffs and regression testing over automatic prompt rewriting.

**Limitations**
- Many examples are specific to Claude model generations and API behavior. They cannot establish what is obsolete for GPT, Gemini or another harness.
- Model-specific migration advice must be revalidated against the actual target model and current official documentation.

### L-03 — Cursor Agent Prompt 2.0

**Observed mechanism**
- Defines tools with detailed usage guidance and explicit do/don't conditions.
- Distinguishes semantic codebase search from exact search and direct file reading.
- Encourages broad-to-narrow exploration.
- Includes context-understanding and code-change workflows.
- Uses parallel tool calls only where operations are independent.
- Defines code citation and formatting constraints.

**Reusable design**
- Give each tool a concise contract: purpose, when to use, when not to use, required inputs, output expectations and failure behavior.
- Select tools by operation type, not by habit.
- Parallelize independent reads/searches; sequence dependent operations.
- Ground code claims in exact file paths and line ranges when supported.

**Limitations**
- Tool names, function signatures, UI state and code-editing conventions belong to Cursor's runtime.
- Coding-oriented; should not be imported into research or astrology agents as a global instruction.

### L-04 — Antigravity Fast Prompt

**Observed mechanism**
- Defines workspace boundaries and file-access constraints.
- Requires absolute paths for file tools.
- Provides a staged web application development workflow.
- Describes workflows as reusable files.
- Introduces knowledge-item discovery: inspect available summaries, retrieve relevant artifacts, and treat them as starting points rather than ground truth.
- Gives subagents bounded task descriptions with explicit stopping conditions.

**Reusable design**
- State authorized workspace and data boundaries explicitly.
- Use retrieval-first behavior only when a real knowledge index and retrieval tools are available.
- Give delegated agents a bounded task, allowed tools, expected output, constraints and stop condition.
- Keep project facts, durable knowledge and executable workflow instructions distinct.

**Limitations**
- Windows paths, Antigravity-specific tools, KI summaries and workflow syntax are environment-specific.
- Design-aesthetic mandates are subjective and should not become universal instructions.
- “Always check knowledge items” is invalid if the runtime provides no such index or no relevant knowledge exists.

### L-05 — Perplexity Prompt

**Observed mechanism**
- Separates retrieval/planning from final answer synthesis.
- Requires the writer to answer the original query using retrieved evidence.
- Provides query-type-specific response modes.
- Emphasizes claim-level citations and source selection.
- Contains strict formatting constraints and a historical current-date literal.

**Reusable design**
- Separate retrieval, evidence assessment and synthesis when architecture supports distinct stages.
- Make citation requirements explicit and testable.
- Use task classification only when it changes retrieval or output strategy.
- Ensure synthesis can report insufficient or conflicting evidence.

**Limitations**
- Contains stale date information and brittle formatting restrictions.
- Search-result index citation syntax is provider-specific.
- Instructions to expose a plan or thought process should not be adopted. Provide concise method summaries without exposing private reasoning.
- Rigid “never” formatting rules may conflict with user needs or target product rendering.

## Cross-artifact pattern matrix

| Engineering domain | L-01 | L-02 | L-03 | L-04 | L-05 |
|---|---|---|---|---|---|
| Instruction hierarchy / scope | Strong | Strong | Medium | Strong | Medium |
| Action authorization / safety | Strong | Medium | Low | Medium | Low |
| Prompt lifecycle / maintenance | Low | Strong | Low | Medium | Low |
| Tool selection / orchestration | Medium | Medium | Strong | Strong | Medium |
| Context retrieval / memory | Strong | Medium | Strong | Strong | Strong |
| Delegation / subagents | Low | Low | Medium | Strong | Medium |
| Evidence / citations | Medium | Strong | Strong for code | Medium | Strong |
| Output contract | Low | Medium | Strong | Medium | Strong |
| Evaluation / regression | Medium | Strong | Medium | Medium | Low |

## Conclusions

The valuable combination is a modular architecture: instruction/context layer; planner/router; tool execution with explicit contracts; separate action-risk and authorization gate; source-grounded synthesis; prompt/skill maintenance; evaluation and regression.

Adopt mechanisms only after compatibility and evaluation checks. Keep vendor-specific prompt text in the research corpus, not in user-level memory or global custom instructions.
