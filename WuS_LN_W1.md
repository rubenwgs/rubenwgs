# 1. Wahrscheinlichkeit
## 1.1 Grundbegriffe
---

**Definition:** Der *Ereignisraum* $\Omega \neq \emptyset$ ist die Menge aller möglichen Ergebnisse eines betrachteten Zufallsexperiment. Die Elemente $\omega \in \Omega$ heissen *Elementarereignisse* des Experiments.

---

---

**Definition:** Die *Potenzmenge* von $\Omega$, bezeichnet mit $\mathcal{P}(\Omega)$ oder $2^{\Omega}$, ist die Menge aller Teilmengen vom $\Omega$. Ein *prinzipielles Ereignis* ist eine Teilmenge $A \subseteq \Omega$, also eine Kollektion von Elementarereignissen. Die Klasse aller (beobachtbaren) *Ereignisse* ist $\mathcal{F}$.

---

Generell sagen wir nun, dass das Ereignis $A$ *eintritt*, falls das realisierte Elementarereignis $\omega$ in $A$ liegt, d.h. $\omega \in A$.

---

**Definition:** Ein *Wahrscheinlichkeitsmass* ist eine Abbildung $P : \mathcal{F} \to [0, \, 1]$, welche die nachfolgenden Axiome erfüllt. Für $A \in \mathcal{F}$ nennen wir $P[A] \in [0, \, 1]$ die *Wahrscheinlichkeit* (kurz ***WS***), dass $A$ eintritt. Die geforderten Axiome sind:
- **A0)** $P[A] \geq 0$ für alle Ereignisse $A \in \mathcal{F}$
- **A1)** $P[\Omega] = 1$
- **A2)** $P\Big[\bigcup_{i = 1}^{\infty} A_i \Big] = \sum_{i = 1}^{\infty} P[A_i]$, sofern die $A_i \in \mathcal{F}$ *paarweise disjunkt* sind. Wir schreiben dies auch kürzer als $$P\Big[ \dot{\bigcup}_{i = 1}^{\infty} A_i  \Big] = \sum_{i = 1}^{\infty} P[A_i]$$ die Notation $\dot{\bigcup}$ steht dabei für eine Vereinigung von paarweise disjunkten Mengen.

---
Aus den obigen Axiomen lassen sich einige grundlegende *Rechenregeln* ableiten:
1. $P[A^c] = 1- P[A]$
2. $P[\emptyset] = 0$
3. Für $A \subseteq B$ gilt $P[A] \leq P[B]$
4. Für beliebige (nicht unbdeingt disjunkte) $A, \, B$ gilt die allgemeine *Additionsregel* $$P[A \cup B] = P[A] + P[B] - P[A \cap B]$$

## 1.2 Diskrete Wahrscheinlichkeit
Ist $\Omega = \{\omega_1, \, \omega_2,..., \, \omega_N \}$ endlich mit $|\Omega| = N$ und $\mathcal{F} = 2^{\Omega}$, und sind $\omega_1, \, \omega_2,..., \, \omega_N$ alle gleich wahrscheinlich, also $p_1 = p_2 = \cdots = p_N = \frac{1}{N}$, so heisst $\Omega$ ein *Laplace-Raum* und $P$ die *diskrete Gleichverteilung* auf $\Omega$. Für beliebige $A \subseteq \Omega$ ist dann
$$ P[A] = \frac{\text{Anzahl der Elementarereignisse in } A}{\text{Anzahl der Elementarereignisse in }\Omega} = \frac{|A|}{|\Omega|}.$$

## 1.3 Bedingte Wahrscheinlichkeit
---
**Definition:** Seien $A, \, B$ Ereignisse und $P[A] > 0$. Die *bedingte Wahrscheinlichkeit* von $B$ unter der Bedingung. dass $A$ eintritt (kurz: gegeben A) wird definiert durch
$$ P[B | A] := \frac{P[B \cap A]}{P[A]}. $$
---
Direkt aus der Definition der beginten Wahrscheinlichkeit erhält man die sogenannte *Multiplikationsregel:* Für beliebige Ereignisse $A, \, B$ ist
$$ P[A \cap B] = P[B | A] \cdot P[A].$$
---
**Satz 1.1 (Satz der totalen Wahrscheinlichkeit)**  
Sei $A_1, \, A_2,..., \, A_n$ eine Zerlegung von $\Omega$ (in paarweise disjunkte Ereignisse). Für beliebige Ereignisse $B$ gilt dann
$$ P[B] = \sum_{i = 1}^{n} P[B | A_i] \cdots P[A_i].$$
---

## 1.4 Unabhängigkeit von Ereignissen
---
**Definition:** Zwei Ereignisse $A, \, B$ heissen *stochastisch unabhängig*, falls
$$ P[A \cap B] = P[A] \cdot P[B].$$
Ist $P[A] = 0$ oder $P[B] = 0$, so sind $A$ und $B$ immer unabhängig. Für $P[A] \neq 0$ gilt
$$ A, \, B \text{ unabhängig } \Leftrightarrow P[B | A] = P[B],$$
und symmetrisch gilt für $P[B] \neq 0$
$$ A, \, B \text{ unabhängig } \Leftrightarrow P[A | B] = P[A].$$
---
---
**Definition:** Die Ereignisse $A_1, \, A_2,..., \, A_n$ heissen *stochastisch unabhängig*, wenn für jede endliche Teilfamilie die Produktformel gilt, d.h. für $m \in \mathbb{N}$ und $\{k_1,..., \, k_m \} \subseteq \{1,..., \, n \}$ gilt immer
$$ P \Big[ \bigcap _{i=1}^{m} A_{k_i} \Big] = \prod_{i=1}^{m} P{A_{k_i}}.$$
---
# 2. Diskrete Zufallsvariablen und Verteilungen
## 2.1 Grundbegriffe
---
**Definition:** Eine *diskrete Zufallsvaraible* (***ZV***) auf $\Omega$ ist eine Funktion $X : \Omega \to \mathbb{R}$. Mit $\Omega$ ist natürlich auch der Wertebreich $\mathcal{W}(X) = \{x_1, \, x_2,... \}$ endlich oder abzählbar. Die *Verteilungsfunktion* (***VF***) von $X$ ist die Abbildung $F_X : \mathbb{R} \to [0, \, 1]$, die definiert ist durch
$$ t \to F_X(t) := P[X \leq t] := P[\{\omega : X(\omega) \leq t\}].$$
Die *Gewichtsfunktion* oder *diskrete Dichte* von $X$ ist die Funtkion $p_X : \mathcal{W}(X) \to [0, \, 1]$, die durch
$$ p_X(x_k) := P[X = x_k] = P[\{\omega : X(\omega) = x_k\}] \text{ für } k = 1, \, 2,...$$
definiert ist.

---
