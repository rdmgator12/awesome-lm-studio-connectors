# Changelog

All notable changes to this list will be documented in this file. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [Semantic Versioning](https://semver.org/) — MAJOR for category restructures, MINOR for new entries, PATCH for description/URL fixes.

## [Unreleased]

### Planned for v1.1.0
- Field reports per entry — local-model + quant + observed behavior. Establishes credibility around the 🪶 token-frugality flag.
- Track LM Studio's [Popular MCP Integrations](https://lmstudio.ai/docs/integrations/mcp-remote/popular) page for new official additions and reflect within ~7 days.
- Add a "Server Settings checklist" section explaining LM Studio's `Allow per-request MCPs` and `Allow calling servers from mcp.json` toggles — they're prerequisites for several entries to work.
- Add `awesome-lint` to CI once the repo is ≥30 days old (lint blocks submissions on `git-repo-age` until 2026-06-09).

---

## [1.0.4] — 2026-07-02

### Changed
- About-paragraph stable version: **v0.4.17 → v0.4.18** (Build 1, June 26, 2026 — shipped hours after the v1.0.3 sweep). UI zoom-clipping fix, reasoning-toggle fix for models with custom reasoning settings, chat-title generation fix for reasoning models, and settings guidance for llama.cpp options under LM Studio Engine Protocol. **No MCP-surface changes.**
- SSRF note: the `lms` [tracking issue #574](https://github.com/lmstudio-ai/lms/issues/574) is **closed (completed June 7, 2026)** — reworded to "now-closed tracking issue". Guard behavior unchanged.
- Header date → July 2, 2026.
- Added the inaugural **Connector of the Week** block (rotates weekly), matching the sibling-list convention. First pick: Brave Search MCP — the entry that best embodies the token-frugal local-first thesis.

### Added
- CONTRIBUTING: two new Recommended-Remote submission criteria — **vendor-affiliation disclosure** (undisclosed self-promotion = auto-reject) and a **field-report requirement** for new remote entries (endpoint-liveness checks alone don't qualify). Added after PR #1 demonstrated that automated spam can pass every liveness check.

### Notes
- **PR #1 (Xquik) rejected** — undisclosed vendor self-promotion within an automated spam campaign (3,200+ Xquik-mentioning PRs across GitHub in June 2026; the contributor's profile links the vendor site). The GitHub repo is a verification stub / distribution shell, and the service's X automation surface (DM sending, mass follow/like/retweet, follower export) violates X's ToS. Fails the section's auth criterion regardless (manual API-key management). Expect re-submissions under other names — the campaign also runs "Hermes Tweet" and "TweetClaw" variants.
- Verified the official [Popular MCP Integrations](https://lmstudio.ai/docs/integrations/mcp-remote/popular) page directly: still exactly 4 entries (Linear, Notion, Atlassian, Sentry). Counts unchanged: 4 / 13 / 8.
- Beta channel empty as of July 2 ("The stable version is the latest"); mlx-engine remains v1.8.5. LM Studio docs now carry agent-backend integration guides (Claude Code, Codex, Hermes Agent, OpenClaw) — LM Studio-as-backend, not MCP connectors; out of entry scope.

---

## [1.0.3] — 2026-06-26

### Changed
- About-paragraph version references brought current: stable **v0.4.13 → v0.4.17**; **MTP Speculative Decoding** reclassified from *v0.4.14 beta* to **stable (v0.4.14 Build 4, May 22, 2026)**.
- Reframed the **Locally AI** line: the April 8 acquisition shipped as a real product in **v0.4.16** (June 4 / June 8, 2026) — the **Locally** mobile app (iPhone/iPad) plus **LM Link**, an end-to-end-encrypted desktop→mobile bridge (no longer waitlisted as of Build 2). Default chat context bumped to 8k.
- Added a one-line **mlx-engine v1.8.5** (June 5, 2026) callout — disk-backed KV-cache reuse + continuous batching for agentic local workloads.

### Added
- **Security-hardening note** in the About section documenting the **v0.4.15** SSRF guard: dynamic / ephemeral *remote* MCP connections to non-public addresses (e.g. `http://127.0.0.1`) are now blocked. Clarifies that local **stdio** servers are unaffected and a localhost HTTP MCP still works when declared explicitly in `mcp.json`. Directly relevant to this list's self-hosting audience.

### Notes
- Verified the official [Popular MCP Integrations](https://lmstudio.ai/docs/integrations/mcp-remote/popular) page directly: still exactly 4 entries (Linear, Notion, Atlassian, Sentry). Officially Featured count remains 4.
- No new OAuth-friendly remote MCPs from common vendors surfaced since v1.0.2. Recommended Remote MCPs (13) and Local Stdio (8) counts unchanged — this is a platform-state + safety-note refresh, not an entry addition (hence PATCH, not MINOR).
- v0.4.14 Build 2 also fixed an OAuth MCP token-exchange failure; v0.4.17 ships the LM Studio Engine Protocol (off by default) — no entry-level changes required.

---

## [1.0.2] — 2026-05-22

### Changed
- About-paragraph version reference updated from v0.4.10 → **v0.4.13** (May 13, 2026 stable).
- Added callout for the **v0.4.14 beta** (May 20, 2026) introducing **MTP Speculative Decoding** — multi-token prediction for faster local inference. Aligns with the list's local-first / token-frugal thesis.
- Header date → May 22, 2026.

### Notes
- Verified the official [Popular MCP Integrations](https://lmstudio.ai/docs/integrations/mcp-remote/popular) page directly: still exactly 4 entries (Linear, Notion, Atlassian, Sentry). No new additions to the curated set. Officially Featured count remains 4.
- No new OAuth-friendly remote MCPs from common vendors surfaced since v1.0.1. Recommended Remote MCPs count remains 13.
- v0.4.14 beta Build 1 also fixed an OAuth token-exchange failure affecting some MCPs — context for the 8 🔐 OAuth entries in the list, no entry-level changes required.

---

## [1.0.1] — 2026-05-15

### Added
- **Crawleo** under *Search and Knowledge* — hosted MCP for real-time web search, page crawl-to-markdown, Google Search, Google Maps, and headful browser rendering. Bearer-auth, joined the LM Studio docs ecosystem [May 6, 2026](https://www.crawleo.dev/blog/how-to-connect-crawleo-to-lm-studio-via-mcp).
- About-section bullet for the **Locally AI acquisition** (April 8, 2026) — LM Studio's expansion onto iPhone, iPad, and Apple Silicon Macs. Not a connector but reframes the device surface this list runs on.
- Version-stamp on OAuth 2.1 support — now attributed to v0.4.10 (April 9, 2026) for accuracy.

### Changed
- Header date → May 15, 2026.
- Recommended Remote MCPs count: 12 → 13 (Crawleo).

### Fixed
- Officially Featured count typo: header said 5, body had 4 (Linear, Notion, Atlassian, Sentry). Corrected to 4.

---

## [1.0.0] — 2026-05-10

### Added
- Initial seed across three tiers:
  - **Officially Featured by LM Studio (4):** Linear, Notion, Atlassian (Jira + Confluence), Sentry. Sourced directly from [lmstudio.ai/docs/integrations/mcp-remote/popular](https://lmstudio.ai/docs/integrations/mcp-remote/popular).
  - **Recommended Remote MCP Servers (12):** Hugging Face, Brave Search, GitHub, Cloudflare, Vercel, Stripe, PayPal, Square, Asana, Monday.com, Slack, Figma. Curated for OAuth-friendly remote endpoints + local-LLM token discipline.
  - **Local Stdio MCP Servers (8):** Filesystem, Memory, Desktop Commander, Time, Sequential Thinking, Playwright, Browserbase, Fetch. Curated for low-overhead offline workflows.
- README.md with About, Legend (⭐ 🌐 💻 🔐 🪶 🅖 🅜 🛠️), surface-grouped Contents, and per-entry use cases.
- CONTRIBUTING.md with local-LLM-specific token-discipline guidance and field-report template.
- CHANGELOG.md (this file).
- LICENSE (CC0-1.0) — awesome-list canonical convention.
- code-of-conduct.md (Contributor Covenant 2.1).
- .editorconfig + .gitignore.
- Badges row: Awesome, License (CC0-1.0), Last Commit, Track Awesome List.

### Notes
- LM Studio added MCP host support in **v0.3.17 (June 25, 2025)**.
- OAuth 2.1 support with browser-based auth flow added late 2025 / early 2026.
- LM Studio is structurally an MCP **client / host**, not a publisher — there is no `lmstudio/*` MCP server. This list mirrors that reality: we curate MCPs that are *consumable* by LM Studio, not MCPs Element Labs ships.
- Token-frugality flag (🪶) reflects the maintainer's best judgment. Field reports in v1.1.0 will replace judgment with measured behavior.
- The list deliberately overlaps with `awesome-mcp-servers` (broader, transport-agnostic) but differentiates on the curation criterion: **MCPs that work well with local LLMs in LM Studio's specific transport + auth model**.

[Unreleased]: https://github.com/rdmgator12/awesome-lm-studio-connectors/compare/v1.0.4...HEAD
[1.0.4]: https://github.com/rdmgator12/awesome-lm-studio-connectors/compare/v1.0.3...v1.0.4
[1.0.3]: https://github.com/rdmgator12/awesome-lm-studio-connectors/compare/v1.0.2...v1.0.3
[1.0.2]: https://github.com/rdmgator12/awesome-lm-studio-connectors/compare/v1.0.1...v1.0.2
[1.0.1]: https://github.com/rdmgator12/awesome-lm-studio-connectors/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/rdmgator12/awesome-lm-studio-connectors/releases/tag/v1.0.0
