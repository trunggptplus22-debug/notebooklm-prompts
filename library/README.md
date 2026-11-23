# Prompt Library — Storage and Maintenance

This directory documents the canonical storage layer. It is not the primary user interface.

## Separation of responsibilities

- `use/` is the user-facing layer. It helps a person describe a goal and lets the AI select the right prompt.
- `templates/` is the canonical prompt archive. Each prompt remains a standalone Markdown file.
- `MASTER_RESEARCH_PROTOCOL.md` contains shared quality rules. Task-specific prompts may add stricter rules but must not silently weaken the master requirements.

Do not duplicate full prompt bodies in the user-facing layer. The launcher should point to the canonical file in `templates/`.

## Canonical prompt record

Each stored prompt should use YAML frontmatter followed by the full Markdown prompt:

```yaml
---
name: "Choose the Best System Architecture"
category: "04-system-architecture"
use_case: "Select an architecture that satisfies explicit requirements and constraints."
difficulty: "advanced"
mode_support: "discovery-and-evidence"
default_mode: "both"
source_requirement: "optional"
standalone: true
version: "1.0.0"
original_path: "templates/data-engineering-specific/architecture-decision-comparison.md"
---
```

## Metadata definitions

| Field | Meaning |
|---|---|
| `name` | Plain-language task name. Avoid internal labels such as "Variant", "Engine", or "Advanced Technique" unless they distinguish materially different tasks. |
| `category` | Stable category identifier used for filtering and maintenance. |
| `use_case` | One sentence describing the user outcome. |
| `difficulty` | Practical complexity: beginner, intermediate, advanced, expert. |
| `mode_support` | Whether the prompt supports discovery, evidence-based work, both, or neither. |
| `default_mode` | Default execution mode. |
| `source_requirement` | required, optional, or none. |
| `standalone` | Whether the prompt can run without another prompt. |
| `version` | Semantic version of this prompt. |
| `original_path` | Stable source path or provenance path. Do not change it merely because the file is moved. |

## Naming rules

1. Name prompts after the user's desired outcome: "Diagnose the Problem", "Compare Methods", "Choose the Best System Architecture".
2. Use one canonical name per distinct task.
3. Remove vague suffixes such as "Variant", "Full", "Compact", or version numbers from display names unless users genuinely need to choose between different deliverables.
4. Keep technical distinctions in metadata or the description, not in a confusing display name.
5. Use descriptive kebab-case filenames.
6. Keep each prompt standalone. Shared protocols are references, not a reason to remove essential instructions from prompts that must work independently.

## Quality and lifecycle rules

- The archive is the source of truth. The launcher must not become a second divergent prompt repository.
- Preserve provenance and original path.
- Keep prompts with materially different outputs separate. Merge only true duplicates.
- When two prompts overlap, document the distinction and define a preferred default.
- Every prompt must state when to use it, required inputs, copy-ready prompt, deliverables, and limitations.
- Validate YAML frontmatter and verify that every launcher route points to an existing prompt.
- Never claim a prompt was tested against a model unless an actual execution test was performed.
