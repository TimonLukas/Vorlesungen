# Session 4

## Aufgaben
$a_k$ ist eine Folge:

$$
\begin{align}
&A_0 := \sum_{k = 0}^{0} a_k \\
&A_1 := \sum_{k = 0}^{1} a_k \\
&A_2 := \sum_{k = 0}^{2} a_k \\
&\ldots
\end{align}
$$
### Aufgabe 1
#### 1
$$
a_k = (-2)^k \\
a_k = 1, -2, 4, -8, 16, -32, 64, -128, 256, -512, \ldots \\
\sum_{k = 0}^{\infty} a_k \\
\\
\begin{align}
&A_0 := \sum_{k = 0}^{0} a_k = 1 \\
&A_1 := \sum_{k = 0}^{1} a_k = 1 - 2 = -1 \\
&A_2 := \sum_{k = 0}^{2} a_k = 1 - 2 + 4 = 3 \\
&A_3 := \sum_{k = 0}^{3} a_k = 1 - 2 + 4 - 8 = -5 \\
&A_4 := \sum_{k = 0}^{4} a_k = 1 - 2 + 4 - 8 + 16 = 11 \\
\end{align}
$$
### Aufgabe 4
#### 2

$$
\begin{align}
\frac{x^k}{3^k} \rightarrow &\lvert \frac{\frac{x^{k + 1}}{3^{k + 1}}}{\frac{x^k}{3^k}} \rvert \leq q \\
\Leftrightarrow &\lvert \frac{x^{k + 1} * 3^k}{x^k * 3^{k + 1}} \rvert \leq q \\
\Leftrightarrow &\lvert \frac{x^{k + 1}}{x^k} * \frac{3^k}{3^{k + 1}} \rvert \leq q \\
\Leftrightarrow &\lvert x * \frac{1}{3} \rvert \leq q < 1 \\
\end{align} \\
-3 < x < 3
$$

## Quotientenkriterium
Eine Folge ist dann konvergent wenn gilt:
$$
\lvert \frac{a_{k + 1}}{a_k} \rvert < q
$$
### Motivation des Quotientenkriteriums
#### Geometrische Reihe
$$
\begin{align}
&\sum_{k = 0}^{n} q^k = \frac{1 - q^{n + 1}}{1 - q} \\
\rightarrow &\sum_{k = 0}^{\infty} = \frac{1}{1 - q} \qquad \text{für $\lvert q \rvert < 1$}
\end{align}
$$

$$
\begin{align}
&\lvert a_{k + 1} \rvert = \lvert \frac{a_{k + 1}}{a_k} \rvert * \lvert a_k \rvert \leq q * \lvert a_k \rvert \\
&\lvert a_{k + 1} \rvert = \lvert \frac{a_k}{a_k} * a_{k + 1} \rvert = \lvert a_k \rvert * \lvert \frac{a_{k + 1}}{a_k} \leq q * \lvert a_k \rvert \\
&\lvert a_{k + 2} \rvert = \lvert \frac{a_k}{a_k} * \frac{a_{k + 1}}{a_{k + 1}} * a_{k + 2} \rvert = \lvert a_k \rvert * \lvert \frac{a_{k + 1}}{a_k} \rvert * \lvert \frac{a_{k + 2}}{a_{k + 1}} \rvert \leq \lvert a_k \rvert * q * q = \lvert a_k \rvert * q^2 \\
&\lvert a_{k + 3} \rvert = \lvert \frac{a_k}{a_k} * \frac{a_{k + 1}}{a_{k + 1}} * \frac{a_{k + 2}}{a_{k + 2}} * a_{k + 3} \rvert = \lvert a_k \rvert * \lvert \frac{a_{k + 1}}{a_k} \rvert * \lvert \frac{a_{k + 2}}{a_{k + 1}} \rvert * \lvert \frac{a_{k + 3}}{a_{k + 2}} \rvert \leq \lvert a_k \rvert * q * q * q = \lvert a_k \rvert * q^3 \\
&\lvert a_{k + 17} \rvert \leq \lvert a_k \rvert * q^{17} \\
&\lvert a_{k + t} \rvert \leq \lvert a_k \rvert * q^t
\end{align}
$$
$$
\sum_{k = 0}^n \leq \sum_{k = 0}^n a_0 * q^k = a_0 \sum_{k = 0}^n q^k
$$

## 3. Grenzwerte und Stetigkeit
### 3.1 Grenzwerte
#### Definition
Ist $f: \mathbb{R} \rightarrow \mathbb{R}$ eine Funktion, dan ist **$f_G (a)$** der **Grenzwert von $f$ in $a$**, wenn für alle $\epsilon > 0$ ein $\delta > 0$ gibt mit
$$
\lvert x - a \rvert < \delta \Rightarrow \lvert f(x) - f_G(a) \rvert < \epsilon \qquad x \neq a
$$
Für den Grenzwert $f_G(a)$ schreiben wir
$$
f_G(a) = \lim_{x \rightarrow a} f(x)
$$
Kurz:
$$
\forall \; \epsilon > 0 \; \exists \; \delta > 0 : \lvert x - a \rvert < \delta \Rightarrow \lvert f(x) - f_G(a) \rvert < \epsilon \qquad x \neq a
$$
#### Beispiele
##### 1.
$$
\begin{align}
&f(x) = 2x \\
&a = 1 \\
&\lvert x - a \rvert < \delta \\
&\lvert f(x) - f(1) \rvert < \epsilon
\end{align}
$$
$$
\text{These:} \; f_G(1) = 2 \qquad \epsilon = 0,01 \\\\
\begin{align}
&f(x) = 2 + \epsilon\\
\Leftrightarrow &2x = 2 + \epsilon\\
\Leftrightarrow &x = 1 + \frac{\epsilon}{2}\\
\Rightarrow &\delta = \frac{\epsilon}{2}
\end{align}
$$
##### 2.
$$
f(x) =
\begin{cases}
2x, &\text{für} \; x \neq 1\\
3, &\text{für} \; x = 1
\end{cases}
$$
**Bekannt**: $f_G(1) = 2$  
$\epsilon = 0,01 \color{red}{\rightarrow \delta = \frac{\epsilon}{2}}$

$f(1,001) = 2,002$  
$f(0,009) = 1,998$  
$\Rightarrow f_G(1) = 2$
##### 3.
$f(x) = 2x \;\text{für} \; x \neq 1$  
$f_G(1) = 2$
##### 4.
$$
f(x) =
\begin{cases}
1, &\text{für} \; x \geq 0 \\
-1, &\text{für} \; x \lt 0
\end{cases}
$$
Grenzwert im Punkt $a = 0$?  
$$
f_G(0)
$$
Der Grenzwert existiert nicht:
* Angenommen $f_G(0) = 1$  
zu $\epsilon = 0,1$ für $\delta > 0$ beliebig gilt für $x = -\frac{\delta}{2}$
$$
\forall \; \epsilon > 0 \; \exists \; \delta > 0: \lvert x - a \rvert < \delta \Rightarrow \lvert f(x) - f_G(a) \rvert < \epsilon \qquad x \neq a\\
\exists \; \epsilon > 0 \; \forall \; \delta > 0 \; \exists \; x \; \text{mit} \; \lvert x - a \rvert < \delta \; \text{und} \; \lvert f(x) - f_G(a) \rvert > \epsilon \qquad x \neq a
$$

#### Linksseitiger Grenzwert $f_{G,L}(a)$
$$
\forall \; \epsilon > 0 \; \exists \; \delta > 0 \qquad 0 < a - x < \delta \Rightarrow \lvert f(x) - f_{G,L}(a) \rvert < \epsilon
$$
#### Rechtsseitiger Grenzwert $f_{G,R}(a)$
$$
\forall \; \epsilon > 0 \; \exists \; \delta > 0 \qquad 0 < x - a < \delta \Rightarrow \lvert f(x) - f_{G,R}(a) \rvert < \epsilon
$$
#### Satz
Existieren der Links- und der Rechtsseitige Grenzwert und gilt $f_{G,L}(a) = f_{G,R}(a)$, dann existiert der Grenzwert $f_G(a)$ und es gilt
$$
f_G(a) = f_{G,L}(a) = f_{G,R}(a)
$$
