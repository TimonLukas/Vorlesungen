# Session 04

## Kongruenzen

$$
x \equiv y\;\%\;n \text{ heißt:}
$$

1. $x - y$ wird ohne Rest durch $n \in \mathbb{N}$ geteilt
2. $x - y = k * n\;(k \in \mathbb{Z})$ (oder $x = y + kn$)
3. $x$ und $y$ haben den gleichen Rest, wenn sie durch $n \in \mathbb{N}$ geteilt werden.

Die Kongruenzrelation $x \equiv y\;\%\;n$ ist eine Äquivalenzrelation, d. h. sie ist reflexiv, symmetrisch und transitiv.

Die Äquivalenzklassen dieser Äquivalenzrelation nennt man **Restklassen**.

### Restklassen
#### Beispiel
Restklassen von $x \equiv y\;\%\;5$:

$$
\begin{align}
[0] &= \{x \in \mathbb{Z} \vert (x, 0) \in R\}\\
&= \{x \in \mathbb{Z} \vert x \equiv 0\;\%\;5\}\\
&= \{x \in \mathbb{Z} \vert x = k * 5 + 0, k \in \mathbb{Z}\}\\
&= \{\ldots, -15, -10, -5, 0, 5, 10, 15, \ldots\}
\end{align}
$$

$$
\begin{align}
[1] &= \{x \in \mathbb{Z} \vert x \equiv 1\;\%\;5\}\\
&= \{x \in \mathbb{Z} \vert x = k * 5 + 1, k \in \mathbb{Z}\}\\
&= \{\ldots, -14, -9, -4, 1, 6, 11, 16, \ldots\}
\end{align}
$$

$$
[2] = \{\ldots, -13, -8, -3, 2, 7, 12, 17, \ldots\}
$$

$$
[3] = \{\ldots, -12, -7, -2, 3, 8, 13, 18, \ldots\}
$$

Dies ist eine Partitionierung der Menge der ganzen Zahlen $\mathbb{Z}$, d. h.:
$$
[0] \cap [1] = \emptyset
$$

Daraus folgt:

$$
[0] \cup [1] \cup \ldots \cup [5] = \mathbb{Z}
$$

Analog zerfällt die Menge $\mathbb{Z}$ in $n$ Restklassen für die Kongruenzrelation $x \equiv y\;\%\;n$:

$$
[i] = \{x \in \mathbb{Z} \vert x \equiv i \;\%\; n\}
$$

Man bezeichnet mit
$$
\mathbb{Z}_n = \{[0], [1], \ldots, [n - 1]\} \text{ für } n \in \mathbb{N}, n > 1
$$
die Menge der Restklassen für $\text{mod } n$.

### Sinn
Arithmetik auf $\mathbb{Z}_n$ ist die Grundlage heutiger Public-Key-Verfahren.

Es gibt heute zwei grundlegend verschiedene Verschlüsselungsvefahren:
* Symmetrische Verschlüsselung
* Public-Key-Verfahren, asymmetrische Verschlüsselung.

### Operationen
* $\oplus$: Modulare Addition
$$
\mathbb{Z}_n \times \mathbb{Z}_n \rightarrow \mathbb{Z}_n\\
(a, b) \rightarrow (a + b) \;\%\; n
$$
* $\otimes$: Modulare Multiplikation
$$
\mathbb{Z}_n \times \mathbb{Z}_n \rightarrow \mathbb{Z}_n\\
a, b \rightarrow a \otimes b = (a * b) \;\%\; b
$$

#### Beispiel
$$
\mathbb{Z}_5 = \{0, 1, 2, 3, 4\}
$$

|$(a + b) \;\%\; 5$|0|1|2|3|4|
|------------------|-|-|-|-|-|
|**0**             |0|1|2|3|4|
|**1**             |1|2|3|4|0|
|**2**             |2|3|4|0|1|
|**3**             |3|4|0|1|2|
|**4**             |4|0|1|2|3|

Diese Tabelle zeigt folgendes:
* Zeile/Spalte 1: $a \oplus 0 = a$. D. h. 0 ist neutrales Element der Addition $\%\;5$.
* Für alle $a \in \mathbb{Z}_5$ existiert ein $b \in \mathbb{Z}_5$ mit:
$$
a \oplus b = 0\\
0 \oplus 0 = 0\\
1 \oplus 4 = 0\\
2 \oplus 3 = 0\\
3 \oplus 2 = 0\\
4 \oplus 1 = 0
$$


|$(a * b) \;\%\; 5$|0|1|2|3|4|
|------------------|-|-|-|-|-|
|**0**             |0|0|0|0|0|
|**1**             |0|1|2|3|4|
|**2**             |0|2|4|1|3|
|**3**             |0|3|1|4|2|
|**4**             |0|4|3|2|1|

Diese Tabelle zeigt folgendes:
* $1$ ist ein neutrales Element der Multiplikation (Zeile 2 / Spalte 2)
* Zu jedem $a \in \mathbb{Z}_5, a \neq 0$ existiert ein $a^{-1} \in \mathbb{Z}_5$ mit
$$
a * a^{-1} \equiv 1\;\%\;5\\
1 * 1 \equiv 1\;\%\;5\\
2 * 3 \equiv 1\;\%\;5\\
3 * 2 \equiv 1\;\%\;5\\
4 * 4 \equiv 1\;\%\;5
$$

$a^{-1}$ heißt multiplikatives Inverses von $a$!
$$
a * a^{-1} = 1\;\%\;5
$$

Auf $\mathbb{Z}_5$ kann man mit $a + b\;\%\;5$ und $a * b\;\%\;5$
* Addieren
* Subtrahieren
* Multiplizieren
* Dividieren

#### XOR
$a + b \;\%\;2$:

|     |0|1|
|-----|-|-|
|**0**|0|1|
|**1**|1|0|
