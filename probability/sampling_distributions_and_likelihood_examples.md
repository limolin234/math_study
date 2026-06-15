# 抽样分布、样本方差与似然例题

本文由 `tmp.md` 中关于正态样本、卡方分布、t/F 分布、样本方差修正和似然函数的讨论整理而成。

---

## 正态样本中 \(\bar X\)、\(S^2\) 与卡方分布

设

$$
X_1,
\dots,
X_n\sim N(0,1)
$$

独立同分布。样本均值为

$$
\bar X=\frac1n\sum_{i=1}^n X_i
$$

样本方差按常用无偏定义：

$$
S^2=\frac1{n-1}\sum_{i=1}^n (X_i-\bar X)^2
$$

---

### 1. 样本均值部分

因为正态分布线性组合仍为正态，

$$
\bar X\sim N\left(0,\frac1n\right)
$$

所以

$$
\sqrt n\bar X\sim N(0,1)
$$

因此

$$
n\bar X^2=(\sqrt n\bar X)^2\sim \chi^2(1)
$$

---

### 2. 样本方差部分

正态样本有标准结论：

$$
\frac{(n-1)S^2}{\sigma^2}\sim \chi^2(n-1)
$$

这里总体方差

$$
\sigma^2=1
$$

所以

$$
(n-1)S^2\sim \chi^2(n-1)
$$

并且对于正态样本，

$$
\bar X\quad \text{与}\quad S^2
$$

相互独立。

---

### 3. 让 \(a\bar X^2+bS^2\) 服从卡方分布

因为

$$
n\bar X^2\sim \chi^2(1)
$$

$$
(n-1)S^2\sim \chi^2(n-1)
$$

且二者独立，所以它们相加仍为卡方分布：

$$
n\bar X^2+(n-1)S^2\sim \chi^2(n)
$$

因此若要求两个部分都参与，并且结果是标准卡方分布，应取

$$
a=n,
\qquad
b=n-1
$$

此时自由度为

$$
n
$$

---

### 4. \(a,b\) 是否唯一？

如果题目要求

$$
a\bar X^2+bS^2
$$

由两个部分相加构成一个标准卡方分布，那么自然取

$$
a=n,
\qquad
b=n-1
$$

这是把两个独立卡方项都标准化后的取法。

但如果允许其中一个系数为 0，也有退化选择：

$$
n\bar X^2\sim \chi^2(1)
$$

或者

$$
(n-1)S^2\sim \chi^2(n-1)
$$

所以需要看题目是否要求两个项都出现。通常这类题意是找

$$
a=n,
\quad
b=n-1
$$

使整体服从

$$
\chi^2(n)
$$

---

### 5. \(D(S^2)\) 怎么算

由

$$
(n-1)S^2\sim \chi^2(n-1)
$$

而如果

$$
Y\sim \chi^2(k)
$$

则

$$
E(Y)=k,
\qquad
D(Y)=2k
$$

令

$$
Y=(n-1)S^2
$$

则

$$
D(Y)=2(n-1)
$$

而

$$
S^2=\frac{Y}{n-1}
$$

所以

$$
D(S^2)=\frac{D(Y)}{(n-1)^2}
=\frac{2(n-1)}{(n-1)^2}
=\frac{2}{n-1}
$$

因此

$$
\boxed{D(S^2)=\frac{2}{n-1}}
$$

这里不需要先单独算期望也能算方差，但通常会同时知道：

$$
E(S^2)=1
$$

因为

$$
E[(n-1)S^2]=n-1
$$

所以

$$
E(S^2)=1
$$

---

### 6. 如果样本方差用分母 \(n\)

有些教材把样本中心二阶矩定义为

$$
S_n^2=\frac1n\sum_{i=1}^n (X_i-\bar X)^2
$$

这时

$$
nS_n^2=(n-1)S^2\sim \chi^2(n-1)
$$

所以对应结论会变成：

$$
n\bar X^2+nS_n^2\sim \chi^2(n)
$$

并且

$$
D(S_n^2)=\frac{2(n-1)}{n^2}
$$

因此做题前要先确认样本方差分母是 $n-1$ 还是 $n$。

## 什么时候会出现 \(n-1\) 这种无偏估计修正

### 1. 最典型场景：用样本均值估计总体均值后，再估计方差

设

$$
X_1,
\dots,
X_n
$$

独立同分布，且

$$
E(X_i)=\mu,
\qquad
D(X_i)=\sigma^2
$$

如果总体均值 $\mu$ 已知，那么方差可以用

$$
\frac1n\sum_{i=1}^n (X_i-\mu)^2
$$

估计，并且它是无偏的：

$$
E\left[\frac1n\sum_{i=1}^n (X_i-\mu)^2\right]=\sigma^2
$$

但实际中 $\mu$ 通常未知，要用样本均值

$$
\bar X
$$

代替，于是得到

$$
\frac1n\sum_{i=1}^n (X_i-\bar X)^2
$$

它的期望是

$$
\frac{n-1}{n}\sigma^2
$$

偏小。因此要修正成

$$
S^2=\frac1{n-1}\sum_{i=1}^n (X_i-\bar X)^2
$$

这样才有

$$
E(S^2)=\sigma^2
$$

---

### 2. 为什么是 \(n-1\)

残差为

$$
X_i-\bar X
$$

它们满足约束

$$
\sum_{i=1}^n (X_i-\bar X)=0
$$

所以 $n$ 个残差中只有 $n-1$ 个可以自由变化。

这就是自由度损失 1 的来源。

直观上：你先用同一批样本估计了一个参数 $\mu$，再用这些残差估计方差，因此损失了一个自由度。

---

### 3. 是否只在正态分布下成立？

样本方差无偏性

$$
E\left[\frac1{n-1}\sum (X_i-\bar X)^2\right]=\sigma^2
$$

不要求正态分布。

只需要：

- $X_1,
\dots,
X_n$ 独立同分布；
- 方差存在。

正态分布额外给出更强结论：

$$
\frac{(n-1)S^2}{\sigma^2}\sim \chi^2(n-1)
$$

这个卡方分布结论需要正态性。

---

### 4. 是否只和二阶矩有关？

最常见的 $n-1$ 修正确实出现在二阶中心矩，也就是方差估计中。

原因是方差是围绕未知均值的平方偏差：

$$
E[(X-\mu)^2]
$$

当 $\mu$ 未知并用 $\bar X$ 替代时，会让残差平方和系统性偏小。

但是更广义地，只要你用样本先估计了一些参数，再估计误差大小，就会出现“自由度修正”。

例如线性回归中有 $p$ 个参数，残差平方和的无偏方差估计常写成

$$
\hat\sigma^2=\frac{RSS}{n-p}
$$

这里不是 $n-1$，而是 $n-p$。

---

### 5. 什么时候不用 \(n-1\)

#### 二阶原点矩不用

估计

$$
E(X^2)
$$

时用

$$
\frac1n\sum X_i^2
$$

这是样本二阶原点矩，不需要 $n-1$ 修正。

#### 总体均值已知时不用

如果 $\mu$ 已知，估计方差用

$$
\frac1n\sum (X_i-\mu)^2
$$

就是无偏的。

#### 最大似然估计常不用

正态总体方差的最大似然估计是

$$
\hat\sigma^2_{MLE}=\frac1n\sum (X_i-\bar X)^2
$$

它有偏，但一致。

#### 矩估计常自然得到 \(n\)

矩估计匹配的是样本原点矩和理论原点矩，常出现

$$
\frac1n\sum X_i^k
$$

因此也常得到分母 $n$。

---

### 6. 一句话总结

$n-1$ 修正常见于：

$$
\text{用同一批样本估计均值后，再用残差估计方差。}
$$

它本质上是自由度修正。

普通样本方差无偏性只需要 iid 且方差存在；而

$$
\frac{(n-1)S^2}{\sigma^2}\sim \chi^2(n-1)
$$

这个卡方结论还需要正态分布。

## 哪些分布可以看作 Gamma 分布的特例

这里采用 rate 参数记法：

$$
X\sim Gamma(\alpha,\lambda)
$$

密度为

$$
f(x)=\frac{\lambda^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\lambda x},
\qquad x>0
$$

期望和方差是

$$
E(X)=\frac{\alpha}{\lambda}
$$

$$
D(X)=\frac{\alpha}{\lambda^2}
$$

如果用 scale 参数 $\beta=1/\lambda$，则

$$
E(X)=\alpha\beta
$$

$$
D(X)=\alpha\beta^2
$$

---

### 1. 指数分布是 Gamma 特例

指数分布

$$
X\sim Exp(\lambda)
$$

等价于

$$
X\sim Gamma(1,\lambda)
$$

所以

$$
E(X)=\frac1\lambda
$$

$$
D(X)=\frac1{\lambda^2}
$$

---

### 2. Erlang 分布是 Gamma 特例

当 Gamma 分布的形状参数是正整数 $k$ 时：

$$
X\sim Gamma(k,\lambda)
$$

称为 Erlang 分布。

它可以看作 $k$ 个独立同参数指数变量的和：

$$
X=X_1+
\cdots+X_k,
\qquad
X_i\sim Exp(\lambda)
$$

所以

$$
X\sim Gamma(k,\lambda)
$$

---

### 3. 卡方分布是 Gamma 特例

若

$$
X\sim \chi^2(n)
$$

则在 rate 记法下：

$$
X\sim Gamma\left(\frac n2,\frac12\right)
$$

因此

$$
E(X)=\frac{n/2}{1/2}=n
$$

$$
D(X)=\frac{n/2}{(1/2)^2}=2n
$$

如果用 scale 记法，则写成：

$$
X\sim Gamma\left(\frac n2,2\right)
$$

---

### 4. Gamma 可加性

如果

$$
X\sim Gamma(\alpha_1,\lambda)
$$

$$
Y\sim Gamma(\alpha_2,\lambda)
$$

独立，并且 rate 参数相同，则

$$
X+Y\sim Gamma(\alpha_1+
\alpha_2,
\lambda)
$$

所以：

- 指数变量同 rate 相加得到 Gamma；
- 卡方变量相加仍是卡方；
- 同 rate 的 Gamma 相加仍是 Gamma。

---

### 5. 是否只背 Gamma 公式就行？

可以把 Gamma 公式作为母公式，但要非常注意参数化。

如果用 rate 记法：

$$
Gamma(\alpha,
\lambda):
\qquad
E=\frac{\alpha}{\lambda},
\quad
D=\frac{\alpha}{\lambda^2}
$$

如果用 scale 记法：

$$
Gamma(\alpha,
\beta):
\qquad
E=\alpha\beta,
\quad
D=\alpha\beta^2
$$

很多教材对 Gamma 第二个参数到底是 rate 还是 scale 不统一。

所以不能只机械背“第二个参数怎么放”，必须先看密度里是

$$
e^{-\lambda x}
$$

还是

$$
e^{-x/\beta}
$$

---

### 6. 总结表

| 分布 | Gamma 表示，rate 记法 | 期望 | 方差 |
|---|---|---|---|
| $Exp(\lambda)$ | $Gamma(1,\lambda)$ | $1/\lambda$ | $1/\lambda^2$ |
| $Erlang(k,\lambda)$ | $Gamma(k,\lambda)$ | $k/\lambda$ | $k/\lambda^2$ |
| $\chi^2(n)$ | $Gamma(n/2,1/2)$ | $n$ | $2n$ |

一句话：指数、Erlang、卡方都可以看作 Gamma 分布的特例；背 Gamma 的期望方差很有用，但必须确认使用的是 rate 参数还是 scale 参数。

## t 分布和 F 分布与 Gamma/卡方的关系，以及期望方差为什么奇怪

### 1. t 分布和 F 分布不是 Gamma 的子集

Gamma 分布、指数分布、卡方分布都是定义在正半轴上的分布。

而 t 分布定义在整个实数轴：

$$
T\in(-\infty,
\infty)
$$

所以 t 分布不可能是 Gamma 分布的子集。

F 分布虽然也定义在正半轴：

$$
F>0
$$

但它是两个独立卡方变量的比值，不是一个 Gamma 变量本身，所以一般也不是 Gamma 分布。

---

### 2. 它们是由卡方组合出来的分布

卡方分布是 Gamma 特例：

$$
\chi^2(n)=Gamma\left(\frac n2,\frac12\right)
$$

而 t 分布和 F 分布都是在卡方基础上构造出来的。

#### t 分布

若

$$
Z\sim N(0,1)
$$

$$
U\sim \chi^2(\nu)
$$

且 $Z,U$ 独立，则

$$
T=\frac{Z}{\sqrt{U/\nu}}
\sim t(\nu)
$$

也就是说：

$$
\text{t 分布}=
rac{\text{标准正态}}{\sqrt{\text{独立卡方}/\text{自由度}}}
$$

#### F 分布

若

$$
U_1\sim \chi^2(\nu_1),
\qquad
U_2\sim \chi^2(\nu_2)
$$

且独立，则

$$
F=\frac{U_1/\nu_1}{U_2/\nu_2}
\sim F(\nu_1,
\nu_2)
$$

也就是说：

$$
\text{F 分布}=
rac{\text{方差估计量 1}}{\text{方差估计量 2}}
$$

---

### 3. 为什么 t 分布的期望方差奇怪

$t(\nu)$ 的定义是

$$
T=\frac{Z}{\sqrt{U/\nu}}
$$

分母是随机的。

当 $U$ 偶尔很小时，分母很小，$T$ 的绝对值会被放得很大。

所以 t 分布有厚尾。

这导致低自由度时某些矩不存在。

结论：

$$
E(T)=0,\qquad \nu>1
$$

$$
D(T)=\frac{\nu}{\nu-2},
\qquad \nu>2
$$

如果 $\nu\le1$，期望不存在。

如果 $1<\nu\le2$，期望存在但方差不存在。

直觉：自由度小的时候，分母的波动太大，尾部太厚，导致平均平方发散。

当

$$
\nu\to\infty
$$

时，

$$
U/\nu\to 1
$$

于是

$$
T\approx Z
$$

所以

$$
t(\nu)\to N(0,1)
$$

并且

$$
D(T)=\frac{\nu}{\nu-2}\to 1
$$

---

### 4. 为什么 F 分布的期望方差更怪

F 分布是比值：

$$
F=\frac{U_1/\nu_1}{U_2/\nu_2}
$$

问题主要来自分母。

如果 $U_2$ 偶尔很小，那么整个比值会非常大。

这会造成很长的右尾。

所以 F 分布的期望、方差存在条件依赖分母自由度 $\nu_2$。

期望：

$$
E(F)=\frac{\nu_2}{\nu_2-2},
\qquad
\nu_2>2
$$

方差：

$$
D(F)=
\frac{2\nu_2^2(\nu_1+
\nu_2-2)}{\nu_1(\nu_2-2)^2(\nu_2-4)},
\qquad
\nu_2>4
$$

如果 $\nu_2\le2$，期望不存在。

如果 $2<\nu_2\le4$，期望存在但方差不存在。

直觉：分母自由度越小，分母越容易接近 0，比值越容易爆大。

---

### 5. t 和 F 的关系

如果

$$
T\sim t(\nu)
$$

则

$$
T^2\sim F(1,
\nu)
$$

因为

$$
T^2=
rac{Z^2}{U/\nu}
$$

而

$$
Z^2\sim \chi^2(1)
$$

所以

$$
T^2=
rac{\chi^2(1)/1}{\chi^2(\nu)/\nu}
\sim F(1,
\nu)
$$

---

### 6. 类比总结

| 分布 | 来源 | 直觉 |
|---|---|---|
| Gamma | 指数型等待时间/正半轴连续量 | 正变量累加 |
| Chi-square | 标准正态平方和 | 平方能量 |
| t | 正态除以随机标准差 | 均值估计中方差未知 |
| F | 两个独立方差估计的比 | 比较方差大小 |

所以 t 和 F 不是 Gamma 子集，但它们都建立在卡方上，而卡方是 Gamma 特例。

---

### 7. 记忆方式

t 分布：

$$
\frac{N(0,1)}{\sqrt{\chi^2(\nu)/\nu}}
$$

F 分布：

$$
\frac{\chi^2(\nu_1)/\nu_1}{\chi^2(\nu_2)/\nu_2}
$$

记住它们是“除以随机量”的分布，所以尾部会变厚，期望方差公式才会比 Gamma/正态看起来更怪。

## Student t 分布有什么用，分子分母代表什么

### 1. t 分布解决的问题

Student t 分布主要用于：

$$
\text{总体方差未知时，对正态总体均值做推断。}
$$

如果总体是

$$
X\sim N(\mu,
\sigma^2)
$$

我们想估计或检验均值 $\mu$。

如果总体标准差 $\sigma$ 已知，那么

$$
Z=\frac{\bar X-\mu}{\sigma/\sqrt n}
\sim N(0,1)
$$

但实际中 $\sigma$ 通常未知，只能用样本标准差 $S$ 替代。

于是得到

$$
T=\frac{\bar X-\mu}{S/\sqrt n}
$$

这个量不再服从标准正态，而是服从 t 分布：

$$
T\sim t(n-1)
$$

---

### 2. t 分布的标准定义

若

$$
Z\sim N(0,1)
$$

$$
U\sim \chi^2(\nu)
$$

并且 $Z,U$ 独立，则

$$
T=\frac{Z}{\sqrt{U/\nu}}
\sim t(\nu)
$$

这里 $\nu$ 是自由度。

---

### 3. 分子代表什么

在均值推断中，分子来自样本均值和真实均值的偏差：

$$
\bar X-\mu
$$

标准化后：

$$
\frac{\bar X-\mu}{\sigma/\sqrt n}
\sim N(0,1)
$$

所以 t 分布定义里的分子

$$
Z
$$

代表：

$$
\text{样本均值相对真实均值的标准化偏差。}
$$

也就是“均值估计误差有多大”。

---

### 4. 分母代表什么

分母是

$$
\sqrt{U/\nu}
$$

其中

$$
U\sim \chi^2(\nu)
$$

在样本均值推断里，它来自样本方差：

$$
\frac{(n-1)S^2}{\sigma^2}
\sim \chi^2(n-1)
$$

令

$$
U=\frac{(n-1)S^2}{\sigma^2}
$$

自由度

$$
\nu=n-1
$$

那么

$$
\sqrt{U/\nu}
=
\sqrt{\frac{(n-1)S^2/\sigma^2}{n-1}}
=
\frac{S}{\sigma}
$$

因此 t 统计量可以写成

$$
\frac{Z}{S/\sigma}
$$

它等于

$$
\frac{(\bar X-\mu)/(\sigma/\sqrt n)}{S/\sigma}
=
\frac{\bar X-\mu}{S/\sqrt n}
$$

所以分母代表：

$$
\text{用样本估计出来的标准差相对于真实标准差的随机误差。}
$$

---

### 5. 为什么 t 分布比正态尾巴厚

如果 $\sigma$ 已知，只需要用正态：

$$
\frac{\bar X-\mu}{\sigma/\sqrt n}
\sim N(0,1)
$$

但如果 $\sigma$ 未知，用 $S$ 替代，分母也变成随机的。

当 $S$ 偶尔偏小时，

$$
\frac{\bar X-\mu}{S/\sqrt n}
$$

会被放大，产生更大的极端值。

所以 t 分布比标准正态尾巴更厚。

自由度越大，$S$ 越稳定，t 分布越接近正态。

---

### 6. t 分布的主要用途

#### 均值的置信区间

当总体近似正态、方差未知时：

$$
\mu\in
\bar X\pm t_{\alpha/2}(n-1)\frac{S}{\sqrt n}
$$

#### 单样本 t 检验

检验

$$
H_0:\mu=\mu_0
$$

统计量：

$$
T=\frac{\bar X-\mu_0}{S/\sqrt n}
\sim t(n-1)
$$

#### 两样本 t 检验

用于比较两个总体均值是否相等。

#### 回归系数显著性检验

线性回归中，每个回归系数的显著性常用 t 检验。

---

### 7. 一句话总结

Student t 分布的核心用途是：

$$
\text{当总体方差未知时，用样本标准差替代真实标准差后，均值标准化误差的分布。}
$$

分子表示均值估计误差，分母表示样本方差估计带来的随机尺度修正。

## \(x/\sqrt{\sum x_i^2/n}\) 表示什么

考虑式子

$$
\frac{x}{\sqrt{\frac1n\sum_{i=1}^n x_i^2}}
$$

分母是样本的均方根，也叫 RMS：

$$
RMS=\sqrt{\frac1n\sum_{i=1}^n x_i^2}
$$

所以整个式子是：

$$
\frac{x}{RMS}
$$

意思是：

$$
\text{把 }x\text{ 按样本整体能量尺度归一化。}
$$

---

### 1. 分母估计的是什么

样本二阶原点矩是

$$
\frac1n\sum_{i=1}^n X_i^2
$$

它估计的是

$$
E(X^2)
$$

因此

$$
\sqrt{\frac1n\sum X_i^2}
$$

估计的是

$$
\sqrt{E(X^2)}
$$

这个量是随机变量的 RMS 尺度。

---

### 2. 和标准差有什么区别

标准差是

$$
\sigma=\sqrt{E[(X-\mu)^2]}
$$

而 RMS 是

$$
\sqrt{E(X^2)}
$$

两者关系为

$$
E(X^2)=D(X)+[E(X)]^2
$$

也就是

$$
RMS^2=\sigma^2+
\mu^2
$$

所以只有当

$$
\mu=0
$$

时，RMS 才等于标准差。

如果总体均值为 0，比如

$$
X\sim N(0,\sigma^2)
$$

那么

$$
E(X^2)=\sigma^2
$$

这时

$$
\sqrt{\frac1n\sum X_i^2}
$$

可以看作对 $\sigma$ 的估计。

---

### 3. 这个式子为什么会出现

它常出现在归一化、标准化、尺度消除中。

原始 $x$ 有单位，比如电压、电流、误差、样本值。

除以 RMS 后：

$$
\frac{x}{RMS}
$$

变成无量纲数，表示：

$$
\text{这个 }x\text{ 大约是整体 RMS 尺度的多少倍。}
$$

如果结果是 2，表示 $x$ 的大小大约是 RMS 的 2 倍。

---

### 4. 它和 t 统计量的区别

t 统计量通常是

$$
T=\frac{\bar X-\mu}{S/\sqrt n}
$$

其中

$$
S^2=\frac1{n-1}\sum (X_i-\bar X)^2
$$

它用的是围绕样本均值的样本方差。

而

$$
\frac{x}{\sqrt{\frac1n\sum x_i^2}}
$$

用的是二阶原点矩，没有减去均值。

所以它一般不是标准 t 统计量。

只有在均值为 0、并且语境是在用 RMS 估计尺度时，才和“用样本估计标准差后做标准化”的思想类似。

---

### 5. 一句话总结

$$
\frac{x}{\sqrt{\sum x_i^2/n}}
$$

表示把 $x$ 除以样本 RMS 尺度。

它衡量 $x$ 相对于样本整体平方平均大小的倍数。

如果总体均值为 0，分母可以看作标准差尺度估计；如果总体均值不为 0，它估计的是 RMS，不是标准差。

## 例题：由两个样本均值和后 3 个样本方差构造的 t 分布

题目：设

$$
X_1,
\dots,
X_9
$$

是来自正态总体

$$
N(\mu,
\sigma^2)
$$

的样本。令

$$
Y_1=\frac16\sum_{i=1}^6 X_i
$$

$$
Y_2=\frac13\sum_{i=7}^9 X_i
$$

$$
S^2=\frac12\sum_{i=7}^9 (X_i-Y_2)^2
$$

并定义

$$
Z=\frac{Y_1-Y_2}{S}
$$

求

$$
P(Z>1.33)
$$

---

### 1. 先看分子

因为 $Y_1$ 是前 6 个样本均值：

$$
Y_1\sim N\left(\mu,
\frac{\sigma^2}{6}\right)
$$

$Y_2$ 是后 3 个样本均值：

$$
Y_2\sim N\left(\mu,
\frac{\sigma^2}{3}\right)
$$

而前 6 个样本和后 3 个样本独立，所以

$$
Y_1-Y_2\sim N\left(0,
\frac{\sigma^2}{6}+\frac{\sigma^2}{3}\right)
$$

即

$$
Y_1-Y_2\sim N\left(0,
\frac{\sigma^2}{2}\right)
$$

所以

$$
\frac{Y_1-Y_2}{\sigma/\sqrt2}\sim N(0,1)
$$

---

### 2. 再看分母

$S^2$ 是后 3 个样本的无偏样本方差：

$$
S^2=\frac1{3-1}\sum_{i=7}^9 (X_i-Y_2)^2
$$

因此

$$
\frac{(3-1)S^2}{\sigma^2}\sim \chi^2(3-1)
$$

也就是

$$
\frac{2S^2}{\sigma^2}\sim \chi^2(2)
$$

记

$$
U=\frac{2S^2}{\sigma^2}
$$

则

$$
U\sim \chi^2(2)
$$

并且在正态样本中，样本均值 $Y_2$ 与样本方差 $S^2$ 独立；同时 $Y_1$ 来自前 6 个样本，也与 $S^2$ 独立。所以

$$
Y_1-Y_2
$$

与

$$
S^2
$$

独立。

---

### 3. 构造 t 分布

标准 t 分布形式是

$$
T=\frac{N(0,1)}{\sqrt{\chi^2(\nu)/\nu}}
$$

这里

$$
\frac{Y_1-Y_2}{\sigma/\sqrt2}\sim N(0,1)
$$

并且

$$
\sqrt{\frac{U}{2}}
=
\sqrt{\frac{2S^2/\sigma^2}{2}}
=
\frac{S}{\sigma}
$$

所以

$$
T=
\frac{\dfrac{Y_1-Y_2}{\sigma/\sqrt2}}{S/\sigma}
=
\sqrt2\frac{Y_1-Y_2}{S}
$$

即

$$
T=\sqrt2 Z
$$

因此

$$
\sqrt2 Z\sim t(2)
$$

注意：不是 $Z\sim t(2)$，而是 $\sqrt2Z\sim t(2)$。

---

### 4. 计算概率

$$
P(Z>1.33)
=
P(\sqrt2 Z>1.33\sqrt2)
$$

因为

$$
\sqrt2 Z\sim t(2)
$$

所以

$$
P(Z>1.33)=P(t(2)>1.33\sqrt2)
$$

计算

$$
1.33\sqrt2\approx1.881
$$

查 t 分布表或用 $t(2)$ 的尾概率公式，可得

$$
P(t(2)>1.881)\approx0.100
$$

所以

$$
\boxed{P(Z>1.33)\approx0.10}
$$

---

### 5. 常见错误

容易误认为

$$
Z\sim t(2)
$$

但这是错的。

因为分子

$$
Y_1-Y_2
$$

的标准差是

$$
\sigma/\sqrt2
$$

而分母 $S$ 估计的是

$$
\sigma
$$

不是

$$
\sigma/\sqrt2
$$

所以必须多一个因子

$$
\sqrt2
$$

即

$$
\sqrt2Z\sim t(2)
$$

## 随机变量记号、事件 \(X=k\) 与似然函数乘积/求和

### 1. 大写 \(X\) 是随机变量

随机变量 $X$ 本质上是一个函数：

$$
X:\Omega\to \mathbb R
$$

它把随机试验的结果映射成一个数。

所以 $X$ 可以参与代数运算，例如：

$$
X^2,
\qquad
2X+1,
\qquad
\frac{X-\mu}{\sigma}
$$

这些仍然是随机变量。

例如如果 $X$ 表示一次试验结果，那么

$$
Y=2X+1
$$

也是随机变量。

---

### 2. \(X=k\) 是事件

写

$$
X=k
$$

不是普通代数等式，而是在说一个事件：

$$
\{\omega\in\Omega:X(\omega)=k\}
$$

也就是：随机变量 $X$ 取到数值 $k$ 的那些样本点组成的事件。

所以

$$
P(X=k)
$$

表示 $X$ 取值为 $k$ 的概率。

对于离散型随机变量，可以列分布列：

$$
P(X=k)=p_k
$$

---

### 3. 大写 \(X\) 和小写 \(x\) 的区别

大写：

$$
X
$$

表示抽样前的随机变量。

小写：

$$
x
$$

表示一次抽样后的具体观测值。

例如抽样前：

$$
X\sim Bernoulli(p)
$$

抽样后可能观察到：

$$
x=1
$$

多个样本时：

$$
X_1,
\dots,X_n
$$

是随机变量；

$$
x_1,
\dots,x_n
$$

是已经观测到的具体数据。

---

### 4. 可以把随机变量直接带入公式吗？

可以。

例如

$$
E(X)
$$

表示 $X$ 的期望。

$$
E(X^2)
$$

表示 $X^2$ 的期望。

$$
\bar X=\frac1n\sum_{i=1}^n X_i
$$

表示样本均值，它本身也是随机变量。

$$
S^2=\frac1{n-1}\sum_{i=1}^n (X_i-\bar X)^2
$$

表示样本方差，它也是随机变量。

一旦观测到具体数据，才变成具体数值：

$$
\bar x=\frac1n\sum_{i=1}^n x_i
$$

---

### 5. 似然函数为什么是累乘

假设样本独立同分布，单个样本的概率或密度为

$$
f(x;\theta)
$$

观测到样本

$$
x_1,
\dots,x_n
$$

因为样本独立，所以联合概率/联合密度是乘积：

$$
f(x_1,
\dots,x_n;\theta)
=
\prod_{i=1}^n f(x_i;\theta)
$$

把数据固定，把参数 $\theta$ 当变量，就得到似然函数：

$$
L(\theta)=\prod_{i=1}^n f(x_i;\theta)
$$

所以似然函数本身是累乘。

原因是独立事件同时发生的概率要相乘。

---

### 6. 为什么有时看到求和

求和出现在线性化后的对数似然。

对数似然定义为

$$
\ell(\theta)=\ln L(\theta)
$$

因为

$$
L(\theta)=\prod_{i=1}^n f(x_i;\theta)
$$

所以

$$
\ell(\theta)=\ln\prod_{i=1}^n f(x_i;\theta)
$$

利用

$$
\ln(ab)=\ln a+
\ln b
$$

得到

$$
\ell(\theta)=\sum_{i=1}^n \ln f(x_i;\theta)
$$

所以：

- 似然函数 $L$ 是乘积；
- 对数似然函数 $\ell$ 是求和。

最大化二者得到同一个参数，因为对数函数单调递增。

---

### 7. 离散例子

若

$$
P(X=1)=\theta^2,
\quad
P(X=2)=2\theta(1-\theta),
\quad
P(X=3)=(1-\theta)^2
$$

观测到

$$
x_1=1,
\quad
x_2=2,
\quad
x_3=1
$$

则似然函数是

$$
L(\theta)=P(X=1)P(X=2)P(X=1)
$$

所以

$$
L(\theta)=\theta^2\cdot 2\theta(1-\theta)\cdot \theta^2
$$

即

$$
L(\theta)=2\theta^5(1-\theta)
$$

对数似然是

$$
\ell(\theta)=\ln2+5\ln\theta+
\ln(1-\theta)
$$

---

### 8. 一句话总结

$X=k$ 表示一个事件，意思是随机变量 $X$ 取值为 $k$。

随机变量可以直接放进公式形成新的随机变量。

最大似然中，独立样本的联合概率/密度是乘积，所以似然函数 $L$ 是累乘；取对数后才变成求和。

---

## 最大似然例子：由似然函数求参数估计

前面得到观测样本

$$
x_1=1,
\quad
x_2=2,
\quad
x_3=1
$$

对应的似然函数为

$$
L(\theta)=2\theta^5(1-\theta),
\quad 0<\theta<1.
$$

为了求最大似然估计，可以最大化对数似然：

$$
\ell(\theta)=\ln L(\theta)
=\ln 2+5\ln\theta+\ln(1-\theta).
$$

对 $\theta$ 求导：

$$
\ell'(\theta)
=
\frac{5}{\theta}-\frac{1}{1-\theta}.
$$

令导数为零：

$$
\frac{5}{\theta}-\frac{1}{1-\theta}=0.
$$

于是

$$
\frac{5}{\theta}=\frac{1}{1-\theta}.
$$

交叉相乘：

$$
5(1-\theta)=\theta.
$$

所以

$$
5-5\theta=\theta,
$$

即

$$
6\theta=5.
$$

因此

$$
\hat\theta_{MLE}=\frac{5}{6}.
$$

为了确认这是最大值，可以看二阶导数：

$$
\ell''(\theta)
=
-
\frac{5}{\theta^2}
-
\frac{1}{(1-\theta)^2}.
$$

由于在 $0<\theta<1$ 内恒有

$$
\ell''(\theta)<0,
$$

所以 $\ell(\theta)$ 是严格凹函数，驻点就是最大值点。

因此这个例子的最大似然估计是

$$
\boxed{\hat\theta_{MLE}=\frac{5}{6}}.
$$

一句话理解：观测到的数据中，$X=1$ 出现了两次，$X=2$ 出现了一次，而 $P(X=1)=\theta^2$ 强烈偏向较大的 $\theta$，所以估计值 $5/6$ 比较靠近 $1$。

