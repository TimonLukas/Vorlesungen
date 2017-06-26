# Session 02

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Mengen](#mengen)
  * [Operationen](#operationen)
    * [Vereinigung](#vereinigung)
    * [Durchschnitt](#durchschnitt)
    * [Distributivgesetze](#distributivgesetze)
  * [Anzahl der Elemente einer Menge](#anzahl-der-elemente-einer-menge)
  * [Siebformel](#siebformel)
  * [Satz von Sylvester](#satz-von-sylvester)
  * [Differenzmenge](#differenzmenge)
  * [Komplementmenge](#komplementmenge)
  * [Satz (De Morgan)](#satz-de-morgan)
  * [Das kartesische Produkt von Mengen](#das-kartesische-produkt-von-mengen)

<!-- tocstop -->

## Mengen
### Operationen
#### Vereinigung
**Definition**: Die Vereinigung von zwei Mengen $M_1$ und $M_2$ ist:
$$
M_1 \cup M_2 = \{x | x \in M_1 \text{ oder } x \in M_2\}
$$

**Beispiel**:
$$
\{1, 2, 3\} \cup \{3, 4\} = \{1, 2, 3, 4\}
$$

Sind $M_1, M_2, \ldots, M_n n$ Mengen, dann ist

$$
\cup_{i = 1}^n M_i = $M_1 \cup M_2 \cup \ldots \cup M_n
$$

Es gelten folgende Rechenregeln (müssen eigentlich bewiesen werden):
1. $M \cup M = M$ (Idempotenzgesetz)
2. $M_1 \cup M_2 = M_2 \cup M_1$ (Kommutativgesetz)
3. $M_1 \cup (M_2 \cup M_3)) = (M_1 \cup M_2) \cup M_3$ (Assoziativgesetz)
4. $M \cup \emptyset = M$, $\emptyset$ ist das neutrale Element der Vereinigungsoperation

Oft ist es hilfreich, sich die Mengenoperationen mit Hilfe von **VENN**-Diagrammen klarzumachen.


#### Durchschnitt
**Definition**:
a) Der Durchschnitt zweier Mengen $M_1$ und $M_2$ ist
$$
M_1 \cup M_2 = \{x | x \in M_1 \text{ und } x \in M_2\}
$$

b) Falls $M_1 \cap M_2 = \emptyset$, dann nennt man $M_1$ und $M_2$ **disjunkt**.

**Beispiel**:
$$\{1, 2, 3, 4\} \cap \{2, 4, 6, 8\} = \{2, 4\}$$

$$
\cap_{i = 1}^n M_i = M_1 \cap M_2 \cap \ldots \cap M_n
$$

**Rechenregeln**:
1. $M \cap M = M$ (Idempotenzgesetz)
2. $M_1 \cap M_2 = M_2 \cap M_1$ (Kommutativgesetz)
3. $M_1 \cap (M_2 \cap M_3) = (M_1 \cap M_2) \cap M_3 (Assoziativgesetz)
4. $M \cap \emptyset = \emptyset$


#### Distributivgesetze
Es gelten die folgenden **Distributivgesetze**:
$$
M_1 \cup (M_2 \cap M_3) = (M_1 \cup M_2) \cap (M_1 \cup M_3)\\
M_1 \cap (M_2 \cup M_3) = (M_1 \cap M_2) \cup (M_1 \cap M_3)
$$


### Anzahl der Elemente einer Menge
Man bezeichnet mit $| M |$ die Anzahl der Elemente der Menge $M$. Dies nennt man auch **Kardinalität**.

Sind $M_1, M_2$ endliche Mengen, dann ist:
$$
|M_1 \cup M_2| = |M_1| + |M_2| - |M_1 \cap M_2|
$$


### Siebformel
**Beispiel**:
$$
M_1 = \{1, 2, 3, 4\}; |M_1| = 4\\
M_2 = \{3, 4, 6, 7\}; |M_2| = 4\\
$$

$$
|M_1| + |M_2| = 8\\
M_1 \cup M_2 = \{1, 2, 3, 4, 6, 7\}; |M_1 \cup M_2| = 6\\
M_1 \cap M_2 = \{3, 4\}\\
\Rightarrow |M_1 \cup M_2| = |M_1| + |M_2| - |M_1 \cup M_2|
$$


### Satz von Sylvester
Seien $M_1, M_2, \ldots, M_n n$ Mengen (endlich); dann gilt:
$$
|M_1 \cup M_2 \cup \ldots \cup M_n|\\
= \sum_{i = 1}^n (-1)^{i - 1} k_i
$$
mit
$$
\begin{align}
k_1 &= |M_1| + |M_2| + \ldots + |M_n|\\
k_2 &= \sum_{i = 1; j = 1; i \neq j}^{n, n} |M_i \cap M_j|\\
k_3 &= \sum_{i, j, k = 1; i < j < k} |M_i \cap M_j \cap M_k|\\
\ldots\\
k_n &= |M_1 \cap M_2 \cap \ldots \cap M_n|
\end{align}
$$

**Beispiel**:
$$
\begin{align}
&M_1 = \{1, 2, 3, 4, 5\}\\
&M_2 = \{1, 3, 5, 7, 9\}\\
&M_3 = \{3, 5, 7, 11\}\\
&M_4 = \{1, 3, 9, 12\}
\end{align}
$$

$$
|M_1 \cup M_2 \cup M_3 \cup M_4| = \sum_{i = 1}^4 (-1)^{i - 1} k_i\\
= k_1 - k_2 + k_3 - k_4
$$

$$
k_1 = |M_1| + |M_2| + |M_3| + |M_4|\\
= 5 + 5 + 4 + 4 = 18
$$

$$
k_2 = \sum_{i, j = 1; i < j}^4 |M_i \cap M_j|\\
= |M_1 \cap M_2| + |M_1 \cap M_3| + |M_1 \cap M_4| + |M_2 \cap M_3| + |M_2 \cap M_4| + |M_3 \cap M_4|\\
(= \text{ alle möglichen 2er-Schnitte von 4 Mengen})\\
= |\{1, 3, 5\}| + |\{3, 5\}| + |\{1, 3\}| + |\{3, 5, 7\}| + |\{1, 3, 9\}| + |\{3\}|\\
= 14
$$

$$
k_3 = \sum_{i, j, k = 1}^4 |M_i \cap M_j \cap M_k|\\
= |M_1 \cap M_2 \cap M_3| + |M_1 \cap M_2 \cap M_4| + |M_1 \cap M_3 \cap M_4| + |M_2 \cap M_3 \cap M_4|\\
= |\{3, 5\}| + |\{1, 3\}| + |\{3\}| + |\{2, 3, 4\}|\\
= 6
$$

$$
k_4 = |M_1 \cap M_2 \cap M_3 \cap M_4| = |\{3\}| = 1
$$

$$
M_1 \cup M_2 \cup M_3 \cup M_4 = \{1, 2, 3, 4, 5, 7, 9, 12\}\\
|M_1 \cup \ldots \cup M_4| = 9
$$

$$
k_1 - k_2 + k_3 - k_4 = 18 - 14 + 6 - 1 = 9
$$


### Differenzmenge
Seien $M_1, M_2$ zwei Mengen; dann ist $$
M_1 \backslash M_2 = \{x | x \in M_1 \text{ und } x \notin M_2\}
$$
die **Differenzmenge**.

**Beispiel**:
$$
M_1 = \{1, 2, 3, 4\}, M_2 = \{3, 4, 5\}\\
M_1 \backslash M_2 = \{1, 2\}\\
M_2 \backslash M_1 = \{5\}\\
M_1 \backslash M_2 \neq M_2 \backslash M_1
$$

$$
M \backslash M = \emptyset\\
M \backslash \emptyset = M\\
\emptyset \backslash M = \emptyset
$$


### Komplementmenge
Sei $M_1$ Teilmenge von $M$. Das Komplement $\overline{M_1}$ von $M_1$ bezüglich der Obermenge $M$ sind alle Elemente von $M$, die nicht $M_1$ sind:
$$
\overline{M_1} = \{x \in M | x \notin M_1\}
$$

Es gilt:
$$
M_1 \cup \overline{M_1} = M\\
M_1 \cap \overline{M_1} = \emptyset\\
\overline{M} = \emptyset\\
\overline{\emptyset} = M\\
\overline{(\overline{M_1})} = M_1
$$


### Satz (De Morgan)
Seien $M_1, M_2$ zwei Mengen, dann gilt:
$$
\overline{M_1 \cup M_2} = \overline{M_1} \cap \overline{M_2}\\
\overline{M_1 \cap M_2} = \overline{M_1} \cup \overline{M_2}
$$

**Beispiel**:
$$
\text{if(x >= 1 && x <= 3)}
$$

Negieren der Bedingung $\text{x >= 1 && x <= 3}$:

$$
\text{if(x < 1 || x > 3)}
$$

**Beispiel**:
$$
\begin{align}
M &= \{1, \ldots, 10\}\\
M_1 &= \{1, 2, 3, 4\}\\
M_2 &= \{3, 4, 5, 6\}
\end{align}
$$

$$
M_1 \cup M_2 = \{1, 2, 3, 4, 5, 6\}\\
\overline{M_1 \cup M_2} = \{7, 8, 9, 10\}
$$

$$
\overline{M_1} = \{5, 6, 7, 8, 9, 10\}\\
\overline{M_2} = \{1, 2, 7, 8, 9, 10\}\\
\overline{M_1} \cup \overline{M_2} = \{1, 2, 5, 6, 7, 8, 9, 10\}\\
\overline{M_1} \cap \overline{M_2} = \{7, 8, 9, 10\} = \overline{M_1 \cup M_2}
$$

**Kleine Übung**
$$
\begin{align}
M &= \{1, 2, \ldots, 10\}\\
M_1 &= \{1, 2, 3, 4\}\\
M_2 &= \{3, 4, 5, 6, 7\}
\end{align}
$$

Man gebe die folgenden Mengen explizit an.

|Menge                                            |Ergebnis               |
|-------------------------------------------------|-----------------------|
|$\overline{M_1}$                                 |$\{5, \ldots, 10\}$    |
|$\overline{M_2}$                                 |$\{1, 2, 8, 9, 10\}$   |
|$M_1 \cup M_2$                                   |$\{1, \ldots, 7\}$     |
|$M_1 \backslash \overline M_2$                   |$\{3, 4\}$             |
|$\overline{M_1 \backslash M_2}$                  |$\{3, \ldots, 10\}$    |
|$\overline{M_2} \backslash M_1$                  |$\{8, 9, 10\}$         |
|$(M_1 \backslash M_2) \cup (M_2 \backslash M_1)$ |$\{1, 2, 5, 6, 7\}$    |
|$(M_1 \backslash M_2) \cap (M_2 \backslash M_1)$ |$\{\}$                 |
|$M_1 \cap (M_1 \backslash M_2)$                  |$\{1, 2\}$             |


### Das kartesische Produkt von Mengen
Seien $M_1$ und $M_2$ zwei Mengen, dann ist
$$
M_1 \times M_2 = \{(m_1, m_2)|m_1 \in M_1 \text{ und } m_2 \in M_2\}
$$

ist die Menge der **geordneten Paare**.

**Beispiel**:
$$
M_1 = \{1, 2\}, M_2 = \{a, b\}\\
M_1 \times M_2 = \{(1, a), (1, b), (2, a), (2, b)\}
$$

Das kartesische Produkt von $n$ Mengen $M_1, \ldots, M_n$ ist
$$
M_1 \times \ldots \times M_n = \{(m_1, m_2, \ldots m_n) | m_i \in M_i (i = 1, \ldots, n)\}
$$

**Beispiel**:
$$
\mathbb{R}^2 = \mathbb{R} \times \mathbb{R} = \{(x, y) | x \in \mathbb{R}, y \in \mathbb{R}\}
$$

**Übung** (**WINK MIT ZAUNPFAHL**)
$M_1 = \{-2, -1, 0\}; M_2 = \{1, 2\}$

|Term                              |Ergebnis|
|----------------------------------|--------|
|$\vert M_1 \times M_2\vert$       |$6$
|$\vert p(M_1)\vert$               |$8$
|$\vert p(M_1) \times p(M_2)\vert$ |$32$
|$\vert p(M_1 \times M_2)\vert$    |$64$

Wahr oder falsch?

|Term                         |Ergebnis|
|-----------------------------|--------|
|$\vert\emptyset\vert \in M_1$|Wahr    |
|$\emptyset \in p(M_1)$       |Wahr    |
|$M_1 \subseteq p(M_1)$       |Falsch  |
