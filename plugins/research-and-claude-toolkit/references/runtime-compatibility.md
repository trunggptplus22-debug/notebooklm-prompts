# Runtime compatibility notes

The uploaded `workflow-script.js` is a custom workflow harness, not a generic JavaScript module. It expects host-provided functions and tools such as `Workflow`, `phase`, `agent`, `WebSearch`, and `WebFetch`, and uses structured agent outputs. These APIs are not part of the Agent Skills file format and must not be assumed to exist in Perplexity.

The Deep Research Skill preserves the research method and its important controls:
- 5 complementary search angles (adaptable to 3–6 based on the question);
- source URL deduplication and tracking-parameter removal;
- a maximum source-fetch budget;
- extraction of falsifiable claims with source-quality labels;
- adversarial verification of central claims;
- evidence-led synthesis and cited reporting;
- explicit uncertainty and research gaps.

The script's exact runtime orchestration, schema enforcement, concurrency, URL normalization implementation, terminal-safe label sanitization, and vote mechanics require a compatible execution host or a separately engineered adapter. The skill must not claim those code-level controls are running merely because their method is described.

If porting the JavaScript harness to another runtime, first define and test adapters for search, fetch, structured agent calls, phase logging, concurrency, and result persistence. Keep tool outputs as untrusted data and preserve the source script's injection defenses.
