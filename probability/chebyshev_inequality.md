# 切比雪夫不等式

切比雪夫不等式用于在不知道具体分布的情况下，用方差控制随机变量偏离均值的概率。

## 结论

设随机变量 \(X\) 的期望和方差存在：

\[
E(X)=\mu,
\qquad
D(X)=\operatorname{Var}(X)=\sigma^2.
\]

则对任意 \(\varepsilon>0\)，

\[
P(|X-\mu|\ge \varepsilon)
\le
\frac{\sigma^2}{\varepsilon^2}.
\]

也可以写成标准差形式：对任意 \(k>0\)，

\[
P(|X-\mu|\ge k\sigma)
\le
\frac{1}{k^2}.
\]

## 推导

马尔可夫不等式说：若 \(Z\ge 0\)，\(a>0\)，则

\[
P(Z\ge a)
\le
\frac{E(Z)}{a}.
\]

令

\[
Z=(X-\mu)^2.
\]

则

\[
|X-\mu|\ge \varepsilon
\iff
(X-\mu)^2\ge \varepsilon^2.
\]

所以

\[
P(|X-\mu|\ge \varepsilon)
=
P((X-\mu)^2\ge \varepsilon^2).
\]

由马尔可夫不等式，

\[
P((X-\mu)^2\ge \varepsilon^2)
\le
\frac{E[(X-\mu)^2]}{\varepsilon^2}.
\]

因为

\[
E[(X-\mu)^2]=D(X)=\sigma^2,
\]

得到

\[
P(|X-\mu|\ge \varepsilon)
\le
\frac{D(X)}{\varepsilon^2}.
\]

## 例子

若

\[
E(X)=100,
\qquad
D(X)=25,
\]

则

\[
P(|X-100|\ge 20)
\le
\frac{25}{20^2}
=
\frac{1}{16}.
\]

也就是说，偏离均值至少 \(20\) 的概率最多为 \(6.25\%\)。

## 用途

切比雪夫不等式的优点是条件很弱：不需要知道随机变量服从什么分布，只需要方差存在。

它常用于：

1. 估计随机变量远离均值的概率上界；
2. 用方差描述集中程度；
3. 证明大数定律。

例如独立同分布随机变量 \(X_1,\dots,X_n\)，满足

\[
E(X_i)=\mu,
\qquad
D(X_i)=\sigma^2.
\]

样本均值

\[
\overline X_n=\frac{1}{n}\sum_{i=1}^n X_i
\]

满足

\[
E(\overline X_n)=\mu,
\qquad
D(\overline X_n)=\frac{\sigma^2}{n}.
\]

因此

\[
P(|\overline X_n-\mu|\ge \varepsilon)
\le
\frac{\sigma^2}{n\varepsilon^2}.
\]

当 \(n\to\infty\) 时，右边趋于 \(0\)，所以样本均值越来越接近期望。

## 最小记忆

\[
P(|X-\mu|\ge \varepsilon)
\le
\frac{D(X)}{\varepsilon^2}.
\]

切比雪夫不等式可以理解为：方差越小，随机变量越不容易远离均值。
