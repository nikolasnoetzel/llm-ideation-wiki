---
title: "SH Speed-to-Power"
type: "idea"
summary: "Lean powered-land DevCo engineering fast grid connections for AI data center sites in Schleswig-Holstein via flexible connection agreements, maturity-based queue position, and BESS co-location."
status: "active"
verdict: "exploring"
tags: ["energy", "data-centers", "grid", "schleswig-holstein", "powered-land", "venture-vs-rollup"]
source_files:
  [
    "raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md",
    "raw/notes/2026-08-28-speed-to-power-competitive-landscape-research.md",
    "raw/notes/2026-08-28-powered-land-economics-research.md",
  ]
updated: "2026-08-28"
---

# SH Speed-to-Power

A small (5–8 person) development company that manufactures the scarcest input of Europe's AI buildout — energized megawatts — by carrying data-center sites in Schleswig-Holstein to grid-secured status faster than anyone else, using the 2025–2027 German regulatory shift from first-come-first-served to maturity- and flexibility-based grid connection, then selling or JV-ing the sites to data center operators. Not a software company, not a colo operator: a powered-land developer whose product is time.

## Problem

Grid connection, not capital, is the binding constraint on data center buildout in Germany: new data centers wait up to 7 years on average for a connection (energy-supplier estimates run 10–15), Frankfurt's grid operator says larger new projects have no chance before 2030 and high-performance connections return only in the mid-2030s, and FLAP-D queues across Europe run 7–13 years ([grid mechanics L68-L70](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L68-L70), [economics L37](../../../raw/notes/2026-08-28-powered-land-economics-research.md#L37), [landscape L55](../../../raw/notes/2026-08-28-speed-to-power-competitive-landscape-research.md#L55)).

#### Details

Brandenburg's grid operator alone received 170 data-center enquiries totaling 22 GW since 2022 and connected two ([economics L37](../../../raw/notes/2026-08-28-powered-land-economics-research.md#L37)). Meanwhile Schleswig-Holstein has the opposite problem: 802 GWh onshore plus 2,430 GWh offshore wind curtailed in 2025 (~€74M compensation cost), and a state government explicitly marketing grid headroom — "large consumers like industry or data centers have a real chance of grid connection" (Energy Minister Goldschmidt strategy paper, Nov 2025) ([grid mechanics L60-L65](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L60-L65)).

**Who feels it (ICP):**
Data center operators/investors who need 50–300MW of power on a 2–4 year clock instead of 7+. Institutional capital already pays for exactly this bundle: Goodman/CPP's €8bn European platform advertises "all projects have secured power connections, planning permits" ([economics L48](../../../raw/notes/2026-08-28-powered-land-economics-research.md#L48)). Not locked: which specific operator/fund is the first counterparty.

**Still to validate:**
SH-specific connection lead times for 50–200MW loads (no public figure found); substation-level congestion hotspots (the SH Engpassmanagement report likely has them; not fetchable by proxy).

## Solution

Per-site SPVs; the DevCo carries each site from land options to "secured" status (land + signed grid connection agreement + permits) with €5.5–11.5M at-risk capital over 3–4 years, engineering queue position through the instruments that now legally reward speed: a first-of-a-kind load-side Flexible Connection Agreement with SH Netz/TenneT, maturity scoring in the TSOs' Reifegradverfahren, and BESS co-location. Exit per site: sale or JV to an operator/infra fund, structured as cash plus energization-contingent earn-out.

#### Details

- The FCA legal basis (§17(2b) EnWG, §8a EEG) has been in force since Feb 2025 and is technology-neutral — consumption caps expressly allowed ([grid mechanics L40-L47](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L40-L47)).
- The four TSOs' Reifegradverfahren ("first ready, not first come") has covered data centers and large consumers since 1 April 2026; maturity (land, permits, financing) is the currency — exactly what a developer manufactures ([grid mechanics L42-L43](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L42-L43)).
- Deal template exists: VivoPower–OGDC (Finland, Jan 2026) — ~$45k/MW cash upfront on 291MW, remainder in convertibles triggered "only when successful grid connection happens" ([economics L45-L47](../../../raw/notes/2026-08-28-powered-land-economics-research.md#L45-L47)).
- Interim yield while holding: 50MW/100MWh BESS earns ~€205–240k/MW/yr in 2026 (≈€10–12M/yr gross), trending to ~half by 2030 ([economics L52-L53](../../../raw/notes/2026-08-28-powered-land-economics-research.md#L52-L53)).

**Still to validate:**
No load-side FCA has demonstrably been signed anywhere in Germany — every documented FCA is battery storage; a DC FCA means first-of-a-kind bilateral negotiation until BNetzA standardization in 2027 ([grid mechanics L45-L47](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L45-L47)). Whether SH Netz will engage is the single highest-value unknown — and answerable only through the founders' network.

## Traction

None. Pre-validation. Three raw research notes synthesized into this overview; all three pre-registered kill criteria came back SURVIVES (one reframed). No customer conversations, no site, no capital.

#### Details

Kill-criteria status (pre-registered 2026-08-28, before research ran):

1. **FCA/prioritization applies to large new loads → SURVIVES.** Statute technology-neutral; Reifegradverfahren includes data centers since Apr 2026; Netzpaket §17b prioritization criteria expressly include consumers and data-center siting ([grid mechanics L98](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L98)).
2. **Operators pay for energized sites outside Frankfurt → SURVIVES, reframed.** Powered land is a priced asset class (€2.36M/MW core vs ~€1M/MW secondary, JLL 2026); 63% of new EU capacity lands outside FLAP-D; AI training ≥100MW follows power, not latency. But the premium is powered-vs-unpowered, not secondary-over-prime: the margin is creation cost vs ~€0.5–1M/MW secondary value ([landscape L50-L64](../../../raw/notes/2026-08-28-speed-to-power-competitive-landscape-research.md#L50-L64)).
3. **Final law strips load-side flexibility → SURVIVES (no evidence).** Cabinet-stage changes weakened grid-operator powers, not connectee flexibility; FCA basis predates the Netzpaket. Residual risk until the Sept 2026 Bundestag vote ([grid mechanics L100](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L100)).

**Still to validate:**
First primary signal = a warm SH Netz conversation confirming they would negotiate a load FCA, plus one operator/investor indicating willingness to pay for a secured SH site.

## Why this works

Germany's grid-connection regime is flipping from first-come-first-served to rewarding maturity and flexibility on a knowable 2025–2027 schedule, and the founders' Schleswig-Holstein network sits exactly at the gatekeepers of the best surplus-power region in the country — a window that closes when BNetzA standardizes FCAs (2027) and turns bilateral relationship advantage into an off-the-shelf product.

#### Details

- **Regulatory clock, dated.** FCAs law since Feb 2025; Reifegradverfahren live Apr 2026; Netzpaket (Bundestag Sept 2026) in force ~Jan 2027; BNetzA FCA/BKZ standardization 2027 ([grid mechanics L94-L96](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L94-L96)). The relationship-advantage window is now-to-2027.
- **SH political tailwind.** State government actively recruiting large consumers; live precedents (Langenhorn 150–300MW campus, Schuby energy park, Lyten's Heide takeover including a data center) ([grid mechanics L64-L77](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L64-L77)).
- **Demand relocating to power.** 63% of new EU capacity outside the big five hubs; average new-site distance from major hubs jumping 46km → 175km (2026–28 vs 2022–25) ([landscape L54](../../../raw/notes/2026-08-28-speed-to-power-competitive-landscape-research.md#L54)).
- **Founder-market fit, revised 2026-08-28.** SH network access is table stakes, not the moat — three players hold better SH-specific assets on at least one axis (UNIQ LAND building, OMNIO's founder's grid access, GP Joule's political standing). The defensible claims are (1) load-side FCA craft (zero consumption-side FCAs exist anywhere in Germany) and (2) buyer-side institutional deal packaging toward Goodman/CPP- and Schroders-Greencoat-type capital. Community acceptance (Langenhorn's visible failure mode) remains a genuine founder strength.
- **Category priced by reference rounds.** GridCARE's oversubscribed $64M Series A (Sutter Hill, May 2026) validates VC appetite for the speed-to-power category ([landscape L36](../../../raw/notes/2026-08-28-speed-to-power-competitive-landscape-research.md#L36)).

**Still to validate:**
Whether relationship advantage actually converts to FCA/queue outcomes (vs. a strictly proceduralized BNetzA process where relationships buy nothing durable). Note the curtailment narrative weakens every year — SH onshore curtailment fell 3,350 GWh (2019) → 825 GWh (2025); the durable story is queue-jumping and cheap wind PPAs, not "eating curtailed power" ([economics L56-L57](../../../raw/notes/2026-08-28-powered-land-economics-research.md#L56-L57)).

## Business model

Development margin per MW, realized at site sale: ~€5.5–11.5M at-risk DevCo capital per 100MW site to secured status, exiting at €200–500k/MW (€20–50M) at secured stage or €0.5–1M/MW energized — roughly 2–5x on development capital, ~10x richer per MW than the German solar-RTB analogue (€53k/MW). Margin pool = the spread between manufacturing a grid connection and the market price of powered land; heavy energization capex (€53–90M) is buyer- or SPV-funded, keeping the DevCo lean and high-margin.

#### Details

Reference points: 110kV cable €1.5–3.5M/km; BKZ ~€5–12M per 100MW [uncertain — MV anchor €118/kVA; BGH July 2025 confirmed BESS pays BKZ too]; 2h BESS €700k/MW (Modo Q2 2026); Orrön 76MW solar RTB sold at ≈€53k/MW; TotalEnergies–VSB DevCo exit ≈€85-90k/MW-pipeline ([economics L82-L104](../../../raw/notes/2026-08-28-powered-land-economics-research.md#L82-L104)).

**Still to validate:**
No German secondary-market powered-land transaction comps exist publicly — the €0.5–1M/MW exit value is derived from pan-European broker tiers, both marked uncertain. SH-area 110kV BKZ level unverified. Flexibility-as-a-service fee levels: nothing found.

## Market

Germany's national Data Centre Strategy (18 March 2026) targets doubling DC capacity and at least quadrupling AI/HPC capacity by 2030; SH Netz's own scenario work sees distribution-level data center demand going from <2 GW today toward 37 GW by 2045 [uncertain: E.ON-area vs SH-only]. At 100MW per site and €20–50M development margin each, a 5-site pipeline is a €100–250M-margin company — venture-scale without ever operating a server.

#### Details

See [grid mechanics L81-L84](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L81-L84) and [L67](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L67). Buyer depth in northern Germany is the open flank: 72% of German capacity is still Rhine-Main, and Langenhorn has no announced anchor tenant.

**Still to validate:**
A named operator or fund expressing indicative willingness to pay for a secured SH site (kill-criterion #2's remaining primary-evidence gap).

## Team

Nikolas (ex-Bain; 4 years operating in the northern German solar/energy market; trust-based network into SH Netz/HanseWerk, Stadtwerke Kiel, SH state politics; superpower: converting trust into commitments from owners, politicians, utilities, investors) + Caspar Freiberg (ex-Bain; ex-TikTok Strategy & Ops European Markets Lead; co-founded Lakestar-backed Twentyfour Industries; analysis and slide/deal execution speed). Both explicitly want a small, elite, high-margin team — the development model is the shape that preference fits.

#### Details

Origin decision (settled in the 2026-08-28 grill): this idea is the venture-route alternative to the Fire/Ice KK buy-and-build, whose validated reality (≈20% recurring revenue vs 40–50% hypothesis, 10–15% margins vs 20%, structural Fachkräfte headwind) contradicts the founders' revealed preferences. Services revenue scales with billable heads; development revenue does not — that, not team size per se, is where high margin comes from.

Named gaps: (a) grid/electrical engineering — nobody on the team has negotiated a Netzanschluss or built a substation; path: first senior hire or advisor from a DSO/TSO or wind-developer background; (b) data-center-side credibility with operator counterparties; path: advisor or first anchor-tenant LOI.

**Still to validate:**
Caspar's actual commitment to this thesis (conversations so far predate this research); whether the SH network converts (see Next moves).

## Risks

- **SH is already occupied.** UNIQ LAND Development (founded 2026, Keim/Kampkötter) is executing the identical powered-land play at Langenhorn, Nordfriesland (150–300MW), citing the same wind-surplus rationale. First-mover positioning is dead; differentiation (FCA structuring, BESS co-location, community-acceptance capability, different sub-regions) is mandatory. → [landscape L16-L24](../../../raw/notes/2026-08-28-speed-to-power-competitive-landscape-research.md#L16-L24)
- **First-of-a-kind FCA risk.** Zero load-side FCAs signed anywhere; DSO drafting behavior on the storage side has been restrictive ("restrict… instead of enabling" — Green Flexibility). The bilateral-negotiation premise may die in SH Netz's legal department. → [grid mechanics L30](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L30), [L45-L47](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L45-L47)
- **Exit-value uncertainty.** No German powered-land transaction comps; the VivoPower precedent says buyers pay mostly on energization (earn-out), so realized cash at secured stage may be far below the €20–50M headline. → [economics L45-L47](../../../raw/notes/2026-08-28-powered-land-economics-research.md#L45-L47), [L100](../../../raw/notes/2026-08-28-powered-land-economics-research.md#L100)
- **Municipal opposition.** Langenhorn's hostile town hall (June 2026) shows rural SH can strand a site pre-permit; community acceptance is part of the product. → [landscape L23](../../../raw/notes/2026-08-28-speed-to-power-competitive-landscape-research.md#L23)
- **Legislative residual.** Netzpaket final text lands only with the Sept 2026 Bundestag vote (force ~Jan 2027); FCAs survive regardless, but the prioritization superstructure could shift. → [grid mechanics L53-L56](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md#L53-L56)
- **Gridfield opacity.** The €15M/€50M funding figures are unverified hearsay (zero public corroboration); its registry charter is broad (incl. operation) and its geography unknown — it may or may not collide. → [landscape L13](../../../raw/notes/2026-08-28-speed-to-power-competitive-landscape-research.md#L13)
- **SH incumbents with superior local assets** (added 2026-08-28 from user testimony + search). GP Joule (Reußenköge; full generation/H2 value chain, deep SH political access — Minister-President-visit level) is the gorilla *if* it enters DC powered land; no public DC project found, and its organization is generation-side (sells electrons/H2, feed-in connections). OMNIO energy GmbH (Dr. Olaf Jäger-Roschko, ex-GP-Joule-context per user, 25–30+ yrs SH energy; fee-based advisory: feasibility, grid connection & permitting planning, financing, EPC coordination for BESS/H2/RE) is a services firm, not an at-risk principal — better read as first-advisor-to-recruit than competitor, but confirms SH grid expertise is available to any entrant. Net effect: the SH-network claim is downgraded from moat to table stakes; differentiation must rest on load-side FCA craft + institutional buyer access. [uncertain: OMNIO/GP Joule read based on search extraction + user testimony; omnio-energy.de not directly fetchable.]

## Next moves

Gating move: the SH Netz conversation — everything else (differentiation, capital, Caspar commitment, Fire/Ice decision) depends on whether the load-side FCA premise converts from statute to practice.

**To validate (6–8 week sprint, Mom-Test style):**

1. SH Netz / HanseWerk: would they negotiate a flexible connection for a 50–200MW load, at which substations, on what timeline? (Answers kill-criterion #1's practice gap + the hotspot map research couldn't reach.)
2. Stadtwerke Kiel / SH state politics: would the Land champion a flagship flexible data-center project; what died and why at Langenhorn?
3. One DC operator or infra investor: indicative €/MW for a secured SH site and preferred deal structure (validates the exit side; targets: Goodman/CPP-type platforms, NDC-Garbe, Schroders Greencoat).
4. Ludwig Schönack: verify Gridfield's actual model, geography, and whether collision or collaboration — decide beforehand what to disclose.
4b. Olaf Jäger-Roschko (OMNIO): sound out as advisor/first grid hire — he closes the "nobody has negotiated a Netzanschluss" gap and his OMNIO practice is fee-based, so a principal offering advisory equity or a site-#1 co-development stake is aligned, not competitive. Also the cheapest way to learn whether GP Joule has DC ambitions.
5. Caspar: put this page and the three raw notes in front of him; decision on co-founding basis.
6. Fire/Ice disposition: if 1–3 come back warm, park Fire/Ice explicitly (update its status; the KK network remains an asset — cooling trades are data-center suppliers).

**To build (once validated):** ~€1–2M pre-seed from angels/family offices/strategic (Stadtwerk-adjacent or wind developer contributing land as in-kind equity — no EU institutional-seed precedent exists in this model); first senior grid-engineering hire; 2–3 site options in SH congestion-relief locations.

## Related

- [Raw: SH Netzpaket grid mechanics](../../../raw/notes/2026-08-28-sh-netzpaket-grid-mechanics-research.md) — regulatory timeline, FCA practice, SH quantification, Northvolt Heide.
- [Raw: Speed-to-power competitive landscape](../../../raw/notes/2026-08-28-speed-to-power-competitive-landscape-research.md) — layer map, UNIQ LAND, Gridfield, powered-land pricing.
- [Raw: Powered-land economics](../../../raw/notes/2026-08-28-powered-land-economics-research.md) — 100MW reference-site model, SPV structure, funding precedents.
