## Gödel's Incompleteness Theorem

*Thm 4.17* **All consistent axiomatic formulation of number theory which include Peano arithmetic include undecidable proposition.**

***

### Peano Arithmetic

1. Constant $0$
2. Successor Operator S (s.t. $1=S(0), 2=S(S(0)),...$​)
3. Addition($+$), Multiplication($\cdot$)
4. Logical Conjunction: $\wedge,\vee,\neg$
5. Quantifier: $\forall,\exist$
6. Binary: $<,=$
7. Parenthesis: $()$
8. Variables: $x,x^*,x^{**}...$

- Examples:

  1. "$x$ divides $y$​"
     $$
     DIVIDES(x,y):(\exist z)(y=x\cdot z)
     $$

  2. "$y$​ is a prime number"
     $$
     PRIME(y):(\forall x)(x=S(0)\vee x=y\vee \neg DIVIDES(x,y))
     $$

  3. **Goldbach's Conjecture**
     $$
     (\forall x)(x\geq S(S(0))\Rightarrow (\exist y)(\exist z)(x+x=y+z\ \wedge PRIME(y)\ \wedge PRIME(z)))
     $$

     - $A\Rightarrow B$ is equivalent to $\neg A \vee B$

***

*Thm 4.17's Proof idea:* For any $\alpha,x\in\{0,1\}^*$, construct a first-order Peano arithmetic formula $\phi_{\alpha,x}$ s.t. $\phi_{\alpha,x}$ is true if and only if $M_\alpha$ halts on $x$.

Assume for contradiction that the proof system is complete, i.e. every formula can either be proved or disproved. We construct a TM that enumerates all proofs $\pi$ up to length $k$, and verify if $\pi$ is a valid proof of $\phi_{\alpha,x}$ or $\neg \phi_{\alpha,x}$.

Since the proof system is complete, the TM $M$ must halt, which implies that $L_{halt}$ is decidable. Contradiction. *Q.E.D.*

***

## Diophantine Equation

- **A Diophantine Equation is a polynomial equation with integer coefficients and a finite number of unknowns.**
- For example, $x^2+y^2+1=0$ has no solution. $3x^2-2xy-y^2z-7=0$ has a solution: $x=1,y=2,z=-2$.

***

## Hilbert $10^{th}$ Problem

### $L_{Dio}$

- $L_{Dio}=\{\langle p(x_1,...,x_n)\rangle |Diophantine\ equation\ p(x_1,...,x_n)=0\ has\ a\ solution\}$

*Thm 4.18(MRDP Thm.)* **$L_{Dio}$​​ is undecidable.**

*Proof idea:* For any $\alpha,w\in\{0,1\}^*$, construct a Diophantine equation $P_{\alpha,w}$ s.t. $M_\alpha$ halts on $w$ if and only if $P_{\alpha,w}$ has an integral solution. Therefore, if $L_{Dio}$ is decidable, $L_{halt}$ is decidable. Contradiction. *Q.E.D.*

***

## Complexity Theory

*Def 5.1* Let $T:\mathbb{N}\rightarrow\mathbb{N}$. Let $DTIME(T(n))$ be the class of languages that can be decided by a TM in time $O(T(n))$.
$$
P=\cup_{c\geq1}DTIME(n^c)\\
EXP=\cup_{c\geq1}DTIME(2^{n^c})
$$




