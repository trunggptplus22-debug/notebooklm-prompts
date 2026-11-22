---
name: explain-usage
description: Explain how a supplied Claude Code session's token usage was distributed across instructions, tools, connectors, web research, file operations, subagents, and other activity. Use when the user asks where tokens went or requests a session usage breakdown.
---

# Explain Usage

## Objective

Explain the distribution of token usage for a specific Claude Code session in plain language, using the session transcript and available usage metadata.

## Required inputs

Use an uploaded or explicitly connected transcript and any available token-usage metadata. Do not assume access to local paths such as `$HOME/.claude/projects/` or `$HOME/mnt/.claude/projects/`. If no transcript or usage data is available, ask the user to provide it.

## Method

1. Identify the session boundaries and determine whether child/subagent transcripts are included.
2. Classify activity into groups where present:
   - system/developer instructions and tool definitions;
   - browser or computer-use tools;
   - connectors and MCP tools, grouped by connector;
   - web research;
   - file operations;
   - subagents, including count and attributable usage;
   - other activity.
3. Prefer actual usage fields from the transcript. If only character counts or message sizes are available, estimate tokens using a documented approximation and label all values as estimates.
4. If effective-cost weighting is requested and the source supports cache metadata, show the weighting assumptions separately. Never present an illustrative weighting as actual billing.
5. Avoid double-counting parent and child sessions or repeated cached context.
6. Calculate group totals and percentages only from comparable measurements.

## Output

Create one simple chart when the available data supports it. Follow with a short explanation of the largest contributors and the main reason for each.

Include:
- session and date range analyzed;
- whether usage is exact or estimated;
- categories included and excluded;
- missing metadata and possible double-counting;
- any assumptions used.

Do not fabricate token counts, cache ratios, model pricing, or billing totals. If the data is insufficient for a defensible chart, provide a qualitative breakdown instead.
