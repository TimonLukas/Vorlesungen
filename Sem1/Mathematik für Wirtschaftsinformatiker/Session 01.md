# Einführung

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Referent](#referent)
- [1. Reelle Funktionen](#1-reelle-funktionen)
	- [Definition](#definition)
	- [Beispiel](#beispiel)
- [Mengen](#mengen)
	- [Definition](#definition)
	- [Beispiel](#beispiel)
- [Injektiv, Surjektiv](#injektiv-surjektiv)
	- [Definition](#definition)
	- [Formal](#formal)
	- [Beispiel](#beispiel)
	- [Bemerkung](#bemerkung)
- [1.1 Polynome und Nullstellen](#11-polynome-und-nullstellen)
	- [Definition](#definition)
	- [Nullstellenbestimmung](#nullstellenbestimmung)
	- [Beispiele Produktsummen:](#beispiele-produktsummen)
	- [Numerische Verfahren](#numerische-verfahren)
		- [Intervallschachtelung (Bisektionsverfahren)](#intervallschachtelung-bisektionsverfahren)
		- [Sekantenverfahren](#sekantenverfahren)
		- [Newtonverfahren](#newtonverfahren)

<!-- /TOC -->

## Referent
* Michael Tichy

## 1. Reelle Funktionen

### Definition
Seien $M, N$ zwei nicht leere Mengen, dann heißt eine Vorschrift, die jedem $x \in M$ eindeutig ein $y \in N$ zuordnet eine *Funktion* von $M$ nach $N$.  
Das dem Element $x$ zugeordnete Element $y$ nennen wir auch $f(x)$ oder **Wert** von $x$.

Schreibe:
  $$f: M \to N$$$$f(x) = y$$

M ist die **Definitionsmenge**.
N ist die **Zielmenge**.

### Beispiel
$$M = \{A, B, C\}$$$$N = \{1, 2, 3\}$$
$$f(x) =
\begin{cases}
1, & \text{falls x = A} \\
2, & \text{sonst}
\end{cases}$$

## Mengen

### Definition
Seien $M, N$ zwei beliebige nicht leere Mengen und $f: M \to N$ eine Funktion.  
Dann ist die Menge

$$
f(M) := \{y \in N : \exists \; x \in M : f(x) = y\}
$$

die Bildmenge von $M$ unter $f$.

Ist $y \in f(M)$, dann ist die Menge

$$
x := \{x \in M : f(x) \in y\}
$$

das Urbild von $y$ in $M$ unter $f$.

### Beispiel
$$M = \{1, 2, 3\}$$$$N = \{1, 2, \ldots, 10\}$$$$f(x) = x^2$$$$\color{red}{f(M) = \{1, 4, 9\}}$$
$$y = \{1, 9\}$$$$x = \{1, 2, 3\}$$

## Injektiv, Surjektiv

### Definition
Seien $M, N$ zwei beliebige nicht leere Mengen und $f: M \to N$ eine Funktion.  
Dann heißt $f$ **surjektiv**, falls es zu jedem $y$ ein $x \in M$ gibt mit $f(x) = y$.

$f$ heißt **injektiv (eineindeutig)**, falls für alle $x1, x2 \in M$ aus $f(x_1) = f(x_2)$ schon $x_1 = x_2$ folgt.

### Formal
* Surjektiv: $$\forall \; y \in N \; \exists \; x \in M : f(x) = y$$
* Injektiv: $$\forall \; x_1, x_2 \in M : f(x_1) = f(x_2) \Rightarrow x_1 = x_2$$

### Beispiel
$M = \{1, 2, 3\}$ $N = \{A, B, C\}$

$f(1) = A$ | $g(1) = C$  
$f(2) = B$ | $g(2) = B$  
$f(3) = A$ | $g(3) = A$  
~~injektiv~~&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; injektiv

### Bemerkung
Funktionen, die **injektiv** und **surjektiv** sind, heißen **bijektiv**.  
Eine **reelle Funktion** ist eine Funktion, bei der $M, N$ die reellen Zahlen ($\mathbb{R} $) sind.

## 1.1 Polynome und Nullstellen
### Definition
Eine Funktion der Form
$$P(x) := \sum_{i=0}^n a_i x^i := a_0 + a_1 x^1 + \ldots + a_n x^n$$$$a_i \in \mathbb{R}, a_n \neq 0$$
heißt **(reelles) Polynom** der **Ordnung n**.  
Im Falle von $a_n = 1$ heißt das Polynom **normiert**.

### Nullstellenbestimmung
Nullstellen bei normierten Polynomen der Ordnung 2:
$$P(x) = x^2 + px + q, \,\, p, q \in \mathbb{R}$$
Nullstellen:
$$x_{1/2} = -\frac{p}{2} \pm \sqrt{(\frac{p}{2})^2 - q}$$
Höhere Polyone: Raten!
$$P(x) = x^3 + 2x^2 - x - 2$$
Rate: $x = 1$ Stimmt  
Über Polynomdivison:
$$(x^3 + 2x^2 - x - 2) = (x - 1) * (x + 1) * (x + 2)$$
Allgemein lassen sich Polynome wie folgt darstellen:
$$P(x) = \sum_{i = 0}^n a_i x^i = \prod_{k = 1}^{m_1} (b_k - x) * \prod_{k = 1}^{m_2} (x^2 - c_k x - d_k)$$
Wobei die Polynome $x^2 - c_k x - d_k$ keine Nebenstellen haben.

### Beispiele Produktsummen
$$
\begin{align}
& \prod_{k = 1}^n a_k = a_1 * a_2 * \ldots * a_n \\
& \prod_{k = 1}^5 k = 1 * 2 * 3 * 4 * 5 = 120 \\
& \prod_{k = 2}^7 2 = 2 * 2 * 2 * 2 * 2 * 2 = \ldots
\end{align}
$$
### Numerische Verfahren
#### Intervallschachtelung (Bisektionsverfahren)
Grafik 1

Vorgabe:  
2 Werte $x_1, x_2$ mit $f(x_1) < 0$ und $f(x_2) > 0$

**Voraussetzungen**: Ein Intervall $[a, b]$ mit
$$f(a) * f(b) < 0$$ (und eine stetige Funktion).
$$m = a + \frac{b - a}{2} = \frac{b + a}{2}$$ ist die Mitte des Intervalls $[a, b]$.  
* Wenn $f(a) * f(b) > 0$ => Abbruch
* Sonst
  * Wenn $f(a) * f(b) = 0$ => Fertig
  * Sonst
    * $m = \frac{a + b}{2}$
    * Wenn $f(a) * f(m) < 0$ dann
      * $b = m$
    * Sonst
      * $a = m$
* Anfang. Bis $\lvert b - a \rvert < \epsilon$

#### Sekantenverfahren
Grafik 2

**Idee:**
1. Gehe von 2 Punkten $x_0, x_1$ aus.
2. Lege die Gerade $y_1$ durch die Punkte $(x_0, f(x_0)), (x_1, f(x_1))$
3. Bestimme $x_2$ aus $y_1(x_2) = 0$
4. Lege die Gerade $y_2(x)$ durch die Punkte $(x_1, f(x_1)), (x_2, f(x_2))$
5. $\ldots$

**Allgemein:**
* $y_n(x)$ ist die Gerade durch $(x_{n-1}, f(x_{n-1})), (x_n, f(x_n))$
* Bestimme $x_{n + 1}$ aus $y_n(x_{n + 1}) = 0$.

$$
\begin{align}
& y_n(x) = \frac{f(x_n) - f(x_{n - 1})}{x_n - x_{n - 1}} * (x - x_n) + f(x_n) \\
& y_n(x_{n + 1}) = 0 = \frac{f(x_n) - f(x_{n - 1})}{x_n - x_{n - 1}} * (x_{n + 1} - x_n) + f(x_n) \\
\Leftrightarrow & -f(x_n) = \frac{f(x_n) - f(x_{n - 1})}{x_n - x_{n - 1}} * (x_{n + 1} - x_n) \\
& -f(x_n) = \frac{(x_n - x_{n - 1})}{f(x_n) - f(x_{n - 1})} = x_n + 1 - x_n \\
& x_n - f(x_n) * \frac{(x_n - x_{n - 1})}{f(x_n) - f(x_{n - 1})} = x_{n + 1}
\end{align}
$$

* Starte mit $x_k$
* Wenn $f(x_k) \neq 0$ Dann
$$x_{k + 1} = x_k - f(x_k) * \frac{x_k - x_{k - 1}}{f(x_k) - f(x_{k - 1})}$$
* Anfang. Bis $\lvert f(x_k) \rvert < \epsilon$

#### Newtonverfahren
Grafik 3

1. Gehe von $(x_0, f(x_0))$ aus und bestimme $f'(x_0)$
2. Konstruiere die Tangente an $(x_0, f(x_0))$
$$t_0(x) = f'(x_0) * (x - x_0) + f(x_0)$$
3. Bestimme $x_1$ über
$$
\begin{align}
& t_0(x_1) = 0 \\
\Leftrightarrow & f'(x_0) * (x_1 - x_0) + f(x_0) = 0 \\
\Leftrightarrow & f'(x_0) * (x_1 - x_0) = -f(x_0) \\
\Leftrightarrow & x_1 - x_0 = - \frac{f(x_0)}{f'(x_0)} \\
\Leftrightarrow & x_1 = x_0 - \frac{f(x_0)}{f'(x_0)}
\end{align}
$$
4. Bis $\lvert f(x_k) \rvert < \epsilon$
