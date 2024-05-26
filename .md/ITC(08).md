*Lem 4.2* **Almost all languages are undecidable.**

*Proof:* $\#languages=2^{\aleph_0}=\aleph_1$,$\#\{L\subseteq \{0,1\}^*\}=TMs=\aleph_0$.*Q.E.D.*

***

### $L_{flip}$

- $L_{flip}=\{\alpha|M_{\alpha}\ does\ not\ accept\ \alpha\}$

*Lem 4.3* **$L_{flip}$​ is undecidable.**

*Proof:* Assume for contradiction that $L_{flip}$ is decided by a TM $M_\beta$, which implies that $L(M_\beta)=L_{flip}$.

- Case 1: $\beta \in L_{flip}$. By definition, $M_\beta$ does not accept $\beta$, i.e. $M_\beta$ rejects $\beta$. So, $\beta \notin L(M_\beta)=L_{flip}$. Contradiction.
- Case 2: $\beta \notin L_{flip}$. By definition, $M_\beta$ accepts $\beta$. So, $\beta \in L(M_\beta)=L_{flip}$. Contradiction. *Q.E.D.*

***

### Turing Halting Problem

- $L_{halt}{def\atop =}\{(\alpha,x)|M_\alpha\ halts\ on\ input\ x\}$

- **Fermat's Last Theorem:** $(\forall m\geq3)(\forall a,b,c\geq1)(a^m+b^m\neq c^m)$
  - $M_\alpha$ for *FLT*:
    - $T=2$
    - while true:
      - $T=T+1$
      - for $d=3$ to $T$
        - for $a,b,c\in\{1,2,...,T\}$
          - if $a^d+b^d=c^d$, exit
  - *FLT*$\Harr(M_\alpha,\epsilon)\notin L_{halt}$.

***

## Reduction

*Def 4.4* **Let $L_1,L_2\subseteq\{0,1\}^*$. Write $L_1\leq L_2$ if there is a reduction from $L_1$ to $L_2$. That is, there exists a TM $M:\{0,1\}^*\rightarrow \{0,1\}^*$ (On any input $x$, $M$ always halts and outputs a string $M(x)$) s.t.:**

1. $(\forall x\in L_1)(M(x)\in L_2)$
2. $(\forall x\notin L_1)(M(x)\notin L_2)$

- Let $L_1\leq L_2$. If $L_2$ is decidable, then $L_1$ is decidable. Contrapositively, if $L_1$ is undecidable, then $L_2$ is undecidable.

***

*Thm 4.5* **$L_{halt}$​ is undecidable.**

*Proof:* We will prove $L_{flip}\leq L_{halt}$.

Assume that $L_{halt}$ is decidable by a TM $M_{halt}$, we will prove $L_{flip}$ is decidable, which would be a contradiction.

Create a TM $M_{flip}$ as follows:

- Run $M_{halt}$ on input $(\alpha,\alpha)$.
  1. If $M_{halt}$ rejects $(\alpha,\alpha)$, let $M_{flip}$ accept $\alpha$.
  2. If $M_{halt}$ accepts $(\alpha,\alpha)$, simulate $M_\alpha$ on input $\alpha$ (using a UTM), and flip the output.

It's easy to verify $M_{flip}$ decides $L_{flip}$. Contradiction. *Q.E.D.*

***

### $L_{accept}$​

- $L_{accept}=\{(\alpha,x)|M_\alpha\ accepts\ x\}$

*Lem 4.6* **$L_{accept}$ is undecidable.**

*Proof:* We will prove $L_{halt}\leq L_{accept}$. Assuming for contradiction that $L_{accept}$ is decidable, i.e. there exists a TM $M_{accept}$ that decides $L_{accept}$, we construct a TM $M_{halt}$ that decides $L_{halt}$ as follows:

1. On input $(\alpha,x)$, create a new TM $M_\beta$, which simulates $M_\alpha$ on input $x$, and always accepts whenever $M_\alpha$ halts. (If $M_\alpha$ loops forever, $M_\beta$ loops forever as well)
2. Run $M_{accept}$ on input $(\beta,x)$, and forward its output. Clearly, $M_{halt}$ decides $L_{halt}$. Contradiction. *Q.E.D.*

***

### $L_{empty}$​

- $L_{empty}=\{\langle M\rangle|M\ does\ not\ accept\ any\ input,\ i.e.\ L(M)=\phi\}$

*Lem 4.7* **$L_{empty}$​ is undecidable.**

*Proof:* We will prove $L_{halt}\leq L_{empty}$. Assume for contradiction that $L_{empty}$ can be decided by a TM $M_{empty}$. We construct a TM $M_{halt}$ as follows.

1. On input $(\alpha,x)$, we construct a new TM $M_\beta$, whose input is $y\in \{0,1\}^*$ as follows:

   a. Simulate $M_\alpha$ on input $x$

   b. If step a halts, always accepy $y$

   Clearly, $L(M_\beta)=\phi$ if $M_\alpha$ does not halt on $x$. Otherwise, $L(M_\beta)=\{0,1\}^*$.

2. Run $M_{empty}$ on input $\beta$ and flip the output. We can verify that $M_{halt}$ decides $L_{halt}$.

Contradiction. *Q.E.D.*

***

### $L_{regular}$

- $L_{regular}=\{\langle M\rangle|M\ is\ a\ TM\ s.t.\ L(M)\ is\ regular\}$

*Thm 4.8* **$L_{regular}$​ is undecidable.**

*Proof:* Assume for contradiction that $L_{regular}$ is decidable, i.e. $\exist$ a TM $M_{regular}$ that decides $L_{regular}$ . We will prove $L_{accept}$ is decidable.

On input $(\alpha,x)$, construct a TM $M_{accept}$​​ as follows:

1. Construct a TM $M_\beta$, where $\beta=\beta(\alpha,x)$, and the input of $M_\beta$ is denoted by $y$.

   a. If $y\in \{0^n1^n|n\geq0\}$, accept

   b. Otherwise, simulate $M_\alpha$ on $x$, and accept if and only if $M_\alpha$ accepts $x$

2. Run $M_{regular}$ on $\beta$, and forward its output.

   - Case 1: $(\alpha,x)\notin L_{accept}$. i.e. $M_\alpha$ does not accept $x$. So, $L(M_\beta)=\{0^n1^n|n\geq0\}$.

     Thus, $M_{regular}$ rejects $\beta$, which implies that $M_{halt}$ rejects $\beta$​.

   - Case 2: $(\alpha,x)\in L_{accept}$. So $L(M_\beta)=\{0,1\}^*$. As such, $M_{regular}$ accepts $\beta$, and so does $M_{halt}$.

Contradiction. *Q.E.D.*

***

### $L_{equal}$

- $L_{equal}=\{(\langle M_1\rangle,\langle M_2\rangle)|M_1\ and\ M_2\ are\ TMs\ s.t.\ L(M_1)=L(M_2)\}$​

*Lem 4.9* **$L_{equal}$ is undecidable.**

*Proof:* Assume for contradiction that $L_{equal}$ is decidable. i.e. $L_{equal}$ is decided by a TM $M_{equal}$. We will prove $L_{empty}$ is decidable.

On input $\langle M\rangle$, construct a TM $M_{empty}$ as follows:

1. Run $M_{equal}$ on input $(\langle M\rangle,\langle M_0\rangle)$, where $M_0$ rejects immediately.
2. Forward the above output. *Q.E.D.*