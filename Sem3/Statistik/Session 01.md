# Session 01

<!-- @import "[TOC]" {cmd="toc" depthFrom=2 depthTo=6 orderedList=false} -->
<!-- code_chunk_output -->

* [Statistik](#statistik)
	* [Deskriptive Statistik](#deskriptive-statistik)
	* [Induktive Statistik](#induktive-statistik)
	* [Vorgehensweisen bei statistischen Untersuchungen](#vorgehensweisen-bei-statistischen-untersuchungen)
	* [Grundbegriffe](#grundbegriffe)
* [Lageparameter](#lageparameter)
	* [Wichtigste Lageparameter](#wichtigste-lageparameter)
	* [Arithmetisches Mittel](#arithmetisches-mittel)
	* [Beispiel: Umsatz eines Unternehmens (Arithmetisches Mittel)](#beispiel-umsatz-eines-unternehmens-arithmetisches-mittel)
	* [Beispiel: Monatsverdienst im Unternehmen (Zentralwert)](#beispiel-monatsverdienst-im-unternehmen-zentralwert)
	* [Modus](#modus)
	* [Fechnersche Lageregel](#fechnersche-lageregel)

<!-- /code_chunk_output -->

## Statistik
* Erhebung, Aufbereitung, Analyse von Daten

### Deskriptive Statistik
* Datenerhebung aus der Realität
* Beispiel: Daten aus dem Kurs werden gesammelt
  * Z. B. Durchschnittsgehalt, Alter etc.
* Ein oder mehrere Merkmale werden betrachtet
  * Zusammenhänge werden gesucht

### Induktive Statistik
* Datenerhebung aus Stichproben

### Vorgehensweisen bei statistischen Untersuchungen
1. Planung/Problemformulierung
  * Was will ich eigentlich untersuchen (konkrete Fragestellung)
2. Datenerhebung
  * Primärstatistik oder Sekundärstatistik (bereits vorhandene Daten)
3. Datenaufbereitung
  * Verdichtung des Datenmaterials (Tabellen und Schaubilder)
4. Datenanalyse
  * Ermittlung von Maßzahlen und Kennziffern
5. Interpretation
  * Was bedeuten meine Ergebnisse vor dem Hintergrund der festgelegten Fragestellung?

### Grundbegriffe
* Statistische Einheit/Merkmalsträger
  * Objekt, dessen Eigenschaften festgestellt werden sollen
* Statistische Masse/Grundgesamtheit
  * Gesamtheit der Merkmalsträger
* Stichprobe/Teilgesamtheit
  * Teil der Grundgesamtheit
  * Aus erhebungstechnischen Gründen oft nur Teilbefragungen
* Merkmal
  * Bestimmte messbare Eigenschaft eines Merkmalsträgers
* Qualitative Merkmale
  * Kategoriale Merkmalsausprügung
* Quantitative Merkmale
  * Sinnvolle Zuordnung von reellen Zahlen möglich
  * **Diskret** (nur bestimmte Werte)
  * **Stetig** (beliebige Werte zumindest in einem bestimmten Intervall)
* Nominalskala
  * Unterschiede feststellbar, aber keine Rangordnung
* Ordinalskala
  * Verschiedenartigkeit und Rangordnung feststellbar
  * Abstände nicht vernünftig quantifizierbar
* Kardinalskala/metrische Skala
  * Zusätzlich noch sinnvoller Messung/Vergleich der Abstände
  * Unterscheidung **Intervallskala** (willkürlicher Nullpunkt) und **Verhältnisskala** (absoluter Nullpunkt)

## Lageparameter
* Beobachtungswerte einer statistischen Masse sollen über **Maßzahlen** beschrieben werden
* Unterscheidung zwischen Lageparametern, Streuuungsparametern, Schiefe- und Wölbungsmaßen sowie Konzentrationsmaßen

### Wichtigste Lageparameter
* Arithmetisches Mittel (Mittelwert)
* Geometrisches Mittel (für Wachstumsraten)
* Zentralwert (Median)
* Modus (häufigster Wert)

### Arithmetisches Mittel
* Nur für kardinal skalierte Merkmale zu berechnen
* Unterschiedliche Formeln bei einfachen Zahlenreihen oder gruppiertem Datenmaterial

**Einfaches arithmetisches Mittel**:
$$
\overline{X} = \frac{1}{N} * \sum{x_i}
$$

**Gewogenes arithmetisches Mittel**:
$$\overline{X} = \frac{1}{N} * \sum{x_i} * f_i = \sum{x_i} * p_i$$

### Beispiel: Umsatz eines Unternehmens (Arithmetisches Mittel)
|       |$x_i$    |Umsatzwachstum in %|$x_i$|
|-------|---------|-------------------|-----|
|2013   |1 Mrd. € |-                  |-    |
|2014   |2 Mrd. € |100 %              |2    |
|2015   |2 Mrd. € |0 %                |1    |
|2016   |3 Mrd. € |50 %               |1,5  |

$$G = \sqrt[3]{2 * 1 * 1.5} = \sqrt[3]{3} = 1,442$$

=> Durchschnittliches Wachstum: $1,442$

### Beispiel: Monatsverdienst im Unternehmen (Zentralwert)
* Gehälter in einem Unternehmen
  * 2 000
  * 2 000
  * 2 000
  * 2 500
  * 2 500
  * 3 000
  * 3 000
  * 3 000
  * 970 000

Arithmetisches Mittel:
$$\overline{X} = \frac{1}{9} * 990.000 = 110.000$$

Zentralwert: ("mittelster" Wert)
$$Z = 2500$$

### Modus
* Der Modus ist derjenige Wert, der am häufigsten auftritt
* Bei Klassen mit quantitativ-stetigen Merkmalen erfolgt eine Feinberechnung des Modus
$$M = X^l_M + C_M * \frac{\Delta_1}{\Delta_1 + \Delta_2}$$
$$\Delta_1 = p_M - p_{M - 1}; \Delta_2 = p_M - p_{M + 1}$$

### Fechnersche Lageregel
* $\overline{X} = Z = M$: Symmetrische Verteilung
* $\overline{X} > Z > M$: Linkssteile = rechtsschiefe Verteilung
* $\overline{X} < Z < M$: Rechtssteile = linksschiefe Verteilung