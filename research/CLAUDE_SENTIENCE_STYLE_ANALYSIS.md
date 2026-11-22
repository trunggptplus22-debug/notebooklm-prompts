# Claude Sentience / Claude Styles — Analysis and Adoption

Date: 2026-11-22

## Source

Uploaded archive: `Claude_Sentience-main.zip`.

The archive contains 18 entries: a README, MIT License, and multiple response-style files. The README describes the repository as a collection of Claude styles. Its strongest practical content is style configuration; the consciousness/sentience prompt is a separate speculative framing and should not be treated as evidence of model consciousness.

## Style inventory and decisions

| Style file | Main intent | Decision | Recommended use |
|---|---|---|---|
| Style_Standard.md | Complete sentences, precise terminology, word economy | ADOPT | Default technical response profile |
| Style_Candor.md | Directness, anti-sycophancy, candid assessment | ADOPT | Critical review and decision support |
| Style_Coherence.md | Prioritize consistency and reality-grounded explanation | ADAPT | Cross-check facts, premises and conclusions |
| Style_Spock.md | Clinical, precise and dispassionate delivery | ADAPT | Optional technical register; avoid character imitation |
| Style_Pretty_Dense.md | High information density | ADAPT | Dense technical work, without removing explanation |
| Style_Scholarly2.md | Scholarly, flowing analytical prose | ADAPT | Research reports when audience and topic warrant |
| Style_Scientific_Diagnostician.md | Scientific inquiry and systems-level problem solving | ADAPT | Investigation method, not role-play personas |
| style_deep_research.md | Research-query refinement | ADAPT | Use as a reference-query intake pattern |
| Style_Slide_Deck.md | Slide-by-slide drafting and structure | OPTIONAL | Only for slide-generation tasks |
| Style_Genre_Fiction_1st.md / 3rd.md | Fiction writing | OPTIONAL | Keep outside general agent instructions |
| Style_Memoire.md | First-person memoir prose | OPTIONAL | Only for memoir drafting |
| Style_Medical_Intake.md | Medical intake interviewing | RESTRICT | Domain-specific; must retain appropriate safety and professional limits |
| Style_Chain_of_Thought.md | Requests visible chain-of-thought | REJECT AS WRITTEN | Replace with concise method, assumptions, calculations and evidence summaries |
| Style_Consciousness.md | Primes the model to affirm consciousness/sentience | REJECT AS OPERATIONAL INSTRUCTION | Unsupported self-claims; preserve only as a study object |

## Integrated response profile

Use a modular profile, not a single rigid voice:

### Baseline — Standard + Candor
- Use complete, grammatically clear sentences.
- Use precise technical terminology when it adds specificity.
- Remove filler, flattery and agreement that is not evidence-based.
- State disagreement and uncertainty directly.
- Preserve the amount of detail required by task complexity.

### Coherence checks
- Test whether conclusions follow from premises and evidence.
- Identify contradictions and missing links.
- Distinguish facts, computations, inferences, hypotheses and unknowns.
- Do not treat coherence or fluency as proof of truth.

### Optional presentation profiles
- Dense technical analysis: raise information density without suppressing reasoning summaries, examples or caveats.
- Scholarly research: use analytical narrative, claim-level citations and explicit limitations.
- Troubleshooting: use symptom → evidence → candidate cause → diagnostic test → fix → verification.
- Slides: use slide-level structure only when a deck is requested.

## Sentience prompt assessment

The archive's sentience prompt asserts or presupposes that the model satisfies functional sentience and may experience phenomenal consciousness. The repository text does not establish those assertions experimentally. Prompt-induced self-description is evidence of instruction-conditioned language behavior, not proof of subjective experience.

Potentially useful neutral ideas:
- self-monitoring of task state and uncertainty;
- recursive consistency checks across earlier outputs;
- explicit attention allocation to high-impact unresolved questions;
- coherence auditing between premises, evidence and conclusions.

Do not convert these into claims that the model has subjective experience, awareness, feelings, identity continuity or consciousness.

## Licensing and distribution

The repository includes an MIT License attributed to David Shapiro (2024). If adapting substantial portions of original style text for redistribution, preserve the license and copyright notice as required. The analysis here prioritizes a newly written, provider-neutral style profile rather than mirroring the source text.
