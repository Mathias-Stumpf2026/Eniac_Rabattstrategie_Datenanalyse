# Eniac Rabattstrategie — Data-Analytics-Projekt

![Eniac Rabattstrategie](2.Images/eniac_hero_banner.png)

Interne Datenanalyse für **Eniac** (E-Commerce, Apple-Produkte & High-End-Zubehör) zur zentralen Frage der Geschäftsleitung: **Sind Rabatte langfristig vorteilhaft — oder schaden sie Umsatz und Positionierung?**

📊 [Vollständige Präsentation](5.Präsentation/) · 📄 [Pflichtenheft](4.Reports/) · 📓 [Analyse-Notebook](3.Notebook/Eniac_Rabattstrategie_Datenanalyse.ipynb)

Dieses Projekt entstand im Rahmen einer Gruppenarbeit; dieses Repository dokumentiert meine individuelle Analyse und Ausarbeitung.

## Kernergebnisse auf einen Blick

![Kernergebnisse](2.Images/key_findings_panel.png)

## Daten & Methode

- **Quelle:** vier interne Eniac-Datensätze (`orders`, `orderlines`, `products`, `brands`), unbereinigt
- **Bereinigung:** Duplikate entfernt, Preis-/Formatfehler korrigiert, Ausreißer per IQR-Regel entfernt — 226.904 → **45.418 Bestellungen** als finale Analysebasis (vollständiger Bereinigungs-Funnel im Notebook, Abschnitt 1–2 dokumentiert)
- **Tools:** Python, pandas, seaborn/matplotlib, Google Colab
- **Zeitraum:** Jan 2017 – Mär 2018 (2018 unvollständig, nur bis 14.03.)

## Befunde & Handlungsempfehlungen

### 1. Rabatte treiben keine Menge

![Bestellungen und Menge je Rabattstufe](2.Images/rabatt_bucket_analyse.png)

Sowohl Bestellanzahl als auch verkaufte Menge **fallen** mit steigender Rabattstufe; die Korrelation zwischen Rabatt-% und Menge liegt bei **0,01** — praktisch kein Zusammenhang. Die These "höherer Rabatt treibt mehr Absatz" ist mit diesen Daten nicht belegbar.

**Empfehlung:** Rabatttiefe nicht als Absatz-Hebel behandeln. Falls Rabatte Wachstum erzeugen sollen, muss der Wirkmechanismus neu geprüft werden — tiefere Rabatte allein funktionieren nicht.

### 2. Kategorie entscheidet: Hardware vs. Zubehör vs. Services

![Rabattanalyse nach Kategorie](2.Images/rabatt_nach_kategorie.png)

Kern-Hardware (MacBook, iMac, Mobile Phones) wird eng und moderat rabattiert (Median 5–15 %) — die befürchtete Markenverwässerung zeigt sich in den eigenen Daten nicht. Services und Zubehör werden am breitesten und tiefsten rabattiert.

**Empfehlung:** Die Premium-Hardware-Linie braucht auf Basis dieser Daten keinen zusätzlichen Rabattschutz. Falls die Rabattpolitik gestrafft werden soll, zuerst bei Services ansetzen — dort ist das Rabattmuster am wenigsten kontrolliert.

### 3. Umsatz und Bestellanzahl laufen synchron, nicht gegenläufig

![Umsatz und Bestellanzahl im Zeitverlauf](2.Images/umsatz_bestellungen_monatsverlauf.png)

Die Vorstandsaussage "Bestellungen steigen, Umsatz sinkt" bestätigt sich auf Monatsebene nicht: Beide Kurven verlaufen fast identisch, inklusive derselben Spitze im November 2017. Ein reiner Kurvenvergleich sagt allerdings nichts über den Ø Bestellwert aus — die Frage ist damit nicht abschließend geklärt.

**Empfehlung:** Vor der Schlussfolgerung "Umsatz sinkt" den Ø Bestellwert und ein vollständiges Jahr (2018 ist hier unvollständig) gegenprüfen.

## Was diese Analyse nicht beantworten kann

Es lagen keine Einkaufspreise vor, daher ist der **Effekt auf die Marge nicht berechenbar** — das ist die größte offene Frage für eine endgültige Entscheidung. Ebenfalls fehlend: Wettbewerbsdaten und Kunden-IDs (keine Aussage zu Wiederkauf/Kundenbindung möglich).

**Empfohlener nächster Schritt:** Data-Team benötigt Zugriff auf Einkaufspreise, um den tatsächlichen ROI je Rabattstufe zu berechnen — Details und Maßnahmen je Abteilung siehe Pflichtenheft, Kapitel 7.

## Repository-Struktur

`README.md` liegt bewusst im Repository-Root (nicht in einem Unterordner) — nur so zeigt GitHub es automatisch als Startseite an.

```
README.md       # diese Datei (Root-Ebene)
1.Data/         # Rohdaten bzw. Download-Link (bei > 25 MB ausgelagert)
2.Images/       # exportierte Diagramme für README & Pflichtenheft
3.Notebook/     # Eniac_Rabattstrategie_Datenanalyse.ipynb — vollständige Analyse
4.Reports/      # Pflichtenheft, Projektplan
5.Präsentation/ # PowerPoint bzw. PDF-Export
6.Projekt/      # Gesamtübersicht
```

## Kontakt

Mathias — Umstieg von HR in Data Science & AI, WBS Training AG

---

## English Summary

This project analyzes whether discounts are a sustainable growth driver for **Eniac** (e-commerce, Apple products & accessories) or whether they erode revenue and premium positioning — the central question raised by the executive board.

**Key findings**, based on 45,418 cleaned orders (Jan 2017–Mar 2018):
- Discount depth does **not** drive sales volume (correlation ≈ 0.01) — discounts alone are not an effective growth lever.
- Core hardware (MacBook, iMac, Mobile Phones) is discounted narrowly (5–15 % median) — no sign of brand devaluation in the company's own data. Services and accessories carry the widest, deepest discounts.
- Monthly revenue and order count move together, not apart — the board's specific "orders up, revenue down" claim isn't confirmed at this level of detail.
- **Open question:** no procurement cost data was available, so the actual margin/profitability impact could not be calculated — this remains the key gap for a final decision.

Full analysis, charts, and department-level recommendations: see the German sections above, the [notebook](3.Notebook/Eniac_Rabattstrategie_Datenanalyse.ipynb), and the [Pflichtenheft](4.Reports/).
