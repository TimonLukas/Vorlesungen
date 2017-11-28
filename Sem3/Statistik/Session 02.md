# Session 02

<!-- @import "[TOC]" {cmd="toc" depthFrom=2 depthTo=6 orderedList=false} -->
<!-- code_chunk_output -->

* [Fortführung Session 01](#fortführung-session-01)
	* [Streuungsparameter](#streuungsparameter)
* [Deskriptive Statistik bei mehrdimensionalem Datenmaterial](#deskriptive-statistik-bei-mehrdimensionalem-datenmaterial)
	* [Darstellungsweise und Grundbegriffe](#darstellungsweise-und-grundbegriffe)
	* [Korrelations- und Regressionsanalyse](#korrelations-und-regressionsanalyse)
		* [Beispiel](#beispiel)

<!-- /code_chunk_output -->

## Fortführung Session 01

### Streuungsparameter
* Während die Lageparameter in erster Linie eine Aussage über das Verteilungszentrum treffen, stellen Streuungsparameter Aussagen über Abweichungen bereit
* Die **wichtigsten Streuungsparameter** sind
  * Spannweite
  * Standardabweichung (= Wurzel aus der Varianz)
  * Variationskoeffizient (= relative Streuung)
* Unwichtig sind
  * Quartilsabstand
  * Mittlere absolute Abweichung
* **Spannweite** bei ordinal oder kardinal skalierten Merkmalen: $R = x_{i(max)} - x_{i(min)}$
* Beim Vorliegen von Klassen verwendet man die obere Klassengrenze der obersten Klasse und die unterste Klassengrenze der untersten Klasse
* Für kardinal skalierte Merkmale gibt es eine Reihe von weiteren Streuungsparametern
* Weniger gebräuchlich, aber sehr gut interpretierbar ist die **mittlere absolute Abweichung**
  * $MAD = \frac{1}{N} * \sum^N_{i = 1} \vert x_i - \overline{X} \vert$
* Von großer Bedeutung sind dagegen die **Varianz** und die aus ihr berechnete **Standardabweichung**
* Varianz für ungruppierte Daten
$$
S^2 = \frac{1}{N} * \sum^N_{i=1}(x_i - \overline{X})^2 = \frac{\sum x^2_i}{N} - \overline{X}^2
$$
* Varianz für gruppierte Daten
$$
S^2 = \frac{1}{N} * \sum^k_{i=1} f_i * (x^*_i - \overline{X})^2 = \frac{1}{N} * \sum^k_{i=1} f_ix_i^{*2} - \overline{X}^2
$$
* Standardabweichung
$$
S = \sqrt{S^2}
$$
* Betrachtet man zwei Verteilungen mit der gleichen Standardabweichung, so ist diese unterschiedlich zu beurteilen, je nachdem in welcher Größenordnung sich das Zahlenmaterial bewegt
  * Dies berücksichtigt der **Variationskoeffizient** (= **relative Steuerung**):
$$
V = \frac{S}{\overline{X}}
$$

## Deskriptive Statistik bei mehrdimensionalem Datenmaterial
### Darstellungsweise und Grundbegriffe
Liegen **zwei Merkmale X und Y** vor, so erfolgt die Darstellung in Kontingenztabellen mit **gemeinsamen absoluten $f_{ij}$ oder gemeinsamen relativen Häufigkeiten $p_{ij}$**:
$$
p_{ij} = \frac{f_{ij}}{N}
$$
Außerdem können folgende Größen berechnet werden:
* **Randverteilungen**:
$$
p_{i.} = \sum^c_{j = 1} p_{ij} = \frac{f_{i.}}{N} \text{ für i = 1, ..., r} \\
p_{.j} = \sum^r_{i = 1} p_{ij} = \frac{f_{.j}}{N} \text{ für j = 1, ..., c}
$$
* **Bedingte Häufigkeitsverteilungen**:
$$
P(X_i / Y_j) = \frac{f_{ij}}{f_{.j}} = \frac{p_{ij}}{p_{.j}} \\
P(Y_j / X_i) = \frac{f_{ij}}{f_{i.}} = \frac{p_{ij}}{p_{i.}}
$$
* **Statistische Unabhängigkeit der beiden Merkmale liegt vor, wenn gilt**:
$$
p_{ij} = p_{i.} * p_{.j} \text{ für alle i, j}
$$

### Korrelations- und Regressionsanalyse
* Bei vielen Fragestellungen interessiert die **Stärke des Zusammenhangs** zwischen den untersuchten Merkmalen
* Bevor man anfängt zu rechnen, sollte man sich hierbei überlegen, ob die (Wirtschafts-)Theorie einen Zusammenhang zwischen den untersuchten Merkmalen nahe legt
* Je nach Skalierung der Merkmale können unterschiedliche **Korrelationskoeffizienten** berechnet werden
* Dies ist bei nominal skalierten Merkmalen vor allem der **Phi-Koeffizient** und bei ordinal skalierten Merkmalen vor allem der **Rangkorrelationskoeffizient** nach Spearman
* Die größte Bedeutung in der Praxis haben kardinal skalierte Merkmale
  * Hier berechnet man den **empirischen Korrelationskoeffizient** nach Bravais-Pearson

**Empirischer Korrelationskoeffizient für kardinal skalierte Merkmale**:
$$
\rho = \frac{\sum^N_{i=1} (x_i - \overline{X}) * (y_i - \overline{Y})}{\sqrt{\sum^N_{i = 1} (x_i - \overline{X})^2 * \sum^N_{i = 1} (y_i - \overline{Y})^2}}
$$
* Während die Korrelationsanalyse nur die Stärke des Zusammenhangs untersucht, berücksichtigt die **Regressionsanalyse** zusätzlich die **funktionale Abhängigkeit** zwischen zwei (oder mehr) Größen
* So hat bspw. die Sonnenscheindauer einen Einfluss auf den Ernteertraag, nicht aber umgekehrt^

#### Beispiel
10 Lebensmittelläden, X: Verkaufsfläche (in 1000 qm), y: Jahresumsatz (in Mio €)

|$i$|$x_i$|$y_i$|$x_i - \overline{X}$|$y_i - \overline{Y}$|$(x_i - \overline{X})^2$|$(y_i - \overline{Y})^2$|$(x_i - \overline{X}) * (y_i - \overline{Y})$|
|-|-|-|-|-|-|-|-|
|1      |0,5  |3,0  |-0,54|-2,64|0,2916 |6,9696 | 1,4256|
|2      |0,9  |5,1  |-0,14|-0,54|0,0196 |0,2916 | 0,0756|
|3      |1,1  |5,5  | 0,06|-0,14|0,0036 |0,0196 |-0,0084|
|4      |1,5  |7,3  |.    |.    |.      |.      |.      |
|5      |1,2  |6,2  |.    |.    |.      |.      |.      |
|6      |1,4  |7,0  |.    |.    |.      |.      |.      |
|7      |1,6  |8,1  |.    |.    |.      |.      |.      |
|8      |0,8  |4,9  |.    |.    |.      |.      |.      |
|9      |1,0  |6,1  |.    |.    |.      |.      |.      |
|10     |0,4  |3,2  |.    |.    |.      |.      |.      |
|$\sum$ |10,4 |56,4 |0    |0    |1,4640 |24,9640|5,934  |

$$
\rho = \frac{5,934}{\sqrt{1,464 * 24,964}} = 0,982
$$

Der empirische Korrelationskoeffizient ist beinahe $1$, d. h. es gibt einen beinahe linearen Zusammenhang zwischen Verkaufsfläche und Jahresumsatz.