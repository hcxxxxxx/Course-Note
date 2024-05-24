## Turing Machine

eg. Decide $L=\{0^{2^n}|n\geq 0\}$, where $\Sigma =\{0\}$

- Idea:
  1. If there is a single $0$, accept
  2. Sweep from left to right, crossing off every other $0$
  3. If the number of $0$'s is odd, reject
  4. Return the head to the left-hand end
  5. Goto step 1
- $\Sigma =\{0\}, \Gamma =\{0,\sqcup,\rhd,x\}$

***

*Def 3.2* **Let $L\subseteq \{0,1\}^*$, let $M$ be a TM. Say $M$ decides $L$ in time $T(n)$ if for every $x\in \{0,1\}^*,$**

1. $M$ halts in $T(n)$ steps
2. If $x\in L$, then $M$ accepts $x$
3. If $x\notin L$, then $M$ rejects $x$

***

*Def 3.3* **Let $L\subseteq \{0,1\}^*$. Call $L$​ (Turing) decidable if there is a TM that decides it.**

- Note that, on an input $x$, a TM may *accept, reject or loop forever*.
- In *Def 3.2*, the machine should never loop forever.

***

*Def 3.4* **Let $M$ be a TM. The set of strings that $M$ accepts is the language recognized by $M$, denoted by $L(M)$.**

***

*Def 3.5* **Let $L\subseteq \{0,1\}^*$. Call $L$​ (Turing) recognizable if there is some TM that recognizes it.** 

- Obviously, every (Turing) decidable language is (Turing) recognizable.
- The converse is not true. eg. $L=\{<M,x>|M\ halts\ on\ x\}$

***

*Def 3.6* **Let $f:\{0,1\}^*\rightarrow \{0,1\}^*\cup \{undefined\}$. Say TM $M$ computes $f$ if for every $x\in \{0,1\}^*$ with $f(x)\neq undefined$, $M$ halts with $f(x)$ on its tape in at most $T(|x|)$​ steps.**

> An algorithm is a Turing Machine.
>
> ——Alan Turing

- Despite its simplicity, TM is capable of implementing any computer algorithm.

***

## Variants of Turing Machines

*Lem 3.7* **If language $L\subseteq \{0,1\}^*$ is decidable in time $T(n)$ by a TM on alphabet $\Gamma$, then it is decidable in time $O(\log |\Gamma|\cdot T(n))=O_\Gamma(T(n))$ by a TM on alphabet $\Gamma =\{0,1,\sqcup,\rhd\}$​.**

*Proof:* Encode any symbol in $\Gamma$ using $k=\lceil \log_2|\Gamma|\rceil=O(\log_2|\Gamma|)$ bits. To simulate one step of $M$, the new TM $M'$ will

1. Use $k$ steps to read a symbol $a\in \Gamma$
2. Transit to next step $q'$, and get the new symbol $b$ (to overwrite $a$)
3. Overwrite $a$ by $b$
4. Go left or right for $k$ steps or stay

***

*Def 3.8* **A k-tape($O(1)$-tape) TM $M$ is a 7-tuple $(Q,\Sigma,\Gamma,\delta,q_0,q_{accept},q_{reject})$, where**
$$
\delta:Q\times \Gamma^k \rightarrow Q\times \Gamma^k\times\{L,R,S\}^k
$$
Usually,the first tape is the *input tape*, the last tape is the *output tape*, and the rest are *work tapes*.

***

*Lem 3.9* **Let $L\subseteq \{0,1\}^*$. If $L$ is decidable by a k-tape TM in time $T(n)$, then $L$ is decidable by a single-tape TM in time $O(k\cdot T(n)^2)$​.**

