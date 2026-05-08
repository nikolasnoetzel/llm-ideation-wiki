---
title: "HGB-Quirks bei Klein-GmbHs — wo HGB lügt und wie wir es fangen"
type: "note"
summary: "Größenklassen §267 HGB, Maßgeblichkeitsprinzip post-BilMoG, Handelsbilanz vs. Steuerbilanz, stille Reserven & Lasten, Inhaber-Normalisierungen, durchgerechnetes Beispiel an Generic Target Alpha. Plus: 30 Dinge, die im Anhang nicht stehen aber stehen sollten."
status: "active"
tags: ["fire-ice", "dd", "hgb", "bilmog", "stille-reserven", "datev", "inhaber-normalisierung"]
source_files: []
updated: "2026-05-08"
---

# HGB-Quirks bei Klein-GmbHs

Bei unseren Targets (€500k-5m EBITDA, typisch 5-25 MA, 2-15 Mio. Umsatz) bewegen wir uns fast immer in den HGB-Größenklassen "Kleinst" oder "Klein" gem. §267a/§267 HGB. Das hat dramatische Folgen für die Aussagekraft des offengelegten Jahresabschlusses — und für unsere Diligence-Strategie. Dieses Doc erklärt die Mechanik, listet die typischen Stille-Reserven-Hebel, und führt eine durchgerechnete EBITDA-Bridge an einem Generic-Target Alpha durch.

## Größenklassen §267/§267a HGB

Eine Kapitalgesellschaft muss zwei der drei Schwellen in zwei aufeinander folgenden Geschäftsjahren überschreiten, um in die nächste Klasse zu fallen.

| Klasse | Bilanzsumme | Umsatzerlöse | Mitarbeiter (Ø) |
|---|---|---|---|
| Kleinst (§267a) | ≤ 450 k€ | ≤ 900 k€ | ≤ 10 |
| Klein (§267) | ≤ 7.5 Mio.€ | ≤ 15 Mio.€ | ≤ 50 |
| Mittelgroß | ≤ 25 Mio.€ | ≤ 50 Mio.€ | ≤ 250 |
| Groß | > 25 Mio.€ | > 50 Mio.€ | > 250 |

**Praktische Folgen für unsere Targets:**

| Kategorie | Kleinst | Klein | Mittelgroß |
|---|---|---|---|
| Bilanz-Veröffentlichungspflicht | Verkürzt (Hinterlegung statt Veröffentlichung möglich!) | Verkürzt | Voll |
| GuV-Veröffentlichungspflicht | Nein | Nein | Ja |
| Anhang | Nein | Verkürzt | Voll |
| Lagebericht | Nein | Nein | Ja |
| Anlagespiegel | Im Anhang (wenn vorhanden) | Im Anhang | Im Anhang |
| Pflichtprüfung WP | Nein | Nein | Ja |

**Was das für uns heißt:**

- **Kleinst-GmbHs (~€450-900k Umsatz, <10 MA):** Wir sehen *nur* eine verkürzte Bilanz im Bundesanzeiger — Aktiva/Passiva auf 3-4 Zeilen. Kein GuV, kein Anhang. Der Kollege "Hinterlegung" (statt Veröffentlichung) bedeutet, dass selbst die Bilanz nur auf Anfrage einsehbar ist (kostenpflichtige Anfrage beim Bundesanzeiger). Hier liegen wir blind bis Stage 2.
- **Klein-GmbHs (~€900k-15 Mio. Umsatz, 11-50 MA):** unser typisches Target-Profil. Verkürzte Bilanz im Bundesanzeiger, kein GuV, verkürzter Anhang ohne Bilanzierungs-und-Bewertungsmethoden-Tiefe. Keine WP-Pflicht. **Das bedeutet: keine externe Plausibilisierung der Buchführung.** Der einzige Filter ist der Steuerberater.
- **Mittelgroße GmbHs (>15 Mio. Umsatz):** komplette Veröffentlichung, WP-Prüfung. Das sind nicht unsere Standard-Targets, aber unter Umständen Ankerakquisitionen für die Plattform.

**Implikation für die DD-Strategie:** Bei Klein-GmbHs ist der offengelegte Jahresabschluss *Marketingmaterial*, kein DD-Substrat. Echte FDD passiert in Stage 3 mit dem internen Datenraum (siehe [03-stage-3-data-room.md](./03-stage-3-data-room.md)).

## Maßgeblichkeitsprinzip — was es heute (post-BilMoG) wirklich bedeutet

Vor BilMoG 2010 galt: die Steuerbilanz orientiert sich strikt an der Handelsbilanz ("Maßgeblichkeit") und umgekehrt steuerliche Wahlrechte mussten in der Handelsbilanz mitgemacht werden ("umgekehrte Maßgeblichkeit"). Das hatte zur Folge, dass das HGB-EBIT an steuerlich günstigen Sonderabschreibungen reichlich nach unten gedrückt wurde.

**Post-BilMoG (gilt seit 2010):**
- **Maßgeblichkeit** in einer abgeschwächten Form bleibt — die Steuerbilanz folgt dem HGB-Ansatz, *außer* das Steuerrecht ordnet was anderes an.
- **Umgekehrte Maßgeblichkeit ist abgeschafft.** Steuerliche Wahlrechte (z.B. Sonderabschreibung §7g EStG) müssen *nicht* mehr in die Handelsbilanz übernommen werden. Theoretisch kann der HGB-Abschluss damit "ehrlicher" sein.
- **Praxis bei Klein-GmbHs:** der Steuerberater minimiert Aufwand. Er führt *eine* Buchhaltung, die er als HGB-Abschluss präsentiert und steuerlich überleitet. Das heißt: HGB-Abschluss enthält in der Realität *immer noch* steuerlich motivierte Bewertungen — degressive AfA wo möglich, GWG-Sofortabschreibung, hohe Rückstellungen, niedrige Vorratsbewertung. Stille Reserven entstehen als Nebenprodukt.
- Die Trennung Handelsbilanz / Steuerbilanz wird bei diesen Targets selten "richtig" gelebt. Latente Steuern werden bei Klein-GmbHs nicht ausgewiesen (Wahlrecht §274 Abs. 1 Satz 2 HGB).

**Was wir daraus ziehen:** wenn der StB sagt "wir machen Handelsbilanz und Steuerbilanz identisch", glauben wir das. Und wir gehen davon aus, dass das HGB-Ergebnis steuer-optimiert ist — also tendenziell *unter* dem ökonomischen Ergebnis.

## GoB / GoBD — Compliance-Signale

Die "Grundsätze ordnungsmäßiger Buchführung" (GoB, ungeschrieben + §238ff. HGB) und die "Grundsätze zur ordnungsmäßigen Führung und Aufbewahrung von Büchern, Aufzeichnungen und Unterlagen in elektronischer Form" (GoBD, BMF-Schreiben) regeln die formale Korrektheit der Buchführung. Bei Klein-GmbHs ist die Praxis sehr unterschiedlich. Was wir prüfen:

- **DATEV-Verfahrensdokumentation vorhanden?** GoBD-Pflicht. Wenn nicht, formaler Mangel — aber bei keiner Bp aufgefallen heißt = Risiko-Toleranz beim Käufer.
- **Belegerfassung digital oder Papier?** DATEV Unternehmen Online indiziert Modernität.
- **Letzte Betriebsprüfung — wann, mit welchem Ergebnis?** Wenn vor >5 Jahren = Bp-Risiko offen für ~3 Jahre nach Closing (Festsetzungsverjährung 4 Jahre + Anlaufhemmung).
- **Steuerbescheide unter Vorbehalt der Nachprüfung?** Standard, aber Volumen relevant.

## Stille Reserven (positiv) — die typischen 8 Hebel

Im Verkauf-Szenario will der Inhaber sie *nicht* zeigen, sondern als "echtes Eigenkapital" einpreisen. Wir zeigen sie auf, um die ökonomische Bilanz zu sehen.

| # | Hebel | Wo zu finden | Typische Größe |
|---|---|---|---|
| 1 | Werkstatt-Immobilie (im Betriebsvermögen, voll abgeschrieben) | Anlagespiegel "Bauten" | €100k-500k |
| 2 | Fuhrpark (Service-Wagen 6+ Jahre alt, Restbuchwert gegen €0, Marktwert 20-30% NP) | Anlagespiegel "Fahrzeuge" | €30k-150k |
| 3 | Werkstatt-Equipment (Spezialwerkzeuge, Hebebühnen, Diagnose) — degressiv abgeschrieben | Anlagespiegel "BGA" | €20k-100k |
| 4 | Wartungs-Vertragsbestand — Goodwill, in HGB nicht aktiviert | Nirgends — wir bewerten extern | €100k-1Mio.€ |
| 5 | Material-Lager LIFO-bewertet bei steigenden Preisen (Kupfer, Komponenten) | Anhang Bewertungsmethode | €10k-50k |
| 6 | Halbfertige Arbeiten zu Selbstkosten statt Marktwert | Bilanz Position 1500 | €20k-100k |
| 7 | Überdotierte Garantie-/Gewährleistungsrückstellungen | Bilanz / Anhang | €20k-100k |
| 8 | Pauschalwertberichtigung Forderungen >2% ohne Anlass | SuSa Konto 1450 | €5k-30k |

## Stille Lasten (negativ) — die typischen 6

| # | Last | Wo zu finden | Typische Größe |
|---|---|---|---|
| 1 | Unter-dotierte Pensionsrückstellung GGF (HGB-Niveau aber steueroptimal niedrig) | Anhang | €50k-300k |
| 2 | Capex-Nachholbedarf (Fuhrpark, F-Gas-Anlagen) | Anlagespiegel-Alter, externes Gutachten | €100k-500k |
| 3 | Garantieforderungen aus laufenden Projekten nicht zurückgestellt | Cut-off-Test | €20k-100k |
| 4 | Mitarbeiter-Klagen / drohende Arbeitsgerichts-Verfahren | Anhang ggf. unvollständig | €0-100k |
| 5 | Steuerbescheid unter Bp-Vorbehalt mit Risiko Schätzungs-Mehraufwand | Steuerakte | €0-200k |
| 6 | Altlasten Werkstattgrundstück (Öl, Lösemittel) | Phase-1-ESA durch externen Gutachter | €0-1Mio.€ |

Die Phase-1-ESA bei Werkstattgrundstück ist *Pflicht* bei jedem Industriekälte-Target. Werkstätten mit 30+ Jahren Geschichte haben fast immer Bodenkontamination unterhalb Sanierungsschwelle aber oberhalb Bagatellniveau — das wird Verhandlungspunkt.

## Inhaber-Normalisierungen im Detail

Was bei Klein-GmbHs systematisch im HGB-EBIT enthalten ist, aber in einer "normalen" GmbH so nicht wäre:

### 1. GGF-Vergütung
Inhaber-GF zahlen sich oft entweder *zu hoch* (steuerlich optimiert, Sozialabgaben gespart durch Tantieme/Pension statt Gehalt) oder *zu niedrig* (Ausschüttung statt Gehalt — KSt günstiger als ESt + SV). Wir vergleichen mit Marktbenchmark für vergleichbare GF-Position (€80-150k brutto bei 5-15-MA-Betrieb, €120-200k bei 15-30-MA-Betrieb). Differenz = Normalisierung.

### 2. GGF-Pension
Direktzusage des Inhabers an sich selbst, jährliche Zuführung €15-50k, dazu noch Steuervorteil weil Aufwand vor KSt + Vermögen "geparkt". Im Verkauf: entweder Übernahme der Verbindlichkeit (Kaufpreismindernd) oder Auslagerung an Versicherung (kostet ca. 15-20% mehr als HGB-Buchwert) oder Fortführung Direktzusage mit Schuldbeitritt. Wir normalisieren weg, weil unter neuem Eigentümer keine GGF-Pension mehr läuft.

### 3. Familie-in-Lohn
Ehefrau Buchhaltung 20h/Woche (€30-50k), Sohn als Azubi mit hoher Vergütung (€20-30k), Tochter als Werkstudentin (€10-15k). Davon wird ein Teil unter neuem Eigentümer entfallen — wir normalisieren den Excess (Differenz zu marktüblicher Vergütung der Funktion).

### 4. Pkw-Geschäftsführung
Standard: ein Premium-Pkw GF (€60-90k Anschaffung), oft auch Ehefrau-Pkw als Zweitwagen Firmenwagen, ggf. Sohn-Pkw. Pkw-Aufwand pro Fahrzeug €15-25k/Jahr (AfA + Leasing + Versicherung + Kraftstoff). Privatanteil ist offiziell als 1%-Regel in den Lohn gerechnet, aber faktisch >50% privat. Normalisieren: 1 GF-Pkw bleibt, Rest raus.

### 5. Reisekosten + Bewirtung
"Branchen-Treff Davos" 4 Tage = €5-10k. Bewirtungen mit "Geschäftspartnern", die Familie/Freunde sind. Schwer extern zu identifizieren; im Erstgespräch + Folgecall fragen, im Datenraum Stichproben.

### 6. Inhaber-Immobilie an GmbH vermietet
Werkstatt im Privatvermögen des Inhabers (Steuer-Standard-Konstruktion: Sonder-Betriebsvermögen + Betriebsaufspaltung). Miete typisch über Marktmiete, weil das Mietergebnis als Vermietungseinkünfte versteuert wird (ESt) statt als Gewerbe-/KSt + GewSt. Wir vergleichen mit lokalem €/m² für Gewerbeflächen, Differenz zur Marktmiete = Normalisierung.

### 7. Versicherungen mit Privatanteil
GF-Berufsunfähigkeit als Betriebsausgabe, GF-Lebensversicherung als verkappte Pension, Familienangehörige in Berufshaftpflicht. €5-15k typisch.

### 8. Berater-/Beratungshonorare einmalig
Steuerberater-Sondererhebungen, Rechtsanwalt für Privatangelegenheiten via Firma, M&A-Vorberatung des Verkaufsprozesses (kann €30-100k im Vorbereitungsjahr sein). Einmaleffekte raus.

### 9. Familien-Darlehen + Zinsen
Inhaber-Darlehen an die GmbH zu marktüblichen oder über-marktüblichen Zinsen (3-6%). Der Zinsaufwand ist Aufwand in der GmbH, der Zinsertrag ist KESt-Einkommen beim Inhaber. Bei Verkauf wird das Darlehen meist zurückgeführt — wir normalisieren den Zinsaufwand entsprechend.

### 10. Verdeckte Gewinnausschüttungen
Bei Bp-Risiko: privater Pkw-Anteil zu niedrig angesetzt, privat genutzte Werkzeuge, Bewirtung mit Privatcharakter. Wenn vom Finanzamt aufgegriffen: vGA + USt-Korrektur. Wir prüfen, ob Bp-Risiko bekannt.

## Worked Example — Generic Target Alpha

Annahmen Alpha:
- Klein-GmbH, 18 MA, €3,2 Mio. Umsatz, Süddeutschland, Industriekälte-Service-Mix 65/35.
- Inhaber 62, Alleingesellschafter+GF, Ehefrau in Buchhaltung 20h, Sohn Azubi 2. LJ.
- Werkstatt im Privatvermögen, vermietet an GmbH €120k/Jahr (Marktmiete-Bench: €70k).
- Direktzusage GF-Pension, jährliche Zuführung €40k.
- 2 Pkw GF + Ehefrau (S-Klasse, Q5).
- BWA-EBIT 2024 €200k, BWA-EBITDA €340k.

### Schritt 1: Reported HGB-EBITDA
€340k (aus BWA, gerundet auf nächsten 10k).

### Schritt 2: Inhaber-Normalisierungen (alle Stufen)

| Position | Effekt | Begründung |
|---|---|---|
| GGF-Vergütung-Excess | +€60k | Ist-Vergütung €180k, Markt-Vergütung €120k für 18-MA-Betrieb |
| GGF-Pension Zuführung | +€40k | Wird unter neuem Eigentümer nicht weitergeführt |
| Ehefrau-Vergütung-Excess | +€20k | Ist €40k, Markt für 20h Buchhaltung €20k |
| Pkw-Privatanteil + Ehefrau-Pkw | +€25k | Ehefrau-Pkw raus (€18k Aufwand), GF-Pkw Privatanteil-Korrektur (€7k) |
| Inhaber-Immo-Miete-Excess | +€50k | Ist €120k, Markt €70k → €50k Excess |
| Reisekosten / Bewirtung Privatanteil | +€8k | Schätzung aus Konten 6800/6815 |
| Beraterhonorare einmalig (M&A-Vorbereitung) | +€15k | Anwalt + StB-Sonderhonorare |
| Familien-Darlehen Zins (€60k Darl @ 5%) | +€3k | Wird zurückgeführt |

**Σ Inhaber-Normalisierungen: +€221k**

### Schritt 3: Adjusted EBITDA
€340k + €221k = **€561k**

### Schritt 4: Run-Rate-Anpassungen

| Position | Effekt | Begründung |
|---|---|---|
| LTM-Aufschlag (Q1 2026 zeigt +5% YoY) | +€28k | LTM ggü. KJ-2024 |
| Bestätigte Wartungsvertrags-Conv. ab Q3 2026 | +€20k | Aus Vertragsbestand-Liste |
| Auslaufender Wartungsvertrag Top-3-Kunde | -€18k | Kunde 3 zog Wartung intern |

**Σ Run-Rate-Anpassungen: +€30k**

### Schritt 5: Run-Rate EBITDA
€561k + €30k = **€591k**

### Schritt 6: Quality-Adjustments

| Position | Effekt | Begründung |
|---|---|---|
| Capex-Nachholbedarf normalisiert (HGB-AfA €140k vs. Run-Rate-Capex €180k) | -€40k | Anlagespiegel zeigt Fuhrpark Restbuchwert 28% — Erneuerungsbedarf |
| F-Gas-Investition Werkstatt-Anlagen (CO₂-fähig machen) verteilt 5 Jahre | -€20k | €100k Capex / 5 Jahre |
| Konzentrations-Discount (Top-3 = 38% Umsatz) | -€30k | Standard-Heuristik 5% des EBITDA bei Top-3 >35% |
| Inhaber-Risk-Reserve (12-Monats-Übergangs-Kosten) | -€15k | Übergangs-Coaching + verlängerte Geschäftsführerbezüge |
| Mitarbeiter-Bindung (Retention-Bonus-Pool 18 Monate) | -€10k | Standard 1% des Personalaufwands p.a. × 1.5J |

**Σ Quality-Adjustments: -€115k**

### Schritt 7: Quality-adjusted EBITDA
€591k - €115k = **€476k**

### Schritt 8: Bewertung

Multiple-Range bei Industriekälte-Service mit >60% Wartungsanteil, gesunder Mitarbeiter-Struktur, ohne F-Gas-Risiken: 4.0-5.5× Quality-adjusted EBITDA.

| Multiple | Equity Value (cash + debt-free) |
|---|---|
| 4.0× | €1.9 Mio. |
| 4.5× | €2.1 Mio. |
| 5.0× | €2.4 Mio. |
| 5.5× | €2.6 Mio. |

Plus ggf. Earn-out-Komponente bis 6× wenn Pipeline-/Wachstums-Hypothesen sich materialisieren.

**Wichtig:** der Inhaber wird argumentieren auf €561k Adjusted EBITDA × 5× = €2.8 Mio. Wir müssen verteidigen, warum wir auf €476k Quality-adjusted bewerten. Das ist *die* zentrale Verhandlung.

## 30 Dinge, die im Anhang nicht stehen aber stehen sollten

Das ist die Checkliste für unsere Zusatzfragen an den Steuerberater des Targets ("STB-Frage-Katalog"). Bei Klein-GmbHs verlangen wir diese Informationen schriftlich.

### A. Bilanzierungs- und Bewertungsmethoden (1-6)
1. Welche AfA-Methode wird pro Anlagengruppe genutzt (linear, degressiv, leistungsbezogen)? Welche Nutzungsdauern werden angesetzt?
2. Welche Vorratsbewertungsmethode (FIFO, LIFO, Durchschnitt)?
3. Wie werden halbfertige Arbeiten bewertet (Selbstkosten oder anteiliger Erlös)?
4. Pauschalwertberichtigung Forderungen — Quote und Begründung?
5. Bewertung Pensionsrückstellungen — Verfahren (Teilwert, BilMoG-Niveau), Rechnungszins, biometrische Annahmen?
6. Garantierückstellungen — Berechnungsmethode (Erfahrungswerte vs. pauschal)?

### B. Inhaber-/Familien-bezogene Sachverhalte (7-13)
7. Höhe und Zusammensetzung der GGF-Gesamtvergütung (Gehalt, Tantieme, Pkw, Pension)?
8. Bestehende Pensionszusagen (an wen, Volumen, Rückstellung)?
9. Familienangehörige in Anstellung (Funktion, Stundenvolumen, Vergütung)?
10. Geschäfte mit nahestehenden Personen (Mietverträge, Darlehen, Aufträge an Familien-GmbHs)?
11. Inhaber-Darlehen (Höhe, Zinssatz, Laufzeit, Sicherheiten)?
12. Privat genutzte Vermögensgegenstände im Betriebsvermögen?
13. Besteht eine Betriebsaufspaltung (Besitz-GmbH/-Privatperson + Betriebs-GmbH)?

### C. Working-Capital und Liquidität (14-19)
14. DSO über 24 Monate?
15. DPO über 24 Monate?
16. Saisonale Liquiditätsschwankung (Bank-Saldo Min/Max)?
17. Bankenfinanzierung (Linien, Auslastung, Sicherheiten, Inhaberbürgschaften)?
18. Erhaltene Anzahlungen (Pattern, Kunden-Konzentration)?
19. Skonto-Politik (Annahme/Ablehnung Lieferanten-Skonto)?

### D. Steuern (20-23)
20. Letzte Betriebsprüfung — Zeitraum, Ergebnis, offene Punkte?
21. Steuerbescheide unter Vorbehalt der Nachprüfung — wie lange offen?
22. Verlustvorträge (KSt, GewSt, Mantelkauf-Risiko)?
23. Latente Steuern (auch wenn Wahlrecht nicht ausgewiesen — interne Berechnung)?

### E. Personal (24-26)
24. Mitarbeiter-Listen mit Sachkundenachweisen Cat I-IV (Anzahl, Status)?
25. Pensions- oder Lebensarbeitszeit-Konten für MA?
26. Drohende oder laufende Arbeitsgerichts-Verfahren?

### F. Verträge und Compliance (27-30)
27. Wesentliche Kunden-/Lieferantenverträge mit Change-of-Control-Klausel?
28. F-Gas-Compliance-Stand (Anlagenliste, Lecksuche-Protokolle, Kältemittel-Inventar)?
29. Versicherungspolicen-Liste (Berufshaftpflicht, Maschinenversicherung, D&O)?
30. Bekannte Umweltrisiken am Werkstattgrundstück (frühere Nutzung, Lagerung, Lecks)?

## Sicherheitsmaßnahmen für die SPA-Verhandlung

Aus den Quirks ergeben sich SPA-Klauseln, die wir nicht missen wollen:
- **Garantien zu HGB-Standardbewertungen** (Vollständigkeit, Vorratsbewertungs-Methode unverändert).
- **Spezielle Gewährleistung Pensionsrückstellungen** (Bewertung nach BilMoG-Niveau, kein Bewertungs-Wahlrecht-Wechsel pre-Closing).
- **Steuer-Garantie + Freistellung** für Bp-Risiko bis Festsetzungsverjährung.
- **Umwelt-Garantie + Freistellung** mit Cap und Schwellenwert (basierend auf Phase-1-ESA).
- **Working-Capital-Peg** zum Stichtag mit Definitions-Annex (welche Positionen einbezogen).
- **Locked-Box-Reference-Date** mit Untersagungs-Klausel für außergewöhnliche Ausschüttungen.
- **Earn-out-Sicherung:** bilanzielle Behandlung der Adjustierungen ist im SPA festgeschrieben, sonst lässt der Verkäufer das EBIT durch Bilanztricks "explodieren".

## Related

- [Stage 3 — Full Data Room](./03-stage-3-data-room.md) — wo die Quirks operationell relevant werden
- [Stage 2 — IOI/LOI](./02-stage-2-ioi-loi-first-pl.md) — erste Inhaber-Normalisierungen
- [Sector Pack](./05-sector-pack-hvac-r.md) — sektor-spezifische Bewertungs-Themen
- [Templates — STB-Frage-Katalog, Self-IC-Memo](./07-templates.md)
- [Overview](./overview.md)
