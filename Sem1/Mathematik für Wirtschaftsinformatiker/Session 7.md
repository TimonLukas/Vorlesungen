# Session 7

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Session 7](#session-7)
	- [Aufgaben](#aufgaben)
		- [Übungen 4](#übungen-4)
			- [Nr. 1](#nr-1)
				- [1.](#1)
				- [2.](#2)
			- [Nr. 2](#nr-2)
				- [1.](#1)
				- [2.](#2)
			- [Nr. 3](#nr-3)
				- [1.](#1)
				- [3.](#3)
		- [Übungen 5](#übungen-5)
			- [Nr. 1](#nr-1)
				- [1.](#1)
			- [Nr. 2](#nr-2)
				- [1.](#1)
				- [2.](#2)
				- [3.](#3)

<!-- /TOC -->

## Aufgaben
### Übungen 4
#### Nr. 1
##### 1.
$f$ ist stetig in $a \Leftrightarrow \; \forall \epsilon > 0 \; \exists \; \delta > 0 : \lvert x - a \rvert < \delta \Rightarrow \lvert f(x) - f(a) \rvert < \epsilon$

Sei $\epsilon > 0$ beliebig, dann gilt für $\delta = \frac{\epsilon}{2}$, $\lvert x - a \rvert < \delta$  
$$\lvert f(x) - f(a) \rvert =  \rvert 2x - 2a \lvert = 2 * \lvert x - a \rvert < \epsilon \; \color{red}{(< 2 * \frac{\epsilon}{2})}$$

##### 2.
a) $f(\lim_{x\rightarrow a}) = f(a) = 2*a$  
b) $\lim{x \rightarrow a} f(x) = \lim_{x \rightarrow a} 2x = 2 * \lim_{x \rightarrow a} x = 2a$

#### Nr. 2
##### 1.
$$
\begin{align}
&\left(\frac{1}{x}\right)' = - \frac{1}{x^2} \\
&\left(\frac{1}{x}\right)' = \lim_{h \rightarrow 0} \frac{\frac{1}{x + h} - \frac{1}{x}}{h} = \lim_{h \rightarrow 0} \frac{\frac{x - (x + h)}{x * (x + h)}}{h} = \lim_{h \rightarrow 0} \frac{-h}{(x^2 + xh) * h} \\
&\lim_{h \rightarrow 0} \frac{-1}{x^2 + xh} = \frac{-1}{x^2} = \frac{lim_{h \rightarrow 0} -1}{\lim_{h \rightarrow 0} x^2 + xh} = \frac{-1}{x^2}
\end{align}
$$

##### 2.
$$
\begin{align}
&t(x) = x \\
&t'(x) = 1 \\
&\left(\frac{1}{x}\right)' = \left(\frac{1}{t(x)}\right) = \frac{1' * t(x) - 1 * t'(x)}{t(x)^2} = \frac{0 - 1}{x^2} = -\frac{1}{x^2}
\end{align}
$$

#### Nr. 3
##### 1.
$$
\begin{align}
&a^x = e^{x * ln(a)} \\
&\left(e^{x * ln(a)}\right)' = e^{x * ln(a)} * (1 * ln(a) + x * 0) \\
&= e^x * ln(a) \\
&= a^x * ln(a)
\end{align}
$$
##### 3.
$$
\begin{align}
\left(tan(x)\right)^2 = \left(\frac{sin(x)}{cos(x)}\right)^2 \\
tan(x)' = \left(\frac{sin(x)}{cos(x)}\right) = &\frac{sin(x)' * cos(x) - sin(x) * cos(x)'}{cos^2(x)} \\
= &\frac{cos^2(x) + sin^2(x)}{cos^2(x)} = \frac{1}{cos^2(x)} \\
\left((tan(x))^2\right) = &2 * tan(x) * tan(x)' \\
= & 2 * tan(x) * \frac{1}{cos^2(x)}
\end{align}
$$

### Übungen 5
#### Nr. 1
##### 1.
$$
\begin{align}
\int_0^213te^{t^2}dt &= \int_0^26,5e^{t^2} * 2t dt \\
&= \int_0^46,5e^zdz = \left[6,5e^z\right]_ 0^4 = \left[6,5e^{t^2}\right]_ 0^2\\
&\color{red}{\int_0^2f(\varphi(t)) * \varphi'(t)dt = \int_{\varphi(0)}^{\varphi(2)}f(z)dz}
\end{align}
$$

#### Nr. 2
Wir bringen ein Produkt raus (Menge $q_1$), ein anderer folgt (Menge $q_2$).
$$
\begin{align}
p(q_1, q_2) = 10 - \frac{1}{2}(q_1 + q_2) \\
c(q_i) = 2 * q_i + &F \\
&F = 6
\end{align}
$$
##### 1.
$$
\begin{align}
&q_1 = \frac{a - c}{2b} = \frac{10 - 2}{1} = 8 \\
&q_2 = \frac{a - c}{4b} = \frac{10 - 2}{2} = 4 \\
\end{align}
$$
##### 2.
$$
\begin{align}
&p(8, 4) = 10 - \frac{1}{2}(8 + 4) = 4 \\
&G_1 = 4 * 8 - 2 * 8 - 6 = 10 \\
&G_2 = 4 * 4 - 2 * 4 - 6 = 2
\end{align}
$$
##### 3.
$$
\begin{align}
q_1 = 10 \\
\text{max } G_2 =& p(10, q_2) * q_2 - 2 * q_2 - F \\
=& \left[10 - \frac{1}{2}(10 + q_2)\right] * q_2 - 2 * q_2 - F
\end{align}
$$
$$
\begin{align}
&G_2' = 10 - \frac{1}{2}(10 + q_2) - \frac{1}{2} * q_2 - 2 = 0 \\
&\Leftrightarrow 10 - 5 - q_2 - 2 = 0 \\
&\Leftrightarrow 3 = q_2
\end{align}
$$

Was passiert dann?

$$
\begin{align}
&p(10, 3) = 10 - \frac{1}{2} * (10 + 3) = 3,5 \\
&G_2 = 3,5 * 3 - 2 * 3 - 6 = 10,5 - 6 - 6 = -1,5
\end{align}
$$

$\Rightarrow$ Unternehmen 2 **geht nicht an den Markt, da sie nur Verluste machen könnten!**

$$
G_2 = 0 \\
\text{Wenn Unternehmen 2 produziert, dann} \\
q_2 = \frac{a - c - b * q_1}{2_b} \qquad \text{(vgl. Vorlesung)} \\
\begin{align}
p(q_1, q_2) &= a - b * (q_1 + q_2) \\
&= a - b * 1_q - \frac{a}{2} + \frac{c}{2} + \frac{b * q_1}{2} = \frac{a + c - b * q_1}{2}
\end{align}
$$
$$
\begin{align}
0 = G_2 &= q_2 * p - q_2 * c - F \\
&= \left(\frac{a - c - b * q_1}{2b}\right) * \frac{a + c - b * q_1}{2} - c * \frac{a - c - b * q_1}{2b} - F \\
&= \left(\frac{a - c - b * q_1}{2b}\right) * \left[\frac{a + c - b * q_1 - 2c}{2}\right] - F \\
&= \left(\frac{a - c - b * q_1}{2b}\right) * \left(\frac{a - c - b * q_1}{2}\right) - F \\
&= \left(8 - \frac{q_1}{2}\right) * \left(8 - \frac{q_1}{2}\right) * \frac{1}{2} - F \\
&= \left[64 - \frac{q_1}{2} + \frac{q_1^2}{4}\right] * \frac{1}{2} - F \\
\Leftrightarrow 0 &= 256 - 32 * q_1 + q_1^2 - 8 * F \\
&= q_1^2 - 32 * q_1 + 256 - 8F \\
q_1 &= 16 \pm \sqrt{(16)^2 - 256 + 8F} \\
&= 16 \pm \sqrt{8F} = 16 \pm \sqrt{48} \approx 9,07
\end{align}
$$

## Integration durch Substitution
$$
\int_a^bf(\varphi(t))\varphi'(t)t = \int_{\varphi(a)}^{\varphi(b)}f(x)dx
$$
### Skizze
$F$ sei Stammfunktion von $f$  
$F'$ = f
$$
\begin{align}
F(\varphi(t))' &= F'(\varphi(t)) * \varphi'(t) \\
&= f(\varphi(t)) * \varphi'(t)
\end{align}
$$

$$
\begin{align}
\int_a^bf(\varphi(t)) * \varphi'(t)dt &= F(\varphi(b)) - F(\varphi(a)) = \int_{\varphi(a)}^{\varphi(b)}f(x)dx
\end{align}
$$

## 6. Vektorräume
### Definition
$V$ ist ein Vektorraum, und seine Elemente $v \in V$ sind Vektoren, wenn
1. $v + w$ rechenbar ist $\forall \; v, w \in V$
2. $\lambda * v$ rechenbar ist $\forall \; v \in V, \; \forall \; \lambda \in \mathbb{R}$
3. $\lambda(\mu * v) = \lambda \mu v \; \forall \; v \in V, \; \forall \; \lambda, \mu \in \mathbb{R}$
4. $(\lambda + \mu) * v = \lambda v + \mu v \; \forall \; v \in V, \; \forall \; \lambda, \mu \in \mathbb{R}$
5. $\lambda (v + w) = \lambda v + \lambda w \; \forall \; v, w \in V, \; \forall \; \lambda \in \mathbb{R}$
6. $1 * v = v$

### Skizze
$$
\begin{align}
&V = \mathbb{R}^n \\
&v = \begin{bmatrix}
v_1 \\
v_2 \\
v_3 \\
\ldots \\
v_n
\end{bmatrix} \qquad v_i \in \mathbb{R} \\
&\mathbb{R}^3 = \begin{bmatrix}
v_1 \\
v_2 \\
v_3
\end{bmatrix} \qquad z. B. v = \begin{bmatrix}
1 \\
3 \\
-7
\end{bmatrix}
\end{align}
$$

### Beispiele
#### 1.
$$
\begin{align}
v + w = \begin{bmatrix}
v_1 \\
v_2 \\
\ldots \\
v_n
\end{bmatrix} + \begin{bmatrix}
w_1 \\
w_2 \\
\ldots \\
w_n
\end{bmatrix} := \begin{bmatrix}
v_1 + w_1 \\
v_2 + w_2 \\
\ldots \\
v_n + w_n
\end{bmatrix}
\end{align}
$$
#### 2.
$$
\begin{align}
&\lambda * v = \lambda * \begin{bmatrix}
v_1 \\
v_2 \\
\ldots \\
v_n
\end{bmatrix} := \begin{bmatrix}
\lambda v_1 \\
\lambda v_2 \\
\ldots \\
\lambda v_n
\end{bmatrix}
\end{align}
$$

### Skizze
$v = \mathbb{P}_2$: Raum der Polynome der Ordnung $\leq 2$.
$$
\begin{align}
&p_1 = a_1x^2 + a_2x + a_3 \\
&p_2 = b_1x^2 + b_2x + b_3 \\
&p_1 + p_2 = (a_1 + b_1) x^2 + (a_2 + b_2) x + a_3 + b_3 \\
& \lambda * p_1 = \lambda a_1x^2 + \lambda a_2x + \lambda a_3
\end{align}
$$

### Definition Länge
Die Länge eines Vektors $v \in \mathbb{R}^n$ ist
$$
\lvert|v\rvert| := \sqrt{v_1^2 + v_2^2 + \ldots + v_n^2}
$$

Dies ist die **euklidische Norm** des Vektors.  
Die Länge ist **eine** Norm.  
Normen gibt es **viele**.

### Beispiele
#### 3.
$$
\begin{align}
&V = \mathbb{R}^1 \\
&v = v_1 \\
&v + w = v_1 + w_1 \\
&\lambda * v = \lambda * v_1 \\
&\lvert|v\rvert| = \sqrt{v_1^2} = \lvert v_1\rvert
\end{align}
$$

### Definition
Sei $V$ ein Vektorraum und $v_1, \ldots, v_n \in V$. ein Element $v \in V$ heißt Linearkombination von $v_1, \ldots, v_n$, wenn es $\alpha_1, \ldots, \alpha_n \in \mathbb{R}$ gibt mit
$$V = \alpha_1 v_1 + \alpha_2 * v_2 + \ldots + \alpha_n * v_n$$.

### Beispiele
$$
\begin{align}
&v_1 = \begin{bmatrix}
1 \\
0 \\
0
\end{bmatrix} \\
&v_2 = \begin{bmatrix}
1 \\
0 \\
2
\end{bmatrix} \\
&v = \begin{bmatrix}
4 \\
0 \\
8
\end{bmatrix}
\end{align}
$$
ist Linearkombination von $v_1, v_2$
$$
v = 4 * v_2 + 0 * v_1 \qquad \alpha_1 = 0, \alpha_2 = 4
$$

$w = \begin{bmatrix}6\\ 0\\ 8\end{bmatrix}$ ist Linearkombination von $v_1, v_2$
$$
w = 4 * v_2 + 2 * v_1 \qquad \alpha_1 = 2, \alpha_2 = 4
$$

$z = \begin{bmatrix}1\\ 1 \\ 1\end{bmatrix}$ ist **keine** Linearkombination von $v_1, v_2$

### Definition
Ist $V$ ein Vektorraum und $S \subseteq V$, dann ist &lt;$S$&rt; die Menge aller endlichen Linearkombination von Elementen aus S. &lt;$S$&rt; heißt auch **Erzeugnis**.

### Beispiele
$$
\begin{align}
&V = \mathbb{R}^3 \\
&S = \left\{\begin{bmatrix}1\\ 0\\ 0\end{bmatrix}, \begin{bmatrix}1\\ 1\\ 0\end{bmatrix}\right\} \\
&<S> = \left\{7 * \begin{bmatrix}1\\ 0\\ 0\end{bmatrix} - 3 * \begin{bmatrix}1\\ 1\\ 0\end{bmatrix}, 2 * \begin{bmatrix}1\\ 0\\ 0\end{bmatrix} + 2 * \begin{bmatrix}1\\ 1\\ 0\end{bmatrix}, \ldots\right\}
\end{align}
$$

### Definition
Sei $V$ ein Vektorraum und $S \leq V$, $S$ heißt **linear unabhängig**, falls der Nullvektor $\begin{bmatrix}0\\ 0\\ \ldots \\ 0\end{bmatrix}$ nur in trivialer Weise als endliche Linearkombination von $n \geq 1$ verschiedene Vektoren aus dargestellt werden kann; d. h. sind $v_1, \ldots, v_n \in S$ verschiedene $\lambda_1, \ldots, \lambda_n \in \mathbb{R}$

$$
\vec{0} = \sum_{k = 1}^n \lambda_k v_k \Rightarrow \lambda_1 = \lambda_2 = \ldots \lambda_n = 0
$$

### Skizze
Linear abhängig:
$$
\begin{bmatrix}1\\ 2\\ 1\end{bmatrix} = \begin{bmatrix}1\\ 0\\ 1\end{bmatrix} + 2 * \begin{bmatrix}0\\ 1\\ 0\end{bmatrix} \\
\left\{\begin{bmatrix}1\\ 2\\ 1\end{bmatrix}, \begin{bmatrix}1\\ 0\\ 1\end{bmatrix}, \begin{bmatrix}0\\ 1\\ 0\end{bmatrix}\right\}
$$
ist linear abhängig.
$$
\vec{0} = 1 * \begin{bmatrix}1\\ 2\\ 1\end{bmatrix} - 1 * \begin{bmatrix}1\\ 0\\ 1\end{bmatrix} - 2 * \begin{bmatrix}0\\ 1\\ 0\end{bmatrix}
$$
