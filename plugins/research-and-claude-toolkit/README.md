# Research and Claude Toolkit

A Perplexity-compatible Agent Plugin bundle containing three task-focused skills.

## Skills

| Skill | Purpose | Runtime requirements |
|---|---|---|
| `deep-research` | Multi-angle web research, source extraction, adversarial verification, cited synthesis | Web search/fetch; parallel agents are optional |
| `claude-code-doctor` | Audit Claude Code installation/configuration and produce safe remediation proposals | User-provided diagnostics/config excerpts; local machine access is not assumed |
| `debug` | Diagnose a Claude Code session from debug logs | User-provided log excerpts/files |

## Import into Perplexity

`https://github.com/trunggptplus22-debug/notebooklm-prompts/tree/main/plugins/research-and-claude-toolkit`

## Compatibility boundary

The source materials were authored for Claude Code and a custom workflow runtime. The skills in this bundle are adapted as instruction-based Agent Skills for Perplexity. They do not automatically gain access to Claude Code's local paths, shell, settings, session transcripts, debug logs, MCP tools, or the custom `Workflow/agent/phase` JavaScript runtime.

Claude Code-specific skills require the relevant diagnostic files to be uploaded or an explicitly supported environment. They are read-only by default and produce proposals; they do not modify local settings or grant permissions.

The original deep-research JavaScript harness is not represented as executable Perplexity code. Its phases, schemas, URL deduplication, evidence extraction, and adversarial verification logic are translated into the Deep Research Skill's operating procedure. A runtime-specific implementation would need a separate adapter.

## Source inventory

- `skills/deep-research/SKILL.md`
- `skills/claude-code-doctor/SKILL.md`
- `skills/debug/SKILL.md`
- `references/runtime-compatibility.md`

The original Researcher and Report Writer procedures are incorporated into Deep Research rather than exposed as separate Skills.
