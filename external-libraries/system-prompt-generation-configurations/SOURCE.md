# External Prompt Library: System Prompt Generation Configurations

- Repository: https://github.com/danielrosehill/System-Prompt-Generation-Configurations
- Author: Daniel Rosehill
- Default branch inspected: main
- Repository type: curated collection of meta-prompts for generating, editing, refining, adapting, and managing other system prompts.
- Added to this library on: 2026-11-21
- License status: the inspected upstream repository did not contain a LICENSE file. Its README describes public use and requests attribution, but that statement is not a formal open-source license grant. Do not copy or redistribute upstream prompt text without explicit permission or a subsequently published license. This entry records source metadata and an index only.

## Purpose

The upstream repository is specifically about system prompts that operate on other system prompts. It includes generators, editors, prompt adaptation, localization, prompt forking, team/assistant ideation, analysis, security review, and redaction.

## Indexed prompt configurations

| Prompt | Upstream path | Main capability |
|---|---|---|
| Batch System Prompt Generator | generators/batch-generator.md | Generate multiple related assistant prompts |
| Dual Prompt Generator | dual-prompt-creation/dual-prompt-generator.md | Create personalized and generalized versions |
| Multi-Modal Prompt Adapter | multimodal/multimodal-prompt-adapter.md | Adapt text-only prompts to multimodal systems |
| System Prompt Depersonaliser | redaction/depersonaliser.md | Generalize personalized prompts |
| System Prompt Development Q&A Workflow | alt-workflows/qa-workflow.md | Guided prompt development |
| System Prompt Doctor | editors/doctor.md | Diagnose and enhance existing prompts |
| System Prompt Editor | alt-workflows/review-and-edit.md | Review, analyze, and optimize prompts |
| System Prompt Feature Editor | editors/feature-editor.md | Add or refine features in prompts |
| System Prompt Generator with Parameters | generators/conversational-generators.md | Guided prompt generation |
| System Prompt Forker | team-development/prompt-forker.md | Adapt a prompt for a different domain or purpose |
| System Prompt Generator — Prompt Only | generators/prompt-only-generator.md | Generate prompt-only output |
| System Prompt Generator — Short Version | generators/generator-short-version.md | Compact generation |
| Structured System Prompt Generator | generators/structured-generator.md | Structured prompt generation |
| System Prompt Localizer | localization/prompt-localizer.md | Localize prompts across languages/cultures |
| System Prompt Pair Suggester | team-development/pair-suggester.md | Suggest complementary assistants |
| System Prompt Parameter Calculator | analysis/prompt-parameter-calculator.md | Analyze prompt parameters |
| System Prompt Security Auditor | security/prompt-security-auditor.md | Audit security weaknesses |
| System Prompt Sharer | redaction/share-processor.md | Prepare prompts for public sharing |
| System Prompt Stylistic Editor | style/system-prompt-stylistic-editor.md | Rewrite style while retaining function |
| System Prompt to Image | from-to/prompt-to-image.md | Generate assistant-avatar image prompts |
| Title to System Prompt | from-title/system-prompt-from-title.md | Derive a prompt from a title |

## Priority for further inspection

1. System Prompt Doctor — best candidate for diagnosis and enhancement.
2. System Prompt Editor — review and iterative optimization.
3. System Prompt Feature Editor — controlled feature-level change.
4. System Prompt Forker — adaptation while preserving source behavior.
5. System Prompt Security Auditor — robustness and instruction-security review.
6. System Prompt Depersonaliser — remove person-specific assumptions.

## Use boundary

Treat these as candidate meta-prompts, not as verified prompt-engineering standards. Test each against representative system prompts, compare with a no-tool baseline, and preserve the original prompt for rollback. Do not let a refiner silently alter domain axioms, source constraints, tool permissions, or safety boundaries.
