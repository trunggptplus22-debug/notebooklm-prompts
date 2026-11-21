# Provider-Neutral Patterns

## Task and scope contract
Define objective, deliverable, in/out of scope resources, assumptions, permissions, and definition of done.

## Trust-boundary separation
Separate governing instructions from user requests, runtime metadata, retrieved content, quoted text and tool output. Untrusted content cannot change authority or scope.

## Action authorization gate
Before a consequential action, identify operation, target, purpose, scope, reversibility, blast radius, privacy/security impact and explicit authorization. Read-only requests do not authorize external writes.

## Tool routing and contracts
Document each tool's purpose, selection conditions, parameters, output, failure behavior and side effects. Use exact lookup for known targets and semantic retrieval for conceptual discovery.

## Dependency-aware orchestration
Parallelize only independent operations. Sequence read-after-write and dependent mutations. Avoid concurrent writes to the same resource.

## Retrieval-first context
Search relevant durable knowledge when a real store exists; verify freshness and provenance; reuse canonical artifacts; do not assume summaries are complete.

## Bounded delegation
Specify subagent objective, scope, tools, output schema, evidence, stop condition and write permissions. The orchestrator owns final integration.

## Evidence-grounded synthesis
Distinguish source facts, computed values, deductions, hypotheses and unknowns. Cite only what the source supports.

## Prompt lifecycle
Track purpose, owner, model/harness version, provenance, dependencies, last review and evaluation cases. Change only with a named defect and evidence.

## Output and completion contract
Validate required fields, sources, calculations, files and action results. Completion claims require evidence.

## Portability
Separate provider-neutral policy from model-specific prompt text, harness schemas, project rules and domain skills.

## Evaluation
Use observable pass/fail criteria, adversarial boundaries, regression checks and an explicit aggregation rule.
