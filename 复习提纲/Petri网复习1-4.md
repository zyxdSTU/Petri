### 第一章

- ##### 全局状态

  >Petri承认系统全局状态的存在，也认识到全局状态的不可实时可知性。因而依
  >
  >自然界各自为政的方式描述系统中的变化。Petri网的变迁规则用局部确定的方
  >
  >式明确指出变化发生的局部条件，也明确指出变化引起的局部变化。

- ##### 全局时间

  >Petri网里面没有全局时间，只有变化及变化间的依赖关系。依赖关系产生先后次序。

### 第二章

- ##### 有向网定义

  三元组$N(S,T;F)$称为有向网, 满足以下条件

  - $S\cap T = \emptyset$

  - $S\cup T \neq \emptyset$

  - $F \subseteq S \times T \cup T \times S$

  - $dom(F) \cup cod(F) = S \cup T$,  $dom(F)=\{x|\exist \ y：(x,y) \in F\}$

    ${cod}(F)=\{y|\exist \ x:(x,y) \in F\}$

  其中$S,T$分别是库所集和变迁集,又称为$S_-$元素和$T_-$元素，$F$称为流关系，最后一个条件规定网中

  不能有孤立元素(孤立的$S_-元素$和$T_-$元素)

- ##### 网系统定义

  六元组$\sum = (S, T; F, K, W, M_0)$构成网系统的条件是：

  - $N=(S,T;F)构成有向网，称为$$\sum$的基网。
  - $K, W, M_0$依次为容量函数，权函数和标识。$M_0$称为$\sum$初始标识

  $\eta_0=\{0,1,2,...\}$, $\eta=\{1,2,3,..\}$, $w$代表无穷

  - $K:S \rightarrow \eta \cup w$,  称为$N$的容量函数
  - $M:M \rightarrow \eta_0$,称为$N$的一个标识，$\forall s \in S:M(s) \leqslant K(s)$
  - $W:F \rightarrow \eta$,$(x,y) \in F$, $W(x,y)=W((x,y))$称为$(x,y)$上的权

- ##### 发送权

  - $^{*}t^{*}=^*t\cup t ^*$, 称为$t$的外延

  - $t$在$M$上有发生权的条件是：
    $$
    \forall s \in ^*t:M(s) \geqslant W(s,t) \wedge \forall s\in t^*:M(s)+W(t,s)\leqslant K(s)
    $$
    称为$M[t>$, $M$授权发生$t$

- ##### 变迁规则

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/petri.PNG)

- ##### 网分类系统

  - 基本网系统($E/N$系统)

    $K \equiv 1, W \equiv 1, M(s)=0 \ or\  1$

  - 库所/变迁网($P/T网$)

    $K \equiv \infty, W \equiv 1$, $\sum(S,T;F, M_0)$

  - 库所/变迁系统($P/T$系统)

    $\sum=(S,T;F,K,W,M_0)$

    $EN$系统，$P/T网$是$P/T$系统的特例

### 第三章

- ##### 基本网系统的定义

  - $(B,E,F)$是一个基本网系统，$B$称为条件，$E$称为事件

  - $c$称为网上的一个条件丛

  - 事件$e \in E$在网上有发生权的条件是$^*e  \subseteq c \wedge e^* \cap c = \empty$,称为$c[e>$

  - $c[e>c^{'}$,$e$在$c$发生的结果是将$c$变为其后继丛$c^{'}$,$c^{'}=(c-^*e)\cup e^*$

    ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/petri2.PNG)

  - 四元组$N=(B,E;F,c_{in})$为基本网系统的条件是:$(B,E;F)$为条件和事件构成的有向网，$c_{in}$为网上的条件丛，$c_{in} \subseteq B$.基本网系统也称为$EN_-$系统

- ##### 局部确定性

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/petri3.PNG)

  - 变迁的能否发生只依赖它的外延，与全局状态无关。变迁发生的外延是恒定的。即

    $e$在$c$有发生权是取决于$^*e以及e^*$

- ##### 事件的基本关系(顺序，并发，冲突，冲撞)

  - **顺序**

    如果$c[e_1>$,但是$\neg c[e_2>$,而$c^{'}[e_2>$,其中$c[e_1>c^{'}$,就说$e_1$和$e_2$有顺序关系

  - **冲突**

    如果$c[e_1> \wedge \ c[e_2 >$,但是$\neg c[|e_1, e_2| >$,则$e_1,e_2$在$c$上互相冲突

  - **冲撞**

    若有$b \in B, c \in C, e \in E$,使得$^*e  \subseteq c$,而且$b \in c \cap e^*$,则说在情态$c$条件$b$处有冲撞

  - **并发**(无冲撞的条件下)

    $e_1$和$e_2$在情态$c$并发的充分必要条件是$^*e_1\cap ^*e_2=\empty \wedge ^*e_1 \cup ^*e_2 \subseteq c$

  - ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/petri4.PNG)

- ##### T图，S图

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/petri5.PNG)

- ##### 活性定理

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri6.PNG)

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri7.PNG)

- ##### 哲学家就餐问题

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri8.PNG)

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri9.PNG)

### 第四章

- ##### 可达标识集

  $P/T_-$系统$\sum=(S,T;F,K,W,M_0)$的可达标识集$[M_0>$是满足下列条件的最小集合

  - $M_0 \in [M_0 > $
  - 若有$M^{'} \in [M_0>, t \in T$， 使$M^{'}[t > M$, 则$M \in [M_0 > $

- ##### 有界，活性

  - 若对于所有$M \in [M_0 > $，存在正整数$k$,使得对所有$s \in S, M(s)  \leqslant k$,就说$\sum$是有界

    $P/T_-$系统，或以$k$为界的$P/T_-$系统。$k=1$时称$\sum$为安全系统

  - 对$t \in T$,若对任一可达标识$M \in [M_0 >$,均有从M可达的标识$M^{'} \in [M >$,使得$M^{'}[t >$

    就说变迁$t$是活的。

  - 若所有$t \in T$是活的，则说$\sum$是活的。

- ##### 覆盖

  设$M$和$M^{'}$为$P/T_-$系统$\sum$基网$(S,T;F)$上的两个标识

  - 若$\forall s \in S: M(s) \leqslant M^{'}(s)$,就说$M$被$M^{'}$覆盖，记作$M \leqslant M^{'}$
  - 若$M \leqslant M^{'}$,且$M \neq M^{'}$,则说$M$小于$M^{'}$，记作 $M < M^{'}$
  - 若$M < M^{'}$,且$M(s) < M^{'}(s)$,就说$M < M^{'}$在库所$s \in S$成立

- ##### 可达树

  - **可达树构造算法**

    每个节点都有一个标记$M_x$,$M_x:S \rightarrow \{0, 1, 2, ...\} \cup \{w\}$

    - $T(\sum)$的初值只有根节点$r$,$M_r=M_0$,即$M_r$以初始标识标记

    - 令$x$为$T(\sum)$的叶节点，若$t \in T$在标识$x$下均无发生权，则$x$为真叶节点

      若从根节点$r$到$x$的路径上有另一节点$y$, $y \neq x$,但是$M(x) == M(y)$则$x$也是真叶节点

      若所有的叶节点均为真叶节点，则算法终止，否则执行下一步

    - 若$x$是$T(\sum)$的叶节点，但不是真叶节点，则在$M_x$上至少有一个变迁有发生权

      对$M_x$授权发生的每个变迁$t \in T$,在$T(\sum)$上添加一个新节点$y$, $y$是$x$的子节点，

      从$x到y$的有向弧用变迁$t$标记，节点$y$的标记$M_y$是如下定义的：首先计算出$M_x$的后继

      $M^{'}$,然后计算$M_y$,对所有$s \in S$,

      $M_y(s) = w​$,  若从$r​$到$y​$的路径上有节点$z​$,使得$M_z<M^{'}​$且$M_z(s) < M^{'}(s)​$

      $M_y(s) = M^{'}(s)$ 否则

    - 回到第二步骤

  - **可达树性质**

    - 只要$\sum$是有限无冲撞的，$T(\sum)$必为有限树

    - 令$M \in [M_0 > $为任一可达标识，则在覆盖树$T(\sum)$上必有节点$x$,使得$M \leqslant M_x$,

      其中$M_x$是$x$的标记，若$w$不出现在$M_x$中，$M=M_x$

    - 设$x$为$T(\sum)$的节点， $M_x$是它的标记

      若$w$不是$M_x$的分量，则$M_x \in [M_0 >$

      若$w$是$M_x$的分量，则存在可达标识序列$M_1M_2...M_i..$,使$\forall i \ M_i \in [M_0 >$

      且对所有$s \in S:$

      $M_i(s) = M_x(s)  若M_x(s) \neq w$

      $M_i(s)  \geqslant i$ 若 $M_x(s) = w$

- ##### 可达图

  - **可达图的构造算法：**如果存在从$T(\sum)$到$G$的满映射$h$,$T(\sum) \rightarrow G$使得

    - $x$为$T(\sum)$的节点，则$h(x)$为$G$的节点，且$h(x)$以$x$在$T(\sum)$中的标记$M_x$为标记

    - $(x,y)$为$T(\sum)$上以变迁$t$为标记的有向弧，则$(h(x), h(y))$为$G$上以$t$为标记的有向弧

    - $x \neq y $为$T(\sum)$的不同节点，则当且仅当$M_x =M_y$且$x和y$同在从$T(\sum)$根节点$r$出发

      的同一条路径时，才有$h(x)=h(y)$

  - **可达图的性质**

    - 若$G(\sum)$有末端节点，则$\sum$的任何变迁都不是活的
    - 若$\sum$的变迁$t$是活的，则$G(\sum)$的每个节点之下都含有以$t$为标记的有向弧的基本圈
    - 若$\sum$是活的，则对任何$t \in T, G(\sum)$的每个节点之下都含有以$t$标记的有向弧的基本圈

- ##### 出现网

  $Net(B,E;F)\wedge \forall b \in B:(|^*b| \leqslant  1 \wedge|b^*| \leqslant 1) \wedge F^+ \cap((F^{-1})^+ = \empty)$

  第二个条件是，最多有一个输入一个输出，最后一个条件是不包含环

- ##### 进程

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri10.PNG)

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri11.PNG)

- ##### 线和切

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri12.PNG)

- ##### 状态方程，$S_-,T_-$不变量

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri13.PNG)

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri14.PNG)









