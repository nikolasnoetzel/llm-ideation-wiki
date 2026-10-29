# Hot

Current-state snapshot for the next agent session. Rewrite this file in full during the ritual. History goes to `wiki/log.md`, run detail goes to its own page or file, and this file links to it.

Caps: 5 KB in total, 300 characters per line, written for a cold reader. `scripts/check_state.py` enforces them.

## Now

- Notion root is `Fire / Ice 2026 Home` (https://www.notion.so/0c354dd4c51c4b14b9c1eb8f583d7063). Raw, Shared, Wiki and Templates are mapped in `notion.config.json` by hand; titles match the seed tree, so `seed --refresh-existing` adopts them.
- First idea: Trail, an AI-native travel operator with a voice concierge. Overview, four deep dives and eight research pages exist. Verdict: active, exploring. https://www.notion.so/4080260c95ef810f9327ccbf68d2c1d7
- Hub page `Alternativen zu Kälte` on the root lists every pivot alternative with status and next decision date. https://www.notion.so/4080260c95ef8125978ccd40609cae90
- The Notion CLI path is live in the cloud environment: the proxy injects the real integration token for `api.notion.com`, so every shell must `export NOTION_API_TOKEN=placeholder` (any non-empty value) before `scripts/notion_wiki.py`. No token is on disk.
- CLI markdown dialect differs from the MCP one: `get` returns `#### Details {toggle="true"}` with tab-indented children and `<mention-page url=.../>`. Edit the `get` output, then `update`; round trip verified lossless on 2026-10-29.

## Active threads

- Trail: Caspar has not seen it. The gating move is alignment (pivot or four-week exploration with kill criteria). Open question queue lives in the Grill Me page. https://www.notion.so/4080260c95ef81968d44e93be07bf210
- Research quality: every quote in the eight research pages comes from search snippets because the research environment could not open travel or news sites. Re-verify before any number enters a pitch.
- No `wiki/founder` page yet. Trail's Team section carries the founder frame as a user claim (venture-scale). Run `/founder-profile`.

## Long runs

One line per active run: its `runs/` folder, status, and next step. See `docs/agent/workflows.md` § Long runs.

- None.

## Next

- Run `/founder-profile`, then re-read Trail's Team section against it.
- Ask Caspar to read the Trail Overview and the Grill Me verdict sketch; record his position in the Team section.
- Do not run `seed --refresh-existing`: it deletes empty spacer paragraphs on the Home page. Plain `seed` confirmed the mapping on 2026-10-29.
- Use `/paul-graham` on the next alternative; the essay corpus is local in `.agents/skills/paul-graham/references/`.
