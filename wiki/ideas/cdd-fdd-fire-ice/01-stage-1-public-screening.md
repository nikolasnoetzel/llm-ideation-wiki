---
title: "Stage 1 — Public-only Screening (Pre-IOI)"
type: "note"
summary: "Welche öffentlichen Quellen wir für ein Industriekälte-Target nutzen, was wir daraus extrahieren, welches Stage-1 Dossier wir produzieren und welcher Pre-IOI Hypothesen-Brief vor dem Erstcall steht."
status: "active"
tags: ["fire-ice", "dd", "stage-1", "public-screening", "openregister", "northdata", "bundesanzeiger"]
source_files:
  - "https://www.notion.so/3350260c95ef802da31cf1bc97d6d549"
updated: "2026-05-08"
---

# Stage 1 — Public-only Screening

Bevor wir den Inhaber das erste Mal anrufen, soll auf einem A4-Pager stehen, was wir glauben zu wissen, was wir nicht wissen, und welche drei Hypothesen wir im Erstcall verifizieren wollen. Wenn wir den Pre-IOI-Brief nicht hinkriegen, ist das Target nicht reif fürs Erstgespräch — wir wollen den Inhaber nicht für unsere Recherche zahlen lassen.

## Quellen — was es gibt und was es kostet

### Pflicht (€0 oder Standard-Abo)

- **OpenRegister.de** — Schnellzugriff auf Handelsregister-Auszüge, Gesellschafterstruktur, Geschäftsführer, Stammkapital, Beteiligungen. Pro Auszug ca. €4-15 oder Flatrate. Wichtigste Felder: Geburtsjahr GGF (Inhaberalter ist die Nummer-1-Variable), Stammkapital, Anzahl Gesellschafter, Beteiligungs-Cluster.
- **Northdata** — Visualisierung der Gesellschafterstruktur, Verflechtungen, Bilanzkennzahlen wenn offengelegt, Personenakte. Ist der Inhaber an drei weiteren GmbHs beteiligt? Hat er vielleicht eine Holding-Struktur, die uns einen Asset-Deal verbietet? Pro-Account: ca. €30-50/Monat.
- **Bundesanzeiger** — Offenlegungspflichtige Jahresabschlüsse (§325 HGB). Bei Klein-GmbHs (siehe [04-hgb-quirks.md](./04-hgb-quirks.md)) nur Bilanz, kein GuV — bei Kleinst-GmbHs nur eine kurze Bilanz ohne Anhang. Trotzdem: Bilanzsumme, Anlagevermögen, Eigenkapital, Rückstellungen, Verbindlichkeiten — daraus lässt sich grobes Working Capital, Verschuldungsgrad, Anlagenintensität schätzen. Kostenlos.
- **Unternehmensregister.de** — Volltextsuche über Bundesanzeiger-Veröffentlichungen, manchmal Bilanzen mehrerer Jahre nebeneinander. Kostenlos.
- **Handelsregister.de / common-register.eu** — Original-Handelsregisterauszüge, Gesellschaftsverträge falls offengelegt (selten bei GmbH). Pro Auszug €4.50.

### Sektor-spezifisch (Pflicht für HVAC-R)

- **VDKF Mitgliedsverzeichnis** — Verband Deutscher Kälte-Klima-Fachbetriebe. Mitgliedschaft signalisiert Qualität und Innungs-Anbindung. ([VDKF Mitgliederbereich](https://www.vdkf.de)).
- **Handwerkskammer Betriebsverzeichnis** — In jedem Bundesland öffentlich, listet eingetragene Kälteanlagenbauer-Meister-Betriebe (HwO Anlage A seit 2020). Wenn ein Target nicht eingetragen ist: Red Flag oder Asset-Deal-Komplikation.
- **BAFA F-Gas-Betriebszertifikat-Register** — Pflicht für jeden Betrieb, der mit teilfluorierten Treibhausgasen umgeht (also de facto jeder HVAC-R-Service-Betrieb). Status, Zertifikat-Nummer, Geltungsbereich. ([BAFA F-Gas-Liste](https://www.bafa.de/DE/Energie/Energieeffizienz/Fluorierte_Treibhausgase_Klimaschutz/fluorierte_treibhausgase_klimaschutz_node.html)).
- **Innungs-Mitgliedslisten** — pro Bundesland teils öffentlich (z.B. Innung SHK Bayern, Landesinnung Kälte- und Klimatechnik). Konkurrenten und Marktdichte vor Ort.
- **TÜV / DEKRA Anlagenbestand** — wenn Target Rückkühl- oder Großkälteanlagen baut, sind diese teils im VDI-2047-Register (Kühltürme — Legionellen) eingetragen. Indirekter Hinweis auf Großauftragsumsatz und Endkunden.

### Web-Forensik (Standard)

- **Eigene Website** — Über uns, Referenzen, Stellenangebote, Karriereseite, ggf. Kunden-Logos. Wayback Machine für historische Snapshots — wann hat sich der "Über uns"-Text zuletzt geändert? Kostenfreie Stellenanzeigen sind gleichzeitig Hinweise auf Wachstumsmodus und Fachkräftedruck.
- **Google Business Profile** — Anzahl Bewertungen, Sterne-Schnitt, Antwortverhalten des Inhabers, Foto-Aktivität. Bewertungen <20 = wenig B2C-Footprint (gut für reines Industrie-Target). Bewertungen mit "Wartung" / "schnell" / "kompetent" Stichworten = Wartungs-DNA.
- **Kununu / Glassdoor** — Mitarbeiter-Sentiment. Achten auf "Inhaber führt autoritär", "kein Nachwuchs", "Werkzeuge alt" — das sind alles Post-Close-Themen.
- **LinkedIn / Xing** — Inhaber-Profil (Ausbildung, Stationen, Vereinsmitgliedschaft Innung, ggf. Verkaufssignale wie "Beirat-Tätigkeiten zunehmend"), Schlüssel-MA (Werkstattleiter, Vertriebsleiter, Projektleiter), Ex-Mitarbeiter-Liste für spätere Stage-3-Calls.
- **YouTube / Branchenvideos** — manche KK-Betriebe haben Imagefilme. Werkstatt-Aufnahmen verraten Anlagenstand, Fuhrpark, Team-Größe.
- **Google Maps Satellitenbild** — Werkstattgröße, Anzahl Servicewagen auf dem Hof, Lagerflächen. Kein Witz, das ist eine 5-Minuten-Sanity-Check für die behauptete MA-Zahl.

### Nice-to-have (Optional, je nach Tiefe)

- **ORBIS / Bureau van Dijk** — internationaler Datensatz, gut für Vergleichswerte aus EU-Nachbarländern. Pro-Account €5-15k/Jahr.
- **Creditreform / Schufa B2B** — Bonität, Mahnverhalten, Gesellschafterhistorie. Pro Anfrage €30-80.
- **TransparenzRegister** — Wirtschaftlich Berechtigte. Bei einfachen GmbH-Strukturen redundant zu OpenRegister; bei Holdings/Treuhand wertvoll.
- **kompass.com / wlw.de** — B2B-Listings, Branchenkategorisierung, manchmal Umsatzklassen-Schätzungen.
- **GoogleNews / ki-portal.de / kka-online.info / heatingandventilating.net** — siehe [05-sector-pack-hvac-r.md](./05-sector-pack-hvac-r.md). Branchen-Erwähnungen, Insolvenzen, Übernahmen, technische Auszeichnungen.
- **DPMA (Deutsches Patent- und Markenamt)** — eigene Marken? Patente? Bei Industriekälte selten relevant außer Spezial-Anlagenbauer.

## Was wir extrahieren — die "20 Datenpunkte pro Target"

Ein Stage-1-Dossier ist nicht eine 30-Seiten-Recherche. Es ist ein 1-Pager mit 20 Datenpunkten, jeder mit Quelle. Was nicht da ist, ist offen. Was geschätzt ist, ist mit "≈" markiert. Was nicht geschätzt werden kann, ist "tbd".

| # | Datenpunkt | Hauptquelle | Notiz |
|---|---|---|---|
| 1 | Firmenname, Rechtsform, Sitz | Handelsregister | |
| 2 | Gründungsjahr | Handelsregister | <15 Jahre = jung, Inhabergeneration evt. nicht reif zum Verkauf |
| 3 | Stammkapital | Handelsregister | <€100k bei >€2m Umsatz = signal für stille Reserven |
| 4 | Gesellschafterstruktur (% + Personen + Geburtsjahr) | OpenRegister + Northdata | Inhaberalter ist die Nummer-1-Variable |
| 5 | Geschäftsführer + Geburtsjahr | Handelsregister | GGF = Gesellschafter-Geschäftsführer? |
| 6 | Bilanzsumme letzte 3 Jahre | Bundesanzeiger | Wachstum/Schrumpfung, Anlagenintensität |
| 7 | Eigenkapitalquote | Bundesanzeiger | <20% = höhere Bankenkomplikation, >50% = wahrscheinlich stille Reserven |
| 8 | Anlagevermögen-Struktur | Bundesanzeiger | Werkstatt? Firmenwagen? Maschinen? |
| 9 | Rückstellungen | Bundesanzeiger | Pensionszusagen GGF? Garantien? |
| 10 | Mitarbeiterzahl ≈ | Website + Kununu + LinkedIn-Suche + Maps | Trianguliert |
| 11 | Wartungs-Anteil-Indikatoren | Website-Sektion "Service", Stellenanzeigen | "Wartungstechniker gesucht" = Indikator hoher Wartungsanteil |
| 12 | Endkunden-Mix-Indikatoren | Referenzen-Liste auf Website, Kunden-Logos | LEH? Datacenter? Industrie? Foodservice? |
| 13 | Innungs- / VDKF-Mitgliedschaft | VDKF-Verzeichnis, Handwerkskammer | Qualitätssignal |
| 14 | F-Gas-Zertifikat | BAFA-Register | Pflicht — wenn nicht da, Red Flag |
| 15 | Meister-Eintrag HwO Anlage A | HwK-Register | Pflicht |
| 16 | Lokale Wettbewerbsdichte | Innungs-Liste, Maps "Kältetechnik [Stadt]" | Anzahl Konkurrenten in 50-km-Radius |
| 17 | PE/Strategen-Aktivität in Region | Bundesanzeiger Suche, News, Northdata Verflechtungen | bluu unit / Vaventus / Salvia / Builtech / Köberl Spuren? |
| 18 | Reputation (Reviews, Kununu) | Google + Kununu | Stichworte: "Wartung", "schnell", "Inhaber" |
| 19 | Karriere/Recruiting-Aktivität | Karriereseite, Stellenanzeigen, Indeed | Aktiv = Wachstumsmodus, inaktiv = Stagnation |
| 20 | Web-Modernisierungsstand | Wayback Machine | Letztes echtes Update — Indikator für Inhaber-Aufmerksamkeit |

## Stage-1 Dossier Template (Output dieser Stufe)

Pro Target eine Markdown-Datei `01-public/stage-1-dossier.md` mit dieser Struktur:

```markdown
# Stage-1 Dossier — [Codename]

**Datum:** YYYY-MM-DD
**Recherche durch:** [Niko/Caspar]
**Zeitaufwand:** [hh:mm]

## Eckdaten
- Firma: [Klarname — nur in dieser internen Datei, nicht in Manual oder Outputs]
- Codename: [Alpha/Bravo/...]
- Rechtsform / Sitz: GmbH, [PLZ Stadt, Bundesland]
- Gründung: [Jahr]
- Stammkapital: [€]
- Gesellschafter: [Name, %, Geburtsjahr] × N
- GGF: [Name, Geburtsjahr]

## Größenschätzung
- Bilanzsumme 2024 / 2023 / 2022: [€ / € / €]
- Eigenkapitalquote: [%]
- Mitarbeiter ≈: [N] (trianguliert: Website [W], Kununu [K], LinkedIn [L], Maps [M])
- Umsatz-Schätzung: €[X-Y]m (Heuristik: Bilanzsumme × [Faktor], MA × €150-200k Umsatz/Kopf)
- EBITDA-Schätzung: €[X-Y]k (15-20% Marge bei Service-lastigem Mix; <10% bei Projekt-lastigem)

## Geschäftsmodell-Indikatoren
- Service vs. Projekt: [Schätzung %/% mit Begründung]
- Endkunden-Mix: [LEH/Datacenter/Industrie/Foodservice/Pharma — Schätzung mit Quellen]
- Geo-Footprint: [Radius, Bundesland, Stadt]
- Spezialisierung: [Industriekälte / Klima / Kombination / Wärmepumpe]
- Natürliche Kältemittel-Kompetenz (CO₂/NH₃)? [Ja/Nein/Unklar — basierend auf Website + Stellenanzeigen]

## Qualifikations- und Compliance-Status
- VDKF: [Mitglied seit / Nein]
- Handwerkskammer Anlage A Meister: [Eintrag ja/nein, Meister-Name]
- BAFA F-Gas-Zertifikat: [Status, Cat]
- Sachkundenachweise im Team: [Hinweise aus Stellenanzeigen / LinkedIn-Profilen]

## Reputation
- Google: [Stern-Ø, Anzahl, Tonnotz]
- Kununu: [Stern-Ø, Anzahl, Top-2-Themen pro/contra]
- Branchenpresse-Erwähnungen letzte 3 Jahre: [Liste]

## Wettbewerbskontext
- Lokale Wettbewerber (50 km): [Anzahl, Top-3 namentlich]
- PE/Strategen-Spuren in Region: [bluu/Vaventus/Salvia/Köberl/Builtech — ja/nein/wo]
- Geographische Marktdichte: [hoch/mittel/dünn]

## Drei Hypothesen für den Erstcall
1. **H-A:** [Vermutung über Geschäftsmodell] — Verifikation im Erstcall durch [konkrete Frage].
2. **H-B:** [Vermutung über Inhabermotivation] — Verifikation durch [Frage].
3. **H-C:** [Vermutung über Risiko/Chance] — Verifikation durch [Frage].

## Offene Punkte (im Erstcall klären)
- [Liste 5-8 konkreter Fragen]

## Empfehlung
[Kontaktieren | Beobachten | Skip] — Begründung in 2 Sätzen.

## Quellen-Anhang
[Liste aller URLs und Datei-Pfade]
```

## Pre-IOI Hypothesen-Brief

Aus dem Stage-1-Dossier destillieren wir vor dem Erstgespräch einen 1-Seiten-Brief, den wir als Niko-Caspar-Pair durchgehen. Das ist *nicht* das Dossier; das ist der konzentrierte Decision-Driver. Struktur:

```markdown
# Pre-IOI Brief — [Codename]
**Datum Erstcall:** YYYY-MM-DD HH:MM
**Lead Niko/Caspar:** [Wer führt das Gespräch]

## Why this target (3 Sätze)
[Warum reizt uns diese Firma — passt zur Plattform-Logik, zur Region, zum Wartungs-Mix?]

## Three KSDs to test
- KSD-A (Geschäftsmodell): [Hypothese] — Frage im Call: "[konkrete Frage]"
- KSD-B (Inhabermotivation): [Hypothese] — Frage: "[konkret]"
- KSD-C (Top-Risiko): [Hypothese] — Frage: "[konkret]"

## Was wir nicht fragen werden im Erstcall
[Bewusst vermeiden: Preisvorstellung, konkrete EBITDA, Mitarbeiterprobleme — das sind Stage-2-Themen]

## Eröffnung & Tonart
[Wir sind keine Heuschrecke, kein Klassen-PE. Wir sind 2 ex-Bain-Berater, die selbst kaufen wollen, mit Kapital von Schweizer Familien. Wir wollen verstehen, nicht verkaufen.]

## Decision-Gate post-Call
- Go: [3+ KSDs grün, Inhaber will weiter, EBITDA ≥€500k vermutbar] → Folgecall + erste P&L anfragen
- Stop: [≥1 KSD definitiv rot, Inhaber im Verkaufsmodus mit anderen, oder Größe deutlich zu klein] → höflich abschließen
```

## Was Claude in Stage 1 macht

Claude nimmt die Roh-Quellen (Bundesanzeiger-PDF, OpenRegister-Auszug, Website-Scrape, Google-Reviews-Export, Kununu-Export) und produziert das Stage-1-Dossier in einem Durchlauf. Konkret:

1. **Datenpunkte 1-9** (Handelsregister + Bundesanzeiger): Claude liest die PDF/HTML-Auszüge und füllt die strukturierten Felder.
2. **Datenpunkte 10-12** (MA-Schätzung, Wartungsanteil, Endkunden-Mix): Claude analysiert Website-Scrape, Stellenanzeigen, Referenzlisten und trianguliert.
3. **Datenpunkte 13-20** (Compliance, Reputation, Wettbewerb): Claude crawlt VDKF-Verzeichnis, BAFA-Liste, Innungs-Liste, Google-Reviews, Wayback-Snapshots.
4. **Hypothesen + Brief**: Claude entwirft H-A/B/C aus dem Dossier; wir verfeinern.

Konkrete Prompts und Slash-Command-Vorschläge in [06-claude-code-playbook.md](./06-claude-code-playbook.md). Empfohlener Slash-Command: `/dd-public-screen <codename>`.

## Decision-Gate Stage 1 → Stage 2

Wir gehen nur in den Erstcall, wenn:
- Inhaberalter ≥55 oder Verkaufssignal klar.
- Geschätzter Wartungsanteil >50%.
- Geschätzter Umsatz €1-15m / EBITDA-Schätzung €500k-5m (unser Band).
- Keine Insolvenz-Spuren, keine offene PE-Akquisition gemäß News-Search.
- F-Gas + Meister-Eintrag vorhanden (sonst Asset-Deal-Komplikation pre-Close).
- 3 plausible Hypothesen formuliert.

Wenn nur 4/6 grün: Beobachten, in 6-12 Monaten erneut. Wenn ≥3/6 rot: Skip dauerhaft, Notiz in CRM.

## Related

- [Overview](./overview.md)
- [Stage 2 — IOI/LOI mit erster P&L](./02-stage-2-ioi-loi-first-pl.md)
- [Sector Pack — Industriekälte/HVAC-R](./05-sector-pack-hvac-r.md)
- [Claude-Code-Playbook](./06-claude-code-playbook.md)
- [Templates & Output-Formate](./07-templates.md)
- Notion: [Brokerübersicht](https://www.notion.so/34b0260c95ef80baac4adfd1286c6e01) (komplementärer Sourcing-Channel)
- Notion: [Target Outreach Strategie](https://www.notion.so/3400260c95ef8173b2d1f171802505c2)
