# Session 8

## Vektorraum
### Definition
Sei $V$ ein Vektorraum und $B \subset V$.  
Ist $B$ eine maximal linear unabhängige Teilmenge, dann heißt $B$ **Basis** von $V$.

### Notation
$$
\begin{align}
&e_i := \text{i-ter Standardbasisvektor oder Einheitsvektor} \\
&e_i := \begin{bmatrix}0\\ \ldots\\ 1 \text{(i)}\\ \ldots\\ 0\end{bmatrix}
\end{align}
$$

### Beispiel
1. $$
\begin{align}
&V = \mathbb{R}^3 \\
&B = \left\{e_1, e_2, e_3, e_1 + e_2 \right\}
\end{align}
$$ &rarr; Keine Basis, da **nicht** linear unabhängig:  
$$
\vec{0} = 1 * e_1 + 1 * e_2 - 1 * (e_1 + e_2)
$$

2. $$
\begin{align}
&V = \mathbb{R}^3 \\
&B = \left\{ e_1, e_2 \right\}
\end{align}
$$ &rarr; Keine Basis, da nicht maximal.  
$$
B' = \left\{ e_1, e_2, e_3\right\} \supset B$$ und **linear abhängig**.

3. $$
\begin{align}
&V = \mathbb{R}^3 \\
&B = \left\{ e_1, e_2, e_3\right\}\\
\end{align}
$$ &rarr; Ist Basis linear unabhängig:  
Nehmen wir ein $v \in \mathbb{R}^3$ hinzu.
$$
\Rightarrow \vec{0} = -v_1 * e_1 - v_2 * e_2 - v_3 * e_3 + v
$$
