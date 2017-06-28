# Session 03

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Relationen](#relationen)
  * [Definition](#definition)
  * [Beispiele](#beispiele)
    * [Schlussfolgerung](#schlussfolgerung)
  * [n-näre Relationen](#n-näre-relationen)
  * [Relationen sind Mengen](#relationen-sind-mengen)
* [Spezielle Relationen](#spezielle-relationen)
  * [Definition](#definition-1)
    * [Beispiele](#beispiele-1)
  * [Adjazenz-Matrix](#adjazenz-matrix)
  * [Definition](#definition-2)
    * [Beispiel](#beispiel)
    * [Übung](#übung)
  * [Definition transitiv](#definition-transitiv)
    * [Beispiele](#beispiele-2)
* [Äquivalenzrelationen](#äquivalenzrelationen)
  * [Definition](#definition-3)
  * [Beispiel](#beispiel-1)
  * [Beispiel](#beispiel-2)
    * [Reflexiv](#reflexiv)
    * [Symmetrisch](#symmetrisch)
    * [Transitiv](#transitiv)
    * [Äquivalenzklassen](#äquivalenzklassen)
* [BELL-Zahlen](#bell-zahlen)
  * [Beispiel](#beispiel-3)
* [Modulus](#modulus)
  * [Definition](#definition-4)
  * [Beispiele](#beispiele-3)
  * [Satz](#satz)
  * [Beweis](#beweis)

<!-- tocstop -->

## Relationen
### Definition
Eine binäre Relation $R$ zwischen den Mengen $M_1$ und $M_2$ ist eine Teilmenge des kartesischen Produkts $M_1 \times M_2$, also

$$
R \subseteq M_1 \times M_2 = \{(m_1, m_2) \vert m_1 \in M_1, m_2 \in M_2\}
$$

Ist $(m, n) \in R$, so schreibt man auch $m R n$.

Eine $n$-näre Relation $R$ zwischen $n$ Mengen $M_1, M_2, \ldots, M_n$ ist eine Teilmenge des kartesischen Produkts

$$
M_1 \times \ldots \times M_n = \{(m_1, \ldots, m_n) \vert m_i \in M_i, i-1, \ldots, n\}
$$

### Beispiele
1. Sei $R = \{(x, y) \in \mathbb{R} \times \mathbb{R} \vert y = x^2\}$. Dies ist die normale Parabelgleichung.

Also: Jede vollwertige Funktion mit reellem Argument ist eine Relation über $\mathbb{R} \times \mathbb{R}$.

Umgekehrt gilt dies nicht! Also: Nicht jede Teilmenge von $\mathbb{R} \times \mathbb{R}$ ist auch eine Funktion.

#### Schlussfolgerung
Funktionen sind spezielle Relationen (Relationen sind allgemeiner)

2. $R = \{(x, y) \in \mathbb{R} \times \mathbb{R} \vert x \leq y\}$. Dies sind alle Werte unterhalb der Funktion $f(x) = x$.

3. $M_1 = \text{Menge der Städte der Welt}$
4. $M_2 = \text{Menge der Länder der Welt}$
5. $M_1 \times M_2$

$$
\begin{align}
R \subset M_1 \times M_2 &= \{(a, b) \in M_1 \times M_2 \vert a \text{ist Hauptstadt von b}\}\\
&= \{(\text{Berlin, D}), (\text{Paris, F}), (\text{London, GB}), (\text{Washington, USA}), \ldots\}
\end{align}
$$

6. Würfel werfen:

$$
\begin{align}
M &= \{1, 2, 3, 4, 5, 6\}\\
M \times M &= \{(x, y) \vert x \in M, y \in M\}\\
&= \{(1, 1), (1, 2), \ldots, (1, 6), (2, 1), (2, 2), \ldots, (2, 6), \ldots\}
\end{align}
$$

$$
\begin{align}
R \subset M \times M &= \{(x, y) \in M \times M \vert \text{x ist Teil von y}\}\\
&= \{(1, 1), (1, 2), (1, 3), (1, 4), (1, 5), (1, 6),\\
&(2, 2), (2, 4), (2, 6), (3, 3), (3, 6), (4, 4), (5, 5), (5, 6)\}
\end{align}
$$

7. Mengen

$$
\begin{align}
M_1 &= \text{Menge der DHBW-Kurse im Sommer-Semester 2017}\\
&= \{\text{WWI16SCA}, \text{WWI16SCB}, \text{WWI16SCI}, \ldots\}\\
M_2 &= \text{Menge der Kursräume an der DHBW}\\
&= \{\text{269C}, \text{271C}, \text{256B}, \text{184C}, \ldots\}\\
R &= M_1 \times M_2 = \{(K, Ra) \vert K \in M_1, Ra \in M_2\}
\end{align}
$$

### n-näre Relationen
Eine n-näre Relatio nist also eine Menge von geordneten n-Tupeln.
$$
R = \{(m_1^1, m_2^1, \ldots, m_n^1), (m_1^2, m_2^2, \ldots, m_n^2), \ldots\} \text{(= n-Tupel)}
$$

Diese sind in der Informatik Tabellen mit $n$ Spalten.

|$M_1$|$M_2$|$\ldots$|$M_n$|
|-----|-----|--------|-----|
|$m_1^1$|$m_2^1$|$\ldots$|$m_n^1$|
|$m_1^2$|$m_2^2$|$\ldots$|$m_n^2$|
|$\ldots$|$\ldots$|$\ldots$|$\ldots$|
|$m_1^k$|$m_2^k$|$\ldots$|$m_n^k$|

### Relationen sind Mengen
Mit Relationen können sämtliche Mengenoperationen durchgeführt werden.  
In der Informatik: SQL-Anweisungen, z. B.

```SQL
SELECT * FROM kunden WHERE HAUSWERT > 1500
```

## Spezielle Relationen
Betrachte ab jetzt binäre Relationen über eine Menge $M$.

### Definition
a) Eine Relation $I$ heißt Identitätsrelation auf $M$, wenn gilt
$$
I = \{(x, x) \in M \times M \vert \text{für alle x} \in \text{M}\}
$$

b) Eine binäre Relation $R \subseteq M \times M$ heißt **reflexiv**, wenn $I \subseteq R$ (jedes Element ist als Paar mit sich selbst vorhanden).

c) Eine binäre Relation $R \subseteq M \times M$ heißt **irreflexiv**, wenn gilt: Es gibt kein $x \in M$ mit $(x, x) \in R$ (kein Element ist als Paar mit sich selbst vorhanden).

#### Beispiele
1. $M = \{1, 2, 3, 4\}$

$$
R \subseteq M \times M = \{(1, 2), (2, 1), (1, 1), (2, 2), (3, 4), (4, 1), (4, 4)\}
$$

$R$ ist nicht reflexiv, da $(3, 3)$ fehlt.
$R$ ist nicht irreflexiv, da es $(1, 1), (2, 2), (4, 4)$ gibt.

2. $M = \mathbb{R}$

$$
R = \{(x, y) \in \mathbb{R} \times \mathbb{R} \vert x \leq y\}
$$

$R$ ist reflexiv, da durch $x \leq y$ der Fall $x = y$ mit eingeschlossen ist.

### Adjazenz-Matrix
Eine binäre Relation $R$ kann auch als Matrix dargestellt werden; diese nennt man Adjazenz-Matrix.

|     |1  |2  |3  |4  |
|-----|---|---|---|---|
|**1**|1  |1  |0  |0  |
|**2**|1  |1  |0  |0  |
|**3**|0  |0  |0  |0  |
|**4**|1  |0  |1  |1  |

### Definition
Eine binäre Relation $R \subseteq M \times M$ heißt **symmetrisch**, wenn gilt:

$$
\forall (x, y) \in R \Rightarrow (y, x) \in R
$$

#### Beispiel
$M$: Menge aller Frauen

**Definiere**: $R \subseteq M \times M = \{(a, b) \in M \times M \text{ mit a ist Schwester von b}\}$

ist symmetrisch, nicht reflexiv, irreflexiv.

#### Übung

$$
\begin{align}
M &= \{1, 2, 3, 4\}\\
R_1 &= \{(1, 1), (3, 4), (4, 3)\}\\
R_2 &= \{(1, 1), (2, 2), (3, 3), (4, 4)\}\\
R_3 &= \{(1, 2), (2, 1), (1, 3), (3, 1)\}
\end{align}
$$

|Menge|Symmetrisch|Reflexiv |Irreflexiv |
|-----|-----------|---------|-----------|
|$R_1$|&check;    |&times;  |&times;    |
|$R_2$|&check;    |&check;  |&times;    |
|$R_3$|&check;    |&times;  |&times;    |

### Definition transitiv
Eine binäre Relation $R \subseteq M \times M$ heißt **transitiv**, wenn gilt:

$$
\text{für } (x, y) \in R \land (y, z) \in R \Rightarrow (x, y, z)
$$

#### Beispiele
1. Schwester-Relationen über $n$ Frauen: transitiv
2. $M = \{1, 2, 3, 4, 5, 6\}$  
$R = \{(1, 2), (2, 3), (2, 6), (1, 3), (4, 4)\}$

Sei $R = \{(a, b) \in \mathbb{N} \times \mathbb{N} \vert a * b \text{ ist gerade}\}$

$R$ ist:
* nicht reflexiv, da $3 * 3 = 9$ nicht gerade ist
* nicht irreflexiv, da $2 * 2 = 4$ gerade ist
* symmetrisch, da die Multiplikation kommutativ ist ($a * b = b * a$)
* nicht transitiv, da $3 * 4 = 12 \land 4 * 5 = 20$, aber $3 * 5 = 15$

## Äquivalenzrelationen
### Definition
EineRelation $R \subseteq M \times M$ heißt **Äquivalenzrelation**, wenn $R$ reflexiv, symmetrisch und transitiv ist.

### Beispiel
$M$ = Menge der DHBW-Ma-Studenten

Ist die Menge...
* Reflexiv? &check;
* Symmetrisch? &check;
* Transitiv? &check;

$\Rightarrow$ Äquivalenzrelation

$[\text{Ipach}] = \{y \in M \vert (y, \text{Ipach}) \in R\}$ ist die **Äquivalenzklasse** von Herr Ipach.  
= WWI16SCB

$[\text{Riedel}] = [\text{Ipach}]$ = WWI16SCB = jeder Studierende des Kurses WWI16SCB ist Repräsentant der Äquivalenzklasse

$[\text{Erlenhofer}]$ = WWI16SCC

$[\text{Riedel}] \cap [\text{Erlenhofer}] = \emptyset$

Äquivalenzrelationen zerlegen eine Menge $M$ in paarweise disjunkte Teilmengen.  
Die Vereinigung aller Äquivalenzrelationen ergibt $M$  
&rarr; Äquivalenzrelationen partitionieren eine Menge $M$.

### Beispiel

$M$ = \{1, 2, 3, 4, 5, 6\}  
$R = \{(1, 2), (2, 4), (4, 6), (3, 5), \ldots\}$


Man ergänze $R$ mit möglichst wenig Elementen zu einer Äquivalenzrelation. Wie sehen die Äquivalenzklassen aus?

Damit $R$ eine Äquivalenzrelation ist, muss $R$
* reflexiv
* symmetrisch
* transitiv

sein.

#### Reflexiv
$(1, 1), (2, 2), (3, 3), (4, 4), (5, 5), (6, 6)$ hinzufügen

#### Symmetrisch
$(2, 1), (4, 2), (6, 4), (5, 3)$ hinzufügen

$$
\begin{align}
R' = \{&(1, 1), (2, 2), (3, 3), (4, 4), (5, 5), (6, 6),\\
  &(1, 2), (2, 1), (2, 4), (4, 2), (4, 6), (6, 4),\\
  &(5, 3), (3, 5)\}
\end{align}
$$

#### Transitiv
$(1, 4), (2, 6), (1, 6), (4, 1), (6, 2), (6, 1)$ hinzufügen

#### Äquivalenzklassen

$$
\begin{align}
[1] &= \{x \in M \vert (x, 1) \in R\}\\
&= \{1, 2, 4, 6\} = [2] = [4] = [6]\\
&[3] = \{3, 5\} = [5]
\end{align}
$$

Es gilt:
$[1] \cap [3] = \emptyset$
$[1] \cup [3] = M$

Also: Jede Äquivalenzrelation führt zu einer Partitionierung der zugrunde liegenden Menge $M$. Umgekehrt gilt auch: Jede Partitionierung einer (endlichen) Menge $M$ induziert eine Äquivalenzrelation über $M$.

## BELL-Zahlen
Die Bell-Zahlen $B_n$ geben an, auf wie viele unterschiedliche Arten eine Menge $M$ mit $n$ Elementen in nichtleere Teilmengen partitioniert werden kann. Dabei sagen die BELL-Zahlen aus, wie viele Äquivalenzrelationen existieren.

### Beispiel
$M = \{a, b, c\}$

$$
\begin{align}
P_1 &= \big\{\{a\}, \{b\}, \{c\}\big\}\\
P_2 &= \big\{\{a, b\}, \{c\}\big\}\\
P_3 &= \big\{\{a, c\}, \{b\}\big\}\\
P_4 &= \big\{\{b, c\}, \{a\}\big\}\\
P_5 &= \big\{\{a, b, c\}\big\}\\\\
B_n &= \sum_{k = 0}^{n - 1} \binom{n-1}{k} B_k
\end{align}
$$

$$
B_0 = 1, B_1 = 1, B_2 = 2, B_3 = 5, B_4 = 15, B_5 = 52, B_6 = 203
$$

d. h. über $\{1, 2, 3, 4, 5, 6\}$ kann man 203 verschiedene Äquivalenzrelationen basteln.

$$
\begin{align}
&n = 1: 1\\
&n = 2: 1, 2\\
&n = 3: 2, 3, 5\\
&n = 4: 5, 7, 10, 15\\
&n = 5: 15, 20, 27, 37, 52\\
&n = 6: 52, 67, 87, 114, 151, 203
\end{align}
$$

## Modulus
### Definition
Über die Menge $\mathbb{Z}$ (= ganze Zahlen) die folgende Relation:
$$
\equiv\;\subseteq \mathbb{Z} \times \mathbb{Z}
$$
mit $x \equiv y$ genau dann, wen die Zahl $n \in \mathbb{N}$ die Differenz $x - y$ ohne Rest teilt.

Andere Schreibweise:
$$
x \equiv y \text{ mod } n
$$

Die folgenden Aussagen sind gleichwertig:
1. $x \equiv y \text{ mod } (\%)\;n$
2. $x - y$ wird ohne Rest durch n geteilt: $x - y = k * n, k \in \mathbb{Z}$
3. Es gibt eine ganze Zahl $l \in \mathbb{Z}$ mit
$$
x = l * n + y
$$
4. $x$ und $y$ haben den gleichen Rest, wenn sie durch $n$ geteilt werden:
$$
x = k * n + r;\;(k \in \mathbb{Z})\\
y = l * n + r;\;(l \in \mathbb{Z})
$$

### Beispiele
1. $15 \equiv 0 \;\%\; 5$
2. $7 \equiv 2 \;\%\; 5$
3. $22 \equiv 7 \equiv 2 \equiv -3 \;\%\; 5$
4. $7 \equiv -3 \;\%\; 5$

### Satz
$a \equiv b \;\%\; n$ ist eine Äquivalenzrelation

### Beweis
1. $a \equiv b \;\%\; n$ ist reflexiv (trivial, weil $a \equiv a \;\%\; n \Leftrightarrow a - a = 0$)
2. $a \equiv b \;\%\; n$ ist symmetrisch.  
$a \equiv b \;\%\; n \Rightarrow b = a \;\%\; n$  
$a = b \;\%\; n$ heißt $a = k * n + b\;(k \in \mathbb{Z})$  
$\Rightarrow b = a - k * n\;(l = -k)$  
$b = l * n + a$  
$\Rightarrow b \equiv a \;\%\; n$
3. $a \equiv b \;\%\; n$ und $b \equiv c \;\%\; n \Rightarrow a \equiv c \;\%\; n$
$(k, l) \in \mathbb{Z}$   
$a - b = k * n$  
$b - c = l * n$  
$a - c = (k + l) * n = m * n \Rightarrow a = c \;\%\; n$
