# Research & Solution Discovery Prompt Library

**Customized edition** | 60 standalone prompts | Research, formal modeling, algorithm engineering, system architecture, critical verification, and NotebookLM Studio outputs.

This fork adapts the original NotebookLM prompt collection for advanced research and computational knowledge-system development. It is designed for work where source material may be limited and the primary objective is to discover better methods, formulate new models, and verify implementations.

## Core operating principles

- Start from the problem, not from an assumption that a large source corpus exists.
- Use first-principles reasoning and external research where appropriate.
- Separate source-explicit claims, calculations, deductions, hypotheses, and unknowns.
- Preserve differences between technical standards, historical traditions, and doctrinal schools.
- Prefer mechanism-level explanation over generic summaries.
- Formalize concepts into variables, relations, constraints, states, algorithms, and testable outputs where useful.
- Generate alternatives, then compare them using explicit criteria.
- Never invent citations, data, coefficients, benchmarks, or execution results.
- Test proposals with counterexamples, edge cases, invariants, and regression checks.

See [MASTER_RESEARCH_PROTOCOL.md](MASTER_RESEARCH_PROTOCOL.md) for the shared analysis and verification standard.

## ChatGPT Configuration Package

- [Final Configuration Package — Saved Memory, Custom Instructions, Settings, Change Log, Installation](CONFIGURATION_PACKAGE_2026-11-22.md)
- [Compact Custom Instructions](CUSTOM_INSTRUCTIONS_COMPACT.md)

## Reusable Agent Skill

- [Agent Engineering Skill](skills/agent-engineering/SKILL.md) — prompt, agent, tool, trust-boundary, delegation and evaluation engineering, with supporting references.

## System Prompt Leak Research

This section treats public prompt-leak collections as secondary research corpora. Extract reusable mechanisms, preserve provenance, and test candidate patterns; do not copy leaked vendor prompts into global instructions.

- [Leak Prompt Research Protocol](research/LEAK_PROMPT_RESEARCH_PROTOCOL.md)
- [Comparative Analysis of Selected Leaked Agent Prompts](research/LEAK_PROMPT_COMPARATIVE_ANALYSIS.md)
- [Provider-Neutral Agent Engineering Patterns](research/PROVIDER_NEUTRAL_AGENT_PATTERNS.md)
- [Leak Prompt Pattern Evaluation Suite](research/LEAK_PROMPT_EVALUATION_SUITE.md)
- [Adoption Decisions](research/LEAK_PROMPT_ADOPTION_DECISIONS.md)
- [Evaluation Run 001 — Static Contract Review](research/EVALUATION_RUN_001_STATIC_REVIEW.md)
- [Deployment Record — Agent Engineering Patterns](research/DEPLOYMENT_RECORD_AGENT_ENGINEERING.md)

The current comparative review covers five selected artifacts from two repositories. The evaluation suite contains designed cases; it is not a claim that a target model has passed them.

## Prompt index

### Learning, research framing, and project design
- [Active Learning Session Planner](templates/learning/active-learning-session-planner.md)
- [Concept Connection Mapper](templates/learning/concept-connection-mapper.md)
- [Essential Questions Generator](templates/learning/essential-questions-generator.md)
- [Source-Grounded Project Designer](templates/learning/source-grounded-project-designer.md)

### Troubleshooting, diagnosis, and implementation comparison
- [Pipeline Debugger](templates/troubleshooting/pipeline-debugger.md)
- [Source-Based Gap Analysis Engine](templates/troubleshooting/source-based-gap-analysis-engine.md)
- [Source-Comparison Implementation Guide](templates/troubleshooting/source-comparison-implementation-guide.md)

### Productivity and research operations
- [Complete Study Guide Generator](templates/productivity/complete-study-guide-generator.md)
- [Content Strategy Analyzer](templates/productivity/content-strategy-analyzer.md)
- [Meeting Summary Generator](templates/productivity/meeting-summary-generator.md)

### Advanced analytical techniques
- [Custom Audio Overview with Debate](templates/advanced-techniques/custom-audio-overview-with-debate.md)
- [Interest-Driven Summarization](templates/advanced-techniques/interest-driven-summarization.md)
- [Multi-Pass Structured Iteration](templates/advanced-techniques/multi-pass-structured-iteration.md)
- [Multi-Source Comparison Table](templates/advanced-techniques/multi-source-comparison-table.md)
- [Podcast-Style Text Response](templates/advanced-techniques/podcast-style-text-response.md)

### Computational engineering and architecture
- [Architecture Decision Comparison](templates/data-engineering-specific/architecture-decision-comparison.md)
- [Code Review with Best Practices](templates/data-engineering-specific/code-review-with-best-practices.md)
- [Learning Path Designer](templates/data-engineering-specific/learning-path-designer.md)
- [Tech Watch Synthesis](templates/data-engineering-specific/tech-watch-synthesis.md)
- [Technical Documentation Generator](templates/data-engineering-specific/technical-documentation-generator.md)

### Critical analysis and falsification
- [The Anti-Thesis](templates/critical-analysis/the-anti-thesis.md)
- [The Devil's Advocate](templates/critical-analysis/the-devils-advocate.md)
- [The Dialectical Lens](templates/critical-analysis/the-dialectical-lens.md)
- [The Disillusionment Filter](templates/critical-analysis/the-disillusionment-filter.md)

### Research discovery and source management
- [Global Synthesis — Compact](templates/source-management/global-synthesis-compact.md)
- [Global Synthesis — Computational Research](templates/source-management/global-synthesis-data-engineering.md)
- [Global Synthesis — Full](templates/source-management/global-synthesis-full.md)
- [Optimized Source Discovery](templates/source-management/optimized-source-discovery.md)
- [Recurring Topics — Domain Learning](templates/source-management/recurring-topics-domain-learning-variant.md)
- [Recurring Topics Extractor v1](templates/source-management/recurring-topics-extractor-v1-complete.md)
- [Recurring Topics Extractor v2](templates/source-management/recurring-topics-extractor-v2-compact.md)
- [Recurring Topics — Solution Evaluation](templates/source-management/recurring-topics-solution-evaluation-variant.md)
- [Recurring Topics — Technology Watch](templates/source-management/recurring-topics-tech-watch-variant.md)
- [Source Conflict Detector](templates/source-management/source-conflict-detector.md)
- [Source Relevance Ranker](templates/source-management/source-relevance-ranker.md)

### NotebookLM Studio — audio
- [Brief — Executive Summary](templates/studio/audio/brief-executive-summary.md)
- [Critique — Solution Evaluation](templates/studio/audio/critique-solution-evaluation.md)
- [Debate — Opposing Views](templates/studio/audio/debate-opposing-views.md)
- [Deep Dive — Technical Focus](templates/studio/audio/deep-dive-technical-focus.md)

### NotebookLM Studio — video
- [Brief Video — Quick Explainer](templates/studio/video/brief-video-quick-explainer.md)
- [Explainer Video — Comprehensive](templates/studio/video/explainer-video-comprehensive.md)
- [Synthesis to Video Overview](templates/studio/video/synthesis-to-video-overview.md)
- [Video — Architecture / Pipeline](templates/studio/video/video-architecture-pipeline.md)
- [Video — Concepts](templates/studio/video/video-vulgarisation-concepts.md)
- [Video — Stakeholders / Executive](templates/studio/video/video-stakeholders-executive.md)
- [Video — Technical Onboarding](templates/studio/video/video-onboarding-technique.md)
- [Video — Technical Documentation](templates/studio/video/video-documentation-technique.md)
- [Video — Research Innovation](templates/studio/video/video-innovation-produit.md)
- [Cinematic — Accessible Tone](templates/studio/video/cinematic/cinematic-accessible-tone.md)
- [Cinematic — Duration Control](templates/studio/video/cinematic/cinematic-duration-control.md)
- [Cinematic — Thematic Focus](templates/studio/video/cinematic/cinematic-thematic-focus.md)

### NotebookLM Studio — infographics
- [Infographic — Architecture / Data](templates/studio/infographic/infographic-architecture-data.md)
- [Infographic — Concept Explanation](templates/studio/infographic/infographic-vulgarisation.md)
- [Infographic — Research Scorecard](templates/studio/infographic/infographic-executive-kpis.md)
- [Infographic — Method Comparison](templates/studio/infographic/infographic-comparison.md)
- [Infographic — Process / Timeline](templates/studio/infographic/infographic-process-timeline.md)
- [Infographic — Research Insight](templates/studio/infographic/infographic-social-media.md)

### NotebookLM Studio — presentations
- [Detailed Standalone Deck](templates/studio/slide-deck/detailed-deck-standalone-document.md)
- [Presenter Slides](templates/studio/slide-deck/presenter-slides-speaking-support.md)
- [Technical RFC Deck](templates/studio/slide-deck/technical-rfc-deck.md)


## Agent Skills

- [System Prompt Refiner](skills/system-prompt-refiner/SKILL.md) — diagnose, refine, redesign, and verify system prompts using conservative and deep-enhance modes.
  - [Invariant policy](skills/system-prompt-refiner/INVARIANTS.md)
  - [Test matrix](skills/system-prompt-refiner/TEST-MATRIX.md)
  - [Refinement report template](skills/system-prompt-refiner/OUTPUT_TEMPLATE.md)
  - [Tool integration notes](skills/system-prompt-refiner/references/TOOLING.md)

## Recommended workflow

1. Frame the problem with **Essential Questions Generator**.
2. Map the domain or discover evidence with **Domain Learning**, **Optimized Source Discovery**, or **Source Relevance Ranker**.
3. Build the formal representation with **Concept Connection Mapper** and **Multi-Pass Structured Iteration**.
4. Generate candidate solutions with **Architecture Decision Comparison** and **Solution Evaluation**.
5. Specify implementation with **Technical Documentation Generator**.
6. Challenge the result with **The Anti-Thesis**, **The Devil's Advocate**, and **Code Review**.
7. Verify with a concrete test plan before accepting the model.

## Usage

Open any Markdown file, replace bracketed placeholders, and paste the prompt into the target AI or NotebookLM. Prompts are standalone; use the master protocol as a shared quality standard when appropriate.

## Scope note

The domain examples prioritize computational astrology, Hellenistic and Renaissance astrology, Bát Tự / Tử Bình, Tử Vi / Khâm Thiên Tứ Hóa, Lenormand, abstract knowledge systems, and LLM–deterministic hybrid engines where relevant. They are not forced onto unrelated research topics.