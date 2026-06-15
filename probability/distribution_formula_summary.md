# 常见分布公式、期望方差与组合性质

本表用于快速复习常见分布的分布函数/密度函数、期望、方差、参数意义以及相加等组合性质。

约定：

- 离散分布写概率质量函数 PMF：$P(X=k)$。
- 连续分布写概率密度函数 PDF：$f(x)$。
- 分布函数统一记为 $F(x)=P(X\le x)$。
- Gamma 分布默认使用 rate 参数 $\lambda$，即密度中是 $e^{-\lambda x}$。如果使用 scale 参数 $\beta=1/\lambda$，公式要相应转换。

---

## 1. Bernoulli 分布

记作：

$$
X\sim Bernoulli(p)
$$

取值：

$$
X\in\{0,1\}
$$

PMF：

$$
P(X=1)=p,
\qquad
P(X=0)=1-p
$$

也可写为：

$$
P(X=x)=p^x(1-p)^{1-x},\qquad x=0,1
$$

期望：

$$
E(X)=p
$$

方差：

$$
Var(X)=p(1-p)
$$

组合性质：若

$$
X_1,
\dots,
X_n\sim Bernoulli(p)
$$

独立同分布，则

$$
\sum_{i=1}^n X_i\sim Binomial(n,p)
$$

---

## 2. Binomial 分布

记作：

$$
X\sim Binomial(n,p)
$$

取值：

$$
X=0,1,
\dots,n
$$

PMF：

$$
P(X=k)=\binom nk p^k(1-p)^{n-k}
$$

期望：

$$
E(X)=np
$$

方差：

$$
Var(X)=np(1-p)
$$

组合性质：若

$$
X\sim Binomial(n_1,p),
\qquad
Y\sim Binomial(n_2,p)
$$

独立，并且成功概率相同，则

$$
X+Y\sim Binomial(n_1+n_2,p)
$$

近似性质：当 $n$ 大、$p$ 小、$np=\lambda$ 适中时，

$$
Binomial(n,p)\approx Poisson(\lambda)
$$

当 $np$ 和 $n(1-p)$ 都较大时，

$$
Binomial(n,p)\approx N(np,np(1-p))
$$

---

## 3. Poisson 分布

记作：

$$
X\sim Poisson(\lambda)
$$

取值：

$$
X=0,1,2,
\dots
$$

PMF：

$$
P(X=k)=e^{-\lambda}\frac{\lambda^k}{k!}
$$

期望：

$$
E(X)=\lambda
$$

方差：

$$
Var(X)=\lambda
$$

组合性质：若

$$
X\sim Poisson(\lambda_1),
\qquad
Y\sim Poisson(\lambda_2)
$$

独立，则

$$
X+Y\sim Poisson(\lambda_1+
\lambda_2)
$$

近似性质：

$$
Binomial(n,p)\approx Poisson(np)
$$

适合稀有事件计数。

---

## 4. Uniform 分布

记作：

$$
X\sim Uniform(a,b)
$$

取值：

$$
a\le X\le b
$$

PDF：

$$
f(x)=\frac{1}{b-a},\qquad a\le x\le b
$$

CDF：

$$
F(x)=
\begin{cases}
0, & x<a,\\
\dfrac{x-a}{b-a}, & a\le x\le b,\\
1, & x>b.
\end{cases}
$$

期望：

$$
E(X)=\frac{a+b}{2}
$$

方差：

$$
Var(X)=\frac{(b-a)^2}{12}
$$

组合性质：独立均匀分布相加一般不再是均匀分布。

若

$$
X_i\sim Uniform(0,1)
$$

独立，则

$$
\sum_{i=1}^n X_i
$$

服从 Irwin-Hall 分布。

---

## 5. Exponential 分布

记作：

$$
X\sim Exponential(\lambda)
$$

取值：

$$
X\ge0
$$

PDF：

$$
f(x)=\lambda e^{-\lambda x},\qquad x\ge0
$$

CDF：

$$
F(x)=1-e^{-\lambda x},\qquad x\ge0
$$

期望：

$$
E(X)=\frac1\lambda
$$

方差：

$$
Var(X)=\frac1{\lambda^2}
$$

无记忆性：

$$
P(X>s+t\mid X>s)=P(X>t)
$$

组合性质：若

$$
X_1,
\dots,
X_n\sim Exponential(\lambda)
$$

独立同分布，则

$$
\sum_{i=1}^n X_i\sim Gamma(n,\lambda)
$$

最小值性质：若

$$
X_i\sim Exponential(\lambda_i)
$$

独立，则

$$
\min_i X_i\sim Exponential\left(\sum_i\lambda_i\right)
$$

并且

$$
P(X_k=\min_iX_i)=\frac{\lambda_k}{\sum_i\lambda_i}
$$

---

## 6. Gamma 分布

记作：

$$
X\sim Gamma(\alpha,\lambda)
$$

这里 $\lambda$ 是 rate 参数。

取值：

$$
X>0
$$

PDF：

$$
f(x)=\frac{\lambda^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\lambda x},\qquad x>0
$$

期望：

$$
E(X)=\frac{\alpha}{\lambda}
$$

方差：

$$
Var(X)=\frac{\alpha}{\lambda^2}
$$

组合性质：若

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

特殊关系：

$$
Exponential(\lambda)=Gamma(1,\lambda)
$$

若采用 rate 记法：

$$
\chi^2(n)=Gamma\left(\frac n2,\frac12\right)
$$

若采用 scale 记法：

$$
\chi^2(n)=Gamma\left(\frac n2,2\right)
$$

---

## 7. Normal 分布

记作：

$$
X\sim N(\mu,\sigma^2)
$$

取值：

$$
X\in(-\infty,
\infty)
$$

PDF：

$$
f(x)=\frac{1}{\sqrt{2\pi}\sigma}\exp\left[-\frac{(x-\mu)^2}{2\sigma^2}\right]
$$

期望：

$$
E(X)=\mu
$$

方差：

$$
Var(X)=\sigma^2
$$

标准化：

$$
Z=\frac{X-\mu}{\sigma}\sim N(0,1)
$$

组合性质：若

$$
X\sim N(\mu_1,
\sigma_1^2),
\qquad
Y\sim N(\mu_2,
\sigma_2^2)
$$

独立，则

$$
X+Y\sim N(\mu_1+
\mu_2,
\sigma_1^2+
\sigma_2^2)
$$

更一般地，独立正态的线性组合仍为正态：

$$
\sum_i a_iX_i\sim N\left(\sum_i a_i\mu_i,
\sum_i a_i^2\sigma_i^2\right)
$$

---

## 8. Chi-square 分布

记作：

$$
X\sim \chi^2(n)
$$

定义：若

$$
Z_1,
\dots,
Z_n\sim N(0,1)
$$

独立，则

$$
X=\sum_{i=1}^n Z_i^2\sim \chi^2(n)
$$

取值：

$$
X\ge0
$$

期望：

$$
E(X)=n
$$

方差：

$$
Var(X)=2n
$$

组合性质：若

$$
X\sim \chi^2(n_1),
\qquad
Y\sim \chi^2(n_2)
$$

独立，则

$$
X+Y\sim \chi^2(n_1+n_2)
$$

与样本方差关系：若

$$
X_1,
\dots,
X_n\sim N(\mu,
\sigma^2)
$$

独立同分布，则

$$
\frac{(n-1)S^2}{\sigma^2}\sim \chi^2(n-1)
$$

---

## 9. t 分布

记作：

$$
T\sim t(n)
$$

定义：若

$$
Z\sim N(0,1),
\qquad
U\sim \chi^2(n)
$$

独立，则

$$
T=\frac{Z}{\sqrt{U/n}}\sim t(n)
$$

取值：

$$
T\in(-\infty,
\infty)
$$

性质：

- 关于 0 对称；
- 自由度越大越接近 $N(0,1)$；
- 小自由度时尾巴比正态更厚；
- 一般无简单相加封闭性。

期望：

$$
E(T)=0\qquad(n>1)
$$

方差：

$$
Var(T)=\frac{n}{n-2}\qquad(n>2)
$$

平方关系：

$$
T^2\sim F(1,n)
$$

应用：总体方差未知时，对正态总体均值做推断。

---

## 10. F 分布

记作：

$$
F\sim F(n_1,n_2)
$$

定义：若

$$
U_1\sim \chi^2(n_1),
\qquad
U_2\sim \chi^2(n_2)
$$

独立，则

$$
F=\frac{U_1/n_1}{U_2/n_2}\sim F(n_1,n_2)
$$

取值：

$$
F>0
$$

性质：

- 右偏；
- 常用于方差比、ANOVA、回归整体显著性检验；
- 一般无简单相加封闭性。

期望：

$$
E(F)=\frac{n_2}{n_2-2}\qquad(n_2>2)
$$

方差：

$$
Var(F)=\frac{2n_2^2(n_1+n_2-2)}{n_1(n_2-2)^2(n_2-4)}\qquad(n_2>4)
$$

倒数关系：

$$
F\sim F(n_1,n_2)
\quad\Rightarrow\quad
\frac1F\sim F(n_2,n_1)
$$

临界值关系：如果 $F_\alpha(n_1,n_2)$ 表示右尾面积为 $\alpha$ 的临界值，则

$$
F_\alpha(n_1,n_2)=\frac{1}{F_{1-\alpha}(n_2,n_1)}
$$

---

## 11. Beta 分布

记作：

$$
X\sim Beta(\alpha,\beta)
$$

取值：

$$
0<X<1
$$

PDF：

$$
f(x)=\frac{1}{B(\alpha,
\beta)}x^{\alpha-1}(1-x)^{\beta-1},
\qquad 0<x<1
$$

其中

$$
B(\alpha,
\beta)=\frac{\Gamma(\alpha)\Gamma(\beta)}{\Gamma(\alpha+
\beta)}
$$

期望：

$$
E(X)=\frac{\alpha}{\alpha+
\beta}
$$

方差：

$$
Var(X)=\frac{\alpha\beta}{(\alpha+
\beta)^2(\alpha+
\beta+1)}
$$

组合关系：若

$$
X\sim Gamma(\alpha,
\lambda),
\qquad
Y\sim Gamma(\beta,
\lambda)
$$

独立且 rate 相同，则

$$
\frac{X}{X+Y}\sim Beta(\alpha,
\beta)
$$

并且

$$
X+Y\sim Gamma(\alpha+
\beta,
\lambda)
$$

应用：比例、概率参数、贝叶斯共轭先验。

---

## 12. 总览表

| 分布 | 期望 | 方差 | 组合/特殊性质 |
|---|---:|---:|---|
| $Bernoulli(p)$ | $p$ | $p(1-p)$ | 独立同参数求和为 $Binomial(n,p)$ |
| $Binomial(n,p)$ | $np$ | $np(1-p)$ | 相同 $p$ 的独立二项相加仍二项 |
| $Poisson(\lambda)$ | $\lambda$ | $\lambda$ | 独立 Poisson 相加仍 Poisson |
| $Uniform(a,b)$ | $(a+b)/2$ | $(b-a)^2/12$ | 相加一般不再均匀 |
| $Exponential(\lambda)$ | $1/\lambda$ | $1/\lambda^2$ | 无记忆；相加为 Gamma；最小值仍指数 |
| $Gamma(\alpha,\lambda)$ | $\alpha/\lambda$ | $\alpha/\lambda^2$ | 相同 rate 时相加仍 Gamma |
| $N(\mu,\sigma^2)$ | $\mu$ | $\sigma^2$ | 独立正态线性组合仍正态 |
| $\chi^2(n)$ | $n$ | $2n$ | 独立卡方相加仍卡方 |
| $t(n)$ | $0$，$n>1$ | $n/(n-2)$，$n>2$ | 平方为 $F(1,n)$ |
| $F(n_1,n_2)$ | $n_2/(n_2-2)$ | 见上式 | 倒数换自由度 |
| $Beta(\alpha,\beta)$ | $\alpha/(\alpha+\beta)$ | $\alpha\beta/[(\alpha+\beta)^2(\alpha+\beta+1)]$ | Gamma 比值得到 Beta |

---

## 13. Geometric 分布

几何分布描述：独立重复 Bernoulli 试验中，第一次成功出现所需的试验次数。

记作：

$$
X\sim Geometric(p)
$$

这里采用“试验次数”记法：

$$
X=1,2,3,
\dots
$$

PMF：

$$
P(X=k)=(1-p)^{k-1}p,
\qquad k=1,2,
\dots
$$

期望：

$$
E(X)=\frac1p
$$

方差：

$$
Var(X)=\frac{1-p}{p^2}
$$

意义：

- 每次试验成功概率为 $p$；
- $X$ 表示等到第一次成功一共做了多少次试验；
- 例如直到第一次命中、第一次故障、第一次收到包。

另一个常见记法是“第一次成功前失败次数”：

$$
Y=X-1
$$

则

$$
P(Y=y)=(1-p)^y p,
\qquad y=0,1,2,
\dots
$$

此时

$$
E(Y)=\frac{1-p}{p}
$$

$$
Var(Y)=\frac{1-p}{p^2}
$$

几何分布是负二项分布在 $r=1$ 时的特例。

---

## 14. Negative Binomial / 逆二项分布 / 负二项分布

负二项分布描述：独立重复 Bernoulli 试验中，得到第 $r$ 次成功所需的试验次数。

也常叫逆二项分布，因为二项分布是固定试验次数数成功次数，而这里是固定成功次数数试验次数。

记作：

$$
X\sim NegativeBinomial(r,p)
$$

这里采用“试验次数”记法：

$$
X=r,r+1,r+2,
\dots
$$

PMF：

$$
P(X=k)=\binom{k-1}{r-1}p^r(1-p)^{k-r},
\qquad k=r,r+1,
\dots
$$

期望：

$$
E(X)=\frac rp
$$

方差：

$$
Var(X)=\frac{r(1-p)}{p^2}
$$

意义：

- 每次试验成功概率为 $p$；
- $X$ 表示为了得到第 $r$ 次成功，一共需要做多少次试验；
- 例如直到第 $r$ 次命中、直到第 $r$ 个合格品、直到第 $r$ 次事件发生。

另一种常见记法是“第 $r$ 次成功前失败次数”：

$$
Y=X-r
$$

则

$$
P(Y=y)=\binom{y+r-1}{r-1}p^r(1-p)^y,
\qquad y=0,1,2,
\dots
$$

此时

$$
E(Y)=\frac{r(1-p)}p
$$

$$
Var(Y)=\frac{r(1-p)}{p^2}
$$

关系：

- $r=1$ 时，负二项分布退化为几何分布；
- 二项分布：固定试验次数 $n$，数成功次数；
- 负二项分布：固定成功次数 $r$，数试验次数或失败次数。

---

## 15. Hypergeometric 分布 / 超几何分布

超几何分布描述：有限总体中不放回抽样时，抽到成功类对象的个数。

设总体大小为 $N$，其中成功类对象有 $M$ 个，失败类对象有 $N-M$ 个。从中不放回抽取 $n$ 个，令 $X$ 为抽到的成功类个数，则

$$
X\sim Hypergeometric(N,M,n)
$$

PMF：

$$
P(X=k)=
\frac{\binom{M}{k}\binom{N-M}{n-k}}{\binom{N}{n}}
$$

其中 $k$ 的范围要满足：

$$
\max(0,n-(N-M))\le k\le \min(n,M)
$$

期望：

$$
E(X)=n\frac{M}{N}
$$

方差：

$$
Var(X)=n\frac{M}{N}\left(1-\frac{M}{N}\right)\frac{N-n}{N-1}
$$

意义：

- 总体有限；
- 抽样不放回；
- 每次抽取之间不独立；
- 用于抽检、摸球、不放回抽样中的合格品数。

和二项分布的关系：

二项分布适合“有放回或近似独立”的抽样：

$$
X\sim Binomial(n,p)
$$

超几何分布适合“不放回”的有限总体抽样。

当总体 $N$ 很大，抽样比例 $n/N$ 很小时，超几何分布可近似为二项分布：

$$
Hypergeometric(N,M,n)
\approx
Binomial\left(n,\frac{M}{N}
\right)
$$

---

## 16. 常见离散分布的意义对比

| 分布 | 实验方式 | 随机变量表示什么 | 典型参数 |
|---|---|---|---|
| Bernoulli | 做 1 次成功/失败试验 | 是否成功 | $p$ |
| Binomial | 固定做 $n$ 次独立试验 | 成功次数 | $n,p$ |
| Geometric | 做到第 1 次成功为止 | 第一次成功所需试验次数 | $p$ |
| Negative Binomial | 做到第 $r$ 次成功为止 | 第 $r$ 次成功所需试验次数 | $r,p$ |
| Hypergeometric | 有限总体不放回抽 $n$ 个 | 抽到的成功类个数 | $N,M,n$ |
| Poisson | 连续时间/空间稀有事件计数 | 单位区间内事件数 | $\lambda$ |

记忆：

- Bernoulli 是一次试验；
- Binomial 是固定次数数成功；
- Geometric 是等第一次成功；
- Negative Binomial 是等第 $r$ 次成功；
- Hypergeometric 是不放回抽样数成功；
- Poisson 是稀有事件计数。
