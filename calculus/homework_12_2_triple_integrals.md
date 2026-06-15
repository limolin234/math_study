# 作业 12.2：三重积分

本文由 `tmp.md` 中 12.2 节作业解答、核对与修正整理而成。

---

# 作业 12.2：三重积分

## 1. 计算下列三重积分

### (1)

题意辨认为：

$$
\iiint_\Omega xyz\,dV,
$$

其中 $\Omega$ 由曲面 $z=xy$，平面 $y=x$，$x=1$ 和 $z=0$ 围成。

取区域为

$$
0\le x\le 1,\qquad 0\le y\le x,\qquad 0\le z\le xy.
$$

于是

$$
\begin{aligned}
I
&=\int_0^1\int_0^x\int_0^{xy} xyz\,dz\,dy\,dx \\
&=\int_0^1\int_0^x xy\cdot {1\over 2}x^2y^2\,dy\,dx \\
&={1\over 2}\int_0^1x^3\left(\int_0^x y^3\,dy\right)dx \\
&={1\over 2}\int_0^1x^3\cdot {x^4\over 4}\,dx \\
&={1\over 8}\int_0^1x^7\,dx \\
&={1\over 64}.
\end{aligned}
$$

所以

$$
\boxed{I={1\over 64}}.
$$

---

### (2)

题意辨认为：

$$
\iiint_\Omega {dV\over (1+x+y+z)^3},
$$

其中 $\Omega$ 是由 $x=0,y=0,z=0,x+y+z=1$ 围成的四面体。

令

$$
u=x+y+z.
$$

在平面 $x+y+z=u$ 上，第一卦限截得三角形面积为

$$
{u^2\over 2}.
$$

因此

$$
I=\int_0^1 {1\over (1+u)^3}\cdot {u^2\over 2}\,du.
$$

计算：

$$
\begin{aligned}
I
&={1\over 2}\int_0^1 {u^2\over (1+u)^3}\,du.
\end{aligned}
$$

令 $v=1+u$，则

$$
{u^2\over(1+u)^3}={(v-1)^2\over v^3}
={1\over v}-{2\over v^2}+{1\over v^3}.
$$

所以

$$
\begin{aligned}
I
&={1\over 2}\int_1^2\left({1\over v}-{2\over v^2}+{1\over v^3}\right)dv \\
&={1\over 2}\left[\ln v+{2\over v}-{1\over 2v^2}\right]_1^2 \\
&={1\over 2}\left(\ln 2-{5\over 8}\right).
\end{aligned}
$$

故

$$
\boxed{I={\ln 2\over 2}-{5\over 16}}.
$$

---

### (3)

题意辨认为：

$$
\iiint_\Omega z^2\,dV,
$$

其中 $\Omega$ 由两个球

$$
x^2+y^2+z^2\le R^2,
\qquad
x^2+y^2+z^2\le 2Rz
$$

的公共部分给出。

用球坐标

$$
z=\rho\cos\theta,
\qquad dV=\rho^2\sin\theta\,d\rho\,d\theta\,d\varphi.
$$

第二个球给出

$$
\rho\le 2R\cos\theta,
\qquad 0\le \theta\le {\pi\over 2}.
$$

公共部分满足

$$
\rho\le \min\{R,2R\cos\theta\}.
$$

当 $0\le\theta\le\pi/3$ 时，$2R\cos\theta\ge R$，上限为 $R$；当 $\pi/3\le\theta\le\pi/2$ 时，上限为 $2R\cos\theta$。

于是

$$
\begin{aligned}
I
&=2\pi\int_0^{\pi/3}\int_0^R \rho^4\cos^2\theta\sin\theta\,d\rho\,d\theta \\
&\quad +2\pi\int_{\pi/3}^{\pi/2}\int_0^{2R\cos\theta}\rho^4\cos^2\theta\sin\theta\,d\rho\,d\theta.
\end{aligned}
$$

第一部分为

$$
2\pi\cdot {R^5\over 5}\int_0^{\pi/3}\cos^2\theta\sin\theta\,d\theta
={7\pi R^5\over 60}.
$$

第二部分为

$$
2\pi\cdot {32R^5\over 5}\int_{\pi/3}^{\pi/2}\cos^7\theta\sin\theta\,d\theta
={\pi R^5\over 160}.
$$

所以

$$
\boxed{I={59\pi R^5\over 480}}.
$$

---

### (4)

题意辨认为：

$$
\iiint_\Omega x^2\,dV,
$$

其中 $\Omega$ 为椭球

$$
{x^2\over a^2}+{y^2\over b^2}+{z^2\over c^2}\le 1.
$$

令

$$
x=au,
\qquad y=bv,
\qquad z=cw.
$$

则 $u^2+v^2+w^2\le 1$，且

$$
dV=abc\,du\,dv\,dw.
$$

因此

$$
I=a^2abc\iiint_{u^2+v^2+w^2\le 1}u^2\,du\,dv\,dw.
$$

单位球中由对称性

$$
\iiint u^2\,dV={1\over 3}\iiint (u^2+v^2+w^2)\,dV.
$$

而

$$
\iiint_{B_1}r^2\,dV=4\pi\int_0^1r^4\,dr={4\pi\over 5}.
$$

故

$$
\iiint_{B_1}u^2\,dV={4\pi\over 15}.
$$

所以

$$
\boxed{I={4\pi a^3bc\over 15}}.
$$

---

### (5)

题意辨认为：

$$
\iiint_\Omega \sqrt{1-{x^2\over a^2}-{y^2\over b^2}-{z^2\over c^2}}\,dV,
$$

其中 $\Omega$ 为椭球

$$
{x^2\over a^2}+{y^2\over b^2}+{z^2\over c^2}\le 1.
$$

令

$$
x=ar\sin\varphi\cos\theta,
\qquad
 y=br\sin\varphi\sin\theta,
\qquad
 z=cr\cos\varphi.
$$

则

$$
dV=abc\,r^2\sin\varphi\,dr\,d\varphi\,d\theta.
$$

积分化为

$$
I=abc\int_0^{2\pi}\int_0^\pi\int_0^1\sqrt{1-r^2}\,r^2\sin\varphi\,dr\,d\varphi\,d\theta.
$$

角向积分为 $4\pi$，所以

$$
I=4\pi abc\int_0^1r^2\sqrt{1-r^2}\,dr.
$$

令 $r=\sin t$，得

$$
\int_0^1r^2\sqrt{1-r^2}\,dr
=\int_0^{\pi/2}\sin^2t\cos^2t\,dt
={\pi\over 16}.
$$

所以

$$
\boxed{I={\pi^2abc\over 4}}.
$$

---

### (6)

题意辨认为：

$$
\iiint_\Omega {z\ln(1+x^2+y^2+z^2)\over 1+x^2+y^2+z^2}\,dV,
$$

其中 $\Omega$ 为上半单位球

$$
x^2+y^2+z^2\le 1,
\qquad z\ge 0.
$$

用球坐标：

$$
z=\rho\cos\theta,
\qquad x^2+y^2+z^2=\rho^2.
$$

于是

$$
\begin{aligned}
I
&=\int_0^{2\pi}\int_0^{\pi/2}\int_0^1
{\rho\cos\theta\ln(1+\rho^2)\over 1+\rho^2}
\rho^2\sin\theta\,d\rho\,d\theta\,d\varphi \\
&=2\pi\left(\int_0^{\pi/2}\cos\theta\sin\theta\,d\theta\right)
\int_0^1{\rho^3\ln(1+\rho^2)\over 1+\rho^2}\,d\rho \\
&=\pi\int_0^1{\rho^3\ln(1+\rho^2)\over 1+\rho^2}\,d\rho.
\end{aligned}
$$

令 $u=1+\rho^2$，则 $\rho^3d\rho=(u-1)du/2$，所以

$$
\begin{aligned}
I
&={\pi\over 2}\int_1^2\left(1-{1\over u}\right)\ln u\,du \\
&={\pi\over 2}\left[ u\ln u-u-{1\over 2}(\ln u)^2\right]_1^2 \\
&={\pi\over 2}\left(2\ln2-1-{(\ln2)^2\over 2}\right).
\end{aligned}
$$

故

$$
\boxed{I={\pi\over 2}\left(2\ln2-1-{(\ln2)^2\over 2}\right)}.
$$

---

### (7)

题意辨认为：

$$
\iiint_\Omega (x+y+z)^2\,dV,
$$

其中 $\Omega$ 由抛物面

$$
x^2+y^2=2az
$$

和球面

$$
x^2+y^2+z^2=9a^2
$$

围成。

用柱坐标，抛物面为

$$
z={r^2\over 2a},
$$

球面上半部为

$$
z=\sqrt{9a^2-r^2}.
$$

交线由

$$
{r^2\over 2a}=\sqrt{9a^2-r^2}
$$

给出。令 $s=r^2$，得

$$
s^2+4a^2s-36a^4=0,
$$

所以

$$
r_0^2=2a^2(\sqrt{10}-1).
$$

对角变量积分时，

$$
\int_0^{2\pi}(x+y+z)^2\,d\theta
=2\pi(r^2+z^2).
$$

因此

$$
\boxed{
I=2\pi\int_0^{a\sqrt{2(\sqrt{10}-1)}}
\int_{r^2/(2a)}^{\sqrt{9a^2-r^2}}
(r^2+z^2)r\,dz\,dr
}.
$$

若需要继续化简，只需对 $z$ 和 $r$ 作普通一元积分。

---

### (8)、(9)、(10)

这三题手写区域条件辨认不够可靠，暂时不直接给最终值，避免把题意读错。可按如下方法处理：

- (8) 若区域为某平面曲线绕 $z$ 轴旋转并由平面 $z=8$ 截成的旋转体，优先用柱坐标，写成 $r,z,\theta$ 的积分。
- (9) 若区域为球

$$
x^2+y^2+(z-1)^2\le 1,
$$

则用球心平移坐标

$$
X=x,
\qquad Y=y,
\qquad Z=z-1
$$

后再用球坐标。
- (10) 令

$$
u=x+y-z,
\qquad v=x-y+z,
\qquad w=y+z-x.
$$

区域为 $0\le u,v,w\le1$。反解为

$$
x={u+v\over 2},
\qquad y={u+w\over 2},
\qquad z={v+w\over 2}.
$$

Jacobian 为

$$
\left|{\partial(x,y,z)\over\partial(u,v,w)}\right|={1\over 2}.
$$

被积函数就是 $uvw$，所以若题意确为

$$
\iiint_\Omega (x+y-z)(x-y+z)(y+z-x)\,dV,
$$

则

$$
I={1\over 2}\int_0^1\int_0^1\int_0^1uvw\,du\,dv\,dw
={1\over 16}.
$$

---

## 2. 曲面包围区域体积

题意辨认为：求曲面

$$
\left({x^2\over a^2}+{y^2\over b^2}+{z^2\over c^2}\right)^2=ax,
\qquad a,b,c>0
$$

所围成空间区域体积。

直接按 $x$ 截面计算最简单。

固定 $x$，令

$$
K(x)=\sqrt{ax}-{x^2\over a^2}.
$$

因为

$$
\left({x^2\over a^2}+{y^2\over b^2}+{z^2\over c^2}\right)^2=ax,
$$

且括号内非负，所以边界上

$$
{x^2\over a^2}+{y^2\over b^2}+{z^2\over c^2}=\sqrt{ax}.
$$

因此固定 $x$ 后，$yz$ 截面满足

$$
{y^2\over b^2}+{z^2\over c^2}\le \sqrt{ax}-{x^2\over a^2}=K(x).
$$

截面非空要求

$$
K(x)\ge0.
$$

即

$$
\sqrt{ax}\ge {x^2\over a^2}.
$$

由于 $x\ge0$，两边平方得

$$
ax\ge {x^4\over a^4}.
$$

所以

$$
x^3\le a^5,
$$

从而

$$
0\le x\le a^{5/3}.
$$

固定 $x$ 时，截面是椭圆：

$$
{y^2\over b^2K(x)}+{z^2\over c^2K(x)}\le1.
$$

其半轴分别为

$$
b\sqrt{K(x)},
\qquad c\sqrt{K(x)}.
$$

所以截面面积为

$$
A(x)=\pi bcK(x)
=\pi bc\left(\sqrt{ax}-{x^2\over a^2}\right).
$$

于是体积为

$$
\begin{aligned}
V
&=\int_0^{a^{5/3}}A(x)\,dx \\
&=\pi bc\int_0^{a^{5/3}}\left(\sqrt{ax}-{x^2\over a^2}\right)dx.
\end{aligned}
$$

分别计算：

$$
\int_0^{a^{5/3}}\sqrt{ax}\,dx
=\sqrt a\int_0^{a^{5/3}}x^{1/2}\,dx
=\sqrt a\cdot {2\over3}\left(a^{5/3}\right)^{3/2}
={2\over3}a^3.
$$

而

$$
\int_0^{a^{5/3}}{x^2\over a^2}\,dx
={1\over a^2}\cdot {\left(a^{5/3}\right)^3\over3}
={a^3\over3}.
$$

所以

$$
V=\pi bc\left({2a^3\over3}-{a^3\over3}\right)
={\pi a^3bc\over3}.
$$

故

$$
\boxed{V={\pi a^3bc\over3}}.
$$

---

## 3. 物体质量

题意辨认为：物体由曲面

$$
4z^2=25(x^2+y^2)
$$

与平面 $z=5$ 围成，密度为

$$
\rho(x,y,z)=x^2+y^2.
$$

求物体质量。

用柱坐标

$$
x=r\cos\theta,
\qquad y=r\sin\theta,
\qquad x^2+y^2=r^2.
$$

由

$$
4z^2=25r^2
$$

得

$$
r={2z\over5}.
$$

区域为

$$
0\le z\le5,
\qquad 0\le r\le {2z\over5},
\qquad 0\le\theta\le2\pi.
$$

密度为

$$
\rho=r^2,
$$

体积元为

$$
dV=r\,dr\,d\theta\,dz.
$$

所以质量

$$
\begin{aligned}
M
&=\iiint_\Omega \rho\,dV \\
&=\int_0^5\int_0^{2\pi}\int_0^{2z/5} r^2\cdot r\,dr\,d\theta\,dz \\
&=2\pi\int_0^5\left[{r^4\over4}\right]_0^{2z/5}dz \\
&=2\pi\int_0^5 {1\over4}\left({2z\over5}\right)^4dz \\
&=2\pi\int_0^5 {4z^4\over625}dz \\
&={8\pi\over625}\int_0^5z^4\,dz \\
&={8\pi\over625}\cdot {5^5\over5} \\
&={8\pi\over625}\cdot 625 \\
&=8\pi.
\end{aligned}
$$

因此

$$
\boxed{M=8\pi}.
$$

---

## 4. 球内一维化公式验证

题意辨认为：设 $f(u)$ 在 $[-1,1]$ 连续，证明

$$
\iiint_{x^2+y^2+z^2\le1} f(z)\,dV
=\pi\int_{-1}^1 f(u)(1-u^2)\,du.
$$

证明：固定 $z=u$，截面为

$$
x^2+y^2\le 1-u^2,
$$

面积为

$$
\pi(1-u^2).
$$

因此按截面分层积分：

$$
\iiint_\Omega f(z)\,dV
=\int_{-1}^1 f(u)\cdot \pi(1-u^2)\,du.
$$

故

$$
\boxed{
\iiint_\Omega f(z)\,dV=\pi\int_{-1}^1 f(u)(1-u^2)\,du
}.
$$

---

---

# 12.2 相关核对与修正

## 核对：12.2 第 3 题为什么不是 \(R^3\)

题目第 3 题若为

$$
\iiint_\Omega z^2\,dV,
$$

其中

$$
\Omega:\quad x^2+y^2+z^2\le R^2,
\qquad
x^2+y^2+z^2\le 2Rz,
$$

则结果不应该和 $R^3$ 成正比，而应该和 $R^5$ 成正比。

原因是：

- $dV$ 的量纲是 $R^3$；
- $z^2$ 的量纲是 $R^2$；
- 所以 $z^2dV$ 的量纲是 $R^5$。

因此

$$
\iiint_\Omega z^2\,dV
$$

必须是常数乘以 $R^5$。

如果只求公共部分体积，也就是

$$
V=\iiint_\Omega 1\,dV,
$$

那才应该和 $R^3$ 成正比。

用球坐标

$$
z=\rho\cos\theta,
\qquad dV=\rho^2\sin\theta\,d\rho\,d\theta\,d\varphi.
$$

两个球给出

$$
\rho\le R,
\qquad \rho\le 2R\cos\theta.
$$

所以公共区域为

$$
0\le\theta\le {\pi\over 3}:\quad 0\le\rho\le R,
$$

以及

$$
{\pi\over 3}\le\theta\le {\pi\over 2}:\quad 0\le\rho\le 2R\cos\theta.
$$

若求体积：

$$
\begin{aligned}
V
&=2\pi\int_0^{\pi/3}\int_0^R \rho^2\sin\theta\,d\rho\,d\theta
+2\pi\int_{\pi/3}^{\pi/2}\int_0^{2R\cos\theta}\rho^2\sin\theta\,d\rho\,d\theta \\
&={\pi R^3\over3}+{\pi R^3\over12} \\
&={5\pi R^3\over12}.
\end{aligned}
$$

所以

$$
\boxed{V={5\pi R^3\over12}}
$$

是公共部分的体积。

但若求原先辨认出来的积分

$$
I=\iiint_\Omega z^2\,dV,
$$

则

$$
z^2=\rho^2\cos^2\theta,
$$

所以

$$
I=2\pi\int_0^{\pi/3}\int_0^R \rho^4\cos^2\theta\sin\theta\,d\rho\,d\theta
+2\pi\int_{\pi/3}^{\pi/2}\int_0^{2R\cos\theta}\rho^4\cos^2\theta\sin\theta\,d\rho\,d\theta.
$$

计算得

$$
I={59\pi R^5\over480}.
$$

结论：

$$
\boxed{
{5\pi R^3\over12}\text{ 是体积，不是 }\iiint_\Omega z^2\,dV.
}
$$

如果 PDF 原题第 3 题其实是“求公共部分体积”，那你的答案是对的；如果原题确实写的是 $\iiint_\Omega z^2\,dV$，那答案应为

$$
\boxed{{59\pi R^5\over480}}.
$$

---

## 核对：12.2 第 2 大题可以直接按 \(x\) 截面算：右端为 \(ax\)

确认原题是

$$
\left({x^2\over a^2}+{y^2\over b^2}+{z^2\over c^2}\right)^2=ax.
$$

所以固定 $x$ 后应该是

$$
{y^2\over b^2}+{z^2\over c^2}
\le
\sqrt{ax}-{x^2\over a^2}.
$$

这里不能把上限取成 $a$。因为截面非空需要

$$
\sqrt{ax}-{x^2\over a^2}\ge0.
$$

即

$$
\sqrt{ax}\ge {x^2\over a^2}.
$$

平方后：

$$
ax\ge {x^4\over a^4}.
$$

由于 $x\ge0$，所以

$$
x^3\le a^5.
$$

因此

$$
0\le x\le a^{5/3}.
$$

于是截面面积为

$$
A(x)=\pi bc\left(\sqrt{ax}-{x^2\over a^2}\right).
$$

体积为

$$
\begin{aligned}
V
&=\pi bc\int_0^{a^{5/3}}\left(\sqrt{ax}-{x^2\over a^2}\right)dx \\
&=\pi bc\left({2a^3\over3}-{a^3\over3}\right) \\
&={\pi a^3bc\over3}.
\end{aligned}
$$

所以正确结果为

$$
\boxed{V={\pi a^3bc\over3}}.
$$

你原先写的“按 $x$ 截面直接算”这个思路完全正确；需要改的是：右端为 $ax$ 时，积分上限不是 $a$，而是 $a^{5/3}$。

---
