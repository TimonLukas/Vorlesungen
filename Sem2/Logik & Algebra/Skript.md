# Logik und Algebra

<!-- toc orderedList:0 depthFrom:1 depthTo:6 -->

* [Logik und Algebra](#logik-und-algebra)
  * [Mengenlehre](#mengenlehre)
    * [Mathematische Zeichen](#mathematische-zeichen)
    * [Menge](#menge)
      * [Beispiele für Mengen](#beispiele-für-mengen)
      * [Beispiele für Nicht-Mengen](#beispiele-für-nicht-mengen)
      * [Definition](#definition)
      * [Notation](#notation)
      * [Standardbezeichnungen](#standardbezeichnungen)
      * [Widersprüche](#widersprüche)
    * [Unendlichkeit von Mengen](#unendlichkeit-von-mengen)
    * [Beziehungen zwischen Mengen](#beziehungen-zwischen-mengen)
      * [Definition](#definition-1)
      * [Teilmengen](#teilmengen)
        * [Definition](#definition-2)
        * [Beispiele](#beispiele)
        * [Anzahl der Elemente einer Teilmenge](#anzahl-der-elemente-einer-teilmenge)
      * [Potenzmengen](#potenzmengen)
        * [Definition](#definition-3)
        * [Menge der Elemente](#menge-der-elemente)
        * [Übung](#übung)
        * [Leere Menge](#leere-menge)
        * [Übungen](#übungen)
    * [Mengenoperationen](#mengenoperationen)
      * [Vereinigung](#vereinigung)
        * [Beispiel](#beispiel)
      * [Rechenregeln](#rechenregeln)
  * [Relationen](#relationen)
  * [Kongruenzrelationen](#kongruenzrelationen)
  * [Modulare Arithmetik](#modulare-arithmetik)
  * [Boolesche Algebra](#boolesche-algebra)
  * [Schaltalgebra](#schaltalgebra)
  * [Aussagenlogik](#aussagenlogik)

<!-- tocstop -->

## Mengenlehre
Die Mengenlehre wurde entwickelt von **Georg Cantor**.
### Mathematische Zeichen
* $\vert$: für die gilt
* $\in$: Wenn $x$ Element von $\mathbb{N}$ ist &rarr; $x \in \mathbb{N}$

### Menge
* Kommt auch in der Umgangssprache vor
  * Bezeichnet eine Gesamtheit konkreter Dinge, abstrakter Konzepte oder Personen

#### Beispiele für Mengen
* Menge der Einwohner von Mannheim
* Menge der Produkte eines Unternehmens
* Menge der Studenten des Kurses WWI16SCB
* Menge der natürlichen Zahlen
* Menge der Primzahlen
* Menge der reellen Zahlen
* Menge der Kunden eines Unternehmens
* Menge der Vereine der 1. Fußball-Bundesliga

#### Beispiele für Nicht-Mengen
* Eine Menge Butter
* Eine Menge Energie

#### Definition
Unter einer Menge $M$ verstehen wir eine Zusammenfassung von bestimmten wohlunterschiedenen Objekten der Anschauung oder des Denkens - diese heißen **Elemente** der Menge $M$ - zu einem Ganzen.

#### Notation
* $M = \{a, b, c, d\}$
* $\{\} = \text{ Mengenklammern}$
* $\mathbb{N} = \{0, 1, 2, 3, \ldots\}$
* $\mathbb{G} = \{0, 2, 4, 6, 8, \ldots, 2n, \ldots\}$

Mengen lassen sich häufig über die definierende Eigenschaft beschreiben:
$$
M = \{x\;\vert\;x\text{ hat die Eigenschaft } Q\}
$$

**Beispiel**:

$$
\begin{align}
M &= \{x\;\vert\;x\text{ ist natürliche Zahl und gerade}\\
&= \{x\;\vert\;x\in\mathbb{N}\text{ und }\frac{x}{2}\in\mathbb{N}\}
\end{align}
$$

#### Standardbezeichnungen
* $\mathbb{N}$: Menge der natürlichen Zahlen
* $\mathbb{Z}$: Menge der ganzen Zahlen $(= \{\ldots, -3, -2, -1, 0, 1, 2, 3, \ldots,\})$
  * $\mathbb{Z}_N$: $\{0, 1, \ldots, n - 1\}$
  * $\mathbb{Z}_2$: $\{0, 1\}$
* $\mathbb{Q}$: Menge der rationalen Zahlen $(= \{\frac{p}{q}\;\vert\;p\in\mathbb{Z}\text{ und } q\in\mathbb{Z}, q \neq 0)$
* $\mathbb{R}$: Alle rationalen und irrationalen Zahlen
* $\mathbb{C}$: Menge der komplexen Zahlen
* $\mathbb{H}$: Menge der Quaternionen
* $\emptyset$: Die eindeutige Menge, die keine Elemente enthält $(\{\})$
* $\{\emptyset\}$: Die Menge, die aus der leeren Menge besteht (Hat also ein Element)

#### Widersprüche
* Die "naive" Mengenlehre von Cantor enthält viele Widersprüche
* Genannt **Anomalien**
* Dies liegt an der Definition des Begriffs "Menge"
* Beispiel: **Russellsche Antinomie**
  * Der Barbier von Sevilla ist so definiert, dass er alle Männer von Sevilla rasiert, die sich nicht selbst rasieren
  * Rasiert er sich selbst?
  * Aufgrund von **Selbstreferenz** gibt es nicht auflösbare Widersprüche

### Unendlichkeit von Mengen
* Kardinalität oder Mächtigkeit der Menge $M$ ist die Anzahl der Elemente
* Sie its **abzählbar endlich**, wenn man die Elemente der Menge abzählen kann und jedes Element erwischt:

|$\mathbb{Z}$ |$\mathbb{N}$ |
|-------------|-------------|
|0            |0            |
|1            |1            |
|-1           |2            |
|2            |3            |
|-2           |4            |
|3            |5            |
|-3           |6            |

Analog klappt das mit $\mathbb{Q}$, d. h. es kann eine umkehrbare Abbildung $\mathbb{Q} \Leftrightarrow \mathbb{N}$ ausgegeben werden.

Ist $\mathbb{R}$ abzählbar? Nein &rarr; Cantorsches Diagonalisierungsverfahren  
$\mathbb{R}$ überabzählbar unendlich

### Beziehungen zwischen Mengen
#### Definition
Zwei Mengen $M_1$ und $M_2$ heißen gleich, wenn jedes Element von $M_1$ auch Element von $M_2$ ist und umgekehrt.
$$
M_1 \equiv M_2
$$
Dabei spielt die Reihenfolge der aufgelisteten Elemente keine Rolle, mehrfach auftretende Elemente zählen nur 1&times;.
$$
\{a, b, c\} = \{c, a, b\} = \{c, a, b, a , c\}
$$

#### Teilmengen
##### Definition
* Eine Menge $M_1$ heißt **Teilmenge** von $M_2$, wenn jedes Element von $M_1$ auch Element von $M_2$ ist (aber nicht notwendigerweise umgekehrt)
* Zeichen: $\subseteq$ ($M_1 \subseteq M_2$)
* $M_1$ heißt **echte Teilmenge** von $M_2$, falls $M_1$ Teilmenge von $M_2$ ist und es ein $a \in M_2$ gibt mit $a \notin M_1$
  * Bedeutet: $M_1$ ist dann echte Teilmenge von $M_2$, wenn alle Elemente von $M_1$ in $M_2$ vorkommen, aber nicht andersrum

##### Beispiele
$M_1 = \{1, 2, 3\} \land M_2 = \{1, 2, 3, 4, 5\}$:
* $M_1 \subset M_2$
* Da $1, 2, 3$ in M_2 vorkommen, $4, 5$ aber nicht in $M_1$

$M_1 = \{1, 2, 3\} \land M_2 = \{1, 2, 3, 4, 5\} \land M_3 = \{1\}$:
* $M_3 \subset M_2$
* $M_3 \subset M_1$
* $1 \in M_2$

$M = \{a, b, c\}$; Man liste alle Teilmengen von $M$ auf:

|Teilmenge                      |Elemente             |
|-------------------------------|---------------------|
|$\emptyset$                    |1 TM mit 0 Elementen |
|$\{a\}, \{b\}, \{c\}$          |3 TM mit 1 Element   |
|$\{a, b\}, \{a, c\}, \{b, c\}$ |3 TM mit 2 Elementen |
|$\{a, b, c\}$                  |1 TM mit 3 Elementen |

##### Anzahl der Elemente einer Teilmenge
* Der Binomialkoeffizient $\binom{n}{k}$ sagt aus, wie viele verschiedene $k$-elementige Teilmengen eine $n$-elementige Menge hat:
$$
\binom{n}{k} = \frac{n!}{k!(n - k)!}
$$
* Das PASCALsche Zahlendreieck sind exakt die Binomialkoeffizienten:
$$
\binom{n}{k} = \binom{n - 1}{k - 1} + \binom{n - 1}{k}
$$


#### Potenzmengen
##### Definition
* Die **Potenzmenge** ist die Menge aller Teilmengen einer Menge
* Sei $M$ eine (endliche) Menge
* $p(M)$ ist die **Potenzmenge** von $M$:
$$
\begin{align}
M =& \{a, b, c\}\\
p(M) =& \{\emptyset, \{a\}, \{b\}, \{c\}, \{a, b\}, \{a, c\}, \{b, c\}, \{a, b, c\}\}
\end{align}
$$

##### Menge der Elemente
* Wenn $M$ eine $n$-elementige Menge ist, dann hat $p(M)$ $2^n$ Elemente
* Herleitung:

Wenn $M$ $n$ Elemente hat, dann hat die Potenzmenge $p(M)$
$$
\begin{align}
&\binom{n}{0} + \binom{n}{1} + \binom{n}{2} + \binom{n}{3} + \ldots + \binom{n}{n}\\
&= \sum^n_{k = 0} \binom{n}{k} = 2^n
\end{align}
$$
Elemente. Das gilt aufgrund des Binomialtheorems:
$$
\begin{align}
&(a + b)^n = \sum^n_{k = 0} \binom{n}{k} a^{n - k} * b^k\\
&(a + b)^2 = a^2 + 2ab + b^2\\
&(a + b)^3 = a^3 + 3a^2b + 3ab^2 + b^3\\
&(a + b)^4 = a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4
\end{align}
$$
Mit $a = 1 \land b = 1$:
$$
2^n = \sum^n_{k = 0} \binom{n}{k}
$$
Außerdem: Setzt man $a = 1 \land b = -1$:
$$
0 = \sum^n_{k = 0} \binom{n}{k}(-1)^k
$$

##### Übung
Man gebe in jedem Fall an, ob $x \in M$, $x \subseteq M$, beides oder keins gilt.

|Aufgabe                                          |Ergebnis     |Begründung|
|-------------------------------------------------|-------------|----------|
|$x = \{1\}, M = \{1, 2, 3\}$                     |$x \subset M$|$x$ ist eine Menge von Zahlen mit dem Element $1$. $M$ ist ebenfalls eine Menge von Zahlen mit den Elementen $1, 2, 3$. Da $1 \in x \land 1 \in M$, ist $x \subseteq M$. Da $2 \in M \land 2 \notin x$, ist $x \subset M$.|
|$x = \{1\}, M = \big\{\{1\}, \{2\}, \{3\}\big\}$ |$x \in M$    |Die Elemente von $M$ sind die Mengen $\{1\}, \{2\}, \{3\}$. Da $x = \{1\}$, ist $x \in M$.|
|$x = \{1\}, M = \big\{1, 2, \{1, 2\}\big\}$      |$x \subset M$|$x \subset M$ wie 1.|
|$x = \{1, 2\}, M = \big\{1, 2, \{1, 2\}\big\}$   |Beides       |Die Teilmengen von $M$ sind: $p(M) = \big\{\emptyset, \{1\}, \{2\}, \{\{1, 2\}\}, \{1, 2\}, \{1, \{1, 2\}\}, \{2, \{1, 2\}\}, \{1, 2, \{1, 2\}\}\big\}$|
|$x = \{1\}, M = \big\{\{1, 2\}, 3\big\}$         |Keins        ||
|$x = 1, M = \big\{\{1\}, \{2\}, \{3\}\big\}$     |Keins        ||

##### Leere Menge
$$
\begin{align}
&p(\emptyset) = \emptyset\\
&p(p(\emptyset)) = \emptyset
\end{align}
$$

##### Übungen
Sei $M_1 = \{1, 2, 3\}, M_2 = \{1, 2\}$:

|Term                                   |Wahr   |Falsch |
|---------------------------------------|-------|-------|
|$M_2 \in p(M_1)$                       |&times;|       |
|$M_2 \in M_1$                          |       |&times;|
|$M_1 \in p(M_1)$                       |&times;|       |
|$M_1 \subseteq p(M_1)$                 |       |&times;|
|$M_2 \subseteq p(M_1)$                 |       |&times;|
|$\big\{1\}, M_2\big\} \subseteq p(M_1)$|&times;|       |
|$\emptyset \in p(M_1)$                 |&times;|       |
|$\emptyset \subseteq p(M_2)$           |&times;|       |
|$p(M_2) \subseteq p(M_1)$              |&times;|       |

### Mengenoperationen
#### Vereinigung
Seien $M_1, M_2$ zwei Mengen. Die **Vereinigung**
$$
M_1 \cup M_2 = \{x\;\vert\;x\in M_1 \lor x \in M_2\}
$$
ist die Menge aller $x$, die entweder in $M_1$ oder in $M_2$ oder beides sind.
Man schreibt:
$$
\cup^n_{i = 1} M_i = M_1 \cup M_2 \cup \ldots \cup M_n
$$
für die Vereinigung mehrerer Mengen.
##### Beispiel
$$
\begin{align}
M_1 &= \{1, 2, 3\}, M_2 = \{2, 3, 4\}\\
M_1 \cup M_2 &= \{1, 2, 3\} \cup \{2, 3, 4\}\\
&= \{1, 2, 3, 4\}
\end{align}
$$

#### Rechenregeln
**Müssen eigentlich bewiesen werden!**
1. $M \cup M = M$ (Idempotenzgesetz)
2. $M \cup \emptyset = M$ ($\emptyset$ ist das neutrale Element der $\cup$-Operation)
3. $M_1 \cup M_2 = M_2 \cup M_1$ (Kommutativgesetz)

## Relationen

## Kongruenzrelationen

## Modulare Arithmetik

## Boolesche Algebra

## Schaltalgebra

## Aussagenlogik
