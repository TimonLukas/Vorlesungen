# Session 05

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Kongruenzrelation](#kongruenzrelation)
  * [Modulare Arithmetik](#modulare-arithmetik)
    * [Beispiel](#beispiel)
    * [Weiteres Beispiel](#weiteres-beispiel)
    * [Satz](#satz)
    * [EUKLIDischer Algorithmus](#euklidischer-algorithmus)
      * [Fußweg](#fußweg)
      * [Allgemeiner erweiterter EUKLID](#allgemeiner-erweiterter-euklid)
        * [Initialisierung](#initialisierung)
        * [Denksport-Aufgabe](#denksport-aufgabe)
        * [Rechnen mit % n](#rechnen-mit-n)
        * [Übung](#übung)
        * [Übung](#übung-1)
        * [Noch ne Übung](#noch-ne-übung)
    * [Algorithmus **fastexp**](#algorithmus-fastexp)
    * [Satz](#satz-1)
      * [Beweis](#beweis)

<!-- tocstop -->

## Kongruenzrelation

$$
x \equiv y\;\%\;n
$$
Definiert auf $\mathbb{Z}$ eine Äquivalenzrelation mit den Äquivalenzklassen (Restklassen)

$$
[i] = \{x \in \mathbb{Z}\vert x \equiv i\;\%\;n\}
$$

Die Menge aller Restklassen ist
$$
\begin{align}
\mathbb{Z}_n &= \{[0], \ldots, [n - 1]\}\\
&= \{0, \ldots, n - 1\}
\end{align}
$$

### Modulare Arithmetik
* $\oplus$: $\mathbb{Z}_n \times \mathbb{Z}_n \rightarrow \mathbb{Z}_n [a] \oplus [b]$  
$([a], [b]) \rightarrow [c], c = (a + b) \;\%\; n$

* $\otimes$: $\mathbb{Z}_n \times \mathbb{Z}_n \rightarrow \mathbb{Z}_n$  
$([a], [b]) \rightarrow [c] = [a] \otimes [b] = (a * b) \;\%\; n$

#### Beispiel
Auf $\mathbb{Z}_5$ kann man addieren, subtrahieren, multiplizieren und dividieren

$(\mathbb{Z}_5, \oplus, \otimes)$ hat die algebraische Struktur eines endlichen Körpers

#### Weiteres Beispiel

|$\mathbb{Z}_9$ |0|1|2|3|4|5|6|7|8|
|---------------|-|-|-|-|-|-|-|-|-|
|**0**          |0|0|0|0|0|0|0|0|0|
|**1**          |0|1|2|3|4|5|6|7|8|
|**2**          |0|2|4|6|8|1|3|5|7|
|**3**          |0|3|6|0|3|6|0|3|6|
|**4**          |0|4|8|3|7|2|6|1|5|
|**5**          |0|5|1|6|2|7|3|8|4|
|**6**          |0|6|3|0|6|3|0|6|3|
|**7**          |0|7|5|3|1|8|6|4|2|
|**8**          |0|8|7|6|5|4|3|2|1|

$3 * 2 \equiv 6 \;\%\;9$  
$12 * 11 = 132 = 14 \text{ Rest } 6$

Daher ist es **sehr** zweckmäßig:
$$
(a * b) \;\%\;n = \big[(a \;\%\; n) * (b \;\%\; n)\big] \;\%\; n
$$


Zurück zu $\mathbb{Z}_9$: Gibt es zu jedem $a \in \mathbb{Z}_9 \text{ außer } 0$ ein $a^{-1} \in \mathbb{Z}_9$ mit $a = a^{-1} \equiv 1 \;\%\; 9$?

$a^{-1}$ = multiplikatives Inverses

Es klappt bei $a = 1, 2, 4, 5, 7, 8$. Es klappt nicht bei $a = 3, 6$.  
D. h. auf $\mathbb{Z}_9$ kann man **nicht** beliebig dividieren!

#### Satz
Falls $n = p$ eine Primzahl ist, dann hat $(\mathbb{Z}_p, \oplus, \otimes)$ die Struktur eines endlichen Körpers, insbesondere existiert für jedes $a \in \mathbb{Z}_p, a \neq 0$ ein $a^{-1} \in \mathbb{Z}_p$ mit $a * a^{-1} \equiv 1 \;\%\;p$.

Falls $n$ eine zusammengesetzte Zahl ist, dann gilt:
$$
a^{-1} \in \mathbb{Z}_n \text{ existiert } \Leftrightarrow \text{ ggT}(a, n) = 1
$$


Also:
$$
a = 1, 2, 4, 5, 7, 8 \rightarrow \text{ ggT}(a, 9) = 1
$$
aber
$$
a = 3, 6 \rightarrow \text{ ggT}(a, 9) \neq 1
$$

Nächste Frage: Wie erhält man $a^{-1} \;\%\;n$?  
Z. B. $510 * x \equiv 1 \;\%\; 1001$?

1. Möglichkeit: Ma nerstellt eine $1001 \times 1001$-Tabelle, berechnet $a * b \;\%\;1001$ und geht in die $510$te Zeile, liest ab, wo die $1.$ steht.
2. Besseres Verfahren: Der erweiterte $\text{EUKLID}$ische Algorithmus

#### EUKLIDischer Algorithmus
##### Fußweg
Berechne $510^{-1} \;\%\; 1001$, d. h. berechne $x \in \mathbb{Z}_{1001}$ mit $510 * x \equiv 1 \;\%\; 1001$

1. Schritt: Dividiere $1001$ durch $510$:
$$
1001 = 1 * 510 + 491
$$
Drücke (immer) den Rest durch $1001$ und $510$ aus:
$$
491 = 1 * 1001 - 1 * 510
$$

2. Schritt: Dividiere $510$ durch $491$:
$$
\begin{align}
510 &= 1 * 491 + 19\\
19 &= 510 - 1 * 491\\
&= 510 - 1 * (1 * 1001 - 1 * 510)
\end{align}
$$

3. Schritt: Dividiere $491$ durch $19$:
$$
\begin{align}
491 &= 25 * 19 + 16\\
16 &= 491 - 25 * 19\\
&= 1 * 1001 - 1 * 510 - 25 * (-1 * 1001 + 2 * 510)\\
&= 26 * 1001 - 51 * 510
\end{align}
$$

4. Schritt: Dividiere $19$ durch $16$
$$
\begin{align}
19 &= 1 * 16 + 3\\
3 &= 19 - 1 * 16\\
&= (-1) * 1001 + 2 * 510 - (26 * 1001 - 51 * 510)\\
&= -27 * 1001 + 53 * 510
\end{align}
$$

5. Schritt:
$$
16 = 5 * 3 + 1\\
1 = 16 - 5 * 3\\
= 26 * 1001 - 51 * 510 - 5 * (-27 * 1001 + 53 * 510)\\
= 161 * 1001 - 316 * 510
$$

Also:
$$
1 = 161 * 1001 - 316 * 510
$$
oder:
$$
-316 * 510 = 1 - 161 * 1001
$$
oder:
$$
-316 * 510 \equiv 1 \;\%\; 1001
$$
oder:
$$
685 * 510 \equiv 1 \;\%\;1001
$$
damit:
$$
685 \equiv 510^{-1} \;\%\; 1001
$$

**Check**: $685 * 510 = 349 350 = 349 * 1001 + 1$

##### Allgemeiner erweiterter EUKLID
Input: Zwei natürliche Zahlen $a, n$ ohne Beschränkung der Allgemeinheit, $a < n$.  
Hilfsvariablen:
$$
x_1, x_2, x_3\\
y_1, y_2, y_3\\
T_1, T_2, T_3, Q
$$

###### Initialisierung
Setze:
* $x_1 = 1$
* $x_2 = 0$
* $x_3 = n$
* $y_1 = 0$
* $y_2 = 1$
* $y_3 = a$

**Iteration**:
* Falls $y_3 == 0$ STOP. Output $x_3 = \text{ ggT}(a, n)$, kein Inverses.
* Falls $y_3 == 1$ STOP. Output $y_2 = a^{-1}\;\%\;n$.
* Sonst $Q = \lfloor\frac{x_3}{y_3}\rfloor$ ($\lfloor\rfloor$ = größte ganze Zahl $\leq x$)  
$T_1 = x_1 - Q * y_1$  
$T_2 = x_2 - Q * y_2$  
$T_3 = x_3 - Q * y_3$  
Setze: $x_1 = y_1, x_2 = y_2, x_3 = y_3, y_1 = T_1, y_2 = T_2, y_3 = T_3$

**Beispiel**:  
Berechne $510^{-1} \;\%\; 1001$.  
Input $a = 510, n = 1001$.
* $x_1 = 1$
* $x_2 = 0$
* $x_3 = 1001$
* $y_1 = 0$
* $y_2 = 1$
* $y_3 = 510$

$y_3 = 0$? $y_3 = 1$? Nö.

$$
Q = \lfloor\frac{x_3}{y_3}\rfloor = \lfloor\frac{1001}{510}\rfloor
$$

* $T_1 = x_1 - Q * y_1 = 1$
* $T_2 = x_2 - Q * y_2 = -1$
* $T_3 = x_3 - Q * y_3 = 1001 - 510 = 451$
* $x_1 = 0$
* $x_2 = 1$
* $x_3 = 510$
* $y_1 = 1$
* $y_2 = -1$
* $y_3 = 491$

$y_3 = 0$? $y_3 = 1$? Nä.

$$
Q = \lfloor\frac{x_3}{y_3}\rfloor = \lfloor\frac{510}{451}\rfloor
$$

* $T_1 = x_1 - Q * y_1 = -1$
* $T_2 = x_2 - Q * y_2 = 2$
* $T_3 = x_3 - Q * y_3 = 19$
* $x_1 = 1$
* $x_2 = -1$
* $x_3 = 491$
* $y_1 = -1$
* $y_2 = 2$
* $y_3 = 19$

$y_3 = 0$? $y_3 = 1$? Nü.

$$
Q = \lfloor\frac{x_3}{y_3}\rfloor = \lfloor\frac{451}{19}\rfloor
$$

* $T_1 = x_1 - Q * y_1 = 26$
* $T_2 = x_2 - Q * y_2 = -51$
* $T_3 = x_3 - Q * y_3 = 16$
* $x_1 = -1$
* $x_2 = 2$
* $x_3 = 19$
* $y_1 = 26$
* $y_2 = -51$
* $y_3 = 16$

$y_3 \neq 0, 1$

$$
Q = \lfloor\frac{x_3}{y_3}\rfloor = \lfloor\frac{19}{10}\rfloor = 1
$$

* $T_1 = x_1 - Q * y_1 = -27$
* $T_2 = x_2 - Q * y_2 = 53$
* $T_3 = x_3 - Q * y_3 = 3$
* $x_1 = 26$
* $x_2 = -51$
* $x_3 = 16$
* $y_1 = -27$
* $y_2 = 53$
* $y_3 = 3$

$y_3 \neq 0, 1$

$$
Q = \lfloor\frac{x_3}{y_3}\rfloor = \lfloor\frac{16}{3}\rfloor = 5
$$

* $T_1 = x_1 - Q * y_1 = 26 - 5 * (-27) = 161$
* $T_2 = x_2 - Q * y_2 = -51 - 5 * 53) = 316$
* $T_3 = x_3 - Q * y_3 = 1$
* $x_1 = -27$
* $x_2 = 53$
* $x_3 = 3$
* $y_1 = 161$
* $y_2 = -316$
* $y_3 = 1$

$y_3 == 1 \Rightarrow$ STOP $y_2 = -316 \equiv 685 \Rightarrow$ ist $510^{-1}\;\%\;1001$


###### Denksport-Aufgabe
Wenn der erweiterte $\text{EUKLID}$ terminiert, steht in der $y_2$-Variable $a^{-1} \;\%\;n$. Was steht in der $y_1$-Variable?

Dort steht $n^{-1} \;\%\;a$.

Wir hatten
$$
1 = 161 * 1001 - 316 * 510\\
-316 * 510 = -161 * 1001 + 1\\
\equiv 1 \;\%\;1001
$$
$$
161 * 1001 = 316 * 510 + 1\\
\equiv 1 \;\%\; 510
$$


###### Rechnen mit % n
Es gibt: $(a \pm b) \;\%\; n = \big[(a \;\%\; n) \pm (b \;\%\; n)\big] \;\%\; n$  
und $(a * b) \;\%\; n = \big[(a \;\%\; n) * (b \;\%\; n)\big] \;\%\; n$

**Beispiel**:
$$
13 * 17 \;\%\; 11 = 221 \;\%\; 11 \equiv 1 \;\%\; 11
$$

Rechte Seite:
$$
\big[(13 \;\%\; 11) * (17 \;\%\; 11)\big] \equiv (2 * 6) \;\%\; 11 \equiv 1 \;\%\; 11
$$

Das ist insbesondere bei der modularen Exponentiation sehr hilfreich. Strategie ist immer, durch $(a * b) \;\%\; n = \big[(a \;\%\; n) * (b \;\%\; n)\big] \;\%\; n$ muss man höchstens mit Zahlen der Größe $(n - 1) * (n - 1)$ rechnen.

###### Übung
$$
Z = 2^{1234} \;\%\; 789
$$

1. Schritt: Zerlege den Exponenten in eine Summe von $2$er-Potenzen:
$$
1234 = 1024 + 128 + 64 + 16 + 2
$$

$$
\begin{align}
2^{1234} \;\%\; 789 &= (2^{1024 + 128 + 64 + 16 + 2}) \;\%\; 789\\
&= (2^{1024} * 2^{128} * 2^{64} * 2^{16} * 2) \;\%\; 789\\
&= \big[(2^{1024} \;\%\; 789) * (2^{128} \;\%\;789) * (2^{64} \;\%\; 789) * (2^{16} \;\%\; 789) * (2 \;\%\; 789)\big] \;\%\; 789
\end{align}
$$

###### Übung
Berechnen Sie $3^{35} \;\%\; 11$.

$$
\begin{align}
3^{35} \;\%\; 11 &= (3^{32} + 3^2 + 3) \;\%\; 11\\
&= \big[(3^{32} \;\%\; 11) * (3^2 \;\%\; 11) * (3 \;\%\; 11)\big] \;\%\; 11
\end{align}
$$

**Nebenrechnung**:
* $3^2 \;\%\; 11 \equiv 9 \;\%\; 11$
* $3^4 \;\%\; 11 \equiv 81 \;\%\; 11 \equiv 4 \;\%\; 11$
* $3^8 \;\%\; 11 \equiv 16 \;\%\; 11 \equiv 5 \;\%\; 11$
* $3^{16} \;\%\; 11 \equiv 25 \;\%\; 11 \equiv 3 \;\%\; 11$
* $3^{32} \;\%\; 11 \equiv 9 \;\%\; 11$

$$
\begin{align}
&\equiv (9 * 9 * 3) \;\%\; 11\\
&\equiv (4 * 3) \;\%\; 11\\
&\equiv 1 \;\%\; 11
\end{align}
$$

###### Noch ne Übung
$$
2^{53} \;\%\; 7 \equiv ? \;\%\; 7\\
2^{53} = 2^{32} + 2^{16} + 2^4 + 2
$$

**Nebenrechnung**:
* $2^2 \;\%\; 7 \equiv 4 \;\%\; 7$
* $2^4 \;\%\; 7 \equiv 2 \;\%\; 7$
* $2^8 \;\%\; 7 \equiv 4 \;\%\; 7$
* $2^{16} \;\%\; 7 \equiv 2 \;\%\; 7$
* $2^{32} \;\%\; 7 \equiv 4 \;\%\; 7$

$$
\begin{align}
\equiv& (4 * 2 * 2 * 2) \equiv 7\\
\equiv& 4 \equiv 7
\end{align}
$$


#### Algorithmus **fastexp**
Der folgende Algorithmus berechnet $\text{fastexp } = x^y \;\%\; n$.

Input: Drei Zahlen $x, y, n > 0$, natürliche Zahlen.  
Drei Hilfsvariablen $a, b, c$.  

Initialisierung:  
Setzte $a = x, b = 1, c = y$.  
Falls $c$ gerade, setze $a = a^2 \;\%\; n, b = b, c = \frac{c}{2}$  
Falls $c$ ungerade, setze $a = a, b = (a * b) \;\%\; n, c = c - 1$  
Falls $c \neq 0$, gehe zum Anfang, sonst STOP.

Output: $b = \text{ fastexp } = x^y \;\%\; n$

#### Satz
Der Algorithmus **Modulare Exponentiation** terminiert und ist korrekt.

##### Beweis
1. Der Algorithmus terminiert, wenn $c = $ ist.  
Jeder Zwischenschritt reduziert den Wert von $c$:
$$
c = \frac{c}{2} \lor c = c - 1
$$

Damit terminiert der Algorithmus für alle Instanzen, d. h. beliebiger Wert von $c$.

2. Der Algorithmus ist korrekt, d. h. er liefert das Ergebnis $b = x^y \;\%\; n$.  
Beweis über Induktion (Schleifenvariante):
$$
b * a^c \;\%\; n = x^y \;\%\; n
$$

a) Induktionsanfang  
$$
a = x, b = 1, c = y (b * a^c \;\%\; n = x^y \;\%\; n)
$$

b) Induktionshypothese  
Der Algorithmus hat $m$ Runden durchlaufen und vor Eintritt in die $m + 1$ Runde:
$$
a = a', b = b', c = c' (b' * a'^{c'} \;\%\; n = x^y \;\%\; n)
$$

c) Induktionsschluss  
Die Schleife wird zum $m + 1$ten Mal durchlaufen  
i) $c'$ gerade:
$$
a = (a')^2 \;\%\; n\\
b = b'\\
c = \frac{c'}{2}\\
b * a^c \;\%\; n = b'(a'^2)^{\frac{c'}{2}} \;\%\; n\\
= b' (a')^{c'} \;\%\; n\\
= \text{ HYPOTHESE } x^y \;\%\; n
$$
ii) $c'$ ungerade:  
$$
a = a'\\
b = (a'b') \;\%\; n\\
c = c' - 1\\
\begin{align}
b * a^c \;\%\; n &= (a'b')(a')^{c'-1} \;\%\; n\\
&= b'a'^{c'} \;\%\; n\\
&= y^y \;\%\; n
\end{align}
$$

$$
c = 0, b = b * a^0 \;\%\; n = x^y \;\%\; n
$$
