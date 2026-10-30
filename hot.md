# Hot

Current-state snapshot for the next agent session. Rewrite this file in full during the ritual. History goes to `wiki/log.md`, run detail goes to its own page or file, and this file links to it.

Caps: 5 KB in total, 300 characters per line, written for a cold reader. `scripts/check_state.py` enforces them.

## Now

- Notion root is `Fire / Ice 2026 Home` (https://www.notion.so/0c354dd4c51c4b14b9c1eb8f583d7063). Raw, Shared, Wiki and Templates are mapped in `notion.config.json`. Do not run `seed --refresh-existing`; plain `seed` is safe.
- First idea: Trail, an AI-native travel operator with a voice concierge. Overview, four deep dives, ten research pages, nine verification pages, two founder notes. Verdict: active, exploring. https://www.notion.so/4080260c95ef810f9327ccbf68d2c1d7
- Inventory thesis refined 2026-10-30: target top small operators with little web presence (jeep tours, Nepal treks, treehouses, jungle safaris), not mainstream permits. Research says capacity is real, access is not: no free-sale allotments, 15% entry net rate.
- Paul Graham corpus: 234 essays mirrored as child pages under Raw → Shared → Paul Graham Essays (https://www.notion.so/4080260c95ef8186b4dced64475cc9eb) and local in `.agents/skills/paul-graham/references/`. `/paul-graham` was applied to Trail; result sits in Grill Me.
- Hub page `Alternativen zu Kälte` lists every pivot alternative plus a YC RFS Winter 2027 fit note. https://www.notion.so/4080260c95ef8125978ccd40609cae90
- Notion CLI path: the cloud proxy injects the integration token for `api.notion.com`, so every shell must `export NOTION_API_TOKEN=placeholder` before `scripts/notion_wiki.py`. No token on disk. Edit the `get` output (toggle and mention-page dialect), then `update`.
- Known CLI limit: `create` cannot pass a title that contains a colon (inline `path=value` parsing). Rename afterwards with `ntn api -X PATCH /v1/pages/<id> -d @file.json`.

## Active threads

- Trail: Caspar has not seen it. Gating move is alignment (pivot or four-week exploration with kill criteria). Open question queue in Grill Me. https://www.notion.so/4080260c95ef81968d44e93be07bf210
- Two disconfirmable supply tests now sit in Overview § Solution: at least 3 of 20 target operators grant a 14-day hold without deposit; half of the first 20 suppliers grant 25%+ net rates within 12 months.
- Research quality: the 2026-10-29 run was verified at primary sources (340 claims: 223 confirmed, 63 corrected). The 2026-10-30 pages opened every cited source except arival, phocuswire and tripadvisor (403). https://www.notion.so/4080260c95ef814ab3cdfc79b8610e38
- No `wiki/founder` page yet. Trail's Team section carries the founder frame as a user claim (venture-scale). Run `/founder-profile`.
- Memory: five memories plus the About page in Notion Memory record root, Trail codename, CLI rule, preferences and Fire / Ice context (saved 2026-10-30).

## Long runs

One line per active run: its `runs/` folder, status, and next step. See `docs/agent/workflows.md` § Long runs.

- None.

## Next

- Ask Caspar to read the Trail Overview and the Grill Me verdict sketch; record his position in the Team section.
- Run `/founder-profile`, then re-read Trail's Team section against it.
- Supply test in one corridor (Nepal tea-house treks or northern Tanzania walking safaris): 20 operator conversations from the public register, Zicasso-style trial itinerary on the best five, signed net-rate letters, not conversations.
- Open gaps worth a browser: official commission terms of TourRadar, GetYourGuide, Bookmundi and Evaneos; Arival primary data; register counts for TAAN, KATO, TATO; insurer cost for organizers under EUR 10m.
