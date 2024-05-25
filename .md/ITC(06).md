*Lem 3.9* **Let $L\subseteq \Sigma^*$. If $L$ is decidable by a k-tape TM in time $T(n)$, then it is decidable by a single-tape TM in time $O(k\cdot T(n)^2)$​.**

*Proof:* Use location $i-1,k+i-1,2k+i-1,...$ to store the content of the $i^{th}$ tape, where $i=1,2,...,k$. For every $a\in \Gamma$, introduce $a,\hat{a}\in \Gamma'$, where $\hat a$ denotes the location of the head.

To simulate one step of $M$, the single-tape TM $M'$ will

1. Sweep the tape from left to right to read $k$ symbols marked by  $\hat{}$​ .
2. Apply $M$'s transition function $\delta$ to determine the next state.
3. Sweep back from right to left to update $k$ symbols, if needed, and move  $\hat{}$​ , if needed. 

In total, 1.2.3. take $O(k\cdot T(n))$ time.

***

- **A Bidirectional-tape TM is a TM where tape is infinite in both directions.**

***

*Lem 3.10* **Let $L\subseteq \Sigma^*$. If $L$ is decidable by a Bidirectional-tape TM in time $T(n)$, then it is decidable by a single-tape TM in time $O(T(n))$.**

*Proof:* Index the Bidirectional tape by $\mathbb{Z}$:

(Assuming that the Bidirectional tape was indexed by: $...,-3,-2,-1,0,1,2,3,...$)
$$
Mapping:\lbrace^{i\rightarrow 2i}_{-i\rightarrow 2i-1}
$$
In this way, we create a new (single) tape indexed by: $0,-1,1,-2,2,...$

For every step of $M$, $M'$ will:

1. Read the symbol
2. Transit to the next state
3. Update the symbol
4. Move left or right for 2 steps if needed

It takes $O(1)$ to simulate 1 step. In total, the running time is $O(T(n))$. *Q.E.D.*

***

## RAM TM

*Def 3.11* **A RAM TM is a TM with random access memory.**

1. $M$ has an infinite memory tape $A$ indexed by $\mathbb{N}$.

2. One of $M$'s tape is the address tape.

3. $\Gamma$ contains 2 special symbols $R$ (Read) and $W$ (Write).

4. $Q$ has some special states $Q_{access}\subseteq Q$.

   Whenever $M$ gets into a state $q\in Q_{access}$:

   1. If the address tape contains $iR$, the value $A[i]$ is written to the cell next to $R$.
   2. If the address tape contains $iW\sigma$, then set $A[i]$ to symbol $\sigma$.

Assume the RAM TM $M$ has $k$ work tapes, and an address tape. Then
$$
M=(Q,\Sigma,\Gamma,\delta,q_0,q_{accept},q_{reject},Q_{access})\\
\delta:Q\times \Gamma^{k+1} \rightarrow Q\times \Gamma^{k+1}\times \{L,R,S\}^{k+1}
$$

***

*Lem 3.12* **Let $L\subseteq \{0,1\}^*$. If $L$ is decidable by a RAM TM in time $T(n)$, it is decidable by a Multitape TM in time $O(T(n)^3)$​.** 

- Moreover, if the address length is $O(1)$, then $L$ is decidable by a Multitape TM in time $O(T(n)^2)$.

*Proof:* Use an extra work tape as memory.

***

- **Ignoring polynomial factors, all TM variants are equivalent.**

$$
{C++\atop T(n)}\rightarrow {Assembly\atop O(T(n))}\rightarrow {RAM\ TM\atop O(T(n))}\rightarrow {Multitape\atop O(T(n)^3)/O(T(n)^2)^*}\rightarrow {Single-tape\atop O(T(n)^6)/O(T(n)^4)^*}
$$

