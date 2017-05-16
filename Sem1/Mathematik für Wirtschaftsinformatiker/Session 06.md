# Session 6

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [4.2 Anwendung der Ableitung](#42-anwendung-der-ableitung)
	- [Definition](#definition)
	- [Lemma](#lemma)
		- [Notwendige Bedingung 1. Ordnung](#notwendige-bedingung-1-ordnung)
		- [Definition](#definition)
		- [Satz](#satz)
	- [Praktische Anwendung: Gewinnmaximierung](#praktische-anwendung-gewinnmaximierung)
		- [Beispiel](#beispiel)
			- [Annahme: **nur wir** produzieren (Monopol)](#annahme-nur-wir-produzieren-monopol)
			- [Annahme: Es gibt schon einen Produzenten (Menge: $q_1$).](#annahme-es-gibt-schon-einen-produzenten-menge-q1)
			- [Wir sind erster, aber es kommt einer nach](#wir-sind-erster-aber-es-kommt-einer-nach)
- [5. Integrale](#5-integrale)
	- [Definition](#definition)
	- [Regeln](#regeln)
	- [Definition](#definition)
	- [Beispiel](#beispiel)
	- [Bemerkung](#bemerkung)
	- [Satz](#satz)
	- [Skizze](#skizze)
	- [Satz](#satz)
	- [Skizze](#skizze)
	- [Regel](#regel)

<!-- /TOC -->

## 4.2 Anwendung der Ableitung
### Definition
$f : I \rightarrow \mathbb{R}$ hat in $a$ ein
* **lokales Minimum**, wenn es ein $\epsilon > 0$ gibt mit
$$
f(x) \geq f(a) \; \forall \; \lvert x - a \rvert < \epsilon
$$
* **lokales Maximum**, wenn es ein $\epsilon > 0$ gibt mit
$$
f(x) \leq f(a) \; \forall \; \lvert x - a \rvert < \epsilon
$$

### Lemma
#### Notwendige Bedingung 1. Ordnung
Ist $f$ differenzierbar und hat $f$ in $a$ ein lokales Extremum, dann ist $f'(a) = 0$.  
(Notwendig: Gilt für jedes Extremum, aber nicht immer wenn erfüllt bedeutet Extrempunkt)

#### Definition
Für $n \geq z \; (n \in \mathbb{N})$ heißt $f$ **$n$-mal differenzierbar**, wenn $f$ $n - 1$ mal differenzierbar ist und für die $n - 1$-te Ableitung gilt, dass diese differenzierbar ist.
$$
\frac{d^nf}{dx^n} (a) = f^{(n)}(a) = (f^{(n - 1)}(a))'
$$
$$
f^{(2)}(a) = f''(a) = \lim_{h \rightarrow 0} \frac{f'(a + h) - f'(a)}{h}
$$
$$
f^{(3)}(a) = f'''(a) = \lim_{h \rightarrow 0} \frac{f''(a + h) - f''(a)}{h}
$$

#### Satz
Ist $f : I \rightarrow \mathbb{R}$ 2-mal differenzierbar und ist $f'(a) = 0$, dann gilt:  
Ist $f''(a) > 0$, dann hat $f$ ein lokales Minimum $a$.

### Praktische Anwendung: Gewinnmaximierung
$$\text{Gewinn} = \text{Umsatz} - \text{Herstellungskosten}$$

Menge $q$

$$G(q) = p * q - c(q)$$

Maximum von $G(a)$ finden:

$$G'(q) = p - c'(q) = 0$$

#### Beispiel
$$c(q) = c * q,\;c'(q) = c$$
$$G'(q) = 0 \Leftrightarrow p = c$$
("Vollkommener Markt" $\Rightarrow$ Preis ist da und ändert sich nicht, konstant)

##### Annahme: **nur wir** produzieren (Monopol)
$$p(q) = a - b * q \qquad a, b > 0$$
$$G(q) = p * q - c* q) = (a - b * q) * q - c * q$$

$$
\begin{align}
\frac{db}{dq} &= a - bq - bq - c = 0 \\
&\Leftrightarrow 2bq = a - c \\
&\Leftrightarrow q = \frac{a - c}{2b}
\end{align}
$$

##### Annahme: Es gibt schon einen Produzenten (Menge: $q_1$).
Wie viel produzieren wir?  
Der Preis ergibt sich aus der gemeinsamen Menge.

$$
p(q) = a - b(q + q_1)
$$
$$
\begin{align}
G(q) &= q * p - cq \\
&= q * (a - b * (q + q_1)) - cq \rightarrow \text{max} \\
G'(q) &= a - b * (q + q_1) + q * (-b) - c = a - c - b * q_1 - 2 * bq = 0
\end{align}
$$
**$$
\frac{a - c - bq_1}{2b} = q
$$**

##### Wir sind erster, aber es kommt einer nach
$$G(q) = q * p - c * q$$
$$
\begin{align}
p(q) &= a - b * (q + q_2) \\
&= a - b * (q + \frac{a - c - b * q}{2b})
\end{align}
$$

$$
G(q) = q * \left[a - b\left[q + \frac{a - c - b * q}{2b}\right]\right] - cq
$$

$$
\begin{align}
G'(q) &= \left[a - bq - \frac{a - c - b * q}{2}\right] + q * \left[-b + \frac{b}{2}\right] - c \\
&= \frac{a}{2} + \frac{c}{2} - \frac{bq}{2} - bq + \frac{bq}{2} - c \\
&= \frac{a - c}{2} - bq = 0 \\
&\Leftrightarrow q_1 = \frac{a - c}{2b} \\ \\
&\Rightarrow q_2 = \frac{a - c - b * \frac{a - c}{2b}}{2b} = \frac{a - c}{4b}
\end{align}
$$

## 5. Integrale
### Definition
Fläche zwischen $f$ und $x$-Achse über dem Intervall $[a, b]$ ist
$$
\int_a^bf(x)dx
$$

### Regeln
* $$
\int_a^bf(x)dx + \int_b^cf(x)dx = \int_a^cf(x)dx
$$
* $$
\int_a^bf(x)+g(x)dx = \int_a^bf(x)dx + \int_a^bg(x)dx
$$

### Definition
Sind $f, F : [a, b] \rightarrow \mathbb{R}$ Funktionen, dann heißt $F$ **Stammfunktion von $f$** ($\int f$) falls $F'(x) = f(x)$ gilt.

### Beispiel
$$
\begin{align}
&f(x) = 2x \\
\Rightarrow &F(x) = x^2 \text{ ist _eine_ Stammfunktion.} \\
\Rightarrow &F_1(x) = x^2 + c \qquad c \in \mathbb{R}
\end{align}
$$

### Bemerkung
Stamfuktion ist nur bis auf Konstante bestimmbar.

### Satz
Ist $f : [a, b] \rightarrow \mathbb{R}$ eine Funktion, dann ist
$$
F : [a, b] \rightarrow R \\
F(x) = \int_a^xf(y)dy
$$
eine Stammfunktion.

### Skizze
$$
\begin{align}
&\frac{F(x + h) - F(x)}{h} = \frac{\int_a^{x + h}f(y)dy - \int_a^xf(y)dy}{h} \\
= &\frac{\int_x^{x + h}f(y)dy}{h} \\
\end{align}
$$

### Satz
Ist $f: [a, b] \rightarrow \mathbb{R}$ eine Funktion und ist $\phi$ eine Stammfunktion von $f$. Dann gilt
$$
\int_a^bf(x)dx = \phi(b) - \phi(a) =: [\phi]_a^b
$$

### Skizze
$$
\phi_1(x) \Rightarrow \phi_2(x) = \phi_1(x) + c \\
\phi_1, \phi_2 \text{ sind Stammfunktionen von }f
$$

$$
\phi_2(b) - \phi_2(a) = \phi_1(b) + c - (\phi_1(a) + c) = \phi_1(b) - \phi_1(a)
$$

* Für die Stammfunktion aus dem Hauptsatz:

$$
\begin{align}
F(a) &= \int_a^af(x)dx = 0 \\
F(b) &= \int_a^bf(x)dx \\
F(b) - F(a) &= \int_a^bf(x)dx - 0
\end{align}
$$

### Regel
Für Funktionen $f, g: [a, b] \rightarrow \mathbb{R}$ gilt
* $$
\int_a^bf'(x)g(x)dx = [fg]_a^b - \int_a^bf(x)g'(x)dx
$$
* $$
\int_a^bf(\varphi(t)) \varphi'(t)dt = \int_{\varphi(a)}^{\varphi(b)}f(x)dx
$$

Mit der Produktregel der Differentialrechnung:
$$
\begin{align}
&\int_a^b(fg)'(x)dx = \int_a^bf'(x)g(x)dx + \int_a^bf(x)g'(x)dx \\
\Leftrightarrow &\int_a^b(fg)'(x)dx - \int_a^bf(x)g'(x)dx = \int_a^bf'(x)g(x)dx
\end{align}
$$
