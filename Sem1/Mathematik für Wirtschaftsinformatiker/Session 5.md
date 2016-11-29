# Session 5

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Aufgaben](#aufgaben)
	- [Aufgabe 1](#aufgabe-1)
	- [Aufgabe 3](#aufgabe-3)
		- [Beispiel](#beispiel)
		- [Allgemein](#allgemein)
- [Grenzwerte](#grenzwerte)
	- [Regel](#regel)
	- [Beispiel](#beispiel)
- [3.2 Stetigkeit](#32-stetigkeit)
	- [Definition](#definition)
	- [Folgerung](#folgerung)
	- [Regel](#regel)
	- [Skizze](#skizze)
- [4. Differentialrechnung](#4-differentialrechnung)
	- [Definition](#definition)
	- [Anwendung](#anwendung)
	- [Beispiele](#beispiele)
	- [Regel](#regel)
	- [Skizze zur Produktregel](#skizze-zur-produktregel)
	- [Kettenregel](#kettenregel)
		- [Regel](#regel)
		- [Beispiele](#beispiele)

<!-- /TOC -->

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
$\color{red}{\text{Grenzwert}}$
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

### Folgerung
$f$ ist stetig in $a$, wenn gilt
$$
\lim_{x \rightarrow a} f(x) = \color{red}{(} f(lim_{x \rightarrow a} x) = \color{red}{)} f(a)
$$

### Regel
Sind $f, g$ stetig in $a$, dann ist
* $(\alpha f + \beta g)$ stetig in $a$
* $f * g$ stetig in $a$
* für $g(a) \neq 0$ ist auch $\frac{f}{g}$ stetig in $a$

### Skizze
$$
\begin{align}
\lim_{x \rightarrow a} (f + g)(x) &= \lim_{x \rightarrow a} f(x) + lim_{x \rightarrow a} g(x) \\
&= f(lim_{x \rightarrow a} x) + g(lim_{x \rightarrow a} x) \\
&= f(a) + g(a) = (f + g)(a)
\end{align}
$$

## 4. Differentialrechnung
### Definition
Sei $f: I \rightarrow \mathbb{R}$ eine Funktion und $a \in I$. Dann heißt $f$ in $a \in I$ Ü
**differenzierbar**, falls der Grenzwert
$$
\lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
existiert.  
Wir bezeichnen den Grenzwert mit
$$
f'(a) \text{ oder } \frac{df}{dx}(a)
$$
und sprechen von der **ersten Ableitung** von $f$ in $a$.

### Anwendung
$h = 1:$
$$
\frac{\sqrt{2} - \sqrt{1}}{1} = \frac{1,41 - 1}{1} = 0,41
$$

$h = \frac{1}{2}:$
$$
\frac{\sqrt{\frac{3}{2}} - \sqrt{1}}{\frac{3}{2} - 1} = \frac{1,22\ldots - 1}{\frac{1}{2}} = \frac{0,22\ldots}{\frac{1}{2}} = 0,44\ldots
$$
$h = \frac{1}{4}$
$$
\frac{\sqrt{\frac{5}{4}} - \sqrt{1}}{\frac{5}{4} - 1} = \frac{1,12\ldots - 1}{\frac{1}{4}} = \frac{0,12\ldots}{\frac{1}{4}} = 0,48\ldots
$$

### Beispiele
1. $$\\
\begin{align}
&f(x) = 2 \\
&\text{in } a = 5 \\
&\lim_{h \rightarrow 0} \frac{f(5 + h) - f(5)}{h} = \lim_{h \rightarrow 0} \frac{2 - 2}{h} = \lim_{h \rightarrow 0} \frac{0}{h} = 0 = f'(5)
\end{align}
$$

2. $$\\
\begin{align}
&g(x) = x \qquad \text{in } a = 3 \\
&\lim_{h \rightarrow 0} \frac{g(3 + h) - g(3)}{h} = \lim_{h \rightarrow 0} \frac{3 + h - 3}{h} = \lim_{h \rightarrow 0} \frac{h}{h} = \lim_{h \rightarrow 0} 1 = 1 = g'(3)
\end{align}
$$

3. $$\\
\begin{align}
&t(x) = x^2 \qquad \text{in } a\\
&\lim_{h \rightarrow 0} \frac{t(a + h) - t(a)}{h} = \lim_{h \rightarrow 0} \frac{(a + h)^2 - a^2}{h} \\
&= \lim_{h \rightarrow 0} \frac{a^2 + 2a^h + h^2 - a^2}{h} = \lim_{h \rightarrow 0} \frac{2ah + h^2}{h} = \lim_{h \rightarrow 0} 2a + h = 2a = t'(a) \\
&t(x) = x^2 = g(x) * g(x) \qquad g(x) = x; g'(x) = 1 \\
&\Rightarrow \text{Produktregel:} \\
&Z'(x) = g'(x) * g(x) + g(x) * g'(x) = 1 * x + x * 1 = 2x
\end{align}
$$

### Regel
Sind $f, g$ differenzierbar, dann gilt
* $\alpha f + \beta g$ differenzierbar mit $(\alpha f + \beta g)'(x) = \alpha f'(x) + \beta g'(x)$
* $f(x) * g(x)$ differenzierbar mit $(f * g)'(x) = f(x) * g'(x) + f'(x) * g(x)$
* Falls $g'(x) \neq 0: (\frac{f}{g})'(x) = \frac{f'(x) * g(x) - f(x) * g'(x)}{g^2(x)}$

### Skizze zur Produktregel
$$
\begin{align}
&\lim_{h \rightarrow 0} \frac{(f * g)(x + h) - (f * g)(x)}{h} \\
= &\lim_{h \rightarrow 0} \frac{f(x + h) * g(x + h) - f(x) * g(x)}{h} \\
= &\lim_{h \rightarrow 0} \frac{f(x + h) * g(x + h) - f(x + h) * g(x) + f(x + h) * g(x) - f(x) * g(x)}{h} \\
= &\lim_{h \rightarrow 0} f(x + h) * \frac{g(x + h) - g(x)}{h} + \lim_{h \rightarrow 0} g(x) * \frac{f(x + h) - f(x)}{h} \\
= &\lim_{h \rightarrow 0} f(x + h) * \lim_{h \rightarrow 0} \frac{g(x + h) - g(x)}{h} + \lim_{h \rightarrow 0} g(x) * \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h} \\
= &f(x) * g'(x) + g(x) * f'(x)
\end{align}
$$

$$
\text{Es gilt: }\color{red}{\lim_{h \rightarrow 0} f(x + h) = f(\lim_{h \rightarrow 0} x + h) = f(x)}
$$

### Kettenregel
#### Regel
Sind $f, g$ differenzierbar, dann ist
$$
g(f(x))' = g'(f(x)) * f'(x)
$$

#### Beispiele
$f(x) = x^2 \\
g(y) = y^3$  

$x = 2 \\
g(f(2)) = g(4) = 64$  

$g(f(x))' = 3 * (f(x))^2 * 2 * x = 3 * x^4 * 2 * x = 6 * x^5 \\
g(f(x)) = g(x^2) = x^6$

$$
\begin{align}
&\lim_{h \rightarrow 0} \frac{g(f(x + h)) - g(f(x))}{h} \\
= &\lim_{h \rightarrow 0} \frac{g(f(x + h)) - g(f(x))}{f(x + h) - f(x)} * \frac{f(x + h) - f(x)}{h} \\
= &\lim_{h \rightarrow 0} \frac{g(f(x + h)) - g(f(x))}{f(x + h) - f(x)} * \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h} \\
= &\lim_{h \rightarrow 0} g'(f(x))  * f'(x)
\end{align}
$$
