# Seed: WhatsApp + Claude home server ("Suche über alles")

Captured from an ideation conversation on 2026-08-27. Personal infrastructure project, not a venture idea.

## Core idea

Run an always-on machine at home that hosts a Claude Code session with access to all personal data sources — WhatsApp history, Obsidian vault, local files. Access it remotely from the Claude mobile app, so saying "suche über alles nach X" from anywhere fans out across every source.

## Decisions made

- **WhatsApp integration via `wacli`, not an MCP server.** Originally considered lharries/whatsapp-mcp (Go bridge on whatsmeow + Python MCP server). Switched to wacli (openclaw/wacli, originally by Peter Steinberger): same whatsmeow foundation, but a plain CLI — `wacli sync`, `wacli search`, `wacli send` — that Claude Code calls over Bash. Advantages: SQLite FTS5 full-text index (millisecond offline search), no MCP tool-definition token overhead, composable with grep/jq, built-in `--json` output, read-only mode (`WACLI_READONLY=1`) as a hard guardrail against Claude sending messages.
- **Hardware: MacBook M2** as the always-on machine. Silent, single-digit-watt idle, battery doubles as a built-in UPS.
- **Remote access via Claude Code Remote Control** (`claude remote-control`), not a tunnel/Tailscale/custom connector. Since the Aug 2026 update the machine appears as a device card in the Claude mobile app; the session (including all local tool access) runs entirely on the home machine, outbound HTTPS only, no open ports.
- **Obsidian needs no integration.** The vault is Markdown on disk; Claude Code searches it natively. Vault must sync to the MacBook (Obsidian Sync or Syncthing; if iCloud, disable "Optimize Mac Storage" so files stay materialized).
- **Full-disk search via `mdfind`** (Spotlight CLI) — content search across PDFs, mail, Office files, called over Bash.
- **Glue: a `CLAUDE.md` in the workspace folder** the Remote Control session starts in, documenting the search routes (wacli for WhatsApp, vault path for notes, mdfind for everything else). Each new source is one more line.

## macOS always-on configuration

- `sudo pmset -a sleep 0`, `sudo pmset -a disablesleep 1` (no sleep with lid closed), `sudo pmset -a autorestart 1` (reboot after power loss).
- Permanently on charger; cap charge at ~70–80% with AlDente.
- FileVault stays on (message DB sits unencrypted in SQLite); accept manual unlock after rare reboots. Disable automatic macOS updates, apply manually — fits the ~20-day wacli QR re-auth rhythm.
- `wacli sync --follow` and `claude remote-control` as launchd LaunchAgents.

## Known risks / caveats

- wacli uses the unofficial WhatsApp Web API (whatsmeow) — formally violates Meta ToS; theoretical (in practice rare) account-ban risk.
- WhatsApp history before pairing syncs only partially (best-effort recovery from the phone); the index becomes complete only going forward.
- Session re-auth via QR scan roughly every 20 days — requires physical access to the phone.
- All messages unencrypted in local SQLite → FileVault mandatory, no exposed services on the machine.
- Single machine at home = single point of failure for the whole setup (power, ISP outage).

## Timeline

- Implementation planned for **Q4 2026**.
- Gating constraint: **Caspar is using the MacBook M2 for another 1–2 months** (until roughly Oct/Nov 2026).

## References

- wacli: https://github.com/openclaw/wacli / https://wacli.sh
- whatsapp-mcp (rejected alternative): https://github.com/lharries/whatsapp-mcp
- Claude Code Remote Control: https://code.claude.com/docs/en/remote-control
