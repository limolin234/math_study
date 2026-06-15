# tmp.md 归档：12.2/12.4/12.5 作业与向量分析机制（2026-06-10）

本文件由 `tmp.md` 整理归档而来。归档后 `tmp.md` 已清空，后续黑板继续从空文件追加。

---

# PDF 作业解答草稿（12.2、12.4、12.5）

说明：PDF 是手写扫描件，`pdftotext` 无法提取文字；下面按图片辨认题意解答。少数题目字迹或区域条件不完全确定，我在对应小题标出“题意待核对”。

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

# 作业 12.4：曲线积分

## 1. 第一型曲线积分

### (1)

题意辨认为：

$$
\int_L(x+y)\,ds,
$$

其中 $L$ 为以 $O(0,0),A(1,0),B(0,1)$ 为顶点的三角形边界。

三边分别计算。

$OA$ 上 $y=0$：

$$
\int_{OA}(x+y)ds=\int_0^1x\,dx={1\over2}.
$$

$OB$ 上 $x=0$：

$$
\int_{OB}(x+y)ds=\int_0^1y\,dy={1\over2}.
$$

$AB$ 上 $x+y=1$，线段长度为 $\sqrt2$，所以

$$
\int_{AB}(x+y)ds=\sqrt2.
$$

故

$$
\boxed{I=1+\sqrt2}.
$$

---

### (2)

题意辨认为：

$$
\int_L |x|^{1/3}\,ds,
$$

其中 $L$ 为星形线

$$
x^{2/3}+y^{2/3}=a^{2/3}.
$$

参数方程：

$$
x=a\cos^3t,
\qquad y=a\sin^3t,
\qquad 0\le t\le 2\pi.
$$

有

$$
ds=3a|\sin t\cos t|\,dt,
$$

且

$$
|x|^{1/3}=a^{1/3}|\cos t|.
$$

因此

$$
\begin{aligned}
I
&=3a^{4/3}\int_0^{2\pi}|\cos t|\,|\sin t\cos t|\,dt \\
&=3a^{4/3}\int_0^{2\pi}|\sin t|\cos^2t\,dt \\
&=3a^{4/3}\cdot 4\int_0^{\pi/2}\sin t\cos^2t\,dt \\
&=3a^{4/3}\cdot 4\cdot {1\over 3}.
\end{aligned}
$$

所以

$$
\boxed{I=4a^{4/3}}.
$$

---

### (3)

题意辨认为：

$$
\int_L |x|\,ds,
$$

其中 $L$ 为双纽线

$$
(x^2+y^2)^2=x^2-y^2.
$$

用极坐标，曲线为

$$
r^2=\cos 2\theta.
$$

两个叶片分别对应

$$
-\frac\pi4\le\theta\le\frac\pi4,
\qquad
\frac{3\pi}4\le\theta\le\frac{5\pi}4.
$$

由

$$
ds=\sqrt{r^2+\left({dr\over d\theta}\right)^2}\,d\theta={d\theta\over r},
$$

而

$$
|x|=|r\cos\theta|,
$$

所以

$$
|x|ds=|\cos\theta|d\theta.
$$

因此

$$
I=\int_{-\pi/4}^{\pi/4}\cos\theta\,d\theta
+\int_{3\pi/4}^{5\pi/4}(-\cos\theta)\,d\theta
=\sqrt2+\sqrt2.
$$

故

$$
\boxed{I=2\sqrt2}.
$$

---

### (4)

题意辨认为：

$$
\int_L(x^2+y^2+z^2)\,ds,
$$

其中 $L$ 为螺旋线

$$
x=a\cos t,
\qquad y=a\sin t,
\qquad z=bt,
\qquad 0\le t\le2\pi.
$$

有

$$
ds=\sqrt{a^2+b^2}\,dt,
$$

且

$$
x^2+y^2+z^2=a^2+b^2t^2.
$$

所以

$$
\begin{aligned}
I
&=\sqrt{a^2+b^2}\int_0^{2\pi}(a^2+b^2t^2)\,dt \\
&=\sqrt{a^2+b^2}\left(2\pi a^2+{8\pi^3b^2\over 3}\right).
\end{aligned}
$$

故

$$
\boxed{I=\sqrt{a^2+b^2}\left(2\pi a^2+{8\pi^3b^2\over 3}\right)}.
$$

---

### (5)

题意辨认为：

$$
\int_L xyz\,ds,
$$

其中

$$
x=t,
\qquad y={2\sqrt2\over3}t^{3/2},
\qquad z={1\over2}t^2,
\qquad 0\le t\le1.
$$

有

$$
x'=1,
\qquad y'=\sqrt{2t},
\qquad z'=t.
$$

所以

$$
ds=\sqrt{1+2t+t^2}\,dt=(1+t)dt.
$$

又

$$
xyz=t\cdot {2\sqrt2\over3}t^{3/2}\cdot {1\over2}t^2
={\sqrt2\over3}t^{9/2}.
$$

因此

$$
\begin{aligned}
I
&={\sqrt2\over3}\int_0^1t^{9/2}(1+t)\,dt \\
&={\sqrt2\over3}\left({2\over11}+{2\over13}\right) \\
&={28\sqrt2\over 429}.
\end{aligned}
$$

故

$$
\boxed{I={28\sqrt2\over429}}.
$$

---

## 2. 椭圆周线密度

题意辨认为：椭圆

$$
x=a\cos t,
\qquad y=b\sin t,
\qquad 0\le t\le 2\pi
$$

在点 $M(x,y)$ 处线密度为

$$
\rho(x,y)=|y|.
$$

质量为

$$
M=\int_L\rho\,ds.
$$

由

$$
ds=\sqrt{a^2\sin^2t+b^2\cos^2t}\,dt,
$$

得到

$$
M=\int_0^{2\pi}|b\sin t|\sqrt{a^2\sin^2t+b^2\cos^2t}\,dt.
$$

利用对称性：

$$
\boxed{
M=4b\int_0^{\pi/2}\sin t\sqrt{a^2\sin^2t+b^2\cos^2t}\,dt
}.
$$

也可令 $u=\cos t$，写成

$$
\boxed{
M=4b\int_0^1\sqrt{a^2+(b^2-a^2)u^2}\,du
}.
$$

这个结果已经是一元积分形式；根据 $a,b$ 大小可进一步用反三角或双曲函数写闭式。

---

## 3. 第二型曲线积分

### (1)

题意辨认为：

$$
\int_L (x^2+y^2)\,dx+(x^2-y^2)\,dy,
$$

其中 $L$ 是以 $A(1,0),B(2,0),C(2,1),D(1,1)$ 为顶点的矩形边界，方向为逆时针。

用 Green 公式：

$$
\oint_LPdx+Qdy=\iint_D\left({\partial Q\over\partial x}-{\partial P\over\partial y}\right)dA.
$$

其中

$$
P=x^2+y^2,
\qquad Q=x^2-y^2.
$$

所以

$$
{\partial Q\over\partial x}-{\partial P\over\partial y}=2x-2y.
$$

区域为

$$
1\le x\le2,
\qquad 0\le y\le1.
$$

于是

$$
I=\int_1^2\int_0^1(2x-2y)\,dy\,dx=2.
$$

故

$$
\boxed{I=2}.
$$

---

### (2)

题意辨认为：

$$
\int_L{(x+y)dx-(x-y)dy\over x^2+y^2},
$$

其中 $L$ 是圆周 $x^2+y^2=a^2$，方向为逆时针。

取

$$
x=a\cos t,
\qquad y=a\sin t,
\qquad 0\le t\le2\pi.
$$

则

$$
dx=-a\sin t\,dt,
\qquad dy=a\cos t\,dt.
$$

分子为

$$
(x+y)dx-(x-y)dy=-a^2dt.
$$

分母为

$$
x^2+y^2=a^2.
$$

所以

$$
I=\int_0^{2\pi}(-1)\,dt=-2\pi.
$$

故

$$
\boxed{I=-2\pi}.
$$

---

### (3)

题意辨认为：

$$
\int_L y\,dx-x\,dy+(x^2+y^2)\,dz,
$$

其中

$$
x=e^t,
\qquad y=e^{-t},
\qquad z=a^t,
\qquad 0\le t\le1.
$$

有

$$
dx=e^tdt,
\qquad dy=-e^{-t}dt,
\qquad dz=a^t\ln a\,dt.
$$

于是

$$
ydx-xdy=1\,dt+1\,dt=2dt.
$$

并且

$$
x^2+y^2=e^{2t}+e^{-2t}.
$$

所以

$$
I=\int_0^1\left[2+(e^{2t}+e^{-2t})a^t\ln a\right]dt.
$$

若 $a>0$ 且 $a\ne e^{\pm2}$，则

$$
\boxed{
I=2+\\ln a\left({ae^2-1\over \ln(ae^2)}+{a/e^2-1\over \ln(a/e^2)}\right)
}.
$$

当分母为 $0$ 时按极限理解。

---

### (4)

题意辨认为：

$$
\int_L x\,dx+y\,dy+(x+y-1)\,dz,
$$

其中 $L$ 是从 $(1,1,1)$ 到 $(2,3,4)$ 的直线段。

参数化：

$$
x=1+t,
\qquad y=1+2t,
\qquad z=1+3t,
\qquad 0\le t\le1.
$$

于是

$$
dx=dt,
\qquad dy=2dt,
\qquad dz=3dt.
$$

积分为

$$
\begin{aligned}
I
&=\int_0^1\left[(1+t)+2(1+2t)+3\{(1+t)+(1+2t)-1\}\right]dt \\
&=\int_0^1(6+14t)\,dt \\
&=13.
\end{aligned}
$$

故

$$
\boxed{I=13}.
$$

---

### (5)

题意辨认为：

$$
\int_L y\,dx+z\,dy+x\,dz,
$$

其中 $L$ 为

$$
x^2+y^2+z^2=2az,
\qquad x+z=a,
\qquad a>0
$$

的交线，方向为从 $z$ 轴正方向看去逆时针。

把积分看成向量场

$$
\mathbf F=(y,z,x)
$$

沿闭曲线 $L$ 的环流：

$$
\oint_L y\,dx+z\,dy+x\,dz
=\oint_L\mathbf F\cdot d\mathbf r.
$$

因为 $L$ 是闭合曲线，可以用 Stokes 公式：

$$
\oint_L\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot \mathbf n\,dS,
$$

其中 $S$ 可以取平面 $x+z=a$ 内、由 $L$ 围成的圆盘。

先算旋度：

$$
\nabla\times\mathbf F
=\begin{vmatrix}
\mathbf i&\mathbf j&\mathbf k\\
\partial_x&\partial_y&\partial_z\\
y&z&x
\end{vmatrix}
=(-1,-1,-1).
$$

再看几何区域。球面

$$
x^2+y^2+z^2=2az
$$

可写为

$$
x^2+y^2+(z-a)^2=a^2.
$$

这是以

$$
(0,0,a)
$$

为球心、半径为 $a$ 的球。

平面

$$
x+z=a
$$

通过球心，因为球心满足

$$
0+a=a.
$$

所以交线 $L$ 是球的大圆，半径为

$$
a.
$$

圆盘面积为

$$
\pi a^2.
$$

平面 $x+z=a$ 的法向量可取

$$
(1,0,1).
$$

题目说从 $z$ 轴正方向看去为逆时针。这个方向对应法向量的 $z$ 分量为正，因此取单位法向

$$
\mathbf n={1\over\sqrt2}(1,0,1).
$$

于是

$$
(\nabla\times\mathbf F)\cdot\mathbf n
=(-1,-1,-1)\cdot {1\over\sqrt2}(1,0,1)
=-{2\over\sqrt2}
=-\sqrt2.
$$

因此

$$
\begin{aligned}
I
&=\iint_S(\nabla\times\mathbf F)\cdot \mathbf n\,dS \\
&=-\sqrt2\,\iint_SdS \\
&=-\sqrt2\,\pi a^2.
\end{aligned}
$$

所以

$$
\boxed{I=-\sqrt2\pi a^2}.
$$

为什么可以这样算：

- 原积分是闭曲线上的第二型曲线积分，也就是向量场环流；
- 闭曲线 $L$ 是某个曲面 $S$ 的边界；
- Stokes 公式允许把边界上的环流换成曲面上的旋度通量；
- 这里旋度是常向量，曲面又可以选成最简单的平面圆盘，所以只剩下“常数乘圆盘面积”。

若方向取反，答案也取反，即

$$
\sqrt2\pi a^2.
$$

---

### (6)

题意辨认为：

$$
\int_L (y-z)dx+(z-x)dy+(x-y)dz,
$$

其中 $L$ 为

$$
x^2+y^2+z^2=1,
\qquad y=x\tan\alpha,
\qquad 0<\alpha<\pi/2
$$

的交线，从 $x$ 轴方向看去为逆时针方向。

令

$$
\mathbf F=(y-z,z-x,x-y).
$$

则

$$
\nabla\times\mathbf F=(-2,-2,-2).
$$

曲线是过原点平面截单位球得到的大圆，面积为 $\pi$。从 $+x$ 轴方向看去逆时针，对应单位法向可取

$$
\mathbf n=(\sin\alpha,-\cos\alpha,0).
$$

于是

$$
I=(-2,-2,-2)\cdot(\sin\alpha,-\cos\alpha,0)\pi.
$$

所以

$$
\boxed{I=2\pi(\cos\alpha-\sin\alpha)}.
$$

如果课堂约定“从 $x$ 轴看”指从负 $x$ 轴方向看，则答案差一个负号。

---

## 4. 变力做功题

题意：质点沿抛物线

$$
y^2=1-x
$$

从点

$$
(1,0)
$$

运动到点

$$
(0,1).
$$

力场方向沿纵轴负方向，大小等于作用点横坐标的平方。

因此力场为

$$
\mathbf F=(0,-x^2).
$$

做功为第二型曲线积分：

$$
W=\int_L\mathbf F\cdot d\mathbf r.
$$

因为

$$
d\mathbf r=(dx,dy),
$$

所以

$$
\mathbf F\cdot d\mathbf r=(0,-x^2)\cdot(dx,dy)=-x^2\,dy.
$$

路径为

$$
y^2=1-x.
$$

从 $(1,0)$ 到 $(0,1)$ 时，可以用 $y$ 作参数：

$$
x=1-y^2,
\qquad 0\le y\le1.
$$

于是

$$
W=-\int_0^1x^2\,dy
=-\int_0^1(1-y^2)^2\,dy.
$$

展开：

$$
(1-y^2)^2=1-2y^2+y^4.
$$

所以

$$
\begin{aligned}
W
&=-\int_0^1(1-2y^2+y^4)\,dy \\
&=-\left[y-{2\over3}y^3+{1\over5}y^5\right]_0^1 \\
&=-\left(1-{2\over3}+{1\over5}\right) \\
&=-{8\over15}.
\end{aligned}
$$

因此力场所做的功为

$$
\boxed{W=-{8\over15}}.
$$

结果为负，说明力场方向向下，而质点整体从 $y=0$ 到 $y=1$ 向上运动，力与位移方向相反，所以做负功。

---

# 作业 12.5：曲面积分

## 1. 求下列曲面的面积

### (1)

题意辨认为：曲面

$$
z=axy
$$

包含在圆柱面

$$
x^2+y^2=a^2
$$

内部的部分。

曲面面积公式：

$$
S=\iint_D\sqrt{1+z_x^2+z_y^2}\,dA.
$$

这里

$$
z_x=ay,
\qquad z_y=ax,
$$

所以

$$
\sqrt{1+z_x^2+z_y^2}=\sqrt{1+a^2(x^2+y^2)}.
$$

区域 $D$ 是圆盘 $r\le a$。于是

$$
\begin{aligned}
S
&=\int_0^{2\pi}\int_0^a\sqrt{1+a^2r^2}\,r\,dr\,d\theta \\
&=2\pi\int_0^a r\sqrt{1+a^2r^2}\,dr \\
&={2\pi\over3a^2}\left[(1+a^4)^{3/2}-1\right].
\end{aligned}
$$

故

$$
\boxed{S={2\pi\over3a^2}\left[(1+a^4)^{3/2}-1\right]}.
$$

---

### (2)

题意辨认为：锥面

$$
x^2+y^2={1\over3}z^2,
\qquad z>0
$$

被平面

$$
x+y+z=2a
$$

截成的部分。

可用参数

$$
x=r\cos\theta,
\qquad y=r\sin\theta,
\qquad z=\sqrt3r.
$$

平面条件给出

$$
r(\cos\theta+\sin\theta+\sqrt3)=2a,
$$

所以

$$
0\le r\le {2a\over \sqrt3+\cos\theta+\sin\theta}.
$$

锥面的面积元：

$$
dS=\sqrt{1+z_x^2+z_y^2}\,dxdy=2\,dxdy=2r\,dr\,d\theta.
$$

因此面积为

$$
\boxed{
S=\int_0^{2\pi}\int_0^{2a/(\sqrt3+\cos\theta+\sin\theta)}2r\,dr\,d\theta
=4a^2\int_0^{2\pi}{d\theta\over(\sqrt3+\cos\theta+\sin\theta)^2}
}.
$$

若需要闭式，可继续用 $\cos\theta+\sin\theta=\sqrt2\cos(\theta-\pi/4)$ 的标准积分。

---

### (3)

题意辨认为：球面

$$
x^2+y^2+z^2=a^2
$$

包含在锥面

$$
z=\sqrt{x^2+y^2}
$$

内部的部分。

锥面对应球坐标中的

$$
\theta={\pi\over4}.
$$

球面在锥内上方的球冠满足

$$
0\le\theta\le {\pi\over4}.
$$

面积为

$$
S=\int_0^{2\pi}\int_0^{\pi/4}a^2\sin\theta\,d\theta\,d\varphi.
$$

所以

$$
\boxed{S=2\pi a^2\left(1-{\sqrt2\over2}\right)}.
$$

---

### (4)

题意辨认为：圆柱面

$$
x^2+y^2=a^2
$$

被平面

$$
x+z=0,
\qquad x-z=0
$$

截得的第一卦限部分，$x>0,y>0$。

参数化：

$$
x=a\cos\theta,
\qquad y=a\sin\theta,
\qquad 0\le\theta\le {\pi\over2}.
$$

两个平面给出

$$
-a\cos\theta\le z\le a\cos\theta.
$$

圆柱面面积元为

$$
dS=a\,d\theta\,dz.
$$

于是

$$
S=\int_0^{\pi/2}\int_{-a\cos\theta}^{a\cos\theta}a\,dz\,d\theta
=2a^2\int_0^{\pi/2}\cos\theta\,d\theta.
$$

故

$$
\boxed{S=2a^2}.
$$

---

### (5)

题意辨认为：抛物面

$$
x^2+y^2=2az
$$

包含在柱面

$$
(x^2+y^2)^2=2a^2xy
$$

内的部分。

抛物面写作

$$
z={r^2\over2a}.
$$

面积元为

$$
dS=\sqrt{1+{r^2\over a^2}}\,r\,dr\,d\theta.
$$

柱面在极坐标中为

$$
r^4=2a^2r^2\cos\theta\sin\theta,
$$

即

$$
r^2=a^2\sin2\theta.
$$

有效范围为

$$
0\le\theta\le {\pi\over2},
\qquad 0\le r\le a\sqrt{\sin2\theta}.
$$

因此面积为

$$
\boxed{
S=\int_0^{\pi/2}\int_0^{a\sqrt{\sin2\theta}}
\sqrt{1+{r^2\over a^2}}\,r\,dr\,d\theta
}
$$

也可先对 $r$ 积分：

$$
\boxed{
S={a^2\over3}\int_0^{\pi/2}\left[(1+\sin2\theta)^{3/2}-1\right]d\theta
}.
$$

---

### (6)

题意辨认为：环面

$$
x=(b+a\cos\theta)\cos\varphi,
\qquad y=(b+a\cos\theta)\sin\varphi,
\qquad z=a\sin\theta,
$$

其中

$$
0\le\theta\le2\pi,
\qquad 0\le\varphi\le2\pi,
\qquad 0<a<b.
$$

这是标准环面。面积元为

$$
dS=a(b+a\cos\theta)\,d\theta\,d\varphi.
$$

所以

$$
S=\int_0^{2\pi}\int_0^{2\pi}a(b+a\cos\theta)\,d\theta\,d\varphi=4\pi^2ab.
$$

故

$$
\boxed{S=4\pi^2ab}.
$$

---

## 2. 第一型曲面积分

### (1)

题意辨认为：

$$
\iint_S(x+y+z)\,dS,
$$

其中 $S$ 是球面

$$
x^2+y^2+z^2=a^2
$$

在半空间 $y\le0$ 中的部分。

由对称性：

$$
\iint_Sx\,dS=0,
\qquad \iint_Sz\,dS=0.
$$

而半球 $y\le0$ 上

$$
\iint_S y\,dS=-\pi a^3.
$$

所以

$$
\boxed{I=-\pi a^3}.
$$

---

### (2)

题意辨认为：

$$
\iint_S(x^2+y^2)\,dS,
$$

其中 $S$ 是区域

$$
\sqrt{x^2+y^2}\le z\le1
$$

的边界。

边界由圆锥面 $z=r$ 和顶面圆盘 $z=1$ 组成。

圆锥面上

$$
dS=\sqrt2\,r\,dr\,d\theta,
\qquad 0\le r\le1.
$$

顶面圆盘上

$$
dS=r\,dr\,d\theta.
$$

所以

$$
\begin{aligned}
I
&=\int_0^{2\pi}\int_0^1r^2\sqrt2\,r\,dr\,d\theta
+\int_0^{2\pi}\int_0^1r^2r\,dr\,d\theta \\
&={\pi\sqrt2\over2}+{\pi\over2}.
\end{aligned}
$$

故

$$
\boxed{I={\pi\over2}(1+\sqrt2)}.
$$

---

### (3)

题意辨认为：

$$
\iint_S(xy+yz+zx)\,dS,
$$

其中 $S$ 是锥面

$$
z=\sqrt{x^2+y^2}
$$

被柱面

$$
x^2+y^2=2ax
$$

截得的部分。

在极坐标中 $z=r$，柱面为

$$
r=2a\cos\theta,
\qquad -{\pi\over2}\le\theta\le {\pi\over2}.
$$

有

$$
dS=\sqrt2\,r\,dr\,d\theta.
$$

被积函数为

$$
xy+yz+zx=r^2\cos\theta\sin\theta+r^2\sin\theta+r^2\cos\theta.
$$

因此

$$
I=\sqrt2\int_{-\pi/2}^{\pi/2}\int_0^{2a\cos\theta}
\left(r^2\cos\theta\sin\theta+r^2\sin\theta+r^2\cos\theta\right)r\,dr\,d\theta.
$$

含 $\sin\theta$ 的奇函数项积分为零，剩下

$$
I=\sqrt2\int_{-\pi/2}^{\pi/2}\cos\theta\cdot { (2a\cos\theta)^4\over4}\,d\theta.
$$

所以

$$
I=4\sqrt2 a^4\int_{-\pi/2}^{\pi/2}\cos^5\theta\,d\theta.
$$

而

$$
\int_{-\pi/2}^{\pi/2}\cos^5\theta\,d\theta={16\over15}.
$$

故

$$
\boxed{I={64\sqrt2\over15}a^4}.
$$

---

### (4)

题意辨认为：

$$
\iint_S{1\over x^2+y^2+z^2}\,dS,
$$

其中 $S$ 是圆柱面

$$
x^2+y^2=a^2
$$

介于平面 $z=0$ 和 $z=12$ 之间的部分。

圆柱面参数为

$$
x=a\cos\theta,
\qquad y=a\sin\theta,
\qquad 0\le z\le12.
$$

面积元

$$
dS=a\,d\theta\,dz.
$$

所以

$$
\begin{aligned}
I
&=\int_0^{2\pi}\int_0^{12}{a\over a^2+z^2}\,dz\,d\theta \\
&=2\pi\arctan{12\over a}.
\end{aligned}
$$

故

$$
\boxed{I=2\pi\arctan{12\over a}}.
$$

---

### (5)

题意辨认为：

$$
\iint_S\left({x^2\over7}+{y^2\over5}+{z^2\over4}\right)dS,
$$

其中 $S$ 是球面

$$
x^2+y^2+z^2=a^2.
$$

球面对称性给出

$$
\iint_Sx^2dS=\iint_Sy^2dS=\iint_Sz^2dS.
$$

三者之和为

$$
\iint_S(x^2+y^2+z^2)dS=a^2\cdot4\pi a^2=4\pi a^4.
$$

所以每一个为

$$
{4\pi a^4\over3}.
$$

于是

$$
I={4\pi a^4\over3}\left({1\over7}+{1\over5}+{1\over4}\right).
$$

括号中

$$
{1\over7}+{1\over5}+{1\over4}={83\over140}.
$$

故

$$
\boxed{I={83\pi a^4\over105}}.
$$

---

### (6)

题意辨认为：

$$
\iint_S(x^2+y^2+z)\,dS,
$$

其中 $S$ 是抛物面

$$
z=x^2+y^2
$$

介于 $z=0$ 和 $z=8$ 之间的部分。

用柱坐标，$z=r^2$，$0\le r\le\sqrt8$。面积元

$$
dS=\sqrt{1+4r^2}\,r\,dr\,d\theta.
$$

被积函数

$$
x^2+y^2+z=r^2+r^2=2r^2.
$$

因此

$$
I=\int_0^{2\pi}\int_0^{\sqrt8}2r^2\sqrt{1+4r^2}\,r\,dr\,d\theta.
$$

即

$$
I=4\pi\int_0^{\sqrt8}r^3\sqrt{1+4r^2}\,dr.
$$

令 $u=1+4r^2$，则 $r^3dr=(u-1)du/32$，上下限为 $1$ 到 $33$，所以

$$
\boxed{
I={\pi\over8}\left[{2\over5}u^{5/2}-{2\over3}u^{3/2}\right]_{1}^{33}
}.
$$

---

### (7)

题意辨认为：

$$
\iint_S z\,dS,
$$

其中 $S$ 是螺旋面

$$
x=u\cos v,
\qquad y=u\sin v,
\qquad z=v,
\qquad 0\le u\le a,
\qquad 0\le v\le2\pi.
$$

计算面积元：

$$
\left|\mathbf r_u\times\mathbf r_v\right|=\sqrt{1+u^2}.
$$

所以

$$
\begin{aligned}
I
&=\int_0^{2\pi}\int_0^a v\sqrt{1+u^2}\,du\,dv \\
&=\left(\int_0^{2\pi}v\,dv\right)
\left(\int_0^a\sqrt{1+u^2}\,du\right) \\
&=2\pi^2\cdot {1\over2}\left(a\sqrt{1+a^2}+\operatorname{arsinh}a\right).
\end{aligned}
$$

故

$$
\boxed{I=\pi^2\left(a\sqrt{1+a^2}+\operatorname{arsinh}a\right)}.
$$

---

## 3. 球面投影面积题

题意辨认为：球面 $S$ 半径为 $R$，问球面在三个坐标平面上的投影面积。

对于半径为 $R$ 的球面，其在任一坐标平面上的正交投影都是半径为 $R$ 的圆盘，所以投影面积均为

$$
\boxed{\pi R^2}.
$$

如果题目问的是“带重数的投影面积”，即积分

$$
\iint_S |\cos\gamma|\,dS,
$$

则每个方向为

$$
\boxed{2\pi R^2}.
$$

需要根据教材中“投影面积”的定义核对。

---

## 4. 上半椭球面上的积分

题意辨认为：$S$ 为上半椭球面

$$
{x^2\over2}+{y^2\over2}+z^2=1,
\qquad z\ge0,
$$

$P(x,y,z)$ 处密度为点到原点到平面 $xOy$ 的距离，求

$$
\iint_S {z\over \rho(x,y,z)}\,dS,
$$

其中

$$
\rho(x,y,z)=\sqrt{x^2+y^2+z^2}.
$$

写成图形

$$
z=\sqrt{1-{x^2+y^2\over2}}.
$$

令 $r^2=x^2+y^2$，则 $0\le r\le\sqrt2$，并且

$$
z=\sqrt{1-{r^2\over2}}.
$$

有

$$
\rho=\sqrt{r^2+z^2}=\sqrt{1+{r^2\over2}}.
$$

又

$$
dS=\sqrt{1+z_x^2+z_y^2}\,dA
={\sqrt{4-r^2}\over 2z}\,dA.
$$

所以

$$
{z\over\rho}dS
={\sqrt{4-r^2}\over 2\sqrt{1+r^2/2}}\,dA.
$$

故

$$
\boxed{
I=2\pi\int_0^{\sqrt2}
{r\sqrt{4-r^2}\over 2\sqrt{1+r^2/2}}\,dr
}.
$$

也可写成

$$
\boxed{
I=\pi\int_0^2\sqrt{{4-u\over 2+u}}\,du
}
$$

其中 $u=r^2$。

---

## 5. 第二型曲面积分

把

$$
\iint_S P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

看成向量场

$$
\mathbf F=(P,Q,R)
$$

的通量积分。

---

### (1)

题意辨认为：

$$
\iint_S (x+y)\,dy\,dz+(y+z)\,dz\,dx+(z+x)\,dx\,dy,
$$

其中 $S$ 是以原点为中心、边长为 $2h$ 的立方体表面，方向取外侧。

令

$$
\mathbf F=(x+y,y+z,z+x).
$$

则

$$
\nabla\cdot\mathbf F=1+1+1=3.
$$

由 Gauss 公式：

$$
I=\iiint_V3\,dV=3(2h)^3=24h^3.
$$

故

$$
\boxed{I=24h^3}.
$$

---

### (2)

题意辨认为：

$$
\iint_S yz\,dz\,dx,
$$

其中 $S$ 是椭球面

$$
{x^2\over a^2}+{y^2\over b^2}+{z^2\over c^2}=1
$$

的上半部分，方向取上侧。

把它看成向量场

$$
\mathbf F=(0,yz,0)
$$

通过上半椭球面的通量。

用上半椭球与底面 $z=0$ 围成闭曲面。底面上法向沿 $-z$，而 $\mathbf F$ 没有 $z$ 分量，所以底面通量为 $0$。

因此所求等于闭曲面通量。

由 Gauss 公式：

$$
\nabla\cdot\mathbf F={\partial(yz)\over\partial y}=z.
$$

令

$$
x=au,
\qquad y=bv,
\qquad z=cw.
$$

则上半单位球中

$$
\iiint z\,dV=abc\cdot c\iiint_{u^2+v^2+w^2\le1,w\ge0}w\,du\,dv\,dw.
$$

单位上半球中

$$
\iiint w\,dV={\pi\over4}.
$$

所以

$$
\boxed{I={\pi ab c^2\over4}}.
$$

---

### (3)

题意辨认为：

$$
\iint_S z\,dy\,dz+x\,dz\,dx+y\,dx\,dy,
$$

其中 $S$ 是柱面

$$
x^2+y^2=1
$$

被平面 $z=0$ 和 $z=h$ 截得的侧面，方向取外侧。

向量场为

$$
\mathbf F=(z,x,y).
$$

柱面参数化：

$$
x=\cos\theta,
\qquad y=\sin\theta,
\qquad 0\le z\le h.
$$

外法向为

$$
\mathbf n=(\cos\theta,\sin\theta,0).
$$

所以

$$
\mathbf F\cdot\mathbf n=z\cos\theta+x\sin\theta
=z\cos\theta+\cos\theta\sin\theta.
$$

对 $0\le\theta\le2\pi$ 积分均为零，因此

$$
\boxed{I=0}.
$$

---

### (4)

题意辨认为：

$$
\iint_S 8x\,dy\,dz+3b\,dx\,dy,
$$

其中 $S$ 是抛物面

$$
z=4-x^2-y^2,
\qquad z\ge0,
$$

方向取上侧。

向量场为

$$
\mathbf F=(8x,0,3b).
$$

用抛物面加底面 $z=0$ 构成闭曲面。闭曲面外侧中，抛物面方向正是上侧。

散度：

$$
\nabla\cdot\mathbf F=8.
$$

体积为

$$
V=\int_0^{2\pi}\int_0^2(4-r^2)r\,dr\,d\theta=8\pi.
$$

闭曲面通量为

$$
8V=64\pi.
$$

底面 $z=0$ 外法向向下，通量为

$$
\iint_D\mathbf F\cdot(0,0,-1)\,dA=-3b\cdot \pi(2)^2=-12\pi b.
$$

所以抛物面上通量

$$
I=64\pi-(-12\pi b)=64\pi+12\pi b.
$$

故

$$
\boxed{I=64\pi+12\pi b}.
$$

---

### (5)

题意辨认不完全可靠。形式大约为

$$
\iint_S [f(x,y,z)+x]dy dz+[z f(x,y,z)+y]dz dx+[f(x,y,z)+z]dxdy,
$$

其中 $f$ 满足某个条件，$S$ 是平面 $x-y+z=1$ 在第一卦限中的部分，方向取上侧。

此题需要先确认 $f$ 的条件。若使用第二型曲面积分，第一步仍是设

$$
\mathbf F=(P,Q,R)
$$

然后取平面上侧法向。平面写成

$$
z=1-x+y.
$$

上侧有向面积元为

$$
\mathbf n\,dS=(-z_x,-z_y,1)dxdy=(1,-1,1)dxdy.
$$

积分化为

$$
\iint_D \mathbf F(x,y,1-x+y)\cdot(1,-1,1)\,dxdy.
$$

区域 $D$ 为第一卦限截面在 $xy$ 平面上的投影，需要由

$$
x\ge0,
\qquad y\ge0,
\qquad z=1-x+y\ge0
$$

确定。

---

### (6)

题意辨认为：

$$
\iint_S x^2\,dy\,dz+y^2\,dz\,dx+(z^2+5)\,dx\,dy,
$$

其中 $S$ 是锥面

$$
z=\sqrt{x^2+y^2},
\qquad 0\le z\le h,
$$

方向取下侧。

向量场：

$$
\mathbf F=(x^2,y^2,z^2+5).
$$

用锥面和顶面圆盘 $z=h$ 构成闭曲面。对实心圆锥 $0\le r\le z\le h$，外法向在锥面上正是“下侧”。

散度：

$$
\nabla\cdot\mathbf F=2x+2y+2z.
$$

体内 $x,y$ 项由对称性积分为零，所以闭曲面通量为

$$
\iiint_V2z\,dV
=2\int_0^h z\cdot \pi z^2\,dz
={\pi h^4\over2}.
$$

顶面圆盘 $z=h$ 的外法向向上，通量为

$$
\iint_{r\le h}(h^2+5)dA=\pi h^2(h^2+5).
$$

故锥面通量为

$$
I={\pi h^4\over2}-\pi h^2(h^2+5)
=-{\pi h^4\over2}-5\pi h^2.
$$

所以

$$
\boxed{I=-{\pi h^4\over2}-5\pi h^2}.
$$

---

### (7)、(8)

这两题的字迹和分母表达式不够清楚，暂不直接给数值。解法框架如下：

- 先把第二型曲面积分写成通量

$$
\iint_S\mathbf F\cdot\mathbf n\,dS.
$$

- 如果 $S$ 是闭曲面，优先用 Gauss 公式：

$$
\iint_S\mathbf F\cdot\mathbf n\,dS=\iiint_V\nabla\cdot\mathbf F\,dV.
$$

- 如果 $S$ 是图形曲面 $z=f(x,y)$ 且方向取上侧，直接用

$$
\mathbf n\,dS=(-f_x,-f_y,1)dxdy.
$$

- 如果题中有椭球面

$$
{x^2\over a^2}+{y^2\over b^2}+{z^2\over c^2}=1,
$$

并取外侧，通常优先尝试椭球变换

$$
x=au,
\qquad y=bv,
\qquad z=cw.
$$

---

### (9)

题意辨认为：

$$
\iint_S x^2\,dy\,dz+y^2\,dz\,dx+z^2\,dx\,dy,
$$

其中 $S$ 是球面

$$
(x-a)^2+(y-b)^2+(z-c)^2=R^2,
$$

方向取外侧。

向量场为

$$
\mathbf F=(x^2,y^2,z^2).
$$

散度为

$$
\nabla\cdot\mathbf F=2x+2y+2z.
$$

球心为 $(a,b,c)$。球内积分中

$$
\iiint_Vx\,dV=a\operatorname{Vol}(V),
$$

同理对 $y,z$ 也成立。

球体积为

$$
{4\over3}\pi R^3.
$$

因此

$$
\begin{aligned}
I
&=\iiint_V(2x+2y+2z)dV \\
&=2(a+b+c){4\over3}\pi R^3.
\end{aligned}
$$

故

$$
\boxed{I={8\pi R^3\over3}(a+b+c)}.
$$

---

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

## 计算 \(4b\int_0^1\sqrt{a^2+(b^2-a^2)x^2}\,dx\)

要计算

$$
I=4b\int_0^1\sqrt{a^2+(b^2-a^2)x^2}\,dx.
$$

这个积分需要按 $a,b$ 的大小分情况，因为根号内是

$$
a^2+(b^2-a^2)x^2.
$$

---

### 一、积分表法

#### 情况 1：\(b>a\)

令

$$
k=\sqrt{b^2-a^2}>0.
$$

则

$$
\sqrt{a^2+(b^2-a^2)x^2}=\sqrt{a^2+k^2x^2}.
$$

用积分表公式

$$
\int \sqrt{a^2+k^2x^2}\,dx
={x\over2}\sqrt{a^2+k^2x^2}
+{a^2\over2k}\ln\left(kx+\sqrt{a^2+k^2x^2}\right)+C.
$$

也常写成

$$
\int \sqrt{a^2+k^2x^2}\,dx
={x\over2}\sqrt{a^2+k^2x^2}
+{a^2\over2k}\operatorname{arsinh}{kx\over a}+C.
$$

定积分为

$$
\begin{aligned}
\int_0^1\sqrt{a^2+k^2x^2}\,dx
&=\left[{x\over2}\sqrt{a^2+k^2x^2}
+{a^2\over2k}\operatorname{arsinh}{kx\over a}\right]_0^1 \\
&={1\over2}\sqrt{a^2+k^2}+{a^2\over2k}\operatorname{arsinh}{k\over a}.
\end{aligned}
$$

因为

$$
\sqrt{a^2+k^2}=b,
$$

所以

$$
\int_0^1\sqrt{a^2+k^2x^2}\,dx
={b\over2}+{a^2\over2k}\operatorname{arsinh}{k\over a}.
$$

乘上 $4b$，得到

$$
\boxed{
I=2b^2+{2a^2b\over\sqrt{b^2-a^2}}\operatorname{arsinh}{\sqrt{b^2-a^2}\over a}
}
\qquad (b>a).
$$

由于

$$
\operatorname{arsinh}u=\ln(u+\sqrt{1+u^2}),
$$

也可写成

$$
\boxed{
I=2b^2+{2a^2b\over\sqrt{b^2-a^2}}
\ln{b+\sqrt{b^2-a^2}\over a}
}
\qquad (b>a).
$$

---

#### 情况 2：\(a>b\)

令

$$
k=\sqrt{a^2-b^2}>0.
$$

则

$$
\sqrt{a^2+(b^2-a^2)x^2}=\sqrt{a^2-k^2x^2}.
$$

用积分表公式

$$
\int\sqrt{a^2-k^2x^2}\,dx
={x\over2}\sqrt{a^2-k^2x^2}
+{a^2\over2k}\arcsin{kx\over a}+C.
$$

所以

$$
\begin{aligned}
\int_0^1\sqrt{a^2-k^2x^2}\,dx
&=\left[{x\over2}\sqrt{a^2-k^2x^2}
+{a^2\over2k}\arcsin{kx\over a}\right]_0^1 \\
&={1\over2}\sqrt{a^2-k^2}+{a^2\over2k}\arcsin{k\over a}.
\end{aligned}
$$

因为

$$
\sqrt{a^2-k^2}=b,
$$

所以

$$
\int_0^1\sqrt{a^2-k^2x^2}\,dx
={b\over2}+{a^2\over2k}\arcsin{k\over a}.
$$

乘上 $4b$，得到

$$
\boxed{
I=2b^2+{2a^2b\over\sqrt{a^2-b^2}}\arcsin{\sqrt{a^2-b^2}\over a}
}
\qquad (a>b).
$$

因为

$$
\arcsin{\sqrt{a^2-b^2}\over a}=\arccos{b\over a},
$$

也可写成

$$
\boxed{
I=2b^2+{2a^2b\over\sqrt{a^2-b^2}}\arccos{b\over a}
}
\qquad (a>b).
$$

---

#### 情况 3：\(a=b\)

若 $a=b$，则

$$
\sqrt{a^2+(b^2-a^2)x^2}=\sqrt{a^2}=a.
$$

所以

$$
I=4b\int_0^1a\,dx=4ab=4a^2.
$$

即

$$
\boxed{I=4a^2}\qquad(a=b).
$$

---

### 二、换元积分法

---

#### 情况 1：\(b>a\)

仍令

$$
k=\sqrt{b^2-a^2}.
$$

要算

$$
J=\int_0^1\sqrt{a^2+k^2x^2}\,dx.
$$

使用三角换元

$$
kx=a\tan\theta,
\qquad x={a\over k}\tan\theta.
$$

则

$$
dx={a\over k}\sec^2\theta\,d\theta,
$$

并且

$$
\sqrt{a^2+k^2x^2}=a\sec\theta.
$$

当 $x=0$ 时，$\theta=0$；当 $x=1$ 时，

$$
\tan\theta_1={k\over a}.
$$

因此

$$
\sec\theta_1={\sqrt{a^2+k^2}\over a}={b\over a}.
$$

于是

$$
\begin{aligned}
J
&=\int_0^{\theta_1}a\sec\theta\cdot {a\over k}\sec^2\theta\,d\theta \\
&={a^2\over k}\int_0^{\theta_1}\sec^3\theta\,d\theta.
\end{aligned}
$$

用公式

$$
\int\sec^3\theta\,d\theta
={1\over2}\left(\sec\theta\tan\theta+
\ln|\sec\theta+	an\theta|\right)+C.
$$

所以

$$
\begin{aligned}
J
&={a^2\over2k}\left[\sec\theta\tan\theta+
\ln(\sec\theta+	an\theta)\right]_0^{\theta_1} \\
&={a^2\over2k}\left({b\over a}{k\over a}
+\ln{b+k\over a}\right) \\
&={b\over2}+{a^2\over2k}\ln{b+k\over a}.
\end{aligned}
$$

乘上 $4b$：

$$
\boxed{
I=2b^2+{2a^2b\over\sqrt{b^2-a^2}}
\ln{b+\sqrt{b^2-a^2}\over a}
}
\qquad(b>a).
$$

---

#### 情况 2：\(a>b\)

令

$$
k=\sqrt{a^2-b^2}.
$$

要算

$$
J=\int_0^1\sqrt{a^2-k^2x^2}\,dx.
$$

使用换元

$$
kx=a\sin\theta,
\qquad x={a\over k}\sin\theta.
$$

则

$$
dx={a\over k}\cos\theta\,d\theta,
$$

并且

$$
\sqrt{a^2-k^2x^2}=a\cos\theta.
$$

当 $x=0$ 时，$\theta=0$；当 $x=1$ 时，

$$
\sin\theta_1={k\over a},
\qquad
\cos\theta_1={b\over a}.
$$

于是

$$
\begin{aligned}
J
&=\int_0^{\theta_1}a\cos\theta\cdot {a\over k}\cos\theta\,d\theta \\
&={a^2\over k}\int_0^{\theta_1}\cos^2\theta\,d\theta \\
&={a^2\over k}\int_0^{\theta_1}{1+\cos2\theta\over2}\,d\theta \\
&={a^2\over2k}\left[\theta+\sin\theta\cos\theta\right]_0^{\theta_1} \\
&={a^2\over2k}\left(\theta_1+{k\over a}{b\over a}\right) \\
&={a^2\over2k}\arcsin{k\over a}+{b\over2}.
\end{aligned}
$$

乘上 $4b$：

$$
\boxed{
I=2b^2+{2a^2b\over\sqrt{a^2-b^2}}\arcsin{\sqrt{a^2-b^2}\over a}
}
\qquad(a>b).
$$

也就是

$$
\boxed{
I=2b^2+{2a^2b\over\sqrt{a^2-b^2}}\arccos{b\over a}
}
\qquad(a>b).
$$

---

### 三、总结

$$
I=4b\int_0^1\sqrt{a^2+(b^2-a^2)x^2}\,dx.
$$

若

$$
b>a,
$$

则

$$
\boxed{
I=2b^2+{2a^2b\over\sqrt{b^2-a^2}}
\ln{b+\sqrt{b^2-a^2}\over a}
}.
$$

若

$$
a>b,
$$

则

$$
\boxed{
I=2b^2+{2a^2b\over\sqrt{a^2-b^2}}\arccos{b\over a}
}.
$$

若

$$
a=b,
$$

则

$$
\boxed{I=4a^2}.
$$

---

## 核对：12.4 3(5) 环流本来就是 \(\mathbf F\cdot\mathbf T\,ds\)

第二型曲线积分

$$
\oint_L P\,dx+Q\,dy+R\,dz
$$

本质上就是

$$
\oint_L \mathbf F\cdot d\mathbf r,
$$

其中

$$
\mathbf F=(P,Q,R),
\qquad d\mathbf r=(dx,dy,dz).
$$

如果用参数方程

$$
\mathbf r(t)=(x(t),y(t),z(t)),
$$

则

$$
d\mathbf r=\mathbf r'(t)dt.
$$

因此

$$
\oint_L \mathbf F\cdot d\mathbf r
=\int \mathbf F(\mathbf r(t))\cdot \mathbf r'(t)\,dt.
$$

又因为

$$
\mathbf r'(t)=\mathbf T {ds\over dt},
$$

所以

$$
\mathbf F\cdot \mathbf r'(t)dt
=\mathbf F\cdot\mathbf T\,ds.
$$

也就是说，环流确实是“向量场沿切线方向的分量”乘弧长元。

Stokes 公式不是改变环流的定义，而是说对于闭曲线：

$$
\oint_L\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

左边是切向积分，右边是旋度通量。二者相等。

---

### 直接用切向量参数化验证 12.4 3(5)

题目中

$$
\mathbf F=(y,z,x).
$$

曲线为球

$$
x^2+y^2+(z-a)^2=a^2
$$

与平面

$$
x+z=a
$$

的交线。

平面法向取

$$
\mathbf n={1\over\sqrt2}(1,0,1),
$$

它的 $z$ 分量为正，对应“从 $z$ 轴正方向看去逆时针”。

取平面内一组正向正交基

$$
\mathbf e_1=(0,1,0),
\qquad
\mathbf e_2=\left(-{1\over\sqrt2},0,{1\over\sqrt2}\right),
$$

它们满足

$$
\mathbf e_1\times\mathbf e_2=\mathbf n.
$$

于是大圆可参数化为

$$
\mathbf r(t)=(0,0,a)+a(\mathbf e_1\cos t+\mathbf e_2\sin t),
\qquad 0\le t\le2\pi.
$$

即

$$
x=-{a\over\sqrt2}\sin t,
\qquad
 y=a\cos t,
\qquad
 z=a+{a\over\sqrt2}\sin t.
$$

在 $xy$ 平面投影中，$t=0$ 时点在 $(0,a)$，随后 $x'<0$，也就是从顶点向左走，所以从 $z$ 轴正方向看是逆时针。

求导：

$$
x'=-{a\over\sqrt2}\cos t,
\qquad
 y'=-a\sin t,
\qquad
 z'={a\over\sqrt2}\cos t.
$$

于是

$$
\begin{aligned}
\mathbf F\cdot\mathbf r'
&=y x'+z y'+x z' \\
&=a\cos t\left(-{a\over\sqrt2}\cos t\right)
+\left(a+{a\over\sqrt2}\sin t\right)(-a\sin t)
+\left(-{a\over\sqrt2}\sin t\right)
\left({a\over\sqrt2}\cos t\right) \\
&=-{a^2\over\sqrt2}\cos^2t-a^2\sin t
-{a^2\over\sqrt2}\sin^2t
-{a^2\over2}\sin t\cos t \\
&=-{a^2\over\sqrt2}-a^2\sin t-{a^2\over2}\sin t\cos t.
\end{aligned}
$$

所以

$$
\begin{aligned}
I
&=\int_0^{2\pi}\left(-{a^2\over\sqrt2}-a^2\sin t-{a^2\over2}\sin t\cos t\right)dt \\
&=-{a^2\over\sqrt2}\cdot2\pi \\
&=-\sqrt2\pi a^2.
\end{aligned}
$$

这和 Stokes 公式得到的结果一致：

$$
\boxed{I=-\sqrt2\pi a^2}.
$$

---

## 12.4 3(5)：为什么切向环流可以转换成旋度通量

原题积分是

$$
\oint_L y\,dx+z\,dy+x\,dz.
$$

先把它写成向量形式。令

$$
\mathbf F=(y,z,x),
$$

并且

$$
d\mathbf r=(dx,dy,dz).
$$

那么

$$
\mathbf F\cdot d\mathbf r
=(y,z,x)\\cdot(dx,dy,dz)
=y\,dx+z\,dy+x\,dz.
$$

所以原积分就是

$$
\oint_L\mathbf F\cdot d\mathbf r.
$$

如果曲线用参数方程表示为

$$
\mathbf r(t)=(x(t),y(t),z(t)),
$$

那么

$$
d\mathbf r=\mathbf r'(t)dt.
$$

因此

$$
\oint_L\mathbf F\cdot d\mathbf r
=\int \mathbf F(\mathbf r(t))\cdot\mathbf r'(t)\,dt.
$$

又因为

$$
\mathbf r'(t)=\mathbf T {ds\over dt},
$$

其中 $\mathbf T$ 是单位切向量，所以

$$
\mathbf F(\mathbf r(t))\cdot\mathbf r'(t)\,dt
=\mathbf F\cdot\mathbf T\,ds.
$$

这说明

$$
\oint_L\mathbf F\cdot d\mathbf r
=\oint_L\mathbf F\cdot\mathbf T\,ds.
$$

所以它本质上就是沿曲线切线方向的积分，也就是环流。

---

### 1. Stokes 公式说了什么

Stokes 公式是

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

左边是边界曲线上的切向环流；右边是曲面上的旋度通量。

这里

$$
\partial S=L.
$$

也就是说，只要曲面 $S$ 的边界正好是曲线 $L$，就可以把

$$
\oint_L\mathbf F\cdot d\mathbf r
$$

转换成

$$
\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

注意：这不是说环流的定义变了。环流仍然是切线方向积分。Stokes 公式只是告诉我们，对于闭曲线，切向环流等于它所围曲面上的旋度通量。

---

### 2. 本题为什么能选平面圆盘

本题曲线 $L$ 是两个曲面的交线：

$$
x^2+y^2+z^2=2az,
$$

和

$$
x+z=a.
$$

第一个曲面可写成

$$
x^2+y^2+(z-a)^2=a^2.
$$

这是球心为

$$
(0,0,a)
$$

半径为 $a$ 的球面。

平面

$$
x+z=a
$$

经过球心，因为

$$
0+a=a.
$$

所以它截球面得到的是一个大圆。这个大圆就是 $L$。

既然 $L$ 是平面 $x+z=a$ 上的大圆，那么它自然围成平面内的一个圆盘 $S$。

这个圆盘满足

$$
\partial S=L.
$$

所以 Stokes 公式可以用，并且选这个圆盘最简单。

---

### 3. 方向怎么对应

Stokes 公式要求曲线方向和曲面法向一致。

规则是右手定则：

- 右手大拇指指向曲面法向 $\mathbf n$；
- 四指弯曲方向就是边界曲线的正方向。

题目说：从 $z$ 轴正方向看去，$L$ 为逆时针方向。

因此要选 $z$ 分量为正的法向。

平面

$$
x+z=a
$$

的法向量是

$$
(1,0,1).
$$

它的 $z$ 分量为正，所以取

$$
\mathbf n={1\over\sqrt2}(1,0,1).
$$

这就和题目给的逆时针方向匹配。

---

### 4. 转换后的计算

先算旋度：

$$
\mathbf F=(y,z,x).
$$

所以

$$
\nabla\times\mathbf F
=\begin{vmatrix}
\mathbf i&\mathbf j&\mathbf k\\
\partial_x&\partial_y&\partial_z\\
y&z&x
\end{vmatrix}.
$$

展开：

$$
\nabla\times\mathbf F
=\left({\partial x\over\partial y}-{\partial z\over\partial z},
{\partial y\over\partial z}-{\partial x\over\partial x},
{\partial z\over\partial x}-{\partial y\over\partial y}
\right).
$$

也就是

$$
\nabla\times\mathbf F=(-1,-1,-1).
$$

于是

$$
(\nabla\times\mathbf F)\cdot\mathbf n
=(-1,-1,-1)\cdot {1\over\sqrt2}(1,0,1).
$$

计算得

$$
(\nabla\times\mathbf F)\cdot\mathbf n
=-{2\over\sqrt2}
=-\sqrt2.
$$

由于这个量是常数，所以

$$
\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS
=-\sqrt2\iint_SdS.
$$

圆盘 $S$ 是半径为 $a$ 的大圆盘，所以

$$
\iint_SdS=\pi a^2.
$$

因此

$$
\oint_L y\,dx+z\,dy+x\,dz
=-\sqrt2\pi a^2.
$$

最终：

$$
\boxed{
\oint_L y\,dx+z\,dy+x\,dz=-\sqrt2\pi a^2
}.
$$

---

### 5. 一句话理解

直接算法是

$$
\oint_L\mathbf F\cdot\mathbf T\,ds.
$$

Stokes 转换是

$$
\oint_L\mathbf F\cdot\mathbf T\,ds
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

左边看的是沿边界的切向流动，右边看的是曲面上每一点的局部旋转强度累加。闭曲线环流和内部旋转累加相等，这就是 Stokes 公式的含义。

---

## 第二型曲线积分：什么时候能转成原函数法，不是拍脑袋

对于第二型曲线积分

$$
\int_L P\,dx+Q\,dy
$$

或者空间中的

$$
\int_L P\,dx+Q\,dy+R\,dz,
$$

所谓“转成原函数”，意思是看它能不能写成某个函数的全微分。

---

### 1. 平面情形

若存在函数 $u(x,y)$，使得

$$
du=P\,dx+Q\,dy,
$$

那么必须有

$$
u_x=P,
\qquad
u_y=Q.
$$

于是混合偏导应满足

$$
P_y=Q_x.
$$

所以平面中先检查：

$$
\boxed{P_y=Q_x}.
$$

若区域单连通且 $P,Q$ 有连续偏导，则这个条件通常也足够。

这时积分与路径无关，并且

$$
\int_A^B P\,dx+Q\,dy=u(B)-u(A).
$$

---

### 2. 空间情形

空间中若存在函数 $u(x,y,z)$，使得

$$
du=P\,dx+Q\,dy+R\,dz,
$$

那么

$$
u_x=P,
\qquad
u_y=Q,
\qquad
u_z=R.
$$

这等价于

$$
\mathbf F=(P,Q,R)=\nabla u.
$$

也就是说，向量场必须是梯度场。

梯度场的旋度为零：

$$
\nabla\times\mathbf F=\mathbf 0.
$$

所以空间中先检查：

$$
\boxed{\nabla\times\mathbf F=\mathbf 0}.
$$

若区域单连通且偏导连续，则旋度为零通常说明可以找原函数。

---

### 3. 本题 12.4 3(5) 为什么不能用原函数法

本题积分是

$$
\oint_L y\,dx+z\,dy+x\,dz.
$$

对应向量场为

$$
\mathbf F=(y,z,x).
$$

计算旋度：

$$
\nabla\times\mathbf F=(-1,-1,-1).
$$

这不是零向量。

所以

$$
\mathbf F
$$

不是梯度场，不能写成某个原函数的全微分。

因此本题不能转成

$$
u(B)-u(A)
$$

这种形式。

而且本题 $L$ 是闭合曲线，即使能用原函数法，闭合曲线上的全微分积分也会是

$$
\oint_Ldu=0.
$$

但本题结果是

$$
-\sqrt2\pi a^2\ne0.
$$

这也说明它不是全微分积分。

---

### 4. 如果能用原函数法，怎么找原函数

以空间情形为例。若

$$
\mathbf F=(P,Q,R)
$$

满足

$$
\nabla\times\mathbf F=0,
$$

就尝试找 $u$，使

$$
u_x=P,
\qquad
u_y=Q,
\qquad
u_z=R.
$$

步骤：

1. 先对 $P$ 关于 $x$ 积分：

$$
u(x,y,z)=\int P(x,y,z)\,dx+C(y,z).
$$

这里的“常数”不能只写成常数，而要写成

$$
C(y,z),
$$

因为对 $x$ 积分时，$y,z$ 都暂时看成常量。

2. 再对所得 $u$ 求 $y$ 偏导，并令它等于 $Q$：

$$
u_y=Q.
$$

由此确定 $C_y(y,z)$。

3. 再用 $u_z=R$ 确定剩余只依赖 $z$ 的部分。

最终得到原函数 $u$。

---

### 5. 一句话总结

原函数法不是靠看出来的，而是按这个顺序判断：

$$
\boxed{
\text{先算旋度，若 }\nabla\times\mathbf F=0\text{，再尝试找原函数。}
}
$$

如果

$$
\nabla\times\mathbf F\ne0,
$$

就不要找原函数；闭合曲线时优先考虑 Stokes 公式。

---

## 边界、法向量与广义 Stokes 公式：为什么积分会从内部跑到边界上

核心公式是广义 Stokes 公式：

$$
\boxed{
\int_M d\omega=\int_{\partial M}\omega
}
$$

其中：

- $M$ 是一个带边界的有向区域或有向流形；
- $\partial M$ 是它的边界；
- $\omega$ 是一个微分形式；
- $d\omega$ 是它的外微分。

这条公式统一了：

- Newton-Leibniz 公式；
- Green 公式；
- Stokes 公式；
- Gauss 公式。

---

### 1. 一维情形：边界最容易看见

一维时，$M=[a,b]$，边界是两个端点：

$$
\partial [a,b]=\{b\}-\{a\}.
$$

Newton-Leibniz 公式是

$$
\int_a^b f'(x)\,dx=f(b)-f(a).
$$

用广义 Stokes 的语言，就是

$$
\int_{[a,b]}df=\int_{\partial[a,b]}f.
$$

这里边界为什么有正负号？

因为区间的正方向是从 $a$ 到 $b$，所以终点 $b$ 是正边界，起点 $a$ 是负边界。

也就是说，边界方向不是额外拍脑袋加的，而是由内部区域的方向诱导出来的。

---

### 2. Green 公式：内部边抵消，只剩外边界

平面 Green 公式为

$$
\oint_{\partial D}P\,dx+Q\,dy
=\iint_D\left({\partial Q\over\partial x}-{\partial P\over\partial y}\right)dA.
$$

为什么会出现边界？

可以把区域 $D$ 切成很多小矩形。

对每个小矩形，计算边界积分

$$
\oint P\,dx+Q\,dy.
$$

相邻小矩形共享一条边。

这条共享边对左边的小矩形来说方向可能向上，对右边的小矩形来说方向就是向下。

同一条内部边被积分两次，但方向相反，所以互相抵消。

最后所有内部边都抵消，只剩最外面的边界。

因此：

$$
\text{局部小边界的和}=\text{整体外边界}.
$$

这就是边界自然出现的原因。

---

### 3. Gauss 公式中法向量是怎么出现的

Gauss 公式是

$$
\iiint_\Omega \nabla\cdot\mathbf F\,dV
=\iint_{\partial\Omega}\mathbf F\cdot\mathbf n\,dS.
$$

右边为什么是

$$
\mathbf F\cdot\mathbf n?
$$

因为它表示穿过边界面的通量。

设

$$
\mathbf F=(P,Q,R).
$$

散度是

$$
\nabla\cdot\mathbf F=P_x+Q_y+R_z.
$$

先看第一项：

$$
\iiint_\Omega P_x\,dV.
$$

如果区域暂时看成一个长方体

$$
a\le x\le b,
\qquad c\le y\le d,
\qquad e\le z\le f,
$$

那么

$$
\begin{aligned}
\iiint_\Omega P_x\,dV
&=\int_c^d\int_e^f\left(\int_a^b P_x\,dx\right)dz\,dy \\
&=\int_c^d\int_e^f[P(b,y,z)-P(a,y,z)]\,dz\,dy.
\end{aligned}
$$

这正是左右两个边界面的贡献。

在右侧面 $x=b$，外法向为

$$
\mathbf n=(1,0,0),
$$

所以

$$
\mathbf F\cdot\mathbf n=P.
$$

在左侧面 $x=a$，外法向为

$$
\mathbf n=(-1,0,0),
$$

所以

$$
\mathbf F\cdot\mathbf n=-P.
$$

因此

$$
P(b,y,z)-P(a,y,z)
$$

正好就是 $x$ 方向两个边界面上的通量贡献。

同理：

$$
\iiint Q_y\,dV
$$

给出前后两个边界面上的通量；

$$
\iiint R_z\,dV
$$

给出上下两个边界面上的通量。

三部分合起来就是

$$
\iint_{\partial\Omega}\mathbf F\cdot\mathbf n\,dS.
$$

所以法向量不是额外塞进去的。它来自于“外侧减内侧”的符号，也就是边界方向。

---

### 4. 内部小面的抵消也解释 Gauss 公式

把三维区域切成很多小盒子。

每个小盒子都有自己的外法向。

两个相邻小盒子共享一个小面。

对左边盒子来说，这个小面的外法向可能是

$$
\mathbf n.
$$

对右边盒子来说，同一个小面的外法向就是

$$
-\mathbf n.
$$

所以同一个内部小面的通量出现两次：

$$
\mathbf F\cdot\mathbf n\,dS
$$

和

$$
\mathbf F\cdot(-\mathbf n)\,dS.
$$

它们相加为零。

因此所有内部面通量抵消，只剩整体区域最外层边界面的通量。

这就是为什么体积分最后变成边界面积分。

---

### 5. Stokes 公式中边界曲线方向是怎么出现的

三维 Stokes 公式是

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

这里 $S$ 是一个有向曲面，$\partial S$ 是它的边界曲线。

曲面方向由法向量 $\mathbf n$ 决定。

一旦选定 $\mathbf n$，边界曲线方向也被规定了。

规则是右手定则：

- 右手大拇指指向 $\mathbf n$；
- 四指弯曲方向就是 $\partial S$ 的正方向。

也可以说：当你沿边界正方向走，并且头朝法向量方向时，曲面应该在你的左手边。

因此边界方向不是额外给的，而是由曲面的法向量诱导出来的。

---

### 6. Stokes 公式为什么也会只剩边界

把曲面 $S$ 切成很多小曲面片。

每个小曲面片都有自己的边界。

对每个小片，用局部的旋度-环流关系：

$$
\oint_{\partial S_i}\mathbf F\cdot d\mathbf r
\approx
(\nabla\times\mathbf F)\cdot\mathbf n_i\,\Delta S_i.
$$

把所有小片加起来：

$$
\sum_i\oint_{\partial S_i}\mathbf F\cdot d\mathbf r.
$$

相邻两个小片共享一条内部边。

这条内部边在两个小片的边界方向中正好相反，所以积分抵消。

最终只剩下整个曲面 $S$ 的外边界：

$$
\partial S.
$$

因此

$$
\sum_i\oint_{\partial S_i}\mathbf F\cdot d\mathbf r
=\oint_{\partial S}\mathbf F\cdot d\mathbf r.
$$

右边的小片旋度通量求和，在极限中变成

$$
\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

所以得到

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

---

### 7. 广义 Stokes 公式的统一理解

广义 Stokes 公式：

$$
\int_M d\omega=\int_{\partial M}\omega.
$$

可以理解为：

$$
\text{内部的变化率积分}=\text{边界上的总累积}.
$$

或者更具体地说：

- $d\omega$ 描述 $\omega$ 的局部变化；
- 在很多小块上积分时，每个小块都有自己的边界；
- 小块之间共享的内部边界方向相反，全部抵消；
- 最后只剩整体区域的外边界。

所以“边界条件”不是后来硬加进去的。

边界来自于一个事实：

$$
\boxed{
\text{把局部变化累加起来时，内部界面互相抵消，只剩外边界。}
}
$$

---

### 8. 边界法向量和边界切向量的关系

不同维度里，边界上的方向对象不同：

#### 体区域的边界

若 $\Omega$ 是三维体区域，则边界 $\partial\Omega$ 是二维曲面。

边界方向用外法向量表示：

$$
\mathbf n=\text{outward normal}.
$$

因此 Gauss 公式中出现

$$
\mathbf F\cdot\mathbf n\,dS.
$$

#### 曲面的边界

若 $S$ 是二维曲面，则边界 $\partial S$ 是一维曲线。

曲面方向由法向量 $\mathbf n$ 决定，边界方向由右手定则决定。

因此 Stokes 公式中出现

$$
\mathbf F\cdot d\mathbf r
=\mathbf F\cdot\mathbf T\,ds.
$$

#### 平面区域的边界

若 $D$ 是二维平面区域，则边界 $\partial D$ 是平面曲线。

通常约定正方向为逆时针，这等价于区域法向量取

$$
\mathbf k=(0,0,1).
$$

这就是 Green 公式中正向边界的来源。

---

### 9. 边界条件和边界方向不是一回事

这里说的“边界”不是微分方程里那种边界条件，比如

$$
u|_{\partial\Omega}=0
$$

或者

$$
{\partial u\over\partial n}\bigg|_{\partial\Omega}=g.
$$

Stokes/Gauss/Green 公式里的边界是区域本身的几何边界。

它的方向由区域方向自动诱导出来。

所以这里不是“给了一个边界条件”，而是：

$$
\boxed{
\text{区域有边界，积分公式自然把内部变化和边界累积联系起来。}
}
$$

---

### 10. 一句话总结

法向量、切向量和边界方向进入体系的方式是：

$$
\boxed{
\text{先给内部区域定方向，再由内部方向诱导边界方向。}
}
$$

体区域的边界用外法向量；曲面的边界用右手定则确定切向方向；广义 Stokes 公式说明所有内部边界都会抵消，最终只剩真正的外边界。

---

## 12.4 3(5)：用 Stokes 时不是从边界切向量反解 \(P,Q,R\)

原积分是

$$
\oint_L y\,dx+z\,dy+x\,dz.
$$

它本身已经给出了向量场：

$$
P=y,
\qquad Q=z,
\qquad R=x.
$$

所以

$$
\mathbf F=(P,Q,R)=(y,z,x).
$$

这里不需要从边界方向向量反解 $P,Q,R$。

$P,Q,R$ 来自被积表达式：

$$
P\,dx+Q\,dy+R\,dz.
$$

边界方向的作用不是决定 $P,Q,R$，而是决定 Stokes 公式右边曲面法向量 $\mathbf n$ 的正负。

---

### 1. 直接参数化法需要切向量

如果直接算原积分，需要先参数化曲线：

$$
\mathbf r(t)=(x(t),y(t),z(t)).
$$

然后求切向量：

$$
\mathbf r'(t)=(x'(t),y'(t),z'(t)).
$$

于是

$$
\oint_L y\,dx+z\,dy+x\,dz
=\int \bigl[y(t)x'(t)+z(t)y'(t)+x(t)z'(t)\bigr]dt.
$$

这里确实要用边界的方向向量，因为它决定 $\mathbf r'(t)$ 的方向。

---

### 2. Stokes 法不需要显式写出切向量

Stokes 公式是

$$
\oint_L\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

它把左边的切向积分换成右边的旋度通量。

所以使用 Stokes 时，流程是：

1. 从积分式读出向量场

$$
\mathbf F=(P,Q,R).
$$

2. 计算旋度

$$
\nabla\times\mathbf F.
$$

3. 选择一个以 $L$ 为边界的曲面 $S$。

4. 根据题目给的边界方向，确定 $S$ 的法向量 $\mathbf n$。

5. 计算

$$
\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

注意：边界方向只在第 4 步用来确定 $\mathbf n$ 的正负。

---

### 3. 本题中 \(P,Q,R\) 怎么来

原式：

$$
y\,dx+z\,dy+x\,dz.
$$

对照

$$
P\,dx+Q\,dy+R\,dz,
$$

得到

$$
P=y,
\qquad Q=z,
\qquad R=x.
$$

所以

$$
\mathbf F=(y,z,x).
$$

旋度为

$$
\nabla\times\mathbf F=(-1,-1,-1).
$$

这一步完全由被积表达式决定，和边界方向无关。

---

### 4. 本题中边界方向怎么进入

曲线 $L$ 是平面

$$
x+z=a
$$

和球面

$$
x^2+y^2+(z-a)^2=a^2
$$

的交线。

它是平面 $x+z=a$ 上的半径为 $a$ 的大圆。

平面法向量有两个选择：

$$
\mathbf n_+= {1\over\sqrt2}(1,0,1),
$$

和

$$
\mathbf n_-=-{1\over\sqrt2}(1,0,1).
$$

这两个法向量对应相反的边界方向。

题目说从 $z$ 轴正方向看去为逆时针。

因为

$$
\mathbf n_+
$$

的 $z$ 分量为正，所以它对应从 $z$ 轴正方向看去逆时针的边界方向。

因此取

$$
\mathbf n={1\over\sqrt2}(1,0,1).
$$

然后计算

$$
(\nabla\times\mathbf F)\cdot\mathbf n
=(-1,-1,-1)\cdot {1\over\sqrt2}(1,0,1)
=-\sqrt2.
$$

圆盘面积为

$$
\pi a^2.
$$

所以

$$
\oint_L y\,dx+z\,dy+x\,dz
=-\sqrt2\pi a^2.
$$

---

### 5. 如果坚持先求边界切向量，也可以验证方向

取

$$
\mathbf n={1\over\sqrt2}(1,0,1).
$$

平面内取

$$
\mathbf e_1=(0,1,0),
\qquad
\mathbf e_2=\left(-{1\over\sqrt2},0,{1\over\sqrt2}\right),
$$

满足

$$
\mathbf e_1\times\mathbf e_2=\mathbf n.
$$

于是边界正向参数化为

$$
\mathbf r(t)=(0,0,a)+a(\mathbf e_1\cos t+\mathbf e_2\sin t).
$$

即

$$
x=-{a\over\sqrt2}\sin t,
\qquad
 y=a\cos t,
\qquad
 z=a+{a\over\sqrt2}\sin t.
$$

这个参数化的投影从 $z$ 轴正方向看是逆时针。

它的切向量是

$$
\mathbf r'(t)=\left(-{a\over\sqrt2}\cos t,-a\sin t,{a\over\sqrt2}\cos t\right).
$$

如果直接算，就代入

$$
\int_0^{2\pi}\mathbf F(\mathbf r(t))\cdot\mathbf r'(t)\,dt.
$$

这会得到同样结果

$$
-\sqrt2\pi a^2.
$$

---

### 6. 总结

不能把步骤理解成：

$$
\text{边界方向向量}\longrightarrow \text{反解 }P,Q,R.
$$

正确逻辑是：

$$
P,Q,R\text{ 从积分式直接读出。}
$$

边界方向只负责决定：

$$
\mathbf n\text{ 还是 }-\mathbf n.
$$

也就是

$$
\boxed{
\text{被积式决定向量场，边界方向决定法向量正负。}
}
$$

---

## 第二型曲线积分里的 \(dx,dy,dz\)：不是分别独立积分，而是沿同一条曲线一起变化

第二型曲线积分常写成

$$
\int_L P\,dx+Q\,dy+R\,dz.
$$

也可以写成向量形式：

$$
\int_L\mathbf F\cdot d\mathbf r,
$$

其中

$$
\mathbf F=(P,Q,R),
\qquad
 d\mathbf r=(dx,dy,dz).
$$

但这里的

$$
dx,dy,dz
$$

不是三个互相独立的积分变量。

它们是沿同一条曲线 $L$ 发生的微小位移分量。

---

### 1. 严格定义需要曲线参数

如果曲线 $L$ 用参数方程表示为

$$
\mathbf r(t)=(x(t),y(t),z(t)),
\qquad \alpha\le t\le\beta,
$$

那么

$$
dx=x'(t)dt,
\qquad
 dy=y'(t)dt,
\qquad
 dz=z'(t)dt.
$$

所以

$$
\int_L P\,dx+Q\,dy+R\,dz
$$

严格意思是

$$
\int_\alpha^\beta
\left[ P(x(t),y(t),z(t))x'(t)
+Q(x(t),y(t),z(t))y'(t)
+R(x(t),y(t),z(t))z'(t)\right]dt.
$$

也就是

$$
\int_\alpha^\beta \mathbf F(\mathbf r(t))\cdot\mathbf r'(t)\,dt.
$$

因此第二型曲线积分默认背后一定有一个参数在驱动。

即使题目没有显式写出 $t$，曲线本身也可以局部参数化；积分定义就是通过参数化来理解的。

---

### 2. 为什么可以不显式写 \(t\)

虽然定义时需要参数化，但最终积分值不依赖你选哪个具体参数。

假设换一个参数

$$
t=\phi(s),
$$

只要 $\phi$ 保持方向，即

$$
\phi'(s)>0,
$$

那么

$$
\mathbf r(t)=\mathbf r(\phi(s)).
$$

新的导数为

$$
{d\mathbf r\over ds}
={d\mathbf r\over dt}{dt\over ds}.
$$

于是

$$
\mathbf F\cdot {d\mathbf r\over ds}ds
=
\mathbf F\cdot {d\mathbf r\over dt}{dt\over ds}ds
=
\mathbf F\cdot {d\mathbf r\over dt}dt.
$$

所以积分值不变。

这就是为什么可以直接写

$$
\int_L\mathbf F\cdot d\mathbf r
$$

而不每次都写出参数 $t$。

这个记号表示“沿有向曲线 $L$ 积分”，不是表示 $dx,dy,dz$ 独立。

---

### 3. 微分形式语言：\(Pdx+Qdy+Rdz\) 是一个 1-形式

从微分形式角度看，

$$
\omega=P\,dx+Q\,dy+R\,dz
$$

是一个 $1$-形式。

曲线参数化

$$
\mathbf r:[\alpha,\beta]\to\mathbb R^3
$$

会把 $\omega$ 拉回到参数区间上：

$$
\mathbf r^*\omega
=\left[P(\mathbf r(t))x'(t)+Q(\mathbf r(t))y'(t)+R(\mathbf r(t))z'(t)\right]dt.
$$

于是

$$
\int_L\omega
:=\int_\alpha^\beta \mathbf r^*\omega.
$$

这就是严格定义。

---

### 4. Stokes 公式不是把 \(dx,dy,dz\) 分别积分

Stokes 公式说：

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

左边仍然是沿边界曲线的切向积分。

右边不是对 $dx,dy,dz$ 分别积分，而是对曲面面积元 $dS$ 积分。

这一步是定理给出的等价转换。

也就是说，Stokes 公式把

$$
\text{边界曲线上的切向积分}
$$

转换成

$$
\text{曲面上的旋度通量积分}.
$$

它不是把

$$
Pdx+Qdy+Rdz
$$

里的三个部分拆开各算各的。

---

### 5. 本题中的左边如果直接算，必须参数化

本题左边是

$$
\oint_L y\,dx+z\,dy+x\,dz.
$$

若直接算，必须取参数方程，例如

$$
x=-{a\over\sqrt2}\sin t,
\qquad
 y=a\cos t,
\qquad
 z=a+{a\over\sqrt2}\sin t.
$$

然后

$$
dx=-{a\over\sqrt2}\cos t\,dt,
$$

$$
dy=-a\sin t\,dt,
$$

$$
dz={a\over\sqrt2}\cos t\,dt.
$$

所以

$$
y\,dx+z\,dy+x\,dz
$$

会整体变成一个关于 $t$ 的表达式：

$$
\left[y(t)x'(t)+z(t)y'(t)+x(t)z'(t)\right]dt.
$$

不能把 $dx,dy,dz$ 看成三个互相独立的变量。

---

### 6. 如果不用参数，为什么还能算

不用显式参数时，通常是因为用了 Green 公式或 Stokes 公式。

比如本题中，直接用 Stokes：

$$
\oint_L\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

这时不需要写出曲线参数 $t$。

但并不是说曲线积分没有参数驱动，而是 Stokes 公式让我们绕开了边界参数化。

右边的曲面积分严格来说也可以参数化曲面来定义：

$$
\mathbf R(u,v).
$$

只是本题选的 $S$ 是平面圆盘，旋度又是常向量，所以可以直接用

$$
(\nabla\times\mathbf F)\cdot\mathbf n\cdot \text{面积}
$$

来算。

---

### 7. 一句话总结

$$
\boxed{
P\,dx+Q\,dy+R\,dz
\text{ 不是三个独立积分，而是 }\mathbf F\cdot d\mathbf r.
}
$$

其中

$$
d\mathbf r
$$

必须沿同一条有向曲线产生。

没有显式写参数时，参数化仍然在定义背后；只是我们可以用 Green/Stokes 等定理绕开显式参数化。

---

## Stokes 公式中的曲面可以任意选吗

Stokes 公式是

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

这里的曲面 $S$ 不唯一。

只要满足：

1. $S$ 是光滑或分片光滑曲面；
2. $S$ 的边界是给定曲线 $L$，即

$$
\partial S=L;
$$

3. 曲面法向量 $\mathbf n$ 诱导出的边界方向和题目给的 $L$ 的方向一致；
4. 向量场 $\mathbf F$ 在包含 $S$ 的区域内有连续一阶偏导；

就可以用这个 $S$。

所以本题中，交线 $L$ 是平面

$$
x+z=a
$$

上的大圆。可以选：

- 平面圆盘；
- 球面上的一个半球面；
- 任何以这个大圆为边界的光滑曲面。

它们都可以。

---

### 为什么不同曲面结果一样

如果 $S_1$ 和 $S_2$ 有同一个边界 $L$，且方向都和 $L$ 匹配，那么 Stokes 公式分别给出

$$
\oint_L\mathbf F\cdot d\mathbf r
=\iint_{S_1}(\nabla\times\mathbf F)\cdot\mathbf n_1\,dS,
$$

以及

$$
\oint_L\mathbf F\cdot d\mathbf r
=\iint_{S_2}(\nabla\times\mathbf F)\cdot\mathbf n_2\,dS.
$$

左边是同一个曲线积分，所以右边相等。

因此旋度通量虽然是在不同曲面上算的，但只要边界相同、方向一致，结果一样。

---

### 为什么本题选平面圆盘

本题中

$$
\nabla\times\mathbf F=(-1,-1,-1)
$$

是常向量。

平面圆盘的单位法向量也是常向量：

$$
\mathbf n={1\over\sqrt2}(1,0,1).
$$

所以

$$
(\nabla\times\mathbf F)\cdot\mathbf n
$$

是常数。

于是积分直接变成

$$
\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS
=\bigl[(\nabla\times\mathbf F)\cdot\mathbf n\bigr]\cdot \operatorname{Area}(S).
$$

而这个圆盘半径为 $a$，面积为

$$
\pi a^2.
$$

所以选平面圆盘最省事。

如果选球面半球，也可以算，但法向量随点变化，积分会麻烦一些。

---

### 注意：不能跨过奇点或不连续区域

如果向量场 $\mathbf F$ 在某些地方没有定义，或者一阶偏导不连续，就不能随便换曲面跨过这些坏点。

例如有些场在原点或某条轴线上有奇点。这时两个曲面虽然边界相同，但如果一个曲面穿过奇点，另一个不穿过，Stokes 公式的使用条件可能不同，结果就不能随便等同。

本题中

$$
\mathbf F=(y,z,x)
$$

是全空间光滑向量场，所以没有这个问题。

---

### 一句话总结

$$
\boxed{
\text{Stokes 公式中曲面可任意选，只要边界相同、方向一致、场足够光滑。}
}
$$

本题取平面圆盘只是因为它最方便。

---

## 第二型曲面积分 \(P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy\) 是什么驱动的，怎么转成三重积分

第二型曲面积分常写成

$$
\iint_S P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy.
$$

它对应向量场

$$
\mathbf F=(P,Q,R)
$$

穿过有向曲面 $S$ 的通量：

$$
\iint_S\mathbf F\cdot\mathbf n\,dS.
$$

这里的核心是：

$$
(dy\,dz,\ dz\,dx,\ dx\,dy)
$$

不是三个独立面积，而是有向面积元向量的三个分量。

---

### 1. 曲面积分由两个参数驱动

曲线积分由一个参数 $t$ 驱动：

$$
\mathbf r(t)=(x(t),y(t),z(t)).
$$

曲面积分由两个参数驱动，例如

$$
\mathbf r(u,v)=(x(u,v),y(u,v),z(u,v)).
$$

这时曲面上的两个切向量是

$$
\mathbf r_u=(x_u,y_u,z_u),
\qquad
\mathbf r_v=(x_v,y_v,z_v).
$$

它们叉乘得到有向面积元向量：

$$
\mathbf r_u\times\mathbf r_v\,du\,dv.
$$

展开叉乘：

$$
\mathbf r_u\times\mathbf r_v
=\left(
\begin{vmatrix}y_u&z_u\\y_v&z_v\end{vmatrix},
\begin{vmatrix}z_u&x_u\\z_v&x_v\end{vmatrix},
\begin{vmatrix}x_u&y_u\\x_v&y_v\end{vmatrix}
\right).
$$

也就是

$$
\mathbf r_u\times\mathbf r_v\,du\,dv
=\left(
{\partial(y,z)\over\partial(u,v)},
{\partial(z,x)\over\partial(u,v)},
{\partial(x,y)\over\partial(u,v)}
\right)du\,dv.
$$

所以记号

$$
dy\,dz,
\qquad dz\,dx,
\qquad dx\,dy
$$

严格对应为

$$
dy\,dz={\partial(y,z)\over\partial(u,v)}du\,dv,
$$

$$
dz\,dx={\partial(z,x)\over\partial(u,v)}du\,dv,
$$

$$
dx\,dy={\partial(x,y)\over\partial(u,v)}du\,dv.
$$

因此

$$
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

就是

$$
(P,Q,R)\cdot(\mathbf r_u\times\mathbf r_v)\,du\,dv.
$$

也就是

$$
\mathbf F\cdot\mathbf n\,dS.
$$

---

### 2. 为什么 \((dy\,dz,dz\,dx,dx\,dy)\) 是面积元向量

普通面积元是标量：

$$
dS.
$$

但通量需要知道曲面朝向，所以要用有向面积元：

$$
\mathbf n\,dS.
$$

而参数化曲面给出

$$
\mathbf n\,dS=\mathbf r_u\times\mathbf r_v\,du\,dv.
$$

于是

$$
\mathbf n\,dS
=(dy\,dz,dz\,dx,dx\,dy).
$$

所以第二型曲面积分的形式

$$
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

就是

$$
(P,Q,R)\cdot(dy\,dz,dz\,dx,dx\,dy).
$$

这和曲线积分中

$$
P\,dx+Q\,dy+R\,dz=(P,Q,R)\cdot(dx,dy,dz)
$$

完全平行。

区别只是：

- 曲线积分中 $(dx,dy,dz)$ 是切向位移元；
- 曲面积分中 $(dy\,dz,dz\,dx,dx\,dy)$ 是法向面积元。

---

### 3. 图形曲面 \(z=f(x,y)\) 的常用公式

若曲面写成

$$
z=f(x,y),
$$

并取上侧方向，则参数化为

$$
\mathbf r(x,y)=(x,y,f(x,y)).
$$

有

$$
\mathbf r_x=(1,0,f_x),
\qquad
\mathbf r_y=(0,1,f_y).
$$

所以

$$
\mathbf r_x\times\mathbf r_y=(-f_x,-f_y,1).
$$

因此

$$
\mathbf n\,dS=(-f_x,-f_y,1)dx\,dy.
$$

于是

$$
\iint_S P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

变成

$$
\iint_D\left(-P f_x-Q f_y+R\right)dx\,dy,
$$

其中 $P,Q,R$ 都要代入

$$
z=f(x,y).
$$

如果取下侧方向，就整体取负号。

---

### 4. 怎么转换成三重积分：Gauss 公式

如果 $S$ 是封闭曲面，并且取外侧方向，则第二型曲面积分可以用 Gauss 公式转成三重积分。

设

$$
\mathbf F=(P,Q,R).
$$

通量积分为

$$
\iint_S P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
=\iint_S\mathbf F\cdot\mathbf n\,dS.
$$

若 $S=\partial\Omega$，方向取外侧，则

$$
\iint_{\partial\Omega}\mathbf F\cdot\mathbf n\,dS
=\iiint_\Omega\nabla\cdot\mathbf F\,dV.
$$

而

$$
\nabla\cdot\mathbf F=P_x+Q_y+R_z.
$$

所以

$$
\boxed{
\iint_{\partial\Omega} P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
=\iiint_\Omega(P_x+Q_y+R_z)\,dx\,dy\,dz.
}
$$

这就是第二型曲面积分转成三重积分的公式。

---

### 5. 微分形式角度更直接

从微分形式看，第二型曲面积分中的对象是一个 $2$-形式：

$$
\omega=P\,dy\wedge dz+Q\,dz\wedge dx+R\,dx\wedge dy.
$$

通常教材把楔积符号省略，写成

$$
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy.
$$

对它求外微分：

$$
d\omega
=dP\wedge dy\wedge dz+dQ\wedge dz\wedge dx+dR\wedge dx\wedge dy.
$$

因为

$$
dP=P_xdx+P_ydy+P_zdz,
$$

所以

$$
dP\wedge dy\wedge dz=P_x\,dx\wedge dy\wedge dz.
$$

同理：

$$
dQ\wedge dz\wedge dx=Q_y\,dx\wedge dy\wedge dz,
$$

$$
dR\wedge dx\wedge dy=R_z\,dx\wedge dy\wedge dz.
$$

因此

$$
d\omega=(P_x+Q_y+R_z)dx\wedge dy\wedge dz.
$$

广义 Stokes 公式给出

$$
\int_{\partial\Omega}\omega=\int_\Omega d\omega.
$$

于是

$$
\iint_{\partial\Omega} P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
=\iiint_\Omega(P_x+Q_y+R_z)dV.
$$

这就是 Gauss 公式的微分形式版本。

---

### 6. 如果曲面不是封闭的怎么办

Gauss 公式要求曲面封闭。

如果题目给的是一个开曲面 $S$，就不能直接变成三重积分。

常用方法是补一个简单曲面 $S_0$，使

$$
S\cup S_0=\partial\Omega.
$$

然后

$$
\iint_S\mathbf F\cdot\mathbf n\,dS
=\iiint_\Omega\nabla\cdot\mathbf F\,dV
-\iint_{S_0}\mathbf F\cdot\mathbf n\,dS.
$$

这就是“补面法”。

---

### 7. 一句话总结

第二型曲面积分由两个参数驱动：

$$
\mathbf r(u,v)=(x(u,v),y(u,v),z(u,v)).
$$

其中

$$
(dy\,dz,dz\,dx,dx\,dy)
=\mathbf r_u\times\mathbf r_v\,du\,dv
=\mathbf n\,dS.
$$

所以

$$
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
=\mathbf F\cdot\mathbf n\,dS.
$$

若曲面封闭并取外侧方向，则

$$
\boxed{
\iint_{\partial\Omega}P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
=\iiint_\Omega(P_x+Q_y+R_z)dV.
}
$$

---

## \(dx,dy,dz\)、\(dy\,dz,dz\,dx,dx\,dy\)、\(dx\,dy\,dz\) 的规律

可以按“维度”理解这些微分元。

---

### 1. 一维：曲线上的切向位移元

曲线积分用的是

$$
d\mathbf r=(dx,dy,dz).
$$

它是沿曲线方向的微小位移，所以是切向的。

如果

$$
\mathbf F=(P,Q,R),
$$

那么

$$
\mathbf F\cdot d\mathbf r
=P\,dx+Q\,dy+R\,dz.
$$

所以

$$
\boxed{
P\,dx+Q\,dy+R\,dz
}
$$

是沿曲线的切向积分对象。

---

### 2. 二维：曲面上的法向面积元

曲面积分用的是有向面积元

$$
\mathbf n\,dS.
$$

在坐标形式下：

$$
\mathbf n\,dS=(dy\,dz,dz\,dx,dx\,dy).
$$

所以

$$
\mathbf F\cdot \mathbf n\,dS
=P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy.
$$

因此

$$
\boxed{
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
}
$$

是穿过曲面的法向通量积分对象。

这里的规律是：

- $dy\,dz$ 对应 $x$ 方向面积元；
- $dz\,dx$ 对应 $y$ 方向面积元；
- $dx\,dy$ 对应 $z$ 方向面积元。

也就是“缺哪个变量，就对应哪个方向”。

例如：

$$
dy\,dz
$$

缺 $x$，所以它是垂直于 $x$ 轴方向的面积元分量。

---

### 3. 三维：体积元

三维体积分用的是

$$
dV=dx\,dy\,dz.
$$

它不是切向量，也不是法向量，而是体积元。

在三维空间里，体积元已经占满了全部三个方向，所以没有额外的法向或切向方向。

因此

$$
\boxed{dx\,dy\,dz}
$$

是三维有向体积元。

---

### 4. 第二型曲面积分转三重积分的规律

若

$$
\mathbf F=(P,Q,R),
$$

则第二型曲面积分是

$$
\iint_{\partial\Omega}P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy.
$$

如果 $\partial\Omega$ 是封闭曲面，方向取外侧，则用 Gauss 公式：

$$
\iint_{\partial\Omega}P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
=\iiint_\Omega(P_x+Q_y+R_z)\,dx\,dy\,dz.
$$

所以这里确实是：

$$
\boxed{
P_x+Q_y+R_z
}
$$

乘上体积元

$$
\boxed{dx\,dy\,dz}
$$

来积分。

也就是

$$
\boxed{
\text{通量的边界积分}=\text{散度的体积分}.
}
$$

---

### 5. 更统一的规律：外微分

这些公式背后有一个统一结构。

#### 0 维到 1 维：梯度

函数 $f$ 的微分是

$$
df=f_xdx+f_ydy+f_zdz.
$$

这对应梯度：

$$
\nabla f=(f_x,f_y,f_z).
$$

#### 1 维到 2 维：旋度

对

$$
\omega=P\,dx+Q\,dy+R\,dz
$$

求外微分，得到

$$
d\omega
=(R_y-Q_z)\,dy\,dz+(P_z-R_x)\,dz\,dx+(Q_x-P_y)\,dx\,dy.
$$

这对应旋度：

$$
\nabla\times\mathbf F
=(R_y-Q_z,\ P_z-R_x,\ Q_x-P_y).
$$

所以曲线环流转曲面积分时，出现旋度。

#### 2 维到 3 维：散度

对

$$
\eta=P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

求外微分，得到

$$
d\eta=(P_x+Q_y+R_z)\,dx\,dy\,dz.
$$

这对应散度：

$$
\nabla\cdot\mathbf F=P_x+Q_y+R_z.
$$

所以曲面通量转体积分时，出现散度。

---

### 6. 表格总结

| 几何对象 | 微分元 | 含义 | 对应积分 |
|---|---|---|---|
| 曲线 | $(dx,dy,dz)$ | 切向位移元 | $Pdx+Qdy+Rdz$ |
| 曲面 | $(dy\,dz,dz\,dx,dx\,dy)$ | 法向面积元 | $Pdy\,dz+Qdz\,dx+Rdx\,dy$ |
| 体区域 | $dx\,dy\,dz$ | 体积元 | $(P_x+Q_y+R_z)dx\,dy\,dz$ |

再对应到算子：

| 维度提升 | 算子 | 积分公式 |
|---|---|---|
| 点到线 | 梯度 | Newton-Leibniz |
| 线到面 | 旋度 | Stokes/Green |
| 面到体 | 散度 | Gauss |

---

### 7. 一句话总结

$$
\boxed{
(dx,dy,dz)\text{ 是切向位移元；}
(dy\,dz,dz\,dx,dx\,dy)\text{ 是法向面积元；}
 dx\,dy\,dz\text{ 是体积元。}
}
$$

对应的微分算子依次是：

$$
\boxed{
\text{梯度、旋度、散度。}
}
$$

---

## \((dy\,dz,dz\,dx,dx\,dy)\) 可以理解成叉乘得到的有向投影面积

对曲面作参数化：

$$
\mathbf r(u,v)=(x(u,v),y(u,v),z(u,v)).
$$

两个切向量是

$$
\mathbf r_u=(x_u,y_u,z_u),
\qquad
\mathbf r_v=(x_v,y_v,z_v).
$$

它们张成一个微小平行四边形。

这个微小平行四边形的有向面积向量是

$$
\mathbf r_u\times\mathbf r_v\,du\,dv.
$$

展开叉乘：

$$
\mathbf r_u\times\mathbf r_v
=\left(
 y_uz_v-z_uy_v,
 z_ux_v-x_uz_v,
 x_uy_v-y_ux_v
\right).
$$

因此

$$
\mathbf r_u\times\mathbf r_v\,du\,dv
=\left(
{\partial(y,z)\over\partial(u,v)},
{\partial(z,x)\over\partial(u,v)},
{\partial(x,y)\over\partial(u,v)}
\right)du\,dv.
$$

所以记号上写成

$$
\boxed{
\mathbf n\,dS=(dy\,dz,dz\,dx,dx\,dy).
}
$$

---

### 1. 为什么说它是投影面积

设一个有向小面积元为

$$
\mathbf n\,dS.
$$

它的 $x$ 分量是

$$
n_xdS.
$$

几何意义是：这个小面积元投影到 $yz$ 平面上的有向面积。

所以

$$
\boxed{dy\,dz=n_xdS}
$$

表示投影到 $yz$ 平面上的有向面积。

同理：

$$
\boxed{dz\,dx=n_ydS}
$$

表示投影到 $zx$ 平面上的有向面积；

$$
\boxed{dx\,dy=n_zdS}
$$

表示投影到 $xy$ 平面上的有向面积。

---

### 2. 规律：缺哪个变量，就投影到哪个坐标面，对应哪个法向分量

- $dy\,dz$ 缺 $x$，所以是投影到 $yz$ 平面的面积，对应 $x$ 方向法向分量；
- $dz\,dx$ 缺 $y$，所以是投影到 $zx$ 平面的面积，对应 $y$ 方向法向分量；
- $dx\,dy$ 缺 $z$，所以是投影到 $xy$ 平面的面积，对应 $z$ 方向法向分量。

也就是：

$$
(dy\,dz,dz\,dx,dx\,dy)
=(n_xdS,n_ydS,n_zdS).
$$

---

### 3. 为什么有正负号

投影面积是有向的。

如果法向量的 $x$ 分量为正，则

$$
dy\,dz>0.
$$

如果法向量的 $x$ 分量为负，则

$$
dy\,dz<0.
$$

因此它不是普通面积，而是带方向的投影面积。

普通面积 $dS$ 总是非负；但

$$
dy\,dz,
\quad dz\,dx,
\quad dx\,dy
$$

可以正也可以负。

---

### 4. 一句话总结

$$
\boxed{
(dy\,dz,dz\,dx,dx\,dy)
\text{ 是由 }\mathbf r_u\times\mathbf r_v\text{ 得到的有向面积向量。}
}
$$

它的每个分量就是这个微小曲面片在对应坐标平面上的有向投影面积。
