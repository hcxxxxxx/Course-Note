## Equivalence of DFA & NFA

*Thm 2.9* **Every NFA has an equivalent DFA.**

*Proof:* Let $N=(Q,\Sigma,\delta,q_0,F)$ be the NFA recognizing A. Construct a DFA $M=(Q',\Sigma,\delta',q_0',F)$ recognizing A. (Let $E(R)=\{q\in Q|q\ can\ be\ reached\ from\ R\ by\ traveling\ along\ 0\ or\ more\ \epsilon\ arrows\}$)

Define M as follows:

1. $Q'=P(Q)$
2. For $R\in Q'$ and $a\in \Sigma$, let

$$
\delta'(R,a)=\{q\in Q|q\in E(\delta(r,a))\ for\ some\ r\in R\}\\
=\cup_{r\in R}\ E(\delta(r,a))
$$

