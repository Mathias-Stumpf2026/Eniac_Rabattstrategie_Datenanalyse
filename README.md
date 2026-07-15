# Eniac Rabattstrategie – Data-Analytics-Projekt

![Eniac Rabattstrategie](2.Images/eniac_hero_banner.png)

Interne Datenanalyse für **Eniac** (E-Commerce, Apple-Produkte & High-End-Zubehör) zur zentralen Frage der Geschäftsleitung: **Sind Rabatte langfristig vorteilhaft — oder schaden sie Umsatz und Positionierung?**

📊 [Vollständige Präsentation](5.Präsentation/) · 📄 [Pflichtenheft](4.Reports/) · 📓 [Analyse-Notebook](3.Notebook/Eniac_Rabattstrategie_Datenanalyse.ipynb)

Dieses Projekt entstand im Rahmen einer Gruppenarbeit; Dieses Repository dokumentiert meine individuelle Analyse und Ausarbeitung.

## Kernergebnisse auf einen Blick

![Kernergebnisse](2.Images/key_findings_panel.png)

## Daten & Methode

- **Quelle:** vier interne Eniac-Datensätze (`orders`, `orderlines`, `products`, `brands`), unbeeinigt
- **Bereinigung:** Duplikate entfernt, Preis-/Formatfehler korrigiert, Ausreißer per IQR-Regel entfernt — 226.904 → **45.418 Bestellungen** als finale Analysebasis (vollständiger Bereinigungs-Funnel im Notebook, Abschnitt 1–2 dokumentiert)
- **Tools:** Python, pandas, seaborn/matplotlib, Google Colab
- **Zeitraum:** Jan 2017 – März 2018 (2018 unvollständig, nur bis 14.03.)

## Befunde & Handlungsempfehlungen

### 1. Rabatte treiben keine Menge

![Bestellungen und Menge je Rabattstufe](2.Images/rabatt_bucket_analyse.png)

Sowohl Bestellanzahl als auch verkaufte Menge **gefallen** mit steigender Rabattstufe; Die Korrelation zwischen Rabatt-% und Menge liegt bei **0,01** – praktisch kein Zusammenhang. Die These „höherer Rabatt treibt mehr Absatz“ ist mit diesen Daten nicht belegbar.

**Empfehlung:** Rabatttiefe nicht als Absatz-Hebel behandeln. Falls Rabatte Wachstum erzeugen sollen, muss der Wirkmechanismus neu geprüft werden – tiefere Rabatte allein funktionieren nicht.

### 2. Kategorie entscheidet: Hardware vs. Zubehör vs. Services

![Rabattanalyse nach Kategorie](2.Images/rabatt_nach_kategorie.png)

Kern-Hardware (MacBook, iMac, Mobiltelefone) wird eng und moderat rabattiert (Median 5–15 %) – die befürchtete Markenverwässerung zeigt sich in den eigenen Daten nicht. Services und Zubehör werden am breitesten und tiefsten rabattiert.

**Empfehlung:** Die Premium-Hardware-Linie benötigt auf Basis dieser Daten keinen zusätzlichen Rabattschutz. Falls die Rabattpolitik gestrafft werden soll, zuerst bei Services ansetzen – dort ist das Rabattmuster am wenigsten kontrolliert.

### 3. Umsatz und Bestellanzahl laufen synchron, nicht gegenläufig

![Umsatz und Bestellanzahl im Zeitverlauf](2.Images/umsatz_bestellungen_monatsverlauf.png)

Die Vorstandsaussage „Bestellungen steigen, Umsatz sinkt“ bestätigt sich auf Monatsebene nicht: Beide Kurven verlaufen fast identisch, inklusive gleicher Spitze im November 2017. Ein reiner Kurvenvergleich sagt allerdings nichts über den Ø Bestellwert aus – die Frage ist damit nicht abschließend geklärt.

**Empfehlung:** Vor der Schlussfolgerung „Umsatz sinkt“ den Ø Bestellwert und ein vollständiges Jahr (2018 ist hier unvollständig) gegenprüfen.

## Was diese Analyse nicht beantworten kann

Es liegen keine Einkaufspreise vor, daher ist der **Effekt auf die Marge nicht berechenbar** — das ist die größte offene Frage für eine endgültige Entscheidung. Ebenfalls fehlen: Wettbewerbsdaten und Kunden-IDs (keine Aussage zum Wiederkauf/Kundenbindung möglich).

**Empfohlener nächster Schritt:** Data-Team benötigt Zugriff auf Einkaufspreise, um den tatsächlichen ROI je Rabattstufe zu berechnen – Details und Maßnahmen je Abteilung siehe Pflichtenheft, Kapitel 7.

## Repository-Struktur

`README.md` liegt bewusst im Repository-Root (nicht in einem Unterordner) — nur so zeigt GitHub es automatisch als Startseite an.

```
README.md # diese Datei (Root-Ebene)
1.Daten/ # Rohdaten bzw. Download-Link (bei > 25 MB ausgelagert)
2.Bilder/ # exportierte Diagramme für README & Pflichtenheft
3.Notebook/ # Eniac_Rabattstrategie_Datenanalyse.ipynb – vollständige Analyse
4.Berichte/ # Pflichtenheft, Projektplan
5.Präsentation/ # PowerPoint bzw. PDF-Export
6. Projekt/ # Gesamtübersicht
```

## Kontakt

Mathias — Umstieg von HR in Data Science & AI, WBS Training AG

---

## Englische Zusammenfassung

Dieses Projekt analysiert, ob Rabatte ein nachhaltiger Wachstumstreiber für **Eniac** (E-Commerce, Apple-Produkte & Zubehör) sind oder ob sie den Umsatz und die Premiumpositionierung untergraben – die zentrale Frage, die der Vorstand aufgeworfen hat.

**Wichtigste Ergebnisse**, basierend auf 45.418 Reinigungsaufträgen (Jan. 2017–März 2018):
- Die Höhe der Rabatte beeinflusst das Verkaufsvolumen **nicht** (Korrelation ≈ 0,01) — Rabatte allein sind kein effektiver Wachstumshebel.
Die Kernhardware (MacBook, iMac, Mobiltelefone) ist nur geringfügig reduziert (Median 5–15 %) – laut Unternehmensangaben gibt es keine Anzeichen für eine Markenabwertung. Dienstleistungen und Zubehör werden am stärksten und höchsten reduziert angeboten.
- Der monatliche Umsatz und die Anzahl der Bestellungen entwickeln sich parallel, nicht unabhängig voneinander – die konkrete Behauptung des Vorstands, dass die Bestellungen steigen, der Umsatz aber sinkt, lässt sich auf dieser Detailebene nicht bestätigen.
- **Offene Frage:** Es lagen keine Daten zu den Beschaffungskosten vor, sodass die tatsächlichen Auswirkungen auf die Marge/Rentabilität nicht berechnet werden konnten – dies bleibt die entscheidende Lücke für eine endgültige Entscheidung.

Vollständige Analysen, Diagramme und Empfehlungen auf Abteilungsebene: siehe die oben stehenden deutschen Abschnitte, das [Notebook](3.Notebook/Eniac_Rabattstrategie_Datenanalyse.ipynb) und das [Pflichtenheft](4.Reports/).
