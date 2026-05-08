---
title: "Claude-Code-Playbook für Fire/Ice-DD"
type: "note"
summary: "Working-Folder-Konvention pro Deal, CLAUDE.md-Vorlage, copy-paste Prompt-Templates pro Stage, vorgeschlagene Slash-Commands, MCP-Setup-Empfehlungen, OCR/Excel-Patterns. Alles für Niko & Caspar mit Claude Code Max."
status: "active"
tags: ["fire-ice", "dd", "claude-code", "prompts", "slash-commands", "mcp", "playbook"]
source_files:
  - "raw/notes/2026-05-07-anthropic-finance-agents-memo.md"
updated: "2026-05-08"
---

# Claude-Code-Playbook für Fire/Ice-DD

Das ist die operationale Schnittstelle zwischen unserer DD-Methodik und Claude Code Max. Pro Deal ein Codename-Ordner, pro Stufe Standard-Prompts, ein konsistentes CLAUDE.md, das Claude die Thesis und den aktuellen Stand jedes Mal automatisch lädt. Wir wollen Claude nicht jedes Mal neu erklären müssen, was Fire/Ice ist und was wir suchen — und wir wollen Claude nicht in Versuchung führen, eine generische DD aus seinem Trainingskorpus zu produzieren.

## Working-Folder-Konvention

Pro Deal ein Codename-Ordner unter `~/fire-ice-deals/`. Codename ist sequentiell (Alpha, Bravo, Charlie, Delta, …) — nicht der Klarname, weil wir mit Claude in Cafés und Coworking arbeiten. Klarname-Mapping nur in einer privaten Datei `~/fire-ice-deals/_codename-map.md` (verschlüsselt mit `gpg --symmetric` falls paranoia-relevant).

```
~/fire-ice-deals/
├── _codename-map.md.gpg              # Klarname↔Codename, verschlüsselt
├── _shared/
│   ├── CLAUDE.md                     # Globale Fire/Ice-Context, lädt in jedem Deal-Run
│   ├── manual/                       # Symlink auf llm-ideation-wiki/wiki/ideas/cdd-fdd-fire-ice
│   ├── notion-mcp.json               # Notion-MCP-Config (read-only, Workspace fire-ice)
│   ├── skr03-kontenrahmen.md         # DATEV SKR03 Referenz für Claude
│   ├── skr04-kontenrahmen.md         # DATEV SKR04 Referenz für Claude
│   ├── prompt-templates/             # Reusable Prompt-Templates (siehe unten)
│   ├── ksd-library.md                # 30 Standard-KSDs für Industriekälte-DD
│   └── red-flag-library.md           # Die 18+30 Red Flags
└── alpha/                            # Pro Deal
    ├── CLAUDE.md                     # Pro-Deal-Context (Thesis, KSDs, Status)
    ├── 01-public/
    ├── 02-ioi/
    ├── 03-dataroom/
    ├── 04-spa/
    └── _trash/
```

**Warum `_shared/`?** Damit der Fire/Ice-Kontext nicht 12 Mal kopiert wird, sondern Claude immer aus einer zentralen Quelle liest. `~/fire-ice-deals/_shared/CLAUDE.md` enthält die Thesis (1-Pager-Auszug), die KSD-Library, die Red-Flag-Library, das SKR-Referenz, und die Notion-Deep-Links. Pro Deal wird darüber hinaus eine Deal-spezifische CLAUDE.md gelegt.

## CLAUDE.md — Vorlagen

### Vorlage `_shared/CLAUDE.md` (global)

```markdown
# Fire/Ice DD Context — global

Du arbeitest für Fire/Ice Partners GmbH, Buy-and-Build-Akquisition für deutsche
Industriekälte- und HVAC-R-Service-Betriebe. Zielprofil: €500k–5m EBITDA,
>50% Wartungsanteil, Inhaber 55+, Süd-/Mittel-/Norddeutschland.

## Wer wir sind
- Niko Noetzel (Bain) und Caspar Freiberg (Co-Founder), Sitz München.
- Equity-Kapital aus CH-Family-Offices, 30 Mio. EUR Fundraise-Ziel.
- Plattform-Logik: 1 Anker-Akquisition + 2-4 Bolt-ons in 36 Monaten.

## Ziel jedes DD-Runs
- Hypothesen-getrieben (nicht Checklisten-getrieben).
- Pro Stage-Gate maximal 5-7 KSDs (Key Strategic Decisions).
- Auf Quality-adjusted EBITDA bewerten, nicht auf Adjusted.
- Sensitivitäten in 5 Szenarien (Preis -5%, Volumen -10%, Mgmt-Churn 30%, F-Gas-Beschleunigung 2J, Top-Kunde-Verlust).

## Manual-Quellen
- Manual: ~/fire-ice-deals/_shared/manual/ (symlink, immer aktuell)
- KSD-Library: ~/fire-ice-deals/_shared/ksd-library.md
- Red-Flag-Library: ~/fire-ice-deals/_shared/red-flag-library.md
- Konten-Referenz: ~/fire-ice-deals/_shared/skr03-kontenrahmen.md, skr04-kontenrahmen.md

## Notion-Workspace (deep-link via MCP)
- Fire / Ice 2026 Home: https://www.notion.so/0c354dd4c51c4b14b9c1eb8f583d7063
- Knowledge Base: https://www.notion.so/3350260c95ef80dbb1a1e307deb393d8
- Interviewfragen Kälte-Klima: https://www.notion.so/2bf0260c95ef80e78226f7080ce5d694
- Traction (Live-Targets): https://www.notion.so/3350260c95ef80749e6cde28905ad294

## Verhaltens-Regeln
- Output IMMER strukturiert (Markdown-Tabellen, klare Zwischenüberschriften).
- Bei Unsicherheit: explizit kennzeichnen ("≈" für Schätzungen, "tbd" für Lücken).
- Bei kritischen Lücken: nicht erfinden — Frage zurückgeben.
- Pro Datenpunkt: Quelle nennen (BWA-Konto, Bilanz-Position, Anhang, Calls).
- Sprache: Deutsch mit englischen PE/Consulting-Termini (EBITDA-Bridge, KSD, IC-Memo, QofE).
- Bei DATEV-Konten: SKR-Referenz nutzen (Konto 8410 = "Erlöse Wartung", nicht raten).
```

### Vorlage `~/fire-ice-deals/<codename>/CLAUDE.md` (pro Deal)

```markdown
# Deal Context — Codename [Alpha]

## Stand-Snapshot (immer aktuell halten)
- Stage: [1 Public / 2 IOI/LOI / 3 Datenraum / 4 SPA]
- Kontaktiert: [YYYY-MM-DD]
- LOI signed: [YYYY-MM-DD oder n/a]
- Letzte Update: [YYYY-MM-DD]
- Lead: Niko / Caspar

## Eckdaten Target
- Sektor: Industriekälte/HVAC-R Service & Installation
- Geo: [Bundesland, Stadt]
- Größe: ~€[X]m Umsatz, ~[N] MA, ~€[Y]k EBITDA reported / €[Z]k Quality-adjusted
- Wartungsanteil: ~[XX]%
- Endkunden-Mix: [LEH/Datacenter/Industrie/Foodservice/Pharma]

## KSDs für diesen Deal (max 7)
1. KSD-A: [Hypothese] — Diskonfirmation: [...] — Quelle: [...]
2. KSD-B: [...]
3. ...

## Red Flags aktiv beobachten (aus Library)
- [Liste relevanter Red Flags pro Stufe]

## Folder-Map
- 01-public/: Stage-1-Dossier + Roh-Quellen
- 02-ioi/: Erstgespräch-Memo + P&L + Bridge v0
- 03-dataroom/: BWA/SuSa/JA + Customer Calls + Bridge final
- 04-spa/: nach IC-Approval

## Letzter Output
- [Datei] [Zusammenfassung was drin steht]
```

## Prompt-Templates

Standard-Prompts pro Sub-Aufgabe. Alle leben in `~/fire-ice-deals/_shared/prompt-templates/`. Wir kopieren in den Claude-Code-Run — oder besser: über Slash-Commands (siehe nächste Sektion). Die Prompts sind wirklich nur Skelette; gutes Prompting bei dieser Modell-Generation heißt: Kontext, Aufgabe, Format, Constraints knackig setzen, dann Modell laufen lassen.

### Stage 1 — Public Screening

#### `prompt-stage1-dossier.md`

```
ROLLE: Du bist DD-Analyst für Fire/Ice. Stage 1 Public-only Screening.

KONTEXT: Ich gebe dir gleich Roh-Quellen zu einem deutschen Kälte-/Klimatechnik-
Betrieb. Sie liegen in 01-public/. Quellen: OpenRegister-Auszug, Bundesanzeiger-
PDF (verkürzte Bilanz), Website-Scrape (Markdown), Google-Reviews-Export, Kununu-
Export, LinkedIn-Team-Liste, ggf. VDKF/HwK-Eintrag.

AUFGABE: Erstelle ein Stage-1-Dossier nach dem Template aus
~/fire-ice-deals/_shared/manual/01-stage-1-public-screening.md (Sektion
"Stage-1 Dossier Template"). Fülle alle 20 Datenpunkte aus.

ZUSÄTZLICH:
- Berechne Umsatz-Schätzung mit zwei Methoden (Bilanzsumme-Faktor + MA × €150-200k),
  zeige Range.
- Schätze EBITDA mit Mix-Annahme (60-70% Wartung → 18-22% EBITDA-Marge,
  40-50% Wartung → 10-15%).
- Formuliere die drei Hypothesen für den Erstcall (H-A Geschäftsmodell, H-B
  Inhabermotivation, H-C Top-Risiko) — explizit verifizierbar im Erstgespräch.
- Empfehlung: Kontaktieren / Beobachten / Skip — mit zwei-Satz-Begründung.

FORMAT: Markdown, exakt nach Template. Tabellen wo Template Tabellen hat.
Quellen-Anhang am Ende mit jeder URL/Datei-Referenz.

UNSICHERHEIT: Schätzungen mit "≈" markieren, fehlende Daten mit "tbd",
Zwei-Methoden-Schätzung in Range angeben. Nicht erfinden.

OUTPUT-DATEI: 01-public/stage-1-dossier.md
```

#### `prompt-stage1-pre-ioi-brief.md`

```
ROLLE: DD-Lead. Aufgabe ist die Decision-Brief vor dem Erstcall.

KONTEXT: Lies das eben erstellte Stage-1-Dossier (01-public/stage-1-dossier.md).

AUFGABE: Erstelle den Pre-IOI-Brief nach Template aus dem Manual
(01-stage-1-public-screening.md, Sektion "Pre-IOI Hypothesen-Brief").

INHALT:
- 3-Sätze "Why this target": warum reizt es uns?
- Drei KSDs to test, jede mit konkreter Frage für den Call.
- Was wir bewusst NICHT fragen.
- Eröffnungstonart.
- Decision-Gate post-Call (Go/Stop-Kriterien).

FORMAT: Knapp, 1 Seite, kein Geblubber.

OUTPUT-DATEI: 02-ioi/pre-ioi-brief.md
```

### Stage 2 — IOI/LOI

#### `prompt-stage2-erstcall-memo.md`

```
ROLLE: Notarius des Erstgesprächs.

KONTEXT: Ich gebe dir das Otter-Transkript (oder Stichworte) eines Erstgesprächs
mit dem Inhaber. Plus den Pre-IOI-Brief (02-ioi/pre-ioi-brief.md) als KSD-Anker.

AUFGABE: Strukturiertes Memo nach Q&A-Logik der drei KSDs aus dem Pre-IOI-Brief.
Pro KSD: was wurde gesagt (verbatim oder paraphrasiert), wie bewerten wir es
(grün/gelb/rot), was bleibt offen.

ZUSÄTZLICH:
- Liste neuer Datenpunkte (Umsatz, MA, Wartungsanteil, Endkunden-Mix), die der
  Inhaber genannt hat. Mit Plausibilisierungs-Hinweis.
- Liste "neue Hypothesen" oder "neue offene Punkte", die im Call aufgekommen sind.
- Inhaberlautstärke: wirkt der Inhaber verkaufsbereit, im Verhandlungsmodus,
  verschüchtert, aufgewärmt? Subjektive Note.
- Empfehlung Next Step: Folgecall + welche Daten anfordern.

FORMAT: Markdown, max 2 Seiten.

OUTPUT-DATEI: 02-ioi/erstgespraech-memo-YYYY-MM-DD.md
```

#### `prompt-stage2-pl-scrub.md`

```
ROLLE: FDD-Analyst. Erste P&L-Verarbeitung bei einem Mittelstand-Target.

KONTEXT: Inhaber hat eine P&L geschickt — meist BWA-PDF aus DATEV oder ein
handgepflegtes Excel. Liegt in 02-ioi/. Plus: das Erstgespräch-Memo
(02-ioi/erstgespraech-memo-*.md) mit Inhaber-Aussagen zu Mix, Personal, etc.

AUFGABE:
1. Extrahiere die P&L in eine strukturierte Markdown-Tabelle: Umsatz,
   Material, Personal, sonstige Aufwendungen, AfA, EBIT, EBITDA. Wenn Vorjahres-
   Vergleich da: zeig beide Spalten.
2. Identifiziere die typischen 12 Inhaber-Normalisierungen (siehe
   02-stage-2-ioi-loi-first-pl.md, Tabelle Normalisierungen). Pro Position:
   "wahrscheinlich vorhanden", "vorhanden", "unklar — fragen". Mit konkretem
   Schätzwert wo möglich, Range wo nicht.
3. Erste EBITDA-Bridge v0 in 4 Spalten (Reported / Adjusted / Run-Rate /
   Quality-adjusted) wie im Manual beschrieben. Source-Anchor pro Zeile.
4. Cross-Check Inhaber-Aussagen mit P&L: sagt Inhaber "60% Wartung", ist es
   plausibel basierend auf P&L-Strukur? Wenn nein: flagge.
5. Liste der 5 wichtigsten Folge-Fragen für Folgecall #1 zum P&L-Verständnis.

FORMAT: Markdown mit Tabellen. EBITDA-Bridge in eigener Sektion.

OUTPUT-DATEI: 02-ioi/pl-scrub.md
```

#### `prompt-stage2-loi-draft.md`

```
ROLLE: M&A-Lead beim LOI-Draft.

KONTEXT: Wir haben jetzt EBITDA-Bridge v0 (02-ioi/pl-scrub.md), Customer-
Concentration-Cube (02-ioi/customer-cube.md), und Erstgespräch-Memo. Wir
wollen einen LOI drafte.

AUFGABE: Fülle das LOI-Template aus dem Manual (07-templates.md, Sektion
"LOI Template DE") mit den Werten für dieses Target.

INPUTS:
- Quality-adjusted EBITDA aus pl-scrub.md → Bewertungs-Range 4.0× bis 5.5×
  (oder bis 6× mit Earn-out).
- Struktur: Asset-Deal bevorzugt (steuerlich, Haftungsausschluss).
- Earn-out: 50/25/25 über 3 Jahre an EBITDA-Ziele gekoppelt (konkrete Schwellen).
- Inhaber-Übergang: 12-24 Monate Beirat / Senior Advisor.
- Closing-Conditions: DD-Abschluss, Bankenfinanzierung, F-Gas/Meister-Lizenz-
  Continuity, Mitarbeiter-Bindung Top-3.
- Exklusivität: 75 Tage.

FORMAT: LOI in Briefform, deutsch, 3-4 Seiten. Bindende Klauseln explizit
markieren. Schlussformel + Unterschriftsfelder.

OUTPUT-DATEI: 02-ioi/loi-draft-v1.md
```

### Stage 3 — Data Room

#### `prompt-stage3-bwa-ingest.md`

```
ROLLE: Data-Engineer für DD.

KONTEXT: In 03-dataroom/raw-pdfs/ liegen 24-36 BWA-PDFs (DATEV-Standard),
ein PDF pro Monat. Standard-Layout (siehe 03-stage-3-data-room.md, Sektion
"BWA lesen"). Je PDF eine Seite mit Umsatzerlöse, Bestandsveränderungen,
Materialaufwand, Roh-Ergebnis, Personalaufwand, AfA, sonst. Aufwendungen,
Betriebsergebnis, Zinsen, vorl. Ergebnis vor Steuern.

AUFGABE:
1. Pro PDF Strukturextraction (Monat, Jahr, alle Positionen).
2. Konsolidierung in EINE Markdown-Tabelle / CSV mit Monats-Spalten und
   Positions-Zeilen.
3. Validitäts-Check: Roh-Ergebnis = Gesamtleistung - Materialaufwand?
   Betriebsergebnis = Roh-Ergebnis - Personal - AfA - Sonst.? Wenn nicht: flagge.
4. Aggregations-Spalten: 12-Monats-LTM rolling, Quartals-Mittel, Jahres-Summen.
5. Saisonalitäts-Sicht: Index pro Monat (Jahresdurchschnitt = 100), zeige
   Schwankungen.

FORMAT: Markdown-Tabelle für Übersicht + CSV in 03-dataroom/extracted/bwa-monthly.csv.

OUTPUT: 03-dataroom/extracted/bwa-monthly.csv + Markdown-Summary unter 03-dataroom/extracted/bwa-summary.md
```

#### `prompt-stage3-susa-mix.md`

```
ROLLE: FDD-Analyst, SuSa-Spezialist.

KONTEXT: In 03-dataroom/raw-pdfs/ liegt eine SuSa (Summen- und Saldenliste),
quartalsweise oder jährlich. SKR03 (oder SKR04 — checken). Ich habe dir die
SKR-Referenz in ~/fire-ice-deals/_shared/skr03-kontenrahmen.md.

AUFGABE:
1. Extrahiere alle Konten mit Saldo. Klassifiziere nach Familie:
   - 0xxx Anlagevermögen
   - 1xxx Umlaufvermögen
   - 2xxx Verbindlichkeiten
   - 4xxx Personal
   - 5xxx Wareneinsatz
   - 6xxx Sonstige Aufwendungen
   - 8xxx Erlöse (besonders 8400-8499)
2. Mix-Analyse Erlöse: Anteil Wartung (8410), Reparatur (8420), Projekt (8430),
   Material-Weiterverkauf (8440) am Gesamt-Erlös.
3. Personal-Aufschlüsselung: Monteure (4100), Angestellte (4120),
   GGF-Vergütung (4130).
4. Sonstige Aufwendungen detailliert: Mieten (6300er), Pkw (6700er),
   Reise/Bewirtung (6800er), Beratung (6850), Versicherungen.
5. Working-Capital-Zahlen: Forderungen LL (1400), halbfertige Arbeiten (1500),
   Verbindl. LL (1600), erhaltene Anzahlungen (2700), Bank/Kasse (0600/1300).

FORMAT: Strukturierte Markdown-Tabelle pro Familie + Top-Level-Summary mit den
wichtigsten Verhältnissen (Wartungsanteil, Personalquote, Material-Quote, DSO, DPO).

OUTPUT-DATEI: 03-dataroom/extracted/susa-analysis.md
```

#### `prompt-stage3-bridge-final.md`

```
ROLLE: FDD-Lead. QofE-Bridge-Master.

KONTEXT: Wir haben jetzt:
- Reported P&L aus Jahresabschluss + BWA-LTM (03-dataroom/extracted/bwa-summary.md)
- SuSa-Mix-Analyse (susa-analysis.md)
- Erstgespräch-Memo, Folgecall-Memos, Site-Visit-Notes
- Customer-Reference-Calls Synthese (03-dataroom/customer-calls/synthesis.md)
- Anlagespiegel-Analyse (03-dataroom/extracted/anlagen-analysis.md)
- KSD-Status aus diesem Deal-CLAUDE.md

AUFGABE: Baue die QofE-Bridge final nach dem Manual-Template
(03-stage-3-data-room.md, Sektion "QofE — 12-Zeilen-Template").

12 Zeilen: A. Reported HGB / B. + GGF-Vergütung-Norm / C. + GGF-Pension /
D. + Familie-in-Lohn / E. + Pkw-Privat / F. + Inhaber-Immo-Miete-Excess /
G. + Einmaleffekte / H. - Capex-Nachzieh / I. = Adjusted / J. + Run-Rate /
K. = Run-Rate / L. - Quality-Adjustments / M. = Quality-adjusted

PRO ZEILE: Wert in EUR k + Source-Anchor (BWA-Konto, SuSa-Position, Anhang-
Stelle, Mgmt-Aussage Folgecall, Customer-Call-Citation).

QUALITY-ADJUSTMENTS (Zeile L) DIFFERENZIERT:
- Konzentrations-Discount (basierend auf Top-3-%)
- Inhaber-Risk-Reserve (12-Mo Übergangs-Coaching + verlängerte GF-Bezüge)
- F-Gas-Capex-Verteilung (jährlicher Anteil bei 5-Jahres-Verteilung)
- Mitarbeiter-Bindung Retention-Bonus (1% Personalaufwand × 1.5J)
- Sonstige spezifische Risiken aus KSDs

FORMAT: Markdown-Tabelle mit Spalten "Position / EUR k / Quelle / Begründung".
Plus: Sensitivitäts-Sektion mit 5 Stress-Szenarien und EBITDA-Effekt jeweils.

OUTPUT-DATEI: 03-dataroom/scrubbed-model/ebitda-bridge-final.md
plus parallele Excel-Version: 03-dataroom/scrubbed-model/ebitda-bridge-final.xlsx
```

#### `prompt-stage3-self-ic-memo.md`

```
ROLLE: Investment Committee Member (uns selbst).

KONTEXT: Alles aus Stage 3 ist da:
- QofE-Bridge final (ebitda-bridge-final.md)
- CDD-Report Erstentwurf
- FDD-Report Erstentwurf
- Customer-/Supplier-/Ex-MA-Calls Synthese
- Sektor-Pack als Markt-Kontext

AUFGABE: Schreibe einen Self-IC-Memo nach Template
(07-templates.md, Sektion "Self-IC-Memo TOC").

ZWINGENDE SEKTIONEN:
1. Executive Summary (max 1 Seite): Empfehlung Go/No-Go, Bewertung,
   Top-3-Risiken, Top-3-Chancen.
2. Thesis: warum dieses Target, warum jetzt, wie passt es zur Plattform.
3. KSDs Status: alle KSDs aus Deal-CLAUDE.md mit Beleg.
4. Bewertung: QofE-Bridge + Multiple-Range + Equity Value + Earn-out-Ladder.
5. Operating-Plan post-Close: konkrete Hebel (siehe 05-sector-pack-hvac-r.md
   Sektion "Operating-Hebel post-Close") mit Quantifizierung.
6. Sensitivitäten: 5 Stress-Szenarien, Equity-Wirkung jeweils. WENN auch nur 1
   negative Equity ergibt → No-Go-Empfehlung.
7. Top-3-Risiken mit Mitigation: Capex, Mgmt, Markt, Konzentration.
8. SPA-Strategy: Earn-out-Struktur, Garantien-Liste, Working-Capital-Peg.
9. Stakeholder-Map post-Close: Inhaber-Übergang, Schlüsselpersonen,
   Mitarbeiter-Kommunikation.
10. Decision: Go / No-Go / Conditional, mit Folge-Bedingungen.

FORMAT: Markdown, 8-15 Seiten. Quantifizierungen bevorzugt in Tabellen.

KRITISCH: KEIN Wischiwaschi. Wenn die Sensitivitäten zeigen, dass eines der 5
Szenarien negativ ist, sag das klar. Wenn 3+ Red Flags noch offen, sag das.
Wir bauen kein Memo, das einen Deal verteidigt — wir bauen ein Memo, das die
Wahrheit zeigt.

OUTPUT-DATEI: 03-dataroom/self-ic-memo.md
```

## Vorgeschlagene Slash-Commands

Die Prompts oben kann man auch als wiederverwendbare Slash-Commands in
`~/.claude/commands/` ablegen, dann ist es Tippen statt Kopieren. Vorschlag
für Naming und Mapping:

| Slash-Command | Mapped Prompt | Wann |
|---|---|---|
| `/dd-public-screen <codename>` | prompt-stage1-dossier.md | Nach Sammlung Stage-1-Quellen |
| `/dd-pre-ioi-brief <codename>` | prompt-stage1-pre-ioi-brief.md | Vor Erstcall |
| `/dd-erstcall-memo <codename> <transkript>` | prompt-stage2-erstcall-memo.md | Nach Erstcall |
| `/dd-pl-scrub <codename>` | prompt-stage2-pl-scrub.md | Nach P&L-Empfang |
| `/dd-bridge-v0 <codename>` | (Sub-Prompt aus pl-scrub) | Nach P&L-Scrub |
| `/dd-customer-cube <codename>` | (eigener Prompt für Top-20-Cube + HHI) | Nach Top-20-Liste |
| `/dd-loi-draft <codename>` | prompt-stage2-loi-draft.md | Vor LOI-Versand |
| `/dd-bwa-ingest <codename>` | prompt-stage3-bwa-ingest.md | Nach DR-Open |
| `/dd-susa-mix <codename>` | prompt-stage3-susa-mix.md | Nach DR-Open |
| `/dd-anlagen-capex <codename>` | (eigener Prompt aus 03-stage-3 Sektion "Anlagespiegel-Analyse") | Mit DR-Open |
| `/dd-bwa-gu-recon <codename>` | (Reconciliation BWA-monthly → GuV-annual) | Nach Ingest + Vorjahres-JA |
| `/dd-wc-cube <codename>` | (Working-Capital aus Bilanz × 3-5 Jahre) | Mit DR-Open |
| `/dd-bridge-final <codename>` | prompt-stage3-bridge-final.md | Nach Calls + DR-Verarbeitung |
| `/dd-redflag-scan <codename>` | (Scan über alle Doks gegen Red-Flag-Library) | Vor IC |
| `/dd-cdd-draft <codename>` | (CDD-Report-Generator) | Vor IC |
| `/dd-fdd-draft <codename>` | (FDD-Report-Generator) | Vor IC |
| `/dd-ic-memo <codename>` | prompt-stage3-self-ic-memo.md | Vor IC |

Implementation: jeder `/dd-*`-Command lädt seinen Prompt aus
`~/fire-ice-deals/_shared/prompt-templates/<name>.md`, ersetzt `<codename>`,
und führt ihn im aktuellen Deal-Ordner-Kontext aus. Wir können das mit Claude
Cowork-Skills oder Claude-Code-Hooks bauen — nicht in 1 Stunde, aber in einem
Wochenende.

## Anthropic financial-analysis Plugin — was wir davon nutzen

In [raw/notes/2026-05-07-anthropic-finance-agents-memo.md](../../../raw/notes/2026-05-07-anthropic-finance-agents-memo.md) ist der Setup für die Anthropic-Plugins. Konkret nutzbar für uns:

| Anthropic-Skill / Command | Wann wir es im DD-Flow nutzen |
|---|---|
| `/comps` (financial-analysis) | Stage 2/3: Bewertungs-Sanity-Check gegen Vergleichstransaktionen (begrenzt, weil Mittelstand-Comps schwer) |
| `/dcf` | Stage 3: Sanity-Check des Multiple-Bewertungs gegen DCF-Bewertung (Plausibilisierung) |
| `/3-statement-model` | Stage 3: Plausibilisierung der Capex/WC-Annahmen via 3-Statement-Modell |
| `/debug-model` | Excel-Audit der Bridge oder eines vom Inhaber gelieferten Modells |
| `/ic-memo` | Komplementärer Generator zum oben definierten `/dd-ic-memo` — vergleichen, mergen |
| `/comps-analysis` (Skill) | Bei Bolt-on-Bewertung relevant |

**Install:**
```bash
claude plugin marketplace add anthropics/claude-for-financial-services
claude plugin install financial-analysis@claude-for-financial-services
claude plugin install equity-research@claude-for-financial-services  # für /thesis-tracker
claude plugin install private-equity@claude-for-financial-services    # für /ic-memo, /dd-checklist, /dd-prep
```

**Limitations:** Die Anthropic-Skills sind auf Mid-Market und größer optimiert. Bei €500k-5m EBITDA Mittelstand-Targets liefern sie generische Outputs ohne unsere sektor-spezifische Sicht — deshalb nutzen wir sie als Komplement, nicht als Ersatz für unsere Custom-Prompts.

## MCP-Setup-Empfehlungen

| MCP | Zweck | Priorität |
|---|---|---|
| **Notion-MCP** (read-only auf fire-ice Workspace) | Deep-link von Manual zu Knowledge Base, Live-Sync mit Meeting Notes / Targets | hoch — sofort einrichten |
| **Egnyte-MCP** (oder Box) | Datenraum-Verarbeitung wenn wir Egnyte/Box als VDR nutzen | mittel — pro Deal entscheiden |
| **Daloopa-MCP** (kostenpflichtig) | Comps-Sanity-Check, Markt-Benchmarks | niedrig — bei dieser Größe weniger relevant |
| **Filesystem-MCP** (lokales `~/fire-ice-deals/`) | Standard, immer aktiv | hoch |
| **GitHub-MCP** (für dieses Wiki-Repo) | Manual updaten ohne Context-Switch | mittel |

Notion-MCP-Setup: in `~/fire-ice-deals/_shared/notion-mcp.json` mit OAuth-Token, Workspace-Scope auf "Fire / Ice Gruppe". Read-only — wir wollen Claude nicht versehentlich in Notion schreiben lassen.

## OCR / PDF-Patterns

DATEV-PDFs sind oft Bild-PDFs (gescannt vom Steuerberater) statt Text-PDFs. Claude kann beides, aber Bild-PDFs sind langsamer und fehleranfälliger. Standard-Tricks:

- **Pre-Processing:** vor dem Claude-Run lokal mit `tesseract` oder `pdftotext` durchlaufen, Output als parallele Text-Datei ablegen. Claude kombiniert Text + Bild.
- **Layout-Konsistenz:** DATEV-BWA folgt einem Standard-Layout. Wir geben Claude eine Beispiel-BWA mit Annotierung (welche Position wo) — er erkennt das in den anderen Monaten.
- **Tabellen-Extraktion:** für SuSa lieber Excel/CSV anfordern als PDF — beim StB direkt fragen "können Sie die SuSa als Excel-Export liefern?". Spart 70% Bearbeitungszeit.
- **Mehrseiten-PDFs:** in einzelne Files splitten (`pdfseparate`), Claude einen pro Iteration verarbeiten lassen, dann Konsolidierung.

## Workflow im Alltag

Ein typischer DD-Tag bei uns sieht so aus:

```
09:00  Caspar bekommt P&L vom Inhaber Target Charlie
09:05  Caspar legt PDF in ~/fire-ice-deals/charlie/02-ioi/
09:10  Claude Code Session öffnen, in /charlie/ wechseln
09:11  /dd-pl-scrub charlie
09:25  Claude liefert pl-scrub.md mit P&L-Tabelle, 12 Normalisierungen, Bridge v0
09:30  Caspar reviewt, korrigiert 2 Punkte (Inhaber-Pkw-Anteil, Familie-in-Lohn-
       Excess), versteht 3 Punkte nicht (fragt zurück bei Inhaber)
10:00  Niko nimmt sich erst mal die Customer-Concentration aus separater Top-20-
       Liste (per /dd-customer-cube charlie)
10:30  Beide gehen Bridge v0 + Concentration-Cube zusammen durch, finalisieren
       Stage-2-Output
11:00  Niko macht /dd-loi-draft charlie, bekommt LOI-Draft, poliert 30 min
11:30  Niko schickt LOI an Caspar zur Review
12:00  Mittagessen
13:00  Caspar springt auf Stage-3-Vorbereitung für Bravo (BWA-Ingest)
       /dd-bwa-ingest bravo
13:45  Claude liefert konsolidierte BWA-Tabelle 36 Monate
14:00  Caspar /dd-susa-mix bravo
       ...
```

Das ist nicht viel anders als ein Bain-Tag mit klaren Tasks und schnellen Iterationen. Der Unterschied: Claude macht die Datenextraktion und Erst-Synthese, wir machen Bewertung, Verhandlung, Strategie. Das ist ein 5-10× Hebel ggü. dem traditionellen Mid-Market-PE-Associate-Workflow.

## Was Claude NICHT machen darf

- **Inhaber direkt anschreiben.** Alle Outbound-Kommunikation läuft über Niko/Caspar.
- **Notion editieren.** Read-only Setup. Wir maintain Notion manuell.
- **CRM (Attio) editieren.** Wir verlinken aus DD-Outputs zurück, manuelle Pflege.
- **Externe APIs aufrufen ohne explizite Genehmigung.** Web-Searches OK, aber kein "Schau mal bei OpenRegister.de und kaufe den Auszug".
- **In CO-Founder-Calls lauschen / mitschneiden ohne Einverständnis.** DSGVO + Vertrauen.
- **Selbständige Entscheidungen treffen.** Claude liefert Empfehlungen mit Begründung, wir entscheiden.

## Maintenance des Playbooks

Pro Deal, nach Closing oder Abbruch:
1. Lessons-Learned-Sektion in der Self-IC-Memo (was hat gut funktioniert, was nicht).
2. Updates an Manual-Docs wenn strukturelle Erkenntnisse (z.B. neuer Red Flag, neuer Sektor-Trick).
3. Updates an Prompt-Templates wenn ein Prompt schlechte Outputs lieferte.
4. CHANGELOG-Eintrag in `~/fire-ice-deals/_shared/CHANGELOG.md` mit Datum + Änderung.

## Related

- [Overview](./overview.md)
- [Stage 1 — Public-only Screening](./01-stage-1-public-screening.md)
- [Stage 2 — IOI/LOI](./02-stage-2-ioi-loi-first-pl.md)
- [Stage 3 — Full Data Room](./03-stage-3-data-room.md)
- [Templates](./07-templates.md) — fertige Letter, IC-Memo-TOC, Sensitivitäts-Tabellen
- [Anthropic financial-analysis Memo](../../../raw/notes/2026-05-07-anthropic-finance-agents-memo.md)
