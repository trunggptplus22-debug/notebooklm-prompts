# Response Intelligence — Agent Plugin

Portable Agent Plugin 1.0 bundle for clients that support GitHub plugin imports and Agent Skills.

## Included skill

- `skills/response-intelligence/SKILL.md`: operational instructions for epistemic classification, anti-sycophancy, coherence audits, diagnostic inquiry, research-query refinement, response profiles, and final-answer audits.
- `skills/response-intelligence/rules.yaml`: machine-readable policy rules.
- `skills/response-intelligence/output_schema.json`: optional structured output contract.
- `skills/response-intelligence/tests/test-cases.json`: ten designed behavioral acceptance cases.
- `skills/response-intelligence/README.md`: provenance, adaptation decisions, and validation status.

## Import into Perplexity Computer

In Perplexity Computer, open **Plugins → Add custom → Import plugin from GitHub** and provide this public folder URL:

`https://github.com/trunggptplus22-debug/notebooklm-prompts/tree/research/agent-workflow-style-integration/plugins/response-intelligence`

After the pull request is merged, use:

`https://github.com/trunggptplus22-debug/notebooklm-prompts/tree/main/plugins/response-intelligence`

## Scope and limitations

This plugin supplies a Skill; it does not bundle MCP connectors, credentials, external APIs, or deterministic calculation engines. The behavioral cases are designed but have not been executed against Perplexity or another target runtime. Import compatibility is based on the Agent Plugins 1.0 package structure and has not yet been runtime-tested in a Perplexity account.

## License and provenance

The Skill is a provider-neutral adaptation of selected response-style and diagnostic methods documented in the repository's research. See the Skill README and research notes for source attribution and adaptation boundaries.
