# Contributing

This list curates MCP integrations and connectors for [LM Studio](https://lmstudio.ai), with a deliberate bias toward **MCPs that work well with local LLMs**. Contributions welcome.

> This is an independent, community-maintained project. Not affiliated with, endorsed by, or sponsored by Element Labs Inc. (LM Studio).

## What You Can Contribute

### Officially Featured additions
When Element Labs adds a new connector to the [Popular MCP Integrations](https://lmstudio.ai/docs/integrations/mcp-remote/popular) page, submit a PR. Use the ⭐ flag and link to the canonical vendor homepage. Include the MCP endpoint URL in the entry's use-case sentence (e.g., `MCP endpoint: https://...`).

### Recommended Remote MCP additions
For MCPs *not* on LM Studio's official Popular page, submit only if **all of these are true**:
- Has a stable remote endpoint (HTTP / SSE) — local-only stdio MCPs go in the local section instead.
- Supports OAuth 2.1 OR plain bearer-header auth without manual token rotation.
- Token-frugal enough to be flagged 🪶 OR clearly worth the token cost (e.g., critical for a specific workflow).
- Built or maintained by the vendor itself (🅜) OR by a high-signal community maintainer (🛠️).

### Local Stdio MCP additions
Submit if the MCP is regularly installable via `npx` / `uvx` / Docker, runs offline (or mostly offline), and pairs well with local-LLM workflows. Keep this section narrow — the criterion is **reliable + low-overhead + locally executable**, not "every MCP with a stdio transport."

### Improved Descriptions
If a description or use case is generic or vague, submit a PR with a more specific one. Use cases should describe what the connector unlocks for *local-LLM* workflows specifically (token cost matters here in a way it doesn't on a frontier-model awesome list).

### Token-frugality (🪶) Corrections
If you've tested an MCP and found it bogs down 7B – 30B local models with context overflow, submit a PR removing the 🪶 flag (or adding it if you've confirmed an entry is safe). Field reports welcome.

### Category Corrections / Legend Fixes
If a connector is in the wrong category or an emoji legend is wrong (⭐ / 🌐 / 💻 / 🔐 / 🪶 / 🅖 / 🅜 / 🛠️), submit a PR fixing it.

### Field Reports
Tested an MCP with a specific local model and have notes? Add a brief field report below the entry:

```markdown
- 🌐 🔐 🪶 🅜 [Connector Name](https://example.com) - Description. *Use case: ...*
  > **Field report (Llama-3.1-8B-Instruct, Q4):** Worked well for X but choked on Y. Used `allowed_tools` to scope to `[Z]`.
```

Field reports with a model + quant noted are especially welcome — they help future readers calibrate.

## Guidelines

- One PR per change unless closely related.
- Keep descriptions concise — one sentence for the description, one for the use case (plus optional MCP endpoint URL).
- Use cases should be specific and practical, not marketing copy.
- Link to the **vendor's canonical page or the MCP server's GitHub repo** — not to a Mistral / Claude / Gemini docs page that happens to mention the same MCP.
- Maintain alphabetical order within categories.
- Apply the legend correctly:
  - ⭐ = on LM Studio's official Popular MCP Integrations page
  - 🌐 = remote MCP (HTTP / SSE)
  - 💻 = local stdio MCP (`npx` / `uvx` / Docker)
  - 🔐 = OAuth 2.1 supported
  - 🪶 = token-frugal — works well with 7B – 30B local models
  - 🅖 = built / maintained by Google
  - 🅜 = built / maintained by the vendor
  - 🛠️ = community-built

## Local-LLM Token Discipline

LM Studio's own docs flag this:

> *"Some MCP servers were designed to be used with Claude, ChatGPT, Gemini and might use excessive amounts of tokens. Watch out for this. It may quickly bog down your local model and trigger frequent context overflows."*

When evaluating new entries, ask:
1. Does the MCP's `tools/list` response fit comfortably in a 4K – 8K prompt?
2. Are tool descriptions concise, or do they include long preambles aimed at frontier-model behavior shaping?
3. Do tool *outputs* tend to be large (e.g., full HTML pages, dense JSON dumps)?

If any of these are concerning, flag it in the use case and skip the 🪶 marker. Optionally suggest `allowed_tools` scoping in the description.

## Updates

This list is updated as LM Studio's official directory grows and as new OAuth-friendly remote MCPs ship. If you notice changes that aren't reflected here, please open an issue or PR.
