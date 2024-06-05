# Chapter 18

## Definition

*Def 18.1* 设$T=\{F,\rightarrow\}$,这里$ar(F)=0,ar(\rightarrow)=2$​.称任何这样的T-代数为**命题代数**.

- 按类型$T=(\{F,\rightarrow\},ar)$定义$P$上的运算:

  - 把$0$元运算$F_{P(X)}$规定为$P(X)$中的特定元素$F$
  - 二元运算$\rightarrow_{P(X)}$定义为:$\rightarrow_{P(X)}(p,q)=(\rightarrow,p,q)$

  构成了$X$上的T-代数$[P(X),F_{P(X)},\rightarrow_{P(X)}]$,为**命题代数**,也为**自由代数**.

*Def 18.2* 设$X$是可列集,$X$上的自由T-代数称为**$X$上关于命题演算的命题代数**,记为$P(X)$,并称$X$为**命题变量集**,$X$中元素称为**命题变元**,$P(X)$中的每个元素称为命题演算的**合式公式**,简记为*wff*,仅由一个命题变元符组成的合式公式称为**原子公式**,所有原子公式全体称为**原子公式集**.

- 在任何命题代数中,可利用$F$和$\rightarrow$定义一元运算$\neg$和其他二元运算$\vee,\wedge,\harr$,定义为:

$$
\neg p {\scriptsize{def}\atop=}p\rightarrow F\\
p\vee q{\scriptsize{def}\atop=}(\neg p)\rightarrow q\\
p\wedge q{\scriptsize{def}\atop=}\neg((\neg p)\vee(\neg q))\\
p\harr q{\scriptsize{def}\atop=}(p\rightarrow q)\wedge(q\rightarrow p)
$$

- 优先级:$\neg>\wedge>\vee>\rightarrow>\harr$

*Def 18.3* 设$P(X)$是$X$上关于命题演算的命题代数,称$P(X)\rightarrow Z_2$的同态映射$v$为$P(X)$的**赋值**.对于任意的$p\in P(X)$,若$v(p)=1$则称**$p$按赋值$v$为真**,若$v(p)=0$则称$p$**按赋值$v$为假**.

<img src="C:\Users\洪成勋\AppData\Roaming\Typora\typora-user-images\image-20240605235959482.png" alt="image-20240605235959482" style="zoom:25%;" />

*Def 18.4* 设$v_0$为$X\rightarrow Z_2$的映射,称$v_0$为命题变元的一个**指派**.
$$
v(p\rightarrow q)=v(p)\rightarrow v(q)=1+v(p)(1+v(q))=1+v(p)+v(p)v(q)\\
v(\neg p)=v(p\rightarrow F)=v(p)\rightarrow v(F)=1+v(p)(1+v(F))=1+v(p)(1+0)=1+v(p)\\
v(p\vee q)=v(\neg p\rightarrow q)=v(\neg p)\rightarrow v(q)=1+(1+v(p))(1+v(q))=v(p)+v(q)+v(p)v(q)\\
v(p\wedge q)=v(\neg(\neg p\vee \neg q))=1+v(\neg p\vee \neg q)=v(p)v(q)\\
v(p\harr q)=v((p\rightarrow q)\wedge(q\rightarrow p))=1+v(p)+v(q)
$$
*Def 18.5* 函数$f:Z_2^n\rightarrow Z_2$​称为**n元真值函数**.

*Def 18.6* 设$p\in P(X)$,定义$p$的n元真值函数$f_p:Z_2^n\rightarrow Z_2$为:$f_p=v(p)$,称$f_p$为**$p$的真值函数**.由$p$的真值函数所建立的函数值表称为**$p$的真值表**.

*Def 18.7* 设$A\subseteq P(X),q\in P(X)$,若对所有使得$\forall p\in A,v(p)=1$的赋值$v$,都有$v(q)=1$,则称$q$是**假设集$A$的后件**,或称$A$**语义蕴含**$q$,记为$A\vDash q$, 用$Con(A)$表示$A$的后件全体,即$Con(A)=\{p\in P(X)|A\vDash p\}$.

- $A\subseteq Con(A)$
- $\forall p\in P(X),p\in Con(\{F\})$

*Def 18.8* 设$p\in P(X)$,若对$P(X)$的任意赋值$v$都有$v(p)=1$,则称$p$是**有效的**,也称为**重言式**.若对$P(X)$的任意赋值$v$都有$v(p)=0$,则称$p$是**永假式**.

- $p$是重言式$\Harr \phi\vDash p$,简记为$\vDash p$​.

*Def 18.9* 设$p,q\in P(X)$,若对$P(X)$的任意赋值$v$有$v(p)=v(q)$,则称$p,q$​**等值**.

*Def 18.10* 形式为$\vee^m_{i=1}(\wedge^n_{j=1}y_{ij})$的合式公式称为**析取范式**.形式为$\wedge^m_{i=1}(\vee^n_{j=1}y_{ij})$的合式公式称为**合取范式**.这里$y_{ij}$为某个命题变元$x_k$或其否定$\neg x_k$​.

*Def 18.11* 一个合式公式若不是永假式,则用*Thm 18.4*的证明方法($q=(y^1_1\wedge y^1_2\wedge...\wedge y^1_n)\vee...\vee(y^i_1\wedge y^i_2\wedge...\wedge y^i_n)\vee...$​)得到的等值析取范式称为该合式公式的**标准析取范式**.

*Def 18.12* 一个合式公式若不是重言式,则用*Cor 18.1*的证明方法($\wedge^m_{i=1}(\vee^n_{j=1}z_{ij}),z_i=\{^{\neg x_i,v(x_i)=1}_{\ x_i,\ \ v(x_i)=0}$)得到的等值合取范式称为该合式公式的**标准合取范式**.



## Theorem

- **命题逻辑的演算**

  1.双重否定律			$A\Harr \neg\neg A$

  2.等幂律				$A\Harr A\vee A$							$A\Harr A\wedge A$

  3.交换律				$A\vee B\Harr B\vee A$						$A\wedge B\Harr B\wedge A$

  4.结合律				$(A\vee B)\vee C\Harr A\vee(B\vee C)$			$(A\wedge B)\wedge C\Harr A\wedge(B\wedge C)$

  5.分配律				$A\vee(B\wedge C)\Harr (A\vee B)\wedge(A\vee C)$     	$A\wedge(B\vee C)\Harr (A\wedge B)\vee(A\wedge C)$

  6.德·摩根律			   $\neg(A\vee B)\Harr \neg A\wedge \neg B$				    $\neg(A\wedge B)\Harr\neg A\vee\neg B$

  7.吸收率				$A\vee(A\wedge B)\Harr A$					     $A\wedge(A\vee B)\Harr A$

  8.零律				    $A\vee1\Harr1$							   $A\wedge0\Harr0$

  9.同一律				$A\vee0\Harr A$							  $A\wedge1\Harr A$

  10.排中律			      $A\vee\neg A\Harr 1$

  11.矛盾律			      $A\wedge\neg A\Harr0$

  12.蕴含等值式		      $A\rightarrow B\Harr\neg A\vee B$

  13.等价等值式		      $A\harr B\Harr (A\rightarrow B)\wedge(B\rightarrow A)$

  14.假言易位			  $A\rightarrow B\Harr\neg B\rightarrow\neg A$

  15.等价否定等值式	       $A\harr B\Harr \neg A\harr\neg B$

  16.归谬论			      $(A\rightarrow B)\wedge(A\rightarrow\neg B)\Harr\neg A$

- **置换规则**:设$\Phi(A)$是含公式$A$的命题公式,$B\Harr A$,若用$B$置换$\Phi(A)$中的$A$,得$\Phi(B)$,则$\Phi(B)\Harr \Phi(A)$.

***

*Thm 18.1* 设$A$为命题代数,$v_0$为$X\rightarrow A$的映射,则$v_0$可唯一扩张为$P(X)\rightarrow A$的同态映射$v$.

<img src="C:\Users\洪成勋\AppData\Roaming\Typora\typora-user-images\image-20240606000145240.png" alt="image-20240606000145240" style="zoom:25%;" />

*Lem 18.1* $Con$是$P(X)$上的封闭运算,有如下性质:

​		(1)$A\subseteq Con(A)$

​		(2)若$A_1\subseteq A_2$,则$Con(A_1)\subseteq Con(A_2)$

​		(3)$Con(Con(A))=Con(A)$

*Thm 18.2* 下述结论是等价的:

​		(1)$p,q$等值

​		(2)$\vDash p\harr q$

​		(3)$p,q$有相同的真值函数和真值表

*Thm 18.3* 对$\forall p,q,r\in P(X)$有下述结论:

​		(1)$\vDash\neg\neg p\harr p$

​		(2)$\vDash\neg(p\wedge q)\harr\neg p\vee\neg q$

​		(3)$\vDash\neg(p\vee q)\harr\neg p\wedge\neg q$

​		(4)$\vDash\neg(p_1\vee p_2\vee...\vee p_n)\harr\neg p_1\wedge\neg p_2\wedge...\wedge\neg p_n$

​		(5)$\vDash\neg(p_1\wedge p_2\wedge...\wedge p_n)\harr\neg p_1\vee\neg p_2\vee...\vee\neg p_n$

*Thm 18.4* 任何命题合式公式(即$P(X)$中的元素)都有只含命题变元及$\neg,\vee,\wedge$这三种运算的合式公式与该命题合式公式等值.

*Cor 18.1* 每个非重言式必等值于一个合取范式.