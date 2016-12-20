# Session 10

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Session 10](#session-10)
	- [Übungen](#übungen)
		- [7](#7)
			- [1](#1)
			- [2](#2)
		- [8](#8)
			- [2.2](#22)
			- [4](#4)
	- [8.6 Eigenvektoren, Eigenwerte](#86-eigenvektoren-eigenwerte)
		- [Was macht man mit Eigenvektoren/Eigenwerten?](#was-macht-man-mit-eigenvektoreneigenwerten)
	- [8.7 Determinanten](#87-determinanten)
		- [Lineare Unabhängigkeit](#lineare-unabhängigkeit)

<!-- /TOC -->

## Übungen
### 7
#### 1
$$
\begin{align}
f((x, &y)) = (x - y, x + y) \qquad f((a, b)) = (a - b, a + b)\\
&1)\;f((x + y) + (a, b)) =\text{?} f((x + a, y + b))\\
&\;\;(x - y + (a - b), x + y + (a + b)) = (x + a - (y + b), x + y + a + b)\\
&2) f((\lambda a, \lambda b)) = \lambda f((a, b))\\
&\;\;(\lambda a - \lambda b, \lambda a + \lambda b) = \lambda (-b + a, a + b)
\end{align}
$$

$$
\begin{align}
f((x, &y, z)) = (x^2, x - y) \\
&1) f((x, y, z) + (a, b, c)) = f((x + a, y + b, z + c))\\
&\;\;(x^2 + a^2, x + a - (y + b)) \color{red}{\neq} ((x + a)^2, x + a - (y + b))
\end{align}
$$

#### 2
$$
\begin{align}
&\text{Behauptung: Lineare Abbildung falls}\\
&\forall \; x, y \in V, \; \forall \; \alpha, \beta \in \mathbb{R}: \alpha f(x) + \beta f(y) = f(\alpha * x + \beta * y)\\\\
&\text{Wir wissen:}\\
&1) f(x) + f(y) = f(x + y)\\
&2) \lambda f(x) = f(\lambda x)\\
\Rightarrow &\text{Zusammenfassend: } \alpha f(x) + \beta f(y) = f(\alpha x) + f(\beta y) = f(\alpha x + \beta y)
\end{align}
$$

### 8
#### 2.2
$$
\begin{align}
&E_n * A = A\\
&E_N * A = C\\
&c_{i, j} = \sum_{k = 1}^n e_{i, k} * a_{k, j}\\
& = \sum_{k = 1}^n \delta_{i, k} * a_{k, j} \qquad \delta = \text{Kronecker-Delta}
\end{align}
$$

#### 4
$$
\begin{align}
&f: \mathbb{R}^2 \to \mathbb{R}^4\\
&f(e_1) = e_1 + 4e_3 \left(= \begin{bmatrix}1\\ 0\\ 4\\ 0\end{bmatrix}\right)\\
&f(e_3) = 2e_2 \left(= \begin{bmatrix}0\\ 2\\ 0\\ 0\end{bmatrix}\right)\\
&A = \begin{bmatrix}1&0\\ 0&2\\ 4&0\\ 0&0\end{bmatrix}\\\\
&f((2, -3)) \text{ auf 3 Arten:}\\
&1)\; A * \begin{bmatrix}2\\ -3\end{bmatrix} = \begin{bmatrix}2\\ -6\\ 8\\ 0\end{bmatrix}\\
&2)\; 2 * \begin{bmatrix}1\\ 0\\ 4\\ 0\end{bmatrix} - 3 * \begin{bmatrix}0\\ 2\\ 0\\ 0\end{bmatrix} = \begin{bmatrix}2\\ -6\\ 8\\ 0\end{bmatrix}\\
&3)\; \begin{bmatrix}2\\ -3\end{bmatrix} = 2 * e_1 - 3 * e_2 \\&\Rightarrow f((2, -3)) = 2 * f((1, 0)) - 3 * f((0, 1)) = 2 * \begin{bmatrix}1\\ 0\\ 4\\ 0\end{bmatrix} - 3 * \begin{bmatrix}0\\ 2\\ 0\\ 0\end{bmatrix} = \begin{bmatrix}2\\ -6\\ 8\\ 0\end{bmatrix}
\end{align}
$$

## 8.6 Eigenvektoren, Eigenwerte
$$
\begin{align}
&A \in \mathbb{R}^{n \times n}, v \neq 0\\
&A * v = \lambda * v\\
&A = \begin{bmatrix}2&1\\ 1&2\end{bmatrix}\\
&v_1 = \begin{bmatrix}1\\ -1\end{bmatrix}, v_2 = \begin{bmatrix}1\\ 1\end{bmatrix}
\end{align}
$$

Bestimmung von Eigenvektor/Eigenwert:
$$
\begin{align}
&A * v = \lambda * v\\
\Leftrightarrow &A * v - \lambda v = \vec{0}\\
\Leftrightarrow &A * v - \lambda * E_n v = \vec{0}\\
\Leftrightarrow &(A - \lambda * E_n) * v = \vec{0}\\
\Rightarrow &\text{ LGS}
\end{align}
$$

**Im Beispiel**:
$$
\begin{align}
&(A - \lambda E_n) * v = \begin{bmatrix}(2 - \lambda)&1\\ 1&(2 - \lambda)\end{bmatrix} * \begin{bmatrix}x\\ y\end{bmatrix} = \begin{bmatrix}0\\ 0\end{bmatrix}\\\\
\Leftrightarrow &(2 - \lambda) * x + y = 0\\
&x + (2 - \lambda) * y = 0\\
&\Rightarrow x = -(2 - \lambda) y \Rightarrow -(2 - \lambda) * (2 - \lambda) * y + y = 0
\end{align}
$$

Fall 1:
$$
\begin{align}
&y = 0\\
\Rightarrow &x = 0 \Rightarrow \text{ Kein Eigenvektor}
\end{align}
$$

Fall 2:
$$
\begin{align}
&y \neq 0\\
&y\left[(2 - \lambda)^2 - 1\right] = 0\\
\Leftrightarrow &(2 - \lambda)^2 - 1 = 0\\
\Leftrightarrow &\lambda^2 - 4 * \lambda + 4 - 1 = 0\\
\Leftrightarrow &\lambda^2 - 4 * \lambda + 3 = 0\\
&\lambda_{1, 2} = 2 \pm \sqrt{4 - 3} = 2 \pm 1\\
&\Rightarrow \lambda_1 = 3\; \land \; \lambda_2 = 1\\\\
&\text{Bestimmung der Eigenvektoren:}\\
&\; \lambda = 1: (A - \lambda E_n) * v = \vec{0}\\
&\begin{bmatrix}1&1\\ 1&1\end{bmatrix} * \begin{bmatrix}x\\ y\end{bmatrix} = \vec{0}\\
\Leftrightarrow &x + y = 0 \Rightarrow x = -y\\
&x + y = 0 \Rightarrow \begin{bmatrix}1\\ -1\end{bmatrix} \text{ ist Eigenvektor}\\\\
&\lambda = 3: (A - \lambda E_n) * v = \vec{0}\\
&\begin{bmatrix}-1&1\\ 1&-1\end{bmatrix} * \begin{bmatrix}x\\ y\end{bmatrix} = \begin{bmatrix}0\\ 0\end{bmatrix}\\
&-x + y = 0\\
&x - y = 0\\
\Rightarrow &x = y \Rightarrow v = \begin{bmatrix}1\\ 1\end{bmatrix} \text{ ist Eigenvektor}
\end{align}
$$

### Was macht man mit Eigenvektoren/Eigenwerten?
$$
\begin{align}
&\ldots f(f(f(f(f(v)))))\\
&\text{Ist A darstellende Matrix, dann}\\
&\ldots A * A * A * A * A * v = A^{17} * v\\
&A = \begin{bmatrix}2&1\\ 1&2\end{bmatrix}, v = \begin{bmatrix}2\\ -8\end{bmatrix}\\\\
&\text{Weg 1:}\\
&A * v = \begin{bmatrix}-4\\ -14\end{bmatrix}\\
&A * (A * v) = \ldots\\
&\ldots\\\\
&\text{Weg 2:}\\
&A^2 = \begin{bmatrix}2&1\\ 1&2\end{bmatrix} * \begin{bmatrix}2&1\\ 1&2\end{bmatrix} = \begin{bmatrix}5&4\\ 4&5\end{bmatrix}\\
&A^3 = A^2 * A = \ldots
\end{align}
$$

Vorher berechnet:
$$
\lambda = 3: v_1 = \begin{bmatrix}1\\ 1\end{bmatrix}\\
\lambda = 1: v_2 = \begin{bmatrix}1\\ -1\end{bmatrix}
$$

$$
\begin{align}
&v = \alpha v_1 + \beta v_2\\
&\begin{bmatrix}2\\ -8\end{bmatrix} = -3v_1 + 5v_2\\\\
&A^{17} * v_1\\
&A * v_1 = 3 * v_1\\
&A^2 * v_1 = A * (A * v_1) = A * 3 * v_1 = 3 * A * v_1 = 3 * 3 * v_1 = 3^2 * v_1\\
&A^3 * v_1 = A * (A^2 * v_1) = A * 3^2 * v_1 = 3^2 * A * v_1 = 3^2 * 3 * v_1 = 3^3 * v_1\\
&\ldots\\
&A^{17} * v_1 = 3^17 * v_1\\
&A^{17} * v_2 = 1^{17} * v_2 = v_2\\
&A * v_2 = v_2\\
&A^{17} * v = A^{17} * (-3 * v_1 + 5 * v_2)\\
&= -3 * A^{17} * v_1 + 5 * A^{17} * v_2 = -3 * 3^17 * v_1 + 5 * v_2
\end{align}
$$

## 8.7 Determinanten
$$
\begin{align}
\begin{bmatrix}1&3&5\\ 0&2&1\\ 0&4&3\end{bmatrix} &= 1 * \begin{bmatrix}2&1\\ 4&3\end{bmatrix} - 0 * \begin{bmatrix}3&5\\ 4&3\end{bmatrix} + 0 * \begin{bmatrix}3&5\\ 2&1\end{bmatrix}\\
&= 1 * (2 * 3 - 4 * 1)\\
&= 1 * (6 - 4)\\
&= 2
\end{align}
$$

1. Schritt: Rückführung der Dimension $n$ auf $n - 1$  
$$
\begin{align}
&\text{Sei } A \in \mathbb{R}^{n \times n}\\
&\left|A\right| = det(A) = \sum_{k = 1}^n a_{k, 1} * (-1)^{k + 1} * det(A^* _ {k, 1})
\end{align}
$$  
$$
A^* _ {k, i} := \text{ Matrix, die durch streichen der k-ten Zeile und i-ten Spalte von A entsteht.}
$$

2. Schritt: Bestimmung der Determinante für $n = 2$

**Allgemein**:
$$
\begin{align}
det(A) &= \sum_{k = 1}^n a_{k, j} * (-1)^{(k + j)} * det(A^* _ {k, j})\\
&= \sum_{k = 1}^n a_{i, k} (-1)^{(i + k)} * det(A^{(* )}_{i, k})
\end{align}
$$

Löse nach 3-ter Zeile auf:
$$
\begin{align}
det(A) = &a_{3, 1} * (-1)^{3 + 1} det(A^ * _ {3, 1})\\
&+ a_{3, 2} * (-1)^{3 + 2} * det(A^* _ {3, 2})\\
&+ a_{3, 3} * (-1)^{3 + 3} * det(A^* _ {3, 3})\\
=& 0 * (-1)^4 * det\left(\begin{bmatrix}3&5\\ 2&1\end{bmatrix}\right)\\
&+ 4 * (-1)^5 det\left(\begin{bmatrix}1&5\\ 0&1\end{bmatrix}\right)\\
&+ 3 * (-1)^6 det\left(\begin{bmatrix}1&3\\ 0&2\end{bmatrix}\right)\\
=& 0 * 1 * (3 * 1 - 5 * 2)\\
&+ 4 * (-1)^5 * (1 * 1 - 0 * 5)\\
&+ 3 * (-1)^6 * (1 * 2 - 3 * 0)\\
=& 0 - 4 * 1 + 3 * 2 = 2
\end{align}
$$

Für $n = 2$:
$$
det\left(\begin{bmatrix}1&b\\ c&d\end{bmatrix}\right) := a * d - b * c\\
A = \begin{bmatrix}a&b\\ c&d\end{bmatrix}\\\\
\begin{align}
det(A) &= a * (-1)^{1 + 1} * det([d]) + b * (-1)^{1 + 2} * det([c])\\
&= a * det([d]) - b * det([c])\\
&det([\lambda]) = \lambda
\end{align}
$$

### Lineare Unabhängigkeit
**Regel**: Sei $A = \begin{bmatrix}-&v_1&-\\ -&v_2&-\\ -&v_3&-\end{bmatrix}$: Sind die Vektoren $\{v_1, \ldots, v_n\}$ linear abhängig, dann ist die Determinante von $A = 0$. Sonst ist die Determinante von $A \neq 0$.

Wann hat $A * v = \vec{0}$ eine nicht triviale Lösung?  
Wenn die Zeilen (oder Spalten) linear abhängig sind.
$$
x + 3y = 0\\
3x - y = 0\\
\Rightarrow \text{ Zeilen sind linear unabhängig}\\
x + 2y = 0\\
2x + 4y = 0\\
\Rightarrow x = -2y \Rightarrow \text{ Zeilen sind linear abhängig}
$$

$$
\begin{align}
det(A) = 0 &\Rightarrow \text{ linear abhängige Zeilen}\\
&\Rightarrow \text{ nicht triviale Lösung von } A * v = \vec{0}
\end{align}
$$

Bestimmung von Eigenwert:
$$
A * v = \lambda * v\\
\ldots\\
(A - \lambda E_n) * v = \vec{0} \qquad v \neq \vec{0}\\
det(A - \lambda E_n) = 0
$$

**Im Beispiel**:
$$
\begin{bmatrix}2 - \lambda&1\\ 1&2 - \lambda\end{bmatrix} = (2 - \lambda)^2 - 1
$$
