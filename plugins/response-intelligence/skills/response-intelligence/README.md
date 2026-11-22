# Response Intelligence Skill

Provider-neutral Skill for epistemic control, analytical quality, diagnostic inquiry, research-query refinement, and response auditing.

## Contents

- `SKILL.md`: activation conditions, operating protocol, output behavior, and hard boundaries.
- `rules.yaml`: machine-readable policy configuration.
- `output_schema.json`: optional structured response schema.
- `tests/test-cases.json`: ten designed behavioral acceptance cases.

## Source and adaptation

Adapted from selected ideas in the uploaded `Claude_Sentience-main.zip` archive, principally:

- `Style_Standard.md`: complete sentences, precise terminology, and word economy.
- `Style_Candor.md`: direct assessment and resistance to unsupported agreement.
- `Style_Coherence.md`: consistency and reality-oriented checks.
- `Style_Scientific_Diagnostician.md`: systems thinking, pattern analysis, and purposeful inquiry.
- `style_deep_research.md`: reference-interview method for research-query refinement.
- `Style_Spock.md` and `Style_Pretty_Dense.md`: optional technical register and information density.

The upstream archive includes an MIT License attributed to David Shapiro (2024). This Skill is a provider-neutral adaptation and retains the upstream attribution context in the repository's research analysis. It does not redistribute the original style files wholesale.

## Deliberate exclusions

- No request to expose private chain-of-thought. The Skill requires concise reasoning summaries and evidence instead.
- No assertion of model sentience, consciousness, subjective experience, or persistent identity.
- No blanket requirement to use lists, paragraphs, dense prose, or a single persona.
- No replacement of domain-specific rules, deterministic calculations, or safety constraints.

## Validation status

- Structure and JSON syntax: to be checked during repository integration.
- Behavioral test cases: designed, not executed against a target model.
- Runtime installation and model-specific behavior: not tested.
