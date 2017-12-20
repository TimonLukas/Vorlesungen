# Session 04

<!-- @import "[TOC]" {cmd="toc" depthFrom=2 depthTo=6 orderedList=false} -->
<!-- code_chunk_output -->

* [Kostenverläufe und Ermittlung von Kostenfunktionen](#kostenverläufe-und-ermittlung-von-kostenfunktionen)
	* [Kennzeichnung bedeutender Kostenverläufe](#kennzeichnung-bedeutender-kostenverläufe)
	* [Kostenfunktion, Kosteneinflussgrößen und Fristigkeit](#kostenfunktion-kosteneinflussgrößen-und-fristigkeit)
	* [Beschäftigungsmaßstäbe bei "Sewing United"](#beschäftigungsmaßstäbe-bei-sewing-united)
	* [Homogene vs. heterogene Kostenverursachung](#homogene-vs-heterogene-kostenverursachung)
	* [Vereinfachung des Kostenverlaufs für Kostenfunktion](#vereinfachung-des-kostenverlaufs-für-kostenfunktion)
	* [Beispiel Aggregation und Linearisierung bei Sewing United](#beispiel-aggregation-und-linearisierung-bei-sewing-united)
	* [Statistische Methoden zur Bestimmung von Kostenfunktionen](#statistische-methoden-zur-bestimmung-von-kostenfunktionen)
		* [Zwei-Punkt-Methode (Hoch-Tief-Methode)](#zwei-punkt-methode-hoch-tief-methode)
	* [Verfahren zur Ermittlung von Kostenfunktionen](#verfahren-zur-ermittlung-von-kostenfunktionen)

<!-- /code_chunk_output -->

## Kostenverläufe und Ermittlung von Kostenfunktionen
### Kennzeichnung bedeutender Kostenverläufe
* Mögliche Kostenveränderung bei Variation der Beschäftigung
  * Proportional: Kosten steigen im gleichen Verhältnis wie die Beschäftigung
    * Z. B. Betriebsstoffkosten in der Montage
  * Überproportional: Kosten steigen stärker als die Beschäftigung
    * Z. B. Überstundenkosten
  * Unterproportional: Kosten steigen weniger stark als die Beschäftigung
    * Z. B. Wartungskosten bei Lerneffekten
* Ausgewählte Kostenverläufe
  * Semi-proportionale Kosten: Fixe und variable Kosten
    * Beispiele
      * Gesamtgehalt mit fixem Sockel und leistungsabhängigem Bonus
      * Telefonkosten mit zweigeteiltem Tarif
  * Kosten mit Ober- bzw. Untergrenze
    * Beispiel: Fertigungslöhne
  * Sprungfixe Kosten
    * Beispiele
      * Löhne von Teilzeitkräften
      * Gehälter von Vorarbeitern
  * S-förmig verlaufende Kosten
    * Beispiel: Hilfs- und Betriebsstoffe
    * Mittlere Auslastung: Unterproportional (Skaleneffekte)
    * Niedirge und hohe Auslastung: Überproportional
  * Skaleneffekt: Stückkosten sinken mit Menge
    * Beispiel: Digitale Güter
  * Sticky Costs (rigide/beharrliche Kosten)
    * Kosten, die schneller steigen, als sie fallen

### Kostenfunktion, Kosteneinflussgrößen und Fristigkeit
Die Kostenfunktion $f$ beschreibt den Ursache-Wirkungs-Zusammenhang zwischen der Einflussgröße $x$ (als unabhängige/erklärene/exogene Variable) und den Kosten $K$ (als abhängige/erklärte/endogene Variable):
$$
K = f(x)
$$

Mögliche Ausgestaltungen der erklärenden Variable
|       |Inputorientiert          |Outputorientiert       |
|-------|-------------------------|-----------------------|
|Menge  |Mengen der Einsatzgüter<br />• Fertigungsstunden<br />•Maschinenstunden<br />• Einsatzmengen|Mengen der Ausbringungsgüter<br />• Anzahl gefertigter Anlagen|
|Wert   |Wert der Einsatzgüter<br />• Fertigungslöhne<br />• Materialeinzelkosten|Werte der Ausbringungsgüter<br />• Herstellkosten gefertigter Anlagen<br />• Umsatzerlöse|

### Beschäftigungsmaßstäbe bei "Sewing United"
|Endogene                     |Mögliche erklärende Variable       |
|-----------------------------|-----------------------------------|
|Kosten Wareneingangskontrolle|Anzahl angelieferter Sendungen     |
|Kosten Lagerhaltung          |Materialeinzelkosten               |
|Lohnkosten Akkord-Arbeiter   |Anzahl der Akkordstunden           |
|Reisekosten Monteure         |Entfernung zu Montagestandorten    |
|Messekosten                  |Anzahl besuchter Messen            |

### Homogene vs. heterogene Kostenverursachung
* Homogen, also **eine** einzelne Exogene, z. B.:
  * Kosten für Hilfs- und Betriebsstoffe = $f(\text{Maschinenzeit})$
* Heterogen, also **mehrere** Exogene, z. B.:
  * Kosten für Hilfs- und Betriebsstoffe = $f(\text{Rüstzeit, Maschinenzeit, ...})$

### Vereinfachung des Kostenverlaufs für Kostenfunktion
* **Beschränkung auf relevanten Bereich**
  * Kostenprognose beschränken sich auf typische Beschäftigungsgrade
  * **Aggregation**: Zusammenfassen der Kosten mehrerer Kostenstellen mit typischerweise unterschiedlich verlaufenden Kostenfunktionen/heterogenen Kostentreibern
  * **Linearisierung**: Vereinfachende Annahme zu Kostenfunktion
  * **Homogenisierung**: Reduzierung der Anzahl der Kosteneinflussgrößen

### Beispiel Aggregation und Linearisierung bei Sewing United
* Kostenstelle "Multifunktionsfräsmaschine"
$$
K = f(\text{monatliche Maschinenstunden})
$$

* Kostenentwicklung bzgl. Maschinenstunden:
  * Abschreibungen (im relevanten Bereich): Weitgehend unabhängig
  * Energie- und Ausschusskosten: Unterproportional
  * Instandhaltungskosten: Steigen, aber vertraglich auf maximal 1.200€/Monat begrenzt
  * Kosten für Hilfs- und Betriebsstoffe: Konstanter Bereich bei niedriger Auslastung, dann überproportionaler Anstieg

### Statistische Methoden zur Bestimmung von Kostenfunktionen
1. Kostenklassifikation
  * Auf Erfahrungswerte basierende Unterteilung in fixe vs. proportionale Kosten
2. Hoch-Tief-Methode
  * Bezug auf zwei Punkte
3. Regression
  * Abhängigkeit einfach oder multipel

#### Zwei-Punkt-Methode (Hoch-Tief-Methode)
Nutzung von allein zwei Beobachtungspunkten zur Prognose der Kosten
$$
\text{Steigung der Kostenfunktion} = \frac{\text{Kostendifferenz bei höchster und niedrigster Beschäftigung}}{\text{Differenz von höchster und niedrigster Beschäftigung}}
$$

Bestimmung des Achensabschnitts der Kostenfunktion:
$$
a = y - bx
$$

### Verfahren zur Ermittlung von Kostenfunktionen