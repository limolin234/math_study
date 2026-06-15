# 作业 12.4：曲线积分

本文由 `tmp.md` 中 12.4 节作业解答、椭圆线密度积分补充整理而成。

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

---

# 12.4 相关补充

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
