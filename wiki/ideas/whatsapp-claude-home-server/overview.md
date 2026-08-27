---
title: "WhatsApp + Claude Home Server"
type: "idea"
summary: "Always-on MacBook M2 at home running Claude Code with wacli, Obsidian vault, and mdfind — 'search over everything' from the Claude mobile app via Remote Control. Q4 2026."
status: "seed"
verdict: "pursuing"
tags: ["personal-infra", "claude-code", "whatsapp", "home-server", "search"]
source_files: ["raw/ideas/whatsapp-claude-home-server-seed.md"]
updated: "2026-08-27"
---

# WhatsApp + Claude Home Server

A personal "search over everything" agent: an always-on MacBook M2 at home hosts a Claude Code session with local access to WhatsApp history, the Obsidian vault, and the full disk, reachable from the Claude mobile app anywhere via Remote Control.

*Scope note: personal infrastructure project, not a venture — the template's Traction/Business model/Market/Team sections are intentionally omitted.*

## Problem

Personal data is scattered across silos — WhatsApp chats, Obsidian notes, files on disk — and none of it is searchable from the phone in one place. Cloud assistants can't reach it because the data is local and private by design.

## Solution

One home machine runs the whole stack; the phone is just a window into it.

```
Claude App (phone, anywhere)
        │  Remote Control bridge (outbound HTTPS only, no open ports)
        ▼
MacBook M2 at home (always on)
├── Claude Code session in a workspace folder (CLAUDE.md documents the search routes)
├── wacli  ──► SQLite + FTS5 index of WhatsApp history
├── Obsidian vault (Markdown on disk — searched natively)
└── mdfind (Spotlight CLI — full-disk content search)
```

#### Details

- **WhatsApp: [wacli](https://github.com/openclaw/wacli)** (whatsmeow-based CLI), chosen over the lharries/whatsapp-mcp server — full-text FTS5 search, `--json` output, no MCP token overhead, and a read-only mode as a hard guardrail against Claude sending messages. See [decisions L11](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L11).
- **Remote access: Claude Code Remote Control** — the machine appears as a device card in the Claude app; the session and all data stay local ([L13](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L13)).
- **Obsidian and disk search need no integration** — Markdown is grep-able, `mdfind` covers the rest ([L14-L15](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L14-L15)).
- **macOS always-on config** (pmset no-sleep, autorestart, AlDente charge cap, FileVault on, launchd agents for `wacli sync --follow` and `claude remote-control`): [L18-L23](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L18-L23).

**Still to validate:**
Whether `disablesleep` + clamshell holds up for weeks unattended, and whether wacli's ~20-day QR re-auth is tolerable in practice.

## Why this works

The pieces only recently became assemblable: wacli ships agent-friendly WhatsApp search as a plain CLI, and Claude Code Remote Control (since the Aug 2026 update) gives the phone a secure window into a local session without tunnels or open ports — so the private-data agent can live entirely at home.

#### Details

- **CLI over MCP.** Zero standing context cost, composable with grep/jq, and the read-only env var is a stronger guardrail than permission prompts ([L11](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L11)).
- **The setup scales by one line per source.** New sources (mail archive, downloads) are added by extending the workspace `CLAUDE.md`, not by new integrations ([L16](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L16)).
- **MacBook as server.** Silent, single-digit-watt idle, battery doubles as a UPS ([L12](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L12)).

## Risks

- **WhatsApp ToS / account ban.** wacli uses the unofficial Web API; Meta could restrict the account. Rare in practice, but real ([L27](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L27)).
- **History gap.** Pre-pairing history syncs only partially; "everything" is only true going forward — an argument for pairing early, even before full Q4 buildout ([L28](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L28)).
- **Plaintext message store.** SQLite DB is unencrypted; FileVault plus a locked-down machine is mandatory ([L30](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L30)).
- **Single point of failure.** Home power or ISP outage takes the whole capability down ([L31](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L31)).

## Next moves

Gating constraint: the MacBook M2 is in use by Caspar until roughly Oct/Nov 2026; implementation is planned for Q4 2026 ([timeline L33-L36](../../../raw/ideas/whatsapp-claude-home-server-seed.md#L33-L36)).

1. **Pair wacli early** (any machine, even before the MacBook frees up) so WhatsApp history starts accumulating — the index only grows from pairing onward.
2. Once the MacBook is free: macOS always-on config, FileVault check, launchd agents.
3. Install wacli + Claude Code, set up the workspace folder with `CLAUDE.md` search routes, `WACLI_READONLY=1` by default.
4. Start `claude remote-control`, verify the device card in the Claude app, test "suche über alles" end-to-end from the phone.
5. Extend to further sources (mail archive, downloads) as one-liners in the workspace `CLAUDE.md`.
