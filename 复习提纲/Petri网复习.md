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

























