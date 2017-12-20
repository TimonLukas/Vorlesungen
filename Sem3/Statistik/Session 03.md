# Session 03

<!-- @import "[TOC]" {cmd="toc" depthFrom=2 depthTo=6 orderedList=false} -->
<!-- code_chunk_output -->

* [Korrelations- und Regressionsanalyse](#korrelations-und-regressionsanalyse)
* [4. Wahrscheinlichkeitsrechnung](#4-wahrscheinlichkeitsrechnung)
	* [4.1 Ereignisse, Wahrscheinlichkeitsbegriffe, Axiome und Theoreme](#41-ereignisse-wahrscheinlichkeitsbegriffe-axiome-und-theoreme)
	* [Grundbegriffe](#grundbegriffe)
	* [Wahrscheinlichkeitsbegriffe](#wahrscheinlichkeitsbegriffe)

<!-- /code_chunk_output -->

## Korrelations- und Regressionsanalyse
* Bei der **linearen Einfachregression** wird die folgende Regressionsgerade ermittelt:

$$
\hat{y}_i = \beta_0 + \beta_1 * x_i
$$

* Das gebräuchlichste Verfahren zur Berechnung dieser Regressionsgerade ist die **Methode der kleinsten Quadrate**:

$$
\sum^N_{i = 1} \epsilon^2 = \sum^N_{i = 1} (y_i - \hat{y}_i)^2 = \sum^N_{i = 1} (y_i - \beta_0 - \beta_1 * x_i)^2 \text{    minimieren!}
$$

$$
\beta_1 = \frac{\sum^N_{i = 1} (x_i - \overline{X}) * (y_i - \overline{Y})}{\sum^N_{i = 1} (x_i - \overline{X})^2}
$$

$$
\beta_0 = \overline{Y} - \beta_1 * \overline{X}
$$

* Um die Qualität einer Regressionsanalyse abzuschätzen, bezeichnet man den **Determinationskoeffizienten**:

$$
R^2 = \frac{\beta_1^2 * \sum^N_{i = 1} (x_i - \overline{X})^2}{\sum^N_{i = 1} (y_i - \overline{Y})^2}
$$

* Ein niedriger Determinationskoeffizient muss nicht in jedem Fall bedeuten, dass es zwischen den untersuchten Merkmalen keinen funktionalen Zusammenhang gibt
* Möglicherweise ist dieser Zusammenhang aber **nicht linear** oder wird von **anderen Variablen** überlagert

## 4. Wahrscheinlichkeitsrechnung
### 4.1 Ereignisse, Wahrscheinlichkeitsbegriffe, Axiome und Theoreme
* Wahrscheinlichkeitsrechnung stellt die Basis für die induktive Statistik dar
  * Da beim Schließen von einer Stichprobe auf die Grundgesamtheit wahrscheinlichkeitstheoretische Überlegungen benötigt werden
* Wahrscheinlichkeitsrechnung beschäftigt sich mit **zufälligen Ereignissen**
  * Vorgänge, deren Ergebnis nicht mit Sicherheit vorausgesagt werden kann
  * Beispiele: Münzwurf, Würfel, Urnenmodell, Roulette

### Grundbegriffe
* Die **Vereinigung** zweier Ereignisse $A$ und $B$, nmlich das neue Ereignis $A \cup B$, ist als die Menge aller Elementarereignisse, die zu $A$ oder $B$ gehören, definiert
* Der **Durchschnitt** zweier Ereignisse $A$ und $B$, nämlich das neue Ereignis $A \cap B$, ist als die Menge aller Ereignisse definiert, die zu $A$ und $B$ gehören
* Zwei Ereignisse $A$ und $B$ schließen einander aus, d. h. sie sind **disjunkt** (= unvereinbar), wenn es kein Elementareignis gibt, das zu beiden gleichzeitig gehört
* Ein Ereignis $B$ ist dann von einem Ereignis $A$ **unabhängig**, wenn das Eintreten von $B$ nicht vom Eintreten oder Nichteintreten von $A$ abhängt

### Wahrscheinlichkeitsbegriffe
* Der **klassische Wahrscheinlichkeitsbegriff* nach Laplace ist nur dann anwendbar, wenn alle Elementarereignisse die gleiche Wahrscheinlichkeit haben
  * Man berechnet den Quotient aus der zahl der günstigsten Fälle zur Zahl aller gleichmögichen Fälle
* Der **statistische Wahrscheinlichkeitsbegriff** geht von einem Zufallsexperiment aus, das aus einer langen Folge voneinander unabhängiger Versuche besteht
  * Das häufige Wiederholen eines Experiments ermöglicht Aussagen zur Wahrscheinlichkeit
* Der **subjektive Wahrscheinlichkeitsbegriff** spielt bei vielen Fragestellungen in der Ökonomie eine wichtige Rolle
  * Er stellt den (mehr oder weniger fundierten) persönlichen Überzeugungsgrad dar


* Aus den **Axiomen** (= Grundsätze formaler Art, die keines Beweises bedürfen), lassen sich verschiedene **Theoreme der Wahrscheinlichkeitsrechnung** herleiten
  * **Addition paarweise disjunkter (= unvereinbarer) Ereignisse**