---
title: "Anthropic Claude for Financial Services — How to Work with /financial-analysis Agents"
type: "note"
summary: "Two-page operator memo: what ships in anthropics/financial-services, how to install it across Cowork / Claude Code / Managed Agents, the top slash commands, and annotated caveats."
status: "seed"
tags: ["anthropic", "agents", "finance", "reference", "claude-code"]
source_files:
  - "https://github.com/anthropics/financial-services"
  - "https://www.anthropic.com/news/finance-agents"
updated: "2026-05-07"
---

# Claude for Financial Services — Operator Memo

## TL;DR

- Anthropic ships a marketplace plugin set (`anthropics/claude-for-financial-services`) that bundles **named agents**, **vertical skill plugins**, and **MCP data connectors** for FSI workflows.
- Same codebase deploys two ways: **Cowork plugins** (UI) or **Claude Managed Agents** via `/v1/agents` (headless API).
- The `financial-analysis` vertical is the **core** — it carries the 11 MCP connectors and must be installed first; everything else layers on top.
- Agents draft analyst work product **for human review**. They do not execute trades, approve onboarding, or make investment recommendations.

## What ships

### Named agents (10)

| Coverage / Advisory | Research / Modeling | Fund Admin & Finance Ops | Operations |
|---|---|---|---|
| Pitch Agent | Market Researcher | Valuation Reviewer | KYC Screener |
| Meeting Prep Agent | Earnings Reviewer | GL Reconciler | |
| | Model Builder | Month-End Closer | |
| | | Statement Auditor | |

### Vertical plugins (9)

`financial-analysis` *(core — required)* · `investment-banking` · `equity-research` · `private-equity` · `wealth-management` · `fund-admin` · `operations` · `partner-built/lseg` · `partner-built/sp-global`

### MCP data connectors (11, centralized in `financial-analysis/.mcp.json`)

Daloopa · Morningstar · S&P Global (Kensho) · FactSet · Moody's · MT Newswires · Aiera · LSEG · PitchBook · Chronograph · Egnyte

> **Note —** Connector access typically requires a paid subscription or API key with the data provider. The plugin only wires the MCP endpoint; it does not bundle credentials.

## How to install

### Claude Code (CLI) — recommended path

```bash
# 1. Add the marketplace
claude plugin marketplace add anthropics/claude-for-financial-services

# 2. Install the core (must come first — carries skills + all MCP connectors)
claude plugin install financial-analysis@claude-for-financial-services

# 3. Add named agents you want
claude plugin install pitch-agent@claude-for-financial-services
claude plugin install gl-reconciler@claude-for-financial-services
claude plugin install market-researcher@claude-for-financial-services

# 4. Add vertical skill bundles
claude plugin install investment-banking@claude-for-financial-services
claude plugin install equity-research@claude-for-financial-services
```

### Cowork (web UI)

Settings → Plugins → **Add plugin** → paste `https://github.com/anthropics/claude-for-financial-services`, then pick agents/verticals. Or zip a single `plugins/<dir>/` and upload it.

### Managed Agents (headless API)

```bash
export ANTHROPIC_API_KEY=sk-ant-...
scripts/deploy-managed-agent.sh gl-reconciler
```

The script resolves file refs, uploads skills, creates leaf-worker subagents, and POSTs the orchestrator to `/v1/agents`. See `scripts/orchestrate.py` for a reference event loop that routes `handoff_request` events between agents.

> **Note —** Cowork, Claude Code, and Managed Agents all consume the same plugin sources — pick the surface, not a different codebase.

## Top slash commands to know

Once installed, slash commands are available in any session; skills fire automatically when relevant.

| Command | Purpose |
|---|---|
| `/comps` | Comparable company analysis with trading multiples |
| `/dcf` | DCF valuation with WACC + sensitivity |
| `/lbo` | Leveraged buyout model |
| `/3-statement-model` | Populate 3-statement model templates |
| `/debug-model` | Excel audit — formula tracing, hardcode detection |
| `/cim` | Draft Confidential Information Memorandum |
| `/teaser` | Anonymous one-page company teaser |
| `/merger-model` | Accretion/dilution M&A analysis |
| `/earnings` | Post-earnings quarterly update |
| `/ic-memo` | Investment committee memo |
| `/rebalance` | Allocation drift + tax-aware rebalancing |
| `/tlh` | Tax-loss harvesting opportunities |

The full set is 40+ commands across the verticals (sourcing, diligence, portfolio monitoring, client review, financial planning, deal tracking, etc.) — see the README for the complete grid.

## Customization hooks

- **Swap data sources** — edit `.mcp.json` in `plugins/vertical-plugins/financial-analysis/` to point at internal systems or alternate vendors.
- **Add firm context** — drop terminology, processes, and formatting standards into skill markdown files.
- **Branded decks** — run `/ppt-template` to teach Claude your PowerPoint layouts (used by `pptx-author` for headless deck output).
- **Tune agent scope** — edit `plugins/agent-plugins/<slug>/agents/<slug>.md`.
- **Validate** — run `python3 scripts/check.py` before pushing; it lints manifests and verifies cross-file references resolve. After adding a skill, run `python3 scripts/sync-agent-skills.py` to propagate it to bundled agents.

## Annotations & things to flag

> **Note (install order) —** `financial-analysis` is the only plugin that carries the MCP connector configs. Skip it and the vertical plugins will load but have no data wiring.

> **Note (legal posture) —** README is explicit that agents "do not make investment recommendations, execute transactions, or approve onboarding." Keep human-in-the-loop in any deployment doc.

> **Note (deployment parity) —** Cowork plugins and Managed Agents share one source tree (`managed-agent-cookbooks/<slug>/` mirrors each agent plugin). Pick a surface based on whether you need a UI or a programmatic event loop.

> **Note (M365 surface) —** A separate `claude-for-msft-365-install` plugin provisions Claude inside Excel/PowerPoint/Word/Outlook and can route to Vertex AI, Bedrock, or an internal LLM gateway instead of api.anthropic.com — useful for firms with existing cloud commitments or compliance constraints.

> **Note (partner plugins) —** `lseg` and `sp-global` are partner-built and gated on the corresponding data subscription. Treat them as additive on top of the core.

> **Note (sourcing caveat) —** The Anthropic announcement page (anthropic.com/news/finance-agents) was inaccessible (HTTP 403) at memo time, so this memo is fully sourced from the GitHub README. If you need the announcement framing (positioning, partner quotes, launch metrics), open the page directly in a browser.

## Source links

- Repo (canonical, used here): https://github.com/anthropics/financial-services
- Announcement (could not be fetched 2026-05-07): https://www.anthropic.com/news/finance-agents
