# 积分、二次式、三角/双曲/复数结构总结

## 0. 总原则

很多积分表公式不是孤立记忆，而是来自同一个核心结构：

\[
\boxed{\text{二次式/平方根结构}+\text{指数群结构}+\text{复根结构}}
\]

常见对象：

\[
x^2+a^2,\quad a^2-x^2,\quad x^2-a^2,\quad ax^2+bx+c
\]

分别对应：

- 无实根二次式：\(\arctan\)
- 有实根二次式：\(\ln\)、\(\operatorname{artanh}\)
- 圆型平方根：\(\arcsin\)
- 双曲型平方根：\(\operatorname{arsinh},\operatorname{arcosh},\ln\)
- 复根：通过复对数统一 \(\ln\) 与 \(\arctan\)

---

## 1. 第 3 题：对数 Poisson 核积分

题目形式：

\[
I(d)=\int_0^\pi \ln(1-2d\cos x+d^2)\,dx,\qquad |d|<1.
\]

结论：

\[
\boxed{I(d)=0}
\]

### 1.1 直接对参数求导法

令

\[
D=1-2d\cos x+d^2.
\]

则

\[
I'(d)=\int_0^\pi \frac{2d-2\cos x}{D}\,dx.
\]

关键恒等式：

\[
D+d^2-1=2d(d-\cos x).
\]

所以

\[
\frac{2d-2\cos x}{D}
=
\frac1d+\frac{d^2-1}{dD}.
\]

因此

\[
I'(d)
=
\frac{\pi}{d}
+
\frac{d^2-1}{d}
\int_0^\pi\frac{dx}{1-2d\cos x+d^2}.
\]

用标准积分：

\[
\int_0^\pi\frac{dx}{1-2d\cos x+d^2}
=
\frac{\pi}{1-d^2},
\qquad |d|<1.
\]

所以

\[
I'(d)=
\frac{\pi}{d}
+
\frac{d^2-1}{d}\frac{\pi}{1-d^2}
=0.
\]

因此 \(I(d)\) 为常数。取 \(d=0\)：

\[
I(0)=\int_0^\pi \ln1\,dx=0.
\]

所以：

\[
\boxed{I(d)=0}
\]

### 1.2 交换积分顺序写法：关键内层积分怎么算

也可以把对数写成对参数的积分。因为

\[
\frac{\partial}{\partial s}
\ln(1-2s\cos x+s^2)
=
\frac{2s-2\cos x}{1-2s\cos x+s^2},
\]

所以

\[
\ln(1-2d\cos x+d^2)-\ln1
=
\int_0^d
\frac{2s-2\cos x}{1-2s\cos x+s^2}\,ds.
\]

于是

\[
I(d)
=
\int_0^\pi\int_0^d
\frac{2s-2\cos x}{1-2s\cos x+s^2}\,ds\,dx.
\]

在 \(|d|<1\) 时，分母不为零，被积函数在矩形区域上连续，所以可以交换积分顺序：

\[
I(d)
=
\int_0^d
\left[
\int_0^\pi
\frac{2s-2\cos x}{1-2s\cos x+s^2}\,dx
\right]ds.
\]

关键是计算内层积分：

\[
J(s)=
\int_0^\pi
\frac{2s-2\cos x}{1-2s\cos x+s^2}\,dx.
\]

令

\[
D=1-2s\cos x+s^2.
\]

有恒等式：

\[
D+s^2-1=2s(s-\cos x).
\]

因此

\[
2(s-\cos x)=\frac{D+s^2-1}{s}.
\]

所以

\[
\frac{2s-2\cos x}{D}
=
\frac{1}{s}+\frac{s^2-1}{sD}.
\]

于是

\[
J(s)
=
\int_0^\pi \frac{dx}{s}
+
\frac{s^2-1}{s}
\int_0^\pi\frac{dx}{1-2s\cos x+s^2}.
\]

即

\[
J(s)
=
\frac{\pi}{s}
+
\frac{s^2-1}{s}K(s),
\]

其中

\[
K(s)=\int_0^\pi\frac{dx}{1-2s\cos x+s^2}.
\]

下面计算 \(K(s)\)。用万能代换

\[
t=\tan\frac{x}{2}.
\]

则

\[
\cos x=\frac{1-t^2}{1+t^2},
\qquad
 dx=\frac{2dt}{1+t^2}.
\]

当 \(x:0\to\pi\) 时，\(t:0\to\infty\)。分母变为

\[
1-2s\cos x+s^2
=
1-2s\frac{1-t^2}{1+t^2}+s^2.
\]

通分：

\[
1-2s\cos x+s^2
=
\frac{(1+s^2)(1+t^2)-2s(1-t^2)}{1+t^2}.
\]

展开分子：

\[
(1+s^2)(1+t^2)-2s(1-t^2)
=
(1-2s+s^2)+(1+2s+s^2)t^2.
\]

也就是

\[
1-2s\cos x+s^2
=
\frac{(1-s)^2+(1+s)^2t^2}{1+t^2}.
\]

所以

\[
K(s)
=
\int_0^\infty
\frac{1}{\frac{(1-s)^2+(1+s)^2t^2}{1+t^2}}
\frac{2dt}{1+t^2}.
\]

约掉 \(1+t^2\)：

\[
K(s)
=
2\int_0^\infty
\frac{dt}{(1-s)^2+(1+s)^2t^2}.
\]

用基础公式

\[
\int_0^\infty\frac{dt}{A+Bt^2}
=
\frac{\pi}{2\sqrt{AB}},
\qquad A,B>0.
\]

这里

\[
A=(1-s)^2,
\qquad
B=(1+s)^2.
\]

因为 \(|s|<1\)，所以

\[
\sqrt{AB}=(1-s)(1+s)=1-s^2.
\]

因此

\[
K(s)
=
2\cdot\frac{\pi}{2(1-s^2)}
=
\frac{\pi}{1-s^2}.
\]

代回 \(J(s)\)：

\[
J(s)
=
\frac{\pi}{s}
+
\frac{s^2-1}{s}\cdot\frac{\pi}{1-s^2}
=
\frac{\pi}{s}-\frac{\pi}{s}=0.
\]

所以

\[
I(d)
=
\int_0^d J(s)\,ds
=0.
\]

这个方法的重点不是对称性，而是：

\[
\boxed{
\text{先把 }\ln\text{ 写成参数积分，再交换积分顺序，最后用 }t=\tan\frac{x}{2}\text{ 算内层积分。}
}
\]

---

## 2. 第 4 题：对数二次三角积分

题目形式：

\[
F(a,b)=\int_0^{\pi/2}\ln(a^2\sin^2x+b^2\cos^2x)\,dx,
\qquad a,b>0.
\]

结论：

\[
\boxed{F(a,b)=\pi\ln\frac{a+b}{2}}
\]

### 2.1 用第 3 题处理

先把

\[
a^2\sin^2x+b^2\cos^2x
\]

写成第 3 题形式。

用

\[
\sin^2x=\frac{1-\cos2x}{2},
\qquad
\cos^2x=\frac{1+\cos2x}{2}.
\]

则

\[
a^2\sin^2x+b^2\cos^2x
=
\frac{a^2+b^2}{2}
+
\frac{b^2-a^2}{2}\cos2x.
\]

设

\[
d=\frac{a-b}{a+b},
\qquad |d|<1.
\]

有分解：

\[
a^2\sin^2x+b^2\cos^2x
=
\left(\frac{a+b}{2}\right)^2
(1-2d\cos2x+d^2).
\]

于是

\[
F(a,b)
=
\int_0^{\pi/2}
\ln\left[
\left(\frac{a+b}{2}\right)^2
(1-2d\cos2x+d^2)
\right]dx.
\]

拆开：

\[
F(a,b)
=
\pi\ln\frac{a+b}{2}
+
\int_0^{\pi/2}\ln(1-2d\cos2x+d^2)\,dx.
\]

令 \(u=2x\)，则

\[
\int_0^{\pi/2}\ln(1-2d\cos2x+d^2)\,dx
=
\frac12
\int_0^\pi
\ln(1-2d\cos u+d^2)\,du.
\]

由第 3 题，该项为 \(0\)。

所以：

\[
\boxed{F(a,b)=\pi\ln\frac{a+b}{2}.}
\]

### 2.2 参数求导法

设

\[
F(a,b)=\int_0^{\pi/2}\ln(a^2\sin^2x+b^2\cos^2x)\,dx.
\]

对 \(a\) 求偏导：

\[
F_a
=
\int_0^{\pi/2}
\frac{2a\sin^2x}{a^2\sin^2x+b^2\cos^2x}\,dx.
\]

令

\[
t=\tan x.
\]

则

\[
\sin^2x=\frac{t^2}{1+t^2},
\qquad
\cos^2x=\frac{1}{1+t^2},
\qquad
dx=\frac{dt}{1+t^2}.
\]

所以

\[
a^2\sin^2x+b^2\cos^2x
=
\frac{a^2t^2+b^2}{1+t^2}.
\]

因此

\[
F_a
=
\int_0^\infty
\frac{2at^2}{(a^2t^2+b^2)(1+t^2)}\,dt.
\]

注意：这里不是

\[
\frac{2at}{a^2t^2+b^2}.
\]

因为对参数 \(a\) 求导时：

\[
\frac{\partial}{\partial a}(a^2t^2+b^2)=2at^2.
\]

并且换元后还要乘：

\[
dx=\frac{dt}{1+t^2}.
\]

部分分式可得：

\[
F_a=\frac{\pi}{a+b}.
\]

于是

\[
F(a,b)=\pi\ln(a+b)+C(b).
\]

取 \(a=b\)：

\[
F(b,b)=\int_0^{\pi/2}\ln b^2\,dx
=
\pi\ln b.
\]

而

\[
F(b,b)=\pi\ln(2b)+C(b).
\]

所以

\[
C(b)=-\pi\ln2.
\]

最终：

\[
\boxed{F(a,b)=\pi\ln\frac{a+b}{2}.}
\]

---

## 3. 三角积分的核心换元

### 3.1 出现 \(\sin^2x,\cos^2x\)

优先考虑：

\[
\boxed{t=\tan x}
\]

因为：

\[
\sin^2x=\frac{t^2}{1+t^2},
\qquad
\cos^2x=\frac{1}{1+t^2},
\qquad
dx=\frac{dt}{1+t^2}.
\]

典型：

\[
\int_0^{\pi/2}
\frac{dx}{a^2\sin^2x+b^2\cos^2x}
=
\int_0^\infty \frac{dt}{a^2t^2+b^2}
=
\frac{\pi}{2ab}.
\]

### 3.2 出现 \(1-2d\cos x+d^2\)

优先考虑万能代换：

\[
\boxed{t=\tan\frac{x}{2}}
\]

因为：

\[
\cos x=\frac{1-t^2}{1+t^2},
\qquad
\sin x=\frac{2t}{1+t^2},
\qquad
dx=\frac{2dt}{1+t^2}.
\]

并且：

\[
1-2d\cos x+d^2
=
\frac{(1-d)^2+(1+d)^2t^2}{1+t^2}.
\]

所以：

\[
\int_0^\pi
\frac{dx}{1-2d\cos x+d^2}
=
2\int_0^\infty
\frac{dt}{(1-d)^2+(1+d)^2t^2}
=
\frac{\pi}{1-d^2}.
\]

---

## 4. 最重要的基础积分表

### 4.1 反正切型

\[
\boxed{
\int\frac{dx}{a^2+x^2}
=
\frac1a\arctan\frac{x}{a}+C
}
\]

定积分：

\[
\boxed{
\int_0^\infty\frac{dt}{A+Bt^2}
=
\frac{\pi}{2\sqrt{AB}},
\qquad A,B>0
}
\]

特别地：

\[
\int_0^\infty\frac{dt}{a^2t^2+b^2}
=
\frac{\pi}{2ab}.
\]

### 4.2 反双曲正切/对数型

\[
\boxed{
\int\frac{dx}{a^2-x^2}
=
\frac1{2a}\ln\left|\frac{a+x}{a-x}\right|+C
=
\frac1a\operatorname{artanh}\frac{x}{a}+C
}
\]

\[
\boxed{
\int\frac{dx}{x^2-a^2}
=
\frac1{2a}\ln\left|\frac{x-a}{x+a}\right|+C
}
\]

其中：

\[
\operatorname{artanh}x
=
\frac12\ln\frac{1+x}{1-x}.
\]

### 4.3 反正弦型

\[
\boxed{
\int\frac{dx}{\sqrt{a^2-x^2}}
=
\arcsin\frac{x}{a}+C
}
\]

原因：

\[
x=a\sin\theta,
\qquad
a^2-x^2=a^2\cos^2\theta.
\]

### 4.4 反双曲正弦型

\[
\boxed{
\int\frac{dx}{\sqrt{x^2+a^2}}
=
\operatorname{arsinh}\frac{x}{a}+C
=
\ln\left|x+\sqrt{x^2+a^2}\right|+C
}
\]

原因：

\[
x=a\sinh u,
\qquad
x^2+a^2=a^2\cosh^2u.
\]

### 4.5 反双曲余弦型

\[
\boxed{
\int\frac{dx}{\sqrt{x^2-a^2}}
=
\operatorname{arcosh}\frac{x}{a}+C
=
\ln\left|x+\sqrt{x^2-a^2}\right|+C
}
\]

原因：

\[
x=a\cosh u,
\qquad
x^2-a^2=a^2\sinh^2u.
\]

---

## 5. 三角、双曲、指数、复数的统一解释

### 5.1 指数函数是核心

实指数：

\[
e^{x+y}=e^xe^y.
\]

它把加法变乘法：

\[
(\mathbb R,+)\to(\mathbb R_{>0},\times).
\]

反函数 \(\ln\) 把乘法结构还原为加法参数：

\[
\ln(ab)=\ln a+\ln b.
\]

### 5.2 欧拉公式

\[
\boxed{e^{ix}=\cos x+i\sin x}
\]

虚指数表示旋转：

\[
e^{i(x+y)}=e^{ix}e^{iy}.
\]

所以角度相加对应复数乘法。

单位圆群：

\[
U(1)=\{z:|z|=1\}
\]

满足：

\[
U(1)\cong \mathbb R/2\pi\mathbb Z.
\]

### 5.3 复对数

若

\[
z=re^{i\theta},
\]

则

\[
\boxed{\log z=\ln r+i\theta.}
\]

含义：

- 实部 \(\ln r\)：记录伸缩；
- 虚部 \(\theta\)：记录旋转角度。

所以 \(\log\) 不是单纯“逆映射回模长和角度”，而是把复数乘法结构拆成：

\[
\boxed{\text{模长的加法}+\text{角度的加法}}
\]

### 5.4 双曲函数

定义：

\[
\sinh x=\frac{e^x-e^{-x}}2,
\qquad
\cosh x=\frac{e^x+e^{-x}}2.
\]

\[
\tanh x=\frac{\sinh x}{\cosh x}
=
\frac{e^{2x}-1}{e^{2x}+1}.
\]

恒等式：

\[
\boxed{\cosh^2x-\sinh^2x=1}
\]

对应双曲线：

\[
X^2-Y^2=1.
\]

普通三角函数满足：

\[
\boxed{\cos^2x+\sin^2x=1}
\]

对应圆：

\[
X^2+Y^2=1.
\]

### 5.5 三角和双曲通过虚数连接

由欧拉公式：

\[
\cos z=\frac{e^{iz}+e^{-iz}}2,
\qquad
\sin z=\frac{e^{iz}-e^{-iz}}{2i}.
\]

代入 \(z=ix\)：

\[
\boxed{\cos(ix)=\cosh x}
\]

\[
\boxed{\sin(ix)=i\sinh x}
\]

所以：

\[
\boxed{\text{双曲函数是三角函数在虚轴方向的版本。}}
\]

---

## 6. 判别式 \(\Delta\) 与积分形式

一般二次式：

\[
ax^2+bx+c.
\]

判别式：

\[
\Delta=b^2-4ac.
\]

### 6.1 \(\Delta>0\)：两个实根

\[
ax^2+bx+c=a(x-r_1)(x-r_2).
\]

部分分式后出现：

\[
\ln|x-r_1|,\quad \ln|x-r_2|.
\]

所以：

\[
\boxed{\Delta>0 \Rightarrow \ln}
\]

### 6.2 \(\Delta=0\)：重根

\[
ax^2+bx+c=a(x-r)^2.
\]

积分出现有理函数型：

\[
\int\frac{dx}{(x-r)^2}
=
-\frac1{x-r}+C.
\]

所以：

\[
\boxed{\Delta=0 \Rightarrow 有理函数型}
\]

### 6.3 \(\Delta<0\)：无实根/复共轭根

配方：

\[
ax^2+bx+c
=
a\left(x+\frac b{2a}\right)^2
+
\frac{4ac-b^2}{4a}.
\]

变成：

\[
u^2+\alpha^2.
\]

积分出现：

\[
\arctan.
\]

所以：

\[
\boxed{\Delta<0 \Rightarrow \arctan}
\]

本质上：

\[
x^2+a^2=(x-ia)(x+ia).
\]

复根在实数积分里表现为 \(\arctan\)。

---

## 7. 复对数统一 \(\ln\) 和 \(\arctan\)

在复数中：

\[
x^2+a^2=(x-ia)(x+ia).
\]

于是：

\[
\frac1{x^2+a^2}
=
\frac1{2ia}
\left(
\frac1{x-ia}-\frac1{x+ia}
\right).
\]

积分：

\[
\int\frac{dx}{x^2+a^2}
=
\frac1{2ia}
\ln\frac{x-ia}{x+ia}+C.
\]

它等价于实函数：

\[
\frac1a\arctan\frac{x}{a}+C.
\]

经典公式：

\[
\boxed{
\arctan x
=
\frac1{2i}\log\frac{1+ix}{1-ix}.
}
\]

因此：

\[
\boxed{\arctan \text{ 是复对数的角度部分。}}
\]

---

## 8. 有理分式积分的完整套路

处理：

\[
\int R(x)\,dx
=
\int \frac{P(x)}{Q(x)}\,dx.
\]

### 8.1 第一步：多项式除法

若

\[
\deg P\ge \deg Q,
\]

先做除法：

\[
\frac{P(x)}{Q(x)}
=
S(x)+\frac{R_1(x)}{Q(x)},
\qquad
\deg R_1<\deg Q.
\]

多项式部分 \(S(x)\) 直接积分。

### 8.2 第二步：分解分母

实数范围内：

\[
Q(x)
=
\prod_i (x-a_i)^{m_i}
\prod_j (x^2+p_jx+q_j)^{n_j},
\]

其中不可约二次因子满足：

\[
p_j^2-4q_j<0.
\]

### 8.3 第三步：部分分式

一般展开：

\[
\frac{R_1(x)}{Q(x)}
=
\sum_{i,k}\frac{A_{ik}}{(x-a_i)^k}
+
\sum_{j,k}
\frac{B_{jk}x+C_{jk}}{(x^2+p_jx+q_j)^k}.
\]

逐项积分。

### 8.4 一次因子积分

\[
\boxed{
\int\frac{dx}{x-a}
=
\ln|x-a|+C
}
\]

\[
\boxed{
\int\frac{dx}{(x-a)^k}
=
-\frac1{(k-1)(x-a)^{k-1}}+C,
\qquad k\neq1
}
\]

### 8.5 不可约二次因子积分

考虑：

\[
\int\frac{Bx+C}{x^2+px+q}\,dx,
\qquad p^2-4q<0.
\]

令

\[
D=x^2+px+q,
\qquad
D'=2x+p.
\]

把分子拆成：

\[
Bx+C=\lambda(2x+p)+\mu.
\]

于是：

\[
\int\frac{Bx+C}{D}\,dx
=
\lambda\int\frac{D'}D\,dx
+
\mu\int\frac{dx}{D}.
\]

第一项：

\[
\lambda\ln D.
\]

第二项配方：

\[
D=
\left(x+\frac p2\right)^2
+
\left(q-\frac{p^2}{4}\right).
\]

令

\[
\alpha=\sqrt{q-\frac{p^2}{4}}.
\]

则：

\[
\int\frac{dx}{D}
=
\frac1\alpha
\arctan\frac{x+p/2}{\alpha}.
\]

因此不可约二次因子产生：

\[
\boxed{\ln+\arctan}
\]

---

## 9. 二次式与函数类型总表

| 结构 | 典型形式 | 换元/根结构 | 积分函数 |
|---|---|---|---|
| 平方和 | \(x^2+a^2\) | 复根 \(\pm ia\)，或 \(x=a\tan\theta\) | \(\arctan\) |
| 平方差 | \(x^2-a^2\) | 实根 \(\pm a\) | \(\ln\) |
| 圆型根式 | \(\sqrt{a^2-x^2}\) | \(x=a\sin\theta\) | \(\arcsin\) |
| 双曲根式一 | \(\sqrt{x^2+a^2}\) | \(x=a\sinh u\) | \(\operatorname{arsinh},\ln\) |
| 双曲根式二 | \(\sqrt{x^2-a^2}\) | \(x=a\cosh u\) | \(\operatorname{arcosh},\ln\) |
| \(1-x^2\) 分母 | \(1-x^2\) | 实根 \(\pm1\) | \(\operatorname{artanh},\ln\) |
| \(1+x^2\) 分母 | \(1+x^2\) | 复根 \(\pm i\) | \(\arctan\) |

---

## 10. 最小记忆包

真正需要熟练的不是大量积分表，而是以下母公式和换元。

### 10.1 换元

\[
\boxed{
t=\tan x:
\quad
\sin^2x=\frac{t^2}{1+t^2},
\quad
\cos^2x=\frac1{1+t^2},
\quad
dx=\frac{dt}{1+t^2}
}
\]

\[
\boxed{
t=\tan\frac{x}{2}:
\quad
\cos x=\frac{1-t^2}{1+t^2},
\quad
\sin x=\frac{2t}{1+t^2},
\quad
dx=\frac{2dt}{1+t^2}
}
\]

### 10.2 基础积分

\[
\boxed{
\int\frac{dx}{x-a}=\ln|x-a|+C
}
\]

\[
\boxed{
\int\frac{dx}{x^2+a^2}
=
\frac1a\arctan\frac{x}{a}+C
}
\]

\[
\boxed{
\int\frac{dx}{a^2-x^2}
=
\frac1{2a}\ln\left|\frac{a+x}{a-x}\right|+C
}
\]

\[
\boxed{
\int\frac{dx}{\sqrt{a^2-x^2}}
=
\arcsin\frac xa+C
}
\]

\[
\boxed{
\int\frac{dx}{\sqrt{x^2+a^2}}
=
\ln\left|x+\sqrt{x^2+a^2}\right|+C
}
\]

\[
\boxed{
\int\frac{dx}{\sqrt{x^2-a^2}}
=
\ln\left|x+\sqrt{x^2-a^2}\right|+C
}
\]

\[
\boxed{
\int_0^\infty\frac{dt}{A+Bt^2}
=
\frac{\pi}{2\sqrt{AB}},
\qquad A,B>0
}
\]

---

## 11. 总结性判断规则

遇到积分时：

1. 如果是有理分式，先多项式除法，再因式分解，再部分分式。
2. 分母是二次式，先看判别式：
   \[
   \Delta>0\Rightarrow \ln,
   \quad
   \Delta=0\Rightarrow 有理项,
   \quad
   \Delta<0\Rightarrow \arctan.
   \]
3. 出现 \(\sin^2,\cos^2\)，优先用：
   \[
   t=\tan x.
   \]
4. 出现 \(1-2d\cos x+d^2\)，优先用：
   \[
   t=\tan\frac{x}{2}.
   \]
5. 出现 \(\sqrt{a^2-x^2}\)，用三角换元：
   \[
   x=a\sin\theta.
   \]
6. 出现 \(\sqrt{x^2+a^2}\)，用双曲换元：
   \[
   x=a\sinh u.
   \]
7. 出现 \(\sqrt{x^2-a^2}\)，用双曲换元：
   \[
   x=a\cosh u.
   \]
8. \(\ln\) 记录伸缩，\(\arg/\arctan\) 记录角度，复对数统一二者：
   \[
   \log(re^{i\theta})=\ln r+i\theta.
   \]
9. 三角函数、双曲函数、指数函数不是孤立对象：
   \[
   e^{ix}=\cos x+i\sin x,
   \]
   \[
   \cos(ix)=\cosh x,
   \qquad
   \sin(ix)=i\sinh x.
   \]
10. 本质上：
    \[
    \boxed{
    积分表是二次式根结构、平方根几何、指数/复数群结构的不同投影。
    }
    \]
