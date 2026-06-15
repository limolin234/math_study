# 常用积分识别表

这份表的目的不是背大全，而是训练看到积分时快速判断它属于哪一类、该用什么工具。重点服务后续电路理论、概率论、电磁学和信号相关计算。

---

## 1. 幂函数、指数函数、对数函数

### 幂函数

当 $n\ne -1$：

$$
\int x^n\,dx=\frac{x^{n+1}}{n+1}+C
$$

特殊情形：

$$
\int \frac{1}{x}\,dx=\ln|x|+C
$$

识别：

- 多项式积分直接逐项积分。
- 出现 $1/x$ 时产生 $\ln|x|$。
- 有理函数拆分后常常会出现 $1/(x-a)$，它也产生对数。

### 指数函数

$$
\int e^{ax}\,dx=\frac{1}{a}e^{ax}+C\qquad(a\ne 0)
$$

$$
\int_0^\infty e^{-ax}\,dx=\frac{1}{a}\qquad(a>0)
$$

$$
\int_0^\infty x^n e^{-ax}\,dx=\frac{\Gamma(n+1)}{a^{n+1}}
$$

若 $n$ 是非负整数：

$$
\int_0^\infty x^n e^{-ax}\,dx=\frac{n!}{a^{n+1}}
$$

识别：

- 电路一阶响应经常出现 $e^{-t/\tau}$。
- $\int_0^\infty e^{-t/\tau}\,dt=\tau$，可以理解成指数衰减的等效宽度。
- 概率论中指数分布、Gamma 分布都靠这类积分归一化。

---

## 2. 三角函数常用积分

### 基本积分

$$
\int \sin x\,dx=-\cos x+C
$$

$$
\int \cos x\,dx=\sin x+C
$$

$$
\int \sec^2 x\,dx=\tan x+C
$$

$$
\int \csc^2 x\,dx=-\cot x+C
$$

$$
\int \sec x\tan x\,dx=\sec x+C
$$

$$
\int \csc x\cot x\,dx=-\csc x+C
$$

### 平方降幂

$$
\sin^2 x=\frac{1-\cos 2x}{2}
$$

$$
\cos^2 x=\frac{1+\cos 2x}{2}
$$

因此：

$$
\int_0^{\pi/2}\sin^2 x\,dx=\int_0^{\pi/2}\cos^2 x\,dx=\frac{\pi}{4}
$$

识别：

- 偶次三角函数通常用降幂。
- 奇次三角函数通常拆一个导数因子，例如 $\sin^3x=\sin x(1-\cos^2x)$。
- 圆、球、极坐标、傅里叶平均中经常出现 $\sin^2$、$\cos^2$。

---

## 3. 反三角与二次式

### 无实根二次式

$$
\int \frac{dx}{x^2+a^2}=\frac{1}{a}\arctan\frac{x}{a}+C
$$

$$
\int \frac{dx}{(x-b)^2+a^2}=\frac{1}{a}\arctan\frac{x-b}{a}+C
$$

识别：

- 分母是正定二次式，最后常出 $\arctan$。
- 有理函数部分分式中，不可约二次因子对应 $\arctan$ 和 $\ln$ 的组合。

### 圆型平方根

$$
\int \frac{dx}{\sqrt{a^2-x^2}}=\arcsin\frac{x}{a}+C
$$

$$
\int \sqrt{a^2-x^2}\,dx
=\frac{x}{2}\sqrt{a^2-x^2}+\frac{a^2}{2}\arcsin\frac{x}{a}+C
$$

特别地：

$$
\int_0^1 \sqrt{1-x^2}\,dx=\frac{\pi}{4}
$$

识别：

- $a^2-x^2$ 对应圆。
- 常用换元 $x=a\sin\theta$。

---

## 4. 对数型与双曲结构

### 实根二次式

$$
\int \frac{dx}{x^2-a^2}
=\frac{1}{2a}\ln\left|\frac{x-a}{x+a}\right|+C
$$

$$
\int \frac{dx}{a^2-x^2}
=\frac{1}{2a}\ln\left|\frac{a+x}{a-x}\right|+C
$$

识别：

- 分母能分解成两个一次因子，通常产生对数。
- $a^2-x^2$ 也可以和 $\operatorname{artanh}$ 联系。

### 双曲函数关系

$$
\cosh^2 u-\sinh^2 u=1
$$

$$
\frac{d}{du}\sinh u=\cosh u,
\qquad
\frac{d}{du}\cosh u=\sinh u
$$

典型结构：

$$
\sqrt{x^2+a^2}\quad \text{可考虑 } x=a\sinh u
$$

$$
\sqrt{x^2-a^2}\quad \text{可考虑 } x=a\cosh u
$$

识别：

- 三角换元适合 $a^2-x^2$。
- 双曲换元适合 $x^2+a^2$、$x^2-a^2$。
- 实际工程计算中，很多双曲结果最终会写成对数。

---

## 5. 有理函数积分

一般形式：

$$
\int \frac{P(x)}{Q(x)}\,dx
$$

步骤：

1. 若分子次数不小于分母次数，先做多项式除法。
2. 分解分母 $Q(x)$。
3. 部分分式展开。
4. 一次因子产生 $\ln$。
5. 不可约二次因子产生 $\ln$ 与 $\arctan$。

常见基本块：

$$
\int \frac{dx}{x-a}=\ln|x-a|+C
$$

$$
\int \frac{dx}{(x-a)^n}
=\frac{(x-a)^{1-n}}{1-n}+C\qquad(n\ne 1)
$$

$$
\int \frac{Ax+B}{x^2+px+q}\,dx
$$

处理方法：把分子拆成“分母导数的一部分 + 剩余常数”：

$$
Ax+B=\alpha(2x+p)+\beta
$$

于是：

- $\alpha(2x+p)/(x^2+px+q)$ 给出 $\ln$；
- $\beta/(x^2+px+q)$ 配方后给出 $\arctan$ 或 $\ln$。

识别：

- 有理积分不要硬背表，先看能否部分分式。
- 看见“分母导数在分子里”，优先考虑 $u=Q(x)$。

---

## 6. Gamma 函数与 Beta 函数

### Gamma 函数

定义：

$$
\Gamma(s)=\int_0^\infty x^{s-1}e^{-x}\,dx\qquad(s>0)
$$

缩放形式：

$$
\int_0^\infty x^{s-1}e^{-\lambda x}\,dx
=\frac{\Gamma(s)}{\lambda^s}
\qquad(\lambda>0)
$$

常用值：

$$
\Gamma(n+1)=n!
$$

$$
\Gamma\left(\frac12\right)=\sqrt{\pi}
$$

$$
\Gamma\left(n+\frac12\right)
=\frac{(2n)!}{4^n n!}\sqrt{\pi}
$$

识别：

- $0$ 到 $\infty$。
- 幂函数乘指数衰减。
- 上限必须是 $\infty$ 才是完整 Gamma；有限上限通常是不完全 Gamma。

### Beta 函数

定义：

$$
B(a,b)=\int_0^1 x^{a-1}(1-x)^{b-1}\,dx
\qquad(a,b>0)
$$

与 Gamma 的关系：

$$
B(a,b)=\frac{\Gamma(a)\Gamma(b)}{\Gamma(a+b)}
$$

识别：

- 积分区间是 $0$ 到 $1$。
- integrand 形如 $x^m(1-x)^n$。
- 概率论里 Beta 分布、Dirichlet 分布会大量出现。

例子：

$$
\int_0^1 x^2(1-x)^3\,dx=B(3,4)=\frac{2!3!}{6!}=\frac{1}{60}
$$

二维单纯形版本：

$$
\int_{x\ge0,y\ge0,x+y\le1}x^a y^b\,dxdy
=\frac{\Gamma(a+1)\Gamma(b+1)}{\Gamma(a+b+3)}
$$

例如：

$$
\iint_D xy\,dA=\frac{1}{24}
$$

---

## 7. 高斯积分、误差函数、不完全 Gamma

完整高斯积分：

$$
\int_{-\infty}^{\infty}e^{-x^2}\,dx=\sqrt{\pi}
$$

半轴：

$$
\int_0^{\infty}e^{-x^2}\,dx=\frac{\sqrt{\pi}}{2}
$$

缩放：

$$
\int_{-\infty}^{\infty}e^{-ax^2}\,dx=\sqrt{\frac{\pi}{a}}\qquad(a>0)
$$

有限上限：

$$
\int_0^1 e^{-x^2}\,dx=\frac{\sqrt{\pi}}{2}\operatorname{erf}(1)
$$

也可令 $t=x^2$：

$$
\int_0^1 e^{-x^2}\,dx
=\frac12\int_0^1 t^{-1/2}e^{-t}\,dt
=\frac12\gamma\left(\frac12,1\right)
$$

识别：

- $e^{-x^2}$ 没有初等原函数。
- 积分上限是 $\infty$ 时，能用完整 Gamma/高斯积分。
- 积分上限有限时，通常用误差函数或不完全 Gamma。

---

## 8. 参数积分

基本思想：把难积分看成某个参数函数的导数。

例子：

$$
F(a)=\int_0^\infty e^{-ax}\,dx=\frac{1}{a}\qquad(a>0)
$$

对 $a$ 求导：

$$
F'(a)=\int_0^\infty -xe^{-ax}\,dx=-\frac{1}{a^2}
$$

所以：

$$
\int_0^\infty xe^{-ax}\,dx=\frac{1}{a^2}
$$

继续求导可以得到：

$$
\int_0^\infty x^n e^{-ax}\,dx=\frac{n!}{a^{n+1}}
$$

识别：

- 积分里有 $x^n e^{-ax}$，可以对参数 $a$ 求导生成 $x^n$。
- 严格交换求导和积分通常需要一致收敛或支配收敛；工程计算中先掌握操作结构。

---

## 9. 二重积分与极坐标

极坐标：

$$
x=r\cos\theta,
\qquad
 y=r\sin\theta,
\qquad
 dA=r\,dr\,d\theta
$$

关键点：

$$
\left|\frac{\partial(x,y)}{\partial(r,\theta)}\right|=r
$$

常见识别：

- 区域是圆、扇形、环形，优先极坐标。
- 被积函数含 $x^2+y^2$，优先极坐标。
- 区域由直线、抛物线、简单上下界给出，通常直角坐标更自然。

典型例子：

$$
\iint_{x^2+y^2\le R^2}(x^2+y^2)\,dA
=\int_0^{2\pi}\int_0^R r^2\cdot r\,dr\,d\theta
=\frac{\pi R^4}{2}
$$

环形对数积分：

$$
\iint_{a^2\le x^2+y^2\le b^2}\frac{1}{x^2+y^2}\,dA
=2\pi\ln\frac{b}{a}
$$

识别：

- 面积积分是积分 $1$。
- 若被积函数是 $r^2$，结果不等于面积，会更偏重外圈。
- 电磁场里 $1/r$、$1/r^2$、$\ln r$ 类型经常通过极坐标出现。

---

## 10. 电路理论最常用积分

### RC/RL 一阶指数

$$
\int e^{-t/\tau}\,dt=-\tau e^{-t/\tau}+C
$$

$$
\int_0^t e^{-s/\tau}\,ds=\tau(1-e^{-t/\tau})
$$

$$
\int_0^\infty e^{-t/\tau}\,dt=\tau
$$

识别：

- 看到 $e^{-t/RC}$，时间常数是 $RC$。
- 看到 $e^{-t/(L/R)}$，时间常数是 $L/R$。

### 电容、电感关系

电容：

$$
i(t)=C\frac{dv(t)}{dt},
\qquad
v(t)=v(0)+\frac{1}{C}\int_0^t i(s)\,ds
$$

电感：

$$
v(t)=L\frac{di(t)}{dt},
\qquad
i(t)=i(0)+\frac{1}{L}\int_0^t v(s)\,ds
$$

若

$$
i(t)=I_0e^{-t/\tau},\qquad v(0)=0
$$

则

$$
v(t)=\frac{I_0\tau}{C}(1-e^{-t/\tau})
$$

---

## 11. 最小记忆清单

真正需要长期熟悉的是这些模式：

1. $1/x \rightarrow \ln|x|$
2. $1/(x^2+a^2) \rightarrow \arctan$
3. $1/\sqrt{a^2-x^2} \rightarrow \arcsin$
4. $e^{-t/\tau}$ 的积分给出 $\tau$
5. $x^n e^{-\lambda x}$ 是 Gamma 型
6. $x^a(1-x)^b$ 是 Beta 型
7. $e^{-x^2}$ 是高斯/误差函数型
8. 圆域、环域、$x^2+y^2$ 优先极坐标
9. 有理函数先部分分式，不要硬背
10. 参数积分可以通过求导生成 $x^n$
