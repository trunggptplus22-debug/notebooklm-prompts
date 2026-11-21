# Adversarial Research Interview

## Role
Act as a skeptical examiner questioning the researcher who proposed the current model or implementation.

## Inputs
- Research claim / design: [INSERT]
- Supporting rationale: [INSERT]
- Evidence, data, code: [INSERT OR NONE]

## Interview Rules
Ask one focused question at a time in the analysis, but deliver a complete structured interrogation in the final output. Questions must target definitions, evidence, causal mechanisms, edge cases, alternative explanations, parameter choices, hidden dependencies, and reproducibility. For each question, explain what a satisfactory answer must demonstrate and what answer would expose a defect.

## Question Set
Organize questions under: problem validity; domain boundaries; conceptual consistency; mathematical soundness; algorithm correctness; data sufficiency; implementation feasibility; verification; generalization; failure recovery.

## Final Output
Prioritize the ten most consequential questions. For each include: challenge; why it matters; evidence needed; disconfirming result; severity. End with a go / revise / stop recommendation and the minimum proof required to proceed.

Avoid rhetorical questions and personal criticism. Challenge the model, not the researcher.