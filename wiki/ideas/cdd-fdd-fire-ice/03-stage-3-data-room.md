---
title: "Stage 3 — Full Data Room (BWA / SuSa / Jahresabschluss)"
type: "note"
summary: "Wie wir den vollen Datenraum bei einem €500k–5m EBITDA Industriekälte-Target verarbeiten — DATEV-Standardkontenrahmen lesen, BWA→GuV-Reconciliation, Working-Capital aus der Bilanz, QofE-Bridge final, FDD-Report-Output."
status: "active"
tags: ["fire-ice", "dd", "stage-3", "data-room", "bwa", "susa", "jahresabschluss", "datev", "qofe", "fdd"]
source_files: []
updated: "2026-05-08"
---

# Stage 3 — Full Data Room (BWA / SuSa / Jahresabschluss)

Stage 3 beginnt mit dem unterschriebenen LOI und endet mit dem Self-IC-Memo + SPA-Verhandlung. Wir bekommen Zugang zu 24-36 Monaten BWA, 12-24 Monaten SuSa, 3-5 Jahren Jahresabschluss, Anlagespiegel, Verträgen, Mitarbeiterliste, ggf. Mgmt-Präsentation. 4-8 Wochen Bearbeitungszeit. Output: QofE-Bridge final, CDD-Report, FDD-Report, Self-IC-Memo.

## Was im Datenraum steht — und was nicht

### Was wir typisch bekommen

- **BWA monatlich (24-36 Monate):** "Betriebswirtschaftliche Auswertung" aus DATEV oder einem DATEV-Wettbewerber (Lexware, Addison, sevDesk seltener). PDF oder Excel. Pro Monat eine Seite mit Umsatz, Wareneinsatz, Personalkosten, sonstigen Kosten, Kostengruppen-Ergebnis. Ist *nicht* GuV im strengen Sinne, sondern eine Management-Auswertung mit Plausibilisierungen vom Steuerberater.
- **SuSa quartalsweise oder jährlich:** "Summen- und Saldenliste". Vollständige Kontenliste mit Soll-/Haben-Summen und Saldo per Stichtag. Granulare Sicht auf jedes Konto (z.B. Konto 8400 "Erlöse Wartungsverträge" vs. Konto 8410 "Erlöse Reparaturen" vs. Konto 8430 "Erlöse Projekte"). Aus SuSa lassen sich die *echten* Mix-Verhältnisse herausziehen, die in der BWA aggregiert sind.
- **Jahresabschluss (3-5 Jahre):** Bilanz + GuV + Anhang + ggf. Lagebericht (nur bei mittelgroßen GmbHs Pflicht — bei unseren Targets meist nicht) + Anlagespiegel.
- **Anlagespiegel:** Pro Anlagengruppe (Werkstatt-Equipment, Fahrzeuge, BGA, Software, etc.) Anschaffungswerte, kumulierte AfA, Restbuchwert, Zugänge/Abgänge/Umbuchungen. Wesentlich für Capex-Normalisierung.
- **Mitarbeiterliste:** Name, Funktion, Eintrittsdatum, Geburtsdatum, Bruttogehalt, ggf. Sachkundenachweis-Status, Vertragsart (unbefristet/befristet, VZ/TZ).
- **Top-20-Kundenliste mit Umsatz 2-3 Jahre:** verfeinert aus Stage 2.
- **Vertragsbestand:** Wartungsverträge mit Laufzeit, Volumen, Verlängerungsklauseln.
- **Lieferantenverträge:** Großhändler-Konditionen, Hersteller-Partnerprogramme (Daikin, Mitsubishi, Bitzer, etc.).
- **Steuerbescheide letzte 3 Jahre:** Körperschaft, Gewerbe, USt; Betriebsprüfungsstand.
- **Mietvertrag Werkstatt / Verwaltungssitz:** Vermieter (ggf. Inhaber-Privat = Cross-Reference zu Inhaber-Normalisierung), Laufzeit, Index.
- **F-Gas Compliance Akte:** Zertifikate, Schulungen, Anlagenliste mit Kältemittel-Inventar.
- **Versicherungspolicen:** Berufshaftpflicht, Betriebshaftpflicht, Maschinenversicherung, D&O.

### Was wir nicht bekommen (aber brauchen)

- **Dimensions-getrennte Profitabilität pro Kunde / Projekt / Region.** Bei dieser Größe gibt es keine Kostenstellenrechnung. Wir bauen sie selbst aus SuSa + Kundenliste + Mitarbeiter-Allokation.
- **Echte Cashflow-Rechnung.** HGB-GuV ist akkrual; Cashflow muss aus Bilanz-Differenzen + GuV abgeleitet werden.
- **Pipeline / Auftragsbestand strukturiert.** Inhaber sagt "wir haben 12 Wochen voll" — wir wollen das in einer Excel mit Auftrag, Volumen, Wahrscheinlichkeit, geplanter Ausführung.
- **Customer churn data.** Wir konstruieren aus Kundenliste 2023 vs. 2024 vs. 2025 die Verweildauer/Verlust selbst.

## DATEV-Standardkontenrahmen — Mini-Primer für SKR03 / SKR04

Die meisten Mittelstands-GmbHs kontieren in **SKR03** (industrieller Standard, Konten nach Bilanzposition organisiert) oder **SKR04** (kostenrechnungsorientiert, gleichartiger Aufbau wie HGB-Bilanz). Service-Handwerksbetriebe nutzen oft SKR03. Beide werden von DATEV geliefert.

**Wichtigste Kontengruppen für ein HVAC-R-Service-Target (SKR03):**

| Kontogruppe | Was es ist | Warum es uns interessiert |
|---|---|---|
| 0xxx | Anlagevermögen | Werkstatt-Equipment, Fuhrpark, BGA — Capex-Pattern |
| 1xxx | Umlaufvermögen / Bestände | Material, halbfertige Arbeiten, Forderungen — Working-Capital |
| 2xxx | Verbindlichkeiten / passive Rechnungsabgrenzung | Lieferantenkredite, Bankschulden, erhaltene Anzahlungen |
| 3xxx | Vorsteuer / USt | Cross-Check zu USt-Vorauszahlungen |
| 4xxx | Personalkosten | Lohn, Gehalt, SV, GGF-Bezüge, Tantiemen |
| 5xxx | Wareneinsatz | Material, Fremdleistungen, ggf. Sub-Unternehmer |
| 6xxx | Sonstige betriebliche Aufwendungen | Mieten, Versicherungen, Pkw, Reise, Werbung, Beratung |
| 7xxx | Steuern, Zinsen | Gewerbesteuer, KSt, Zinserträge/-aufwand |
| 8xxx | Erlöse | Wartung, Reparatur, Projekte, Material-Weiterverkauf — **Mix-Analyse hier** |
| 9xxx | Vortragskonten / Statistik | meist intern |

**Wichtigste konkrete Konten für unser Target:**

- **8400er-Reihe (Erlöse):** 8400 Erlöse 19% USt allgemein, 8410 Wartungserlöse, 8420 Reparaturerlöse, 8430 Projekterlöse, 8440 Materialweiterverkauf. Aus diesen Konten ziehen wir den *echten* Mix.
- **5000er-Reihe (Wareneinsatz):** 5000 Materialaufwand, 5400 Fremdleistungen / Sub-Unternehmer. Verhältnis 5400 zu Eigenleistung interessiert uns für die Frage "wie viel Outsourcing".
- **4100er-Reihe (Löhne):** 4100 Löhne Gewerbliche, 4120 Gehälter Angestellte, 4130 GGF-Vergütung. Aufteilung Monteur/Verwaltung.
- **4310 Soziale Abgaben:** Plausibilisierung gegen Bruttolohnsumme (~20%).
- **6300er Mieten / 6303 Inhaber-Miete:** Cross-Check Inhaber-Vermietung.
- **6700 Pkw-Aufwand:** mit Privatanteil-Frage.
- **0240 Fuhrpark + 0250 Werkstatt-Einrichtung:** Anlagenstand für Capex-Diskussion.
- **0600 / 1300er Bank/Kasse:** Liquiditätsstand.
- **1400er Forderungen / 1600er Verbindlichkeiten:** Working-Capital.

Claude soll mit dem SKR03-Mapping arbeiten — wir laden eine SKR03-Referenztabelle einmal ins Deal-CLAUDE.md, dann interpretiert es jeden Konto-Code richtig.

## BWA lesen — Aufbau und Fallstricke

Eine Standard-DATEV-BWA hat folgenden Aufbau (Monatswerte + Vorjahresvergleich):

```
1. Umsatzerlöse                           XXX     YY%   ggü. VJ +/- Z%
2. Bestandsveränderungen                  XXX
3. Aktivierte Eigenleistungen             XXX
4. Sonstige betriebliche Erträge          XXX
   Gesamtleistung                         ===

5. Materialaufwand                       (XXX)
6. Roh-Ergebnis                          ===

7. Personalaufwand                       (XXX)
8. Abschreibungen                        (XXX)
9. Sonstige betriebliche Aufwendungen    (XXX)
   Betriebsergebnis (vorl. EBIT)          ===

10. Zinsen und ähnliche Erträge           XXX
11. Zinsen und ähnliche Aufwendungen     (XXX)
    Neutrales Ergebnis                    ===

    Vorläufiges Ergebnis vor Steuern      ===
```

**Fallstricke beim BWA-Lesen:**

- **"Vorläufig"** — die BWA ist nicht testiert, der Steuerberater hat möglicherweise Korrekturen, Abgrenzungen und USt-Buchungen noch nicht eingearbeitet. Die monatliche BWA und der Jahresabschluss können um 5-15% am EBIT divergieren. Wir vergleichen immer beide.
- **Periodengerechte Abgrenzungen fehlen oft.** Personalaufwand wird kontinuierlich gebucht, aber Umsatz erst bei Rechnungsstellung — wenn Projekte unterbeendet sind, ist die Monats-BWA bei Service-Projekt-Mix verzerrt.
- **Bestandsveränderungen können "kosmetisch" sein.** Manche Steuerberater nutzen sie, um Quartalsergebnisse zu glätten. Hinterfragen.
- **Aktivierte Eigenleistungen** verschieben Aufwand zu Anlage. Bei <€10k unkritisch, bei >€30k klären.
- **AfA in BWA vs. Jahres-AfA.** Monats-BWA verteilt linear; Jahres-AfA enthält Korrekturen, Sonderabschreibungen.

## SuSa lesen — Granulare Sicht

Die SuSa zeigt jedes Konto mit Soll-/Haben-Summe und Saldo per Stichtag. Was wir damit machen:

1. **Mix-Reconstruction.** 8410 (Wartung) + 8420 (Reparatur) + 8430 (Projekte) + 8440 (Material-Weiterverkauf) → echter Wartungsanteil. Vergleichbar zur Stage-2-Frage. Wenn Inhaber sagt "60% Wartung" und SuSa sagt "42% Wartung, 28% Reparatur, 25% Projekte, 5% Material" — das ist ein Gespräch.
2. **Personalaufwand granular.** 4100 vs. 4120 vs. 4130 → Monteur/Angestellten/GGF-Verhältnis.
3. **Material-Schwankungen.** Konto 5000 monatlich → Zusammenhang zu Umsatzkonten → echte variable Kostenquote.
4. **Sonstige-Aufwendungen-Detektivarbeit.** 6700 Pkw, 6300 Mieten, 6800 Reisekosten, 6815 Bewirtung, 6820 Werbung, 6850 Beratungskosten — jede Position einzeln plausibilisieren gegen MA-Anzahl, Umsatz, Branchen-Benchmark.
5. **Working-Capital-Analyse.** 1400er Forderungen, 1500 halbfertige Arbeiten, 1600er Verbindlichkeiten LL, 2700 erhaltene Anzahlungen → DSO, DPO, Working-Capital-Quote zu Umsatz.
6. **Periodische Konten-Bewegungen.** Garantierückstellungen, Urlaubsrückstellungen, Boni — Auflösungs-/Zuführungs-Pattern.

## Jahresabschluss — Komponenten und was bei kleinen GmbHs fehlt

Der HGB-Jahresabschluss besteht aus:

| Komponente | Pflicht bei Kleinst | Pflicht bei Klein | Pflicht bei Mittelgroß |
|---|---|---|---|
| Bilanz | Verkürzt | Verkürzt | Voll |
| GuV | Nein* | Nein* | Voll |
| Anhang | Nein | Verkürzt | Voll |
| Lagebericht | Nein | Nein | Ja |
| Anlagespiegel | Nein | Im Anhang | Im Anhang |
| Kapitalflussrechnung | Nein | Nein | Nein (Pflicht erst KapGes-Konzern) |
| Eigenkapitalspiegel | Nein | Nein | Nein |

*GuV-Hinterlegung beim Bundesanzeiger ist bei Klein-GmbHs nicht Pflicht; bei Verkaufsprozess bekommen wir sie im Datenraum. Die Größenklassen gem. §267 HGB werden in [04-hgb-quirks.md](./04-hgb-quirks.md) detailliert.

**Was wir aus dem Anhang ziehen — wenn er existiert:**

- Bilanzierungs- und Bewertungsmethoden (FIFO/LIFO, Abschreibungsmethoden, Rückstellungs-Bewertung).
- Pensionsrückstellungen (Berechnungsverfahren — Teilwert, BilMoG-Niveau).
- Verbindlichkeiten Restlaufzeit-Aufgliederung.
- Anteilsbesitz an verbundenen Unternehmen.
- Geschäfte mit nahestehenden Personen (DAS ist gold — Inhaber-Immobilien-Vermietung steht hier).
- Anzahl Mitarbeiter (Durchschnitt im GJ).
- Abschlussprüfer-Honorar (wenn nicht prüfungspflichtig: nicht enthalten).

**Wenn der Anhang dünn ist (Kleinst-GmbHs ohne freiwilligen Anhang):** wir bauen die fehlenden Informationen aus SuSa + Anlagespiegel + Direkt-Anfragen an den Steuerberater. Siehe [04-hgb-quirks.md](./04-hgb-quirks.md) für die "30 Dinge, die im Anhang nicht stehen aber stehen sollten".

## Reconciliation BWA-monthly → GuV-annual

Standard-Diskrepanz-Analyse pro Konto-Familie. Wir bauen eine Excel mit drei Spalten:

| Position | BWA Σ Monate | GuV (Bundesanzeiger oder DR) | Δ | Erklärung |
|---|---|---|---|---|
| Umsatz | ... | ... | ±X% | meist Periodenabgrenzungen |
| Materialaufwand | ... | ... | ±Y% | Stichtags-Zukäufe, Bestandsveränderungen |
| Personalaufwand | ... | ... | ±Z% | Boni, Urlaubsrückstellungen, BilMoG-Anpassungen |
| Sonstige Aufwendungen | ... | ... | ... | jährliche Versicherungen, Beraterhonorare |
| AfA | ... | ... | ... | linear vs. degressiv, Sonderabschreibungen |

Δ <2% = ok, 2-5% = Erklärung erforderlich, >5% = Red Flag und mit StB des Targets klären.

## Working-Capital aus der Bilanz

| Position | Konto | Bedeutung |
|---|---|---|
| Forderungen aus Lieferungen und Leistungen | 1400er | Days Sales Outstanding (DSO) — schlechte Zahler? |
| Halbfertige Arbeiten | 1500 | Project Backlog buchhalterisch — wachsend = mehr offene Projekte |
| Erhaltene Anzahlungen | 2700 | Vorauskassen — gutes Liquiditätspolster |
| Verbindlichkeiten aus LL | 1600er | Days Payable Outstanding (DPO) — Lieferantenbeziehung |
| Bank/Kasse | 0600/1300 | Working-Capital-Reserve |
| Bankverbindlichkeiten kurzfristig | 1620er | Saisonal-Linie? |

Berechnungen:
- **DSO** = (Forderungen LL × 365) / Umsatz brutto. Industriekälte typisch 30-60 Tage. >75 = Inkasso-Problem.
- **DPO** = (Verbindlichkeiten LL × 365) / Materialaufwand brutto. 30-45 Tage typisch. <20 = möglicherweise Skonto-genutzt; >60 = Lieferantenstress.
- **Working-Capital-Quote** = (Forderungen + Vorräte − Verbindlichkeiten) / Umsatz. 8-15% typisch im Service-Geschäft, 15-25% im Projektgeschäft.
- **Working-Capital-Bedarf bei Wachstum.** Pro €1 Umsatzwachstum brauchen wir ca. €0.10-0.15 Working Capital. Wichtig fürs Wachstumsfinanzierungs-Modell.

## Cut-off-Testing

Bei einem 31.12.-Abschluss prüfen wir die letzten 4 Wochen vor und die ersten 4 nach Stichtag stichprobenartig. Konkret:

- **Eingangsrechnungen Dez/Jan:** Sind alle Materialien, die im Dez geliefert wurden, auch im Dez gebucht? Oder ist Verschiebung erkennbar?
- **Ausgangsrechnungen Dez/Jan:** Sind alle Leistungen Dez auch Dez fakturiert? Oder Sammelrechnung Anfang Jan = "verschobener Umsatz"?
- **Bestandsaufnahme:** Ist eine ordentliche Inventur dokumentiert? Inventurprotokoll im Anhang oder im DR?
- **Halbfertige Arbeiten:** Plausible Bewertung gegen tatsächlichen Projekt-Stand?
- **Garantierückstellungen:** Im Vergleich zu tatsächlichen Garantieleistungen über letzte 3 Jahre — angemessen oder kosmetisch?

Cut-off-Probleme kosten typisch 5-15% des EBIT in einer Periode — kritisch für die Bridge.

## Vorratsbewertung im Service-Handwerksbetrieb

Industriekälte hat zwei Bestandskategorien: **Material auf Lager** (Ersatzteile, Standard-Komponenten) und **halbfertige Arbeiten** (Projekte mit Material- und Arbeitseinsatz vor Endabnahme). Beide können stille Reserven oder stille Lasten sein:

- **Materialbestand FIFO/LIFO/Durchschnitt** — Bewertungsmethode im Anhang. FIFO = höhere Bewertung in steigenden Märkten = höheres EBIT. Bei Kupferpreis-Schwankungen oder Kältemittel-Preisanstiegen relevant.
- **Halbfertige Arbeiten** — Ansatz zu Herstellungskosten oder zu erwartetem Erlös abzgl. Restkosten. Bei letzterem werden vorzeitige Gewinne realisiert; konservative Bewertung schiebt Gewinn ins nächste Jahr.
- **Niederstwertprinzip** — beizulegender Wert <Anschaffungskosten erzwingt Abschreibung. Bei alten F-Gas-Beständen (R22, R404A) kann das relevant werden.
- **Pauschalwertberichtigung Forderungen** — typisch 1-3% pauschal; höhere Quoten ohne dokumentierten Anlass = stille Last.

## Anlagespiegel-Analyse für Capex-Normalisierung

Der Anlagespiegel zeigt pro Anlagengruppe: Anschaffungswert kumuliert, Zugänge Berichtsjahr, Abgänge Berichtsjahr, kumulierte AfA, AfA Berichtsjahr, Restbuchwert. Daraus:

- **Capex-Run-Rate:** Σ Zugänge letzte 3-5 Jahre / 3-5 = laufender Capex. Wenn AfA > Capex über mehrere Jahre = Anlagenpark altert, Nachholbedarf.
- **Restbuchwert / Anschaffungswert je Gruppe:** <30% bei Werkstatt-Equipment = stark abgeschrieben, ggf. Sanierungs-/Erneuerungsbedarf. Beim Fuhrpark <40% = Fahrzeuge >5 Jahre alt im Schnitt.
- **Sonderabschreibungen (degressiv, AfaA):** stille Reserven (Anlagen mit Restbuchwert €0, faktischem Wert >0) sind gut für die Bilanz aber "frisst" zukünftiges EBIT-Polster — wir nehmen für Run-Rate eine *normalisierte* AfA (linear über Nutzungsdauer), nicht die HGB-AfA.
- **Geringwertige Wirtschaftsgüter (GWG):** Sofortabschreibung für Anlagen <€800 oder Sammelposten <€1000. Im Service-Handwerksbetrieb signifikant (Werkzeuge). Plausibilisieren.

## Pensionsrückstellungen / Garantierückstellungen

- **Pensionsrückstellung GGF:** Direktzusage des Inhabers an sich selbst. Berechnet nach §6a EStG (Teilwert) oder BilMoG-Niveau (HGB §253). HGB > Steuerbilanz typisch um 10-30%. Cross-Check Anhang. Im Verkauf entweder vom Käufer übernommen (mit Bewertungs-Diskussion) oder ausgelagert (Pensionssicherungsverein) oder durch Versicherung gedeckt.
- **Pensionszusagen weitere MA:** seltener, aber bei Altbestand möglich.
- **Garantie-/Gewährleistungsrückstellungen:** Im Projektgeschäft typisch 1-3% des Projektumsatzes der letzten 2 Jahre, bei besonders kritischen Branchen (Pharma, Lebensmittel) höher. Auflösungs-/Zuführungs-Pattern prüfen — kosmetische Bewegungen sind klassisches EBIT-Glätten.

## QofE — Quality of Earnings — Mid-Market-Standard-Template

Die QofE-Bridge in Stage 3 ist die finale, pflicht-detaillierte Version der Bridge aus Stage 2. Sie ist 12-Zeilen, pro Zeile mit eindeutigem Source-Anchor (BWA-Konto, SuSa-Eintrag, Anhang-Position).

```
QofE-Bridge — Codename Alpha — LTM per 2025-12-31
                                          | EUR k  | Quelle
A. Reported EBITDA HGB                    |   340  | GuV 2025 BoH
B. + GGF-Vergütung Normalisierung         |  +170  | Konto 4130, Mgmt-Marktvergleich
C. + GGF-Pension Zuführung                |   +35  | Anhang, Konto 4920
D. + Familie-in-Lohn (Ehefrau, Kinder)    |   +60  | MA-Liste, Konto 4120
E. + Pkw-Privatanteil + Reisekosten       |   +25  | Konto 6700, 6800
F. + Inhaber-Immo-Miete-Excess            |   +35  | Konto 6303, Marktmiete-Bench
G. + Einmaleffekte (Beraterhonorare etc.) |   +20  | Konto 6850, GuV "Sonstige Erträge/Aufwendungen"
H. − Capex-Nachzieh-Bedarf normalisiert   |   -20  | Anlagespiegel-Analyse
I. = Adjusted EBITDA                      |   665  |
J. + Run-Rate-Aufschlag (LTM × 1.05)      |   +33  | Pipeline + bestätigte Wartung-Conv.
K. = Run-Rate EBITDA                      |   698  |
L. − Quality-Adjustments                  |   -178 | Konzentration, Inhaber-Risk, F-Gas-Capex
M. = Quality-adjusted EBITDA              |   520  | ← Bewertungsbasis
```

Auf M wenden wir das Multiple an. Der Inhaber will I; wir verhandeln zwischen K und M.

## CDD-Report-TOC (12 Sektionen)

Stand-alone Dokument, 30-50 Seiten, mit Excel-Anhängen.

1. Executive Summary — KSDs, Empfehlung, Bewertungs-Range.
2. Markt — TAM, Wachstum, F-Gas-Treiber, Klima-Wachstum (siehe [Sector Pack](./05-sector-pack-hvac-r.md)).
3. Wettbewerbslandschaft — bluu/Vaventus/Salvia, lokale Wettbewerber, Marktanteile.
4. Geschäftsmodell des Targets — Wartung/Projekt-Mix, Endkunden-Branchen, Geographie.
5. Kunden — Konzentration, Loyalty, Top-20-Cube, Reference-Calls-Synthese.
6. Lieferanten und Wertschöpfung — Großhändler, Hersteller-Partnerschaften, Material-Mix.
7. Personal und Organisation — Altersstruktur, Sachkundenachweis, Schlüsselpersonen, Recruiting-Track.
8. Operations — Auftragsmanagement, IT, Werkstatt, Fuhrpark.
9. Compliance — F-Gas, Meister, Innung, Versicherungen.
10. Marktposition und Wettbewerbsvorteile — was macht das Target verteidigungsfähig.
11. Wachstumsoptionen — organisch, geographisch, Endkunden, Technologie.
12. Top-5-Risiken und Mitigationen.

## FDD-Report-TOC (10 Sektionen)

Stand-alone Dokument, 25-40 Seiten, mit Excel-Anhängen (QofE-Bridge, Working-Capital-Cube, Anlagespiegel-Analyse, Pipeline-Modell).

1. Executive Summary — Adjusted vs. Quality-adjusted EBITDA, Working-Capital-Bedarf, Capex-Run-Rate.
2. Historische GuV (3-5 Jahre) — Roh und normalisiert, Trends, Saisonalität.
3. EBITDA-Bridge — die 12-Zeilen-Bridge mit Source-Anchors.
4. Working-Capital — DSO, DPO, halbfertige Arbeiten, saisonale Schwankung.
5. Capex und Anlagespiegel — Run-Rate, Nachholbedarf, F-Gas-Investments.
6. Bilanz-Analyse — stille Reserven/Lasten, Pensions-/Garantierückstellungen, Inhaber-Verbindlichkeiten.
7. Steuern — Bp-Stand, Steuersatz, latente Steuern, Verlustvorträge.
8. Pipeline und Run-Rate — bestätigte Wartung-Conversions, Auftragsbestand, saisonale Verteilung.
9. Cashflow-Profile — Free Cashflow nach Working-Capital + Capex.
10. Sensitivitäten — fünf Szenarien, EBITDA-Wirkung, Equity-Effekt.

## Was Claude in Stage 3 macht

Claude trägt 60-70% der mechanischen Last. Konkret pro Sub-Aufgabe:

1. **PDF/Excel-Ingest:** Datenraum-Files in `/03-dataroom/raw-pdfs/` und `/03-dataroom/extracted/` — Claude OCR-extrahiert PDF (DATEV exportiert oft als Bild-PDF), strukturiert in JSON, validiert Plausibilität.
2. **BWA-Aggregation:** 24-36 Monats-PDFs → eine Excel-Tabelle mit Monatswerten. Claude erkennt das DATEV-BWA-Layout und extrahiert.
3. **SuSa-Konto-Mapping:** SKR03-Konten klassifizieren (Erlöse-Familie, Personal-Familie, sonstige), Mix-Verhältnisse berechnen, Anomalien flaggen.
4. **BWA→GuV-Reconciliation:** Tabelle pro Konto-Familie, Diskrepanz-Analyse, Erklärungs-Vorschläge.
5. **EBITDA-Bridge final:** aus Adjusted-Liste + KSD-Risiken + Capex-Nachholbedarf → 12-Zeilen-Bridge mit Source-Anchors.
6. **Working-Capital-Cube:** Aufbau aus Bilanz × 3-5 Jahre, DSO/DPO-Berechnung, saisonale Schwankungen aus BWA.
7. **Anlagespiegel-Analyse:** AfA vs. Capex über 5 Jahre, Restbuchwert-Quoten, Identifikation Capex-Nachholbedarf.
8. **Customer-/Supplier-/Ex-MA-Calls Synthese:** 12-15 Calls je → strukturierte Cluster-Synthese, Citation auf Call-Transkripte.
9. **CDD-Report Erstentwurf:** aus allen Sources → 30-Seiten-Erstentwurf, wir polieren.
10. **FDD-Report Erstentwurf:** dito, mit Excel-Anhängen verlinkt.
11. **Self-IC-Memo Erstentwurf:** Executive-Summary-Format, KSDs, Bewertung, Sensitivitäten, Empfehlung.

Empfohlene Slash-Commands: `/dd-bwa-ingest`, `/dd-susa-mix`, `/dd-bridge-final`, `/dd-wc-cube`, `/dd-anlagen-capex`, `/dd-cdd-draft`, `/dd-fdd-draft`, `/dd-ic-memo`. Details und Prompts in [06-claude-code-playbook.md](./06-claude-code-playbook.md).

## Decision-Gate Stage 3 → SPA

Wir gehen in die SPA-Verhandlung nur, wenn:
- Quality-adjusted EBITDA bestätigt mit <±10% gegen Stage-2-Schätzung.
- Reconciliation BWA-GuV pro Konto-Familie <5% Diskrepanz oder erklärt.
- Customer-Reference-Calls bestätigen die KSD-Hypothesen (mind. 10/15 grün).
- Working-Capital-Bedarf und Capex-Nachholbedarf finanziell tragbar (<20% des Equity-Volumens).
- Keine roten Compliance-Themen (F-Gas-Lecks, Steuer-Bp offen, Mitarbeiter-Klagen).
- Self-IC-Memo zeigt Equity-Investment in allen 5 Stress-Szenarien positiv.

Wenn auch nur eines hart rot: zurück zum LOI-Verhandeln (Bewertung, Earn-out, Closing-Conditions) oder Abbruch.

## Related

- [Overview](./overview.md)
- [Stage 2 — IOI/LOI](./02-stage-2-ioi-loi-first-pl.md)
- [HGB-Quirks bei Klein-GmbHs](./04-hgb-quirks.md) — Größenklassen-Detail, durchgerechnete Bridge
- [Sector Pack — HVAC-R](./05-sector-pack-hvac-r.md)
- [Claude-Code-Playbook](./06-claude-code-playbook.md)
- [Templates — QofE-Bridge, FDD-TOC, Self-IC-Memo](./07-templates.md)
