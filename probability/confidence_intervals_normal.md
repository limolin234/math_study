# 正态总体的区间估计与枢轴量方法

## 1. 区间估计估计的是什么

设总体含有未知参数，例如

$$
X_1,X_2,\ldots,X_n \overset{i.i.d.}{\sim} N(\mu,\sigma^2).
$$

区间估计估计的是总体参数，例如总体均值 $\mu$ 或总体方差 $\sigma^2$。它不是估计样本均值 $\bar X$；$\bar X$ 只是用来构造区间的统计量。

频率学派中，参数被看作固定但未知的常数：

$$
\mu \text{ 固定但未知。}
$$

随机的是样本

$$
X_1,\ldots,X_n,
$$

以及由样本构造出来的区间

$$
[L(X_1,\ldots,X_n),\ U(X_1,\ldots,X_n)].
$$

置信水平 $1-\alpha$ 表示这个造区间的方法在重复抽样中的覆盖概率：

$$
P_\mu\{L(X_1,\ldots,X_n)\le \mu\le U(X_1,\ldots,X_n)\}=1-\alpha.
$$

也可以理解为对所有可能样本积分：

$$
\int_{\{x:L(x)\le \mu\le U(x)\}}
 f(x_1,\ldots,x_n;\mu,\sigma^2)\,dx_1\cdots dx_n
=1-\alpha.
$$

注意：已经抽样后得到的具体区间要么包含真实参数，要么不包含真实参数；$95\%$ 说的是长期重复抽样的覆盖率，不是说固定参数有 $95\%$ 概率落入已经算出的区间。

贝叶斯统计中可以把参数当作随机变量，并讨论后验概率

$$
P(\mu\in [a,b]\mid X_1,
\ldots,X_n)=0.95,
$$

这类区间叫可信区间，不是频率学派的置信区间。

## 2. 区间估计的基本做题思路

核心是寻找枢轴量。枢轴量满足：

1. 含有待估参数；
2. 含有样本统计量；
3. 其分布不含未知参数。

通用步骤：

$$
\boxed{
\text{构造估计量}
\longrightarrow
\text{归一化成已知分布}
\longrightarrow
\text{取分位数}
\longrightarrow
\text{反解参数区间}
}
$$

即先找

$$
G(X_1,
\ldots,X_n;\theta)
$$

使它服从已知分布，然后写

$$
P(a\le G\le b)=1-\alpha,
$$

再把

$$
a\le G(X;\theta)
\le b
$$

解成

$$
L(X)\le \theta\le U(X).
$$

## 3. 为什么区间不唯一

置信区间的本质要求是覆盖概率：

$$
P_\theta\{L(X)\le \theta\le U(X)\}=1-\alpha.
$$

只要满足这个要求，区间一般不唯一。

例如

$$
Z=\frac{\bar X-\mu}{\sigma/\sqrt n}\sim N(0,1).
$$

常用对称区域

$$
[-z_{\alpha/2},z_{\alpha/2}],
$$

满足

$$
P(-z_{\alpha/2}\le Z\le z_{\alpha/2})=1-\alpha.
$$

但也可以选不对称的 $a<b$，只要

$$
P(a\le Z\le b)=1-\alpha,
$$

就可得到

$$
\bar X-b\frac{\sigma}{\sqrt n}
\le \mu\le
\bar X-a\frac{\sigma}{\sqrt n}.
$$

因此“点估计 $\pm$ 误差界”只是最常见的对称双侧区间，不是区间估计的定义。

## 4. 正态均值的归一化与 $\sqrt n$

样本均值为

$$
\bar X=\frac{1}{n}\sum_{i=1}^n X_i.
$$

若

$$
X_i\sim N(\mu,\sigma^2),
$$

则

$$
\bar X\sim N\left(\mu,\frac{\sigma^2}{n}\right).
$$

这是因为独立时方差可加：

$$
\operatorname{Var}(X_1+\cdots+X_n)=n\sigma^2,
$$

所以

$$
\operatorname{Var}(\bar X)
=\operatorname{Var}\left(\frac{X_1+\cdots+X_n}{n}\right)
=\frac{1}{n^2}n\sigma^2
=\frac{\sigma^2}{n}.
$$

因此样本均值的标准差，也叫标准误，是

$$
\operatorname{SE}(\bar X)=\frac{\sigma}{\sqrt n}.
$$

标准化就是减去均值、除以标准差：

$$
Z=\frac{\bar X-\mu}{\sigma/\sqrt n}
=\frac{\sqrt n(\bar X-\mu)}{\sigma}
\sim N(0,1).
$$

所以区间中出现 $\sqrt n$，是因为平均以后方差缩小到 $\sigma^2/n$，标准差缩小到 $\sigma/\sqrt n$。

## 5. 单个正态总体均值区间：方差已知

若 $\sigma^2$ 已知，估计 $\mu$。

枢轴量为

$$
Z=\frac{\bar X-\mu}{\sigma/\sqrt n}\sim N(0,1).
$$

取标准正态上 $\alpha/2$ 分位数 $z_{\alpha/2}$，使

$$
P(-z_{\alpha/2}\le Z\le z_{\alpha/2})=1-\alpha.
$$

代入并反解 $\mu$：

$$
P\left(
\bar X-z_{\alpha/2}\frac{\sigma}{\sqrt n}
\le \mu\le
\bar X+z_{\alpha/2}\frac{\sigma}{\sqrt n}
\right)=1-\alpha.
$$

故 $1-\alpha$ 置信区间为

$$
\boxed{
\left[
\bar X-z_{\alpha/2}\frac{\sigma}{\sqrt n},
\bar X+z_{\alpha/2}\frac{\sigma}{\sqrt n}
\right]
}
$$

常见写法是

$$
\boxed{
\bar X\pm z_{\alpha/2}\frac{\sigma}{\sqrt n}
}
$$

## 6. 单个正态总体均值区间：方差未知

若 $\sigma^2$ 未知，用样本方差

$$
S^2=\frac{1}{n-1}\sum_{i=1}^n (X_i-\bar X)^2
$$

估计总体方差。

正态总体有两个关键结论：

$$
\frac{\bar X-\mu}{\sigma/\sqrt n}\sim N(0,1),
$$

$$
\frac{(n-1)S^2}{\sigma^2}\sim \chi^2(n-1),
$$

并且 $\bar X$ 与 $S^2$ 独立。

令

$$
Z=\frac{\bar X-\mu}{\sigma/\sqrt n},
\qquad
V=\frac{(n-1)S^2}{\sigma^2}.
$$

则

$$
\frac{Z}{\sqrt{V/(n-1)}}\sim t(n-1).
$$

而

$$
\frac{Z}{\sqrt{V/(n-1)}}
=\frac{\frac{\bar X-\mu}{\sigma/\sqrt n}}
{\sqrt{\frac{(n-1)S^2/\sigma^2}{n-1}}}
=\frac{\bar X-\mu}{S/\sqrt n}.
$$

所以

$$
T=\frac{\bar X-\mu}{S/\sqrt n}\sim t(n-1).
$$

取 t 分布上 $\alpha/2$ 分位数 $t_{\alpha/2}(n-1)$：

$$
P\left(-t_{\alpha/2}(n-1)\le T\le t_{\alpha/2}(n-1)\right)=1-\alpha.
$$

反解得到

$$
\boxed{
\left[
\bar X-t_{\alpha/2}(n-1)\frac{S}{\sqrt n},
\bar X+t_{\alpha/2}(n-1)\frac{S}{\sqrt n}
\right]
}
$$

也就是

$$
\boxed{
\bar X\pm t_{\alpha/2}(n-1)\frac{S}{\sqrt n}
}
$$

方差未知时表面上要处理二维随机量

$$
(\bar X,S^2),
$$

但正态总体下 $\bar X$ 与 $S^2$ 独立，并且分别对应正态分布与卡方分布，所以二维问题被封装成了一维的 t 分布问题。

## 7. 点估计、标准误与误差界

常见对称置信区间可以理解为

$$
\boxed{
\text{点估计}
\pm
\text{分位数}\times \text{标准误}
}
$$

不是“点估计 $\pm$ 方差”。方差单位与参数单位不同，不能直接加到参数上；要用标准差或标准误。

对于正态均值：

$$
\hat\mu=\bar X,
\qquad
\operatorname{Var}(\bar X)=\frac{\sigma^2}{n},
\qquad
\operatorname{SE}(\bar X)=\frac{\sigma}{\sqrt n}.
$$

所以方差已知时

$$
\bar X\pm z_{\alpha/2}\operatorname{SE}(\bar X),
$$

方差未知时

$$
\bar X\pm t_{\alpha/2}(n-1)\frac{S}{\sqrt n}.
$$

例如 $95\%$ 正态区间常用

$$
\bar X\pm 1.96\operatorname{SE}(\bar X).
$$

## 8. 与 $\chi^2$ 分布、F 分布的关系

估计单个正态总体方差时，用卡方分布：

$$
\frac{(n-1)S^2}{\sigma^2}\sim \chi^2(n-1).
$$

若用右尾分位数记号，$\sigma^2$ 的 $1-\alpha$ 置信区间为

$$
\boxed{
\left[
\frac{(n-1)S^2}{\chi^2_{\alpha/2}(n-1)},
\frac{(n-1)S^2}{\chi^2_{1-\alpha/2}(n-1)}
\right]
}
$$

不同教材的卡方分位数记号可能不同，关键是：左端分母用较大的卡方分位数，右端分母用较小的卡方分位数。

F 分布来自两个独立卡方变量的比值。若

$$
U\sim \chi^2(m),
\qquad
V\sim \chi^2(n),
$$

且独立，则

$$
\frac{U/m}{V/n}\sim F(m,n).
$$

F 分布常用于两个正态总体方差比、方差分析、回归整体显著性检验等问题。

若

$$
T\sim t(\nu),
$$

则

$$
T^2\sim F(1,\nu).
$$

所以双侧 t 检验也可以改写成某种 F 检验形式，但均值区间估计中直接用 t 分布最自然。

## 9. 做题时如何判断用哪个分布

常见规则：

1. 估计正态总体均值 $\mu$，且 $\sigma^2$ 已知：用标准正态分布；
2. 估计正态总体均值 $\mu$，且 $\sigma^2$ 未知：用 t 分布；
3. 估计单个正态总体方差 $\sigma^2$：用卡方分布；
4. 比较两个正态总体方差或估计方差比：用 F 分布；
5. 大样本下估计比例、均值差或一般参数：常用渐近正态分布。

考试中不要只背公式，优先问：

$$
\boxed{
\text{能否把含未知参数的统计量变成一个已知分布？}
}
$$

找到枢轴量以后，剩下就是查分位数并反解参数。

## 10. 考试计算精度建议

如果题目没有特殊说明，通常可按下面规则：

1. 分位数按教材附表或题目给出的数值使用；
2. 中间计算保留 $4$ 到 $6$ 位有效数字；
3. 最终答案保留 $2$ 到 $4$ 位小数；
4. 若题目要求“精确到 $0.01$”，最终保留两位小数；
5. 不要太早四舍五入，最后统一取整。

常用分位数例子：

$$
z_{0.025}\approx 1.96,
\qquad
z_{0.05}\approx 1.645,
\qquad
z_{0.005}\approx 2.576.
$$

手动计算时建议拆开：

$$
SE=\frac{S}{\sqrt n},
\qquad
E=c\cdot SE,
$$

最后算

$$
\bar X-E,
\qquad
\bar X+E.
$$

这样比每次重新输入整个公式更不容易出错。

若给原始样本，可先算

$$
\sum X_i,
\qquad
\sum X_i^2,
$$

再用

$$
\bar X=\frac{1}{n}\sum X_i,
$$

$$
S^2=\frac{1}{n-1}\left(\sum X_i^2-n\bar X^2\right).
$$

卷面上建议写清楚：枢轴量、分布与自由度、分位数、标准误、误差界、最终区间。即使最后小数略有误差，也更容易拿到步骤分。
