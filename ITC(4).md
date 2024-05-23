- Regular languages: $\aleph_0$ (countable)
- All languages: $\aleph_1$ (uncountable)

***

*Lem 2.16* **If a language is regular, it is described by a regular expression.**
$$
DFA\rightarrow GNFA\rightarrow Regular\ expression
$$
*Def 2.17* **A generalized nondeterministic finite automaton (GNFA) is a 5-tuple $(Q,\Sigma,\delta,q_{start},q_{accept})$, where**

1. $Q$ is a finite set of states
2. $\Sigma$ is the alphabet
3. $\delta:(Q-\{q_{accept}\})\times R\rightarrow (Q-\{q_{start}\})$ is the transition function
   - $R$ is the set of all regular expression, $q_{accept}$ has no incoming edge, and $q_{start}$ has no outgoing edge.
4. $q_{start}$ is the start state
5. $q_{accept}$ is the accept state

-  **Except for the start state and accept state, there is one arrow from one state to every other state, and also from each state to itself.**

eg. 3-state DFA $?\atop \rightarrow$ 5-state GNFA $?\atop \rightarrow$ 4-state GNFA $\rightarrow$ 3-state GNFA $\rightarrow$ 2-state GNFA $\rightarrow$ ($q_{start}$ $R\atop \rightarrow$ $q_{accept}$)

*Proof:* Let $M$ be the DFA for language $A$. Convert $M$ to a GNFA as follows:

1. Add a new start state with $\epsilon$ arrow to the old start state

2. Add a new accept state with $\epsilon$ arrows from the old accept states

3. Replace multiple edges by one edge using "$\cup$"

4. Add arrows with $\phi$ between states that had no arrow

   - $Convert(G):$

   1. Let $k$ be the number of states in $G$.

   2. If $k=2$, return $\delta(q_{start},q_{accept})$

   3. If $k>2$, choose $q_{rip}\in Q\setminus \{q_{start},q_{accept}\}$

      - Let $G'$ be the GNFA$(Q',\Sigma,\delta',q_{start},q_{accept})$, where

      1. $Q'=Q-\{q_{rip}\}$
      2. $\forall q_i\in Q'-\{q_{accept}\}, \forall q_j\in Q'-\{q_{start}\}$
      3. Let $\delta'(q_i,q_j)=\delta(q_i,q_j)\cup\delta(q_i,q_{rip})\delta(q_{rip},q_{rip})^*\delta(q_{rip},q_j)$

      (Notice $q_i$ can be equal to $q_j$)

   4. Return $Convert(G')$



*Claim:* **For any GNFA $G$, $Convert(G)$ is equivalent to $Convert(G')$.**



