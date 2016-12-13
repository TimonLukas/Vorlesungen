# Session 8

## Vektorraum
### Definition
Sei $V$ ein Vektorraum und $B \subset V$.  
Ist $B$ eine maximal linear unabhängige Teilmenge, dann heißt $B$ **Basis** von $V$.

### Notation
$$
\begin{align}
&e_i := \text{i-ter Standardbasisvektor oder Einheitsvektor} \\
&e_i := \begin{bmatrix}0\\ \ldots\\ 1 \text{(i)}\\ \ldots\\ 0\end{bmatrix}
\end{align}
$$

### Beispiel
1. $$
\begin{align}
&V = \mathbb{R}^3 \\
&B = \left\{e_1, e_2, e_3, e_1 + e_2 \right\}
\end{align}
$$ &rarr; Keine Basis, da **nicht** linear unabhängig:  
$$
\vec{0} = 1 * e_1 + 1 * e_2 - 1 * (e_1 + e_2)
$$

2. $$
\begin{align}
&V = \mathbb{R}^3 \\
&B = \left\{ e_1, e_2 \right\}
\end{align}
$$ &rarr; Keine Basis, da nicht maximal.  
$$
B' = \left\{ e_1, e_2, e_3\right\} \supset B$$ und **linear abhängig**.

3. $$
\begin{align}
&V = \mathbb{R}^3 \\
&B = \left\{ e_1, e_2, e_3\right\}\\
\end{align}
$$ &rarr; Ist Basis linear unabhängig:  
Nehmen wir ein $v \in \mathbb{R}^3$ hinzu.
$$
\Rightarrow \vec{0} = -v_1 * e_1 - v_2 * e_2 - v_3 * e_3 + v
$$

### Satz
Sei $V$ ein Vektorraum und $B \subset V$.  
Dann ist $B$ genau dann eine Basis von $V$, wenn sich jedes $v \in V$ auf genau eine Art als Linearkombination von Elementen aus $B$ darstellen lässt.

### Beispiel
$$
\begin{align}
&V = \mathbb{R}^3\\
&B = \left\{ e_1 + e_2, e_1, e_3\right\}\\
\begin{bmatrix}5\\ 4\\ 3\end{bmatrix} &= \alpha (e_1 + e_2) + \beta e_1 + \gamma e_3\\
&= 4(e_1 + e_2) + 1 * e_1 + 3 * e_3
\end{align}
$$

**Angenommen**
$$
\begin{bmatrix}5\\ 4\\ 3\end{bmatrix} = a * (e_1 + e_2) + b * e_1 + c * e_3\\
\text{und} (a, b, c) \neq (\alpha, \beta, \gamma) = (4, 1, 3)
$$

$$
\begin{align}
\begin{bmatrix}5\\ 4\\ 3\end{bmatrix} - \begin{bmatrix}5\\ 4\\ 3\end{bmatrix} = \vec{0} &= \left[ e * (e_1 + e_2) + 1 * e_1 + 3 * e_3\right] - \left[ \alpha * (e_1 + e_2) + b * e_1 + c * e_3\right]\\
&= (4 - a) * (e_1 + e_2) + (1 - b) e_1 + (3 - c) * e_3
\end{align}$$ &rarr; Ist **nicht** triviale Darstellung der Null (Darf es nicht geben!) &rarr; Basis linear unabhängig

### Beispiel 2
$$
\begin{align}
&B = \left\{ e_1, e_2, e_3, e_1 + e_2\right\}\\
&\text{Nicht linear unabhängig: } e_1 + e_2 - (e_1 + e_2) = \vec{0}\\
&\begin{bmatrix}5\\ 4\\ 3\end{bmatrix} = 4 * (e_1 + e_2) + 1 * e_1 + 3 * e_3\\
&\begin{bmatrix}5\\ 4\\ 3\end{bmatrix} = 5 * e_1 + 4 * e_2 + 3 * e_3\\
\vec{0} = \begin{bmatrix}5\\ 4\\ 3\end{bmatrix} - \begin{bmatrix}5\\ 4\\ 3\end{bmatrix} &= (4 * (e_1 + e_2) + 1 * e_1 + 3 * e_3) - (5 * e_1 + e * e_2 + 3 * e_3)\\
&= 4 * (e_1 + e_2) + (1 - 5) * e_1 - 4 * e_2 + (3 * 3) * e_3\\
&= 4 * (e_1 + e_2) - 4 * e_1 - 4 * e_2 \\\\
&\vec{0} = (e_1 + e_2) - e_1 - e_2 \\\\
&\begin{bmatrix}5\\ 4\\ 3\end{bmatrix} = 4 * (e_1 + e_2) + 1 * e_1 + 3 * e_3 + \vec{0} \\
&= 4 * (e_1 + e_2) * e_1 + 3 * e_3 + \lambda \left[ (e_1 + e_2) - e_1 - e_2\right]
\end{align}
$$

### Definition
Sei $V$ ein Vektorraum und $B$ eine Basis mit $|B| = n$.  
Dann sagen wir: $V$ hat die Dimension $n$.

#### Bemerkung
Eine Basis ist nicht eindeutig. Die Dimension schon.

### Beispiele
$$
\begin{align}
&V = \mathbb{R}^3\\
&|B| = 3\\
&B_1 = \left\{ e_1, e_2, e_3\right\}\\
&B_2 = \left\{ e_1 + e_2, e_1, e_3\right\}\\
&B_3 = \left\{ e_1, e_2, e_2 + e_3\right\}
\end{align}
$$

## 7. Lineare Gleichungssysteme
1. Tag:
$2 \text{ Stifte} + 1 \text{ Block } = 1,90€; 1 \text{ Stift} + 3 \text{ Blöcke } = 1,20€$

$$
\begin{align}
&x := \text{Preis der Blöcke} \\
&y := \text{Preis der Stifte} \\\\
&I. x + 2y = 1,90\\
&II. 3x + y = 1,20\\\\
&I * 3 - II: 0x + 5y = 4,50\\
&\Rightarrow y = 0,90 \\
&\Rightarrow \text{in } I: x + 2 * 0,90 = 1,90 \Rightarrow x = 0,1
\end{align}
$$

2. Tag:
$1 \text{ Stift} + 3 \text{ Blöcke } = 1,20€$

3. Tag:
$2 \text{ Stifte} + 1 \text{ Block } = 1,50€$
$$
\begin{align}
&I. x + 2y = 1,90\\
&II. 3x + y = 1,20\\
&III. x + 2y = 1,50\\
&I - III: 0x + 0y = 0,40\\
&\Rightarrow \text{Unendlich viele Lösungen; die Informationen sind linear abhängig voneinander.}
\end{align}
$$

### 7.1 Einführung
$$
\begin{align}
&V = \mathbb{R}^3\\
&S = \text{SKL } \begin{bmatrix}1\\ 0\\ 0\end{bmatrix}, \begin{bmatrix}0\\ 1\\ 0\end{bmatrix}, \begin{bmatrix}1\\ 1\\ 0\end{bmatrix} \text{ SKR}\\
&v = \alpha * \begin{bmatrix}1\\ 0\\ 0\end{bmatrix} + \beta * \begin{bmatrix}0\\ 1\\ 0\end{bmatrix} + \gamma * \begin{bmatrix}1\\ 1\\ 0\end{bmatrix}\\\\
&\begin{bmatrix}1\\ 0\\ 1\end{bmatrix} \begin{bmatrix}1\\ 1\\ 0\end{bmatrix} \begin{bmatrix}0\\ 1\\ 0\end{bmatrix} \\\\
&B \text{ ist Basis}:\\
&\text{SKL } B \text{ SKR} = V
\end{align}
$$

### 7.2 Formalisierung
#### Definition
Seien $m, n \in \mathbb{N}$ und $\left\{ a_i, k\right\}_{i = 1, \ldots, m; k = 1, \ldots, n} \in \mathbb{R}$ und $\left\{ b_i\right\}_{i = 1, \ldots, m} \in \mathbb{R}$. Dann heißt ein Schema der Form

$$
\begin{align}
&a_{1,1} x_1 + a_{1,2} x_2 + a_{1, 3} x_3 + \ldots + a_{1, n} x_n = b_1\\
&a_{2,1} x_1 + a_{2,2} x_2 + a_{2, 3} x_3 + \ldots + a_{2, n} x_n = b_2\\
&\ldots \\
&a_{m,1} x_1 + a_{m,2} x_2 + a_{m, 3} x_3 + \ldots + a_{m, n} x_n = b_m\\
\end{align}
$$

ein **lineares Gleichungssysteme (LGS)** mit m **Gleichungen** und n **Variablen**.  
Die Zahlen $\left\{ a_{i, k} \right\}$ heißen **Koeffizienten**, und die Zahlen $\left\{ b_i \right\}$ heißen **Daten** oder **rechte Seite**.

Ein n-Tupel $(x_1, \ldots, x_n)$, das alle $m$-Gleichungen löst, heißt **Lösung des LGS**.

##### Elementare Schritte zum Lösen (3 Stück)
1. Vertauschen zweier Zeilen
2. Multiplikation einer Zeile mit $\lambda \neq 0$
3. Addition des Vielfachen einre Zeile auf eine andere

### Das Gauss-Verfahren
Ziel ist Dreiecksform:

$$
\begin{bmatrix}a & b & c\\ 0 & d & e\\ 0 & 0 & f\end{bmatrix}
$$

1. Betrachte die erste Spalte und vertausche die Zeilen (Elementarer Schritt 1), sodass gilt: $$
|a_{1, 1}| \geq |a_{1, k}| \qquad \forall \; k = 1, \ldots, n
$$

2. Führe Elementarschritt 3 aus:
$$
\text{Multipliziere 1. Zeile mit } - \frac{a_{i, 1}}{a_{1, 1}} \text{ und Addition auf die i-te Zeile}
$$
$$
\begin{align}
\Rightarrow &a_{1, 1} x_1 + a_{1, 2} x_2 + \ldots + a_{1, n} x_n = b_1 \\
&0 x_1 + a_{2, 2}' x_2 + a_{2, 3}' x_3 + \ldots + a_{2, n}' x_n = b_2 \\
&\ldots \\
&0 x_1 + a_{m, 2}' x_2 + a_{m, 3}' x_3 + \ldots + a_{m, n}' x_n = b_m'
\end{align}
$$
$$
\left( \text{Da gilt: }a_{i, k}' = a_{i, k} - a_{1, k} * \frac{a_{i, 1}}{a_{1, 1}} \right)
$$

3. Verwende das Verfahren für das reduzierte System


### Beispiele
#### 1.
1. $$
\begin{align}
-x + 2y + z &= 0\\
3x - 8y - 2z &= 0\\
x + 0y + 4z &= 1
\end{align}
$$

2. $$
\begin{align}
3x - 8y - 2z &= 0\\
-x + 2y + z &= 0\\
x + 0y + 4z &= 1
\end{align}
$$

3. $$
\begin{align}
3x - 8y - 2z &= 0\\
0x - \frac{2}{3}y + \frac{1}{3}z &= 0\\
0x - \frac{8}{3}y + \frac{14}{3}z &= 1
\end{align}
$$

4. $$
\begin{align}
3x - 7y - 2z &= 0\\
0x - \frac{8}{3}y + \frac{14}{3}z &= 1\\
0x - \frac{2}{3}y + \frac{1}{3}z &= 0
\end{align}
$$

5. $$
\begin{align}
3x - 8y - 2z &= 0\\
0x - \frac{8}{3}y + \frac{14}{3}z &= 1\\
0x + 0y - \frac{55}{12}z &= -\frac{1}{4}
\end{align}
$$

#### 2.
1. $$
\begin{align}
x + y + z &= 1\\
y - z &= 1\\
x + 2y &= 2
\end{align}
$$

2. $$
\begin{align}
x + y + z &= 1\\
y - z &= 1\\
y - z &= 1
\end{align}
$$

3. $$
\begin{align}
x + y + z &= 1\\
y - z &= 1\\
0 &= 0
\end{align}
$$


4. z. B. $$
\begin{align}
z &= t\\
y &= t + 1\\
x &= 1 - t - (1 + t)\\
&= -2t
\end{align}$$ &rarr; $\begin{bmatrix}-2t\\ t + 1\\ t\end{bmatrix}$ ist Lösung für $t \in \mathbb{R}$

5. $$
\begin{bmatrix}-2t\\ t + 1\\ t\end{bmatrix} = \begin{bmatrix}0\\ 1\\ 0\end{bmatrix} + t * \begin{bmatrix}-2\\ 1\\ 1\end{bmatrix}
$$ &rarr; **Allgemeine** Lösung = **Eine** Lösung + **allgemeine** Lösung des zugehörigen homogenen LGS

## 8. Matrizen
### 8.1 Lineare Abbildungen
#### Definition
Sind $V, W$ Vektorräume, dann ist eine Abbildung $f: V \to W$ eine **lineare Abbildung**, wenn gilt
1. $f(x + y) = f(x) + f(y) \; \forall \; x, y \in V$
2. $f(\lambda x) = \lambda f(x) \; \forall \; x \in V, \; \forall \; \lambda \in \mathbb{R}$

#### Beispiele
1. $$
\begin{align}
V &= \mathbb{R}^3\\
W &= \mathbb{R}^3\\
f((x_1, x_2)) &= (x_1, x_1 * x_2, x_3)\\
f((2, 3)) &= (2, 6, 3)\\
f((2, 1)) &= (2, 2, 1)\\
f((2, 3) + (2, 1)) &= f((4, 4)) = (4, 16, 4) \neq f((2, 3)) + f((2, 1)) = (4, 8, 4) \\
\Rightarrow &\color{red}{\text{Keine lineare Abbildung}}
\end{align}
$$

2. $$
\begin{align}
V &= \mathbb{R}^3\\
W &= \mathbb{R}^2\\
f((x_1, x_2, x_3)) &= (2 * x_2 + x_3, x_1 - x_2)
\end{align}
$$
##### Test
$$
\begin{align}
f((1, 2, 3)) &= (4 + 3, 1 - 2) = (7, -1)\\
f(5 * (1, 2, 3)) &= f((5, 10, 15)) = (20 + 15, 5- 10) = (35, -5)\\
5 * f((1, 2, 3)) &= 5 * (7, -1) = (35, -5)
\end{align}
$$
Zeige, dass dies eine lineare Abbildung ist
1. $$
\begin{align}
f((x_1, x_2, x_3) + (y_1, y_2, y_3)) &= f((x_1 + y_1, x_2 + y_2, x_3 + y_3))\\
&= (2 * (x_2 + y_2) + x_3 + y_3, x_1 + y_1 - x_2 - y_2)\\
f((y_1, y_2, y_3)) &= (2y_2 + y_3, y_1 - y_2)\\
f((x_1, x_2, x_3)) + f((y_1, y_2, y_3)) &= (2x_2 + x_3, x_1 - x_2) + (2y_2 + y_3, y_1 - y_2)\\
&= (2 * (x_2 + y_2) + x_3 + y_3, x_1 + y_1 - x_2 - y_2)
\end{align}
$$

2. $$
\begin{align}
&f(\lambda * (x_1, x_2, x_3)) = f((\lambda x_1, \lambda x_2, \lambda x_3))\\
= &(2 * \lambda x_2 + \lambda x_3, \lambda x_1 - \lambda x_2)\\
= &(\lambda * (2x_2 + x_3), \lambda * (x_1 - x_2))\\
= &\lambda (2x_2 + x_3, x_1 - x_2)\\
= &\lambda * f((x_1, x_2, x_3))
\end{align}
$$
