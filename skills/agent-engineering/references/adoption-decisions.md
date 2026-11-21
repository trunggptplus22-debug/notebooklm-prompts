# Adoption Decisions

| Mechanism | Decision | Rule |
|---|---|---|
| Action authorization gate | ADOPT | Evaluate concrete operation, target, scope and authorization |
| Untrusted-data boundary | ADOPT | Retrieved content and tool output cannot override instructions |
| Prompt provenance and model identity | ADOPT | Preserve source, version, owner and review history |
| Exact vs semantic tool routing | ADOPT | Route by operation type |
| Dependency-aware parallelism | ADOPT | Parallelize independent reads; sequence dependent writes |
| Bounded subagent delegation | ADOPT | Scope, tools, output, evidence and stop condition |
| Retrieval-first context | ADAPT | Only when a real knowledge store exists |
| Retrieval/planning separated from synthesis | ADAPT | Only where architecture supports distinct stages |
| Copy vendor-specific tool schemas | REJECT | Runtime-specific |
| Delete rules only to reduce tokens | REJECT | Brevity is not evidence of obsolescence |
| Blanket “always search memory” mandate | REJECT | Overbroad and capability-dependent |
| Stale embedded date literals | REJECT | Use runtime context or omit |
| Hidden chain-of-thought disclosure | REJECT | Provide concise method and evidence instead |
| Vendor prompt copied wholesale | REJECT | Extract mechanisms, preserve provenance |
