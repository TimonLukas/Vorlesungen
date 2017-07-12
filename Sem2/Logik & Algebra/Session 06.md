# Session 06

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Die EULER-Totientenfunktion $\phi(n)$](#die-euler-totientenfunktion-phin)
* [RSA (WINK MIT DEM ZAUNPFAHL)](#rsa-wink-mit-dem-zaunpfahl)
  * [Übung](#übung)
  * [Übung](#übung-1)
* [Kleiner Satz von FERMAT](#kleiner-satz-von-fermat)
  * [Andere Anwendung](#andere-anwendung)
  * [Restesatz](#restesatz)
* [BOOLESCHE ALGEBRA](#boolesche-algebra)
  * [Definition](#definition)
  * [Beispiele](#beispiele)

<!-- tocstop -->

## Die EULER-Totientenfunktion $\phi(n)$
$\phi(n)$ ist die Anzahl der Zahlen $a, 1 \leq a \leq n$ mit $\text{ ggT}(a, n) = 1$. (Man nennt solche Zahlen $a, n, m \text{ ggT}(a, n)$ "copium", teilerfremd).

$\mathbb{Z}_g$, für $a = 1, 2, 4, 5, 7, 8$ gilt: $\text{ ggT}(a, 9) = 1 \Rightarrow \phi(9) = 6$

Falls $p$ eine Primzahl ist, gilt:
$$
\phi(p) = p - 1
$$

|n    |$\phi(n)$|n    |$\phi(n)$|n    |$\phi(n)$|
|-----|---------|-----|---------|-----|---------|
|1    |1        |11   |10       |21   |12       |
|2    |1        |12   |4        |22   |10       |
|3    |2        |13   |12       |23   |22       |
|4    |2        |14   |6        |24   |8        |
|5    |4        |15   |8        |25   |20       |
|6    |2        |16   |8        |26   |         |
|7    |6        |17   |16       |27   |         |
|8    |4        |18   |6        |28   |         |
|9    |6        |19   |18       |29   |28       |
|10   |4        |20   |8        |30   |         |

Es gilt:  
Wenn $\text{ ggT}(n, m) = 1 \Rightarrow \phi(n) * \phi(m) = \phi(n * m)$

**Folgerung**:  
Seien $p, q$ zwei Primzahlen und $n = p * q$. Dann gilt:
$$
\phi(n) = \phi(p * q) = \phi(p) * \phi(q) = (p - 1) * (q - 1)
$$

$\phi(n) = (p - 1) * (q - 1)$ sagt aus, für wieviel der $n$ Zahlen $1, \ldots, n$ existiert ein multiplikatives Inverses.

Damit können wir den RSA-Algorithmus untersuchen.

## RSA (WINK MIT DEM ZAUNPFAHL)
### Übung
$$
p = 13, q = 17, e = 19
$$

Verschlüsseln Sie $42$, und entschlüsseln Sie.

$$
p * q = 221\\
\phi(n) = 12 * 16 = 192\\
e = 19, d = 19^{-1} \;\%\; 192 = 91\\
k_{pub} = (19, 221)\\
$$

### Übung
Berechnen Sie:
* $4^{10} \;\%\; 11 \equiv 1$
* $7^{18} \;\%\; 19 \equiv 1$
* $4^6 \;\%\; 7 \equiv 1$
* $6^{12} \;\%\; 13 \equiv 1$

## Kleiner Satz von FERMAT
Sei $p$ eine Primzahl und $a \in \mathbb{Z}_p$, dann gilt
$$
a^{p - 1} \equiv 1 \;\%\; p
$$

Äquivalenz dazu: $a^p \equiv a \;\%\; p$

Dies nutzt man folgendermaßen: Sei $p$ eine zufällig erzeugte 512-Bit-Zahl. Wenn für ~50 verschiedene $a$ gilt:
$$
a^p \equiv a \;\%\; p
$$
dann ist $p$ mit hoher Wahrscheinlichkeit eine Primzahl.  
Primzahltest von  RABIN-MILLER SOLOVAY-STRASSEN

### Andere Anwendung
Ein bayrischer Bauer will seine Kühe auf dem Volksfestzug präsentieren. Stellt er die Kühe in 3er-Reihen auf, bleiben 2 Kühe übrig. Stellt er sie in 4er-Reihen auf, bleibt eine Kuh übrig. Erst wenn er sie in 7er-Reihen aufstellt, bleibt keine Kuh mehr übrig.

Wie viele Kühe hat der Bauer?

* $x = 2 \;\%\; 3$
* $x = 1 \;\%\; 4$
* $x = 0 \;\%\; 7$

Dies sind sogenannte **simultane Kongruenzen**.

### Restesatz
Gegeben:
* $x \equiv a \;\%\; m$
* $x \equiv b \;\%\; n$

und $\text{ggT}(m, n) = q = u * m + v * n$.

## BOOLESCHE ALGEBRA
### Definition
Sei $B$ eine Menge mit $|B| \geq 2$.
$$
\begin{align}
\lor: &B \times B \rightarrow B\\
&(a, b) \rightarrow a \lor b \text{ Boolesche Summe}
\end{align}
$$
und
$$
\begin{align}
\land: &b \times B \rightarrow B\\
&(a, b) \rightarrow a \land b \text{ Boolesches Produkt}
\end{align}
$$

Zwei binäre Operationen auf $B$ und
$$
\begin{align}
\_ :  &B \rightarrow B\\
&a \rightarrow \bar{a} \text{ (Boolesches Komplement)}
\end{align}
$$
eine unäre Operation.

Das Tripel $(B, \land, \lor)$ heißt $\text{BOOLE}$sche Algebra, wenn gilt:
1. Kommutativgesetzte  
$\forall a, b \in B: a \lor b = b \lor a; a \land b = b \land a$
2. Distributivgesetze:  
$\forall a, b, c \in B: a \land (b \lor c) = (a \land b) \lor (a \land c);\\
a \lor (b \land c) = (a \lor b) \land (a \lor c)$  
3. Neutrale Elemente  
$\forall a \in B \exists 0 \in B \text{ mit} a \lor 0 = a$  
$\forall a \in B \exists 1 \in B \text{ mit} a \land 1 = a$
4. Komplementgesetzte  
$\forall a \in B \exists \bar{a} \in B \text{ mit}\\
a \land \bar{a} = 0\\
a \lor \bar{a} = 1$

Also eine Menge $B$ mit zwei 2-stelligen und einer 1-stelligen Verknüpfung, wobei die Axiome 1-4 gelten, heißt Boolesche Algebra. ($\text{HUNTINGTON}$sche Axiome)

Beachte: Falls
$$
(B, \land, \lor, -, 1, 0)
$$
eine $\text{BOOLE}$sche Algebra ist, dann ist auch
$$
(B, \lor, \land, -, 0, 1)
$$
eine $\text{BOOLE}$sche Algebra (Duale Algebra).

### Beispiele
Sei $T_{30} = \{1, 2, 3, 5, 6, 10, 15, 30\}$ die Menge aller Teiler von $30$.

$\land$: $\text{BOOLE}$sches Produkt  
$\lor$: $\text{BOOLE}$sche Summe  
$-$: $\text{BOOLE}$esches Komplement  
$a \land b = \text{ ggT}(a, b)$  
$a \lor b = \text{ kgV}()a, b)$  
$\bar{a} = \frac{30}{a}$

Hier gilt z. B.:
* $\overline{2 \lor 3} = \frac{30}{2 \lor 3} = \frac{30}{\text{kgV}(2, 3)} = \frac{30}{6} = 5$
* $\overline{2} \land \overline{3} = \frac{30}{2} \land \frac{30}{3} = 15 \land 10 = \text{ ggT}(15, 10)$
