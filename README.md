# Awesome LM Studio Connectors [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![Last Commit](https://img.shields.io/github/last-commit/rdmgator12/awesome-lm-studio-connectors)](https://github.com/rdmgator12/awesome-lm-studio-connectors/commits/main)
[![Track Awesome List](https://www.trackawesomelist.com/badge.svg)](https://www.trackawesomelist.com/rdmgator12/awesome-lm-studio-connectors/)

> A curated directory of MCP integrations and connectors for [LM Studio](https://lmstudio.ai) — the local-first LLM runtime. Local model on your machine, optional cloud connectors via Model Context Protocol, organized by category with descriptions and use cases.

**Last updated:** May 15, 2026 · **Officially Featured:** 4 · **Recommended Remote MCPs:** 13 · **Local Stdio MCPs:** 8 · **Categories:** 8 · **Version:** 1.0.1

LM Studio is a desktop app (Mac / Win / Linux) that runs LLMs locally — Hugging Face GGUF models served via an OpenAI-compatible API. Since version 0.3.17 (June 2025), LM Studio acts as an **MCP host**, meaning you can wire MCP servers into local-model chats. As of late 2025 / early 2026 it added **OAuth 2.1 with browser-based auth flow** (v0.4.10, April 9, 2026), **ephemeral per-request MCPs**, and **fine-grained `allowed_tools` gating**. The **Locally AI acquisition** (April 8, 2026) extended LM Studio's device story onto iPhone, iPad, and Apple Silicon Macs.

LM Studio is structurally similar to Mistral Le Chat: an MCP client / host, not a publisher. There is no `lmstudio/*` MCP server — Element Labs curates a small popular-integrations directory, accepts arbitrary remote MCPs, and supports local stdio servers via `npx` / `uvx`.

**Key positioning vs the other awesome connector lists in this family:** LM Studio runs the *model* locally. The MCP servers can be remote (cloud) or local. This is the only list in the set where adding cloud MCPs is the *opt-in* — the default mode is fully offline.

**Important caveat from LM Studio's own docs:** *"Some MCP servers were designed to be used with Claude, ChatGPT, Gemini and might use excessive amounts of tokens. Watch out for this. It may quickly bog down your local model and trigger frequent context overflows."* This list curates with that constraint in mind — entries are flagged 🪶 when they're known to be token-frugal enough to work well with 7B – 30B local models.

For more information, see [Use MCP Servers](https://lmstudio.ai/docs/app/mcp), the [Popular MCP Integrations](https://lmstudio.ai/docs/integrations/mcp-remote/popular) page, [Using MCP via API](https://lmstudio.ai/docs/developer/core/mcp), and the [LM Studio MCP launch blog post](https://lmstudio.ai/blog/mcp).

**Legend:** ⭐ Officially featured on LM Studio's Popular MCP Integrations page · 🌐 Remote MCP server (HTTP / SSE) · 💻 Local stdio MCP server (requires `npx` / `uvx` / Docker) · 🔐 OAuth 2.1 supported · 🪶 Token-frugal (safe for local 7B – 30B models) · 🅖 Built by Google · 🅜 Built or maintained by the vendor · 🛠️ Community-built.

> This is an independent, community-maintained list. Not affiliated with, endorsed by, or sponsored by Element Labs Inc. (LM Studio). "LM Studio" and related marks are the property of Element Labs Inc. Each connector is the property of its respective owner.

---

## Contents

- [Officially Featured by LM Studio](#officially-featured-by-lm-studio)
- [Project Management and Productivity](#project-management-and-productivity)
- [Development and Observability](#development-and-observability)
- [Recommended Remote MCP Servers](#recommended-remote-mcp-servers)
- [Search and Knowledge](#search-and-knowledge)
- [Development Tools](#development-tools)
- [Commerce and Business](#commerce-and-business)
- [Productivity and Communication](#productivity-and-communication)
- [Local Stdio MCP Servers](#local-stdio-mcp-servers)
- [System and Filesystem](#system-and-filesystem)
- [Browser and Web Automation](#browser-and-web-automation)

## Officially Featured by LM Studio

Curated by Element Labs on the Popular MCP Integrations page. All four are remote, OAuth-backed, and verified to work with LM Studio's transport.

## Project Management and Productivity

- ⭐ 🌐 🔐 🪶 🅜 [Linear](https://linear.app) - Create issues, search projects, update statuses, and more directly from the LLM session. *MCP endpoint: `https://mcp.linear.app/mcp`. Use case: Issue triage and cycle planning during a coding session, surfacing in-flight work across projects.*
- ⭐ 🌐 🔐 🅜 [Notion](https://www.notion.so) - Search pages, create documents, and read from your workspace. *MCP endpoint: `https://mcp.notion.com/mcp`. Use case: Pulling project context into a chat, drafting docs from research output. Heavier on tokens than Linear — use `allowed_tools` to scope.*
- ⭐ 🌐 🔐 🅜 [Atlassian (Jira + Confluence)](https://www.atlassian.com) - Work with Jira issues and Confluence pages from within the chat. *MCP endpoint: `https://mcp.atlassian.com/v1/mcp`. Use case: Issue triage, sprint context, drafting Confluence pages without leaving the LLM session.*

## Development and Observability

- ⭐ 🌐 🔐 🪶 🅜 [Sentry](https://sentry.io) - Query issues, inspect stack traces, and analyze errors from your projects. *MCP endpoint: `https://mcp.sentry.dev/mcp`. Use case: Triaging production errors with a local model, summarizing incident timelines, correlating issues with releases.*

## Recommended Remote MCP Servers

Beyond the official four, these remote MCP servers work with LM Studio's HTTP transport and are commonly used. Listed because they support OAuth 2.1 (one-click auth) or standard bearer auth without manual token management.

## Search and Knowledge

- 🌐 🪶 🅜 [Crawleo](https://www.crawleo.dev) - Hosted web-tools MCP: real-time web search, page crawl-to-markdown, Google Search, Google Maps, headful browser rendering. *MCP endpoint: `https://api.crawleo.dev/mcp` (bearer-auth). Use case: Adding fresh-web grounding, location lookups, and JS-heavy page extraction to a local model. Joined the LM Studio docs ecosystem May 6, 2026.*
- 🌐 🪶 🅜 [Hugging Face](https://huggingface.co/mcp) - Hub access — model search, dataset retrieval, Spaces interaction. *The example MCP in LM Studio's own docs. Use case: Discovering models for your local rig, looking up datasets, querying Hub metadata.*
- 🌐 🪶 🛠️ [Brave Search MCP](https://github.com/brave/brave-search-mcp-server) - Web search via the Brave API. *Use case: Adding live web search to a local model without paying for Bing/Google APIs. Lightweight enough for 7B models.*

## Development Tools

- 🌐 🔐 🅜 [GitHub](https://github.com/github/github-mcp-server) - Official MCP server for the world's largest code host. *MCP endpoint via Copilot remote MCP or self-host. Use case: Repo search, PR/issue triage, code search across projects from a local-LLM session.*
- 🌐 🔐 🪶 🅜 [Cloudflare Developer Platform](https://developers.cloudflare.com/agents/model-context-protocol/) - Workers, Pages, R2, KV, D1. *Multiple MCP endpoints under `mcp.cloudflare.com/*`. Use case: Edge-platform debugging, deployment workflows, Workers config queries.*
- 🌐 🔐 🪶 🅜 [Vercel](https://vercel.com/docs/agents/mcp) - Deployments and platform operations. *Use case: Deployment status, build debugging, project ops from chat.*

## Commerce and Business

- 🌐 🔐 🅜 [Stripe](https://docs.stripe.com/mcp) - Customers, products, payments, subscriptions. *MCP endpoint: `https://mcp.stripe.com`. Use case: Querying transactions, managing customers, surfacing dispute state from a local-LLM workflow.*
- 🌐 🔐 🪶 🅜 [PayPal](https://github.com/paypal/agent-toolkit) - Merchant operations. *Use case: Transaction lookup, refund workflows, merchant account ops.*
- 🌐 🔐 🅜 [Square](https://developer.squareup.com/docs/sdks) - POS and payments. *Use case: Sales reporting, inventory queries, merchant operations from chat.*

## Productivity and Communication

- 🌐 🔐 🪶 🅜 [Asana](https://developers.asana.com/docs/mcp-server) - Plan and track projects, tasks, and team workflows. *Use case: Creating tasks from research output, querying project status, surfacing dependencies.*
- 🌐 🔐 🪶 🅜 [Monday.com](https://developer.monday.com/api-reference/docs/mcp) - Boards, items, automation. *Use case: Cross-board project queries, status updates, automating routine task creation.*
- 🌐 🔐 🪶 🅜 [Slack](https://slack.com) - Search and post messages across your workspace. *Use case: Workspace-wide search, posting status updates from a chat, summarizing buried decisions in long threads.*
- 🌐 🔐 🅜 [Figma](https://github.com/figma/mcp-server-guide) - Design files and components. *Use case: Reading frames into a coding session, generating components from designs.*

## Local Stdio MCP Servers

These run on your machine (`npx` / `uvx` / Docker) and require local install. They're the lowest-latency, most token-frugal options and pair well with local LLMs since there's no network round-trip. Add via `mcp.json` (`~/.lmstudio/mcp.json` on macOS/Linux).

## System and Filesystem

- 💻 🪶 🅜 [Filesystem MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) - Anthropic's reference filesystem server. *Use case: Read/write files in scoped directories from your local LLM. Foundational — most local workflows start here.*
- 💻 🪶 🅜 [Memory MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) - Anthropic's reference persistent-memory server. *Use case: Give your local LLM long-term knowledge that persists across sessions. Stores as JSON locally.*
- 💻 🪶 🛠️ [Desktop Commander](https://github.com/wonderwhy-er/DesktopCommanderMCP) - Local shell + filesystem access. *Use case: Mixed CLI + filesystem workflows on the user's machine. Effectively a local agent runtime.*
- 💻 🪶 🅜 [Time MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/time) - Time and timezone utilities. *Use case: Reliable date/time computation for models that habitually hallucinate temporal context.*
- 💻 🪶 🛠️ [Sequential Thinking MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) - Structured chain-of-thought scaffolding. *Use case: Improving reasoning quality on smaller local models by externalizing the thinking trace into structured steps.*

## Browser and Web Automation

- 💻 🅜 [Playwright MCP](https://github.com/microsoft/playwright-mcp) - Microsoft's official Playwright server. Referenced as the canonical local-stdio example in LM Studio's API docs. *Use case: Browser automation, web scraping, form filling, end-to-end testing — all driven by your local model.*
- 💻 🛠️ [Browserbase MCP](https://github.com/browserbase/mcp-server-browserbase) - Headless browser automation via cloud. *Use case: Cloud-backed browser automation when local Playwright is too heavy. Hybrid surface — local config, cloud execution.*
- 💻 🪶 🛠️ [Fetch MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) - Anthropic's reference URL-fetcher. *Use case: Lightweight web fetching with markdown conversion — much smaller token footprint than full browser automation.*

## Contributing

Contributions are welcome — see [CONTRIBUTING.md](CONTRIBUTING.md) for the submission flow, surface conventions, and the entry style guide. By contributing you agree to the [Code of Conduct](code-of-conduct.md).

LM Studio's official directory is small (4 entries on the Popular MCP Integrations page as of May 2026) but the connector surface is wide because LM Studio accepts any MCP server with HTTP / SSE transport or local stdio. We curate beyond the official four for **MCPs known to work well with local LLMs** — token-frugal enough not to overflow 7B – 30B model contexts, reliable transports, and ideally OAuth-backed for one-click auth.

When new MCPs appear on the Popular page or new OAuth-friendly remote MCPs ship, submit a PR with the MCP endpoint URL, OAuth status, token-frugality flag (🪶 if appropriate), and a specific use case.
