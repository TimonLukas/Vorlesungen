<!-- TOC depthFrom:1 depthTo:3 withLinks:1 updateOnSave:1 orderedList:0 -->

- [1.2 Ökonomische Anwendungen](#12-ökonomische-anwendungen)
- [2. Folgen und Reihen](#2-folgen-und-reihen)
	- [2.1 (reelle) Folgen](#21-reelle-folgen)
		- [Definition](#definition)
		- [Beispiele](#beispiele)
		- [Bedeutung](#bedeutung)
		- [Konvergenz](#konvergenz)
		- [Beispiele](#beispiele)
	- [Dreiecksungleichung](#dreiecksungleichung)

<!-- /TOC -->

# 1.2 Ökonomische Anwendungen
Grafik 4

# 2. Folgen und Reihen
## 2.1 (reelle) Folgen
### Definition
Eine reelle Folge ($a_n$) ist eine Funktion
$$f: \mathbb{N} \to \mathbb{R}, n \to a_n$$

### Beispiele
1. $a_n = 1 \; \to 1, 1, 1, 1, \ldots$
2. $a_n = \frac{n}{2} \to \frac{1}{2}, \frac{2}{2}, \frac{3}{2}, \ldots$
3. $a_n = \frac{1}{2} a_{n - 1} + 1, a_0 = 5 \to a_1 = \frac{1}{2} * 5 + 1 = \frac{7}{2}$

### Bedeutung
Ab $a_n$ werden alle Folgeglieder "eingesperrt" im Bereich $a - \epsilon | a + \epsilon$

### Konvergenz
Eine Funktion heißt **konvergent** gegen $a$, wenn für alle $\epsilon > 0$ es gibt ein $N \in \mathbb{N}$ dafür gilt ist $n \geq N$ daraus folgt $\lvert a_n - a \rvert$ ist kleiner als $\epsilon$.
$$\forall \; \epsilon > 0 \; \exists \; N \in \mathbb{N} : n \geq N \Rightarrow \lvert a_n - a \rvert < \epsilon$$
Eine Folge, die gegen kein $a \in \mathbb{R}$ konvergiert, heißt divergent.

Nicht gegen $a$ konvergent:
$$\exists \; \epsilon > 0 \; \forall \; N \in \mathbb{N}: \exists \; n \geq N : \lvert a_n - a \rvert > \epsilon$$

Divergent:
$$\forall \; a \in \mathbb{R} \; \exists \; \epsilon > 0 \; \forall \; N \in \mathbb{N}: \exists \; n \geq N : \lvert a_n - a \rvert > \epsilon$$

### Notation
$a_n$ konvergiert gegen $a$  
$a_n \to a$  
$\lim_{n\to\infty} a_n \to a$

### Beispiele
#### 1.
$a_n = \frac{1}{n}$
* These: Konvergent gegen Null
* Test: $\epsilon = 0,01$  
$\lvert a_n - a \rvert = \lvert \frac{1}{n} - 0 \rvert = \frac{1}{n} < 0,01 \qquad | * 100 * n$  
$\Leftrightarrow 100 < n$  
$\Rightarrow N = 101$

Beweis der Konvergenz gegen $a = 0$.  
Sei $\epsilon > 0$ beliebig aber fest. Dan gilt für $N = $, für alle $n > N$
$$
\begin{align}
\lvert a_n - a \rvert = \lvert \frac{1}{n} - 0 \rvert & = \frac{1}{n} < \epsilon \qquad | * \frac{1}{\epsilon} * n \\
& \Leftrightarrow \frac{1}{\epsilon} < n
\end{align}
$$

#### 2.
* These : $a_n = \frac{1}{n}$ ist nicht konvergent gegen $a = 5$.
* Für $\epsilon = 1$ gilt
$$
\begin{align}
\lvert a_n - a \rvert = \lvert \frac{1}{n} - 5 \rvert & \geq 5 - 1 = 4 > \epsilon \\
& \Rightarrow n = N
\end{align}
$$

### Lemma
Ist $(a_n)$ eine konvergente Folge und konvergiert gegen $a$ und gegen $b$, dan gilt $a = b$.

#### Beweis
Angenommen es ist $a \neq b$, dann ist $\epsilon = \frac{\lvert a - b \rvert}{2} > 0$. Dann gibt es wegen der Konvergenz von $a_n$ gegen $a$ ein $N_1$ mit
$$\lvert a_n - a \rvert < \epsilon \;\;\; \forall \; n \geq N_1$$
Wegen der Kovergenz von $a_n$ gegen $b$ gibt es ein $N_2$ mit
$$\lvert a_n - b \rvert < \epsilon \;\;\; \forall \; n \geq N_2$$
Dann folgt
$$\lvert a - b \rvert = \lvert a - a_n + a_n - b \rvert \leq \lvert a - a_n \rvert + \lvert a_n - b \rvert < \epsilon + \epsilon = 2\epsilon$$ für $n \geq N = max\{N_1, N_2\}$
$$
\begin{align}
& \Rightarrow \lvert a - b \rvert < 2\epsilon \\
& \Leftrightarrow \lvert \frac{a - b}{2} \rvert < \epsilon
\end{align}
$$
=> Annahme war falsch da Widerspruch zu $\epsilon = \frac{\lvert a - b \rvert}{2}$

### Satz
Seien $(a_n), (b_n)$ Folgen mit $(a_n) \to a$ und $(b_n) \to b$, dann gilt:
1. $(a_n \pm b_n)$ sind konvergent mit $\lim_{n\to\infty} (a_n \pm b_n) = a \pm b$
2. $(a_n * b_n)$ ist konvergent mit $\lim_{n\to\infty} (a_n * b_n) = a * b$
3. Sind $b_n, b \neq 0$ dann konvergiert $\frac{1}{b_n}$ mit $\lim_{n\to\infty} \frac{1}{b_n} = \frac{1}{b}$
4. Ist $a_n \leq b_n \; \forall n \in \mathbb{N}$ so folgt $a \leq b$.

#### Beweis
1. Für $+$:
	* Ziel: $\forall \; \epsilon > 0 \; \exists \; N \in \mathbb{N}: \lvert a_n + b_n - a - b \rvert < \epsilon \; \forall \; n \geq N$
	* Sei $\epsilon > 0$ beliebig, aber fest.
	* $a_n \to a:$ Zu $\epsilon_1 = \frac{\epsilon}{2}$ gibt es ein $N_1 \in \mathbb{N}$ mit $\lvert a_n - a \rvert < \epsilon_1 \; \forall \; n \geq N_1$
	* $b_n \to b:$ Zu $\epsilon_2 = \frac{\epsilon}{2}$ gibt es ein $N_2 \in \mathbb{N}$ mit $\lvert b_n - b \rvert < \epsilon_2 \; \forall \; n \geq N_2$
	* Für $N = max\{N_1, N_2\}$ gilt:
	$$\lvert a_n + b_n - a - b \rvert = \lvert a_n - a + b_n - b \rvert \leq \lvert a_n - a \rvert + \lvert b_n - b \rvert < \epsilon_1 + \epsilon_2 = \epsilon$$

## Dreiecksungleichung
$$\lvert a + b \rvert \leq \lvert a \rvert + \lvert b \rvert$$
Umgekehrte Dreiecksungleichung:
$$\lvert a - b \rvert \geq \lvert \lvert a \rvert - \lvert b \rvert \rvert$$
