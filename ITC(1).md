# Introduction to the Theory of Computation

- Computation Model
- Finite Automaton, Context-free Grammar
- Turing Machine (Algorithm)
- Computability
- Complexity Class (eg. P, NP, PSPACE, EXP, L, NL...)
- NP Completeness, Reduction

***

## Big-O Notation

*Def 1.1* Let
$$
f, g:\mathbb{N}\rightarrow\mathbb{R}
$$

1. Write
   $$
   f=O(g)\Harr(\exist c>0)(\exist N) (\forall n \geq N:|f(n)| \leq c \cdot g(n))
   $$

2. Write
   $$
   f=\Omega(g) \Harr (\exist c>0)(\exist N)(\forall n \geq N:|f(n)| \geq c \cdot g(n))
   $$

3. Write
   $$
   f= \Theta (g) \Harr f = O(g) \space and\space f =\Omega(g)
   $$

4. Write
   $$
   f = o(g) \Harr (\forall \epsilon >0)(\exist N)(\forall n \geq N:|f(n)| \leq \epsilon \cdot g(n))
   $$



eg.  $f(n)=6n^4-2n^3+5 =O(n^4)= \Omega (n^4)=\Theta (n^4)$​

***

*Prop 1.2*

1. $f_1=O(g_1), f_2=O(g_2)\Rightarrow f_1\cdot f_2=O(g_1\cdot g_2)$
2. $f\cdot O(g)=O(f\cdot g)$
3. $f_1=O(g_1),f_2=O(g_2)\Rightarrow f_1+f_2=O(max(g_1,g_2))$
4. $f_1=O(g),f_2=O(g)\Rightarrow f_1+f_2=O(g)$
5. $f=O(g)\Rightarrow kf=O(g)\space where\space k\space is\space a \space constant$



eg. 
