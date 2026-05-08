---
title: "CDD/FDD Manual — Fire/Ice Industriekälte (€500k–5m EBITDA, DE)"
type: "idea"
summary: "Operator-Manual für Niko & Caspar: wie wir CDD/FDD auf Industriekälte/HVAC-R-Targets in DE laufen — über drei Informationsstufen (Public → IOI/LOI → Data Room), mit Claude Code, und auf BM-Dollar-Fund-Niveau."
status: "active"
verdict: "pursuing"
tags: ["fire-ice", "dd", "cdd", "fdd", "hvac-r", "kältetechnik", "germany", "hgb", "claude-code", "playbook"]
source_files:
  - "https://www.notion.so/0c354dd4c51c4b14b9c1eb8f583d7063"
  - "https://www.notion.so/3100260c95ef816ebe85ca12ddd58ba5"
  - "https://www.notion.so/3350260c95ef80dbb1a1e307deb393d8"
  - "raw/notes/2026-05-07-anthropic-finance-agents-memo.md"
updated: "2026-05-08"
---

# CDD/FDD Manual — Fire/Ice Industriekälte

Manual für Niko & Caspar zur Durchführung von Commercial und Financial Due Diligence auf deutsche Industriekälte- und HVAC-R-Service-Betriebe im Zielband €500k–5m EBITDA. Drei Informationsstufen, ein konsistentes Claude-Code-Setup, ein BM-Dollar-Fund-Anspruch — als zwei Ex-Bainies mit guter Modellintuition aber dünner M&A-Erfahrung.

## Wofür dieses Manual da ist

Wir machen Buy-and-Build in einem Markt, in dem die einzelne Firma 5–25 MA hat, der Inhaber 60+ ist, der Jahresabschluss nach §267 HGB ein Kleinst- oder Klein-GmbH ist und die "Buchhaltung" eine BWA aus DATEV plus eine SuSa-Liste ist. Das ist nicht Mid-Market-PE mit drei Banken, vier Beratern und einem 200-Seiten-VDD. Das ist Mittelstand-Realität. Trotzdem darf die Diligence-Qualität nicht schlechter sein als bei einem Triton- oder Bridgepoint-Deal — sonst kaufen wir Müll auf 4× und können in fünf Jahren keinen 8× Exit erklären.

Dieses Manual hält uns auf Spur an drei Punkten:
1. **Strukturierter Informationsaufbau.** Jede Stufe hat ein definiertes Output-Artefakt. Wir laufen nicht in den Erstcall ohne Pre-IOI-Brief, und wir unterschreiben kein LOI ohne EBITDA-Bridge v0.
2. **HGB-Realismus.** Bei Klein-GmbHs sagt der Anhang fast nichts. Stille Reserven, Inhabergehalt-Normalisierung, verdeckte Gewinnausschüttungen, Pensionszusagen GGF, Pauschalwertberichtigungen — all das müssen wir rausarbeiten, nicht aus dem Bericht ablesen. Siehe [04-hgb-quirks.md](./04-hgb-quirks.md).
3. **Claude als Force-Multiplier.** Pro Deal ein Codename-Ordner, pro Stufe ein Slash-Command, ein konsistentes Prompt-Set. Siehe [06-claude-code-playbook.md](./06-claude-code-playbook.md).

## Die drei Informationsstufen — Übersicht

| Stufe | Was wir haben | Was wir produzieren | Zeitbudget | Manual-Doc |
|---|---|---|---|---|
| **1. Public-only** | OpenRegister/Northdata, Bundesanzeiger, Website, Google/Kununu, LinkedIn/Xing, Innungs-/F-Gas-Listen | Stage-1 Dossier (1-Pager pro Target) + Pre-IOI Hypothesen-Brief | 4–8 h | [01-stage-1-public-screening.md](./01-stage-1-public-screening.md) |
| **2. IOI/LOI Level** | + Erstgespräch (60–90 min), Folgecall, erste P&L (oft handgepflegt), grobe Kundenliste | Erstgespräch-Memo + scrubbed P&L + EBITDA-Bridge v0 + IOI-Letter | 2–3 Wochen | [02-stage-2-ioi-loi-first-pl.md](./02-stage-2-ioi-loi-first-pl.md) |
| **3. Full Data Room** | + BWA (24-36 Monate), SuSa, Jahresabschluss (3-5 Jahre), Anlagespiegel, Verträge, Mitarbeiterliste, ggf. Mgmt-Präsentation | QofE-Bridge final + CDD-Report + FDD-Report + Self-IC-Memo + SPA-Verhandlungspaket | 4–8 Wochen | [03-stage-3-data-room.md](./03-stage-3-data-room.md) |

Cross-cutting: HGB-Quirks ([04](./04-hgb-quirks.md)), Sector Pack ([05](./05-sector-pack-hvac-r.md)), Claude Playbook ([06](./06-claude-code-playbook.md)), Templates ([07](./07-templates.md)).

## Prinzipien — wie wir DD machen wollen

### 1. Hypothesen-getriebene DD, nicht Checklisten-DD

Bain-Reflex: vor jedem Stage-Gate maximal 5–7 Key Strategic Decisions (KSD) formulieren, jede KSD mit binärer Diskonfirmations-Frage und Daten-Quelle hinterlegen. Wir lesen den Datenraum nicht "von vorne nach hinten", wir gehen mit einer Hypothesenliste rein und suchen das, was sie killt. Beispiel KSD pre-LOI:

- **KSD-1 (Wartungsanteil):** ">60% wiederkehrender Wartungs-/Servicevertragsumsatz in den letzten 3 Jahren". Diskonfirmation: BWA-Aggregation oder Kundenliste zeigt <50%. Datenquelle: BWA Konten 8400er + Top-20-Kundenliste.
- **KSD-2 (Inhaberabhängigkeit):** "Operatives Geschäft ohne Inhaber 12-24 Monate post-Close stabil". Diskonfirmation: alle Top-10-Kunden via Inhaber-Beziehung; keine Vertretung im operativen Geschäft. Datenquelle: Customer-Reference-Calls + Mgmt-Interviews.
- **KSD-3 (Fachkräfte-Kontinuität):** ">90% Mitarbeiterbindung 18 Monate post-Close erwartet". Diskonfirmation: Altersstruktur >55 bei >40% der Monteure, Sachkundenachweise nicht übertragbar. Datenquelle: Mitarbeiterliste mit Geburtsjahr, Funktion, Sachkunde-Zertifikat.

### 2. Primärrecherche schlägt Datenraum

Bei dieser Größe ist der Datenraum dünn — der Inhaber hat keinen CFO. Was den Deal entscheidet, finden wir nicht im Anhang, sondern im Customer-Reference-Call und im Lieferanten-Gespräch.
- **Kunden-Calls:** Mindestens 10–15 Top-Kunden direkt anrufen ("wir prüfen eine Investition in [Firma], bitte 15 min Feedback"). Skript in [07-templates.md](./07-templates.md). Echte Kundeninterviews schlagen jeden DD-Bericht.
- **Lieferanten-Calls:** Mindestens je ein Gespräch mit dem Hauptgroßhändler (REISS / FISCHER / SCHIESSL / FRIGOTechnik — siehe [05-sector-pack-hvac-r.md](./05-sector-pack-hvac-r.md)) und mit 2–3 Hauptlieferanten Komponenten.
- **Ex-Mitarbeiter via LinkedIn/Xing:** Drei Ex-Monteure und ein Ex-Projektleiter, "anonyme" 15-Min-Calls. Die offene Frage "warum bist du gegangen?" ist Gold.
- **Wettbewerbs-Calls:** Mit zwei lokalen Wettbewerbern unter Pretext (Vergabeprüfung). Marktverhalten und Reputation des Targets.

Dieses Volumen schlägt Tegus/GLG bei dieser Dealgröße spielerisch — wir machen es selber, kostet uns 3-5 Tage pro Target.

### 3. EBITDA-Bridge ist das Herzstück

Berichteter HGB-EBITDA → Adjusted (Inhaber-Normalisierung, Einmaleffekte, Versicherungs-/Pkw-/Privatkosten) → Run-Rate (annualisierte LTM, Wartungsstart-Conversions, vertraglich gesicherte Q+1) → Quality-adjusted (Konzentrations-Discount, Fachkräfte-Risiko, F-Gas-Capex). Vier-Spalten-Bridge ist nicht-verhandelbar; wir kaufen auf das letzte, nicht auf das erste.

### 4. Red-Flag-Bibliothek vor jedem Stage-Gate durchlaufen

Die "30 Dinge, die einen Deal töten" ([07-templates.md](./07-templates.md)) ist nach jedem Stage-Gate vollständig durchzuhaken. Wenn drei Rote-Flag-Punkte hängen bleiben, kein Weiterkauf — auch nicht "wir lösen das in 100 Tagen".

### 5. Sensitivität schlägt Punktschätzung

Jedes Self-IC-Memo enthält fünf Stress-Szenarien (Preis -5%, Volumen -10%, Mgmt-Churn 30%, F-Gas-Beschleunigung 2 Jahre, Schlüsselkunde-Verlust). Wenn das Equity-Investment in einem davon negativ wird, kein Deal — auch wenn der Base-Case schön aussieht.

### 6. Honest about our edges and gaps

**Wo wir stark sind (Bain-DNA):**
- Strukturierte CDD: Marktsegmentierung, Wettbewerbskartierung, Endkunden-Penetration, Win/Loss-Analyse, Bottom-up-TAM. Das machen wir besser als die meisten Mid-Cap-PE-Associates.
- Strategische Options-Bewertung: Welche Akquisitionen passen zur Plattform-Logik, welche sind opportunistisch.
- Hypothesen-Disziplin: Wir akzeptieren keine Behauptung ohne Datenfundament, das ist Muskelgedächtnis.

**Wo wir schwach sind (kein M&A-Track-Record):**
- **Legal DD:** Komplett auslagern. Lokale M&A-Kanzlei, idealerweise mit DE-Mittelstand-Erfahrung (z.B. Heuking, Luther, Noerr Mittelstand-Praxis, oder regionale Boutiquen). Kosten: €30-60k pro Deal. Nicht versuchen, das selbst zu machen.
- **Tax DD:** Auch auslagern — Steuerberater des Verkäufers übernimmt fast nie, eigener WP/StB nötig. Kosten: €15-30k pro Deal.
- **Environmental:** Bei Industriekälte fast immer ein Thema (Kältemittel-Lecks, Altanlagen-Entsorgung, Bodenkontamination an Werkstattstandorten). Bei jedem Target eine Phase-1-ESA durch lokalen Gutachter (€3-8k).
- **SPA-Verhandlung:** Die ersten zwei Deals mit erfahrenem M&A-Anwalt am Tisch. Locked-Box vs Closing Accounts, MAC-Klausel, R&W-Versicherung — das sind keine Themen, die man zum ersten Mal live lernt.

**Wo Claude den Hebel macht:**
- Datenraum-Verarbeitung (PDF-Extraction, BWA→GuV-Reconciliation, Anlagespiegel-Parsing): 10× schneller als manuell.
- CDD-Synthese (Customer-Calls clustern, Wettbewerbsmapping aus 50 Lieferanten-Websites, Markt-Sizing aus VDKF/Innungs-Listen): bringt uns auf MBB-Output-Niveau in einem Bruchteil der Zeit.
- IC-Memo-Drafting: erste Version aus Datenraum + Calls + Bridge in 2-3 Stunden, wir polieren statt zu schreiben.

## Working Folder Convention pro Deal

Pro Target wird ein Codename vergeben (kein Klarname — Vorsicht bei Notion-Sync und falls jemand mit auf den Bildschirm schaut). Beispiele: "Alpha", "Bravo", "Charlie" — sequentiell.

```
~/fire-ice-deals/
└── alpha/                          # Codename
    ├── CLAUDE.md                    # Pro-Deal-Context (Thesis, KSDs, Status)
    ├── 01-public/
    │   ├── openregister-export.pdf
    │   ├── northdata-snapshot.html
    │   ├── bundesanzeiger-2024.pdf
    │   ├── website-scrape.md
    │   ├── google-kununu-reviews.md
    │   ├── linkedin-team.md
    │   └── stage-1-dossier.md       # Output dieser Stufe
    ├── 02-ioi/
    │   ├── erstgespraech-protokoll-2026-05-12.md
    │   ├── folgecall-2026-05-19.md
    │   ├── pl-2023-2024-2025-handgepflegt.xlsx
    │   ├── kunden-top20-grob.xlsx
    │   ├── ebitda-bridge-v0.xlsx
    │   ├── pre-ioi-hypothesen-brief.md
    │   └── ioi-letter-final.docx     # Output dieser Stufe
    ├── 03-dataroom/
    │   ├── raw-pdfs/                 # Original-Dataroom-Files
    │   ├── extracted/                # OCR + JSON via Claude
    │   ├── scrubbed-model/
    │   │   ├── bwa-monthly-36mo.xlsx
    │   │   ├── susa-quarterly.xlsx
    │   │   ├── jahresabschluss-3yr.xlsx
    │   │   ├── ebitda-bridge-final.xlsx
    │   │   └── working-capital-cube.xlsx
    │   ├── customer-calls/           # 12-15 Calls mit Transkript+Synthese
    │   ├── supplier-calls/
    │   ├── ex-employee-calls/
    │   ├── cdd-report.md
    │   ├── fdd-report.md
    │   └── self-ic-memo.md            # Output dieser Stufe
    ├── 04-spa/                       # Erst nach IC-Approval
    └── _trash/                       # Sachen, die wir aussortiert haben
```

`CLAUDE.md` pro Deal-Ordner — siehe [06-claude-code-playbook.md](./06-claude-code-playbook.md) für die Vorlage. Sie lädt automatisch in jeden Claude-Code-Run und stellt sicher, dass Claude die Thesis, die KSDs und den aktuellen Stand kennt, ohne dass wir es jedes Mal repetieren.

## Wie wir das Manual benutzen

- **Vor jedem neuen Stage-Gate:** das passende Manual-Doc ([01](./01-stage-1-public-screening.md), [02](./02-stage-2-ioi-loi-first-pl.md), [03](./03-stage-3-data-room.md)) komplett überfliegen — keine 10 Minuten, aber als Zwangs-Reset.
- **Vor jedem IC-Termin (auch self-IC):** [07-templates.md](./07-templates.md) IC-Memo-TOC + die fünf Sensitivitäten durchgehen.
- **Wenn HGB/Buchhaltung Kopfzerbrechen macht:** direkt zu [04-hgb-quirks.md](./04-hgb-quirks.md), dort ist auch eine durchgerechnete EBITDA-Bridge an Generic Target "Alpha".
- **Wenn unklar ist, ob Sektor-spezifisches Detail Standard oder Red Flag ist:** [05-sector-pack-hvac-r.md](./05-sector-pack-hvac-r.md), insbesondere die Customer-/Endkunden-/Großhändler-Maps und die F-Gas-Timeline.
- **Bevor wir Claude für eine neue Aufgabe einspannen:** [06-claude-code-playbook.md](./06-claude-code-playbook.md), insbesondere die Prompt-Templates und die Slash-Command-Vorschläge.

Das Manual ist ein Living Document. Pro Deal eine Lessons-Learned-Sektion in der Self-IC-Memo, die zurück in die entsprechenden Manual-Docs fließt — sonst rosten wir.

## Deep-Links Fire/Ice Notion-Workspace

Das Manual ergänzt, ersetzt nicht. Inhaltliche Tiefe zur Branche, zum Markt, zu konkreten Targets liegt im Notion-Workspace und wird aus den Manual-Docs heraus verlinkt.

- [Fire / Ice 2026 Home](https://www.notion.so/0c354dd4c51c4b14b9c1eb8f583d7063) — Programm-Nordstern.
- [🧊 Fire/Ice — 1-Pager (Validation Sprint Mar 2026)](https://www.notion.so/3100260c95ef816ebe85ca12ddd58ba5) — Thesis, ICP "Harald, 62", Hypothesen H1-H9.
- [🗄️ Knowledge Base](https://www.notion.so/3350260c95ef80dbb1a1e307deb393d8) — Sammelpunkt Sektor-Wissen.
- [❄️ Kältetechnik 101](https://www.notion.so/3350260c95ef802da31cf1bc97d6d549) — Großhändler, Hersteller, Branchen-News.
- [⁉️ Interviewfragen Kälte-Klima](https://www.notion.so/2bf0260c95ef80e78226f7080ce5d694) — bestehende CDD-Frage-Bank, wird in [02](./02-stage-2-ioi-loi-first-pl.md) und [05](./05-sector-pack-hvac-r.md) erweitert.
- [🚀 Traction (Potential Targets / LOIs)](https://www.notion.so/3350260c95ef80749e6cde28905ad294) — aktuelle Pipeline (live, nicht im Manual-Body referenziert).
- [☎️ All Meeting Notes - GlobalDB](https://www.notion.so/1fa0260c95ef81c593d0d16073398ede) — Meeting-Backbone, Kategorie "Target" für Inhaber-Calls.
- [🚀 Value Creation Playbook](https://www.notion.so/3350260c95ef80aabc14df136b77cfdb) — post-Close Hebel; CDD-Annahmen müssen mit dem konsistent sein.

## Related

- [Stage 1 — Public-only Screening](./01-stage-1-public-screening.md) — Quellen, Stage-1-Dossier-Template, Pre-IOI-Brief.
- [Stage 2 — IOI/LOI mit erster P&L](./02-stage-2-ioi-loi-first-pl.md) — Erstgespräch, P&L-Scrub, EBITDA-Bridge v0, IOI-Letter.
- [Stage 3 — Full Data Room (BWA / SuSa / JA)](./03-stage-3-data-room.md) — DATEV-Lesen, Reconciliation, QofE, FDD-Report.
- [HGB-Quirks bei Klein-GmbHs](./04-hgb-quirks.md) — Größenklassen, Maßgeblichkeit, stille Reserven, Inhaber-Normalisierung, durchgerechnetes Beispiel.
- [Sector Pack — Industriekälte / HVAC-R](./05-sector-pack-hvac-r.md) — Economics, F-Gas, Großhändler, Wettbewerber, sektor-spezifische Red Flags.
- [Claude-Code-Playbook](./06-claude-code-playbook.md) — Folder-Konvention, Prompt-Templates, Slash-Commands, MCP-Setup.
- [Templates & Output-Formate](./07-templates.md) — IOI/LOI-Letter, Erstgespräch-Agenda, Customer-Call-Skript, CDD/FDD-Report-TOC, Self-IC-Memo, Sensitivitäten.
- [Anthropic financial-analysis Memo](../../../raw/notes/2026-05-07-anthropic-finance-agents-memo.md) — Plugin-Setup für `/comps`, `/dcf`, `/3-statement-model`, `/debug-model`, `/ic-memo`.
