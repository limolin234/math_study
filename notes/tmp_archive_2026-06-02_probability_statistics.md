# tmp.md 归档：概率统计基础

归档时间：2026-06-02

---

# tmp 黑板

## 当前主题：概率论：二维随机变量的相关系数

### 1. 相关系数解决什么问题？

两个随机变量 \(X,Y\) 之间可能有线性关系。

相关系数用来衡量：

\[
X \text{ 和 } Y \text{ 的线性相关程度有多强。}
\]

它的取值范围是

\[
-1\le \rho_{XY}\le 1.
\]

其中：

\[
\rho_{XY}>0
\]

表示正相关；

\[
\rho_{XY}<0
\]

表示负相关；

\[
\rho_{XY}=0
\]

表示不线性相关。

注意：\(\rho_{XY}=0\) 只表示不线性相关，不一定表示独立。

---

### 2. 先定义协方差

相关系数的核心是协方差。

协方差定义为

\[
\operatorname{Cov}(X,Y)
=E\{[X-E(X)][Y-E(Y)]\}.
\]

常用计算公式是

\[
\operatorname{Cov}(X,Y)=E(XY)-E(X)E(Y).
\]

协方差表示：

- \(X\) 大于自身均值时，\(Y\) 是否也倾向于大于自身均值；
- \(X\) 小于自身均值时，\(Y\) 是否也倾向于小于自身均值。

如果这种同向变化明显，协方差为正。

如果一个大时另一个小，协方差为负。

---

### 3. 相关系数公式

若

\[
D(X)>0,
\qquad
D(Y)>0,
\]

则 \(X,Y\) 的相关系数为

\[
\rho_{XY}
=\frac{\operatorname{Cov}(X,Y)}{\sqrt{D(X)}\sqrt{D(Y)}}.
\]

也就是

\[
\rho_{XY}
=\frac{E(XY)-E(X)E(Y)}
{\sqrt{D(X)}\sqrt{D(Y)}}.
\]

其中

\[
D(X)=E(X^2)-[E(X)]^2,
\]

\[
D(Y)=E(Y^2)-[E(Y)]^2.
\]

---

### 4. 实际计算步骤

计算 \(\rho_{XY}\) 时，不要直接硬套，按下面顺序来。

#### 第一步：算 \(E(X)\)

\[
E(X)
\]

#### 第二步：算 \(E(Y)\)

\[
E(Y)
\]

#### 第三步：算 \(E(XY)\)

\[
E(XY)
\]

#### 第四步：算 \(D(X)\)、\(D(Y)\)

\[
D(X)=E(X^2)-[E(X)]^2,
\]

\[
D(Y)=E(Y^2)-[E(Y)]^2.
\]

#### 第五步：算协方差

\[
\operatorname{Cov}(X,Y)=E(XY)-E(X)E(Y).
\]

#### 第六步：代入相关系数公式

\[
\rho_{XY}
=\frac{\operatorname{Cov}(X,Y)}{\sqrt{D(X)}\sqrt{D(Y)}}.
\]

---

### 5. 离散型二维随机变量怎么求？

如果 \((X,Y)\) 是离散型二维随机变量，联合分布为

\[
P\{X=x_i,Y=y_j\}=p_{ij},
\]

那么

\[
E(X)=\sum_i\sum_j x_i p_{ij},
\]

\[
E(Y)=\sum_i\sum_j y_j p_{ij},
\]

\[
E(XY)=\sum_i\sum_j x_i y_j p_{ij}.
\]

同理

\[
E(X^2)=\sum_i\sum_j x_i^2p_{ij},
\]

\[
E(Y^2)=\sum_i\sum_j y_j^2p_{ij}.
\]

然后代入公式即可。

---

### 6. 连续型二维随机变量怎么求？

如果 \((X,Y)\) 有联合密度 \(f(x,y)\)，那么

\[
E(X)=\iint_D x f(x,y)\,dxdy,
\]

\[
E(Y)=\iint_D y f(x,y)\,dxdy,
\]

\[
E(XY)=\iint_D xy f(x,y)\,dxdy.
\]

以及

\[
E(X^2)=\iint_D x^2 f(x,y)\,dxdy,
\]

\[
E(Y^2)=\iint_D y^2 f(x,y)\,dxdy.
\]

最后还是用

\[
\rho_{XY}
=\frac{E(XY)-E(X)E(Y)}
{\sqrt{D(X)}\sqrt{D(Y)}}.
\]

---

### 7. 相关系数和独立性的关系

如果 \(X\) 与 \(Y\) 独立，并且方差存在，则

\[
E(XY)=E(X)E(Y).
\]

因此

\[
\operatorname{Cov}(X,Y)=0,
\]

所以

\[
\rho_{XY}=0.
\]

也就是说：

\[
X,Y \text{ 独立 } \Longrightarrow \rho_{XY}=0.
\]

但反过来一般不成立：

\[
\rho_{XY}=0 \nRightarrow X,Y \text{ 独立}.
\]

相关系数只检测线性关系，不检测所有关系。

---

### 8. 最小记忆

相关系数公式：

\[
\rho_{XY}
=\frac{\operatorname{Cov}(X,Y)}{\sqrt{D(X)}\sqrt{D(Y)}}.
\]

协方差公式：

\[
\operatorname{Cov}(X,Y)=E(XY)-E(X)E(Y).
\]

方差公式：

\[
D(X)=E(X^2)-[E(X)]^2.
\]

计算顺序：

\[
E(X),\ E(Y),\ E(XY),\ D(X),\ D(Y),\ \operatorname{Cov}(X,Y),\ \rho_{XY}.
\]

---

## 条件分布、边缘分布与独立性

设二维随机变量为 \((X,Y)\)，联合密度为

\[
f_{X,Y}(x,y).
\]

边缘密度分别是

\[
f_X(x)=\int_{-\infty}^{\infty} f_{X,Y}(x,y)\,dy,
\]

\[
f_Y(y)=\int_{-\infty}^{\infty} f_{X,Y}(x,y)\,dx.
\]

这里的边缘分布只描述单个变量自己长什么样；它不描述两个变量之间如何配对。

---

### 1. 固定一个切面时看到的不是边缘分布，而是条件分布

如果固定 \(X=x\)，沿着 \(y\) 方向看到的是 \(Y\) 在条件 \(X=x\) 下的条件密度：

\[
f_{Y\mid X=x}(y)
=\frac{f_{X,Y}(x,y)}{f_X(x)},
\qquad f_X(x)>0.
\]

如果固定 \(Y=y\)，沿着 \(x\) 方向看到的是 \(X\) 在条件 \(Y=y\) 下的条件密度：

\[
f_{X\mid Y=y}(x)
=\frac{f_{X,Y}(x,y)}{f_Y(y)},
\qquad f_Y(y)>0.
\]

所以“每个切面上的分布一样”更标准的说法是：

\[
\text{条件分布不随被条件变量改变。}
\]

---

### 2. 独立性的条件分布写法

\(X\) 与 \(Y\) 独立，当且仅当

\[
f_{Y\mid X=x}(y)=f_Y(y),
\qquad \text{for a.e. }x.
\]

意思是：知道 \(X=x\) 以后，\(Y\) 的分布没有改变。

等价地，

\[
f_{X\mid Y=y}(x)=f_X(x),
\qquad \text{for a.e. }y.
\]

意思是：知道 \(Y=y\) 以后，\(X\) 的分布没有改变。

用分布律符号可以写成

\[
\mathcal L(Y\mid X=x)=\mathcal L(Y),
\qquad \text{for a.e. }x,
\]

或者

\[
\mathcal L(X\mid Y=y)=\mathcal L(X),
\qquad \text{for a.e. }y.
\]

其中 \(\mathcal L(\cdot)\) 表示随机变量的分布律。

---

### 3. 独立性的联合密度写法

如果存在联合密度，则独立性也等价于

\[
f_{X,Y}(x,y)=f_X(x)f_Y(y),
\qquad \text{a.e. }(x,y).
\]

也就是说，二维联合密度可以拆成两个一维边缘密度的乘积。

这才是独立性的标准密度判据。

---

### 4. 和“切片相同”的关系

独立时有

\[
f_{X,Y}(x,y)=f_X(x)f_Y(y).
\]

固定 \(x\) 后，作为 \(y\) 的函数，它的形状都是 \(f_Y(y)\)，但前面乘了一个系数 \(f_X(x)\)。

所以一般只能说

\[
f_{X,Y}(x_1,y) \propto f_{X,Y}(x_2,y),
\]

而不能直接说

\[
f_{X,Y}(x_1,y)=f_{X,Y}(x_2,y).
\]

只有在 \(f_X(x)\) 是常数的特殊情况下，例如 \(X\) 在某个区间上均匀分布，联合密度的不同 \(x\) 切片才可能真的高度也相同。

---

### 5. 最小记忆

不要说：

\[
\text{任意切面上的边缘分布相同。}
\]

更准确地说：

\[
\text{任意切面上的条件分布相同。}
\]

符号上记为

\[
X\perp Y
\iff
f_{Y\mid X=x}(y)=f_Y(y),\quad \text{for a.e. }x.
\]

也可以记为

\[
X\perp Y
\iff
f_{X\mid Y=y}(x)=f_X(x),\quad \text{for a.e. }y.
\]

一句话：

\[
\boxed{\text{独立性表示：知道其中一个变量，不会改变另一个变量的分布。}}
\]


---

## 切比雪夫不等式

设随机变量 \(X\) 的期望和方差存在：

\[
E(X)=\mu,
\qquad
D(X)=\operatorname{Var}(X)=\sigma^2.
\]

则对任意 \(\varepsilon>0\)，有

\[
P(|X-\mu|\ge \varepsilon)
\le
\frac{\sigma^2}{\varepsilon^2}.
\]

也常写成：对任意 \(k>0\)，

\[
P(|X-\mu|\ge k\sigma)
\le
\frac{1}{k^2}.
\]

直观意思是：随机变量偏离均值很多的概率，受到方差控制。方差越小，远离均值的概率越小。

---

### 1. 从马尔可夫不等式推出

马尔可夫不等式：如果 \(Z\ge 0\)，且 \(a>0\)，则

\[
P(Z\ge a)
\le
\frac{E(Z)}{a}.
\]

令

\[
Z=(X-\mu)^2.
\]

因为平方非负，所以 \(Z\ge 0\)。

事件

\[
|X-\mu|\ge \varepsilon
\]

等价于

\[
(X-\mu)^2\ge \varepsilon^2.
\]

因此

\[
P(|X-\mu|\ge \varepsilon)
=
P((X-\mu)^2\ge \varepsilon^2).
\]

对非负随机变量 \((X-\mu)^2\) 使用马尔可夫不等式：

\[
P((X-\mu)^2\ge \varepsilon^2)
\le
\frac{E[(X-\mu)^2]}{\varepsilon^2}.
\]

又因为

\[
E[(X-\mu)^2]=D(X)=\sigma^2,
\]

所以

\[
P(|X-\mu|\ge \varepsilon)
\le
\frac{D(X)}{\varepsilon^2}.
\]

这就是切比雪夫不等式。

---

### 2. 例子

若

\[
E(X)=100,
\qquad
D(X)=25,
\]

则标准差是

\[
\sigma=5.
\]

问偏离均值至少 \(20\) 的概率最多多少：

\[
P(|X-100|\ge 20)
\le
\frac{25}{20^2}
=
\frac{25}{400}
=
\frac{1}{16}.
\]

也就是最多

\[
6.25\%.
\]

---

### 3. 它有什么用

切比雪夫不等式的特点是：不要求知道 \(X\) 的具体分布。

只要知道均值和方差，就能给出偏离均值的概率上界。

它常用于：

1. 粗略估计随机变量的集中程度；
2. 从方差判断随机变量是否容易远离均值；
3. 证明大数定律。

例如独立同分布随机变量 \(X_1,\dots,X_n\)，设

\[
E(X_i)=\mu,
\qquad
D(X_i)=\sigma^2.
\]

样本均值为

\[
\overline X_n=\frac{1}{n}\sum_{i=1}^n X_i.
\]

则

\[
E(\overline X_n)=\mu,
\qquad
D(\overline X_n)=\frac{\sigma^2}{n}.
\]

由切比雪夫不等式，

\[
P(|\overline X_n-\mu|\ge \varepsilon)
\le
\frac{\sigma^2}{n\varepsilon^2}.
\]

当 \(n\to\infty\) 时，右边趋于 \(0\)。

所以样本均值会越来越靠近期望。这就是大数定律的核心直觉之一。

---

### 4. 最小记忆

马尔可夫不等式控制非负随机变量：

\[
P(Z\ge a)
\le
\frac{E(Z)}{a}.
\]

切比雪夫不等式就是把马尔可夫不等式用到

\[
Z=(X-\mu)^2
\]

上面：

\[
P(|X-\mu|\ge \varepsilon)
\le
\frac{D(X)}{\varepsilon^2}.
\]

一句话：

\[
\boxed{\text{方差越小，随机变量越不容易远离均值。}}
\]

---

## 样本中心化变量之间的相关系数

设

\[
X_1,\dots,X_n
\]

独立同分布，且方差有限。记

\[
\mu=E(X_i),\qquad \sigma^2=\operatorname{Var}(X_i),
\]

其中假设 \(\sigma^2>0\)。样本均值为

\[
\widehat X=\overline X=\frac1n\sum_{k=1}^n X_k.
\]

目标是证明：当 \(i\ne j\) 时，

\[
\rho(X_i-\bar X,\,X_j-\bar X)=-\frac1{n-1}.
\]

### 1. 先算协方差

因为

\[
\operatorname{Cov}(X_i,X_j)=0 \quad (i\ne j),
\]

且

\[
\operatorname{Var}(\bar X)=\frac{\sigma^2}{n}.
\]

又有

\[
\operatorname{Cov}(X_i,\bar X)
=\operatorname{Cov}\left(X_i,\frac1n\sum_{k=1}^n X_k\right)
=\frac1n\operatorname{Var}(X_i)
=\frac{\sigma^2}{n}.
\]

同理，

\[
\operatorname{Cov}(X_j,\bar X)=\frac{\sigma^2}{n}.
\]

所以当 \(i\ne j\) 时，

\[
\begin{aligned}
\operatorname{Cov}(X_i-\bar X, X_j-\bar X)
&=\operatorname{Cov}(X_i,X_j)
-\operatorname{Cov}(X_i,\bar X)
-\operatorname{Cov}(\bar X,X_j)
+\operatorname{Var}(\bar X)\\
&=0-\frac{\sigma^2}{n}-\frac{\sigma^2}{n}+\frac{\sigma^2}{n}\\
&=-\frac{\sigma^2}{n}.
\end{aligned}
\]

### 2. 再算方差


\[
\begin{aligned}
\operatorname{Var}(X_i-\bar X)
&=\operatorname{Var}(X_i)+\operatorname{Var}(\bar X)-2\operatorname{Cov}(X_i,
\bar X)\\
&=\sigma^2+\frac{\sigma^2}{n}-2\frac{\sigma^2}{n}\\
&=\sigma^2\left(1-\frac1n\right)\\
&=\frac{n-1}{n}\sigma^2.
\end{aligned}
\]

同理，

\[
\operatorname{Var}(X_j-\bar X)=\frac{n-1}{n}\sigma^2.
\]

### 3. 代入相关系数公式

相关系数定义为

\[
\rho(Y,Z)=
\frac{\operatorname{Cov}(Y,Z)}
{\sqrt{\operatorname{Var}(Y)}\sqrt{\operatorname{Var}(Z)}}.
\]

令

\[
Y=X_i-\bar X,
\qquad
Z=X_j-\bar X.
\]

则

\[
\begin{aligned}
\rho(X_i-\bar X, X_j-\bar X)
&=
\frac{-\sigma^2/n}
{\sqrt{(n-1)\sigma^2/n}\sqrt{(n-1)\sigma^2/n}}\\
&=
\frac{-\sigma^2/n}{(n-1)\sigma^2/n}\\
&=-\frac1{n-1}.
\end{aligned}
\]

因此，

\[
\boxed{
ho(X_i-\bar X, X_j-\bar X)=-\frac1{n-1}\qquad (i\ne j).}
\]

### 4. 直观理解

中心化后的残差满足

\[
\sum_{k=1}^n (X_k-\bar X)=0.
\]

也就是说，这 \(n\) 个残差被一个线性约束绑住了。一个残差偏正时，其他残差整体上必须偏负来抵消它。因此不同残差之间会出现负相关。

而且这个负相关的大小刚好是

\[
-\frac1{n-1}.
\]

样本量越大，单个残差对其他残差的约束越弱，所以相关系数趋近于 \(0\)。

---

## 上面推导中用到的公式说明

这一节专门解释：

\[
D(X_i-\bar X)
\]

是怎么计算出来的，以及协方差展开时用了哪些公式。

### 1. 记号

这里

\[
D(Y)=\operatorname{Var}(Y)
\]

表示随机变量 \(Y\) 的方差。

样本均值是

\[
\bar X=\frac1n\sum_{k=1}^n X_k.
\]

假设

\[
E(X_i)=\mu,\qquad D(X_i)=\operatorname{Var}(X_i)=\sigma^2.
\]

因为 \(X_1,\dots,X_n\) 独立同分布，所以

\[
\operatorname{Cov}(X_i,X_j)=0\qquad (i\ne j).
\]

### 2. 用到的方差公式

最核心的公式是：

\[
\operatorname{Var}(A-B)
=
\operatorname{Var}(A)+\operatorname{Var}(B)-2\operatorname{Cov}(A,B).
\]

更一般地，

\[
\operatorname{Var}(aA+bB)
=
a^2\operatorname{Var}(A)+b^2\operatorname{Var}(B)
+2ab\operatorname{Cov}(A,B).
\]

令 \(a=1,b=-1\)，就得到

\[
\operatorname{Var}(A-B)
=
\operatorname{Var}(A)+\operatorname{Var}(B)-2\operatorname{Cov}(A,B).
\]

所以

\[
D(X_i-\bar X)
=
\operatorname{Var}(X_i-\bar X)
=
\operatorname{Var}(X_i)+\operatorname{Var}(\bar X)
-2\operatorname{Cov}(X_i,\bar X).
\]

下面分别算这三项。

### 3. 第一项：\(\operatorname{Var}(X_i)\)

由题设，

\[
\operatorname{Var}(X_i)=\sigma^2.
\]

### 4. 第二项：\(\operatorname{Var}(\bar X)\)

因为

\[
\bar X=\frac1n(X_1+\cdots+X_n),
\]

所以

\[
\operatorname{Var}(\bar X)
=
\operatorname{Var}\left(\frac1n\sum_{k=1}^n X_k\right).
\]

常数可以平方后提出来：

\[
\operatorname{Var}(cY)=c^2\operatorname{Var}(Y).
\]

因此

\[
\operatorname{Var}(\bar X)
=
\frac1{n^2}\operatorname{Var}\left(\sum_{k=1}^n X_k\right).
\]

又因为 \(X_1,\dots,X_n\) 相互独立，所以和的方差等于方差之和：

\[
\operatorname{Var}\left(\sum_{k=1}^n X_k\right)
=
\sum_{k=1}^n \operatorname{Var}(X_k).
\]

每个 \(X_k\) 的方差都是 \(\sigma^2\)，所以

\[
\sum_{k=1}^n \operatorname{Var}(X_k)
=n\sigma^2.
\]

因此

\[
\operatorname{Var}(\bar X)
=
\frac1{n^2}\cdot n\sigma^2
=
\frac{\sigma^2}{n}.
\]

### 5. 第三项：\(\operatorname{Cov}(X_i,\bar X)\)

先代入 \(\bar X\)：

\[
\operatorname{Cov}(X_i,\bar X)
=
\operatorname{Cov}\left(X_i,\frac1n\sum_{k=1}^n X_k\right).
\]

协方差对第二个位置是线性的：

\[
\operatorname{Cov}\left(A,\sum_{k=1}^n B_k\right)
=
\sum_{k=1}^n \operatorname{Cov}(A,B_k).
\]

常数可以提出来：

\[
\operatorname{Cov}(A,cB)=c\operatorname{Cov}(A,B).
\]

所以

\[
\operatorname{Cov}(X_i,\bar X)
=
\frac1n\sum_{k=1}^n \operatorname{Cov}(X_i,X_k).
\]

把求和拆开：

\[
\sum_{k=1}^n \operatorname{Cov}(X_i,X_k)
=
\operatorname{Cov}(X_i,X_i)
+
\sum_{k\ne i}\operatorname{Cov}(X_i,X_k).
\]

其中

\[
\operatorname{Cov}(X_i,X_i)=\operatorname{Var}(X_i)=\sigma^2.
\]

而当 \(k\ne i\) 时，由独立性，

\[
\operatorname{Cov}(X_i,X_k)=0.
\]

所以

\[
\sum_{k=1}^n \operatorname{Cov}(X_i,X_k)
=\sigma^2.
\]

因此

\[
\operatorname{Cov}(X_i,\bar X)=\frac{\sigma^2}{n}.
\]

### 6. 合并得到 \(D(X_i-\bar X)\)

现在代回：

\[
\operatorname{Var}(X_i-\bar X)
=
\operatorname{Var}(X_i)+\operatorname{Var}(\bar X)
-2\operatorname{Cov}(X_i,\bar X).
\]

所以

\[
\begin{aligned}
D(X_i-\bar X)
&=\sigma^2+\frac{\sigma^2}{n}
-2\cdot \frac{\sigma^2}{n}\\
&=\sigma^2-\frac{\sigma^2}{n}\\
&=\frac{n-1}{n}\sigma^2.
\end{aligned}
\]

因此

\[
\boxed{
D(X_i-\bar X)=\frac{n-1}{n}\sigma^2
}
\]

同理，

\[
D(X_j-\bar X)=\frac{n-1}{n}\sigma^2.
\]

### 7. 协方差展开用了什么公式

要算

\[
\operatorname{Cov}(X_i-\bar X, X_j-\bar X),
\]

用的是协方差的双线性：

\[
\operatorname{Cov}(A+B,C+D)
=
\operatorname{Cov}(A,C)
+
\operatorname{Cov}(A,D)
+
\operatorname{Cov}(B,C)
+
\operatorname{Cov}(B,D).
\]

如果有负号，负号可以提出来：

\[
\operatorname{Cov}(-A,B)=-\operatorname{Cov}(A,B),
\]

\[
\operatorname{Cov}(A,-B)=-\operatorname{Cov}(A,B),
\]

\[
\operatorname{Cov}(-A,-B)=\operatorname{Cov}(A,B).
\]

所以

\[
\begin{aligned}
\operatorname{Cov}(X_i-\bar X, X_j-\bar X)
&=
\operatorname{Cov}(X_i,X_j)
-\operatorname{Cov}(X_i,\bar X)\\
&\quad
-\operatorname{Cov}(\bar X,X_j)
+\operatorname{Cov}(\bar X,\bar X).
\end{aligned}
\]

又因为

\[
\operatorname{Cov}(\bar X,\bar X)=\operatorname{Var}(\bar X),
\]

所以

\[
\begin{aligned}
\operatorname{Cov}(X_i-\bar X, X_j-\bar X)
&=
\operatorname{Cov}(X_i,X_j)
-\operatorname{Cov}(X_i,\bar X)\\
&\quad
-\operatorname{Cov}(\bar X,X_j)
+\operatorname{Var}(\bar X).
\end{aligned}
\]

当 \(i\ne j\) 时：

\[
\operatorname{Cov}(X_i,X_j)=0,
\]

\[
\operatorname{Cov}(X_i,\bar X)=\frac{\sigma^2}{n},
\]

\[
\operatorname{Cov}(\bar X,X_j)=\frac{\sigma^2}{n},
\]

\[
\operatorname{Var}(\bar X)=\frac{\sigma^2}{n}.
\]

因此

\[
\begin{aligned}
\operatorname{Cov}(X_i-\bar X, X_j-\bar X)
&=
0-\frac{\sigma^2}{n}
-\frac{\sigma^2}{n}
+\frac{\sigma^2}{n}\\
&=
-\frac{\sigma^2}{n}.
\end{aligned}
\]

### 8. 最小记忆

这个题主要用四类公式：

1. 方差展开：

\[
\operatorname{Var}(A-B)
=
\operatorname{Var}(A)+\operatorname{Var}(B)-2\operatorname{Cov}(A,B).
\]

2. 协方差双线性：

\[
\operatorname{Cov}(A-B,C-D)
=
\operatorname{Cov}(A,C)-\operatorname{Cov}(A,D)
-\operatorname{Cov}(B,C)+\operatorname{Cov}(B,D).
\]

3. 独立推出协方差为零：

\[
A,B\text{ 独立}\quad\Longrightarrow\quad \operatorname{Cov}(A,B)=0.
\]

4. 自己和自己的协方差就是方差：

\[
\operatorname{Cov}(A,A)=\operatorname{Var}(A).
\]

本题的关键计算是：

\[
\operatorname{Cov}(X_i,\bar X)=\frac{\sigma^2}{n},
\qquad
\operatorname{Var}(\bar X)=\frac{\sigma^2}{n}.
\]

有了这两个量，后面的展开只是代入。

---

## JPG 图片中的概率统计题

### 题 1：正态总体，样本观测值为 \((-3,1,2)\)

设总体

\[
X\sim N(\mu,\sigma^2),
\]

其中 \(\mu\) 已知，\(\sigma\) 未知。样本为

\[
(X_1,X_2,X_3),
\]

观测值为

\[
(-3,1,2).
\]

#### （1）写出联合概率密度

单个 \(X_i\) 的密度为

\[
f(x_i;\sigma)
=
\frac{1}{\sqrt{2\pi}\sigma}
\exp\left\{
-\frac{(x_i-\mu)^2}{2\sigma^2}
\right\}.
\]

因为样本相互独立，所以联合密度等于三个密度相乘：

\[
f(x_1,x_2,x_3;\sigma)
=
\prod_{i=1}^3
\frac{1}{\sqrt{2\pi}\sigma}
\exp\left\{
-\frac{(x_i-\mu)^2}{2\sigma^2}
\right\}.
\]

整理得

\[
f(x_1,x_2,x_3;\sigma)
=
\frac{1}{(2\pi)^{3/2}\sigma^3}
\exp\left\{
-\frac{1}{2\sigma^2}
\sum_{i=1}^3 (x_i-\mu)^2
\right\}.
\]

代入观测值 \((-3,1,2)\)，得到似然函数形式：

\[
L(\sigma)
=
\frac{1}{(2\pi)^{3/2}\sigma^3}
\exp\left\{
-\frac{(-3-\mu)^2+(1-\mu)^2+(2-\mu)^2}{2\sigma^2}
\right\}.
\]

#### （2）求样本的经验分布函数

样本观测值排序为

\[
-3<1<2.
\]

经验分布函数定义为

\[
F_3(x)=\frac{1}{3}\#\{X_i\le x\}.
\]

所以

\[
F_3(x)=
\begin{cases}
0, & x<-3,\\
\frac13, & -3\le x<1,\\
\frac23, & 1\le x<2,\\
1, & x\ge 2.
\end{cases}
\]

#### （3）哪些是统计量？

统计量必须只依赖样本，不能含未知参数。

这里 \(\mu\) 已知，\(\sigma\) 未知。

1. \(X_1+X_2+X_3\) 是统计量。

因为它只依赖样本。

2. \(X_1-\mu\) 是统计量。

因为 \(\mu\) 是已知常数。

3. \(\displaystyle \sum_{i=1}^3 \frac{X_i}{\sigma}\) 不是统计量。

因为它含有未知参数 \(\sigma\)。

4. \(\min\{X_1,X_2,X_3\}\) 是统计量。

因为它只依赖样本。

### 题 2：最大值和最小值概率

设

\[
X_1,\dots,X_5
\]

是来自总体

\[
X\sim N(12,2^2)
\]

的样本。

令标准正态分布函数为 \(\Phi(x)\)。

#### （1）求 \(P(\max(X_1,\dots,X_5)>15)\)

先求反事件：

\[
\max(X_1,\dots,X_5)\le 15
\]

等价于

\[
X_1\le 15,\dots,X_5\le 15.
\]

所以

\[
P(\max(X_1,\dots,X_5)\le 15)
=
\left[P(X\le 15)\right]^5.
\]

标准化：

\[
P(X\le 15)
=
\Phi\left(\frac{15-12}{2}\right)
=
\Phi(1.5).
\]

因此

\[
P(\max(X_1,\dots,X_5)>15)
=
1-\Phi(1.5)^5.
\]

数值约为

\[
1-\Phi(1.5)^5\approx 0.2923.
\]

#### （2）求 \(P(\min(X_1,\dots,X_5)<10)\)

反事件为

\[
\min(X_1,\dots,X_5)\ge 10,
\]

即每个样本都不小于 \(10\)。

因此

\[
P(\min(X_1,\dots,X_5)\ge 10)
=
\left[P(X\ge 10)\right]^5.
\]

标准化：

\[
P(X\ge 10)
=
P\left(Z\ge \frac{10-12}{2}\right)
=
P(Z\ge -1)
=
\Phi(1).
\]

所以

\[
P(\min(X_1,\dots,X_5)<10)
=
1-\Phi(1)^5.
\]

数值约为

\[
1-\Phi(1)^5\approx 0.5784.
\]

#### （3）求 \(P(\max(X_1,\dots,X_5)<15,\min(X_1,\dots,X_5)<10)\)

事件

\[
\max(X_1,\dots,X_5)<15
\]

表示所有样本都小于 \(15\)。

事件

\[
\min(X_1,\dots,X_5)<10
\]

表示至少有一个样本小于 \(10\)。

所以目标事件是：

所有样本都小于 \(15\)，并且至少一个样本小于 \(10\)。

这等于：

所有样本都小于 \(15\)，减去所有样本都在 \([10,15)\) 内。

因此

\[
P(\max<15,\min<10)
=
P(X_1<15,\dots,X_5<15)
-
P(10\le X_1<15,\dots,10\le X_5<15).
\]

第一项：

\[
P(X_1<15,\dots,X_5<15)
=
\Phi(1.5)^5.
\]

第二项：

\[
P(10\le X<15)
=
\Phi(1.5)-\Phi(-1).
\]

所以

\[
P(10\le X_1<15,\dots,10\le X_5<15)
=
\left[\Phi(1.5)-\Phi(-1)\right]^5.
\]

因此

\[
P(\max<15,\min<10)
=
\Phi(1.5)^5-\left[\Phi(1.5)-\Phi(-1)\right]^5.
\]

数值约为

\[
0.4290.
\]

### 题 3：伯努利总体的样本均值和样本方差

设

\[
(X_1,X_2,\dots,X_n)
\]

是取自总体

\[
X\sim B(1,p)
\]

的样本。

也就是

\[
X_i\sim B(1,p).
\]

因此

\[
E(X_i)=p,
\qquad
D(X_i)=p(1-p).
\]

#### （1）计算 \(E\bar X\)

\[
\bar X=\frac1n\sum_{i=1}^n X_i.
\]

所以

\[
E\bar X
=
E\left(\frac1n\sum_{i=1}^n X_i\right)
=
\frac1n\sum_{i=1}^n E(X_i)
=
\frac1n\cdot np
=p.
\]

#### （2）计算 \(D\bar X\)

因为样本独立，

\[
D\bar X
=
D\left(\frac1n\sum_{i=1}^n X_i\right)
=
\frac1{n^2}\sum_{i=1}^n D(X_i).
\]

所以

\[
D\bar X
=
\frac1{n^2}\cdot np(1-p)
=
\frac{p(1-p)}{n}.
\]

#### （3）计算 \(ES^2\)

如果这里的样本方差定义为

\[
S^2=\frac1{n-1}\sum_{i=1}^n (X_i-\bar X)^2,
\]

那么它是总体方差的无偏估计量。

因此

\[
E(S^2)=D(X)=p(1-p).
\]

所以

\[
\boxed{E(S^2)=p(1-p)}.
\]

#### （4）求 \(P(n\bar X=k)\)

因为

\[
n\bar X=\sum_{i=1}^n X_i.
\]

而每个 \(X_i\) 都是伯努利变量，所以

\[
\sum_{i=1}^n X_i\sim B(n,p).
\]

因此

\[
P(n\bar X=k)
=
\binom{n}{k}p^k(1-p)^{n-k},
\qquad k=0,1,\dots,n.
\]

### 题 4：两个正态样本均值之差

设总体

\[
X\sim N(20,3).
\]

从 \(X\) 中分别抽取容量为 \(10\) 和 \(15\) 的两个相互独立的样本。

记两个样本均值为

\[
\bar X_1,\qquad \bar X_2.
\]

求

\[
P(|\bar X_1-\bar X_2|>0.3).
\]

按照本套题常用记号 \(N(\mu,\sigma^2)\)，这里把第二个参数 \(3\) 理解为方差。

于是

\[
\bar X_1\sim N\left(20,\frac{3}{10}\right),
\]

\[
\bar X_2\sim N\left(20,\frac{3}{15}\right).
\]

因为两个样本相互独立，所以

\[
\bar X_1-\bar X_2
\sim
N\left(0,\frac{3}{10}+\frac{3}{15}\right).
\]

计算方差：

\[
\frac{3}{10}+\frac{3}{15}
=
\frac{3}{10}+\frac{1}{5}
=
\frac{3}{10}+\frac{2}{10}
=
\frac12.
\]

所以

\[
\bar X_1-\bar X_2\sim N\left(0,\frac12\right).
\]

标准化：

\[
P(|\bar X_1-\bar X_2|>0.3)
=
P\left(
\left|Z\right|>
\frac{0.3}{\sqrt{1/2}}
\right).
\]

其中

\[
\frac{0.3}{\sqrt{1/2}}
\approx 0.4243.
\]

因此

\[
P(|\bar X_1-\bar X_2|>0.3)
=
2[1-\Phi(0.4243)].
\]

数值约为

\[
0.6714.
\]

如果教材把 \(N(20,3)\) 的第二个参数理解为标准差而不是方差，则应改用总体方差 \(9\)，答案会变为

\[
2\left[
1-\Phi\left(\frac{0.3}{\sqrt{9/10+9/15}}\right)
\right]
\approx 0.8065.
\]

但按本页前面 \(N(12,2^2)\) 的写法，更自然的理解是 \(N(20,3)\) 中的 \(3\) 是方差。

### 题 5：停车场车位设计

题意：

某地区日平均停车数量为

\[
n=1600.
\]

估计有

\[
\frac34
\]

的车会停到新建停车场。

设进入新停车场的车辆数为

\[
Y.
\]

则

\[
Y\sim B\left(1600,\frac34\right).
\]

因此

\[
E(Y)=1600\cdot \frac34=1200.
\]

方差为

\[
D(Y)=1600\cdot \frac34\cdot \frac14=300.
\]

标准差为

\[
\sqrt{300}\approx 17.32.
\]

设停车场设计车位数为 \(m\)。

空车位数至少为 \(200\) 的事件是

\[
m-Y\ge 200.
\]

也就是

\[
Y\le m-200.
\]

题目要求

\[
P(m-Y\ge 200)\le 0.1.
\]

等价于

\[
P(Y\le m-200)\le 0.1.
\]

用正态近似：

\[
Y\approx N(1200,300).
\]

查标准正态分布表：

\[
z_{0.1}\approx -1.2816.
\]

因此 \(Y\) 的 \(10\%\) 分位数约为

\[
1200-1.2816\sqrt{300}
\approx
1177.8.
\]

带连续性修正，要求

\[
m-200+0.5\le 1177.8.
\]

所以

\[
m\le 1377.3.
\]

车位数取整数，最大可取

\[
\boxed{m=1377}.
\]

也就是说，若希望“空车位达到 \(200\) 或以上”的概率不超过 \(0.1\)，车位数不宜超过约 \(1377\) 个。

用二项分布精确检查：

\[
P(Y\le 1177)\approx 0.0975\le 0.1,
\]

而

\[
P(Y\le 1178)\approx 0.1077>0.1.
\]

所以精确判断下最大设计车位数也是

\[
\boxed{1377}.
\]

---

## 方差如何组合运算

方差的组合运算和期望不完全一样。

期望是线性的：

\[
E(aX+bY)=aE(X)+bE(Y).
\]

但方差不是线性的。

### 1. 常数倍的方差

如果 \(a\) 是常数，那么

\[
D(aX)=a^2D(X).
\]

注意是平方。

例如：

\[
D(3X)=9D(X).
\]

如果只是加一个常数，不改变方差：

\[
D(X+c)=D(X).
\]

因为整体平移不会改变离散程度。

所以

\[
D(aX+b)=a^2D(X).
\]

### 2. 两个随机变量相加的方差

一般情况下：

\[
D(X+Y)=D(X)+D(Y)+2\operatorname{Cov}(X,Y).
\]

其中

\[
\operatorname{Cov}(X,Y)
\]

是协方差，用来描述 \(X,Y\) 是否一起变动。

如果 \(X,Y\) 独立，那么

\[
\operatorname{Cov}(X,Y)=0.
\]

于是

\[
D(X+Y)=D(X)+D(Y).
\]

所以“方差可加”必须有条件，常见条件是独立。

### 3. 两个随机变量相减的方差

一般情况下：

\[
D(X-Y)=D(X)+D(Y)-2\operatorname{Cov}(X,Y).
\]

如果 \(X,Y\) 独立，那么协方差为 \(0\)，所以

\[
D(X-Y)=D(X)+D(Y).
\]

注意：独立时，不管加还是减，方差都是相加。

这是因为方差看的是波动大小，减号不会让波动抵消。

### 4. 一般线性组合

对于

\[
aX+bY,
\]

有

\[
D(aX+bY)
=
a^2D(X)+b^2D(Y)+2ab\operatorname{Cov}(X,Y).
\]

如果 \(X,Y\) 独立，则

\[
D(aX+bY)
=
a^2D(X)+b^2D(Y).
\]

### 5. 多个随机变量的线性组合

对

\[
\sum_{i=1}^n a_iX_i,
\]

一般公式是

\[
D\left(\sum_{i=1}^n a_iX_i\right)
=
\sum_{i=1}^n a_i^2D(X_i)
+
2\sum_{1\le i<j\le n}a_ia_j\operatorname{Cov}(X_i,X_j).
\]

如果 \(X_1,\dots,X_n\) 相互独立，那么所有交叉协方差都为 \(0\)，于是

\[
D\left(\sum_{i=1}^n a_iX_i\right)
=
\sum_{i=1}^n a_i^2D(X_i).
\]

### 6. 样本均值的方差

设

\[
X_1,\dots,X_n
\]

独立同分布，且

\[
D(X_i)=\sigma^2.
\]

样本均值为

\[
\bar X=\frac1n\sum_{i=1}^n X_i.
\]

则

\[
D(\bar X)
=
D\left(\frac1n\sum_{i=1}^n X_i\right).
\]

常数 \(\frac1n\) 提出来要平方：

\[
D(\bar X)
=
\frac1{n^2}D\left(\sum_{i=1}^n X_i\right).
\]

由于独立，和的方差等于方差之和：

\[
D\left(\sum_{i=1}^n X_i\right)
=
\sum_{i=1}^n D(X_i)
=
n\sigma^2.
\]

所以

\[
D(\bar X)
=
\frac1{n^2}\cdot n\sigma^2
=
\frac{\sigma^2}{n}.
\]

这就是为什么样本均值的方差会随 \(n\) 增大而减小。

### 7. 两个独立样本均值之差的方差

如果

\[
\bar X_1
\]

来自容量为 \(n_1\) 的样本，

\[
\bar X_2
\]

来自容量为 \(n_2\) 的样本，并且两组样本独立。

若总体方差为 \(\sigma^2\)，则

\[
D(\bar X_1)=\frac{\sigma^2}{n_1},
\qquad
D(\bar X_2)=\frac{\sigma^2}{n_2}.
\]

由于两组样本独立，

\[
D(\bar X_1-\bar X_2)
=
D(\bar X_1)+D(\bar X_2).
\]

所以

\[
D(\bar X_1-\bar X_2)
=
\frac{\sigma^2}{n_1}+\frac{\sigma^2}{n_2}.
\]

例如上一题里，如果

\[
X\sim N(20,3),
\]

且第二个参数 \(3\) 表示方差，那么

\[
D(\bar X_1-\bar X_2)
=
\frac{3}{10}+\frac{3}{15}
=
\frac12.
\]

### 8. 最小记忆

方差运算最常用的几条：

\[
D(aX+b)=a^2D(X).
\]

\[
D(X+Y)=D(X)+D(Y)+2\operatorname{Cov}(X,Y).
\]

\[
D(X-Y)=D(X)+D(Y)-2\operatorname{Cov}(X,Y).
\]

如果 \(X,Y\) 独立：

\[
D(X+Y)=D(X-Y)=D(X)+D(Y).
\]

样本均值：

\[
D(\bar X)=\frac{\sigma^2}{n}.
\]

两个独立样本均值之差：

\[
D(\bar X_1-\bar X_2)
=
\frac{\sigma^2}{n_1}+\frac{\sigma^2}{n_2}.
\]

---

## 第 4 题补充：为什么不是 \(D(X-Y)=6\)

这里容易混淆两个对象：

1. 单个观测值之差：

\[
X-Y.
\]

2. 两个样本均值之差：

\[
\bar X-\bar Y.
\]

题目说的是：

从同一个正态总体中分别抽取容量为 \(10\) 和 \(15\) 的两个相互独立的样本，求两样本均值之差的绝对值大于 \(0.3\) 的概率。

所以要求的是

\[
P(|\bar X-\bar Y|>0.3),
\]

不是

\[
P(|X-Y|>0.3).
\]

### 1. 如果考虑单个随机变量之差 \(X-Y\)

若

\[
X\sim N(20,3),\qquad Y\sim N(20,3),
\]

并且 \(X,Y\) 独立。

则

\[
E(X-Y)=E(X)-E(Y)=20-20=0.
\]

又因为独立，所以

\[
D(X-Y)=D(X)+D(Y)=3+3=6.
\]

因此

\[
X-Y\sim N(0,6).
\]

这个结论是对的，但它对应的是“两个单个观测值之差”。

### 2. 题目真正要的是样本均值之差

第一组样本容量为 \(10\)，所以

\[
D(\bar X)=\frac{3}{10}.
\]

第二组样本容量为 \(15\)，所以

\[
D(\bar Y)=\frac{3}{15}.
\]

两组样本独立，因此两个样本均值也独立。

所以

\[
D(\bar X-\bar Y)
=
D(\bar X)+D(\bar Y).
\]

代入：

\[
D(\bar X-\bar Y)
=
\frac{3}{10}+\frac{3}{15}.
\]

通分：

\[
\frac{3}{10}+\frac{3}{15}
=
\frac{9}{30}+\frac{6}{30}
=
\frac{15}{30}
=
\frac12.
\]

因此

\[
\bar X-\bar Y\sim N\left(0,\frac12\right).
\]

### 3. 最关键区别

如果是单个观测值：

\[
D(X-Y)=3+3=6.
\]

如果是两个样本均值：

\[
D(\bar X-\bar Y)=\frac{3}{10}+\frac{3}{15}=\frac12.
\]

样本均值的方差会除以样本容量。

所以本题不能直接用 \(D(X-Y)=6\)，因为题目问的是两组样本均值之差。

### 4. 为什么不是 \(2\Phi(-0.3)\)

如果随机变量本身是标准正态分布：

\[
Z\sim N(0,1),
\]

那么

\[
P(|Z|>0.3)=2\Phi(-0.3).
\]

但是本题中

\[
\bar X-\bar Y\sim N\left(0,\frac12\right),
\]

它不是标准正态分布。

需要先标准化：

\[
Z=
\frac{\bar X-\bar Y}{\sqrt{1/2}}
\sim N(0,1).
\]

因此

\[
P(|\bar X-\bar Y|>0.3)
=
P\left(
\left|
\frac{\bar X-\bar Y}{\sqrt{1/2}}
\right|
>
\frac{0.3}{\sqrt{1/2}}
\right).
\]

所以

\[
P(|\bar X-\bar Y|>0.3)
=
2\Phi\left(
-\frac{0.3}{\sqrt{1/2}}
\right).
\]

而不是

\[
2\Phi(-0.3).
\]

因为

\[
\frac{0.3}{\sqrt{1/2}}\approx 0.4243.
\]

所以答案是

\[
2\Phi(-0.4243).
\]

只有当被考察的随机变量方差正好是 \(1\) 时，才可以直接写成 \(2\Phi(-0.3)\)。

### 5. 题目里的 \(10\) 和 \(15\) 有什么用

这两个数是两个样本的容量。

第一组样本容量是 \(10\)，第二组样本容量是 \(15\)。

它们的作用是决定样本均值的方差。

如果单个观测值的方差是

\[
\sigma^2=3,
\]

那么容量为 \(n\) 的样本均值的方差是

\[
D(\bar X)=\frac{\sigma^2}{n}.
\]

所以第一组样本均值的方差是

\[
D(\bar X)=\frac{3}{10}.
\]

第二组样本均值的方差是

\[
D(\bar Y)=\frac{3}{15}.
\]

因此两样本均值之差的方差是

\[
D(\bar X-\bar Y)
=
\frac{3}{10}+\frac{3}{15}.
\]

这就是 \(10\) 和 \(15\) 的作用。

如果题目问的是两个单个观测值之差 \(X-Y\)，那就用不到 \(10\) 和 \(15\)，方差就是

\[
D(X-Y)=3+3=6.
\]

但题目问的是两个样本均值之差，所以必须用样本容量 \(10\) 和 \(15\)。

一句话：

\[
\boxed{
10\text{ 和 }15\text{ 用来把总体方差 }3
\text{ 缩小为样本均值方差 }
\frac{3}{10}\text{ 和 }\frac{3}{15}.
}
\]

---

## 统计量是什么，有什么用

### 1. 统计量的定义

设

\[
X_1,X_2,\dots,X_n
\]

是样本。

如果一个量可以写成样本的函数：

\[
T=T(X_1,X_2,\dots,X_n),
\]

并且这个表达式中不含未知参数，那么 \(T\) 就叫统计量。

一句话：

\[
\boxed{
\text{统计量就是只由样本和已知常数组成的随机变量。}
}
\]

### 2. 已知量能不能出现在统计量里

可以。

如果 \(c\) 是已知常数，那么

\[
X_1+c
\]

是统计量。

如果 \(\mu\) 已知，那么

\[
X_1-\mu
\]

也是统计量。

因为 \(\mu\) 此时只是一个已知常数。

### 3. 未知参数不能出现在统计量里

如果 \(\theta\) 是未知参数，那么

\[
X_1-\theta
\]

不是统计量。

因为它不只依赖样本，还依赖一个未知参数。

例如题目中：

\[
X\sim N(\mu,\sigma^2),
\]

其中 \(\mu\) 已知，\(\sigma\) 未知。

那么

\[
X_1-\mu
\]

是统计量。

但是

\[
\frac{X_1}{\sigma}
\]

不是统计量。

因为 \(\sigma\) 未知。

### 4. 统计量本身还是随机变量

统计量是样本的函数。

而样本

\[
X_1,\dots,X_n
\]

本身是随机变量，所以统计量也是随机变量。

例如：

\[
\bar X=\frac1n\sum_{i=1}^n X_i
\]

是统计量。

在抽样之前，\(\bar X\) 是随机变量。

抽样之后，得到具体数据，\(\bar X\) 就变成一个具体数值。

### 5. 常见统计量

样本均值：

\[
\bar X=\frac1n\sum_{i=1}^n X_i.
\]

样本方差：

\[
S^2=\frac1{n-1}\sum_{i=1}^n (X_i-\bar X)^2.
\]

样本最大值：

\[
X_{(n)}=\max\{X_1,\dots,X_n\}.
\]

样本最小值：

\[
X_{(1)}=\min\{X_1,\dots,X_n\}.
\]

样本和：

\[
\sum_{i=1}^n X_i.
\]

这些都只依赖样本，所以都是统计量。

### 6. 统计量有什么应用

统计量的作用是：用样本信息去推断总体。

#### 应用一：估计未知参数

如果总体均值 \(\mu\) 未知，可以用样本均值估计它：

\[
\bar X \approx \mu.
\]

如果总体方差 \(\sigma^2\) 未知，可以用样本方差估计它：

\[
S^2 \approx \sigma^2.
\]

这里 \(\bar X\) 和 \(S^2\) 都是统计量。

#### 应用二：构造置信区间

例如要估计总体均值 \(\mu\)，常用

\[
\bar X
\]

加上误差范围构造置信区间。

置信区间的核心也是统计量。

#### 应用三：假设检验

比如检验总体均值是不是某个数：

\[
H_0:\mu=\mu_0.
\]

会构造检验统计量，例如

\[
Z=\frac{\bar X-\mu_0}{\sigma/\sqrt n}.
\]

然后看这个统计量落在不落在拒绝域里。

#### 应用四：压缩样本信息

原始样本可能有很多个数：

\[
X_1,\dots,X_n.
\]

统计量可以把样本压缩成更有用的信息。

例如：

\[
\bar X
\]

代表样本的中心位置；

\[
S^2
\]

代表样本的离散程度；

\[
\max X_i,\min X_i
\]

代表样本范围。

### 7. 最小记忆

判断一个量是不是统计量，只问两件事：

1. 它是不是由样本 \(X_1,\dots,X_n\) 算出来的？
2. 它里面有没有未知参数？

如果只由样本和已知常数构成，并且不含未知参数，就是统计量。

如果含未知参数，就不是统计量。

所以：

\[
\boxed{
\text{统计量 = 样本的函数，不能含未知参数。}
}
\]

---

## 这些题用到的核心技巧：\(E\)、\(D\)、\(\operatorname{Cov}\)、大数定律

这几道题其实都在反复用同一套工具：

1. 期望 \(E\) 的线性性；
2. 方差 \(D\) 的组合公式；
3. 协方差 \(\operatorname{Cov}\) 判断是否有相关；
4. 独立时协方差为 \(0\)；
5. 样本均值的方差会除以样本容量；
6. 标准化，把正态变量变成标准正态；
7. 用反事件处理最大值和最小值；
8. 用二项分布和正态近似处理计数问题。

### 1. 期望的技巧

期望最简单，因为期望是线性的。

无论随机变量是否独立，都有：

\[
E(aX+bY)=aE(X)+bE(Y).
\]

更一般地，

\[
E\left(\sum_{i=1}^n a_iX_i\right)
=
\sum_{i=1}^n a_iE(X_i).
\]

所以如果

\[
\bar X=\frac1n\sum_{i=1}^n X_i,
\]

并且

\[
E(X_i)=\mu,
\]

则

\[
E(\bar X)
=
\frac1n\sum_{i=1}^n E(X_i)
=
\frac1n\cdot n\mu
=
\mu.
\]

这说明样本均值的期望等于总体均值。

### 2. 方差的技巧

方差不是线性的。

最重要的公式是：

\[
D(aX+bY)
=
a^2D(X)+b^2D(Y)+2ab\operatorname{Cov}(X,Y).
\]

如果 \(X,Y\) 独立，那么

\[
\operatorname{Cov}(X,Y)=0.
\]

于是

\[
D(aX+bY)=a^2D(X)+b^2D(Y).
\]

尤其：

\[
D(X+Y)=D(X)+D(Y),
\]

\[
D(X-Y)=D(X)+D(Y),
\]

前提是 \(X,Y\) 独立。

注意：独立时，减法的方差也是相加。

### 3. 协方差的技巧

协方差衡量两个随机变量一起变化的程度。

定义可以写成：

\[
\operatorname{Cov}(X,Y)
=
E[(X-EX)(Y-EY)].
\]

也常用等价公式：

\[
\operatorname{Cov}(X,Y)
=
E(XY)-E(X)E(Y).
\]

如果 \(X,Y\) 独立，那么

\[
E(XY)=E(X)E(Y),
\]

所以

\[
\operatorname{Cov}(X,Y)=0.
\]

但反过来不一定成立。

协方差为 \(0\) 不一定推出独立。

### 4. 样本均值的方差

这是这几题反复用到的技巧。

设

\[
X_1,\dots,X_n
\]

独立同分布，且

\[
E(X_i)=\mu,\qquad D(X_i)=\sigma^2.
\]

样本均值：

\[
\bar X=\frac1n\sum_{i=1}^n X_i.
\]

则

\[
D(\bar X)
=
D\left(\frac1n\sum_{i=1}^n X_i\right).
\]

常数 \(\frac1n\) 提出来要平方：

\[
D(\bar X)
=
\frac1{n^2}D\left(\sum_{i=1}^n X_i\right).
\]

由于独立：

\[
D\left(\sum_{i=1}^n X_i\right)
=
\sum_{i=1}^n D(X_i)
=
n\sigma^2.
\]

所以

\[
D(\bar X)
=
\frac1{n^2}\cdot n\sigma^2
=
\frac{\sigma^2}{n}.
\]

这就是：

\[
\boxed{
D(\bar X)=\frac{\sigma^2}{n}
}
\]

样本量越大，样本均值的波动越小。

### 5. 两个样本均值之差

如果两组样本独立，容量分别是 \(n_1,n_2\)，总体方差是 \(\sigma^2\)。

则

\[
D(\bar X)=\frac{\sigma^2}{n_1},
\qquad
D(\bar Y)=\frac{\sigma^2}{n_2}.
\]

因为两组样本独立，

\[
D(\bar X-\bar Y)
=
D(\bar X)+D(\bar Y).
\]

所以

\[
\boxed{
D(\bar X-\bar Y)
=
\frac{\sigma^2}{n_1}+\frac{\sigma^2}{n_2}
}
\]

这就是前面容量 \(10,15\) 的作用。

### 6. 正态题的技巧：标准化

如果

\[
X\sim N(\mu,\sigma^2),
\]

那么

\[
Z=\frac{X-\mu}{\sigma}\sim N(0,1).
\]

所以求正态概率时，核心动作是：

\[
\text{原变量}\quad\longrightarrow\quad\text{标准正态变量}.
\]

例如

\[
X\sim N(12,2^2),
\]

求

\[
P(X<15).
\]

标准化：

\[
P(X<15)
=
P\left(
\frac{X-12}{2}<\frac{15-12}{2}
\right)
=
\Phi(1.5).
\]

### 7. 最大值和最小值的技巧：用反事件

如果 \(X_1,\dots,X_n\) 独立同分布。

最大值：

\[
\max(X_1,\dots,X_n)\le a
\]

等价于所有样本都不超过 \(a\)：

\[
X_1\le a,\dots,X_n\le a.
\]

所以

\[
P(\max X_i\le a)
=
[P(X\le a)]^n.
\]

因此

\[
P(\max X_i>a)
=
1-[P(X\le a)]^n.
\]

最小值：

\[
\min(X_1,\dots,X_n)\ge a
\]

等价于所有样本都不小于 \(a\)：

\[
X_1\ge a,\dots,X_n\ge a.
\]

所以

\[
P(\min X_i\ge a)
=
[P(X\ge a)]^n.
\]

因此

\[
P(\min X_i<a)
=
1-[P(X\ge a)]^n.
\]

### 8. 二项分布题的技巧

如果一次试验成功概率是 \(p\)，独立重复 \(n\) 次，成功次数为 \(Y\)，则

\[
Y\sim B(n,p).
\]

于是

\[
P(Y=k)=\binom nk p^k(1-p)^{n-k}.
\]

期望和方差：

\[
E(Y)=np,
\qquad
D(Y)=np(1-p).
\]

当 \(n\) 很大时，可以用正态近似：

\[
Y\approx N(np,np(1-p)).
\]

停车场题就是：

\[
Y\sim B\left(1600,\frac34\right),
\]

然后用

\[
Y\approx N(1200,300).
\]

### 9. 大数定律怎么证明

这里先证明弱大数定律。

设

\[
X_1,\dots,X_n
\]

独立同分布，且

\[
E(X_i)=\mu,\qquad D(X_i)=\sigma^2<\infty.
\]

样本均值为

\[
\bar X_n=\frac1n\sum_{i=1}^n X_i.
\]

我们要证明：

\[
\bar X_n \xrightarrow{P} \mu.
\]

也就是对任意 \(\varepsilon>0\)，有

\[
P(|\bar X_n-\mu|\ge \varepsilon)\to 0.
\]

先算期望：

\[
E(\bar X_n)=\mu.
\]

再算方差：

\[
D(\bar X_n)=\frac{\sigma^2}{n}.
\]

用切比雪夫不等式：

\[
P(|Y-EY|\ge \varepsilon)
\le
\frac{D(Y)}{\varepsilon^2}.
\]

令

\[
Y=\bar X_n.
\]

则

\[
P(|\bar X_n-E\bar X_n|\ge \varepsilon)
\le
\frac{D(\bar X_n)}{\varepsilon^2}.
\]

因为

\[
E\bar X_n=\mu,
\qquad
D(\bar X_n)=\frac{\sigma^2}{n},
\]

所以

\[
P(|\bar X_n-\mu|\ge \varepsilon)
\le
\frac{\sigma^2}{n\varepsilon^2}.
\]

当

\[
n\to\infty
\]

时，

\[
\frac{\sigma^2}{n\varepsilon^2}\to 0.
\]

因此

\[
P(|\bar X_n-\mu|\ge \varepsilon)\to 0.
\]

这就证明了

\[
\boxed{
\bar X_n \xrightarrow{P} \mu
}
\]

这叫弱大数定律。

### 10. 只要有 \(\mu,\sigma\) 就能用切比雪夫证明吗？

要小心。

不是“写了 \(\mu,\sigma\)”就一定可以。

用切比雪夫证明弱大数定律，需要这些条件：

1. 每个 \(X_i\) 有相同的期望：

\[
E(X_i)=\mu.
\]

2. 方差有限：

\[
D(X_i)=\sigma^2<\infty.
\]

3. 样本之间独立，或者至少两两不相关。

因为证明中最关键一步是：

\[
D(\bar X_n)=\frac{\sigma^2}{n}.
\]

这个公式依赖独立性或不相关性。

如果随机变量之间高度相关，那么样本均值的方差不一定会变小。

### 11. 如果方差不存在怎么办

切比雪夫不等式需要方差。

如果 \(D(X_i)\) 不存在，或者方差无限大，就不能直接用这个证明。

有些更强的大数定律只要求期望存在，不一定要求方差有限。

但那需要更高级的证明方法，不是单靠切比雪夫这一步。

所以在初等概率论中，常见版本是：

\[
X_1,\dots,X_n\text{ 独立同分布，且 }E(X_i)=\mu,\ D(X_i)=\sigma^2<\infty.
\]

则

\[
\bar X_n\xrightarrow{P}\mu.
\]

这就是可以用切比雪夫直接证明的版本。

### 12. 最小记忆

这些题的核心套路：

\[
E\text{：直接线性拆开。}
\]

\[
D\text{：常数平方，独立时方差相加。}
\]

\[
\operatorname{Cov}\text{：处理不独立或中心化变量。}
\]

\[
\bar X\text{：方差变成 }\frac{\sigma^2}{n}.
\]

\[
\text{正态概率：先标准化。}
\]

\[
\max,\min\text{：用反事件和独立性。}
\]

\[
\text{大数定律：用切比雪夫证明 }\bar X_n\to\mu\text{ 的概率收敛。}
\]

---

## 概率论核心符号：随机变量、分布、期望、方差、协方差

你的理解方向是对的：

概率论里面很多量，本质上都是围绕随机变量 \(X\) 和期望算子 \(E\) 构造出来的。

### 1. 随机变量 \(X\) 是什么

随机变量 \(X\) 不是一个普通未知数。

它表示一个带有概率规律的量。

严格地说，随机变量是从样本空间到实数的函数。

但在计算中，可以把它理解为：

\[
X=\text{一个会随机取值的量，并且有自己的分布。}
\]

这个分布可以用不同方式描述：

1. 分布函数：

\[
F_X(x)=P(X\le x).
\]

2. 离散型概率：

\[
P(X=x_i)=p_i.
\]

3. 连续型密度：

\[
f_X(x).
\]

所以说 \(X\) 包含的信息不是一定是“概率密度函数”，因为离散型随机变量没有密度。

更准确地说：

\[
\boxed{
X\text{ 的核心信息是它的概率分布。}
}
\]

密度函数只是描述分布的一种方式。

### 2. 期望 \(E\) 是什么

期望 \(E\) 可以理解为“按概率加权平均”。

离散型：

\[
E(X)=\sum_i x_iP(X=x_i).
\]

连续型：

\[
E(X)=\int_{-\infty}^{+\infty}x f_X(x)\,dx.
\]

如果是 \(g(X)\)，那么

离散型：

\[
E[g(X)]=\sum_i g(x_i)P(X=x_i).
\]

连续型：

\[
E[g(X)]
=
\int_{-\infty}^{+\infty}g(x)f_X(x)\,dx.
\]

所以更一般地：

\[
\boxed{
E[g(X)]\text{ 就是对 }X\text{ 的函数按概率加权平均。}
}
\]

### 3. \(E\) 是线性算子

期望最重要的代数性质是线性性：

\[
E(aX+bY)=aE(X)+bE(Y).
\]

更一般：

\[
E\left(\sum_{i=1}^n a_iX_i\right)
=
\sum_{i=1}^n a_iE(X_i).
\]

这里 \(a_i\) 必须是常数。

也就是说，常数可以提到 \(E\) 外面，加法可以拆开。

例如：

\[
E(3X-2Y+5)
=
3E(X)-2E(Y)+5.
\]

### 4. 什么不能随便提到外面

常数可以提出来，但随机变量不能随便提出来。

例如一般不能写：

\[
E(XY)=XE(Y).
\]

这是错的，因为 \(X\) 本身也是随机的。

一般也不能写：

\[
E(XY)=E(X)E(Y).
\]

只有在 \(X,Y\) 独立时，才有：

\[
E(XY)=E(X)E(Y).
\]

所以：

\[
\boxed{
E\text{ 可以线性拆和提常数，但不能随便拆乘法。}
}
\]

### 5. 矩是什么

矩就是用期望描述随机变量的不同层次信息。

一阶原点矩：

\[
E(X).
\]

二阶原点矩：

\[
E(X^2).
\]

\(n\) 阶原点矩：

\[
E(X^n).
\]

中心矩是围绕均值展开：

\[
E[(X-\mu)^n].
\]

其中

\[
\mu=E(X).
\]

二阶中心矩就是方差：

\[
D(X)=E[(X-\mu)^2].
\]

所以方差其实就是一个特殊的二阶中心矩。

### 6. 方差 \(D\) 是什么

方差定义为：

\[
D(X)=E[(X-E X)^2].
\]

所以你说得对：

方差就是在期望符号里面放了一个特殊的内容：

\[
(X-EX)^2.
\]

它表示：

先看 \(X\) 偏离均值多少，再平方，再取平均。

常用计算公式：

\[
D(X)=E(X^2)-[E(X)]^2.
\]

这个公式来自展开：

\[
E[(X-\mu)^2]
=
E(X^2-2\mu X+\mu^2).
\]

利用 \(E\) 的线性性：

\[
E(X^2-2\mu X+\mu^2)
=
E(X^2)-2\mu E(X)+\mu^2.
\]

因为

\[
\mu=E(X),
\]

所以

\[
D(X)=E(X^2)-\mu^2.
\]

也就是

\[
D(X)=E(X^2)-[E(X)]^2.
\]

### 7. 协方差 \(\operatorname{Cov}\) 是什么

协方差定义为：

\[
\operatorname{Cov}(X,Y)
=
E[(X-EX)(Y-EY)].
\]

所以协方差也是一个期望，只是期望里面放的是：

\[
(X-EX)(Y-EY).
\]

它描述 \(X,Y\) 是否一起偏离各自均值。

常用计算公式：

\[
\operatorname{Cov}(X,Y)=E(XY)-E(X)E(Y).
\]

这个也来自展开：

\[
E[(X-\mu_X)(Y-\mu_Y)].
\]

展开内部：

\[
(X-\mu_X)(Y-\mu_Y)
=
XY-\mu_XY-\mu_YX+\mu_X\mu_Y.
\]

取期望：

\[
E(XY)-\mu_XE(Y)-\mu_YE(X)+\mu_X\mu_Y.
\]

因为

\[
\mu_X=E(X),\qquad \mu_Y=E(Y),
\]

所以最后得到：

\[
\operatorname{Cov}(X,Y)=E(XY)-E(X)E(Y).
\]

### 8. 为什么方差和协方差可以展开

本质原因就是：

\[
E
\]

是线性算子。

例如：

\[
D(aX+bY)
=
E\{[aX+bY-E(aX+bY)]^2\}.
\]

先用期望线性性：

\[
E(aX+bY)=aEX+bEY.
\]

所以

\[
aX+bY-E(aX+bY)
=
a(X-EX)+b(Y-EY).
\]

平方：

\[
[a(X-EX)+b(Y-EY)]^2
=
a^2(X-EX)^2
+b^2(Y-EY)^2
+2ab(X-EX)(Y-EY).
\]

再取期望：

\[
D(aX+bY)
=
a^2E[(X-EX)^2]
+b^2E[(Y-EY)^2]
+2abE[(X-EX)(Y-EY)].
\]

于是：

\[
D(aX+bY)
=
a^2D(X)+b^2D(Y)+2ab\operatorname{Cov}(X,Y).
\]

所以方差组合公式不是背出来的，它就是：

1. 先中心化；
2. 平方展开；
3. 用 \(E\) 的线性性拆开。

### 9. 一个总框架

概率论计算可以这样看：

\[
\boxed{
\text{随机变量 }X
\xrightarrow{\text{分布}}
\text{可以计算 }E[g(X)].
}
\]

然后：

\[
E(X)
\]

描述中心位置；

\[
D(X)=E[(X-EX)^2]
\]

描述波动大小；

\[
\operatorname{Cov}(X,Y)=E[(X-EX)(Y-EY)]
\]

描述两个变量一起变化的关系；

\[
E(X^n)
\]

描述更高阶的形状信息。

所以这些对象都统一在一个框架里：

\[
\boxed{
\text{对随机变量的某个函数取期望。}
}
\]

### 10. 最小记忆

随机变量：

\[
X=\text{带概率分布的量。}
\]

期望：

\[
E=\text{按概率加权平均的线性算子。}
\]

方差：

\[
D(X)=E[(X-EX)^2].
\]

协方差：

\[
\operatorname{Cov}(X,Y)=E[(X-EX)(Y-EY)].
\]

矩：

\[
E(X^n),\qquad E[(X-\mu)^n].
\]

最关键的代数规则：

\[
E(aX+bY)=aE(X)+bE(Y).
\]

但一般不能把乘法拆开：

\[
E(XY)\ne E(X)E(Y).
\]

只有独立时才有：

\[
E(XY)=E(X)E(Y).
\]

---

## 把随机变量看成函数，把 \(E\) 看成积分算子

这是一个很好的理解方式。

概率论可以从这个角度看：

\[
\boxed{
\text{随机变量是函数，期望是积分算子。}
}
\]

### 1. 随机变量是函数

设样本空间为

\[
\Omega.
\]

其中每个元素 \(\omega\in\Omega\) 表示一次可能的随机结果。

随机变量 \(X\) 本质上是一个函数：

\[
X:\Omega\to \mathbb R.
\]

也就是说，每发生一个结果 \(\omega\)，随机变量就给出一个数：

\[
\omega\mapsto X(\omega).
\]

例如掷骰子：

\[
\Omega=\{1,2,3,4,5,6\}.
\]

如果 \(X\) 表示点数，那么

\[
X(\omega)=\omega.
\]

如果 \(Y\) 表示点数的平方，那么

\[
Y(\omega)=X(\omega)^2.
\]

所以 \(Y=X^2\) 也是一个随机变量，也就是另一个函数。

### 2. 期望是对随机变量这个函数积分

期望可以写成：

\[
E(X)=\int_\Omega X(\omega)\,dP(\omega).
\]

这里 \(P\) 是概率测度。

这个式子可以理解为：

\[
\text{把函数 }X(\omega)\text{ 按照概率权重 }dP(\omega)\text{ 积分。}
\]

所以 \(E\) 是一个把随机变量函数变成数的算子：

\[
E:\text{随机变量}\to \mathbb R.
\]

也就是：

\[
X\mapsto E(X).
\]

### 3. 离散型时就是求和

如果 \(\Omega\) 是离散的，那么积分变成求和：

\[
E(X)=\sum_{\omega\in\Omega}X(\omega)P(\{\omega\}).
\]

如果直接按 \(X\) 的取值求和：

\[
E(X)=\sum_i x_iP(X=x_i).
\]

所以离散型期望就是按概率加权求和。

### 4. 连续型时就是普通积分

如果随机变量 \(X\) 有密度 \(f_X(x)\)，那么

\[
E(X)=\int_{-\infty}^{+\infty}x f_X(x)\,dx.
\]

更一般地：

\[
E[g(X)]
=
\int_{-\infty}^{+\infty}g(x)f_X(x)\,dx.
\]

这里可以理解为：

先把随机变量 \(X\) 经过函数 \(g\) 变成新的随机变量 \(g(X)\)，然后再积分求期望。

### 5. \(E\) 的线性性来自积分的线性性

因为积分是线性的，所以期望也是线性的：

\[
E(aX+bY)
=
\int_\Omega [aX(\omega)+bY(\omega)]\,dP(\omega).
\]

利用积分线性性：

\[
E(aX+bY)
=
a\int_\Omega X(\omega)\,dP(\omega)
+b\int_\Omega Y(\omega)\,dP(\omega).
\]

所以：

\[
E(aX+bY)=aE(X)+bE(Y).
\]

因此你可以把 \(E\) 看成一个线性积分算子。

### 6. 独立为什么能让乘积期望拆开

如果 \(X,Y\) 独立，并且有联合密度 \(f_{X,Y}(x,y)\)，则独立意味着：

\[
f_{X,Y}(x,y)=f_X(x)f_Y(y).
\]

于是

\[
E(XY)=
\int_{-\infty}^{+\infty}
\int_{-\infty}^{+\infty}
xy f_{X,Y}(x,y)\,dx\,dy.
\]

由独立性：

\[
E(XY)=
\int\int xy f_X(x)f_Y(y)\,dx\,dy.
\]

把与 \(x\) 有关的部分和与 \(y\) 有关的部分分开：

\[
E(XY)
=
\left(\int x f_X(x)\,dx\right)
\left(\int y f_Y(y)\,dy\right).
\]

所以：

\[
E(XY)=E(X)E(Y).
\]

这就是“独立时二重积分可以拆成两个积分相乘”。

### 7. 不独立时为什么不能拆

如果 \(X,Y\) 不独立，那么一般有：

\[
f_{X,Y}(x,y)\ne f_X(x)f_Y(y).
\]

于是

\[
E(XY)=\int\int xy f_{X,Y}(x,y)\,dx\,dy
\]

不能拆成

\[
\left(\int x f_X(x)\,dx\right)
\left(\int y f_Y(y)\,dy\right).
\]

所以一般情况下：

\[
E(XY)\ne E(X)E(Y).
\]

### 8. 方差和协方差也都是积分算子下的函数

方差：

\[
D(X)=E[(X-EX)^2].
\]

从函数角度看，就是：

\[
D(X)=
\int_\Omega [X(\omega)-E(X)]^2\,dP(\omega).
\]

协方差：

\[
\operatorname{Cov}(X,Y)
=
E[(X-EX)(Y-EY)].
\]

也就是：

\[
\operatorname{Cov}(X,Y)
=
\int_\Omega
[X(\omega)-E(X)][Y(\omega)-E(Y)]\,dP(\omega).
\]

所以方差、协方差都可以理解为：

\[
\boxed{
\text{先构造一个新函数，再对它按概率积分。}
}
\]

### 9. 最小记忆

随机变量：

\[
X:\Omega\to\mathbb R.
\]

期望：

\[
E(X)=\int_\Omega X(\omega)\,dP(\omega).
\]

函数变换：

\[
E[g(X)]=\int g(x)f_X(x)\,dx.
\]

线性性：

\[
E(aX+bY)=aE(X)+bE(Y).
\]

独立时：

\[
E(XY)=E(X)E(Y).
\]

方差：

\[
D(X)=\int_\Omega [X(\omega)-E(X)]^2\,dP(\omega).
\]

协方差：

\[
\operatorname{Cov}(X,Y)
=
\int_\Omega
[X(\omega)-E(X)][Y(\omega)-E(Y)]\,dP(\omega).
\]

---

## 期望 \(E\) 作为积分算子，以及独立时为什么可以拆

你的理解是对的：

\[
E
\]

确实可以看成一种积分算子。

更准确地说，期望是对概率分布积分。

### 1. 连续型随机变量的期望

如果 \(X\) 是连续型随机变量，密度为 \(f_X(x)\)，那么

\[
E[g(X)]
=
\int_{-\infty}^{+\infty}g(x)f_X(x)\,dx.
\]

这就是对 \(g(X)\) 按照 \(X\) 的概率密度加权积分。

### 2. 二维随机变量的期望

如果 \((X,Y)\) 有联合密度

\[
f_{X,Y}(x,y),
\]

那么

\[
E[h(X,Y)]
=
\int_{-\infty}^{+\infty}
\int_{-\infty}^{+\infty}
h(x,y)f_{X,Y}(x,y)\,dx\,dy.
\]

例如

\[
E(XY)
=
\int_{-\infty}^{+\infty}
\int_{-\infty}^{+\infty}
xy f_{X,Y}(x,y)\,dx\,dy.
\]

### 3. 独立时联合密度可以拆

如果 \(X,Y\) 独立，那么

\[
f_{X,Y}(x,y)=f_X(x)f_Y(y).
\]

所以

\[
E(XY)
=
\int\int xy f_X(x)f_Y(y)\,dx\,dy.
\]

把只含 \(x\) 的部分和只含 \(y\) 的部分分开：

\[
E(XY)
=
\left(\int x f_X(x)\,dx\right)
\left(\int y f_Y(y)\,dy\right).
\]

也就是

\[
E(XY)=E(X)E(Y).
\]

这就是为什么独立时乘积的期望可以拆成期望的乘积。

### 4. 更一般的形式

如果 \(X,Y\) 独立，那么对合适的函数 \(g,h\)，有

\[
E[g(X)h(Y)]=E[g(X)]E[h(Y)].
\]

证明也是一样：

\[
E[g(X)h(Y)]
=
\int\int g(x)h(y)f_X(x)f_Y(y)\,dx\,dy.
\]

拆开：

\[
E[g(X)h(Y)]
=
\left(\int g(x)f_X(x)\,dx\right)
\left(\int h(y)f_Y(y)\,dy\right).
\]

所以

\[
E[g(X)h(Y)]=E[g(X)]E[h(Y)].
\]

### 5. 不独立时为什么不能拆

如果 \(X,Y\) 不独立，那么一般有

\[
f_{X,Y}(x,y)\ne f_X(x)f_Y(y).
\]

这时

\[
E(XY)
=
\int\int xy f_{X,Y}(x,y)\,dx\,dy
\]

里面的联合密度不能拆成两个单独密度。

所以一般不能写成

\[
E(XY)=E(X)E(Y).
\]

### 6. 离散型也是同样逻辑

如果 \(X,Y\) 是离散型随机变量，那么

\[
E(XY)=\sum_x\sum_y xyP(X=x,Y=y).
\]

若 \(X,Y\) 独立，则

\[
P(X=x,Y=y)=P(X=x)P(Y=y).
\]

于是

\[
E(XY)
=
\sum_x\sum_y xyP(X=x)P(Y=y).
\]

拆成：

\[
E(XY)
=
\left(\sum_x xP(X=x)\right)
\left(\sum_y yP(Y=y)\right).
\]

所以

\[
E(XY)=E(X)E(Y).
\]

### 7. 最小记忆

\[
E=\text{对概率分布积分或求和的算子。}
\]

连续型：

\[
E[g(X)]=\int g(x)f_X(x)\,dx.
\]

二维连续型：

\[
E[h(X,Y)]=\int\int h(x,y)f_{X,Y}(x,y)\,dx\,dy.
\]

独立的关键是：

\[
f_{X,Y}(x,y)=f_X(x)f_Y(y).
\]

因此：

\[
E[g(X)h(Y)]=E[g(X)]E[h(Y)].
\]

所以你的说法可以精炼成：

\[
\boxed{
\text{独立时，联合积分中的联合密度可拆，因此二重积分可拆成两个积分的乘积。}
}
\]
