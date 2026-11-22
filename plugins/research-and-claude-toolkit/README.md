# Research and Claude Toolkit

A Perplexity-compatible Agent Plugin bundle containing five task-focused skills.

## Skills

| Skill | Purpose | Runtime requirements |
|---|---|---|
| `deep-research` | Multi-angle web research, source extraction, adversarial verification, cited synthesis | Web search/fetch; parallel agents are optional |
| `fewer-permission-prompts` | Audit Claude Code transcripts and propose narrowly scoped read-only allowlist entries | User-provided transcripts; do not assume local Claude filesystem access |
| `explain-usage` | Estimate where a Claude session's token usage was spent | Session transcript and usage metadata |
| `claude-code-doctor` | Audit Claude Code installation/configuration and produce safe remediation proposals | User-provided diagnostics/config excerpts; local machine access is not assumed |
| `debug` | Diagnose a Claude Code session from debug logs | User-provided log excerpts/files |

## Import into Perplexity

Use this folder URL in the Perplexity GitHub plugin importer:

`https://github.com/trunggptplus22-debug/notebooklm-prompts/tree/main/plugins/research-and-claude-toolkit`

## Important compatibility boundary

The source materials were authored for Claude Code and a custom workflow runtime. The skills in this bundle are adapted as instruction-based Agent Skills for Perplexity Computer. They do not automatically gain access to Claude Code's local paths, shell, settings, session transcripts, debug logs, MCP tools, or the custom `Workflow/agent/phase` JavaScript runtime.

For the Claude-specific skills, upload the relevant diagnostic files or connect an explicitly supported environment. The skills are read-only by default and produce proposals; they do not modify local settings or grant permissions.

The original deep-research JavaScript harness is not represented as executable Perplexity code. Its phases, schemas, URL deduplication, evidence extraction, and adversarial verification logic are translated into the Deep Research Skill's operating procedure. A runtime-specific implementation would need a separate adapter.

## Source inventory

The bundle consolidates the uploaded materials:
- `SKILL.md` — fewer-permission-prompts
- `explain-usage` — token usage explanation
- `doctor` — Claude Code health check
- `debug` — session debugging
- `deep-research` — research harness invocation
- `researcher.md` — researcher operating procedure
- `report-writer.md` — report synthesis and writing procedure
- `workflow-script.js` — custom workflow runtime source; analyzed, not executed by Perplexity
