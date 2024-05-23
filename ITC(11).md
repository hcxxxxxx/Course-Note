*Thm 5.16* $P\subseteq NP\subseteq EXP$.

*Proof:*

1. $P\subseteq NP$

Let $L\in P$. We shall prove $L\in NP$​.

Let $p(n)=0$, and let $M$ be a TM that decides $L$ efficiently.

If $x\in L$, then $M(x,\epsilon)=1$. If $x\notin L$, then $M(x,\epsilon)=0$.

2. $NP\subseteq EXP$

Let $L\in NP$. We will prove $L\in EXP$.

Since $L\in NP$, there exists a polynomial $p:\mathbb{N} \rightarrow \mathbb{N}$ and a polynomial-time TM $M$ s.t. 1,2 hold.

Construct a TM $M'$ which enumerates all $w\in \{0,1\}^{p(|x|)}$ and check if $M(x,w)=1$.

If there exists one $w$ s.t. $M(x,w)=1$, then $M$ accepts $x$.

The total running time is $2^{p(n)}\cdot poly(n)=2^{n^{O(1)}}\cdot n^{O(1)}=2^{n^{O(1)}}$

- $poly(n)=n^{O(1)}$​

***

## Nondeterministic TMs

**At any point, the machine may proceed according to severl possibilities. The transition function**
$$
\delta:Q\times \Gamma \rightarrow P(Q\times \Gamma \times \{L,R,S\})
$$
**Formally, an NTM **$M=(\Sigma,\Gamma,Q,\delta,q_0,q_{accept},q_{reject})$

**$M$ accepts $x$ if there is a computation path that accepts $x$**.

*Def 5.17* **Say an NTM $M$ runs in time $T(n)$ if for exery input $x\in \{0,1\}^n$, and every sequence of nondeterministic choice, $M$ reaches an end state in $T(n)$ steps.** 

*Def 5.18* **Say an NTM $M$ decides $L$ if for every $x\in \{0,1\}^*$, $x\in L\Harr M(x)=1$​**

***

 *Def 5.19* **(Binary-choice NTM)**
$$
M=(Q,\Sigma,\Gamma,\delta_1,\delta_2,q_0,q_{accept},q_{reject}),
$$
**where $\delta_1,\delta_2:Q\times \Gamma \rightarrow Q\times \Gamma \times \{L,R,S\}$**

**At each step, $M$ applies $\delta_1$ or $\delta_2$​ arbitrarily.**

*Lem 5.20* **Let $L\subseteq \{0,1\}^*$. If $L$ can be decided by an NTM $M$ in time $T(n)$, then $L$ can be decided by a binary-choice NTM in time $O_M(T(n))$​.**

*Proof:* At each step, $M$ can have at most $2^{|Q|\times|\Gamma|\times3}$ choices. This can be simulated in $\log_22^{|Q|\times|\Gamma|\times3}=|Q|\times|\Gamma|\times3$ steps by a binary-choice NTM.

So, the total running time is $\leq|Q|\times|\Gamma|\times3\times T(n)=O_M(T(n))$. *Q.E.D.*

*Def 5.21* **Let $T:\mathbb{N}\rightarrow \mathbb{N}$. Let $NTIME(T(n))$ be the set of languages that can be decided by an NTM in time $O(T(n))$.**

*Thm 5.22* $NP= {\cup \atop {c\geq 1}} NTIME(n^c)$

