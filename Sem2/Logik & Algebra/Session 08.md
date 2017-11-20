# Session 08

<!-- toc orderedList:0 depthFrom:2 depthTo:6 -->

* [Disjunktive Normalform](#disjunktive-normalform)
  * [Minimieren](#minimieren)
    * [KV-Diagramme für BOOLEsche Funktionen mit 2 Variablen](#kv-diagramme-für-boolesche-funktionen-mit-2-variablen)
      * [Kleine Übung (ZAUNHPFAHL)](#kleine-übung-zaunhpfahl)
    * [KV-Diagramme für BOOLEsche Funktionen mit drei Variablen](#kv-diagramme-für-boolesche-funktionen-mit-drei-variablen)
      * [Beispiel](#beispiel)
        * [Algebraisch Schritt für Schritt](#algebraisch-schritt-für-schritt)
      * [Anderes Beispiel](#anderes-beispiel)
    * [KV-Diagramme für Funktionen mit vier Variablen](#kv-diagramme-für-funktionen-mit-vier-variablen)
* [Schaltnetze](#schaltnetze)
  * [Definition](#definition)
  * [Schreibweise von Gattern](#schreibweise-von-gattern)
  * [Der Halbaddierer](#der-halbaddierer)
    * [Logik](#logik)
  * [Volladdierer](#volladdierer)
    * [Logik](#logik-1)

<!-- tocstop -->

## Disjunktive Normalform
Betrachte die folgende Schalttabelle:

|a|b|f(a, b)|
|-|-|-------|
|0|0|0      |
|0|1|1      |
|1|0|1      |
|1|1|1      |

Konstruiere die disjunktive Normalform:
$$
f_{DNF}(a, b) = (\overline{a} \land b) \lor (a \land \overline{b}) \lor (a \land b)
$$
hat als Schaltung 7 Gatter.
$$
= a \lor b
$$
hat als Schaltung ein Gatter.

Frage: Wie kann man Disjunktive Normalformen minimieren?

### Minimieren
Systematisches Prozedere: Die $\text{KARNAUGH-VEITCH}$-Diagramme (KV)!

#### KV-Diagramme für BOOLEsche Funktionen mit 2 Variablen
(**Fett** = kommt in Term vor)
|                  |$a$                       |$\overline{a}$                   |
|------------------|--------------------------|---------------------------------|
|**$b$**           |**$a \land b$**           |**$\overline{a} \land b$**       |
|**$\overline{b}$**|**$a \land \overline{b}$**|$\overline{a} \land \overline{b}$|

Benachbarte markierte Zellen sind Ergebnis

Algebraisch steht dieses Zusammenziehen für die folgenden Schritte:
* Aufschreiben:  
$f_{DNF}(a, b) = (\overline{a} \land b) \lor (a \land \overline{b}) \lor (a \land b)$  
* Idempotenzgesetz ($A \lor A = A$):  
$= (\overline{a} \land b) \lor (a \land \overline{b}) \lor (a \land b) \lor (a \land b)$
* Kommutativgesetz:  
$= \big[(\overline{a} \land b) \lor (a \land b)\big] \lor \big[(a \land \overline{b}) \lor (a \land b)\big]$
* Distributivgesetz:  
$= \big[(a \lor \overline{a}) \land b\big] \lor \big[a \land (\overline{b} \lor b)\big]$
* Komplementgesetz:  
$= \big[1 \land b\big] \lor \big[a \land 1\big]$
* Eins-Element:  
$= \big[b\big] \lor \big[a\big]$
* Ergebnis:
$= a \lor b$

##### Kleine Übung (ZAUNHPFAHL)
Minimieren Sie die $\text{BOOLE}$sche Funktion
$$
f(a, b) = (a \land b) \lor (\overline{a} \land \overline{b}) \lor (\overline{a} \land b)
$$

Verifizieren Sie das Ergebnis mit einer Schalttabelle.
* Aufschreiben:
$f_{DNF}(a, b) = (a \land b) \lor (\overline{a} \land \overline{b}) \lor (\overline{a} \land b)$
* Idempotenzgesetz:
$= (a \land b) \lor (\overline{a} \land \overline{b}) \lor (\overline{a} \land b) \lor (\overline{a} \land b)$
* Kommutativgesetz:
$= \big[(a \land b) \lor (\overline{a} \land b)\big] \lor \big[(\overline{a} \land b)  \lor (\overline{a} \land \overline{b})\big]$
* Distributivgesetz:
$= \big[(a \lor \overline{a}) \land b)\big] \lor \big[(b \lor \overline{b}) \land \overline{a}\big]$
* Komplementgesetz:
$= \big[1 \land b\big] \lor \big[1 \land \overline{a}\big]$
* Eins-Element:
$= \big[b\big] \lor \big[\overline{a}\big]$
* Ergebnis:
$= b \lor \overline{a}$

Schalttabelle $(a \land b) \lor (\overline{a} \land \overline{b}) \lor (\overline{a} \land b)$
|$a$|$b$|Ergebnis|
|---|---|--------|
|0  |0  |1       |
|0  |1  |1       |
|1  |0  |0       |
|1  |1  |1       |

Schalttabelle $b \lor \overline{a}$:
|$a$|$b$|Ergebnis|
|---|---|--------|
|0  |0  |1       |
|0  |1  |1       |
|1  |0  |0       |
|1  |1  |1       |

#### KV-Diagramme für BOOLEsche Funktionen mit drei Variablen
$$
f(a, b, c)
$$

|                  |$a \land b$|$\overline{a} \land b$|$\overline{a} \land \overline{b}$|$a \land \overline{b}$|
|------------------|-----------|----------------------|----------------------------------------------|----------------------|
|**$c$**           |           |                      |                     | |
|**$\overline{c}$**|           |                      |                     | |

##### Beispiel
$$
f(a, b, c) = (a \land b \land c) \lor (a \land \overline{b} \land c) \lor (\overline{a} \land b \land c) \lor (a \land b \land \overline{c}) \lor (\overline{a} \land b \land \overline{c})
$$

|                  |$a \land b$|$\overline{a} \land b$|$\overline{a} \land \overline{b}$|$a \land \overline{b}$|
|------------------|-----------|----------------------|----------------------------------------------|----------------------|
|**$c$**           |&check;|&check;|                     |&check;|
|**$\overline{c}$**|&check;|&check;|                     |       |

$$
f_{min} = b \lor (a \land c)
$$

###### Algebraisch Schritt für Schritt
* Gleichung aufschreiben:
$f_{DNF}(a, b, c) = (a \land b \land c) \lor (a \land \overline{b} \land c) \lor (\overline{a} \land b \land c) \lor (a \land b \land \overline{c}) \lor (\overline{a} \land b \land \overline{c})$
* Idempotenzgesetz:
$= (a \land b \land c) \lor (a \land b \land c) \lor (a \land \overline{b} \land c) \lor (\overline{a} \land b \land c) \lor (a \land b \land \overline{c}) \lor (\overline{a} \land b \land \overline{c})$
* Kommutativgesetz:
$= \big[(a \land b \land c) \lor (a \land \overline{b} \land c)\big] \lor \big[(a \land b \land c) \lor (\overline{a} \land b \land c) \lor (a \land b \land \overline{c}) \lor (\overline{a} \land b \land \overline{c})\big]$
* Distributivgesetz:
$= \big[(a \land c) \land (b \lor \overline{b})\big] \lor \big[(a \lor \overline{a}) \land (b \land c)\big] \lor \big[(a \lor \overline{a}) \land (b \land \overline{c})\big]$
* Komplementgesetz:
$= \big[(a \land c) \land 1\big] \lor \big[1 \land (b \land c)\big] \lor \big[1 \land (b \land \overline{c})\big]$
* Eins-Element:
$= (a \land c) \lor (b \land c) \lor (b \land \overline{c})$  
$= (a \land c) \lor \big[(c \lor \overline{c})\big]$
* Ergebnis:
$= (a \land c) \lor b$

##### Anderes Beispiel
$\text{DNF}$ der Lichtschalter-Funktion:
$$
f_{DNF}(S_1, S_2, S_3) = (\overline{S_1} \land \overline{S_2} \land S_3) \lor (\overline{S_1} \land S_2 \land \overline{S_3}) \lor (S_1 \land \overline{S_2} \land \overline{S_3}) \lor (S_1 \land S_2 \land S_3)
$$

|                  |$S_1 \land S_2$|$\overline{S_1} \land S_2$|$\overline{S_2} \land \overline{S_2}$|$S_1 \land \overline{S_2}$|
|------------------|-----------|----------------------|----------------------------------------------|----------------------|
|**$S_3$**           |&check;||&check; ||
|**$\overline{S_3}$**||&check;|                     |&check;|

Ist nicht mehr zu vereinfachen. Aber es gilt:
$$
f_{DNF}(S_1, S_2, S_3) = S_1 \oplus S_2 \oplus S_3
$$

#### KV-Diagramme für Funktionen mit vier Variablen
|                     |$a \land b$|$\overline{a} \land b$|$\overline{a} \land \overline{b}$|$a \land \overline{b}$|
|-|-|-|-|-|
|**$c \land d$**|||||
|**$c \land \overline{d}$**|||||
|**$\overline{c} \land \overline{d}$**|||||
|**$\overline{c} \land d$**|||||

## Schaltnetze
### Definition
Ein Schaltnetz $F$ ist die technische Realisierung einer Abbildung
$$
f: B^n \rightarrow B^m\\
a = (a_1, \ldots, a_n) \rightarrow f(a) = (f_1(a), f_2(a), \ldots, f_m(a))
$$

$a_i, i=1, \ldots, n$ sind die Schaltzustände an den Eingängen.  
$f_j, j=1, \ldots, m$ sind die $m$ Ausgänge.

### Schreibweise von Gattern
* $\&$: AND-Gatter
* $\geq 1$: OR-Gatter
* $2k + 1$: XOR-Gatter
* $---o----$: NOT-Gatter

### Der Halbaddierer
Der Halbaddierer ist ein Schaltnetz, das die Addition zweier Bits realisiert, wobei kein Übertrag aus einer vorangehenden Stelle berücksichtigt ist. Übertrag **in** die nächste Stelle ist ein **Carry Out**, ein Übertrag **aus** vorheriger Stelle ist ein **Carry In**.

#### Logik
|$a$|$b$|$sum(a, b)$  |$c_o(a, b)$|
|---|---|-------------|-----------|
|0  |0  |0            |0          |
|0  |1  |1            |0          |
|1  |0  |1            |0          |
|1  |1  |0            |1          |

Offensichtlich:
* $sum(a, b) = a \oplus b$
* $c_o(a, b) = a \land b$

### Volladdierer
Der VA ist ein Schaltnetz mit 3 Inputs ($a$, $b$, $c_{in}$) und 2 Output-Leitungen.

#### Logik
|$a$|$b$|$c_{in}$|$sum(a, b)$  |$c_o(a, b)$|
|---|---|--------|-------------|-----------|
|0  |0  |0       |0            |0          |
|0  |0  |1       |1            |0          |
|0  |1  |0       |1            |0          |
|0  |1  |1       |0            |1          |
|1  |0  |0       |1            |0          |
|1  |0  |1       |0            |1          |
|1  |1  |0       |0            |1          |
|1  |1  |1       |1            |1          |

* $sum(a, b, c) = a \oplus b \oplus c_{in}$
* $f_{c_{in}}(a, b, c) = (a \land c) \lor (a \land b) \lor (b \land c)$

Mit einem Volladdierer lassen sich also 2 Bit addieren. Um zwei Integerzahlen zu addieren, je 32 Bit, benutzt man z. B. einen Ripple-Carry-Addierer.
