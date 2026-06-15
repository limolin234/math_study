# 作业 12.5：曲面积分

本文由 `tmp.md` 中 12.5 节作业解答整理而成。

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
