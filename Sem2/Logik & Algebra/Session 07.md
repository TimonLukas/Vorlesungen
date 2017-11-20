# Session 07

## Schaltalgebra (Claude E. Shannon, 1938)
In seiner Masterarbeit hat C. Shannon den Zusammenhang zwischen der Booleschen Algebra und Schaltalgebra entwickelt.

Müssen zu diesem Zweck die Menge $B$ mit Leben füllen.

Bauteile:
* Schalter (\_/ \_): Zwei stabile Zustände: Offen oder zu
* Leitung (\_): Strom an/Strom aus

Weitere Bauteile in PCs:
* Kondensator: Geladen/nicht geladen
* Pixel: An/aus
* CD (Land/Pit)
* Glasfaser (Licht an, Licht aus)

Zwei stabile physikalische Zustände

Man abstrahiert von dem konkreten physikalischen Bauteil und verwendet dafür einen Platzhalter, den man **Bit** nennt. Die beiden Zustände nennt man $0$ und $1$.

### Definition
Wir definieren die Menge $B$ als Menge der möglichen Schaltzustände:
$$
B = \{0, 1\}
$$

Eine Variable $a \in B$, die genau zwei Werte annehmen kann, heißt **$\text{BOOLE}$sche Variable** oder **binäre Schaltvariable**.

### Frage
Wie können &and;, &or;, - auf dieser Menge realisiert werden?
1. Konjunktion ist die Reihenschaltung zweier Schalter

$\land: B \times B \rightarrow B$

|$a$    |$b$    |Lampe  |
|-------|-------|-------|
|&times;|&times;|&times;|
|&check;|&times;|&times;|
|&times;|&check;|&times;|
|&check;|&check;|&check;|

2. Disjunktion ist die parallele Schaltung zweier Schalter

$\lor: B \times B \rightarrow B$

|$a$    |$b$    |Lampe  |
|-------|-------|-------|
|&times;|&times;|&times;|
|&check;|&times;|&check;|
|&times;|&check;|&check;|
|&check;|&check;|&check;|

3. Negation oder $\text{BOOLE}$sches Komplement wird durch die **Ruhekontaktschaltung** (?) realisiert.

|$a$    |$\overline{a}$|
|-------|--------------|
|0      |1             |
|1      |0             |

### Definition
Zwei $\text{BOOLE}$sche Ausdrücke $A$ und $B$ sind gleich, in Formeln
$$
A = B
$$
wenn sie die gleichen Schaltwerte haben.

Dann ist
$$
a \land b = b \land a\\
a \lor b = b \lor a
$$
es gelten die Kommutativgesetze.

Neutrale Elemente:
* 1 $\Leftrightarrow$ geschlossener Schalter. Ist neutrales Element der Konjunktion.
* 0 $\Leftrightarrow$ ofener Schalter. Ist neutrales Element der Disjunktion.

#### Distributivgesetze
$$
a \land (b \lor c) = (a \land b) \lor (a \land c)\\
a \lor (b \land c) = (a \lor b) \land (a \lor c)
$$

#### Satz
$$
\forall a \in B:\\
a \lor 1 = 1\\
a \land 0 = 0
$$

Es gibt immer zwei Beweisebenen.
1. Syntax-Ebene:  
$$
\begin{align}
a \lor 1 &= (a \lor 1) \land 1) (\text{Identität})\\
&= (a \lor 1) \land (a \lor \overline{a}) (\text{Komplement})\\
&= (a \lor \overline{a}) \land (a \lor 1) (\text{Kommutativ})\\
&= a \lor (\overline{a} \land 1) (\text{Distributiv})\\
&= a \lor \overline{a}\\
&= 1 (\text{Komplement})
\end{align}
$$

2. Semantische Ebene
$$
a \lor 1
$$

|$a$|$1$|$a \lor 1$|
|---|---|----------|
|0  |1  |1         |
|1  |1  |1         |

### Die de Morgansche Regel
$$
\overline{a \land b} = \overline{a} \lor \overline{b}\\
\overline{a \lor b} = \overline{a} \land \overline{b}
$$

#### Schalttabelle
|$a$|$b$|$\overline{a}$|$\overline{b}$|$a \land b$|$\overline{a \land b}$|$\overline{a} \lor \overline{b}|
|---|---|--------------|--------------|-----------|----------------------|--------------------------------|
|0|0|1|1|0|1|1|
|0|1|1|0|0|1|1|
|1|0|0|1|0|1|1|
|1|1|0|0|1|0|0|

## Schaltfunktionen
### Definition
Eine Abbildung
$$
f: B^4 \rightarrow B\\
(a_1, \ldots, a_n) \rightarrow f(a_1, \ldots, a_n)
$$
heißt $n$-stellige binäre **Schaltfunktion**.  
Die technische Realisierung einer solchen Schaltfunktion heißt **Schaltung**.

### Einstellige Schaltfunktionen ($n = 1$)
Es gibt vier einstellige Schaltfunktionen.

|$a$|$f_1(a)$|$f_2(a)$|$f_3(a)$|$f_4(a)$|
|---|--------|--------|--------|--------|
|0  |0       |0       |1       |1       |
|1  |0       |1       |0       |1       |

Technische Realisierungen elementarer $\text{BOOLE}$scher Funktionen wie hier die $\text{NOT}$-Funktion, nennt man **Gatter**, hier **$\text{NOT}$-Gatter**.

### Zweistellige Schaltfunktionen
|$a$|$b$|$f(a, b)$|
|---|---|---------|
|0  |0  |0, 1     |
|0  |1  |0, 1     |
|1  |0  |0, 1     |
|1  |1  |0, 1     |

Es gibt 16 verschiedene 2-stellige $\text{BOOLE}$sche Funktionen.  
Generell, es gibt $2^{2^n}$ $n$-stellige $\text{BOOLE}$sche Funktionen.

Interessante Funktionen:

#### NAND-Funktion
|a|b|NAND(a, b)|
|-|-|----------|
|0|0|1         |
|0|1|1         |
|1|0|1         |
|1|1|0         |

#### NOR-Funktion
|a|b|NOR(a, b)|
|-|-|---------|
|0|0|1        |
|0|1|0        |
|1|0|0        |
|1|1|0        |

#### XOR-Funktion
|a|b|XOR(a, b)|
|-|-|---------|
|0|0|0        |
|0|1|1        |
|1|0|1        |
|1|1|0        |

#### COIN-Funktion (Coincidence)
|a|b|COIN(a, b)|
|0|0|1         |
|0|1|0         |
|1|0|0         |
|1|1|1         |

$COIN(a, b) = \overline{XOR(a, b)}$

Der Beweis, dass die Schaltalgebra ein Modell einer $\text{BOOLE}$schen Algebra ist, erfolgt über die Existenz zweier binärer Verknüpfungen &and; und &or; (und $\text{NOT}$).

&rarr; Sind diese 3 Operationen zum Entwrf beliebiger digitaler Schaltungen notwendig, oder kommt man mit weniger aus?

&rarr; Gibt es andere Operationen, welche den Bau von digitalen Schaltungen vereinfachen?

### Definition
Eine Menge $V$ von Verknüpfungen heißt **Verknüpfungsbasis** für eine Funktionsmenge $F$, wenn sich jede Funktion $f \in F$ mit Verknüpfungen $u \in V$ darstellen lässt.

z. B.:
$$
V = \{1, \lor, -\}
$$ ist Verknüpfungsbasis für $\{f_0, \ldots, f_15\}$

#### Behauptung
$v = \{NAND\}$ und $u = \{NOR\}$ sind Verknüpfungsbasis von $\{f_0, \ldots, f_15\}$.

#### Beweis
Da $\{\land, \lor, -\}$ eine Verknüpfungsbasis ist, genügt es zu zeigen, dass $\land, \lor, -$ durch $\text{NOR}$ ausgedrückt werden können.

##### NOT
$$
\overline{a} = \overline{a \lor a} = NOR(a, a)
$$

##### AND
$$
\begin{align}
a \land b &= \overline{\overline{a \land b}}\\
&= \overline{(\overline(a) \land \overline{b})}\\
&= NOR(\overline{a}, \overline{b})\\
&= NOR(NOR(a, a), NOR(b, b))
\end{align}
$$

##### OR
$$
\begin{align}
a \lor b &= (a \lor b) \land (a \lor b)\\
&= \overline{\overline{(a \lor b) \land (a \lor b)}}\\
&=
\end{align}
$$


In der Praxis verwendet man als Verknüpfungsbasis die Operationen $\land, \lor, -$.

### Realistisches Beispiel
In den praktischen, realen Problemen bei digitalen Schaltungen hat man in der Regel das Problem:  
Gegeben ist eine (logische) Schalttabelle, gesucht: $\text{BOOLE}$sche Funktion.

|$S_1$|$S_2$|$S_3$|Lampe = $f(S_1, S_2, S_3)$|
|-----|-----|-----|--------------------------|
|0    |0    |0    |0                         |
|0    |0    |1    |1                         |
|0    |1    |0    |1                         |
|0    |1    |1    |0                         |
|1    |0    |0    |1                         |
|1    |0    |1    |0                         |
|1    |1    |0    |0                         |
|1    |1    |1    |1                         |

#### Definition
Ein **Konjunktionsterm** einer $n$-stelligen $\text{BOOLE}$schen Funktion ist die $\text{AND}$-Verknüpfung aller Variablen in negierter oder nicht-negierter Form.  
Ein Konjunktionsterm, der den Wert $1$ annimmt, heißt **Minterm**.

Die $\text{OR}$-Verknüpfung aller Minterme liefert die **disjunktive Normalform** (DNF).

#### Beispiel
Betrachte die Belegungen mit Funktionsweit $= 1$.

$f_{DNF}(S_1, S_2, S_3) = (\overline{S_1} \land \overline{S_2} \land S_3) \lor (\overline{S_1} \land S_2 \land \overline{S_3}) \lor (S_1 \land \overline{S_2} \land \overline{S_3}) \lor (S_1 \land S_2 \land S_3)$

Hieraus kann direkt die Schaltung gebastelt werden, die die 3-stellige Funktion $f(S_1, S_2, S_3)$ durch elementare Gatter ausdrückt.

#### Konjunktive Normalform
Für die Konjunktive Normalform wählt man die 0er-Zeilen und konstruiert Maxterme, das sind alle $n$-Variable mit OR-verknüpft in negierter oder nicht-negierter Form.
