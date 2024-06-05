# Chapter 16

## Definition

*Def 16.1* 设$(L;\leq)$为偏序集,若$\forall a,b\in L$,有$a\vee b=lub(a,b)\in L,a\wedge b=glb(a,b)\in L$,称$L$为**格**.

*Def 16.2* $(L,\leq)$为格,若$a\leq b,a\neq b,$且$\nexists u\in L-\{a,b\}:a\leq u\leq b$,则称$b$**覆盖**$a$.当$a<b$,若有$c_1\sim c_k\in L(k\geq 1)$,使$c_{i+1}$覆盖$c_i(i=1,2,...,k-1)$,且有$a=c_1<c_2<...<c_k=b$,则称$c_1...c_k$为连接$a,b$的**链**.若$L$中任两个元素$a<b$,总有连接它们的链,则称$L$是**离散的**.

*Def 16.3* $(L;\leq)$为偏序集,当任意子集$A\subseteq L$有最大下界,最小上界时,$L$显然是格,称为**完全格**.其中$L$自身的最小上界是整个格$L$的最大元,记为$1$;$L$自身的最大下界是整个格$L$的最小元,记为$0$.

*Def 16.4* $[L;\vee,\wedge]$为一代数系统,$\vee,\wedge$为定义在$L$上的二元运算,当其满足$L_1\sim L_4$时,称$L$为**格**,并称$\wedge$为**积(交)**,$\vee$为**和(并)**.若$L$中存在元素$0$,使$\forall x\in L,x\vee 0=x$,则称$0$为$\vee$的单位元,并称$0$为**格$L$的零元**.若$L$中存在元素$1$,使$\forall x\in L,x\wedge1=x$,则称$1$为$\wedge$的单位元,并称$1$为**格$L$的单位元**.

*Def 16.5* $[L;\vee,\wedge]$为格,$T\neq \phi,T\subseteq L$.$T$关于$\vee,\wedge$封闭时($\forall a,b\in T,a\wedge b\in T,a\vee b\in T$),称$T$为$L$的**子格**.

*Def 16.6* 设$[L;\vee,\wedge]$与$[S;+,\cdot]$为两个格.如果存在映射$\phi:L\rightarrow S$, 使$\forall a,b\in L$有:$\phi(a\vee b)=\phi(a)+\phi(b),\phi(a\wedge b)=\phi(a)\cdot \phi(b)$,则称$\phi$为**$L$到$S$的同态映射**.当$\phi(L)=S$即$\phi$为满射时,又称**格$L$与$S$同态**;当$\phi$为一一对应时,称**格$L$与$S$同构**.当$S=L$,分别称其为**自同态**与**自同构**.

*Def 16.7* 若格$[L;\vee,\wedge]$存在零元$0$和单位元$1$,则$0$和$1$分别是$L$的最小元和最大元,称格$[L;\vee,\wedge]$为**有界格**.

*Def 16.8* $[L;\vee,\wedge]$为有界格,对$a\in L$,若$\exist b\in L$,使$a\vee b=1,a\wedge b=0$,则称$b$为$a$的**补元**,记$b$为$a'$.若$L$中每个元都有补元,则称$L$为**有补格**.

*Def 16.9* $[L;\vee,\wedge]$为格,当对$\forall a,b,c\in L$成立分配律(即分配不等式中等号成立),则称该格为**分配格**.即:
$$
D_1:a\vee(b\wedge c)=(a\vee b)\wedge(a\vee c)\\
D_2:a\wedge(b\vee c)=(a\wedge b)\vee(a\wedge c)
$$
*Def 16.10* 有补分配格称为**布尔格**,习惯上写成$(B;\leq)$.又可称为**布尔代数**$[B;\vee,\wedge,']$.

*Def 16.11* 布尔代数$[B;\vee,\wedge,']$中定义$B$上的二元运算$+$和$\cdot$如下:
$$
\forall a,b\in B:a+b=(a\wedge b')\vee(a'\wedge b),a\cdot b=a\wedge b
$$
则在$[B;\vee,\wedge,']$上定义的$[B;+,\cdot]$为可交换的有单位元环.称这样的环为**布尔环**.

*Def 16.12* 一个有单位元环,如果它的每个元素都是幂等的,则称该环为**布尔环**.



## Theorem

*Thm 16.1* $(L;\leq)$为格,则对$\forall a,b\in L$,有:(1)$a\leq a\vee b,b\leq a\vee b,a\wedge b\leq a,a\wedge b\leq b$;(2)$a\leq b\Harr a\vee b=b$;(3)$a\leq b\Harr a\wedge b=a$.

*Thm 16.2* $(L;\leq)$为格,$\forall a,b,c\in L$有:

​	$L_1(幂等律):a\vee a=a,a\wedge a=a$

​	$L_2(交换律):a\vee b=b\vee a,a\wedge b=b\wedge a$

​	$L_3(结合律):a\vee(b\vee c)=(a\vee b)\vee c,a\wedge(b\wedge c)=(a\wedge b)\wedge c$

​	$L_4(吸收率):a\vee(a\wedge b)=a,a\wedge(a\vee b)=a$

*Lem 16.1* 在$[L;\vee,\wedge]$中二元运算$\vee,\wedge$满足$L_1\sim L_4$,则对$\forall a,b\in L,a\wedge b=a\Harr a\vee b=b$.

*Lem 16.2* 在$[L;\vee,\wedge]$中,$\vee,\wedge$满足$L_1\sim L_4$,在$L$上定义二元关系$\leq$:对$\forall a,b\in L$,有$a\leq b\Harr a\vee b=b$.则$(L;\leq)$为偏序集.

*Thm 16.3* 如*Lem 16.2*所得之偏序集$(L;\leq)$为格.



