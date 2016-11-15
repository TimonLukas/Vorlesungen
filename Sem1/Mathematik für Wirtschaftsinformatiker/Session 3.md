# Session 3

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Übungsaufgaben](#übungsaufgaben)
	- [2. Konvergenz der Folge $(a_n) = \frac{1}{n^2}$](#2-konvergenz-der-folge-an-frac1n2)
		- [1. Aus der Definition heraus](#1-aus-der-definition-heraus)
			- [Beispiel](#beispiel)
			- [Allgemein](#allgemein)
		- [2. Mit einem geeigneten Satz](#2-mit-einem-geeigneten-satz)
	- [4. Konvergenzen](#4-konvergenzen)
		- [4.1 $c_n = a_n + b_n \rightarrow c$](#41-cn-an-bn-rightarrow-c)
		- [4.2 $d_n = a_n * b_n \rightarrow d$](#42-dn-an-bn-rightarrow-d)
	- [5. Injektiv, Surjektiv](#5-injektiv-surjektiv)
		- [5.1 Nicht injektiv, nicht surjektiv](#51-nicht-injektiv-nicht-surjektiv)
		- [5.2 Injektiv, nicht surjektiv](#52-injektiv-nicht-surjektiv)
		- [5.3 Nicht injektiv, surjektiv](#53-nicht-injektiv-surjektiv)
		- [5.4 Injektiv, Surjektiv](#54-injektiv-surjektiv)
- [2.2 Reihen](#22-reihen)
	- [Beispiele](#beispiele)
	- [Definition](#definition)
	- [Satz](#satz)
		- [Skizze](#skizze)
	- [Beispiele](#beispiele)
		- [Geometrische Reihe](#geometrische-reihe)
			- [Behauptung](#behauptung)
			- [Beweis](#beweis)
			- [Ist die geometrische Reihe konvergent?](#ist-die-geometrische-reihe-konvergent)
			- [Fälle](#fälle)
		- [Weitere Beispiele](#weitere-beispiele)
- [2.3 Ökonomische Anwendungen](#23-ökonomische-anwendungen)
	- [2.3.1 Zinsen](#231-zinsen)
		- [Sparplan](#sparplan)
		- [Rente](#rente)
		- [Ewige Rente (z. B. Aktiendividende)](#ewige-rente-z-b-aktiendividende)
		- [Negativer Zins](#negativer-zins)

<!-- /TOC -->

## Übungsaufgaben

### 2. Konvergenz der Folge $(a_n) = \frac{1}{n^2}$
#### 1. Aus der Definition heraus
Zur Erfüllung der Konvergenz muss gelten: $\forall \; \epsilon > 0 \; \exists \; N \in \mathbb{N} : n \geq N \Rightarrow \lvert a - a_n \rvert < \epsilon$  
These: $(a_n)$ ist konvergent gegen 0  
##### Beispiel
Es sei $\epsilon = 1$  
$$
\begin{align}
\lvert 0 - a_n \rvert < 1 \Leftrightarrow & \lvert a_n \rvert < 1 \\
& \lvert a_N \rvert = 1 \Rightarrow \lvert \frac{1}{N^2} \rvert \Leftrightarrow N = 1
\end{align}
$$
##### Allgemein  
$$
\begin{align}
\lvert 0 - a_n \rvert < \epsilon \Leftrightarrow & \lvert a_n \rvert < \epsilon \\
& \lvert a_N \rvert = \epsilon \Rightarrow \lvert \frac{1}{N^2} \rvert \Leftrightarrow \frac{1}{\epsilon} = N^2 \Leftrightarrow \sqrt{\frac{1}{\epsilon}} = N \Rightarrow n \geq \sqrt{\frac{1}{\epsilon}}
\end{align}
$$
oder  
Sei $\epsilon > 0$ beliebig
$$
\lvert a_n - 0 \rvert = \frac{1}{n^2} \stackrel{für \; n \geq N}{\leq} \frac{1}{n} < \epsilon
$$

#### 2. Mit einem geeigneten Satz
$$
\left.
\begin{array}{l}
a_n \rightarrow &a\\
b_n \rightarrow &b
\end{array}
\right\}
\begin{align}
&a_n * b_n \rightarrow a * b \\
&a_n + b_n \rightarrow a + b
\end{align}
$$
Aus der Vorlesung:
$$
\frac{1}{n} \rightarrow 0 \\
\frac{1}{n^2} = \frac{1}{n} * \frac{1}{n}
$$
wegen $\frac{1}{n} \rightarrow 0$ folgt  
für $a_n = b_n = \frac{1}{n} : a_n * b_n \rightarrow 0 * 0 = 0$

### 4. Konvergenzen
#### 4.1 $c_n = a_n + b_n \rightarrow c$
$c_n = a_n + b_n \rightarrow c \stackrel{?}{\Rightarrow} a_n, b_n$ sind konvergent  
$a_n = -n, b_n = n$  
$\Rightarrow c_n = 0 \rightarrow 0$
#### 4.2 $d_n = a_n * b_n \rightarrow d$
$d_n = a_n * b_n \rightarrow d \stackrel{?}{\Rightarrow} a_n, b_n$ sind konvergent  
$a_n = \frac{1}{n}, b_n = n$  
$\Rightarrow d_n = 1 \rightarrow 1$

### 5. Injektiv, Surjektiv
$$
\begin{align}
&M = \{1, 2, 3\} \\
&N = \{A, B\} \\
&f: M \rightarrow N
\end{align}
$$
#### 5.1 Nicht injektiv, nicht surjektiv
$f(1) = f(2) = f(3) = A$  
* B kein Urbild $\Rightarrow$ nicht surjektiv
* A hat kein Urbild 1, 2
#### 5.2 Injektiv, nicht surjektiv
Nicht möglich, weil zu wenige Elemente in der Bildmenge vorhanden
#### 5.3 Nicht injektiv, surjektiv
$f(1) = A = f(2), f(3) = B$
#### 5.4 Injektiv, Surjektiv
Siehe 5.2 $\rightarrow$ nicht möglich

## 2.2 Reihen
Wir versuchen
$$
  \sum_{k = 0}^{\infty} a_k \qquad ,a_k \in \mathbb{R}
$$
einen Wert zuzuordnen.
### Beispiele
1.
$$
\begin{align}
&a_k =
\begin{cases}
1 &\text{für $k \leq 10$} \\
0 &sonst
\end{cases} \\
& \Rightarrow \sum_{k = 0}^{\infty} = 11 \\
& \stackrel{k = 0}{1} + \stackrel{k = 1}{1} + \ldots + 1 + \stackrel{k = 11}{1} + 0 + \ldots
\end{align}
$$
2.
$$
\begin{align}
&a_k = 1 \qquad \forall \; k \in \mathbb{N}_0 \\
&\sum_{k = 0}^{\infty} a_k \qquad \text{keine reelle Zahl zuordnenbar}
\end{align}
$$
3.
$$
\begin{align}
&a_k = (-1)^k \\
&\sum_{k = 0}^{\infty} a_k = \sum_{k = 0}^{\infty} (-1)^k = 1 - 1 + 1 - 1 + 1 - 1 \ldots
\end{align}
$$
### Definition
Sei $(a_k)$ eine Folge reeller Zahlen.  
Die Folge $A_n := \sum_{k = 0}^{n} a_k$ heißt **Folge der Partialsummen** oder **Reihe**.  
Die Reihe heißt **konvergent**, falls dies für die Folge der Partialsummen gilt.  
Ansonsten heißt sie **divergent**.
### Satz
Eine Reihe $\sum_{k = 0}^{\infty} a_k$ ist konvergent, wenn es ein $q < 1$ gibt mit
$$
\lvert \frac{a_{k + 1}}{a_k} \rvert \leq q \qquad \text{für fast alle $k \in \mathbb{N}$}
$$
Sie ist divergent, wenn es ein $q > 1$ gibt mit
$$
\lvert \frac{a_{k + 1}}{a_k} \rvert \geq q \qquad \text{für fast alle $k \in \mathbb{N}$}
$$
"Für fast alle" $:=$ Alle bis auf endlich viele Ausnahmen
#### Skizze
$$
\sum_{k = 0}^{\infty} a_k
$$
Es gibt ein $N \in \mathbb{N}$
$$
\begin{align}
&\lvert \frac{a_{k + 1}}{a_k} \rvert \leq q \qquad \forall \; k \geq N \\
&\sum_{k = 0}{N} a_k + \sum_{k = N + 1}^{\infty} a_k \stackrel{\text{siehe unten}}{\leq} \sum_{k = 0}^{\infty} a_k + \sum_{k = N + 1}^{\infty} q^{k - N} * a_N \\
&a_{N + 1} = \frac{a_{N + 1}}{a_N} * a_N \\
&a_{N + 2} = \frac{a_{N + 2}}{a_{N + 1}} * {a_{N + 1}}{a_N} * a_N \leq q * q * a_N \\
&a_{N + 5} = \frac{a_{N + 5}}{a_{N + 4}} * \ldots * \frac{a_{N + 1}}{a_N} * a_N \leq q^5 * a_N
\end{align}
$$
### Beispiele
#### Geometrische Reihe
$$
\begin{align}
&q \in \mathbb{R} \\
&\sum_{k = 0}^{\infty} q^k = q^0 + q^1 + q^2 + q^3 + \ldots \\
&A_n = \sum_{k = 0}^{n} q^k = q^0 + q^1 + \ldots + q^n
\end{align}
$$
##### Behauptung
$$ A_n =
\begin{cases}
\frac{1 - q^{n + 1}}{1 - q} & \text{für $q \neq 1$} \\
n + 1 & \text{für $q = 1$}
\end{cases}
$$
##### Beweis
1. Für $q = 1$ ist $A_n = \sum_{k = 0}^{n} 1 = n + 1$
2. Für $q \neq 1$  
$$
\begin{align}
A_n * (1 - q) = &(q^0 + q^1 + q^2 + q^3 + \ldots + q^{n - 1} + q^n) * (1 - q) \\
= &q^0 + q^1 + q^2 + q^3 + \ldots + q^{n - 1} + q^n - q^1 - q^2 - q^3 - \ldots - q^n - q^{n + 1} \\
= &q^0 - q^{n + 1} \\
\Rightarrow A_N = &\frac{q^0 - q^{n + 1}}{1 - q} = \frac{1 - q^{n + 1}}{1 - q}
\end{align}
$$

##### Ist die geometrische Reihe konvergent?
1. $q = 1: a_n = n + 1$ konvergent? Nein.
2. $q \neq 1: A_n = \frac{1 - q^{n + 1}}{1 - q}$  
$q = 0: A_n = 1$  
$q = 2: \frac{1 - 2}{-1} = 1, \frac{1 - 4}{-1} = 3, \frac{1 - 8}{-1} = 7, \ldots$  
$q = \frac{1}{2}: \frac{1 - \frac{1}{2}}{\frac{1}{2}} = 1, \frac{1 - \frac{1}{4}}{\frac{1}{2}} = \frac{6}{4}, \frac{1 - \frac{1}{8}}{\frac{1}{2}} = \frac{14}{8}$

##### Fälle
1. $\lvert q \rvert < 1: q^{n + 1} \rightarrow 0 \Rightarrow \frac{q^{n + 1}}{1 - q} \rightarrow 0$  
$\Rightarrow A_n \rightarrow \frac{1}{1 - q}$  
2. $\lvert q \rvert > 1:$ "geht gegen unendlich"  
Betrache $q > 1$  
Angenommen $A_n \leq n$ für alle $n \in \mathbb{N}$  
$\Leftrightarrow \frac{1 - q^{n + 1}}{1 - q} \leq n$  
$\Leftrightarrow 1 - q^{n + 1} \geq n * (1 - q) \qquad | + q^{n + 1} - n * (1 - q)$  
$\Leftrightarrow 1 - n * (1 - q) \geq q^{n + 1} \Large{\unicode{x21af}}$

#### Weitere Beispiele
$a_k = \frac{1}{k}, k \in \mathbb{N}$  
$a_0 = 1$

Betrachte die Reihe
$$
\sum_{k = 0}^{\infty} = 1 + 1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \ldots \rightarrow \infty
$$
Denn:
$$
\begin{align}
\frac{1}{2} &\geq \frac{1}{2} \\
\frac{1}{3} + \frac{1}{4} &\geq \frac{1}{2} \\
\frac{1}{5} + \frac{1}{6} + \frac{1}{7} + \frac{1}{8} &\geq \frac{1}{2} \\
\ldots
\end{align}
$$
## 2.3 Ökonomische Anwendungen
### 2.3.1 Zinsen
#### Sparplan
* Jedes Jahr 100€ zur Bank (Anfang)
* 10% Zinsen (p. a., Verzinsung der Zinsen)
* 5 Jahre

$$100 * (1,1)^5 + 100 * (1,1)^4 + 100 * (1,1)^3 + 100 * (1,1)^2 + 100 * (1,1)^1$$

$$
\begin{align}
&q = 1,1 \\
\sum_{k = 1}^5 &= 100 * (q)^k \\
&= 100 * \sum_{k = 1}^5 (q)^k \\
&= 100 * \left[\frac{1 - q^6}{1 - q} - 1\right] \\
&= 100 * \left[\frac{1 - q^6 - 1 + q}{1 - q}\right] \\
&= 100 * \left[\frac{q - q^6}{1 - q}\right] \\
&= 100 * q * \frac{1 - q^5}{1 - q}
\end{align}
$$

#### Rente
* i = 10%
* Es soll so viel eingezahlt werden, dass durch Zinsen 100€ pro Monat rauskommen
* Jahr 1: $x * 1,1 = 100$
* Jahr 2: $x * (1,1)^2 = 100$
* $\ldots$

$$
\begin{align}
\sum_{k = 1}^5 \frac{100}{(1,1)^k} &= 100 * \left[ \frac{1 - q^6}{1 - q} - 1 \right] = \left[\frac{q - q^6}{1 - q}\right] \ldots \\
& q = 1,1
\end{align}
$$

#### Ewige Rente (z. B. Aktiendividende)
$$
\begin{align}
&\sum_{k = 1}^{\infty} \frac{100}{(1,1)^k} = 100 * \sum_{k = 1}^{\infty} q^k \\
&= 100 * \left[\frac{1}{1 - q} - \frac{1 - q}{1 - q}\right] \\
&= 100 * \left[\frac{q}{1 - q}\right] \qquad 0 < q < 1!
\end{align}
$$

#### Negativer Zins
* i = -5%
* Jahr 1: $x * 0.95 = 100$
* Jahr 2: $x * (0.95)^2 = 100$
* $q = \frac{1}{0.95} > 1$

$$
100 * \sum_{k = 1}^{\infty} q^k \rightarrow \infty
$$
