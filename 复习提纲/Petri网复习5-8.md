### 第五章

- #### 谓词/变迁系统的定义

  ![](https://raw.githubusercontent.com/zyxdSTU/Image/master/Petri15.PNG)

- #### 变迁规则

  设$M$为$Pr/T_-$系统$\sum$的一个标识

  - 变迁$t \in T$在$M$有发生 权的充分必要条件是：存在$M$下的可行替换$t(z_1 \leftarrow d_1, z_2 \leftarrow d_2...,z_l \leftarrow d_l)$,其中$\{z_1,z_2, ...\}$,为与$t$有关的符号和及公式中的自由变量集。$M$和$t$的这种发生权记作：

    $M[t(z_1 \leftarrow d_1, z_2 \leftarrow d_2,..z_l \leftarrow d_l)>$

  - 若$M[t(z_1 \leftarrow d_1, z_2 \leftarrow d_2, ..., z_l \leftarrow d_l)>$,则$t$可按可行替换$t(z_1 \leftarrow d_1, z_2 \leftarrow d_2, .., z_l \leftarrow d_l)$发生，其后继标识$M^{'}$为：对所有$p \in P$,

    $M^{'}(p)=M(p)-A_F(p,t)(z_1 \leftarrow d_1, z_2 \leftarrow d_2,... z_l \leftarrow d_l)+A_F(t,p)(z_1 \leftarrow d_1, z_2 \leftarrow d_2,...,z_l \leftarrow d_l)$

- ##### 有色网的定义

  $\sum=(P,T;F,C，I_-,I_+,M_0)$称为有色网的充分必要条件

  - $(P,T;F)$为有向网，称为$\sum$的基网

  - $C:P \cup T \rightarrow N(D), N(D)$为颜色集$D$之幂集合

  - 对$p \in P, C(P)$是库所$p$上所有可能的token色集合

  - 对$t \in T, C(t)$是变迁$t$上所有可能的出现色集合

  - $I_-, I_+$ 分别是$PXT$上的负函数和正函数，使得对所有$(p,t) \in P X T$

    - $I_-(p,t) \in [C(p)_{MS} \rightarrow C(t)_{MS}]_L$,且$I_-(p,t)=0$充分必要条件是$(p,t) \notin F$
    - $I_+(p,t) \in [C(t)_{MS} \rightarrow C(p)_{MS}]_L$,且$I_+(p,t)=0$充分必要条件是$(t,p) \notin F$

  - $M_0:P \rightarrow D_{MS}$,称为$\sum$的初始标识，它必须满足条件$\forall p \in P: M_0(p) \in C(p)_{MS}$

    即$M_0(p)$是$p$的token色集合上的多重集

- ##### 有色网的变迁规则

  设$X$为有色网$\sum$在标识$M$下的一步，则$X$发生后的后继标识$M^{'}$,由下式给出：

  $\forall p \in P, M^{'}(p) = M(p) + \sum_{t\in T}I_+(p,t)(X(t)) - \sum_{t \in T}I_-(p,t)(X(t))$



### 第六章











