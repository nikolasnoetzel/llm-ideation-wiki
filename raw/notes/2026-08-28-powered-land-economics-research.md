# 2026-08-28 — Powered-land economics research (100MW SH reference site)

Originating question: What does a lean powered-land DevCo/SPV earn on a ~100MW data-center reference site in Schleswig-Holstein — cost stack, exit value of energized land, monetization structure — and who writes the first check?

Method note: WebFetch was blocked by the egress proxy for most target domains (thenextweb.com, orron.com confirmed blocked). All findings below therefore rely on WebSearch result extraction; quotes are as returned by the search tool, flagged where the underlying page could not be opened. No URL or quote is fabricated; every URL below was returned by a search.

---

## 1. Cost stack for a 100MW site in northern Germany

### Grid connection (110kV) hardware
- **Source:** FS CID, "Was kostet ein Netzanschluss für ein Rechenzentrum?" — https://www.fs-cid.com/post/netzanschluss-rechenzentrum-kosten (no publication date visible in search results)
- Via search-result extraction: "A 110 kV cable costs between 1.5 and 3.5 million euros per kilometer, depending on laying depth, soil conditions, and route planning. If the next suitable grid connection point is several kilometers away, the cable route alone can cost a double-digit million amount." Also: redundant dual connections "can double grid connection costs in extreme cases."
- [uncertain] Exact substation (Umspannwerk) cost for a 100MW customer bay was not returned by searches; industry rule-of-thumb €10–25M for a customer 110kV substation is used below as `[assumption]`.

### Baukostenzuschuss (BKZ)
- **Source:** Bundesgerichtshof press release, 15 July 2025 — https://www.bundesgerichtshof.de/SharedDocs/Pressemitteilungen/DE/2025/2025129.html
  - Via search extraction: the BGH "decided that grid operators can demand a BKZ for battery storage systems that draw power from the grid, ending previous legal uncertainty" (ruling of 2025-07-15). So a co-located BESS **also** pays BKZ on its grid-draw capacity — this is a real cost line, not avoidable.
- **Source:** interconnector.de blog on BKZ for battery storage — https://www.interconnector.de/energieblog/batterievermarktung/baukostenzuschuss-fuer-batteriespeicher-was-bedeutet-die-entscheidung/
  - Via search extraction: "For medium voltage (Mittelspannung) connections, the construction cost contribution was 118.43 euros net per kilovoltampere as of January 1, 2022" and BKZ is computed on the performance-price model ("BKZ = Performance price (>2,500 h/a) of the network level × ordered connection capacity").
- **Source:** BNetzA BKZ overview — https://www.bundesnetzagentur.de/DE/Fachthemen/ElektrizitaetundGas/Netzanschluss/Baukostenzuschuesse/start.html
  - Via search extraction: "The Federal Network Agency (BNetzA) believes transmission system operators should levy a construction cost contribution of at least 20% of the performance price."
- [uncertain] No search result gave a specific €/kW BKZ at 110kV in the SH Netz area. Using the MV anchor (€118/kVA) and the fact that HV-level BKZ is typically lower per kW, the model below uses €50–120/kW → **€5–12M for 100MW** `[assumption]`.

### BESS capex (2026)
- **Source:** Modo Energy, "German BESS investment outlook: Executive summary" (Q2 2026) — https://modoenergy.com/research/en/germany-battery-investment-outlook-q2-2026-executive-summary
  - Via search extraction: 2-hour German BESS capex **€700k/MW**; 4-hour **€935k/MW**; "Near-term 2-hour revenues for German BESS are €240k/MW, but these are expected to halve by 2030… wholesale arbitrage then accounting for 95% of revenue, stabilizing around €125k/MW."
  - Implied: 2h ≈ €350/kWh installed; 4h ≈ €234/kWh. Note the search summary contained a garbled per-kWh calculation for the 2h system; the €/MW figures are the reliable ones.
- **Cross-check source:** Ember, "How cheap is battery storage?" — https://ember-energy.org/latest-insights/how-cheap-is-battery-storage/ (Europe 4h LFP EPC "roughly €180–260/kWh installed" via search extraction) — consistent with Modo's 4h number.

### Land (SH)
- **Source:** grundstueckspreise.info Schleswig-Holstein — https://grundstueckspreise.info/bundesland/schleswig-holstein (Sept 2025): "the average land price is 227.23 euros per square meter" — residential-skewed statewide average, not usable directly.
- [uncertain] Searches returned **no** clean €/m² figure for rural industrial/greenfield land in SH. Rural Gewerbegebiet land in SH is typically far below the statewide residential average; model uses €25–60/m² `[assumption]`. A ~100MW campus + BESS needs roughly 15–25 ha `[assumption]` → **€4–15M land**, or much less if secured via options (typical developer practice: 1–5% of value per year in option fees `[assumption]`).

### Soft costs / development timeline
- **Source (renewables analogue):** BMWK cost study for onshore wind (windmonitor/Fraunhofer via search) — https://windmonitor.iee.fraunhofer.de/windmonitor_en/3_Onshore/5_betriebsergebnisse/3_investitionskosten/ — via search extraction: for 2024–2026 commissioned wind, "auxiliary investment costs (excluding foundation) total €506 per kW, with planning costs accounting for 40% of these auxiliary costs" and grid-connection distance adds "€50,000 to €100,000 per MW" per extra km to the substation.
- **Grid-connection wait times (the moat):** Clean Energy Wire — https://www.cleanenergywire.org/news/data-centres-germany-planning-own-fossil-fuel-plants-citing-slow-grid-connections-report — via search extraction: "New data centers in Germany wait an average of up to 7 years for a grid connection, though some estimates from energy suppliers suggest connection to the grid in Germany takes 10 to 15 years." Also (regional demand signal): "The local grid operator in Brandenburg has received 170 enquiries from data centres with a total capacity of 22 GW since 2022, but only two data centres with a capacity of 100 MW have been connected so far."
- **Reform in progress:** Norton Rose Fulbright on the German Netzanschlusspaket (EnWG amendment) for BESS/data-center grid connections — https://www.nortonrosefulbright.com/en/knowledge/publications/ddde3596/grid-connections-for-bess-and-data-centers-reimagined — flexible/conditional connection agreements are the policy direction. [uncertain: draft-bill stage per search extraction; final rules not confirmed.]

## 2. Value of energized / powered land

- **Source:** TNW (The Next Web), "63% of Europe's new data centre capacity is now going somewhere other than the big five" — https://thenextweb.com/news/europe-data-centres-leaving-flap-d-grid-queues-land — via search extraction (page fetch blocked by proxy): "Prime powered land in Europe now costs €2.26 million per megawatt, up 82% since 2021… primary markets carry a 2.3 times premium over secondary sites and four times over tertiary ones." [uncertain: could not open the article to identify the underlying report (likely a broker study); treat €2.26M/MW as prime-FLAP-D, not SH.]
  - Implied secondary ≈ €1.0M/MW, tertiary ≈ €0.55–0.6M/MW. SH is tertiary-to-secondary.
- **US benchmark (marked as such):** Cushman & Wakefield 2026 Data Center Development Cost Guide — https://www.cushmanwakefield.com/en/united-states/insights/data-center-development-cost-guide — returned by search but per-MW powered-land figures were not extractable; cited as existence of a benchmark, no number used.
- **Closest actual transaction (Nordics, Jan 2026):** VivoPower–OGDC — https://www.globenewswire.com/news-release/2026/01/22/3223700/0/en/vivopower-to-acquire-ogdc-securing-291mw-of-powered-sites-in-finland-with-sub-4-per-kwh-renewable-power-for-sovereign-ai-data-centers.html (announced 2026-01-22)
  - Via search extraction: "approximately $13 million cash upfront… and the issuance of convertible preference shares with a conversion price of $15 per ordinary share which is triggered only when successful grid connection happens"; 291MW "expected to be grid-connected within 12 months," hydropower "sub-4¢ per kWh."
  - Read-through: upfront cash ≈ **$45k/MW** for near-energized Finnish sites, with most consideration **contingent on energization** — i.e., the market prices the grid connection, not the land, and pays for it on delivery. This contradicts the €2.26M/MW headline unless that figure refers to fully-entitled prime-market sites [contradiction surfaced: €2.26M/MW (prime FLAP-D, broker stat) vs ~$45k/MW upfront + earn-out (tertiary Finland, real deal). SH sits between; deal structure (earn-out on energization) matters as much as headline €/MW].
- **Platform validation:** Goodman/CPP Investments €8bn European DC platform — https://www.datacenterdynamics.com/en/news/goodman-cpp-investments-establish-8bn-european-data-center-plaform/ — via search extraction: "All projects have secured power connections, planning permits, and have substantially progressed site infrastructure works" — i.e., institutional capital pays for exactly the bundle a powered-land DevCo produces.

## 3. Alternative monetizations (hold instead of / before sale)

- **BESS revenue stacking, Germany 2026:** Modo Energy benchmark — https://modoenergy.com/research/en/germany-revenue-bess-benchmark-july-2026-summer-solar-spreads-afrr-fcr-day-ahead-scarcity — via search extraction: 2h German BESS revenues "€205k/MW/yr in July 2026"; April 2026 "€218k/MW/yr"; July 2026 "aFRR-up prices dropped 35% to €10.1/MW/h… FCR revenue more than doubled to €48k/MW/yr."
  - Modo outlook (exec summary, above): €240k/MW near-term → ~€125k/MW by 2030 as ancillary saturates. Spread vs €700k/MW capex: ~3–4 yr gross payback now, lengthening.
  - Enervis index cross-check — https://www.ess-news.com/2026/04/29/enervis-battery-storage-index-german-bess-revenues-rebound-in-march-amid-middle-east-tensions/ (2026-04-29).
- **New stream:** Germany inertia-service market launching 2026 (grid-forming BESS) — https://www.hsfkramer.com/notes/energy/2025-posts/germany-to-launch-inertia-service-market-in-2026-new-revenue-stream-for-grid-forming-bess/ — upside optionality, no € figure extracted.
- **Curtailed wind in SH (the resource story):** SH state report on Engpassmanagement — https://www.schleswig-holstein.de/DE/fachinhalte/N/netzausbau/Downloads/bericht_engpassmanagement_sh.pdf?__blob=publicationFile&v=3 and top agrar — https://www.topagrar.com/energie/news/weniger-abregelungen-von-windparks-in-schleswig-holstein-13156679.html — via search extraction: onshore curtailment in SH fell to "825 GWh" in 2025 (vs peak "rund 3.350 GWh" in 2019); "Die Schleswig-Holstein Netz AG hat 2025 rund 802 Gigawattstunden an Land abgeregelt, mit Kosten von rund 74,2 Millionen Euro" (≈ €92/MWh average compensation cost).
  - [uncertain — thesis-relevant] Curtailment is **declining** (grid buildout is working), so "eat curtailed wind" is a shrinking standalone rationale; the durable rationale is cheap grid capacity + wind PPAs, not curtailed energy per se. 825 GWh ≈ 94MW average — roughly ONE 100MW site's annual load, so the resource is real but not deep.
- **Redispatch context:** nationwide congestion-management cost "rund 3,0 Mrd. Euro" (2024, preliminary) via the same search set (energie-experten.org — https://www.energie-experten.org/erneuerbare-energien/oekostrom/stromnetz/redispatch).
- Flexibility-as-a-service fees for DC loads in Germany: **no usable € figures returned by searches** — stated explicitly as a gap.

## 4. Structure: what lean developers earn (renewables analogue)

- **RTB sale comp (solar, Germany):** Orrön Energy sells 76MW German solar project to Saxovent "for a total consideration of €4.0 million" — https://www.orron.com/orron-energy-announces-the-sale-of-a-76-mw-solar-project-in-germany/ — ≈ **€53k/MW at RTB** (via search extraction; page fetch blocked). Other RTB deals without prices: Visiolar 95MWp → Sunovis (Brookfield-owned) — https://www.renewable-energy-industry.com/news/press-releases/pm-8712-visiolar-completes-sale-of-a-95-mwp-ready-to-build-solar-pv-project-in-germany-to-sunovis ; Deutsche WindXperts 69MW wind RTB → Exus — https://www.renewable-energy-industry.com/news/world/article-7146-strong-interest-in-ready-to-build-wind-projects-exus-deepens-its-presence-in-the-german-wind-market-with-acquisition-of-69-mw-wind-farm-project
  - [uncertain] German wind RTB typically trades well above solar per MW (permits are scarcer); no wind €/MW returned by searches.
- **DevCo exit comp:** TotalEnergies acquired VSB Group (Dresden) for **€1.57bn** (announced Dec 2024, closed 2025-04-02) with "a European pipeline of 18GW" plus ">475 MW in operation or under construction" — https://www.powerengineeringint.com/renewables/strategic-development/totalenergies-aquires-german-vsb-group-for-e1-57bn/ and https://totalenergies.com/news/press-releases/integrated-power-renewables-totalenergies-implements-its-strategy-capital — crude read-through ≈ **€85–90k per MW of pipeline** (ignoring operating-asset value, so pipeline-only value is lower).
- **Powered-land is the same playbook at higher unit value:** a DC site with secured 100MW connection is worth per-MW multiples of a solar RTB project (see §2), with the same lean cost base — the margin lives in the grid-connection allocation and entitlements, not construction.

## 5. Who writes the first check

- **GridCARE (US, closest funded analogue in grid-capacity-for-DC):** "$13.5 million in seed funding" (emerged from stealth May 2025), then $64M Series A "led by Sutter Hill Ventures, with backing from venture capitalist John Doerr, bringing its total funding to $77.5 million" — https://www.datacenterdynamics.com/en/news/gridcare-raises-64m-in-series-a-funding-round/ and https://www.latitudemedia.com/news/gridcare-raises-oversubscribed-64-million-series-a/ — i.e., top-tier US VC funds the software/optionality layer at seed. (US comp, marked as such.)
- **Infra capital enters at platform stage, not seed:** Schroders Greencoat green digital infrastructure platform (50:50 JV with Greencoat Renewables), first investment "a brownfield industrial site in Ireland planned for a data centre project" — https://schroders-capital.prezly.com/schroders-greencoat-announces-new-green-digital-infrastructure-platform-and-first-data-centre-investment — infra funds will fund per-site SPVs once a credible team holds land + a connection pathway.
- **Strategics buy the outcome:** Goodman/CPP (€8bn platform, above); Partners Group majority stake in AVK plus ">USD 1 billion" growth capital for DC power solutions — https://www.partnersgroup.com/en/news-and-views/press-releases/investment-news/detail?news_id=80e9420b-67c0-43f1-b298-e0dfa2aba73e
- **Deal-structure precedent for a DevCo exit:** VivoPower/OGDC (above): small cash upfront + contingent consideration triggered "only when successful grid connection happens" — a template for how a SH DevCo would actually get paid.
- No search result returned a named **European seed investor in a pure powered-land DC developer**; a Munich "gridfield GmbH" (HRB 308027) exists per Northdata — https://www.northdata.com/gridfield%20GmbH,%20M%C3%BCnchen/HRB%20308027 — but no funding information was returned. Stated as a gap.

---

### Synthesis

Back-of-envelope for a 100MW (grid-draw) SH reference site, lean DevCo in a per-site SPV. Two stages: (A) "secured" = land control + signed grid-connection agreement + B-Plan/permits; (B) "energized" = substation built, BKZ paid, BESS optional.

**Stage-A cost (DevCo's at-risk capital):**
| Item | € | Basis |
|---|---|---|
| Land options / partial acquisition (15–25 ha) | €0.5–3M | §1 land [assumption: options at 1–5%/yr, not full purchase; full purchase €4–15M] |
| Grid studies, connection application, reservation | €0.5–1.5M | [assumption; no fee schedule returned] |
| Permitting, B-Plan, legal, engineering (soft costs) | €1.5–3M | scaled from wind auxiliary-cost data (€506/kW incl. hardware; planning = 40% share) — §1 |
| Team, 3–4 yrs × ~€1M/yr | €3–4M | [assumption: 5–8 FTE lean shop] |
| **Total to "secured/RTB" status** | **€5.5–11.5M** | |

**Stage-B additional capex (usually the buyer's or SPV co-investor's money):**
| Item | € | Basis |
|---|---|---|
| 110kV line, 2–5 km | €3–17.5M | €1.5–3.5M/km (FS CID) |
| Customer substation | €10–25M | [assumption] |
| BKZ on 100MW | €5–12M | €50–120/kW [uncertain — anchored on MV €118/kVA + BNetzA ≥20%-of-Leistungspreis rule] |
| Optional BESS 50MW/100MWh (2h) | €35M | €700k/MW (Modo Q2 2026) |
| **Total to energized (incl. BESS)** | **€53–90M** | |

**Exit value:** tertiary/secondary powered land at €0.5–1.0M/MW (derived from €2.26M/MW prime ÷ 2.3–4x premium — both [uncertain]) → **€50–100M for 100MW energized**. Even at half that (deep discount for SH's lack of fiber/latency ecosystem, and the VivoPower precedent that buyers pay mostly on energization), a **secured-stage sale at €200–500k/MW = €20–50M** against €5.5–11.5M at-risk cost → **~2–5x multiple on development capital, €15–40M development margin**, versus €53k/MW for solar RTB — the DC-load premium is the whole business.

**Interim yield if holding:** 50MW BESS at €205–240k/MW/yr (Modo, 2026) ≈ **€10–12M/yr gross** now, trending to ~€6M/yr by 2030 — covers SPV holding costs and de-risks the wait, but doesn't replace the land sale.

**Capital to first energized site:** €5.5–11.5M to secured status (seed + Series A territory); the further €50–90M is SPV project finance from an infra fund (Schroders-Greencoat-style JV) or paid by the acquirer via a VivoPower-style contingent structure. **First €1M:** realistically angels/family offices + a strategic (Stadtwerke/SH Netz-adjacent player or a wind developer with stranded sites contributing land as in-kind equity); no European precedent for institutional seed in this exact model was found — US precedent (GridCARE: Sutter Hill, John Doerr) shows tier-1 VC appetite for the adjacent software layer.

**Key contested points:** (1) €2.26M/MW prime powered land is a broker headline I could not open/verify [uncertain]; (2) SH curtailment is shrinking (825 GWh 2025 vs 3,350 GWh 2019) — the "curtailed wind" narrative weakens every year, the "7–15-year grid queue" narrative strengthens; (3) BKZ now confirmed payable by BESS (BGH 2025) — worsens co-location economics vs older assumptions; (4) 110kV BKZ level in SH Netz area unverified.

---

## Suggested wiki integration

Section: **Business model / Economics** of the powered-land DC developer idea overview (and the "Who funds this" line under Go-to-market).
Draft diff: "Replace the placeholder unit economics with: ~€6–12M at-risk dev capital to a secured 100MW SH site, exit €20–50M at secured stage (up to €50–100M energized incl. €53–90M buyer-funded capex), interim BESS yield ~€10M/yr on 50MW; first check = angels/FO/strategic (no EU institutional-seed precedent found; US comp GridCARE $13.5M seed), infra funds enter at SPV stage (Schroders Greencoat precedent), exits structured as cash + energization-contingent earn-out (VivoPower/OGDC precedent)."
