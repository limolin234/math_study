# 作业 12.5：曲面积分解答

来源：`~/Downloads/作业(12.5节).pdf`。

说明：PDF 为手写扫描件，部分题目字迹较难辨认；能明确辨认的题目给出完整解答，个别题目若条件不清，在对应处标注。

---

# 1. 求下列曲面的面积

## 1(1) \(z=axy\) 在圆柱 \(x^2+y^2=a^2\) 内的部分

曲面为图形曲面

$$
z=f(x,y)=axy.
$$

面积公式：

$$
S=\iint_D\sqrt{1+f_x^2+f_y^2}\,dxdy.
$$

有

$$
f_x=ay,
\qquad
f_y=ax.
$$

所以

$$
1+f_x^2+f_y^2=1+a^2(x^2+y^2).
$$

区域为

$$
D:\ x^2+y^2\le a^2.
$$

用极坐标：

$$
x=r\cos\theta,
\qquad y=r\sin\theta,
\qquad dxdy=rdrd\theta.
$$

因此

$$
\begin{aligned}
S
&=\int_0^{2\pi}\int_0^a\sqrt{1+a^2r^2}\,r\,dr\,d\theta \\
&=2\pi\int_0^a r\sqrt{1+a^2r^2}\,dr \\
&={2\pi\over3a^2}\left[(1+a^4)^{3/2}-1\right].
\end{aligned}
$$

答案：

$$
\boxed{S={2\pi\over3a^2}\left[(1+a^4)^{3/2}-1\right]}.
$$

---

## 1(2) 锥面 \(x^2+y^2={1\over3}z^2\) 被平面 \(x+y+z=2a\) 截得部分

锥面为

$$
z=\sqrt3\sqrt{x^2+y^2}.
$$

它是图形曲面

$$
z=f(x,y)=\sqrt3\sqrt{x^2+y^2}.
$$

先算面积放大因子。

有

$$
f_x={\sqrt3 x\over\sqrt{x^2+y^2}},
\qquad
f_y={\sqrt3 y\over\sqrt{x^2+y^2}}.
$$

所以

$$
f_x^2+f_y^2=3.
$$

因此

$$
dS=\sqrt{1+f_x^2+f_y^2}\,dxdy=2\,dxdy.
$$

所以曲面面积等于其 $xy$ 投影面积的 $2$ 倍。

接下来求投影区域 $D$ 的面积。

平面

$$
x+y+z=2a
$$

代入锥面

$$
z=\sqrt3\sqrt{x^2+y^2}
$$

得到投影边界：

$$
x+y+\sqrt3\sqrt{x^2+y^2}=2a.
$$

用极坐标

$$
x=r\cos\theta,
\qquad y=r\sin\theta.
$$

则边界为

$$
r(\cos\theta+\sin\theta+\sqrt3)=2a.
$$

所以

$$
r={2a\over\sqrt3+\cos\theta+\sin\theta}.
$$

因此投影区域面积为

$$
\begin{aligned}
A_D
&={1\over2}\int_0^{2\pi}r^2\,d\theta \\
&={1\over2}\int_0^{2\pi}{4a^2\over(\sqrt3+\cos\theta+\sin\theta)^2}d\theta \\
&=2a^2\int_0^{2\pi}{d\theta\over(\sqrt3+\cos\theta+\sin\theta)^2}.
\end{aligned}
$$

因为

$$
\cos\theta+\sin\theta=\sqrt2\cos\left(\theta-{\pi\over4}\right),
$$

所以需要计算

$$
\int_0^{2\pi}{d\theta\over(\sqrt3+\sqrt2\cos\theta)^2}.
$$

标准公式：若 $A>|B|$，则

$$
\int_0^{2\pi}{d\theta\over(A+B\cos\theta)^2}
={2\pi A\over(A^2-B^2)^{3/2}}.
$$

这里

$$
A=\sqrt3,
\qquad B=\sqrt2.
$$

因此

$$
A^2-B^2=3-2=1.
$$

所以

$$
\int_0^{2\pi}{d\theta\over(\sqrt3+\sqrt2\cos\theta)^2}
=2\pi\sqrt3.
$$

于是

$$
A_D=2a^2\cdot 2\pi\sqrt3=4\pi\sqrt3 a^2.
$$

曲面面积为

$$
S=2A_D=8\pi\sqrt3 a^2.
$$

答案：

$$
\boxed{S=8\sqrt3\pi a^2}.
$$

也可以理解为：先通过仿射/旋转变换把投影边界看成平面里的椭圆，再用椭圆面积公式求投影面积；最后乘上锥面图形曲面的面积放大因子 $2$。

---

## 1(3) 球面 \(x^2+y^2+z^2=a^2\) 包含在锥面 \(z=\sqrt{x^2+y^2}\) 内的部分

球坐标中

$$
z=a\cos\varphi,
\qquad
\sqrt{x^2+y^2}=a\sin\varphi.
$$

锥面条件

$$
z=\sqrt{x^2+y^2}
$$

给出

$$
\varphi={\pi\over4}.
$$

“包含在锥面内”的上方球冠满足

$$
0\le\varphi\le {\pi\over4}.
$$

球面面积元：

$$
dS=a^2\sin\varphi\,d\varphi\,d\theta.
$$

所以

$$
\begin{aligned}
S
&=\int_0^{2\pi}\int_0^{\pi/4}a^2\sin\varphi\,d\varphi\,d\theta \\
&=2\pi a^2\left(1-{\sqrt2\over2}\right).
\end{aligned}
$$

答案：

$$
\boxed{S=2\pi a^2\left(1-{\sqrt2\over2}\right)}.
$$

---

## 1(4) 圆柱面 \(x^2+y^2=a^2\) 被平面 \(x+z=0\)、\(x-z=0\) 截得第一卦限部分

参数化圆柱：

$$
x=a\cos\theta,
\qquad y=a\sin\theta.
$$

第一卦限给出

$$
0\le\theta\le {\pi\over2}.
$$

两个平面给出

$$
z=-x=-a\cos\theta,
\qquad
z=x=a\cos\theta.
$$

所以

$$
-a\cos\theta\le z\le a\cos\theta.
$$

圆柱面积元：

$$
dS=a\,d\theta\,dz.
$$

面积：

$$
\begin{aligned}
S
&=\int_0^{\pi/2}\int_{-a\cos\theta}^{a\cos\theta}a\,dz\,d\theta \\
&=2a^2\int_0^{\pi/2}\cos\theta\,d\theta \\
&=2a^2.
\end{aligned}
$$

答案：

$$
\boxed{S=2a^2}.
$$

---

## 1(5) 抛物面 \(x^2+y^2=2az\) 包含在柱面 \((x^2+y^2)^2=2a^2xy\) 内的部分

抛物面写作

$$
z={r^2\over2a}.
$$

曲面面积元：

$$
dS=\sqrt{1+z_x^2+z_y^2}\,dxdy.
$$

由于

$$
z={x^2+y^2\over2a},
$$

所以

$$
z_x={x\over a},
\qquad
z_y={y\over a}.
$$

因此

$$
dS=\sqrt{1+{x^2+y^2\over a^2}}\,dxdy
=\sqrt{1+{r^2\over a^2}}\,r\,drd\theta.
$$

柱面在极坐标中为

$$
(x^2+y^2)^2=2a^2xy.
$$

即

$$
r^4=2a^2r^2\cos\theta\sin\theta.
$$

当 $r\ne0$ 时，

$$
r^2=2a^2\cos\theta\sin\theta=a^2\sin2\theta.
$$

要有实际区域，必须

$$
\sin2\theta\ge0.
$$

所以不仅有第一象限

$$
0\le\theta\le {\pi\over2},
$$

还包括第三象限

$$
\pi\le\theta\le {3\pi\over2}.
$$

也就是确实包含 $x<0,y<0$ 的那一瓣。

两个区域对面积的贡献相同，因此面积为第一象限结果的 $2$ 倍。

第一象限中：

$$
0\le r\le a\sqrt{\sin2\theta},
\qquad 0\le\theta\le {\pi\over2}.
$$

所以总面积

$$
\begin{aligned}
S
&=2\int_0^{\pi/2}\int_0^{a\sqrt{\sin2\theta}}
\sqrt{1+{r^2\over a^2}}\,r\,drd\theta.
\end{aligned}
$$

先对 $r$ 积分：

$$
\int r\sqrt{1+{r^2\over a^2}}\,dr
={a^2\over3}\left(1+{r^2\over a^2}\right)^{3/2}.
$$

因此

$$
\begin{aligned}
S
&=2\cdot {a^2\over3}\int_0^{\pi/2}
\left[(1+\sin2\theta)^{3/2}-1\right]d\theta.
\end{aligned}
$$

所以

$$
\boxed{
S={2a^2\over3}\int_0^{\pi/2}
\left[(1+\sin2\theta)^{3/2}-1\right]d\theta.
}
$$

等价地，也可以写成两个角区间之和：

$$
\boxed{
S=\int_{[0,\pi/2]\cup[\pi,3\pi/2]}
\int_0^{a\sqrt{\sin2\theta}}
\sqrt{1+{r^2\over a^2}}\,r\,drd\theta.
}
$$

---

## 1(6) 环面面积

题目给出环面参数化：

$$
x=(b+a\cos\theta)\cos\varphi,
$$

$$
y=(b+a\cos\theta)\sin\varphi,
$$

$$
z=a\sin\theta,
$$

其中

$$
0\le\theta\le2\pi,
\qquad
0\le\varphi\le2\pi,
\qquad
0<a<b.
$$

标准环面面积元为

$$
dS=a(b+a\cos\theta)d\theta d\varphi.
$$

所以

$$
\begin{aligned}
S
&=\int_0^{2\pi}\int_0^{2\pi}a(b+a\cos\theta)
\,d\theta d\varphi \\
&=4\pi^2ab.
\end{aligned}
$$

答案：

$$
\boxed{S=4\pi^2ab}.
$$

---

# 2. 求下列第一型曲面积分

## 2(1) \(\iint_S(x+y+z)dS\)，半球面 \(x^2+y^2+z^2=a^2,\ y\le0\)

由对称性：

$$
\iint_Sx\,dS=0,
\qquad
\iint_Sz\,dS=0.
$$

在半球 $y\le0$ 上，

$$
\iint_Sy\,dS=-\pi a^3.
$$

所以

$$
\boxed{I=-\pi a^3}.
$$

---

## 2(2) \(\iint_S(x^2+y^2)dS\)，\(S\) 为 \(\sqrt{x^2+y^2}\le z\le1\) 的边界

边界由圆锥面 $z=r$ 和顶面圆盘 $z=1$ 组成。

圆锥面上：

$$
dS=\sqrt2\,r\,drd\theta,
\qquad 0\le r\le1.
$$

顶面圆盘上：

$$
dS=r\,drd\theta.
$$

所以

$$
\begin{aligned}
I
&=\int_0^{2\pi}\int_0^1 r^2\sqrt2\,r\,drd\theta
+\int_0^{2\pi}\int_0^1r^2r\,drd\theta \\
&={\pi\sqrt2\over2}+{\pi\over2}.
\end{aligned}
$$

答案：

$$
\boxed{I={\pi\over2}(1+\sqrt2)}.
$$

---

## 2(3) \(\iint_S(xy+yz+zx)dS\)，锥面被柱面 \(x^2+y^2=2ax\) 截得部分

锥面

$$
z=\sqrt{x^2+y^2}=r.
$$

柱面

$$
x^2+y^2=2ax
$$

在极坐标中为

$$
r=2a\cos\theta,
\qquad -{\pi\over2}\le\theta\le {\pi\over2}.
$$

锥面面积元：

$$
dS=\sqrt2\,r\,drd\theta.
$$

被积函数：

$$
xy+yz+zx=r^2\cos\theta\sin\theta+r^2\sin\theta+r^2\cos\theta.
$$

含 $\sin\theta$ 的项关于区间对称积分为零，只剩 $r^2\cos\theta$ 项。

所以

$$
\begin{aligned}
I
&=\sqrt2\int_{-\pi/2}^{\pi/2}\int_0^{2a\cos\theta}
r^2\cos\theta\,r\,drd\theta \\
&=\sqrt2\int_{-\pi/2}^{\pi/2}\cos\theta{(2a\cos\theta)^4\over4}d\theta \\
&=4\sqrt2a^4\int_{-\pi/2}^{\pi/2}\cos^5\theta\,d\theta \\
&=4\sqrt2a^4\cdot {16\over15}.
\end{aligned}
$$

答案：

$$
\boxed{I={64\sqrt2\over15}a^4}.
$$

---

## 2(4) \(\iint_S {1\over x^2+y^2+z^2}dS\)，圆柱面 \(x^2+y^2=a^2\)，\(0\le z\le12\)

圆柱面参数化：

$$
x=a\cos\theta,
\qquad y=a\sin\theta,
\qquad 0\le z\le12.
$$

面积元：

$$
dS=a\,d\theta dz.
$$

所以

$$
\begin{aligned}
I
&=\int_0^{2\pi}\int_0^{12}{a\over a^2+z^2}\,dzd\theta \\
&=2\pi\arctan{12\over a}.
\end{aligned}
$$

答案：

$$
\boxed{I=2\pi\arctan{12\over a}}.
$$

---

## 2(5) \(\iint_S\left({x^2\over7}+{y^2\over5}+{z^2\over4}\right)dS\)，球面 \(x^2+y^2+z^2=a^2\)

球面对称性：

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

而

$$
{1\over7}+{1\over5}+{1\over4}={83\over140}.
$$

所以

$$
\boxed{I={83\pi a^4\over105}}.
$$

---

## 2(6) \(\iint_S(x^2+y^2+z)dS\)，抛物面 \(z=x^2+y^2\)，\(0\le z\le8\)

令

$$
z=r^2,
\qquad 0\le r\le\sqrt8.
$$

面积元：

$$
dS=\sqrt{1+4r^2}\,r\,drd\theta.
$$

被积函数：

$$
x^2+y^2+z=r^2+r^2=2r^2.
$$

所以

$$
I=\int_0^{2\pi}\int_0^{\sqrt8}2r^2\sqrt{1+4r^2}\,r\,drd\theta.
$$

即

$$
I=4\pi\int_0^{\sqrt8}r^3\sqrt{1+4r^2}\,dr.
$$

令

$$
u=1+4r^2,
\qquad r^3dr={u-1\over32}du.
$$

上下限为 $1$ 到 $33$。

因此

$$
\boxed{
I={\pi\over8}\left[{2\over5}u^{5/2}-{2\over3}u^{3/2}\right]_1^{33}.
}
$$

---

## 2(7) \(\iint_S z\,dS\)，螺旋面 \(x=u\cos v,y=u\sin v,z=v\)，\(0\le u\le a,0\le v\le2\pi\)

参数化：

$$
\mathbf R(u,v)=(u\cos v,u\sin v,v).
$$

面积元：

$$
\left\|\mathbf R_u\times\mathbf R_v\right\|=\sqrt{1+u^2}.
$$

所以

$$
\begin{aligned}
I
&=\int_0^{2\pi}\int_0^a v\sqrt{1+u^2}\,dudv \\
&=\left(\int_0^{2\pi}v\,dv\right)
\left(\int_0^a\sqrt{1+u^2}\,du\right) \\
&=2\pi^2\cdot {1\over2}\left(a\sqrt{1+a^2}+\operatorname{arsinh}a\right).
\end{aligned}
$$

答案：

$$
\boxed{I=\pi^2\left(a\sqrt{1+a^2}+\operatorname{arsinh}a\right)}.
$$

---

# 3. 球面投影面积题

题意：球面 $S$ 半径为 $R$，问它在坐标平面上的投影面积。

若是普通正交投影面积，则每个坐标平面上的投影都是半径为 $R$ 的圆盘：

$$
\boxed{A=\pi R^2}.
$$

若教材指的是带重数的投影面积，即

$$
\iint_S |\cos\gamma|\,dS,
$$

则每个方向为

$$
\boxed{A=2\pi R^2}.
$$

需按教材定义确认“投影面积”是否带重数。

---

# 4. 上半椭球面积分

题意辨认为：$S$ 为上半椭球面

$$
{x^2\over2}+{y^2\over2}+z^2=1,
\qquad z\ge0,
$$

求

$$
\iint_S {z\over \rho(x,y,z)}dS,
$$

其中 $\rho(x,y,z)$ 是点到原点的距离。

写成图形：

$$
z=\sqrt{1-{x^2+y^2\over2}}.
$$

令

$$
r^2=x^2+y^2,
\qquad 0\le r\le\sqrt2.
$$

则

$$
z=\sqrt{1-{r^2\over2}},
\qquad
\rho=\sqrt{x^2+y^2+z^2}=\sqrt{1+{r^2\over2}}.
$$

面积元可算得

$$
dS={\sqrt{4-r^2}\over2z}dA.
$$

所以

$$
{z\over\rho}dS={\sqrt{4-r^2}\over2\sqrt{1+r^2/2}}dA.
$$

因此

$$
\boxed{
I=2\pi\int_0^{\sqrt2}{r\sqrt{4-r^2}\over2\sqrt{1+r^2/2}}dr.
}
$$

也可写为

$$
\boxed{
I=\pi\int_0^2\sqrt{{4-u\over2+u}}du,
\qquad u=r^2.
}
$$

---

# 5. 第二型曲面积分

第二型曲面积分统一写作通量：

$$
\iint_S P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
=\iint_S\mathbf F\cdot\mathbf n\,dS,
$$

其中

$$
\mathbf F=(P,Q,R).
$$

---

## 5(1)

题意辨认为：

$$
\iint_S (x+y)dy dz+(y+z)dz dx+(z+x)dxdy,
$$

其中 $S$ 为以原点为中心、边长为 $2h$ 的立方体表面，方向取外侧。

向量场：

$$
\mathbf F=(x+y,y+z,z+x).
$$

散度：

$$
\nabla\cdot\mathbf F=1+1+1=3.
$$

立方体体积：

$$
(2h)^3=8h^3.
$$

所以

$$
\boxed{I=3\cdot8h^3=24h^3}.
$$

---

## 5(2)

题意辨认为：

$$
\iint_S yz\,dz\,dx,
$$

其中 $S$ 是椭球

$$
{x^2\over a^2}+{y^2\over b^2}+{z^2\over c^2}=1
$$

的上半部分，方向取上侧。

向量场：

$$
\mathbf F=(0,yz,0).
$$

补上底面 $z=0$ 后成为闭曲面。底面通量为 $0$，因为 $
\mathbf F$ 没有 $z$ 分量。

散度：

$$
\nabla\cdot\mathbf F={\partial(yz)\over\partial y}=z.
$$

所以所求为上半椭球体内

$$
\iiint z\,dV.
$$

令

$$
x=au,
\qquad y=bv,
\qquad z=cw.
$$

Jacobian 为 $abc$。

单位上半球中

$$
\iiint w\,dV={\pi\over4}.
$$

所以

$$
\boxed{I={\pi ab c^2\over4}}.
$$

---

## 5(3)

题意辨认为：

$$
\iint_S z\,dy\,dz+x\,dz\,dx+y\,dx\,dy,
$$

其中 $S$ 是柱面

$$
x^2+y^2=1
$$

被平面 $z=0,z=h$ 截得的侧面，方向取外侧。

向量场：

$$
\mathbf F=(z,x,y).
$$

柱面外法向：

$$
\mathbf n=(\cos\theta,\sin\theta,0).
$$

参数：

$$
x=\cos\theta,
\qquad y=\sin\theta.
$$

于是

$$
\mathbf F\cdot\mathbf n=z\cos\theta+x\sin\theta
=z\cos\theta+
\cos\theta\sin\theta.
$$

对 $0\le\theta\le2\pi$ 积分均为零，所以

$$
\boxed{I=0}.
$$

---

## 5(4)

题意辨认为：

$$
\iint_S 8x\,dy\,dz+3b\,dx\,dy,
$$

其中 $S$ 为抛物面

$$
z=4-x^2-y^2,
\qquad z\ge0,
$$

方向取上侧。

向量场：

$$
\mathbf F=(8x,0,3b).
$$

用抛物面加底面 $z=0$ 构成闭曲面。抛物面上侧就是闭曲面的外侧。

散度：

$$
\nabla\cdot\mathbf F=8.
$$

体积：

$$
V=\int_0^{2\pi}\int_0^2(4-r^2)r\,drd\theta=8\pi.
$$

闭曲面通量：

$$
8V=64\pi.
$$

底面外法向向下，底面通量：

$$
-3b\cdot \pi(2)^2=-12\pi b.
$$

所以抛物面通量：

$$
I=64\pi-(-12\pi b)=64\pi+12\pi b.
$$

答案：

$$
\boxed{I=64\pi+12\pi b}.
$$

---

## 5(5)

题目字迹不完全清楚，形式大约为含 $f(x,y,z)$ 的第二型曲面积分，曲面为平面

$$
x-y+z=1
$$

在第一卦限的部分，方向取上侧。

若要计算，通用方法是：

平面写成

$$
z=1-x+y.
$$

上侧有向面积元：

$$
\mathbf n\,dS=(-z_x,-z_y,1)dxdy=(1,-1,1)dxdy.
$$

然后把向量场

$$
\mathbf F=(P,Q,R)
$$

代入：

$$
\iint_S\mathbf F\cdot\mathbf n\,dS
=\iint_D \mathbf F(x,y,1-x+y)\cdot(1,-1,1)dxdy.
$$

需要确认原题中 $f$ 的条件后才能继续化简。

---

## 5(6)

题意辨认为：

$$
\iint_S x^2dy dz+y^2dz dx+(z^2+5)dxdy,
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

用锥面和顶面圆盘 $z=h$ 构成闭曲面。实心圆锥外侧在锥面上就是下侧。

散度：

$$
\nabla\cdot\mathbf F=2x+2y+2z.
$$

由对称性，体内 $x,y$ 项积分为零。

圆锥体积积分：

$$
\iiint_V2z\,dV=2\int_0^h z\cdot \pi z^2dz={\pi h^4\over2}.
$$

顶面 $z=h$ 外法向向上，通量为

$$
\pi h^2(h^2+5).
$$

所以锥面通量：

$$
I={\pi h^4\over2}-\pi h^2(h^2+5)
=-{\pi h^4\over2}-5\pi h^2.
$$

答案：

$$
\boxed{I=-{\pi h^4\over2}-5\pi h^2}.
$$

---

## 5(7)、5(8)

这两题字迹和分母表达式不够清楚，暂不强行给最终值。

可按如下流程：

1. 先把积分写成通量形式

$$
\iint_S\mathbf F\cdot\mathbf n\,dS.
$$

2. 若曲面封闭且场无奇点，用 Gauss 公式。

3. 若曲面是图形曲面，用

$$
\mathbf n\,dS=(-f_x,-f_y,1)dxdy
$$

或对应方向的相反数。

4. 若是椭球面，优先考虑椭球变换或对称性。

---

## 5(9)

题意辨认为：

$$
\iint_S x^2dy dz+y^2dz dx+z^2dxdy,
$$

其中 $S$ 是球面

$$
(x-a)^2+(y-b)^2+(z-c)^2=R^2,
$$

方向取外侧。

向量场：

$$
\mathbf F=(x^2,y^2,z^2).
$$

散度：

$$
\nabla\cdot\mathbf F=2x+2y+2z.
$$

球心为 $(a,b,c)$，球体积为

$$
{4\over3}\pi R^3.
$$

由对称性：

$$
\iiint_Vx\,dV=a\operatorname{Vol}(V),
$$

同理对 $y,z$ 成立。

所以

$$
\begin{aligned}
I
&=\iiint_V(2x+2y+2z)dV \\
&=2(a+b+c){4\over3}\pi R^3.
\end{aligned}
$$

答案：

$$
\boxed{I={8\pi R^3\over3}(a+b+c)}.
$$

---

## 1(5) 继续化简积分

上一式为

$$
S={2a^2\over3}\int_0^{\pi/2}
\left[(1+
\sin2\theta)^{3/2}-1\right]d\theta.
$$

先化简

$$
1+\sin2\theta.
$$

因为

$$
1+\sin2\theta
=\sin^2\theta+
\cos^2\theta+2\sin\theta\cos\theta
=(\sin\theta+
\cos\theta)^2.
$$

在

$$
0\le\theta\le{\pi\over2}
$$

上，

$$
\sin\theta+
\cos\theta\ge0,
$$

所以

$$
(1+
\sin2\theta)^{3/2}
=(\sin\theta+
\cos\theta)^3.
$$

于是

$$
\int_0^{\pi/2}
\left[(1+
\sin2\theta)^{3/2}-1\right]d\theta
=\int_0^{\pi/2}(\sin\theta+
\cos\theta)^3d\theta-{\pi\over2}.
$$

计算

$$
\int_0^{\pi/2}(\sin\theta+
\cos\theta)^3d\theta.
$$

令

$$
u=\theta-{\pi\over4}.
$$

则

$$
\sin\theta+
\cos\theta=\sqrt2\cos u.
$$

当

$$
\theta=0,
$$

有

$$
u=-{\pi\over4};
$$

当

$$
\theta={\pi\over2},
$$

有

$$
u={\pi\over4}.
$$

所以

$$
\begin{aligned}
\int_0^{\pi/2}(\sin\theta+
\cos\theta)^3d\theta
&=\int_{-\pi/4}^{\pi/4}(\sqrt2\cos u)^3du \\
&=2\sqrt2\int_{-\pi/4}^{\pi/4}\cos^3u\,du \\
&=4\sqrt2\int_0^{\pi/4}\cos^3u\,du.
\end{aligned}
$$

注意这里上限是

$$
{\pi\over4},
$$

不是

$$
{\pi\over2}.
$$

所以不能直接用

$$
\int_0^{\pi/2}\cos^3u\,du={2\over3}
$$

这个双阶乘公式。

现在算

$$
\int_0^{\pi/4}\cos^3u\,du.
$$

因为

$$
\cos^3u=\cos u(1-
\sin^2u),
$$

所以

$$
\int\cos^3u\,du
=\sin u-{1\over3}\sin^3u.
$$

代入 $0$ 到 $\pi/4$：

$$
\begin{aligned}
\int_0^{\pi/4}\cos^3u\,du
&=\sin{\pi\over4}-{1\over3}\sin^3{\pi\over4} \\
&={\sqrt2\over2}-{1\over3}{\sqrt2\over4} \\
&={\sqrt2\over2}-{\sqrt2\over12} \\
&={5\sqrt2\over12}.
\end{aligned}
$$

因此

$$
\int_0^{\pi/2}(\sin\theta+
\cos\theta)^3d\theta
=4\sqrt2\cdot {5\sqrt2\over12}
={40\over12}
={10\over3}.
$$

所以

$$
\int_0^{\pi/2}
\left[(1+
\sin2\theta)^{3/2}-1\right]d\theta
={10\over3}-{\pi\over2}.
$$

最终

$$
\boxed{
S={2a^2\over3}\left({10\over3}-{\pi\over2}\right)
}
$$

也就是

$$
\boxed{
S={20a^2\over9}-{\pi a^2\over3}.
}
$$

你写的思路中“换成余弦再用双阶乘”方向是对的，但区间变成了

$$
[-\pi/4,\pi/4],
$$

不是完整的

$$
[-\pi/2,\pi/2]
$$

或

$$
[0,\pi/2],
$$

所以不能直接套

$$
\int_0^{\pi/2}\cos^3u\,du={2!!\over3!!}={2\over3}.
$$

---

## 1(5) 另一种更顺的化简：直接换成余弦并用降幂/三倍角

要算

$$
I=\int_0^{\pi/2}(1+
\sin2\theta)^{3/2}d\theta.
$$

先把正弦换成余弦：

$$
\sin2\theta=\cos\left(2\theta-{\pi\over2}
\right).
$$

所以

$$
1+\sin2\theta
=1+
\cos\left(2\theta-{\pi\over2}\right).
$$

用公式

$$
1+\cos A=2\cos^2{A\over2}.
$$

得到

$$
1+
\sin2\theta
=2\cos^2\left(\theta-{\pi\over4}\right).
$$

在区间

$$
0\le\theta\le {\pi\over2}
$$

内，

$$
\theta-{\pi\over4}\in\left[-{\pi\over4},{\pi\over4}\right],
$$

此时余弦为正，所以

$$
(1+
\sin2\theta)^{3/2}
=\left[2\cos^2\left(\theta-{\pi\over4}\right)
\right]^{3/2}
=2\sqrt2\cos^3\left(\theta-{\pi\over4}\right).
$$

令

$$
u=\theta-{\pi\over4}.
$$

则

$$
I=2\sqrt2\int_{-\pi/4}^{\pi/4}\cos^3u\,du.
$$

利用对称性，$\cos^3u$ 是偶函数，所以

$$
I=4\sqrt2\int_0^{\pi/4}\cos^3u\,du.
$$

现在用三倍角降幂公式：

$$
\cos^3u={3\cos u+
\cos3u\over4}.
$$

因此

$$
\begin{aligned}
\int_0^{\pi/4}\cos^3u\,du
&=\int_0^{\pi/4}{3\cos u+
\cos3u\over4}du \\
&={3\over4}\sin u\bigg|_0^{\pi/4}
+{1\over12}\sin3u\bigg|_0^{\pi/4} \\
&={3\over4}\cdot {\sqrt2\over2}
+{1\over12}\cdot {\sqrt2\over2} \\
&={3\sqrt2\over8}+{\sqrt2\over24} \\
&={10\sqrt2\over24} \\
&={5\sqrt2\over12}.
\end{aligned}
$$

所以

$$
I=4\sqrt2\cdot {5\sqrt2\over12}={10\over3}.
$$

于是原面积中的括号积分为

$$
\int_0^{\pi/2}\left[(1+
\sin2\theta)^{3/2}-1\right]d\theta
={10\over3}-{\pi\over2}.
$$

最终仍是

$$
\boxed{
S={2a^2\over3}\left({10\over3}-{\pi\over2}\right).
}
$$

---

# Green 公式的条件、多连通区域与挖洞

## 1. Green 公式的基本条件

设平面区域 $D$ 的边界为 $\partial D$，向量场为

$$
\mathbf F=(P,Q).
$$

Green 公式的环流形式为

$$
\boxed{
\oint_{\partial D}P\,dx+Q\,dy
=
\iint_D\left(Q_x-P_y\right)dx\,dy.
}
$$

常用的充分条件是：

1. $D$ 是有界平面区域；
2. 边界 $\partial D$ 是闭合的、分片光滑的曲线；
3. $P,Q$ 在包含 $\overline D$ 的开集上具有连续一阶偏导数，即

$$
P,Q\in C^1.
$$

这里不要求 $D$ 一定没有洞。

有洞的多连通区域仍然可以使用 Green 公式，只是必须正确处理所有边界方向。

---

## 2. 有洞区域的边界方向

设区域 $D$ 有一个洞：

- 外边界记为 $C_0$；
- 洞的边界记为 $C_1$。

区域的正向边界要求：沿边界正方向行走时，区域始终位于左手侧。

因此：

- 外边界 $C_0$ 取逆时针方向；
- 内边界 $C_1$ 取顺时针方向。

所以区域的完整有向边界是

$$
\partial D=C_0-C_1,
$$

其中这里的 $C_1$ 默认表示逆时针曲线，而负号表示实际要沿顺时针方向积分。

Green 公式为

$$
\boxed{
\oint_{C_0}^{\mathrm{CCW}}Pdx+Qdy
-
\oint_{C_1}^{\mathrm{CCW}}Pdx+Qdy
=
\iint_D(Q_x-P_y)dA.
}
$$

等价地，把洞边界积分移到右边：

$$
\boxed{
\oint_{C_0}^{\mathrm{CCW}}Pdx+Qdy
=
\iint_D(Q_x-P_y)dA
+
\oint_{C_1}^{\mathrm{CCW}}Pdx+Qdy.
}
$$

所以你说的“面积积分结果再加上沿洞边缘的积分”，在洞边界取逆时针方向时是正确的。

---

## 3. 有多个洞时

若区域有 $m$ 个洞，外边界为 $C_0$，洞边界为 $C_1,\dots,C_m$，并且所有 $C_i$ 都按照逆时针记号表示，则

$$
\boxed{
\oint_{C_0}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r
=
\iint_D\operatorname{curl}\mathbf F\,dA
+
\sum_{i=1}^m
\oint_{C_i}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r.
}
$$

其中二维旋度为

$$
\operatorname{curl}\mathbf F=Q_x-P_y.
$$

---

## 4. 这是不是“旋度相加”

不完全是。

面积积分

$$
\iint_D(Q_x-P_y)dA
$$

才是区域 $D$ 内部局部旋度的累加。

洞边界积分

$$
\oint_{C_i}\mathbf F\cdot d\mathbf r
$$

是绕着被挖掉区域的环流，不是区域 $D$ 内旋度的面积积分。

因此更准确地说：

$$
\boxed{
\text{外边界环流}
=
\text{剩余区域内的旋度总量}
+
\text{各洞的逆时针边界环流}.
}
$$

洞边界环流可能代表：

- 被挖掉区域内部本来存在的旋度；
- 或者洞里存在奇点，导致向量场不能在那里使用 Green 公式。

---

## 5. 如果向量场在洞内也光滑

如果 $P,Q$ 在洞内部也有连续一阶偏导，那么可以把洞填回去，并对洞区域 $H$ 使用 Green 公式：

$$
\oint_{\partial H}^{\mathrm{CCW}}Pdx+Qdy
=
\iint_H(Q_x-P_y)dA.
$$

于是

$$
\begin{aligned}
\oint_{C_0}^{\mathrm{CCW}}Pdx+Qdy
&=
\iint_D(Q_x-P_y)dA
+
\iint_H(Q_x-P_y)dA \\
&=
\iint_{D\cup H}(Q_x-P_y)dA.
\end{aligned}
$$

也就是说，如果洞里没有奇点，洞边界积分确实可以进一步理解成洞内旋度的面积积分。

---

## 6. 如果洞里存在奇点

典型例子：

$$
\mathbf F=
\left(
-{y\over x^2+y^2},
{x\over x^2+y^2}
\right).
$$

在原点之外，

$$
Q_x-P_y=0.
$$

但向量场在原点没有定义。

若闭曲线绕原点一周，则

$$
\oint_C\mathbf F\cdot d\mathbf r=2\pi.
$$

不能直接把曲线内部整个圆盘作为 $D$ 使用 Green 公式，因为原点处不满足 $C^1$ 条件。

正确做法是挖掉原点附近的小圆盘，得到环形区域。环形区域内旋度为零，因此

$$
\oint_{C_{\text{outer}}}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r
=
\oint_{C_{\text{inner}}}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r.
$$

洞边界积分记录了奇点产生的非零环流。

---

## 7. 为什么内部边界方向相反

把有洞区域切成许多小块，对每个小块使用局部 Green 公式。

相邻小块共享的内部边会以相反方向出现，因此互相抵消。

最终只剩：

- 外边界逆时针；
- 洞边界顺时针。

这是区域始终位于行进方向左侧的结果，也是广义 Stokes 公式中边界方向的统一规则。

---

## 8. 总结

Green 公式不要求区域必须无洞，但要求向量场在实际积分区域附近具有连续一阶偏导，且边界分片光滑、闭合。

有洞时：

$$
\boxed{
\text{外边界逆时针，洞边界顺时针。}
}
$$

若把洞边界统一写成逆时针，则

$$
\boxed{
\text{外边界环流}
=
\text{区域内旋度积分}
+
\text{洞边界逆时针环流}.
}
$$

只有当向量场在洞内也光滑时，洞边界环流才能继续转成洞内的旋度面积积分。

---

# 有洞区域的 Green 公式具体怎么计算

设环形区域为

$$
D=\text{外边界 }C_0\text{ 与洞边界 }C_1\text{ 之间的区域}.
$$

规定：

- $C_0$ 按逆时针方向；
- $C_1$ 也按逆时针方向书写。

但对于环形区域 $D$ 来说，真正的正向边界是：

$$
\partial D=C_0^{\mathrm{CCW}}+C_1^{\mathrm{CW}}.
$$

因为

$$
C_1^{\mathrm{CW}}=-C_1^{\mathrm{CCW}},
$$

所以

$$
\partial D=C_0^{\mathrm{CCW}}-C_1^{\mathrm{CCW}}.
$$

Green 公式给出

$$
\oint_{C_0}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r
-
\oint_{C_1}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r
=
\iint_D\operatorname{curl}\mathbf F\,dA.
$$

移项得到

$$
\boxed{
\oint_{C_0}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r
=
\iint_D\operatorname{curl}\mathbf F\,dA
+
\oint_{C_1}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r.
}
$$

所以确实是：

$$
\boxed{
\text{外边界逆时针环流}
=
\text{环形区域内旋度面积分}
+
\text{洞边界逆时针环流}.
}
$$

---

## 具体计算步骤

要求外边界逆时针环流：

$$
I_0=\oint_{C_0}^{\mathrm{CCW}}Pdx+Qdy.
$$

### 第一步：计算环形区域内的旋度

$$
\operatorname{curl}\mathbf F=Q_x-P_y.
$$

然后计算

$$
I_D=\iint_D(Q_x-P_y)dA.
$$

### 第二步：直接计算洞边界逆时针环流

$$
I_1=\oint_{C_1}^{\mathrm{CCW}}Pdx+Qdy.
$$

洞边界通常是简单圆周，可以参数化：

$$
x=r_0\cos t,
\qquad y=r_0\sin t,
\qquad 0\le t\le2\pi.
$$

### 第三步：相加

$$
\boxed{I_0=I_D+I_1}.
$$

---

## 例子：洞内有奇点

设

$$
\mathbf F=
\left(
-{y\over x^2+y^2},
{x\over x^2+y^2}
\right).
$$

外边界 $C_0$ 围绕原点，挖掉原点附近一个小圆盘，洞边界为

$$
C_1:\quad x^2+y^2=\varepsilon^2.
$$

在环形区域 $D$ 内，向量场光滑，并且

$$
Q_x-P_y=0.
$$

所以

$$
I_D=\iint_D0\,dA=0.
$$

计算洞边界逆时针环流。参数化：

$$
x=\varepsilon\cos t,
\qquad y=\varepsilon\sin t,
\qquad 0\le t\le2\pi.
$$

则

$$
dx=-\varepsilon\sin t\,dt,
\qquad dy=\varepsilon\cos t\,dt.
$$

并且

$$
P=-{\sin t\over\varepsilon},
\qquad
Q={\cos t\over\varepsilon}.
$$

于是

$$
\begin{aligned}
Pdx+Qdy
&=\left(-{\sin t\over\varepsilon}\right)
(-\varepsilon\sin t\,dt)
+
\left({\cos t\over\varepsilon}\right)
(\varepsilon\cos t\,dt) \\
&=(\sin^2t+\cos^2t)dt \\
&=dt.
\end{aligned}
$$

所以

$$
I_1=\int_0^{2\pi}dt=2\pi.
$$

最终外边界逆时针环流为

$$
I_0=I_D+I_1=0+2\pi=2\pi.
$$

即

$$
\boxed{
\oint_{C_0}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r=2\pi.
}
$$

---

## 多个洞

若有多个洞 $C_1,\dots,C_m$，全部按照逆时针方向计算，则

$$
\boxed{
\oint_{C_0}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r
=
\iint_D\operatorname{curl}\mathbf F\,dA
+
\sum_{i=1}^m
\oint_{C_i}^{\mathrm{CCW}}\mathbf F\cdot d\mathbf r.
}
$$

口诀：

$$
\boxed{
\text{外圈逆时针}
=
\text{剩余区域旋度积分}
+
\text{所有洞圈逆时针环流}.
}
$$

---

# Green 定理可以和哪些定理互相推导

## 1. Green 定理的两种形式

设平面向量场

$$
\mathbf F=(P,Q),
$$

区域 $D$ 的正向边界 $\partial D$ 为逆时针方向。

### 环流形式

$$
\boxed{
\oint_{\partial D}P\,dx+Q\,dy
=
\iint_D(Q_x-P_y)\,dA.
}
$$

左边是切向环流，右边是二维旋度积分。

### 通量形式

$$
\boxed{
\oint_{\partial D}P\,dy-Q\,dx
=
\iint_D(P_x+Q_y)\,dA.
}
$$

左边是向量场穿过外边界的通量，右边是二维散度积分。

---

## 2. Green 两种形式可以互推

从环流形式出发，将向量场旋转九十度。

令

$$
\widetilde{\mathbf F}=(-Q,P).
$$

对 $\widetilde{\mathbf F}$ 使用环流形式：

$$
\oint_{\partial D}(-Q)\,dx+P\,dy
=
\iint_D\left(P_x-(-Q)_y\right)dA.
$$

因此

$$
\oint_{\partial D}P\,dy-Q\,dx
=
\iint_D(P_x+Q_y)dA.
$$

这就是通量形式。

反过来也同样成立。

所以：

$$
\boxed{
\text{Green 环流形式与通量形式可通过向量场旋转 }90^\circ\text{ 互推。}
}
$$

---

## 3. Green 环流形式是三维 Stokes 定理的平面特例

三维 Stokes 定理：

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=
\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

将平面向量场嵌入三维：

$$
\mathbf F=(P,Q,0).
$$

取曲面 $S$ 为 $xy$ 平面内的区域 $D$，法向量为

$$
\mathbf n=(0,0,1).
$$

则

$$
\nabla\times\mathbf F
=(0,0,Q_x-P_y).
$$

所以

$$
(\nabla\times\mathbf F)\cdot\mathbf n
=Q_x-P_y.
$$

于是 Stokes 定理变成

$$
\oint_{\partial D}Pdx+Qdy
=
\iint_D(Q_x-P_y)dA.
$$

这正是 Green 环流形式。

因此：

$$
\boxed{
\text{Green 环流公式是 Stokes 定理的二维平面特例。}
}
$$

从广义 Stokes 角度，二者本来就是同一个定理。

---

## 4. Green 通量形式是二维 Gauss 散度定理

三维 Gauss 定理：

$$
\iint_{\partial\Omega}\mathbf F\cdot\mathbf n\,dS
=
\iiint_\Omega\nabla\cdot\mathbf F\,dV.
$$

二维对应形式为

$$
\oint_{\partial D}\mathbf F\cdot\mathbf n\,ds
=
\iint_D\nabla\cdot\mathbf F\,dA.
$$

逆时针边界上：

$$
\mathbf n\,ds=(dy,-dx).
$$

因此

$$
\mathbf F\cdot\mathbf n\,ds
=(P,Q)\cdot(dy,-dx)
=Pdy-Qdx.
$$

于是得到

$$
\oint_{\partial D}Pdy-Qdx
=
\iint_D(P_x+Q_y)dA.
$$

所以：

$$
\boxed{
\text{Green 通量公式就是二维 Gauss 散度定理。}
}
$$

---

## 5. Green 定理可以由一维 Newton--Leibniz 公式推出

对于简单区域，可以通过分层积分和一维微积分基本定理证明 Green 公式。

例如设

$$
D=\{(x,y):a\le x\le b,\ \varphi_1(x)\le y\le\varphi_2(x)\}.
$$

那么

$$
\iint_D-P_y\,dA
=
-\int_a^b\left[
P(x,\varphi_2(x))-P(x,\varphi_1(x))
\right]dx.
$$

这正好对应上下边界上的

$$
\int Pdx
$$

之和。

类似地，对适合按 $y$ 分层的区域：

$$
\iint_DQ_x\,dA
$$

对应左右边界上的

$$
\int Qdy.
$$

两部分相加得到 Green 公式。

因此 Green 定理可以看成：

$$
\boxed{
\text{一维 Newton--Leibniz 公式在二维区域上的累加。}
}
$$

严格证明通常还需要把一般区域分割为有限个简单区域，并利用内部边界积分互相抵消。

---

## 6. Green 定理可以推出平面面积公式

在 Green 公式中选择合适的 $P,Q$，使

$$
Q_x-P_y=1.
$$

例如取

$$
P=0,
\qquad Q=x.
$$

则

$$
Q_x-P_y=1.
$$

所以区域面积为

$$
\boxed{
\operatorname{Area}(D)=\oint_{\partial D}x\,dy.
}
$$

也可以取

$$
P=-y,
\qquad Q=0,
$$

得到

$$
\boxed{
\operatorname{Area}(D)=-\oint_{\partial D}y\,dx.
}
$$

两式平均得到常用面积公式：

$$
\boxed{
\operatorname{Area}(D)
={1\over2}\oint_{\partial D}(x\,dy-y\,dx).
}
$$

---

## 7. Green 定理可以推出路径无关判据

若在单连通区域 $D$ 内

$$
Q_x-P_y=0,
$$

则对任意闭曲线 $C\subset D$，由 Green 公式：

$$
\oint_C Pdx+Qdy=0.
$$

因此线积分与路径无关，并且存在势函数 $u$，使

$$
du=Pdx+Qdy.
$$

所以 Green 定理给出：

$$
\boxed{
Q_x=P_y
\quad\Longrightarrow\quad
\text{闭路积分为零、路径无关、局部可找原函数。}
}
$$

这里需要单连通条件；若区域有洞或奇点，仅有

$$
Q_x=P_y
$$

不一定能推出所有闭路积分为零。

---

## 8. Green 第一恒等式可由散度定理推出

注意：这里的 Green 第一恒等式与前面的平面 Green 公式名字相近，但对象不同。

设标量函数 $u,v$，取向量场

$$
\mathbf F=u\nabla v.
$$

根据乘积求导：

$$
\nabla\cdot(u\nabla v)
=\nabla u\cdot\nabla v+u\Delta v.
$$

对区域 $\Omega$ 使用散度定理：

$$
\iiint_\Omega\nabla\cdot(u\nabla v)dV
=
\iint_{\partial\Omega}u{\partial v\over\partial n}dS.
$$

因此得到 Green 第一恒等式：

$$
\boxed{
\iiint_\Omega
\left(\nabla u\cdot\nabla v+u\Delta v\right)dV
=
\iint_{\partial\Omega}u{\partial v\over\partial n}dS.
}
$$

二维时将三重积分换成二重积分即可。

---

## 9. Green 第二恒等式由两个第一恒等式相减得到

交换 $u,v$，Green 第一恒等式还给出

$$
\iiint_\Omega
\left(\nabla v\cdot\nabla u+v\Delta u\right)dV
=
\iint_{\partial\Omega}v{\partial u\over\partial n}dS.
$$

两式相减，梯度点积项抵消，得到 Green 第二恒等式：

$$
\boxed{
\iiint_\Omega(u\Delta v-v\Delta u)dV
=
\iint_{\partial\Omega}
\left(
u{\partial v\over\partial n}
-v{\partial u\over\partial n}
\right)dS.
}
$$

它在调和函数、Poisson 方程和边值问题中非常重要。

---

## 10. 所有这些定理在广义 Stokes 下统一

广义 Stokes 定理是

$$
\boxed{
\int_Md\omega=\int_{\partial M}\omega.
}
$$

它的不同特例包括：

| 维度与形式 | 得到的定理 |
|---|---|
| 区间上的 $0$-形式 | Newton--Leibniz |
| 平面区域上的 $1$-形式 | Green 环流公式 |
| 曲面上的 $1$-形式 | 三维 Stokes 定理 |
| 平面区域上的通量形式 | Green 通量公式 / 二维 Gauss |
| 三维体区域上的 $2$-形式 | Gauss 散度定理 |

所以从现代观点看，它们不是许多互不相关的定理，而是同一个“内部微分积分等于边界积分”的结构。

---

## 11. 互推关系图

可以整理为：

$$
\boxed{
\text{Newton--Leibniz}
\xrightarrow[\text{分层积分、内部边抵消}]{}
\text{Green}
}
$$

$$
\boxed{
\text{Green 环流形式}
\xleftrightarrow[\text{向量场旋转 }90^\circ]{}
\text{Green 通量形式}
}
$$

$$
\boxed{
\text{Green 环流形式}
=\text{平面 Stokes 特例}
}
$$

$$
\boxed{
\text{Green 通量形式}
=\text{二维 Gauss 特例}
}
$$

$$
\boxed{
\text{Gauss 定理}
+\text{乘积求导}
\Longrightarrow
\text{Green 第一恒等式}
\Longrightarrow
\text{Green 第二恒等式}
}
$$

需要注意：低维 Green 公式可以作为高维 Stokes/Gauss 的特例，但仅靠一个固定平面的 Green 公式，不能直接证明完整的任意曲面 Stokes 定理或任意三维区域 Gauss 定理；完整高维结论还需要局部参数化、分片和内部边界抵消。

---

# 无旋场怎么构造势函数：变上限积分的推广

## 1. 一维情形：变上限积分

在一维中，如果

$$
f'(x)=g(x),
$$

那么可以构造

$$
f(x)=f(x_0)+\int_{x_0}^x g(t)dt.
$$

这就是变上限积分。

它的核心是：从固定基点 $x_0$ 出发，沿区间积累导数。

---

## 2. 多维情形：沿路径积分

在多维中，设向量场

$$
\mathbf F=(P,Q)
$$

或

$$
\mathbf F=(P,Q,R).
$$

如果它是某个势函数 $u$ 的梯度：

$$
\nabla u=\mathbf F,
$$

那么

$$
du=\mathbf F\cdot d\mathbf r.
$$

于是从基点 $A$ 到点 $X$，应该有

$$
u(X)-u(A)=\int_A^X\mathbf F\cdot d\mathbf r.
$$

所以可以定义

$$
\boxed{
 u(X)=u(A)+\int_{A}^{X}\mathbf F\cdot d\mathbf r.
}
$$

这就是一维变上限积分在多维中的推广。

区别是：多维中从 $A$ 到 $X$ 有很多路径。

因此要想定义良好，必须保证路径无关。

---

## 3. 什么时候路径无关

在平面中，若区域单连通且

$$
P_y=Q_x,
$$

则闭路积分为零，线积分路径无关。

在空间中，若区域单连通且

$$
\nabla\times\mathbf F=0,
$$

则路径无关。

所以：

$$
\boxed{
\text{无旋} + \text{单连通} \Longrightarrow \text{存在势函数。}
}
$$

如果区域有洞，单纯无旋不一定够。

例如

$$
\mathbf F=
\left(-{y\over x^2+y^2},{x\over x^2+y^2}
\right)
$$

在去掉原点的区域无旋，但绕原点一圈的积分为 $2\pi$，所以没有全局单值势函数。

---

## 4. 构造法一：选一条方便路径

如果路径无关，就可以随便选从基点到 $(x,y)$ 的路径。

平面中常用折线路径：

$$
(x_0,y_0)\to(x,y_0)\to(x,y).
$$

则定义

$$
\boxed{
 u(x,y)=u(x_0,y_0)
 +\int_{x_0}^{x}P(s,y_0)ds
 +\int_{y_0}^{y}Q(x,t)dt.
}
$$

为什么第二段用 $Q(x,t)$？

因为第二段中 $x$ 固定，$dy=dt$，所以

$$
Pdx+Qdy=Q(x,t)dt.
$$

若取基点为 $(0,0)$，常写成

$$
\boxed{
 u(x,y)=C+\int_0^x P(s,0)ds+
\int_0^y Q(x,t)dt.
}
$$

前提是这条路径完全位于定义区域内。

---

## 5. 空间中的折线路径构造

空间中可取路径：

$$
(x_0,y_0,z_0)	o(x,y_0,z_0)	o(x,y,z_0)	o(x,y,z).
$$

若

$$
\mathbf F=(P,Q,R),
$$

则

$$
\boxed{
\begin{aligned}
u(x,y,z)=C
&+\int_{x_0}^{x}P(s,y_0,z_0)ds \\
&+\int_{y_0}^{y}Q(x,t,z_0)dt \\
&+\int_{z_0}^{z}R(x,y,w)dw.
\end{aligned}
}
$$

这就是三维版的变上限积分。

---

## 6. 构造法二：逐项积分法

这是做题中最常用的方法。

设平面场

$$
\mathbf F=(P,Q)
$$

要求

$$
u_x=P,
\qquad
u_y=Q.
$$

先对 $P$ 关于 $x$ 积分：

$$
u(x,y)=\int P(x,y)dx+C(y).
$$

这里 $C(y)$ 是关于 $y$ 的未知函数。

再对 $u$ 求 $y$ 偏导，并令

$$
u_y=Q.
$$

由此解出 $C'(y)$，再积分得到 $C(y)$。

空间中同理：

先由

$$
u_x=P
$$

得到

$$
u=\int Pdx+C(y,z),
$$

再用

$$
u_y=Q,
\qquad
u_z=R
$$

逐步确定 $C(y,z)$。

---

## 7. 两种方法的关系

折线路径积分法更概念清楚：

$$
\boxed{
\text{势函数}=\text{从基点到当前点的路径积分。}
}
$$

逐项积分法更适合手算：

$$
\boxed{
\text{先对一个分量积分，再用其他分量补常数函数。}
}
$$

它们本质上是同一件事。

逐项积分法相当于隐式选择了一条折线路径，并把结果整理成函数表达式。

---

## 8. 例子

设

$$
\mathbf F=(2xy+y^2,\ x^2+2xy).
$$

先检查：

$$
P_y=2x+2y,
\qquad
Q_x=2x+2y.
$$

所以无旋。

构造势函数。

由

$$
u_x=2xy+y^2,
$$

对 $x$ 积分：

$$
u=x^2y+xy^2+C(y).
$$

再求 $y$ 偏导：

$$
u_y=x^2+2xy+C'(y).
$$

要求

$$
u_y=Q=x^2+2xy.
$$

所以

$$
C'(y)=0.
$$

因此

$$
C(y)=C.
$$

势函数为

$$
\boxed{
u=x^2y+xy^2+C.}
$$

---

## 9. 为什么有时不好找

势函数不好找通常有几个原因：

1. 分量表达式复杂，逐项积分困难；
2. 区域不是单连通，无旋不保证全局势函数；
3. 向量场有奇点，不能跨过奇点随便换路径；
4. 有些势函数包含反三角函数、对数等，不容易一眼看出。

这时用路径积分定义更稳：

$$
u(X)=\int_A^X\mathbf F\cdot d\mathbf r.
$$

选一条方便路径，把积分算出来即可。

---

## 10. 总结

势函数构造就是多维变上限积分：

$$
\boxed{
 u(X)=u(A)+\int_A^X\mathbf F\cdot d\mathbf r.
}
$$

若区域单连通且无旋，则路径无关，这个定义良好。

做题时有两种算法：

$$
\boxed{
\text{路径积分法：选基点和路径。}
}
$$

$$
\boxed{
\text{逐项积分法：先对一个分量积分，再补未知函数。}
}
$$

---

## 无旋场如何构造势函数：变上限积分的推广

设平面向量场

$$
\mathbf F=(P(x,y),Q(x,y))
$$

在区域 $D$ 上一阶连续可偏导。若要找势函数 $u$，就是要解

$$
\nabla u=\mathbf F,
\qquad
u_x=P,
\quad
u_y=Q.
$$

### 1. 一维变上限积分的类比

一维中如果

$$
u'(x)=f(x),$$

那么可以取

$$
u(x)=\nu(x_0)+\int_{x_0}^{x}f(t)\,dt.$$

多维中对应地，若 $A$ 是固定基点，$X$ 是动点，可以定义

$$
\boxed{
 u(X)=u(A)+\int_A^X \mathbf F\cdot d\mathbf r.
}
$$

这就是“变上限积分”的多维版本。区别是：多维中从 $A$ 到 $X$ 有很多条路径，所以必须保证这个积分与路径无关。

### 2. 为什么无旋还需要单连通

若

$$
\nabla\times \mathbf F=0,
$$

或者在二维中

$$
Q_x-P_y=0,
$$

这说明局部上路径积分不绕出净环流。但要推出全局路径无关，通常还要求区域 $D$ 单连通。

充分条件是：

$$
\boxed{
D\text{ 单连通},\quad \mathbf F\in C^1(D),\quad \nabla\times\mathbf F=0
\Longrightarrow
\mathbf F\text{ 有势函数}.}
$$

如果区域有洞，无旋不一定有全局势函数。例如

$$
\mathbf F=\left(-\frac{y}{x^2+y^2},\frac{x}{x^2+y^2}\right)
$$

在去掉原点的平面上无旋，但绕原点一圈的环流为 $2\pi$，所以没有全局单值势函数。

### 3. 构造法一：选一条折线路径

在平面中选基点 $(x_0,y_0)$。从 $(x_0,y_0)$ 到 $(x,y)$ 可以走折线：

$$
(x_0,y_0)\to (x,y_0)\to (x,y).
$$

于是定义

$$
\boxed{
 u(x,y)=C+
 \int_{x_0}^{x}P(s,y_0)\,ds
 +\int_{y_0}^{y}Q(x,t)\,dt.
}
$$

这里第一段只有 $x$ 变，所以 $d\mathbf r=(ds,0)$；第二段只有 $y$ 变，所以 $d\mathbf r=(0,dt)$。

若无旋且区域单连通，换别的路径也得到同一个 $u$，最多差一个常数。

三维同理，例如从 $(x_0,y_0,z_0)$ 走三段折线：

$$
(x_0,y_0,z_0)	o(x,y_0,z_0)	o(x,y,z_0)	o(x,y,z).
$$

若

$$
\mathbf F=(P,Q,R),
$$

则可取

$$
\boxed{
 u(x,y,z)=C+
 \int_{x_0}^{x}P(s,y_0,z_0)\,ds
 +\int_{y_0}^{y}Q(x,t,z_0)\,dt
 +\int_{z_0}^{z}R(x,y,w)\,dw.
}
$$

### 4. 构造法二：逐项积分，补“常数函数”

二维中由

$$
u_x=P$$

先对 $x$ 积分：

$$
u=\int P(x,y)\,dx+C(y).
$$

注意这里的“常数”可以依赖于 $y$，因为对 $x$ 求偏导时它会消失。

然后再用

$$
u_y=Q$$

求出 $C'(y)$，进而确定 $C(y)$。

三维中类似：先由 $u_x=P$ 积分，得到

$$
u=\int P(x,y,z)\,dx+C(y,z),$$

再用 $u_y=Q$、$u_z=R$ 依次确定 $C(y,z)$。

### 5. 本质总结

无旋场的势函数不是靠“猜原函数”，而是靠线积分定义：

$$
\boxed{
 u(X)=u(A)+\int_A^X\mathbf F\cdot d\mathbf r.
}
$$

逐项积分法只是把这件事在坐标上展开了。所谓不好找，通常是因为你在脑中试图直接猜 $u$；而严格构造时，只要路径无关，就可以固定一条简单路径来算。


---

## 恰当微分有什么用

### 1. 恰当微分的意思

如果一个微分式

$$
P(x,y)\,dx+Q(x,y)\,dy
$$

可以写成某个函数 $u(x,y)$ 的全微分

$$
du=u_x\,dx+u_y\,dy,
$$

也就是

$$
P=u_x,\qquad Q=u_y,
$$

那么称

$$
P\,dx+Q\,dy
$$

是恰当微分，或者说这个一形式是恰当的。

换句话说，恰当微分就是某个势函数的微分：

$$
\boxed{P\,dx+Q\,dy=du.}
$$

### 2. 最直接的用处：把线积分变成端点差

如果

$$
P\,dx+Q\,dy=du,
$$

那么沿曲线 $C$ 从 $A$ 到 $B$ 的线积分为

$$
\int_C P\,dx+Q\,dy
=
\int_C du
=u(B)-u(A).
$$

所以恰当微分最大的用处是：

$$
\boxed{
\text{线积分只与端点有关，与路径无关。}
}
$$

这就是一元微积分中

$$
\int_a^b f'(x)\,dx=f(b)-f(a)
$$

的多维推广。

### 3. 和无旋场、势函数的关系

令

$$
\mathbf F=(P,Q).
$$

则

$$
P\,dx+Q\,dy=\mathbf F\cdot d\mathbf r.
$$

如果它是恰当微分，则存在势函数 $u$，使得

$$
\mathbf F=\nabla u.
$$

此时

$$
Q_x-P_y=u_{yx}-u_{xy}=0.
$$

所以恰当微分一定满足无旋条件：

$$
\boxed{Q_x=P_y.}
$$

反过来，如果区域单连通且 $P,Q$ 有连续一阶偏导，那么

$$
Q_x=P_y
\Longrightarrow
P\,dx+Q\,dy\text{ 是恰当微分。}
$$

因此在单连通区域中：

$$
\boxed{
\text{无旋} \Longleftrightarrow \text{路径无关} \Longleftrightarrow \text{存在势函数} \Longleftrightarrow \text{恰当微分。}
}
$$

### 4. 解微分方程的用处

一阶微分方程常写成

$$
M(x,y)\,dx+N(x,y)\,dy=0.
$$

如果左边是恰当微分，即

$$
M\,dx+N\,dy=du,
$$

那么方程变成

$$
du=0.
$$

所以解就是

$$
\boxed{u(x,y)=C.}
$$

这就是“恰当方程”的核心。

例如

$$
(2xy+y^2)\,dx+(x^2+2xy)\,dy=0.
$$

这里

$$
M=2xy+y^2,\qquad N=x^2+2xy.
$$

检查：

$$
M_y=2x+2y,
\qquad
N_x=2x+2y.
$$

所以是恰当的。找 $u$：

$$
u_x=2xy+y^2.$$

对 $x$ 积分：

$$
u=x^2y+xy^2+C(y).$$

再对 $y$ 求导：

$$
u_y=x^2+2xy+C'(y).$$

与

$$
N=x^2+2xy
$$

比较，得到

$$
C'(y)=0.
$$

所以

$$
u=x^2y+xy^2+C.$$

原方程解为

$$
\boxed{x^2y+xy^2=C.}
$$

### 5. 为什么它重要

恰当微分把下面几件事统一起来：

$$
\boxed{
\text{全微分} \leftrightarrow \text{势函数} \leftrightarrow \text{保守场} \leftrightarrow \text{路径无关} \leftrightarrow \text{恰当方程。}
}
$$

所以它的作用不是只为了检验一个式子，而是判断一个积分或微分方程能不能降维：

- 线积分从“沿整条曲线算”降为“端点代入”；
- 微分方程从 $Mdx+Ndy=0$ 降为 $u=C$；
- 向量场从研究 $\\mathbf F$ 降为研究一个标量势函数 $u$。


---

## Stokes 公式的证明思路

这里的 Stokes 公式指三维向量分析中的经典 Stokes 定理：

$$
\boxed{
\iint_S (\nabla\times \mathbf F)\cdot \mathbf n\,dS
=
\oint_{\partial S} \mathbf F\cdot d\mathbf r
}
$$

其中：

- $S$ 是一片有向光滑曲面；
- $\partial S$ 是它的边界曲线；
- $\mathbf n$ 是曲面的单位法向量；
- 边界方向由右手定则决定：右手拇指指向 $\mathbf n$，四指弯曲方向就是 $\partial S$ 的正方向。

直观意思是：

$$
\boxed{
\text{曲面内部的旋度通量之和}
=
\text{边界上的环流。}
}
$$

也就是说，曲面里面每个小块的“局部旋转”，累加起来以后，内部相邻边界会互相抵消，只剩下最外层边界的环流。

---

### 1. 先从一个参数曲面开始

设曲面 $S$ 由参数方程给出：

$$
\mathbf r(u,v)=\bigl(x(u,v),y(u,v),z(u,v)\bigr),
\qquad (u,v)\in D.
$$

曲面的有向面积元为

$$
\mathbf n\,dS=\mathbf r_u\times \mathbf r_v\,du\,dv.
$$

所以 Stokes 左边可以写成

$$
\iint_S (\nabla\times \mathbf F)\cdot \mathbf n\,dS
=
\iint_D (\nabla\times \mathbf F)(\mathbf r(u,v))
\cdot (\mathbf r_u\times \mathbf r_v)\,du\,dv.
$$

边界曲线 $\partial S$ 来自参数区域 $D$ 的边界 $\partial D$。沿边界有

$$
d\mathbf r=\mathbf r_u\,du+\mathbf r_v\,dv.
$$

因此右边为

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=
\oint_{\partial D}\mathbf F(\mathbf r(u,v))\cdot
(\mathbf r_u\,du+\mathbf r_v\,dv).
$$

令

$$
P(u,v)=\mathbf F(\mathbf r(u,v))\cdot \mathbf r_u,
\qquad
Q(u,v)=\mathbf F(\mathbf r(u,v))\cdot \mathbf r_v.
$$

于是边界积分变成平面上的线积分：

$$
\oint_{\partial D} P\,du+Q\,dv.
$$

---

### 2. 对参数区域使用 Green 公式

Green 公式告诉我们：

$$
\oint_{\partial D} P\,du+Q\,dv
=
\iint_D\left(\frac{\partial Q}{\partial u}
-\frac{\partial P}{\partial v}\right)du\,dv.
$$

下面只要证明

$$
\boxed{
\frac{\partial Q}{\partial u}-\frac{\partial P}{\partial v}
=(\nabla\times \mathbf F)(\mathbf r(u,v))\cdot
(\mathbf r_u\times \mathbf r_v)
}
$$

就得到 Stokes 公式。

---

### 3. 关键恒等式

记

$$
\mathbf F=(M,N,L).
$$

则

$$
P=\mathbf F(\mathbf r)\cdot \mathbf r_u,
\qquad
Q=\mathbf F(\mathbf r)\cdot \mathbf r_v.
$$

对 $Q$ 求 $u$ 偏导：

$$
Q_u=\frac{\partial}{\partial u}\bigl(\mathbf F(\mathbf r)\cdot \mathbf r_v\bigr)
=\bigl(D\mathbf F(\mathbf r)\,\mathbf r_u\bigr)\cdot \mathbf r_v
+\mathbf F(\mathbf r)\cdot \mathbf r_{vu}.
$$

对 $P$ 求 $v$ 偏导：

$$
P_v=\frac{\partial}{\partial v}\bigl(\mathbf F(\mathbf r)\cdot \mathbf r_u\bigr)
=\bigl(D\mathbf F(\mathbf r)\,\mathbf r_v\bigr)\cdot \mathbf r_u
+\mathbf F(\mathbf r)\cdot \mathbf r_{uv}.
$$

因为混合偏导相等，

$$
\mathbf r_{uv}=\mathbf r_{vu},
$$

所以相减时第二类项抵消：

$$
Q_u-P_v
=\bigl(D\mathbf F(\mathbf r)\,\mathbf r_u\bigr)\cdot \mathbf r_v
-\bigl(D\mathbf F(\mathbf r)\,\mathbf r_v\bigr)\cdot \mathbf r_u.
$$

这个量正好等于旋度和法向面积元的点积：

$$
Q_u-P_v
=(\nabla\times \mathbf F)(\mathbf r)\cdot(\mathbf r_u\times\mathbf r_v).
$$

因此

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\oint_{\partial D}P\,du+Q\,dv
$$

$$
=\iint_D(Q_u-P_v)\,du\,dv
$$

$$
=\iint_D(\nabla\times\mathbf F)(\mathbf r)\cdot
(\mathbf r_u\times\mathbf r_v)\,du\,dv
$$

$$
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

所以

$$
\boxed{
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=
\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
}
$$

这就是 Stokes 公式。

---

### 4. 为什么内部边界会抵消

上面的证明针对一张可以由单个参数区域描述的曲面。如果曲面比较复杂，可以把它切成许多小曲面：

$$
S=S_1\cup S_2\cup\cdots\cup S_m.
$$

对每一小块使用 Stokes 公式：

$$
\iint_{S_i}(\nabla\times\mathbf F)\cdot\mathbf n\,dS
=
\oint_{\partial S_i}\mathbf F\cdot d\mathbf r.
$$

把所有小块加起来：

$$
\sum_i\iint_{S_i}(\nabla\times\mathbf F)\cdot\mathbf n\,dS
=
\sum_i\oint_{\partial S_i}\mathbf F\cdot d\mathbf r.
$$

左边合成整个曲面的面积分：

$$
\sum_i\iint_{S_i}(\nabla\times\mathbf F)\cdot\mathbf n\,dS
=
\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

右边中，两个相邻小曲面共享的内部边界会被走两遍，而且方向相反：

$$
\int_C \mathbf F\cdot d\mathbf r+
\int_{-C}\mathbf F\cdot d\mathbf r=0.
$$

所以内部边界全部抵消，只剩下外边界 $\partial S$：

$$
\sum_i\oint_{\partial S_i}\mathbf F\cdot d\mathbf r
=\oint_{\partial S}\mathbf F\cdot d\mathbf r.
$$

因此整体仍然有

$$
\boxed{
\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS
=
\oint_{\partial S}\mathbf F\cdot d\mathbf r.
}
$$

---

### 5. 一句话总结

Stokes 公式的本质是：

$$
\boxed{
\text{局部旋转的面积累加}
=\text{整体边界的切向环流。}
}
$$

证明的核心有两步：

1. 用参数化把曲面积分转成参数平面上的二重积分；
2. 在参数平面上使用 Green 公式，内部边界相互抵消，只剩外边界。

所以 Stokes 公式可以看成 Green 公式在空间曲面上的推广。
