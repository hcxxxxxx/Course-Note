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

*Def 18.12* 一个合式公式若不是重言式,则用*Cor 18.1*的证明方法($\wedge^m_{i=1}(\vee^n_{j=1}z_{ij}),z_i=\{^{\neg x_i,v(x_i)=1}_{\ x_i,\ \ v(x_i)=0}$​)得到的等值合取范式称为该合式公式的**标准合取范式**.

***

- 一些在任何数学证明中公认允许采用的陈述句,把它们形式化地表述成若干特殊的命题,这些命题可在证明的任何一步引入,这些命题被称为**公理(Axiom)**.对于集合$X$上的命题演算,称$X$上的自由命题代数$P(X)$的子集$\mathcal{A}=\mathcal{A}_1\cup \mathcal{A}_2\cup \mathcal{A}_3$中的所有元素为系统的**公理**.其中:
  - $\mathcal{A}_1=\{p\rightarrow (q\rightarrow p)|p,q\in P(x)\}$
  - $\mathcal{A}_2=\{(p\rightarrow(q\rightarrow r))\rightarrow ((p\rightarrow q)\rightarrow (p\rightarrow r))|p,q,r\in P(X)\}$
  - $\mathcal{A}_3=\{\neg \neg p\rightarrow p|p\in P(X)\}$
- 另一个采用的方法是由若干规则构成,这些规则规定:从某些陈述导出某些特定陈述是可接受的,这些规则在形式化之后,称为系统的**推理规则(Ponens)**.
  - **MP规则**:由$p$和$p\rightarrow q$可导出$q$​.

***

*Def 18.13* 设$q\in P(X),A\subseteq P(X)$,在集合$X$上的命题演算中,由假设$A$导出$q$的证明是一组有限序列$p_1,...,p_n$,这里$p_i\in P(X)(i=1,...,n),p_n=q$,并且对于每个$p_i$:

- 或者$p_i\in \mathcal{A}\cup A$,
- 或者存在$j,k(j,k<i)$,有$p_k=(p_j\rightarrow p_i)$.

*Def 18.14* 设$q\in P(X),A\subseteq P(X)$,如果存在一个由$A$导出$q$的证明,则称$q$是$A$的**推导**,或称$q$是**从$A$可证明的**,记为$A\vdash q$,且用$Ded(A)$表示$A$的推导全体.显然,$A\subseteq Ded(A)$.

*Def 18.15* 设$p\in P(X)$,如果存在一个由$\phi$导出$p$的证明,则称$p$是$X$上的**命题演算的定理**,记为$\phi\vdash p$,也简写为$\vdash p$​.

***

- $p\rightarrow q$是命题合式公式,表示$p$**蕴含**$q$.

- $A\vDash q$是$A$**语义蕴含**$q$,表示当且仅当$A$中所有命题为真时,命题$q$​也为真.

- $A\vdash q$是$A$**逻辑蕴含**$q$,表示从$A$中的性质,通过推理规则可以证明推出$q$​​.

- ***

*Def 18.16* 设$p,w\in P(X)$,若$p$在$w$中出现,则称$p$为$w$​的**子公式**.

*Def 18.17* 一个**逻辑**$L$是由下述集合所组成的系统:

- **元素(命题)集**$P$
- **函数集**$V$(这些函数都是从$P$到某个值集$W$的,称为**赋值**.特别地,若$|W|>2$则称$L$为多值逻辑系统)
- 以及对应于$P$的每个子集$A$导出$P$中元素的**有限序列集**(称为**由前提$A$​得到的证明**)

***

- 用$Prop(X)$表示$X$上命题演算的逻辑,其组成为:
  - (1)集合$P=P(X)$($X$上自由命题代数)
  - (2)所有的$P(X)$到$Z_2$的同态映射集$V$
  - (3)满足*Def 18.13*的证明集($P(X)$的每个子集$A$导出$P(X)$中元素的有限序列集)

***

*Def 18.18* 如果$A\vdash p$必有$A\vDash p$,则称逻辑$L$是**可靠的**.

*Def 18.19* 如果$F$不是$L$的定理,则称逻辑$L$是**协调的**.

*Def 18.20* 如果$A\vDash p$必有$A\vdash p$,则称逻辑$L$是**完备的**.

*Def 18.21* 如果存在一个算法,对逻辑$L$的每个命题$p$,能在有限步内确定$p$是否为重言式,则称逻辑$L$是**有效性可判定的**.

*Def 18.22* 如果存在一个算法,对逻辑$L$的每个命题$p$,能在有限步内确定$p$是否为定理,则称逻辑$L$​是**可证明性可判定的**.

*Def 18.23* 设$A\subseteq P(X)$,若$F\notin Ded(A)$,则称$A$是**协调的**.若$A$是协调的,且对$\forall B\subseteq P(X)$,当$B$真包含$A$时,$B$必定不协调,则称$A$是**极大协调子集**.



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

*Lem 18.2* $Ded(A)$具有如下性质:

​		(1)若$q\in Ded(A)$,则必存在$A$的有限子集$A'$,使得$q\in Ded(A')$.

​		(2)$Ded$在$P(X)$满足封闭性,即:

​			(i)$A\subseteq Ded(A)$

​			(ii)若$A_1\subseteq A_2$,则$Ded(A_1)\subseteq Ded(A_2)$

​			(iii)$Ded(Ded(A))=Ded(A)$

*Thm 18.5* **(演绎定理)**:设$A\subseteq P(X),p,q\in P(X)$,则$A\vdash p\rightarrow q$当且仅当$A\cup \{p\}\vdash q$.

*Thm 18.6* **(代换定理)**:设$X,Y$是两个集合,$\phi$是$P(X)\rightarrow P(Y)$的同态映射,这里$P(X)$和$P(Y)$分别是$X,Y$上的(自由)命题代数.设$w=w(x_1,...,x_n)$是$P(X)$的元素,$A$是$P(X)$的子集,令$q_i=\phi(x_i),q_i\in P(Y)$:

​		(1)如果$A\vdash w$,则$\phi(A)\vdash \phi(w)(=w(q_1,...,q_n))$

​		(2)如果$A\vDash w$,则$\phi(A)\vDash \phi(w)(=w(q_1,...,q_n))$

*Cor 18.2* 设$P(X_n)$为$X_n$上的命题代数,$p_i\in P(X_n)(i=1,...,n),w=w(x_1,...,x_n)\in P(X_n)$,则有:

​		(1)如果$\vdash w$,则$\vdash w(p_1,...,p_n)$

​		(2)如果$\vDash w$,则$\vDash w(p_1,...,p_n)$

*Thm 18.7* **(子公式替换定理)**:设$w,p,p'\in P(X)$,$p$为$w$的子公式,把$p$在$w$中的某些出现替换为$p'$得到的公式记为$w'$.

​		(1)若$\vdash p\harr p'$,则有$\vdash w\harr w'$

​		(2)若$\vDash p\harr p'$,则有$\vDash w\harr w'$

*Thm 18.8* **(可靠性定理)**:设$A\subseteq P(X),p\in P(X)$.若$A\vdash p$,则有$A\vDash p$.简言之:$Ded(A)\subseteq Con(A)$.

*Cor 18.3* **(协调性定理)**:$F$不是$Prop(X)$​的定理.

*Lem 18.3* 设$A\subseteq P(X)$,则$A$是极大协调子集当且仅当同时满足以下三条:

​		(1)$F\notin A$

​		(2)$A=Ded(A)$

​		(3)对所有的$p\in P(X)$,或者$p\in A$或者$\neg p\in A$

*Lem 18.4* 设$A$是不协调的,则存在$A$的有限子集是不协调的.

*Lem 18.5* 设$A$是$P(X)$的协调子集,则$A$必被某个极大协调子集所包含.

*Thm 18.9* **(可满足性定理)**:设$A$是$P(X)$的协调子集,则存在赋值$v:P(X)\rightarrow Z_2$,使得$v(A)\subseteq \{1\}$.

*Thm 18.10* **(完备性定理)**:设$A\subseteq P(X),p\in P(X)$,若在$Prop(X)$中有$A\vDash p$,则在$Prop(X)$中有$A\vdash p$.

*Lem 18.6* 设$w=w(x_1,...,x_n)\in P(X)$,则$\vDash w$当且仅当$w$的真值函数$f_w$是常值函数$1$.

*Thm 18.11* $Prop(X)$的有效性是可判定的.

*Cor 18.4* $Prop(X)$是可证明性可判定的.

​		