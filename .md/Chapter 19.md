# Chapter 19

## Definition

- 在谓词逻辑中，命题是用形如$P(x_1,x_2,...,x_n)$​的**谓词**来表述的.一个谓词可分为**谓词名**与**个体**两个部分.
  - **个体**是命题的主语,表示独立存在的事物或某个抽象的概念.分为:
    - **个体常量**:1,2,张三...
    - **个体变元**:$x_1,x_2,...$
    - **函数**:$father(Zhang)$...
  - **谓词名**表示个体的性质,状态或个体之间的关系,一般用大写字母表示.
- 在$n$元谓词$P(x_1,x_2,...,x_n)$中,若每个个体均为常量,变元或函数,则称它为**一阶谓词**.如果某个个体本身又是一个一阶谓词,则称它为**二阶谓词**,如此类推.
- **谓词公式**
  - **原子谓词公式**:由谓词符号和若干项组成的谓词演算.
  - **分子谓词公式**:可以用连词把原子谓词公式组成复合谓词公式,并把它叫做分子谓词公式.
  - **合式公式(WFF)**:通常把合式公式叫做谓词公式,采用递归定义.

***

*Def 19.1* 由表示某种不确定的可列个个体对象全体所组成的集合称为**个体变元集**,记为$X=\{x_1,...,x_n,...\}$,这里$x_i$称为**个体变元**,用来表示不确定的个体对象.由表示某种确定的个体对象全体所组成的集合称为**个体常元集**,它是可列集或有限集,也可以是空集,记为$C=\{c_1,...,c_n,...\}$,这里$c_i$称为**个体常元**,用来表示某个确定的个体对象.

*Def 19.2* $X\cup C$上的自由$T^{(1)}$-代数$I$称为**项集**,$I$中的每个元素称为**项**,不含个体变元的项称为**闭项**,$I$上的代数运算$f_n^i$称为第$i$个**$n$元函数词**.

<img src="C:\Users\洪成勋\AppData\Roaming\Typora\typora-user-images\image-20240608124153141.png" alt="image-20240608124153141" style="zoom: 50%;" />

eg.$C=\phi,X=\{p,q\},T=\{F,\rightarrow\}$

- $I_0=X\cup C=X=\{p,q\}$​

- $I_1=\{F\}\cup\{(\rightarrow,x_j,x_k)|x_j,x_k\in I_0\}$

  ​     $=\{F,p\rightarrow p,q\rightarrow q,p\rightarrow q,q\rightarrow p\}$​

- ...

*Def 19.3* 设关系集$R=\bigcup^\infin_{n=0}R_n$,其中$R_n$表示某个对象集上的所有$n$元关系,即$R_n=\{R_n^i|ar(R_n^i)=n\}$.

- **关系即谓词**.

*Def 19.4* 对任意的$R_n^i\in R_n\subseteq R$,称$I$上的$n$元关系$R_n^i(t_1,...,t_n)$为$I$上的**原子公式**(特别地,$R_0^i$就是原子命题公式).这里$t_1,...,t_n\in I$,$R_n^i$称为第$i$个$n$元谓词.基于关系集$R$的所有$I$上的原子公式全体称为$I$的**原子公式集**,记为$Y$.

<img src="C:\Users\洪成勋\AppData\Roaming\Typora\typora-user-images\image-20240608131113221.png" alt="image-20240608131113221" style="zoom:50%;" />

*Def 19.5* 原子公式集(作为生成元集)$Y=\{R_n(t_1,...,t_n)|R_n\in R,t_i\in I,1\leq i\leq n\}$上关于类型$\{F,\rightarrow,\forall x|x\in X\}$的自由代数称为**谓词代数**,记为$P(Y)$,$P(Y)$中的元素称为**谓词合式公式**,因此$P(Y)$也成为**谓词公式集**.这里$F$是零元运算,$\rightarrow$是二元运算,而$\forall x$则是一元运算.

- 利用$F,\rightarrow,\forall x$来定义一元运算$\neg$和$\exist x$,以及二元运算$\vee,\wedge,\harr$:
  - $\neg p {\scriptsize{def}\atop=}p\rightarrow F$
  - $\exist x {\scriptsize{def}\atop=}\neg\forall x\neg$
  - $p\vee q{\scriptsize{def}\atop=}\neg p\rightarrow q$
  - $p\wedge q{\scriptsize{def}\atop=}\neg(\neg p\vee\neg q)$
  - $p\harr q{\scriptsize{def}\atop=}(p\rightarrow q)\wedge(q\rightarrow p)$

*Def 19.6* 在谓词合式公式$q=\theta xp$(这里$\theta$表示$\forall$或$\exist$)中,称$p$为$\theta x$的**辖域**,$p$中$x$的出现称为$x$在$q$中的**约束出现**,$p$中不是约束出现的其它变元的出现称为变元在$q$中的**自由出现**.如果变元$x$在$q$中约束/自由出现,则称$x$是$q$中的**约束/自由变元**.$q$中自由出现的个体变元全体构成的集合用$var(q)$表示.若$var(q)=\phi$,则称$q$为**闭式**,此时$q$中无自由变元.

*Def 19.7* 设$p(x)$是$P(Y)$中谓词合式公式,$x$是其自由变元之一,$t(z)$是项,$z$代表$t$中的任一个个体变元.当$x$不出现在$p$的$\theta z$的辖域内,则称$t$对于$p$中的$x$是**自由的**,否则就称$t$对于$p$中的$x$​是**不自由的**.

<img src="C:\Users\洪成勋\AppData\Roaming\Typora\typora-user-images\image-20240608135524095.png" alt="image-20240608135524095" style="zoom:50%;" />

*Def 19.8* 设$p\in P(Y)$,$p$的**量词深度**和**层次**分别用$d(p)$和$l(p)$表示,定义为:

​		(1)若$q$是$P(Y)$中的原子公式,则$d(q)=l(q)=d(F)=l(F)=0$

​		(2)$d(p_1\rightarrow p_2)=\max\{d(p_1),d(p_2)\},l(p_1\rightarrow p_2)=1+\max\{l(p_1),l(p_2)\}$

​		(3)$d(\forall xp)=\{^{1+d(p),x\in var(p)}_{d(p),x\notin var(p)},l(\forall xp)=1+l(p)$

- $P(Y)$的解释域

  $P(Y)$的解释域是一个四元组$(U,\varphi_1,\varphi_2,\varphi_3)$,其中:

  - $U$是非空集,称为**论域**
  - $\varphi_1$是$C\rightarrow U$的函数
  - $\varphi_2$是$P(Y)$上的函数词集合到$U$上运算集的函数,使得$\varphi_2(f^i_n)={f'}^i_n$,这里${f'}^i_n$是$U$上的$n$元运算.
  - $\varphi_3$是$P(Y)$上的谓词集合到$U$上关系集的函数,使得$\varphi_3(R^i_n)={R'}^i_n$,这里${R'}^i_n$是$U$上的$n$元关系.

  解释域$U$中的元素也称为**个体对象**.通常把解释域$(U,\varphi_1,\varphi_2,\varphi_3)$简记为$\mathcal{U}$​.

*Def 19.9* $X\rightarrow U$的映射$\varphi_0$称为个体变元的**指派**,$I\rightarrow U$的同态映射$\varphi$称为**项解释**.

- 对同一解释域可以有不同的变元指派,就会有不同的项解释.

- 给定解释域$\mathcal{U}$和项解释$\varphi$下:原子公式集$Y$记为$Y^{U,\varphi}$,谓词公式集$P(Y)$记为$P(Y^{U,\varphi})$.

<img src="C:\Users\洪成勋\AppData\Roaming\Typora\typora-user-images\image-20240608152846281.png" alt="image-20240608152846281" style="zoom:50%;" />

*Def 19.10* 谓词公式的**赋值函数**$v:P(Y^{U,\varphi})\rightarrow Z_2$分三步$(a),(b),(c_k)$​定义如下:

​		$(a)$对于原子公式$p=R_n^i(t_1,...,t_n)\in Y^{U,\varphi}$定义:当$(\varphi(t_1),...,\varphi(t_n))\in {R'}^i_n$时,$v(p)=1$.否则,$v(p)=0$.

​		$(b)$$v$是$\{F,\rightarrow\}$-代数的同态映射.即:$v(F)=0$.对任何$p,q\in P(Y^{U,\varphi})$,有$v(p\rightarrow q)=v(p)\rightarrow v(q)$.

- 设$P_k(Y^{U,\varphi})=\{p|p\in P(Y^{U,\varphi}),d(p)\leq k\}$,于是$P(Y^{U,\varphi})=\bigcup_{k\geq 0}P_k(Y^{U,\varphi})$.

​		$(c_k)$设$p=\forall xq(x)\in P_k(Y^{U,\varphi})$,则$q(x)\in P_{k-1}(Y^{U,\varphi})$,取$X'=X\cup \{x'\}$,这里$x'\notin X\cup C$.如果对$\varphi_0$的每个扩张$\varphi_0':X'\rightarrow U$,和每个满足$(a),(b),(c_i)(i<k)$的$v'_{k-1}:P_{k-1}(Y^{U,\varphi'})\rightarrow Z_2$,总有$v'_{k-1}(q(x'))=1$,那么:定义$v(p)=1$;否则定义$v(p)=0$.

*Def 19.11* 设$p\in P(Y)$:

- 若在解释域$\mathcal{U}$和项解释$\varphi$下,有$v(p)=1$,则称**$p$在解释域$\mathcal{U}$和项解释$\varphi$​下取值为真**.
- 若在某解释域$\mathcal{U}$下,对任一项解释$\varphi$,$p$的取值总为真,则称$p$在解释域$\mathcal{U}$下是**有效的**.
- 若对任一解释域和任一项解释,$p$都是有效的,则称$p$为**有效式**,也称为**重言式**.

*Def 19.12* 设$A\subseteq P(Y),p\in P(Y),v(A)=\{v(q)|q\in A\}$,若不存在一个使得$v(A)\subseteq \{1\}$而$v(p)=0$的解释域和项解释,则称$p$是假设集$A$的**后件**,或称$A$**语义蕴含**$p$,记为$A\vDash p$,用$Con(A)$表示$A$的后件全体,即$Con(A)=\{p\in P(Y)|A\vDash p\}$.

*Def 19.13* 设$p,q\in P(Y)$,若$\{p\}\vDash q$且$\{q\}\vDash p$,则称$p,q$**等价**,记为$p\mid=\mid q$​​.

- $P(Y)$上的一阶谓词演算用$Pred(Y)$表示.

*Def 19.14* $Pred(Y)$上的**公理集**$\mathcal{A}=\mathcal{A}_1\cup\mathcal{A}_2\cup\mathcal{A}_3\cup\mathcal{A}_4\cup\mathcal{A}_5$.其中:

​		$\mathcal{A}_1=\{p\rightarrow(q\rightarrow p)|p,q\in P(Y)\}$

​		$\mathcal{A}_2=\{(p\rightarrow(q\rightarrow r))\rightarrow((p\rightarrow q)\rightarrow(p\rightarrow r))|p,q,r\in P(Y)\}$

​		$\mathcal{A}_3=\{\neg \neg p\rightarrow p|p\in P(Y)\}$

​		$\mathcal{A}_4=\{\forall x(p\rightarrow q)\rightarrow(p\rightarrow\forall xq)|p,q\in P(Y),x\notin var(p)\}$

​		$\mathcal{A}_5=\{\forall xp(x)\rightarrow p(t)|p(x)\in P(Y),项t对p(x)中的x是自由的\}$

- 如果存在一个由$A$导出$p$的证明,则记为$A\vdash p$,且用$Ded(A)$表示满足$A\vdash p$的所有$p$的全体.当$\phi\vdash p$,简写为$\vdash p$,并称$p$为$Pred(Y)$的**定理**.
- **全称推广规则(G规则)**——除$MP$规则外的另一个重要推理规则:对任意的$x$证明了$p(x)$,则有$\forall xp(x)$成立.即:对一般的$x$证明了$p(x)$后,可推出$\forall xp(x)$.

*Def 19.15* 设$p\in P(Y),A\subseteq P(Y)$,**由假设$A$导出$p$的长度为$n$的证明**是一组有限序列:$p_1,...,p_n$,这里$p_i\in P(Y)(i=1,...,n),p_n=p$,而$p_1,...,p_{n_1}$是长度为$n-1$的由$A$导出$p_{n-1}$的证明序列,并且:对所有$k\leq n$:

​		(1)$p_k\in A\cup \mathcal{A}$,或者

​		(2)存在$i,j(i,j<k)$,有$p_i=(p_j\rightarrow p_k)$,或者

​		(3)$p_k=\forall xw(x)$,并且$p_1,...,p_{k-1}$的某个子序列$p_{k_1},...,p_{k_r}$是一个由$A$的子集$A_0(x\notin var(A_0))$导出$w(x)$的证明(长度小于$n$​).

*Def 19.16* 设$p,q\in P(Y)$,若$\{p\}\vdash q$且$\{q\}\vdash p$,则称$p,q$**语法等价**,记为$p\vdash\dashv q$​.

*Def 19.17* 设$P_1=P(Y_1)$和$P_2=P(Y_2)$,其个体变元与个体常元分别为$X_1,C_1$和$X_2,C_2$,并且或者$C_1=\phi$,或者$C_2\neq\phi$,那么:一个**半同态映射**$(\alpha,\beta):(P_1,X_1\cup C_1)\rightarrow(P_2,X_2\cup C_2)$是一对映射$\alpha:P_1\rightarrow P_2;\beta:X_1\cup C_1\rightarrow X_2\cup C_2$.它们联合实现了映射$p(x,c)\rightarrow \alpha(p)(\beta(x),\beta(c))$​,且具有性质:

​		(1)$\beta(X_1)\subseteq X_2,\beta(C_1)\subseteq C_2$,而且$\beta$在$X_1$上是一对一的

​		(2)$\alpha$是$\{F,\rightarrow\}$-同态映射

​		(3)对任何$p\in P_1$有$\alpha(\forall xp)=\forall \beta(x)\alpha(p)$​

*Def 19.18* **(前束范式)**:$p\in P(Y)$为**前束范式**,当且仅当它具有下面的形式:$p=\theta_1x_1\theta_2x_2...\theta_kx_kq$,

- 其中$\theta_i(i=1,...,k)$是$\forall$或$\exist$
- 且$x_1,x_2,...,x_k$是不同的 
- $q$是$P(Y)$中不带量词的公式
- 称$\theta_1x_1\theta_2x_2...\theta_kx_k$为**前束**，称$q$​为**母式**

*Def 19.19* 设$p\in P(Y)$,称与$p$语法等价的前束范式为**$p$​的前束范式**.

*Def 19.20* **(斯柯伦范式)**:$p\in P(Y)$是前束范式,而且它的形式:$p=\theta_1x_1\theta_2x_2...\theta_kx_kq$中的所有$\forall$(如果有的话)总在$\exist$(如果有的话)的后面,则称$p$为**斯柯伦(T.Skolem)范式**.



## Theorem

*Thm 19.1* 设$\mathcal{U}$为$P(Y)$的一个解释域,$\varphi_0$为$X\rightarrow U$的映射,则$\varphi_0$可唯一扩张为$I\rightarrow U$的同态映射$\varphi$,使得$\varphi(c_i)=c_i'$.这里$c_i'$为$U$​​中的元素.

*Lem 19.1* 设$v_0$为$Y^{U,\varphi}\rightarrow Z_2$的映射,则$v_0$可唯一扩张为$P_0(Y^{U,\varphi})\rightarrow Z_2$的同态映射$v_0'$,这里的同态是指关于$\{F,\rightarrow\}$的同态.

*Thm 19.2* 设$v_0$为$Y^{U,\varphi}\rightarrow Z_2$的映射,则$v_0$可唯一扩张为$P(Y^{U,\varphi})\rightarrow Z_2$的同态映射$v$,并对量词深度满足*Def 19.10*定义过程.则称$v$为$P(Y^{U,\varphi})$​的赋值.

- $v(p\rightarrow q)=1+v(p)+v(p)v(q)$
- $v(\neg p)=1+v(p)$
- $v(p\vee q)=v(p)+v(q)+v(p)v(q)$
- $v(p\wedge q)=v(p)v(q)$
- $v(p\harr q)=1+v(p)+v(q)$
- $v(\exist xp)=1+v(\forall x\neg p)$

*Thm 19.3* 设$p,q\in P(Y)$,

​		(1)如果$p$和$q$语义等价,则$\forall xp\mid=\mid\forall xq$

​		(2)在$p$中将$\theta xq(x)$的某些(不一定所有)出现替换为$\theta yq(y)$而得到$p'$(这里$y$不在$q(x)$中出现),则$p\mid=\mid p'$

*Thm 19.4* 设$p,p_1,p_2\in P(Y),p_1\mid=\mid p_2$,在$p$中将$p_1$的某些出现替换为$p_2$而得到的结果记为$p'$,则$p\mid=\mid p'$.

*Thm 19.5* **(演绎定理)**:设$A\subseteq P=P(Y)$,设$p,q\in P$,则$A\vdash p\rightarrow q$当且仅当$A\cup\{p\}\vdash q$​.

*Lem 19.2* 若$p\vdash \dashv q$,则$\forall xp\vdash\dashv \forall xq$.

*Thm 19.6* **(等价替换定理)**:设$p,p_1,p_2\in P(Y),p_1\vdash \dashv p_2$,在$p$中将$p_1$的某些出现替换为$p_2$而得到的结果记为$p'$,则$p\vdash \dashv p'$​.

*Thm 19.7* **(约束变元符可替换性)**:设在$p$中将$\theta xq(x)$的某些出现替换为$\theta yq(y)$而得到$p'$(这里$y\notin var(q(x))$,且$p(x)$中的自由变元$x$不会出现在$\theta y$的辖域中),则$p\vdash\dashv p'$.

*Thm 19.8* 在$P(Y)$中有:

​		(1)$p\rightarrow q\vdash\dashv \neg p\vee q$

​		(2)$p\harr q\vdash\dashv (\neg p\vee q)\wedge(p\vee\neg q)$

​		(3)$p\harr q\vdash\dashv (p\wedge q)\vee(\neg p\wedge\neg q)$

​		(4)$\neg\neg p\vdash\dashv p$

​		(5)$\neg\theta xp(x)\vdash\dashv \theta'x\neg p(x)$,这里用$\forall'$和$\exist'$分别表示$\exist$和$\forall$

​		(6)$p\wedge \theta xq(x)\vdash\dashv \theta x(p\wedge q(x))$,要求$x\notin var(p)$

​		(7)$p\vee\theta xq(x)\vdash\dashv \theta x(p\vee q(x))$,要求$x\notin var(p)$

​		(8)$\forall xp(x)\wedge\forall xq(x)\vdash\dashv \forall x(p(x)\wedge q(x))$

​		(9)$\exist xp(x)\vee\exist xq(x)\vdash\dashv \exist x(p(x)\vee q(x))$

​		(10)$\theta_1xp(x)\wedge \theta_2yq(y)\vdash\dashv \theta_1x\theta_2y(p(x)\wedge q(y))$,要求$x\notin var(q(y)),y\notin var(p(x))$

​		(11)$\theta_1xp(x)\vee \theta_2yq(y)\vdash\dashv \theta_1x\theta_2y(p(x)\vee q(y))$,要求$x\notin var(q(y)),y\notin var(p(x))$

*Lem 19.3* 设$(\alpha,\beta):(P_1,X_1\cup C_1)\rightarrow (P_2,X_2\cup C_2)$是半同态映射,$p\in P_1$,并且假设$x\notin var(p)$.则$\beta(x)\notin var(\alpha(p))$.

*Thm 19.9* **(代换定理)**:设$(\alpha,\beta):(P_1,X_1\cup C_1)\rightarrow (P_2,X_2\cup C_2)$是半同态映射,$A\subseteq P_1,p\in P_1$.如果$A\vdash p$,则$\alpha(A)\vdash \alpha(p)$​.

*Thm 19.10* 对任何$p\in P(Y)$,有前束范式$p'$满足$p\vdash\dashv p'$​.

*Thm 19.11* **(可靠性定理)**:设$A\subseteq P(Y),p\in P(Y)$.若$A\vdash p$,则有$A\vDash p$.

*Cor 19.1* **(协调性定理)**:$F$不是$Pred(Y)$的定理.

*Lem 19.4* 设$A$是$P(Y)$的协调子集.如果$\exist xp(x)\in A,y\notin var(A)$,且项$y$对$p(x)$中的自由变元$x$自由,则$F\notin Ded(A\cup p(y))$.

*Lem 19.5* 设$A$是$P(Y)$的协调子集,则存在$X\subseteq X^*,A\subseteq A^*$,这里$A^*\subseteq P(Y^*)$($P(Y^*)$中的项集为$X^*\cup C$上的自由代数),使得:

​		(1)$F\notin Ded(A^*)$

​		(2)对所有的$p\in P(Y^*)$,或者$p\in A^*$,或者$\neg p\in A^*$

​		(3)如果$\exist xp(x)\in A^*$,则存在$x'\in X^*$,使得$p(x')\in A^*$.

*Thm 19.12* **(可满足性定理)**:设$A$是$P(Y)$的协调子集,则存在$P(Y)$的解释域$\mathcal{U}$和项解释$\varphi$,使得$v(A)\subseteq\{1\}$.

*Thm 19.13* **(完备性定理)**:设$A\subseteq P(Y),p\in P(Y)$,若$A\vDash p$,则有$A\vdash p$​.

*Thm 19.14* **(紧致性定理)**:如果$A\vDash p$,则存在$A$的某个有限子集$A_0$,使得$A_0\vDash p$.