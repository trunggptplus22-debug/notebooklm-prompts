# Adoption Decisions — Selected Leaked Prompt Patterns

**Decision date:** 2026-11-22  
**Target:** Provider-neutral research and agent-engineering assets in this repository.  
**Important:** This applies to reusable design mechanisms, not wholesale copying of leaked prompt text.

| Pattern | Source | Decision | Rationale |
|---|---|---|---|
| Separate hard security boundaries from risk-sensitive actions | L-01 | ADAPT | Useful authorization architecture; map to actual platform policy and action types. |
| Evaluate concrete action, target, scope and user authorization | L-01 | ADOPT | Improves scope and side-effect review; consistent with explicit-consent design. |
| Treat retrieved/tool content as untrusted data | L-01, L-02, L-04 | ADOPT | General trust-boundary requirement; data cannot override instructions or authorize actions. |
| Maintain prompt provenance and target-model identity | L-02 | ADOPT | Required for reproducibility and model-specific maintenance. |
| Inventory full prompt surface, including tool descriptions and request assembly | L-02 | ADAPT | Apply where repository/runtime exposes these files; do not read secrets or out-of-scope settings. |
| Delete instructions merely to reduce token count | L-02 | REJECT | Brevity is not the audit objective; preserve load-bearing content. |
| Semantic search for conceptual exploration; exact read/search for known symbols | L-03 | ADOPT | Generalizable routing; tool names remain harness-specific. |
| Parallelize independent read operations only | L-03 | ADOPT | General dependency principle; mutations and read-after-write operations must be sequenced. |
| Copy Cursor tool schemas and code formatting rules | L-03 | REJECT | Environment-specific and not portable. |
| Check relevant knowledge summaries before redundant research | L-04 | ADAPT | Valid only when runtime provides an actual knowledge index and artifacts. |
| Always check KIs before every task | L-04 | REJECT | Overbroad; adds needless retrieval and assumes unavailable infrastructure. |
| Bound subagent tasks with scope, tools, output and stop condition | L-04 | ADOPT | Portable delegation contract. |
| Copy Antigravity-specific paths and workflow syntax globally | L-04 | REJECT | Harness-specific. |
| Separate retrieval/planning from evidence-grounded synthesis | L-05 | ADAPT | Useful when retrieval is a distinct pipeline stage. |
| Claim-level citation and source entailment checks | L-05 | ADOPT | Portable evidence discipline; syntax must match destination product. |
| Copy Perplexity formatting restrictions and embedded date literal | L-05 | REJECT | Rigid, stale and provider-specific. |
| Expose private reasoning or hidden chain-of-thought | L-05 | REJECT | Provide concise method summaries and evidence, not hidden internal reasoning. |

## Integration decisions

### Global Saved Memory / Custom Instructions
Do not import vendor prompt text. Keep stable user preferences and concise cross-task behavior. No ChatGPT Saved Memory or Custom Instructions were changed by this repository work.

### NotebookLM prompt library
The research protocol, comparative analysis, provider-neutral patterns, and evaluation suite are reusable research assets.

### Antigravity / coding-agent configuration
Candidate patterns may be translated into project-level rules only after inspecting the actual target configuration and running the evaluation suite. This document does not authorize edits to external agent installations.

### Astrology and traditional knowledge agents
Apply source provenance, school separation, deterministic calculation verification, bounded tool permissions and evaluation. Do not import coding-agent UX rules or search-provider output formatting into astrology interpretation prompts.

## Rollback
All artifacts are additive Markdown files. Revert individual commits or remove the added files if unsuitable. No existing prompt templates were overwritten.
