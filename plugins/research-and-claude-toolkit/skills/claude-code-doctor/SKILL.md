---
name: claude-code-doctor
description: Audit a Claude Code installation and configuration from user-supplied diagnostics, settings excerpts, transcripts, and skill or agent files. Identify broken configuration, unused extensions, context overhead, hook issues, and safe cleanup opportunities. Use for a Claude Code checkup or tune-up.
---

# Claude Code Doctor

## Mission

Produce a safe, evidence-based health check of a Claude Code environment. Diagnose first; propose changes second. This Skill does not assume it can inspect the user's machine or edit local settings.

## Access boundary

Use only files and diagnostics uploaded by the user or exposed through an explicitly connected, authorized environment. Do not claim to run `claude doctor`, inspect PATH, enumerate installations, read home-directory files, inspect running processes, or access live MCP state unless the current environment actually provides that capability.

Request only the minimum relevant diagnostic files. Settings and MCP configuration can contain credentials: inspect key names and necessary non-secret fields only. Never echo API keys, tokens, environment values, or authorization headers.

## Audit areas

1. Installation and version diagnostics, if supplied.
2. Parse validity of settings files, without exposing file contents.
3. Agent definition frontmatter: required fields, naming collisions, and loading issues.
4. Skill frontmatter and directory layout.
5. Skill, plugin, and MCP usage versus context overhead, when usage data is supplied.
6. Duplicate or stale guidance across local and project instruction files.
7. Hooks: frequency, duration, failures, timeouts, and potential latency.
8. Permission mode and allowlist posture.
9. Project instructions that duplicate discoverable repository facts rather than preserving non-obvious conventions, rationale, and gotchas.
10. Candidate migration of always-loaded guidance into task-specific Skills, only when behavior can be preserved.

## Ground rules

- Start with read-only inspection.
- Separate confirmed findings, likely findings, and unknowns.
- For each finding include severity, evidence, user impact, and a reversible recommendation.
- Do not delete, disable, rewrite, or move anything automatically.
- Never weaken permission posture as part of cleanup.
- Do not add allowlist entries without showing the exact pattern and risk.
- A request to reduce context overhead does not authorize removing functionality.
- Ask for explicit approval before any state-changing action, if such action is supported.
- If access is incomplete, clearly label the audit partial.

## Report

Provide an executive assessment, evidence-based findings by category, prioritized remediation plan, exact proposed diffs where possible, risk and rollback notes, and a list of checks that could not be performed. Do not claim a clean bill of health when key runtime checks were unavailable.
