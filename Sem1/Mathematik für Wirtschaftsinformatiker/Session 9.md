# Session 9

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Lineare Abbildung](#lineare-abbildung)
- [8.2 Einführung in Matrizen](#82-einführung-in-matrizen)
	- [Verwendung der Standardbasis](#verwendung-der-standardbasis)
		- [Beispiel](#beispiel)
		- [Beispiel](#beispiel)
- [8.3 "Rechnen mit Matrizen"](#83-rechnen-mit-matrizen)
	- [Beispiel](#beispiel)
- [8.4 Matrixmultiplikation](#84-matrixmultiplikation)
	- [Beispiel](#beispiel)
- [8.5 Bestimmung einer Inversen](#85-bestimmung-einer-inversen)
	- [Definition](#definition)
	- [Beispiel](#beispiel)
	- [Probe](#probe)
	- [Beispiel E2](#beispiel-e2)
- [8.6 Eigenwerte und Eigenvektoren](#86-eigenwerte-und-eigenvektoren)
	- [Definition](#definition)
	- [Beispiel](#beispiel)
	- [Skizze](#skizze)

<!-- /TOC -->

## Lineare Abbildung
1. $f(x) + f(y) = f(x + y) \; \forall \; x, y \in V$
2. $f(\lambda x) = \lambda * f(x) \; \forall \; x \in V, \; \forall \; \lambda \in \mathbb{R}$

## 8.2 Einführung in Matrizen
Sind $V, W$ Vektorräume und $\{v_1, \ldots, v_m\}$ ist eine Basis von $V$ und $\{y_1, \ldots, y_n\}$ ist eine Basis von $W$. Sei $f$ eine lineare Abbildung $f: V \to W$.  
Dann ist $$
f(v_j) = \sum_{i = 1}^n a_{i, j} y_i
$$

$$
\begin{align}
&v \in V\\
&\Rightarrow v = \sum_{j = 1}^n \beta_j v_j
\end{align}
$$

$$
\begin{align}
f(v) &= f\left( \sum_{j = 1}^m \beta_j v_j\right) = \sum_{j = 1}^m f(\beta_j v_j)\\
&= \sum_{j = 1}^m \beta_j f(v_j)\\
&= \sum_{j = 1}^m \beta_j * (\sum_{i = 1}^n a_{i, j} y_i)\\
&= \sum_{i = 1}^n (\sum_{j = 1}^m a_{i, j} \beta_j) y_i
\end{align}
$$

$$
A = \begin{bmatrix}a_{1, 1} & a_{1, 2} & a_{1, 3} & \ldots & a_{1, m}\\ a_{2, 1}\\ \ldots \\ a_{n, 1} & \ldots & \ldots & \ldots & a_{n, m}\end{bmatrix} \in \mathbb{R}^{n \times m}
$$

ist eine **Matrix** mit $n$ Zeilen und $m$ Spalten.

### Verwendung der Standardbasis
$$
\begin{align}
&v_j = e_j = \begin{bmatrix}0\\ \ldots\\ 1\\ \ldots \\ 0\end{bmatrix} \\
\Rightarrow &v = \beta_1 * e_1 + \beta_2 * e_2 + \beta_3 * e_3 + \ldots + \beta_m * e_m = \begin{bmatrix}\beta_1\\ \beta_2\\ \ldots\\ \beta_m\end{bmatrix}
\end{align}
$$

$$
A * v = A \begin{bmatrix}\beta_1\\ \ldots\\ \beta_m\end{bmatrix} := \begin{bmatrix}\sum_{i = 1}^m a_{1, i} \beta_i\\ \sum_{i = 1}^m a_{2, i} \beta_i\\ \ldots\\ \sum_{i = 1}^m a_{n, i} \beta_i\end{bmatrix}
$$

#### Beispiel
$$
A = \begin{bmatrix}1&2&3\\ 4&5&6\end{bmatrix} \qquad v = \begin{bmatrix}1\\ -1\\ 2\end{bmatrix}\\
A * v = \begin{bmatrix}1 * 1 + 2 * (-1) + 3 * 2\\ 4 * 1 + 5 * (-1) + 6 * 2\end{bmatrix} = \begin{bmatrix}5\\ 11\end{bmatrix}
$$

---

$$
\begin{align}
&\sum_{i = 1}^n \left( \sum_{j = 1}^m a_{i, j} \beta_j\right) y_i\\
&= \begin{bmatrix}\sum_{j = 1}^m a_{1, j} \beta_j\\ \sum_{j = 1}^m a_{2, j} \beta_j\\ \ldots\\ \sum_{j = 1}^m a_{n, j} \beta_j\end{bmatrix} = \beta_1 * \begin{bmatrix}a_{1,1}\\ a_{2,1}\\ \ldots \\a_{n, 1}\end{bmatrix} + \beta_2 * \begin{bmatrix}a_{1,2}\\ a_{2,2}\\ \ldots \\a_{n, 2}\end{bmatrix} + \ldots + \beta_m * \begin{bmatrix}a_{1,m}\\ a_{2,m}\\ \ldots \\a_{n, m}\end{bmatrix}
\end{align}
$$

---

**Anfang**:
$$
f(v_j) = \sum_{i = 1}^n a_{i, j} y_i = \begin{bmatrix}a_{1, j}\\ a_{2, j}\\ \ldots\\ a_{n, j}\end{bmatrix} \text{(j-te Spalte der Matrix A)}
$$

#### Beispiel
$$
\begin{align}
&f: \mathbb{R}^3 \to \mathbb{R}^2\\
&f(e_1) = \begin{bmatrix}1\\ 1\end{bmatrix}\\
&f(e_2) = \begin{bmatrix}1\\ 0\end{bmatrix}\\
&f(e_3) = \begin{bmatrix}0\\ 1\end{bmatrix}\\
\end{align}\\
A = \begin{bmatrix}1&1&0\\ 1&0&1\end{bmatrix}\\
A * \begin{bmatrix}1\\ 1\\ 1\end{bmatrix} = \begin{bmatrix}2\\ 2\end{bmatrix}\\
$$
$$
\begin{align}
f(\begin{bmatrix}1\\ 1\\ 1\end{bmatrix}) &= f(1e_1 + 1e_2 + 1e_3)\\
&= f(e_1) + f(e_2) + f(e_3)\\ &= \begin{bmatrix}1\\ 1\end{bmatrix} + \begin{bmatrix}1\\ 0\end{bmatrix} + \begin{bmatrix}0\\ 1\end{bmatrix} = \begin{bmatrix}2\\ 2\end{bmatrix}
\end{align}
$$

## 8.3 "Rechnen mit Matrizen"
Seien $A, B \in \mathbb{R}^{m\times n}$  
$A + B := C$ mit $c_{i, j} = a_{i, j} + b_{i, j}$
### Beispiel
$$
A = \begin{bmatrix}1&2\\ 3&4\\ 5&6\end{bmatrix} \qquad B = \begin{bmatrix}7&8\\ 9&10\\ 11&12\end{bmatrix}\\
A + B = \begin{bmatrix}1+7&2+8\\ 3+9&4+10\\ 5+11&6+12\end{bmatrix} = \begin{bmatrix}8&10\\ 12&14\\ 16&18\end{bmatrix}
$$

und für $\lambda \in \mathbb{R}$ ist $\lambda * A := C$ mit $c_{i, j} = \lambda * a_{i, j}$:
$$
\lambda * A = \begin{bmatrix}2 * 1&2 * 2\\ 2 * 3&2 * 4\\ 2 * 5&2 * 6\end{bmatrix} = \begin{bmatrix}2&4\\ 6&8\\ 10&12\end{bmatrix}
$$
Matrizen gleicher Dimension bilden einen **Vektorraum**.  
Basis:
$$
\text{Basis: } \left\{ \begin{bmatrix}1&0\\ 0&0\\ 0&0\end{bmatrix} \begin{bmatrix}0&1\\ 0&0\\ 0&0\end{bmatrix} \begin{bmatrix}0&0\\ 1&0\\ 0&0\end{bmatrix} \begin{bmatrix}0&0\\ 0&1\\ 0&0\end{bmatrix} \begin{bmatrix}0&0\\ 0&0\\ 1&0\end{bmatrix} \begin{bmatrix}0&0\\ 0&0\\ 0&1\end{bmatrix}\right\}
$$

## 8.4 Matrixmultiplikation
**Abbildung 9.1**
$$
A \in \mathbb{R}^{m \times n}\\
B \in \mathbb{R}^{m \times n}\\\\
C = \{ c_{l, j} \}\\
c_{l,j} = \sum_{i = 1}^n a_{l, i} * b_{i * j}
$$

### Beispiel
$$
A = \begin{bmatrix}1&2&3\\ 4&5&6\end{bmatrix} \qquad B = \begin{bmatrix}-1&0&1\\ 2&1&3\\ 4&0&0\end{bmatrix}\\
\begin{align}
&\{ A * B \}_{1, 1} = 1 * (-1) + 2 * 2 + 3 * 4 = 15\\
&\{ A * B \}_{2, 1} = 4 * (-1) + 5 * 2 + 6 * 4 = 30\\
&\{ A * B \}_{1, 2} = 1 * 0 + 2 * 1 + 3 * 0 = 2
\end{align}
$$

---

$$
A * (B * x) = A * \begin{bmatrix}\sum_{i = 1}^k b_{1, i} x_i\\ \sum_{i = 1}^k b_{2, i} x_i\\ \ldots \\ \sum_{i = 1}^k b_{n, i} x_i\end{bmatrix} = \begin{bmatrix}\sum_{j = 1}^n a_{1, j} * \left( \sum_{i = 1}^k b_{j, i} x_i \right)\\ \sum_{j = 1}^n a_{2, j} * \left( \sum_{i = 1}^k b_{j, i} x_i \right)\\ \ldots \\ \sum_{j = 1}^n a_{m, j} * \left( \sum_{i = 1}^k b_{j, i} x_i \right)\end{bmatrix}\\
A \in \mathbb{R}^{m \times n}\\
B \in \mathbb{R}^{n \times k}
$$

Matrixmultiplikation soll die verkettete Funktion liefern.
$$
(A * B) * x = C * x \text{ mit } c_{l, j} = \sum_{i = 1}^n a_{l, i} * b_{i, j}
$$

$$
\begin{bmatrix}
\sum_{i = 1}^n a_{1, i} b_{i, 1}&\sum_{i = 1}^n a_{1, i} b_{i, 2}&\ldots&\sum_{i = 1}^n a_{1, i} b_{i, k}\\
\sum_{i = 1}^n a_{2, i} b_{i, 1}\\
\ldots\\
\sum_{i = 1}^n a_{m, i} b{i, 1}&\ldots
\end{bmatrix} x = \begin{bmatrix}
\sum_{j = 1}^k \left( \sum_{i = 1}^n a_{1, i} b_{i, j} * x_j\right)\\
\sum_{j = 1}^k \left( \sum_{i = 1}^n a_{2, i} b_{i, j} * x_j\right)\\
\ldots\\
\sum_{j = 1}^k \left( \sum_{i = 1}^n a_{m, i} b_{i, j} * x_j\right)
\end{bmatrix}
$$

## 8.5 Bestimmung einer Inversen
**Beispiel**: Zu $5$ ist $\frac{1}{5}$ das multiplikativ Inverse ($5 * \frac{1}{5} = 1$)
### Definition
Sei $E_n$ die Einheitsmatrix der Dimension $n \times n$.  
D. h. $E_n \in \mathbb{R}^{n \times n}$ mit
$$
e_{i, j} = \delta_{i, j} = \begin{cases}
1&\text{für } i = j\\
0&\text{sonst}
\end{cases}
$$

Zu einer Matrix $A \in \mathbb{R}^{n \times n}$ ist $B$ die **Inverse**, wenn gilt $A * B = E_3$

### Beispiel
$$
\begin{align}
A =& \begin{bmatrix}1&2&-1\\ 1&2&0\\ 0&1&3\end{bmatrix}\\
\Rightarrow A^{-1} =& \begin{bmatrix}-6&7&-2\\ 3&-3&1\\ -1&1&0\end{bmatrix}
\end{align}
$$

### Probe
$$
A * A^{-1} = \begin{bmatrix}1&0& \ldots\\ 0&1&\ldots\\ \ldots &\ldots &\ldots\end{bmatrix}
$$

Wie bestimmt man $A^{-1}$?
$$
A * A^{-1} = E_n
$$

$$
\begin{align}
\begin{bmatrix}1&2&-1\\ 1&2&0\\ 0&1&3\end{bmatrix}&\begin{bmatrix}1&0&0\\ 0&1&0\\ 0&0&1\end{bmatrix}\\
\begin{bmatrix}1&2&-1\\ 0&1&3\\ 1&2&0\end{bmatrix}&\begin{bmatrix}1&0&0\\ 0&0&1\\ 0&1&0\end{bmatrix}\\
\begin{bmatrix}1&2&-1\\ 0&1&3\\ 0&0&1\end{bmatrix}&\begin{bmatrix}1&0&0\\ 0&0&1\\ -1&1&0\end{bmatrix}\\
\begin{bmatrix}1&2&0\\ 0&1&0\\ 0&0&1\end{bmatrix}&\begin{bmatrix}0&1&0\\ 3&-3&1\\ -1&1&0\end{bmatrix}\\
\begin{bmatrix}1&0&0\\ 0&1&0\\ 0&0&1\end{bmatrix}&\begin{bmatrix}-6&-7&2\\ 3&-3&1\\ -1&1&0\end{bmatrix}
\end{align}
$$

Elementare Umformungen $E1, E2, E3$ sind Multiplikationen mit Matrizen.

### Beispiel E2
$$
\begin{bmatrix}1&&\\ &\lambda&\\ &&1\end{bmatrix} * \begin{bmatrix}1&2&-1\\ 1&2&0\\ 0&1&3\end{bmatrix} = \begin{bmatrix}1&2&-1\\ \lambda&2\lambda&0\\ 0&1&3\end{bmatrix}
$$

$$
G_n \ldots G_3 G_2 G_1 A = E
$$

Rechte Seite:
$$
G_n \ldots G_3 G_2 G_1 E = A^{-1}
$$

Für die Einheitsmatrix gilt:
$$
X * E = X \text{ (analog zur "1")}
$$

## 8.6 Eigenwerte und Eigenvektoren
### Definition
Sei $A \in \mathbb{R}^{n \times n}$ und $v \in \mathbb{R}^n, v \neq 0$. Dann ist $v$ ein **Eigenvektor** von $A$, wenn es ein $\lambda \in \mathbb{R}$ gibt mit
$$
A * v = \lambda * v
$$
$\lambda$ heißt in diesem Fall **Eigenwert**.
### Beispiel
$$
A = \begin{bmatrix}2&1\\ 1&2\end{bmatrix}
$$dann sind $v_1 = \begin{bmatrix}1\\ 1\end{bmatrix}$ und $v_2 = \begin{bmatrix}1\\ -1\end{bmatrix}$ Eigenvektoren.

$$
\begin{align}
A * v_1 = \begin{bmatrix}2&1\\ 1&2\end{bmatrix} * \begin{bmatrix}1\\ 1\end{bmatrix} = \begin{bmatrix}3\\ 3\end{bmatrix} = 3 * \begin{bmatrix}1\\ 1\end{bmatrix} &\Rightarrow \text{Eigenwert } \lambda_1 = 3\\
A * v_2 = \begin{bmatrix}2&1\\ 1&2\end{bmatrix} * \begin{bmatrix}1\\ 1\end{bmatrix} = \begin{bmatrix}1\\ -1\end{bmatrix} &\Rightarrow \text{Eigenwert } \lambda_1 = 3
\end{align}
$$

Ist $v$ ein Eigenvektor zu $A$, dann auch $\mu * v$.

### Skizze
$$
\begin{align}
&A * v = \lambda * v\\
&A * (\mu * v) = \mu * a * v= \mu * \lambda * v = \lambda * (\mu * v)
\end{align}
$$
