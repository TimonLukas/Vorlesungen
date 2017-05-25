# Session 01

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Dozent](#dozent)
* [Logik & Algebra](#logik-algebra)
* [Literatur](#literatur)
* [Mengenlehre](#mengenlehre)
  * [1. Grundlegendes](#1-grundlegendes)
    * [Beispiele](#beispiele)
    * [Definition](#definition)
    * [Merke](#merke)
    * [Gegenbeispiele](#gegenbeispiele)
    * [Notation](#notation)
    * [Beispiel](#beispiel)
    * [Standardbezeichnungen](#standardbezeichnungen)
    * [Die 'naive' Mengenlehre](#die-naive-mengenlehre)
      * [Russellsche Antinomie](#russellsche-antinomie)
  * [2. Unendlichkeit von Mengen](#2-unendlichkeit-von-mengen)
  * [3. Beziehungen zwischen Mengen](#3-beziehungen-zwischen-mengen)
    * [Definition](#definition-1)
    * [Teilmengen](#teilmengen)
      * [Definition](#definition-2)
      * [Beispiele](#beispiele-1)
    * [Potenzmenge](#potenzmenge)
      * [Definition](#definition-3)
      * [Übung](#übung)
    * [Mengenoperationen](#mengenoperationen)
      * [Definition](#definition-4)
      * [Beispiel](#beispiel-1)
      * [Rechenregeln](#rechenregeln)

<!-- tocstop -->

## Dozent
* Dr. Armin Wiedemann

## Logik & Algebra
1. Mengenlehre
2. Relationen (relationales Datenbankmodell)
3. Kongruenzrelationen, modulare Arithmetik ($a \equiv b\;mod\;n$)
4. Boolesche Algebra
5. Schaltalgebra
6. Aussagenlogik

## Literatur
* Skripte und dort zitierte Literatur

## Mengenlehre
### 1. Grundlegendes
* (*Georg Canter*, 1845 - 1918)

Der Begriff *Menge* ist in der Umgangssprache bekant und bezeichnet eine Gesamtheit konkreter Dinge, abstrakte Konzepte oder Personen.

#### Beispiele
* Menge der Einwohner von Mannheim
* Menge der Produkte eines Unternehmens
* Menge der Studenten des Kurses 16SCB
* Menge der natürlichen Zahlen
* Menge der Primzahlen
* Menge der reellen Zahlen
* Menge der Kunden eines Unternehmens
* Menge der Vereine der 1. Fußball-Bundesliga

#### Definition
Unter einer Menge $M$ verstehen wir eine Zusammenfassung von bestimmten wohlunterschiedenen Objekten der Anschauung oder des Denkens - diese heißen **Elemente** der Menge $M$ - zu einem Ganzen.

#### Merke
Das letzte Beispiel zeigt, dass die Elemente von Mengen auch selbst Mengen sein können

#### Gegenbeispiele
Keine Menge im Sinne *Canters*:
* Eine Menge Butter
* Eine Menge Energie

#### Notation
* $M = \{a, b, c, d\}$
* $\{\}$ = Mengenklammern
* $\mathbb{N} = \{0, 1, 2, 3, \dots\}$
* $\mathbb{G} = \{0, 2, 4, 6, 8, \dots, 2n, \dots\}$

Mengen lassen sich häufig über die definierende Eigenschaft beschreiben:
$$
M = \{x\;\vert\;x \text{ hat die Eigenschaft } Q\}
$$
($\;\vert\;$ = für die gilt)

#### Beispiel
$$
\begin{align}
M &= \{x\;\vert\;x \text{ ist natürliche Zahl und gerade}\}\\
&= \{x\;\vert\;x \in \mathbb{N} \text{ und } \frac{x}{2} \in \mathbb{N}\}
\end{align}
$$
($\in$ &rarr; Wenn $x$ Element von $N$ ist &rarr; $x \in N$)

#### Standardbezeichnungen
$$
\begin{align}
\mathbb{N}&: \text{ Menge der natürlichen Zahlen}\\
\mathbb{Z}&: \text{ Menge der ganzen Zahlen}\\
&= \{\ldots, -3, -2, -1, 0, 1, 2, 3, \ldots\}\\
\mathbb{Z}_N &= \{0, 1, \ldots, n - 1\}\\
\mathbb{Z}_2 &= \{0, 1\}\\
\mathbb{Q} &= \text{ Menge der rationalen Zahlen}\\
&= \{\frac{p}{q}\;\vert\;p \in \mathbb{Z} \text{ und } q \in \mathbb{Z}, q \neq 0\}
\end{align}
$$

Es gibt Zahlen, die sich nicht in der Form $\frac{p}{q}$ darstellen lassen!  
Beispiel: Hypotenuse eines rechtwinkligen Dreiecks mit Kathetenlänge 1 ist $\sqrt{2}$

Irrationale Zahlen: $\sqrt{3}, \ldots, \pi, e, \ldots$

$\mathbb{R}$ beinhaltet alle rationalen und irrationalen Zahlen.

**Problem**: $\mathbb{R}$ ist algebraisch nicht abgeschlossen, d. h. in $\mathbb{R}$ gibt es keine Lösung der Gleichung
$$
x^2 + 1 = 0
$$

$\mathbb{C}$: Menge der komplexen Zahlen  
$\mathbb{H}$: Menge der Quaternionen

Eine weitere Standardbezeichnung ist
$\emptyset$: Leere Menge, die eindeutige Menge, die kein Element enthält  
Alternativ: $\{\;\}$  
$\{\emptyset\}$: dies ist die Menge, die aus der leeren Menge besteht, also 1 Element enthält!

#### Die 'naive' Mengenlehre
Die 'naive' Mengenlehre von Canter enthält jede Menge Widersprüche, sogenannte **Anomalien**. Dies liegt an der Definition des Begriffs 'Menge'.

##### Russellsche Antinomie
Der Barbier von Sevilla ist so definiert, dass er alle Männer von Sevilla rasiert, die sich nicht selbst rasieren.  
Rasiert er sich selbst oder nicht?  
Dies führt wegen der **Selbstreferenz** auf nicht auflösbare Widersprüche.

**Logik**: Dieser Satz ist falsch.

### 2. Unendlichkeit von Mengen
Man nennt die Kardinalität oder Mächtigkeit der Menge $\mathbb{N}$: *abzählbar endlich*, d. h. man kann die Elemente der Menge abzählen und erwischt jedes Element.

|$\mathbb{Z}$ |$\mathbb{N}$ |
|-------------|-------------|
|0            |0            |
|1            |1            |
|-1           |2            |
|2            |3            |
|-2           |4            |
|3            |5            |
|-3           |6            |

Analog klappt das mit $\mathbb{Q}$, d. h. es kann eine umkehrbare Abbildung $\mathbb{Q} \leftrightarrow \mathbb{N}$ ausgegeben werden.

Ist $\mathbb{R}$ abzählbar? Nein &rarr; Cantorsches Diagonalisierungsvefahren  
$\mathbb{R}$ &rarr; überabzählbar unendlich

### 3. Beziehungen zwischen Mengen
#### Definition
Zwei Mengen $M_1$ und $M_2$ heißen gleich, wenn jedes Element von $M_1$ auch Element von $M_2$ ist und umgekehrt.
$$
M_1 \equiv M_2
$$
Dabei spielt die Reihenfolge der aufgelisteten Elemente keine Rolle, mehrfach auftretende Elemente zählen nur 1&times;.

$$
\{a, b, c\} = \{c, a, b\} = \{c, a, b, a, c\}
$$

#### Teilmengen
##### Definition
Eine Menge $M_1$ heißt **Teilmenge** von $M_2$ mit Zeichen
$$
M_1 \subseteq M_2
$$
wenn jedes Element von $M_1$ auch Element von $M_2$ ist (aber nicht notwendigerweise auch umgekehrt). $M_1$ heißt **echte Teilmenge** von $M_2$, falls $M_1$ Teilmenge von $M_2$ ist und es gibt ein $a \in M_2$ mit $a \notin M_1$.

##### Beispiele
$$
M_2 = \{1, 2, 3, 4, 5\}, M_1 = \{1, 2, 3\}
$$
dann ist $M_1 \subset M_2$.

$$
M_3 = \{1\}\;M_3\subset M_2, M_3\subset M_1, 1 \in M_2
$$

$$
M = \{a, b, c\}
$$
Man liste alle Teilmengen von $M$ auf:

|Teilmenge|Elemente|
|---------|--------|
|$\emptyset$|1 TM mit 0 Elementen|
|$\{a\}, \{b\}, \{c\}$|3 TM mit 1 Element|
|$\{a, b\}, \{a, c\}, \{b, c\}$|3 TM mit 2 Elementen|
|$\{a, b, c\}$|1 TM mit 3 Elementen|

Der Binomialkoeffizient $\binom{n}{k}$ sagt aus, wie viele verschiedene $k$-elementige Teilmengen einer $n$-elementigen Menge hat
$$
\binom{n}{k} = \frac{n!}{k!(n - k)!}
$$

Das PASCALsche Zahlendreieck sind exakt die Binomialkoeffizienten.

$$
\binom{n}{k} = \binom{n - 1}{k - 1} + \binom{n - 1}{k}
$$

#### Potenzmenge
##### Definition
Sei $M$ eine (endliche) Menge. $p(M)$ ist die **Potenzmenge** von $M$, dann ist die Menge allter Teilmengen von $M$
$$
\begin{align}
M = &\{a, b, c\} \\
&p(M) = \big\{\emptyset, \{a\}, \{b\}, \{c\}, \{a, b\}, \{a, c\}, \{b, c\}, \{a, b, c\}\big\}
\end{align}
$$

**Satz**: Wenn $M$ eine $n$-elementige Menge ist, dann hat $p(M) 2^n$   Elemente.

**Wissen**: Wenn $M$ $N$ Elemente hat, dann hat sie
$$
\binom{n}{0} + \binom{n}{1} + \binom{n}{2} + \binom{n}{3} + \ldots + \binom{n}{n}
$$

$$
\sum^n_{k = 0} \binom{n}{k} = 2^n
$$

Das gilt aufgrund des Binomialtheorems
$$
\begin{align}
(a + b)^n &= \sum^n_{k = 0} \binom{n}{k} a^{n-k} * b^k\\
(a + b)^2 &= a^2 + 2ab + b^2\\
(a + b)^3 &= a^3 + 3a^2b + 3ab^2 + b^3\\
(a + b)^4 &= a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4
\end{align}
$$

Setze $a = 1$, $b = 1$
$$
2^n = \sum^n_{k = 0} \binom{n}{k}
$$

Außerdem: Setzt man $a = 1$, $b = -1$
$$
\Rightarrow 0 = \sum^n_{k = 0} \binom{n}{k} (-1)^k
$$

##### Übung
Man gebe in jedem Fall an, ob $x \in M, x \subseteq M$, beides oder keines gilt.
1. $x = \{1\}, M = \{1, 2, 3\}$
2. $x = \{1\}, M = \big\{\{1\}, \{2\}, \{3\}\big\}$
3. $x = \{1\}, M = \big\{1, 2, \{1, 2\}\big\}$
4. $x = \{1, 2\}, M = \big\{1, 2, \{1, 2\}\big\}$
5. $x = \{1\}, M = \big\{\{1, 2, 3\big\}$
6. $x = 1, M = \big\{\{1\}, \{2\}, \{3\}\big\}$


1. $x \subset M$, da $x$ eine Menge von Zahlen ist mit dem Element $1$. $m$ ist ebenfalls eine Menge von Zahlen, hier $1, 2, 3$. Da $1 \in x$ **und** $1 \in M$, ist $x \subseteq M$. Da $2 \in M, 2 \notin x$, ist $x \subset M$.
2. $x \in M$, denn die Elemente von $M$ sind die Mengen $\{1\}, \{2\}, \{3\};$ da $x = \{1\}$, ist $x \in M$.
3. $x \subset M$ wie in 1.
4. Beides; die Teilmengen von $M$ sind:
$$
p(M) = \big\{\emptyset, \{1\}, \{2\}, \{1, 2\big\}\}, \{1, 2\}, \{1, \{1, 2\}\}, \{2, \{1, 2\}\}, \{1, 2, \{1, 2\}\}\big\}
$$
5. Weder noch
6. Weder noch

---

Was ist: $p(\emptyset) = $  
Was ist: $p\big(p(\emptyset)\big) = $

---

Sei $M_1 = \{1, 2, 3\}, M_2 = \{1, 2\}$

|Term                                     |w      |f      |Keine Ahnung |
|-----------------------------------------|-------|-------|-------------|
|$M_2 \in p(M_1)$                         |&times;|       |             |
|$M_2 \in M_1$                            |       |&times;|             |
|$M_1 \in p(M_1)$                         |&times;|       |             |
|$M_1 \subseteq p(M_1)$                   |       |&times;|             |
|$M_2 \subseteq p(M_1)$                   |       |&times;|             |
|$\big\{\{1\}, M_2\big\} \subseteq p(M_1)$|&times;|       |             |
|$\emptyset \in p(M_1)$                   |&times;|       |             |
|$\emptyset \subseteq p(M_1)$             |&times;|       |             |
|$p(M_2) \subseteq p(M_1)$                |&times;|       |             |

#### Mengenoperationen
##### Definition
Seien $M_1, M_2$ zwei Mengen. Die **Vereinigung**
$$
  M_1 \cup M_2 = \{x\;\vert\;x\in M_1 \text{ oder } x\in M_2\}
$$
ist die Menge aller $x$, die entweder in $M_1$ oder in $M_2$ oder beides sind.

##### Beispiel
$$
\begin{align}
M_1 &= \{1, 2, 3\}, M_2 = \{2, 3, 4\}\\
M_1 \cup M_2 &= \{1, 2, 3\} \cup \{2, 3, 4\}\\
&= \{1, 2, 3, 4\}
\end{align}
$$

Man schreibt:
$$
\cup^n_{i = 1} M_i = M_1 \cup M_2 \cup \ldots \cup M_n
$$
für die Vereinigung mehrerer Mengen.

##### Rechenregeln
**Müssen eigentlich bewiesen werden!**

1. $M \cup M = M$ (Idempotenzgesetz)
2. $M \cup \emptyset = M$ ($\emptyset$ neutrales Element der $\cup$-Operation)
3. $M_1 \cup M_2 = M_2 \cup M_1$ (Kommutativgesetz)
