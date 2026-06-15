# 概率论基础概念与常见分布性质

本文由 `tmp.md` 中的概率论讨论整理而成，作为参数、估计量、矩、抽样分布以及常见分布性质的复习入口。

---

## t 分布与 F 分布的特性和关系

### 1. t 分布的定义

设

$$
Z\sim N(0,1)
$$

并且

$$
U\sim \chi^2(n)
$$

其中 $Z$ 与 $U$ 相互独立。定义

$$
T=\frac{Z}{\sqrt{U/n}}
$$

则

$$
T\sim t(n)
$$

这里的 $n$ 叫自由度。

直观上，t 分布就是：

$$
\text{标准正态量}\div \text{由样本方差带来的随机尺度}
$$

所以它比标准正态分布尾巴更厚。

---

### 2. t 分布的主要特性

$t(n)$ 分布关于 0 对称：

$$
T\sim t(n)\quad \Rightarrow\quad -T\sim t(n)
$$

当自由度 $n$ 越大，$U/n$ 越接近 1，所以

$$
t(n)\to N(0,1)
$$

自由度越小，分母的不确定性越大，尾巴越厚。

典型用途：总体方差未知时，对均值做推断。

如果

$$
X_1,\dots,X_n\sim N(\mu,\sigma^2)
$$

则

$$
\frac{\bar X-\mu}{S/\sqrt n}\sim t(n-1)
$$

这里用样本标准差 $S$ 代替未知的总体标准差 $\sigma$，所以引入了 t 分布。

---

### 3. F 分布的定义

设

$$
U_1\sim \chi^2(n_1),
\qquad
U_2\sim \chi^2(n_2)
$$

并且 $U_1,U_2$ 相互独立。定义

$$
F=\frac{U_1/n_1}{U_2/n_2}
$$

则

$$
F\sim F(n_1,n_2)
$$

这里 $n_1,n_2$ 分别叫分子自由度和分母自由度。

直观上，F 分布就是：

$$
\text{两个独立方差估计量的比值}
$$

---

### 4. F 分布的主要特性

F 分布只取正值：

$$
F>0
$$

它一般不对称，右尾较长。

如果

$$
F\sim F(n_1,n_2)
$$

则倒数满足

$$
\frac1F\sim F(n_2,n_1)
$$

典型用途：比较两个方差、方差分析 ANOVA、回归模型整体显著性检验。

---

### 5. t 分布与 F 分布的关系

若

$$
T\sim t(n)
$$

则

$$
T^2\sim F(1,n)
$$

推导很直接。因为

$$
T=\frac{Z}{\sqrt{U/n}}
$$

所以

$$
T^2=\frac{Z^2}{U/n}
$$

而

$$
Z^2\sim \chi^2(1)
$$

因此

$$
T^2=\frac{\chi^2(1)/1}{\chi^2(n)/n}
\sim F(1,n)
$$

所以 t 检验的平方，常常可以看成一个特殊的 F 检验。

---

### 6. 一个总览

三者关系可以记成：

$$
N(0,1)^2=\chi^2(1)
$$

$$
\frac{N(0,1)}{\sqrt{\chi^2(n)/n}}=t(n)
$$

$$
\frac{\chi^2(n_1)/n_1}{\chi^2(n_2)/n_2}=F(n_1,n_2)
$$

$$
t(n)^2=F(1,n)
$$

直观层级：

$$
\text{正态} \rightarrow \chi^2 \rightarrow t,F
$$

其中 t 分布主要处理“均值 + 方差未知”，F 分布主要处理“方差比值”。

## 样本方差、残差平方和与卡方分布

### 1. 先统一记号

设样本为

$$
X_1,X_2,\dots,X_n
$$

样本均值为

$$
\bar X=\frac1n\sum_{i=1}^n X_i
$$

残差平方和通常记为

$$
Q=\sum_{i=1}^n (X_i-\bar X)^2
$$

也常写成

$$
Q=\sum_{i=1}^n X_i^2-n\bar X^2
$$

注意不是

$$
\sum X_i-\bar X^2
$$

而是

$$
\sum X_i^2-n\bar X^2
$$

---

### 2. 样本方差的定义

无偏样本方差定义为

$$
S^2=\frac{1}{n-1}\sum_{i=1}^n (X_i-\bar X)^2
$$

所以

$$
(n-1)S^2=\sum_{i=1}^n (X_i-\bar X)^2=Q
$$

这只是定义变形，不是概率分布结论。

---

### 3. 正态样本下的卡方结论

如果

$$
X_1,\dots,X_n\sim N(\mu,\sigma^2)
$$

并且相互独立，则有结论

$$
\frac{(n-1)S^2}{\sigma^2}\sim \chi^2(n-1)
$$

等价地：

$$
\frac{Q}{\sigma^2}\sim \chi^2(n-1)
$$

这里的 $\sigma^2$ 是总体方差，$S^2$ 是样本方差。

所以正确关系不是

$$
\sigma^2=(n-1)S^2
$$

而是：

$$
(n-1)S^2=Q
$$

以及在正态总体假设下：

$$
\frac{(n-1)S^2}{\sigma^2}\sim \chi^2(n-1)
$$

---

### 4. 为什么自由度是 \(n-1\)

因为残差

$$
X_i-\bar X
$$

满足一个约束：

$$
\sum_{i=1}^n (X_i-\bar X)=0
$$

所以虽然有 $n$ 个残差，但只有 $n-1$ 个可以自由变化。

这就是样本方差分母用 $n-1$，以及卡方自由度是 $n-1$ 的原因。

## F 分布临界值的倒数关系

### 1. F 分布本身的倒数性质

设

$$
X\sim F(n_1,n_2)
$$

意思是

$$
X=\frac{U_1/n_1}{U_2/n_2}
$$

其中

$$
U_1\sim \chi^2(n_1),\qquad U_2\sim \chi^2(n_2)
$$

并且 $U_1,U_2$ 独立。

那么

$$
\frac1X=\frac{U_2/n_2}{U_1/n_1}
$$

所以

$$
\frac1X\sim F(n_2,n_1)
$$

这就是 F 分布倒数关系的根源：

$$
X\sim F(n_1,n_2)
\quad\Longrightarrow\quad
\frac1X\sim F(n_2,n_1)
$$

---

### 2. 分位数记号容易混

如果用普通 CDF 分位数记号

$$
q_p(n_1,n_2)
$$

表示

$$
P(X\le q_p)=p
$$

那么由倒数关系得到：

$$
q_p(n_1,n_2)=\frac{1}{q_{1-p}(n_2,n_1)}
$$

原因是倒数会把“大于”变成“小于”。

---

### 3. 统计表里的 \(F_\alpha\) 常是右尾临界值

很多教材把

$$
F_\alpha(n_1,n_2)
$$

定义成右尾面积为 $\alpha$ 的临界值：

$$
P\{X>F_\alpha(n_1,n_2)\}=\alpha
$$

也就是

$$
F_\alpha(n_1,n_2)=q_{1-\alpha}(n_1,n_2)
$$

这时倒数关系会写成

$$
F_\alpha(n_1,n_2)
=\frac{1}{F_{1-\alpha}(n_2,n_1)}
$$

注意这里右边的自由度顺序要交换。

---

### 4. 直观理解

F 分布比较的是两个方差估计的比值：

$$
F=\frac{\text{分子方差估计}}{\text{分母方差估计}}
$$

取倒数就是把分子、分母互换：

$$
\frac1F=\frac{\text{分母方差估计}}{\text{分子方差估计}}
$$

所以自由度也跟着互换。

大值取倒数变小值，因此上侧概率和下侧概率互换，这就是为什么临界值里会出现 $\alpha$ 和 $1-\alpha$。

## 估计量、统计量与估计值

### 1. 统计量是什么

设样本为

$$
X_1,X_2,\dots,X_n
$$

统计量是样本的函数：

$$
T=T(X_1,X_2,\dots,X_n)
$$

并且这个函数里不能含有未知参数。

例如：

$$
\bar X=\frac1n\sum_{i=1}^n X_i
$$

是统计量。

$$
S^2=\frac{1}{n-1}\sum_{i=1}^n (X_i-\bar X)^2
$$

也是统计量。

统计量本质上是：

$$
\text{样本} \rightarrow \text{函数} \rightarrow \text{新的随机变量}
$$

因为样本本身是随机变量，所以统计量也是随机变量。

---

### 2. 估计量是什么

估计量是用来估计未知参数的统计量。

如果总体分布里有未知参数

$$
\theta
$$

我们用样本构造一个统计量

$$
\hat\theta=T(X_1,X_2,\dots,X_n)
$$

来估计它，那么 $\hat\theta$ 就叫 $\theta$ 的估计量。

所以：

$$
\boxed{\text{估计量是统计量的一种}}
$$

区别在于：

- 统计量：任何不含未知参数的样本函数；
- 估计量：专门拿来估计未知参数的统计量。

---

### 3. 估计量和估计值的区别

抽样之前：

$$
\hat\theta=T(X_1,\dots,X_n)
$$

它是随机变量，叫估计量。

抽样之后，得到具体样本值

$$
x_1,x_2,\dots,x_n
$$

代入函数：

$$
\hat\theta=T(x_1,
\dots,x_n)
$$

这时得到的是一个具体数值，叫估计值。

所以：

$$
\text{估计量是随机变量，估计值是一次观测后的数。}
$$

---

### 4. 例子：估计总体均值

设总体均值为未知参数

$$
\mu
$$

常用样本均值估计它：

$$
\hat\mu=\bar X
$$

其中

$$
\bar X=\frac1n\sum_{i=1}^n X_i
$$

所以 $\bar X$ 既是统计量，也是 $\mu$ 的估计量。

如果实际抽到样本

$$
2,3,5
$$

那么估计值是

$$
\bar x=\frac{2+3+5}{3}=\frac{10}{3}
$$

---

### 5. 例子：估计总体方差

总体方差为未知参数

$$
\sigma^2
$$

常用无偏样本方差估计：

$$
S^2=\frac{1}{n-1}\sum_{i=1}^n (X_i-\bar X)^2
$$

所以 $S^2$ 是 $\sigma^2$ 的估计量。

如果用

$$
\frac1n\sum_{i=1}^n (X_i-\bar X)^2
$$

也可以作为估计量，但它是有偏估计量。

---

### 6. 估计量的评价标准

常见评价标准包括：

#### 无偏性

$$
E(\hat\theta)=\theta
$$

意思是长期平均来看不偏。

#### 方差

$$
\operatorname{Var}(\hat\theta)
$$

表示估计量本身的波动大小。

#### 均方误差

$$
\operatorname{MSE}(\hat\theta)=E[(\hat\theta-\theta)^2]
$$

并且

$$
\operatorname{MSE}(\hat\theta)
=\operatorname{Var}(\hat\theta)+\operatorname{Bias}(\hat\theta)^2
$$

#### 一致性

当样本量变大时，估计量越来越接近真参数：

$$
\hat\theta_n\xrightarrow{P}\theta
$$

---

### 7. 一句话总结

估计量可以理解为：

$$
\text{为了估计未知参数而设计的样本函数}
$$

由于样本是随机的，所以估计量在抽样前是随机变量；抽样后代入具体数据，才得到一个具体估计值。

## 常见分布的可加性、封闭性与特殊性质

这里的重点是：哪些分布在相加、缩放、取最小值、条件化时仍然保持同类分布。

---

## 1. 正态分布 Normal

若

$$
X\sim N(\mu_1,\sigma_1^2),
\qquad
Y\sim N(\mu_2,\sigma_2^2)
$$

并且独立，则

$$
X+Y\sim N(\mu_1+\mu_2,\sigma_1^2+\sigma_2^2)
$$

更一般地，如果 $X_i$ 独立且

$$
X_i\sim N(\mu_i,\sigma_i^2)
$$

则

$$
\sum_i a_iX_i\sim N\left(\sum_i a_i\mu_i,\sum_i a_i^2\sigma_i^2\right)
$$

正态分布的核心性质：

- 线性组合仍是正态；
- 期望线性相加；
- 独立时方差相加；
- 标准化后变成标准正态。

标准化：

$$
Z=\frac{X-\mu}{\sigma}\sim N(0,1)
$$

---

## 2. Bernoulli 分布

若

$$
X\sim Bernoulli(p)
$$

则

$$
P(X=1)=p,
\qquad
P(X=0)=1-p
$$

期望和方差：

$$
E(X)=p
$$

$$
Var(X)=p(1-p)
$$

若

$$
X_1,\dots,X_n\sim Bernoulli(p)
$$

独立同分布，则

$$
\sum_{i=1}^n X_i\sim Binomial(n,p)
$$

直观：Bernoulli 是一次成功/失败实验，Binomial 是 $n$ 次 Bernoulli 成功次数。

---

## 3. Binomial 分布

若

$$
X\sim Binomial(n,p)
$$

则

$$
E(X)=np
$$

$$
Var(X)=np(1-p)
$$

可加性：若

$$
X\sim Binomial(n_1,p),
\qquad
Y\sim Binomial(n_2,p)
$$

并且独立，注意成功概率必须相同，则

$$
X+Y\sim Binomial(n_1+n_2,p)
$$

如果两个二项分布的 $p$ 不同，一般相加后不再是普通二项分布。

---

## 4. Poisson 分布

若

$$
X\sim Poisson(\lambda)
$$

则

$$
E(X)=\lambda
$$

$$
Var(X)=\lambda
$$

可加性：若

$$
X\sim Poisson(\lambda_1),
\qquad
Y\sim Poisson(\lambda_2)
$$

并且独立，则

$$
X+Y\sim Poisson(\lambda_1+
\lambda_2)
$$

Poisson 的核心特点：

- 独立计数可以相加；
- 均值等于方差；
- 可作为稀有事件二项分布近似。

二项分布近似：当 $n$ 很大、$p$ 很小、$np=\lambda$ 固定时，

$$
Binomial(n,p)\approx Poisson(\lambda)
$$

---

## 5. Exponential 分布

若

$$
X\sim Exponential(\lambda)
$$

则

$$
E(X)=\frac1\lambda
$$

$$
Var(X)=\frac1{\lambda^2}
$$

指数分布最重要性质是无记忆性：

$$
P(X>s+t\mid X>s)=P(X>t)
$$

指数分布的相加：若

$$
X_1,\dots,X_n\sim Exponential(\lambda)
$$

独立同分布，则

$$
\sum_{i=1}^n X_i\sim Gamma(n,\lambda)
$$

当形状参数 $n$ 是整数时，也叫 Erlang 分布。

注意：指数分布相加一般不再是指数分布，而是 Gamma 分布。

指数分布的最小值性质：若

$$
X_i\sim Exponential(\lambda_i)
$$

独立，则

$$
\min_i X_i\sim Exponential\left(\sum_i \lambda_i\right)
$$

并且

$$
P(X_k=\min_i X_i)=\frac{\lambda_k}{\sum_i\lambda_i}
$$

---

## 6. Gamma 分布

这里采用 rate 参数记法：

$$
X\sim Gamma(\alpha,\lambda)
$$

密度中含 $e^{-\lambda x}$。

期望和方差：

$$
E(X)=\frac{\alpha}{\lambda}
$$

$$
Var(X)=\frac{\alpha}{\lambda^2}
$$

可加性：若

$$
X\sim Gamma(\alpha_1,\lambda),
\qquad
Y\sim Gamma(\alpha_2,\lambda)
$$

独立，并且 rate 参数相同，则

$$
X+Y\sim Gamma(\alpha_1+
\alpha_2,\lambda)
$$

指数分布是 Gamma 的特例：

$$
Exponential(\lambda)=Gamma(1,\lambda)
$$

卡方分布也是 Gamma 的特例：

$$
\chi^2(n)=Gamma\left(\frac n2,\frac12\right)
$$

这里是 rate 记法；如果用 scale 记法，则写成 $Gamma(n/2,2)$。

---

## 7. Chi-square 分布

若

$$
Z_1,
\dots,Z_n\sim N(0,1)
$$

独立，则

$$
\sum_{i=1}^n Z_i^2\sim \chi^2(n)
$$

期望和方差：

$$
E(\chi^2(n))=n
$$

$$
Var(\chi^2(n))=2n
$$

可加性：若

$$
X\sim \chi^2(n_1),
\qquad
Y\sim \chi^2(n_2)
$$

独立，则

$$
X+Y\sim \chi^2(n_1+n_2)
$$

因为卡方本质是独立标准正态平方和。

---

## 8. t 分布

若

$$
T\sim t(n)
$$

则它可以表示为

$$
T=\frac{Z}{\sqrt{U/n}}
$$

其中

$$
Z\sim N(0,1),
\qquad
U\sim \chi^2(n)
$$

并且独立。

性质：

- 关于 0 对称；
- 自由度越大越接近 $N(0,1)$；
- 尾巴比标准正态厚；
- 一般没有简单相加封闭性。

平方关系：

$$
T^2\sim F(1,n)
$$

---

## 9. F 分布

若

$$
F=\frac{U_1/n_1}{U_2/n_2}
$$

其中

$$
U_1\sim \chi^2(n_1),
\qquad
U_2\sim \chi^2(n_2)
$$

独立，则

$$
F\sim F(n_1,n_2)
$$

性质：

- 只取正值；
- 右偏；
- 常用于方差比、ANOVA、回归整体检验；
- 一般没有简单相加封闭性。

倒数关系：

$$
F\sim F(n_1,n_2)
\quad\Rightarrow\quad
\frac1F\sim F(n_2,n_1)
$$

---

## 10. Beta 分布

若

$$
X\sim Beta(\alpha,\beta)
$$

则 $X$ 取值在 $[0,1]$。

期望和方差：

$$
E(X)=\frac{\alpha}{\alpha+
\beta}
$$

$$
Var(X)=\frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}
$$

Beta 分布一般没有简单的相加封闭性。

它的重要性质是和 Gamma 分布的关系：若

$$
X\sim Gamma(\alpha,\lambda),
\qquad
Y\sim Gamma(\beta,\lambda)
$$

独立且 rate 相同，则

$$
\frac{X}{X+Y}\sim Beta(\alpha,\beta)
$$

并且

$$
X+Y\sim Gamma(\alpha+\beta,\lambda)
$$

直观：Beta 分布常用于描述比例、概率参数的不确定性。

---

## 11. Uniform 分布

若

$$
X\sim Uniform(a,b)
$$

则

$$
E(X)=\frac{a+b}{2}
$$

$$
Var(X)=\frac{(b-a)^2}{12}
$$

多个独立均匀分布相加，一般不再是均匀分布。

例如若

$$
X_i\sim Uniform(0,1)
$$

独立，则

$$
\sum_{i=1}^n X_i
$$

服从 Irwin-Hall 分布。

---

## 12. 总结表

| 分布 | 相加/封闭性 | 关键性质 |
|---|---|---|
| Normal | 独立正态线性组合仍正态 | 均值线性，独立方差相加 |
| Bernoulli | 同参数 Bernoulli 求和为 Binomial | 单次 0/1 实验 |
| Binomial | 相同 $p$ 的独立二项相加仍二项 | 成功次数 |
| Poisson | 独立 Poisson 相加仍 Poisson | 均值等于方差，稀有事件 |
| Exponential | 相加为 Gamma，不再指数 | 无记忆性，最小值仍指数 |
| Gamma | 相同 rate 时相加仍 Gamma | 等待时间总和 |
| Chi-square | 独立卡方相加仍卡方 | 标准正态平方和 |
| t | 一般无相加封闭性 | 对称，厚尾，平方是 F |
| F | 一般无相加封闭性 | 方差比，倒数换自由度 |
| Beta | 一般无相加封闭性 | 比例分布，与 Gamma 比值有关 |
| Uniform | 相加一般不均匀 | 区间上等可能 |


## 分布函数 \(F(x;\theta_1,\dots,\theta_m)\) 与原点矩写法

### 1. 分布函数里的分号是什么意思

写

$$
F(x;\theta_1,
\dots,
\theta_m)
$$

意思是：分布函数以 $x$ 为自变量，同时还依赖若干未知参数

$$
\theta_1,
\dots,
\theta_m
$$

分号的作用是把“变量”和“参数”分开：

$$
F(\text{变量};\text{参数})
$$

这里 $x$ 是随机变量取值的位置，$\theta_1,
\dots,
\theta_m$ 是控制分布形状的参数。

例如正态分布：

$$
X\sim N(\mu,\sigma^2)
$$

它的分布函数可以写成

$$
F(x;\mu,
\sigma^2)=P(X\le x)
$$

这里：

- $x$ 是输入位置；
- $\mu,\sigma^2$ 是参数。

指数分布：

$$
X\sim Exp(\lambda)
$$

分布函数为

$$
F(x;\lambda)=1-e^{-\lambda x},\qquad x\ge0
$$

---

### 2. 为什么不用逗号而用分号

数学上也可以写

$$
F(x,\theta_1,
\dots,
\theta_m)
$$

但概率统计里常用分号写成

$$
F(x;\theta_1,
\dots,
\theta_m)
$$

是为了提醒：

- $x$ 是分布函数的自变量；
- $\theta_i$ 是固定但未知的参数。

在估计问题中，参数不是随机变量，而是我们想估计的未知常数。

---

### 3. k 阶原点矩是什么

随机变量 $X$ 的 $r$ 阶原点矩定义为

$$
E(X^r)
$$

之所以叫“原点矩”，是因为它是围绕 0 取矩。

和它相对的是中心矩：

$$
E[(X-E X)^r]
$$

例如：

- 一阶原点矩：

$$
E(X)
$$

- 二阶原点矩：

$$
E(X^2)
$$

- 二阶中心矩：

$$
E[(X-E X)^2]=Var(X)
$$

---

### 4. \(E(X^r)=a_r(\theta_1,\dots,\theta_m)\) 是什么意思

如果 $X$ 的分布依赖参数

$$
\theta_1,
\dots,
\theta_m
$$

那么 $X$ 的各阶矩通常也会依赖这些参数。

所以可以写：

$$
E(X^r)=a_r(\theta_1,
\dots,
\theta_m)
$$

意思是：

$$
\text{第 }r\text{ 阶原点矩是参数的某个函数。}
$$

这里的 $a_r$ 不是新分布，而是一个由分布算出来的函数。

---

### 5. 例子：正态分布

若

$$
X\sim N(\mu,\sigma^2)
$$

则

$$
E(X)=\mu
$$

所以

$$
a_1(\mu,
\sigma^2)=\mu
$$

又因为

$$
Var(X)=E(X^2)-[E(X)]^2
$$

所以

$$
E(X^2)=\sigma^2+
\mu^2
$$

因此

$$
a_2(\mu,
\sigma^2)=\mu^2+
\sigma^2
$$

---

### 6. 例子：指数分布

若

$$
X\sim Exp(\lambda)
$$

则

$$
E(X)=\frac1\lambda
$$

所以

$$
a_1(\lambda)=\frac1\lambda
$$

并且

$$
E(X^r)=\frac{r!}{\lambda^r}
$$

所以

$$
a_r(\lambda)=\frac{r!}{\lambda^r}
$$

---

### 7. 这和矩估计有什么关系

矩估计法就是利用理论矩和样本矩对应。

理论矩：

$$
E(X^r)=a_r(\theta_1,
\dots,
\theta_m)
$$

样本原点矩：

$$
A_r=\frac1n\sum_{i=1}^n X_i^r
$$

矩估计的思想是令

$$
A_r=a_r(\theta_1,
\dots,
\theta_m)
$$

如果有 $m$ 个未知参数，就通常列前 $m$ 个矩方程：

$$
A_1=a_1(\theta_1,
\dots,
\theta_m)
$$

$$
A_2=a_2(\theta_1,
\dots,
\theta_m)
$$

$$
\cdots
$$

$$
A_m=a_m(\theta_1,
\dots,
\theta_m)
$$

然后解出参数估计值。

---

### 8. 避免记号混淆

最好把参数个数和矩的阶数分开写。

参数个数用 $m$：

$$
\theta_1,
\dots,
\theta_m
$$

矩的阶数用 $r$：

$$
E(X^r)=a_r(\theta_1,
\dots,
\theta_m)
$$

这样就不会把“第 $r$ 阶矩”和“第 $m$ 个参数”混在一起。

## 参数 \(\theta\) 和变量 \(x\) 的关系

### 1. \(x\) 是随机变量可能取到的值

分布函数写作

$$
F(x;\theta)=P_\theta(X\le x)
$$

其中 $x$ 是输入位置。

也就是说，给定一个数 $x$，分布函数回答：

$$
X\text{ 落在 }(-\infty,x]\text{ 的概率是多少？}
$$

例如正态分布中，

$$
F(3;\mu,
\sigma^2)
$$

表示：在参数为 $\mu,
\sigma^2$ 的正态总体下，随机变量 $X$ 小于等于 3 的概率。

---

### 2. \(\theta\) 是控制分布形状的参数

$\theta$ 不是样本取值，而是分布背后的控制量。

常见例子：

#### Bernoulli 分布

$$
X\sim Bernoulli(p)
$$

参数是

$$
\theta=p
$$

它控制成功概率。

#### Poisson 分布

$$
X\sim Poisson(\lambda)
$$

参数是

$$
\theta=\lambda
$$

它控制单位时间或单位区域内的平均发生次数。

#### 正态分布

$$
X\sim N(\mu,
\sigma^2)
$$

参数是

$$
\theta_1=\mu,
\qquad
\theta_2=\sigma^2
$$

其中 $\mu$ 控制中心位置，$\sigma^2$ 控制分散程度。

#### 指数分布

$$
X\sim Exp(\lambda)
$$

参数是

$$
\theta=\lambda
$$

它控制等待时间的快慢。

---

### 3. 固定参数，看 \(x\)：这是分布函数

如果参数 $\theta$ 固定，那么

$$
F(x;\theta)
$$

就是关于 $x$ 的函数。

它描述随机变量 $X$ 的分布。

例如固定

$$
\mu=0,
\qquad
\sigma^2=1
$$

则

$$
F(x;0,1)
$$

就是标准正态分布函数。

---

### 4. 固定观测值，看 \(\theta\)：这是估计问题

如果已经观察到样本值 $x$，那么分布公式也可以反过来看成参数的函数。

例如密度函数

$$
f(x;\theta)
$$

当 $x$ 固定、$\theta$ 变化时，就和似然函数有关：

$$
L(\theta)=f(x;\theta)
$$

多个样本时：

$$
L(\theta)=\prod_{i=1}^n f(x_i;\theta)
$$

所以同一个公式有两种视角：

- 参数已知，看 $x$：研究分布；
- 样本已知，看 $\theta$：估计参数。

---

### 5. 频率学派和贝叶斯学派的区别

在经典统计中，参数 $\theta$ 通常被看成固定但未知的常数。

样本

$$
X_1,
\dots,
X_n
$$

是随机变量。

在贝叶斯统计中，参数 $\theta$ 也可以被看成随机变量，并给它一个先验分布。

但在常规数理统计课程里，通常采用经典观点：

$$
\theta\text{ 固定未知，样本随机。}
$$

---

### 6. 一句话总结

$$
F(x;\theta)
$$

中：

- $x$ 是随机变量可能取到的位置；
- $\theta$ 是控制整个分布形状的参数；
- 固定 $\theta$，它是关于 $x$ 的分布函数；
- 固定样本 $x$，反过来看 $\theta$，就进入参数估计问题。

## \(\sum 1/x_i\) 与 \(1/\bar x\) 的关系

设样本为

$$
x_1,x_2,\dots,x_n
$$

样本均值为

$$
\bar x=\frac1n\sum_{i=1}^n x_i
$$

那么

$$
\sum_{i=1}^n \frac1{x_i}
$$

和

$$
\frac1{\bar x}
$$

一般没有相等关系。

---

### 1. 正确对比对象

如果要比较平均意义下的倒数，应该比较

$$
\frac1n\sum_{i=1}^n\frac1{x_i}
$$

和

$$
\frac1{\bar x}
$$

前者是“倒数的平均”，后者是“平均的倒数”。

一般来说：

$$
\frac1n\sum_{i=1}^n\frac1{x_i}
\ne
\frac1{\bar x}
$$

---

### 2. 当所有 \(x_i>0\) 时的不等式

因为函数

$$
f(x)=\frac1x
$$

在 $x>0$ 上是凸函数，所以由 Jensen 不等式：

$$
\frac1n\sum_{i=1}^n\frac1{x_i}
\ge
\frac1{\frac1n\sum_{i=1}^n x_i}
$$

也就是

$$
\frac1n\sum_{i=1}^n\frac1{x_i}
\ge
\frac1{\bar x}
$$

等价地：

$$
\sum_{i=1}^n\frac1{x_i}
\ge
\frac{n}{\bar x}
$$

等号成立当且仅当所有 $x_i$ 都相等。

---

### 3. 和调和平均的关系

调和平均定义为

$$
H=\frac{n}{\sum_{i=1}^n 1/x_i}
$$

所以

$$
\frac1n\sum_{i=1}^n\frac1{x_i}=\frac1H
$$

而对于正数，有

$$
H\le \bar x
$$

因此

$$
\frac1H\ge \frac1{\bar x}
$$

这和上面的 Jensen 结论一致。

---

### 4. 例子

取

$$
x_1=1,
\qquad
x_2=3
$$

则

$$
\bar x=2
$$

所以

$$
\frac1{\bar x}=\frac12
$$

但

$$
\frac12\left(\frac11+\frac13\right)=\frac23
$$

所以

$$
\frac1n\sum_{i=1}^n\frac1{x_i}
>
\frac1{\bar x}
$$

---

### 5. 注意符号条件

上面的不等式要求

$$
x_i>0
$$

如果样本中有负数、零，情况会复杂很多：

- 有 $x_i=0$ 时，$1/x_i$ 不存在；
- 有正有负时，通常没有简单的大小关系。

在概率统计里，如果变量是正值变量，例如寿命、等待时间、尺度参数样本，常用上面的正数结论。
