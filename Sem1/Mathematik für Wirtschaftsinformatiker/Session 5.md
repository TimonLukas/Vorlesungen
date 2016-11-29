# Session 5



## Aufgaben
### Aufgabe 1
$$
\begin{align}
&A_0 = 2 \\
&A_1 = 4 \\
&A_2 = 6 \\
&A_3 = 8 \\
&A_4 = 8,25 \\
&A_5 = 8,45 \\
&A_6 \approx 8,62 \\
&A_7 \approx 8,76 \\
&A_8 \approx 8,76 \\
&A_9 \approx 8,76
\end{align}
$$

### Aufgabe 3
Gibt es zu $a \not\in I$ zu jedem $M > 0$ ein $\delta > 0$ mit
$$
\lvert x - a \rvert < \delta \Rightarrow f(x) > M \; \forall \; x \neq a \\
\Rightarrow f(x) \rightarrow \infty \text{für} x \rightarrow a \text{ bzw.} \lim_{x \rightarrow a} f(x) = \infty
$$

#### Beispiel
$$
\begin{align}
f(x) := \frac{1}{x} \qquad \lim_{x \rightarrow 0} f(x) = \infty \\
g(x) := \frac{1}{1 - x^2} \qquad \lim_{x \rightarrow 1} g(x) = \infty
\end{align}
$$

#### Allgemein
Sei $M > 0$ beliebig, dann gilt für $\delta = \frac{1}{M}$ für alle $x$ mit
$$
\lvert x - 0 \rvert < \delta \text{ bzw. } x < \delta \\
\Rightarrow f(x) = \frac{1}{x} > \frac{1}{\delta} = M
$$

## Grenzwerte
### Regel
Ist $lim_{x \rightarrow a} f(x) = f_G(a)$ und $lim_{x \rightarrow a} g(x) = g_G(a)$, dann gilt
* $\lim_{x \rightarrow a} (\alpha f + \beta g)(x) = \alpha * f_G(a) + \beta * g_G(a)$
* $\lim_{x \rightarrow a} (f * g)(x) = f_G(a) * g_G(a)$
* Ist $g_G(a) \neq 0$, dann auch $lim_{x \rightarrow a} (\frac{f}{g})(x) = \frac{f_G(a)}{g_G(a)}$

### Beispiel
$$
lim_{x \rightarrow \infty} (\frac{1}{x} - \frac{3}{x^2} + \frac{7}{x^3})
$$
Zerlegen:
$$
\begin{align}
&f(x) = \frac{1}{x} \rightarrow 0 \\
&g(x) = \frac{1}{x^2} \\
&g_1(x) = \frac{1}{x} \land g_2(x) = \frac{1}{x} \Rightarrow g(x) = g_1(x) * g_2(x) \rightarrow 0 \\
&h(x) \rightarrow 0
\end{align}
$$

## 3.2 Stetigkeit
### Definition
$$
f: I \rightarrow \mathbb{R}
$$
$f$ ist stetig in $a \in I$ wenn gilt:  
Zu jeden $\epsilon$ > 0 gibt es ein $\delta > 0$ mit
$$
\lvert x - a \rvert < \delta \Rightarrow \lvert f(x) - f_{\color{red}{G}}(a) \rvert < \epsilon \qquad \color{red}{x \neq a}
$$
Kurz:
$$\forall \; \epsilon > 0 \; \exists \; \delta > 0 : \lvert x - a \rvert < \delta \Rightarrow \lvert f(x) - f(a) \rvert < \epsilon$$
