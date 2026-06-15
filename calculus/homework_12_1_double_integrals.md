# tmp 黑板

## 当前主题：作业 12.1（二重积分）

本文件已清理：仅保留这次作业 12.1 相关内容。

## 微积分：二重积分入门与作业 12.1 题型总览

### 0. 作业 12.1 主题

作业 12.1 主要是二重积分：

1. 根据二重积分性质比较大小。
2. 判断二重积分的性质能否直接推出符号。
3. 计算矩形区域上的二重积分。
4. 交换二次积分的积分次序。
5. 计算一般区域上的二重积分。
6. 求平面区域面积。
7. 证明一个交换积分次序的恒等式。
8. 用二重积分性质证明 Cauchy-Schwarz 型不等式。
9. 求两个曲面围成的立体体积。
10. 证明一个圆形区域上的积分恒等式。

这一节的核心不是新函数，而是：

\[
\boxed{\text{看清积分区域 }D\text{，选择合适的积分次序或坐标。}}
\]

---

## 1. 二重积分的基本性质

### 1.1 线性性质

若 \(f,g\) 在 \(D\) 上可积，则：

\[
\iint_D(af+bg)\,d\sigma
=
a\iint_Df\,d\sigma+b\iint_Dg\,d\sigma.
\]

这里 \(d\sigma\) 在平面直角坐标中就是：

\[
d\sigma=dxdy.
\]

---

### 1.2 保号性

如果在区域 \(D\) 上：

\[
f(x,y)\le g(x,y),
\]

则：

\[
\iint_Df(x,y)\,d\sigma
\le
\iint_Dg(x,y)\,d\sigma.
\]

特别地，如果：

\[
f(x,y)\ge0,
\]

则：

\[
\iint_Df(x,y)\,d\sigma\ge0.
\]

---

### 1.3 估值性质

如果在 \(D\) 上：

\[
m\le f(x,y)
\le M,
\]

且 \(D\) 的面积为 \(S_D\)，则：

\[
mS_D\le\iint_Df(x,y)\,d\sigma\le MS_D.
\]

---

### 1.4 区域可加性

如果区域 \(D\) 被分成两个无重叠内部的区域：

\[
D=D_1\cup D_2,
\]

则：

\[
\iint_Df\,d\sigma
=
\iint_{D_1}f\,d\sigma+
\iint_{D_2}f\,d\sigma.
\]

---

## 2. 作业第 1 题：根据性质比较二重积分大小

### 2.1 比较 \((x+y)^2\) 和 \((x+y)^3\)

题目区域：

\[
D=\{(x,y):x\ge0,y\ge0,x+y\le1\}.
\]

在这个区域内：

\[
0\le x+y\le1.
\]

令：

\[
t=x+y.
\]

当 \(0\le t\le1\) 时：

\[
t^3\le t^2.
\]

所以：

\[
(x+y)^3\le (x+y)^2.
\]

因此：

\[
\boxed{
\iint_D(x+y)^3\,dxdy
\le
\iint_D(x+y)^2\,dxdy.
}
\]

如果问谁大，则 \((x+y)^2\) 的二重积分更大。

---

### 2.2 比较 \(\ln(x+y)\) 和 \([\ln(x+y)]^2\)

题目区域是矩形：

\[
D=[2,5]\times[0,1].
\]

于是：

\[
2\le x+y\le6.
\]

令：

\[
s=x+y.
\]

需要比较：

\[
\ln s
\quad\text{和}\quad
(\ln s)^2.
\]

二者大小取决于 \(\ln s\) 是否大于 1。

因为：

\[
(\ln s)^2-\ln s=\ln s(\ln s-1).
\]

当：

\[
1<s<e,
\]

有：

\[
0<\ln s<1,
\]

所以：

\[
(\ln s)^2<\ln s.
\]

当：

\[
s>e,
\]

有：

\[
(\ln s)^2>\ln s.
\]

而本题中 \(s=x+y\) 的范围是：

\[
2\le s\le6.
\]

这个范围跨过了 \(e\)。

所以不能只靠逐点大小在整个区域上直接比较。

如果需要精确判断，要计算：

\[
\iint_D\left[(\ln(x+y))^2-\ln(x+y)\right]dxdy.
\]

粗略数值上它为正，因此：

\[
\iint_D[\ln(x+y)]^2dxdy
>
\iint_D\ln(x+y)dxdy.
\]

但做“性质比较”题时，重点是看函数是否在整个区域上保持同一大小关系。

---

## 3. 作业第 2 题：判断二重积分符号

题目问：不用直接计算，能否根据性质判断下列二重积分为正、负或零。

### 3.1 \(\iint_Dxy(x+y)\,dxdy\)，\(D=[0,1]\times[0,1]\)

在区域中：

\[
x\ge0,
\quad y\ge0,
\quad x+y\ge0.
\]

因此：

\[
xy(x+y)\ge0.
\]

并且除了边界外，大部分点上都大于 0。

所以：

\[
\boxed{
\iint_Dxy(x+y)\,dxdy>0.
}
\]

---

### 3.2 \(\iint_D\frac{dxdy}{100+\cos^2x+\cos^2y}\)，\(|x|+|y|\le10\)

分母满足：

\[
100+\cos^2x+\cos^2y>0.
\]

所以被积函数：

\[
\frac1{100+\cos^2x+\cos^2y}>0.
\]

区域面积也大于 0。

因此：

\[
\boxed{
\iint_D\frac{dxdy}{100+\cos^2x+\cos^2y}>0.
}
\]

---

## 4. 作业第 3 题：矩形区域二重积分

### 4.1 计算 \(\iint_D(x^3+2x^2y+y^3)dxdy\)，\(D=[0,1]\times[0,1]\)

矩形区域上可以直接拆开：

\[
I=\int_0^1\int_0^1(x^3+2x^2y+y^3)\,dy\,dx.
\]

分别计算：

\[
\iint_Dx^3\,dxdy
=
\int_0^1x^3dx\int_0^1dy
=\frac14.
\]

\[
\iint_D2x^2y\,dxdy
=2\int_0^1x^2dx\int_0^1y\,dy
=2\cdot\frac13\cdot\frac12
=\frac13.
\]

\[
\iint_Dy^3\,dxdy
=
\int_0^1dx\int_0^1y^3dy
=\frac14.
\]

所以：

\[
\boxed{
I=\frac14+\frac13+\frac14=\frac56.
}
\]

---

### 4.2 计算 \(\iint_Dxy e^{x^2+y^2}dxdy\)，\(D=[a,b]\times[c,d]\)

被积函数可分离：

\[
xy e^{x^2+y^2}
=xe^{x^2}\cdot ye^{y^2}.
\]

所以：

\[
I=
\left(\int_a^bxe^{x^2}dx\right)
\left(\int_c^dye^{y^2}dy\right).
\]

又：

\[
\int xe^{x^2}dx=\frac12e^{x^2}.
\]

因此：

\[
\int_a^bxe^{x^2}dx
=\frac12(e^{b^2}-e^{a^2}),
\]

\[
\int_c^dye^{y^2}dy
=\frac12(e^{d^2}-e^{c^2}).
\]

所以：

\[
\boxed{
I=\frac14(e^{b^2}-e^{a^2})(e^{d^2}-e^{c^2}).
}
\]

---

## 5. 作业第 4 题：交换积分次序

### 5.1 第一题

原积分：

\[
\int_0^{2a}dx\int_{\sqrt{2ax-x^2}}^{\sqrt{2ax}}f(x,y)dy,
\quad a>0.
\]

区域为：

\[
0\le x\le2a,
\quad
\sqrt{2ax-x^2}\le y\le\sqrt{2ax}.
\]

平方后看边界：

\[
y^2=2ax-x^2
\quad\Longleftrightarrow\quad
(x-a)^2+y^2=a^2,
\]

这是圆心 \((a,0)\)、半径 \(a\) 的上半圆。

另一条边界是：

\[
y^2=2ax
\quad\Longleftrightarrow\quad
x=\frac{y^2}{2a}.
\]

交换次序时，先确定 \(y\) 的范围。

因为最大 \(y\) 来自 \(y^2=2ax\) 且 \(x=2a\)，所以：

\[
0\le y\le2a.
\]

对固定 \(y\)，由：

\[
y\le\sqrt{2ax}
\]

得到：

\[
x\ge\frac{y^2}{2a}.
\]

由：

\[
y\ge\sqrt{2ax-x^2}
\]

得到：

\[
y^2\ge2ax-x^2,
\]

即：

\[
(x-a)^2+y^2\ge a^2.
\]

在 \(0\le x\le2a\) 中，这表示在圆外。

于是右边界需要分段：

当 \(0\le y\le a\) 时，圆外给出：

\[
x\le a-\sqrt{a^2-y^2}
\quad\text{或}\quad
x\ge a+\sqrt{a^2-y^2}.
\]

再结合 \(x\ge y^2/(2a)\)，区域分成两块：

\[
\frac{y^2}{2a}\le x\le a-\sqrt{a^2-y^2},
\]

和：

\[
a+\sqrt{a^2-y^2}\le x\le2a.
\]

当 \(a\le y\le2a\) 时，圆外条件自动成立，只剩：

\[
\frac{y^2}{2a}\le x\le2a.
\]

所以交换后：

\[
\boxed{
\begin{aligned}
I=&\int_0^a dy\int_{y^2/(2a)}^{a-\sqrt{a^2-y^2}}f(x,y)dx\\
&+\int_0^a dy\int_{a+\sqrt{a^2-y^2}}^{2a}f(x,y)dx\\
&+\int_a^{2a}dy\int_{y^2/(2a)}^{2a}f(x,y)dx.
\end{aligned}
}
\]

这一题画图最重要。

---

### 5.2 第二题

原积分：

\[
\int_0^2dx\int_0^{\sqrt{x(2-x)}}f(x,y)dy.
\]

区域为：

\[
0\le x\le2,
\quad
0\le y\le\sqrt{x(2-x)}.
\]

边界：

\[
y^2=x(2-x)=2x-x^2.
\]

即：

\[
(x-1)^2+y^2=1.
\]

这是圆心 \((1,0)\)、半径 \(1\) 的上半圆。

所以：

\[
0\le y\le1.
\]

固定 \(y\) 时：

\[
(x-1)^2\le1-y^2.
\]

因此：

\[
1-\sqrt{1-y^2}\le x\le1+\sqrt{1-y^2}.
\]

交换后：

\[
\boxed{
I=\int_0^1dy\int_{1-\sqrt{1-y^2}}^{1+\sqrt{1-y^2}}f(x,y)dx.
}
\]

---

## 6. 作业第 5 题：一般区域二重积分的计算思路

这组题重点是先画出区域，再选择直角坐标或极坐标。

常用判断：

- 出现 \(x^2+y^2\)，优先考虑极坐标。
- 区域由圆、扇形、圆环给出，优先考虑极坐标。
- 区域由直线夹出，优先考虑直角坐标或换积分次序。
- 被积函数含 \(x+y\)，且区域由 \(x+y=\text{常数}\) 控制，可以考虑变量代换。

极坐标公式：

\[
x=r\cos\theta,
\quad
 y=r\sin\theta,
\]

\[
dxdy=r\,drd\theta.
\]

---

### 6.1 抛物线与直线围成区域

题型：

\[
\iint_Dxy^2\,dxdy,
\]

其中 \(D\) 由抛物线：

\[
y^2=2px
\]

和直线：

\[
x=\frac p2
\]

围成，\(p>0\)。

交点由：

\[
y^2=2p\cdot\frac p2=p^2,
\]

所以：

\[
y=\pm p.
\]

区域可写为：

\[
-p\le y\le p,
\quad
\frac{y^2}{2p}\le x\le\frac p2.
\]

所以：

\[
I=\int_{-p}^p\int_{y^2/(2p)}^{p/2}xy^2\,dxdy.
\]

内层积分：

\[
\int xy^2dx=\frac12x^2y^2.
\]

代入：

\[
I=\int_{-p}^p\frac{y^2}{2}
\left[\left(\frac p2\right)^2-\left(\frac{y^2}{2p}\right)^2\right]dy.
\]

即：

\[
I=\int_{-p}^p\left(\frac{p^2y^2}{8}-\frac{y^6}{8p^2}\right)dy.
\]

因为 integrand 是偶函数：

\[
I=2\int_0^p\left(\frac{p^2y^2}{8}-\frac{y^6}{8p^2}\right)dy.
\]

计算得：

\[
I=\frac{p^5}{12}-\frac{p^5}{28}
=\frac{p^5}{21}.
\]

所以：

\[
\boxed{I=\frac{p^5}{21}.}
\]

---

### 6.2 半圆与坐标轴围成区域

题型：

\[
\iint_D\frac{dxdy}{\sqrt{2a-x}},
\quad a>0.
\]

区域 \(D\) 由圆心 \((a,0)\)、半径 \(a\) 的上半圆和坐标轴围成。

圆方程是：

\[
(x-a)^2+y^2=a^2.
\]

也就是：

\[
x^2+y^2=2ax.
\]

区域在第一象限，可写成：

\[
0\le x\le2a,
\quad
0\le y\le\sqrt{2ax-x^2}.
\]

所以：

\[
I=\int_0^{2a}\int_0^{\sqrt{2ax-x^2}}\frac{1}{\sqrt{2a-x}}\,dydx.
\]

先对 \(y\) 积分：

\[
I=\int_0^{2a}\frac{\sqrt{2ax-x^2}}{\sqrt{2a-x}}dx.
\]

因为：

\[
2ax-x^2=x(2a-x),
\]

所以：

\[
\frac{\sqrt{2ax-x^2}}{\sqrt{2a-x}}
=\sqrt{x}.
\]

因此：

\[
I=\int_0^{2a}\sqrt{x}\,dx
=\frac23(2a)^{3/2}.
\]

所以：

\[
\boxed{I=\frac23(2a)^{3/2}.}
\]

---

## 7. 作业第 6 题：求平面区域面积

题目：求由四张平面：

\[
x=0,
\quad y=0,
\quad x=1,
\quad y=1
\]

围成的区域投影到平面：

\[
z=0
\]

和：

\[
x+3y+2z=6
\]

之间的立体的体积。

如果理解为在柱体：

\[
0\le x\le1,
\quad 0\le y\le1
\]

上方，下底面为：

\[
z=0,
\]

上顶面为：

\[
z=\frac{6-x-3y}{2},
\]

则体积为：

\[
V=\int_0^1\int_0^1\frac{6-x-3y}{2}\,dydx.
\]

计算：

\[
V=\frac12\int_0^1\int_0^1(6-x-3y)dydx.
\]

内层：

\[
\int_0^1(6-x-3y)dy
=6-x-\frac32.
\]

所以：

\[
V=\frac12\int_0^1\left(\frac92-x\right)dx
=\frac12\left(\frac92-\frac12\right)=2.
\]

因此：

\[
\boxed{V=2.}
\]

---

## 8. 作业第 7 题：交换积分次序证明恒等式

题目：设 \(f(x)\) 在 \([0,1]\) 上连续，证明：

\[
\int_0^1dy\int_y^{\sqrt y}e^{x^3}f(x)dx
=
\int_0^1(e^x-e^{x^6})f(x)dx.
\]

先看积分区域：

\[
0\le y\le1,
\quad
 y\le x\le\sqrt y.
\]

条件 \(x\le\sqrt y\) 等价于：

\[
x^2\le y.
\]

条件 \(y\le x\) 等价于：

\[
y\le x.
\]

因此区域是：

\[
0\le x\le1,
\quad
x^2\le y\le x.
\]

交换次序：

\[
\int_0^1dy\int_y^{\sqrt y}e^{x^3}f(x)dx
=
\int_0^1dx\int_{x^2}^{x}e^{x^3}f(x)dy.
\]

因为内层对 \(y\) 积分，被积函数与 \(y\) 无关：

\[
=\int_0^1(x-x^2)e^{x^3}f(x)dx.
\]

注意：如果题目右侧写的是

\[
\int_0^1(e^x-e^{x^2})f(x)dx
\]

或

\[
\int_0^1(e^x-e^{x^6})f(x)dx,
\]

那原式中的被积函数可能应为对应的导数形式，例如：

\[
3x^2e^{x^3}f(x)
\]

或上下限可能有抄写差异。

按当前图片识别到的原式：

\[
\boxed{
\int_0^1dy\int_y^{\sqrt y}e^{x^3}f(x)dx
=
\int_0^1(x-x^2)e^{x^3}f(x)dx.
}
\]

这一题核心是交换积分次序。

---

## 9. 作业第 8 题：二重积分性质证明不等式

证明：若 \(f(x)\) 在 \([a,b]\) 上连续，则：

\[
\left[\int_a^bf(x)dx\right]^2
\le
(b-a)\int_a^b[f(x)]^2dx.
\]

这是积分形式的 Cauchy-Schwarz 不等式。

用二重积分证明：

因为平方恒非负：

\[
(f(x)-f(y))^2\ge0.
\]

所以：

\[
\int_a^b\int_a^b(f(x)-f(y))^2dxdy\ge0.
\]

展开：

\[
\int_a^b\int_a^b(f(x)^2-2f(x)f(y)+f(y)^2)dxdy\ge0.
\]

分别计算：

\[
\int_a^b\int_a^bf(x)^2dxdy
=(b-a)\int_a^bf(x)^2dx.
\]

同理：

\[
\int_a^b\int_a^bf(y)^2dxdy
=(b-a)\int_a^bf(y)^2dy.
\]

中间项：

\[
\int_a^b\int_a^bf(x)f(y)dxdy
=\left(\int_a^bf(x)dx\right)^2.
\]

因此：

\[
2(b-a)\int_a^bf(x)^2dx
-2\left(\int_a^bf(x)dx\right)^2
\ge0.
\]

两边除以 2：

\[
(b-a)\int_a^bf(x)^2dx
\ge
\left(\int_a^bf(x)dx\right)^2.
\]

即：

\[
\boxed{
\left[\int_a^bf(x)dx\right]^2
\le
(b-a)\int_a^b[f(x)]^2dx.
}
\]

---

## 10. 作业第 9 题：两个曲面围成体积

题目：求抛物面：

\[
z=6-x^2-y^2
\]

与锥面：

\[
z=\sqrt{x^2+y^2}
\]

围成的立体体积。

用柱坐标：

\[
r=\sqrt{x^2+y^2}.
\]

两个曲面变为：

\[
z=6-r^2,
\quad
z=r.
\]

交线由：

\[
6-r^2=r.
\]

即：

\[
r^2+r-6=0.
\]

所以：

\[
r=2
\quad (r\ge0).
\]

上方曲面是：

\[
z=6-r^2,
\]

下方曲面是：

\[
z=r.
\]

体积：

\[
V=\int_0^{2\pi}\int_0^2[(6-r^2)-r]r\,drd\theta.
\]

计算：

\[
V=2\pi\int_0^2(6r-r^3-r^2)dr.
\]

\[
\int_0^2(6r-r^3-r^2)dr
=
\left[3r^2-\frac14r^4-\frac13r^3\right]_0^2.
\]

代入：

\[
=12-4-\frac83
=\frac{16}{3}.
\]

所以：

\[
\boxed{V=\frac{32\pi}{3}.}
\]

---

## 11. 作业第 10 题：圆形区域上的积分恒等式

题目：设 \(f(x)\) 在 \([-1,1]\) 上连续，证明：

\[
\iint_{x^2+y^2\le1}f(x+y)dxdy
=\int_{-1}^{1}f(u)\,du
\]

图片中右侧似乎写的是 \(\int_{-1}^1f(u)du\)。但若区域真是单位圆 \(x^2+y^2\le1\)，这个等式一般不成立。

因为令：

\[
u=x+y,
\quad v=x-y.
\]

则：

\[
x=\frac{u+v}{2},
\quad
 y=\frac{u-v}{2}.
\]

Jacobian 为：

\[
\left|\frac{\partial(x,y)}{\partial(u,v)}\right|=\frac12.
\]

单位圆变为：

\[
x^2+y^2\le1
\quad\Longleftrightarrow\quad
\frac{u^2+v^2}{2}\le1.
\]

即：

\[
u^2+v^2\le2.
\]

所以：

\[
-\sqrt2\le u\le\sqrt2,
\quad
-\sqrt{2-u^2}\le v\le\sqrt{2-u^2}.
\]

于是：

\[
\iint_{x^2+y^2\le1}f(x+y)dxdy
=
\frac12\int_{-\sqrt2}^{\sqrt2}f(u)
\int_{-\sqrt{2-u^2}}^{\sqrt{2-u^2}}dv\,du.
\]

因此：

\[
\boxed{
\iint_{x^2+y^2\le1}f(x+y)dxdy
=
\int_{-\sqrt2}^{\sqrt2}f(u)\sqrt{2-u^2}\,du.
}
\]

所以如果题目右侧是 \(\int_{-1}^1f(u)du\)，可能原区域不是单位圆，而是某个经过线性变换后截长恒为 1 的区域，或者图片中的题目条件需要再核对。

---

## 12. 本节最小记忆包

二重积分最核心：

\[
\boxed{\text{先画区域，再选次序。}}
\]

矩形区域：

\[
\iint_{[a,b]\times[c,d]}f(x)g(y)dxdy
=\left(\int_a^bf(x)dx\right)\left(\int_c^dg(y)dy\right).
\]

交换次序：

\[
\int_a^bdx\int_{\varphi_1(x)}^{\varphi_2(x)}f(x,y)dy
\]

要改写成：

\[
\int_c^ddy\int_{\psi_1(y)}^{\psi_2(y)}f(x,y)dx.
\]

极坐标：

\[
x=r\cos\theta,
\quad y=r\sin\theta,
\quad dxdy=rdrd\theta.
\]

体积：

\[
V=\iint_D(z_{\text{上}}-z_{\text{下}})dxdy.
\]

常见不等式：

\[
\left[\int_a^bf(x)dx\right]^2
\le
(b-a)\int_a^b[f(x)]^2dx.
\]

## 作业 12.1：第 5（2）题

题目：计算

\[
I=\iint_D \frac{dxdy}{\sqrt{2a-x}},\qquad a>0.
\]

其中 \(D\) 是圆心为 \((a,a)\)、半径为 \(a\) 的圆周与两坐标轴围成的区域。

注意：这里不是整个圆盘，而是第一象限中由两条坐标轴和圆弧围成的那块小区域。

圆的方程为

\[
(x-a)^2+(y-a)^2=a^2.
\]

取靠近原点的圆弧，有

\[
y=a-\sqrt{a^2-(x-a)^2}.
\]

因此区域 \(D\) 可以写成

\[
0\le x\le a,
\qquad
0\le y\le a-\sqrt{a^2-(x-a)^2}.
\]

因为被积函数只含 \(x\)，所以先对 \(y\) 积分：

\[
I=\int_0^a
\frac{a-\sqrt{a^2-(x-a)^2}}{\sqrt{2a-x}}\,dx.
\]

令

\[
u=2a-x,
\qquad dx=-du.
\]

当 \(x=0\) 时，\(u=2a\)；当 \(x=a\) 时，\(u=a\)。

又因为

\[
x-a=a-u,
\]

所以

\[
a^2-(x-a)^2
=a^2-(a-u)^2
=2au-u^2
=u(2a-u).
\]

于是

\[
I=\int_a^{2a}
\left(
\frac{a}{\sqrt u}-\sqrt{2a-u}
\right)du.
\]

分别计算：

\[
\int_a^{2a}\frac{a}{\sqrt u}\,du
=2a\sqrt u\Big|_a^{2a}
=2a(\sqrt{2a}-\sqrt a)
=2a^{3/2}(\sqrt2-1).
\]

以及

\[
\int_a^{2a}\sqrt{2a-u}\,du
=\int_0^a \sqrt v\,dv
=\frac{2}{3}a^{3/2}.
\]

所以

\[
I=2a^{3/2}(\sqrt2-1)-\frac{2}{3}a^{3/2}.
\]

整理得

\[
I=\left(2\sqrt2-\frac{8}{3}\right)a^{3/2}.
\]

答案：

\[
\boxed{I=\left(2\sqrt2-\frac{8}{3}\right)a^{3/2}}
\]

## 作业 12.1：第 5 大题（3）--（10）

### （3）

题目：

\[
I=\iint_D y\left[1+x e^{-\frac12(x^2+y^2)}\right]dxdy,
\]

其中 \(D\) 由直线 \(y=x\)、\(y=-1\)、\(x=1\) 围成。

区域顶点为

\[
(-1,-1),\quad (1,-1),\quad (1,1).
\]

取竖切：

\[
-1\le x\le 1,
\qquad
-1\le y\le x.
\]

所以

\[
I=\int_{-1}^{1}\int_{-1}^{x}
 y\left[1+x e^{-\frac12(x^2+y^2)}\right]dy dx.
\]

分成两部分：

\[
I=I_1+I_2.
\]

其中

\[
I_1=\int_{-1}^{1}\int_{-1}^{x}y\,dy dx
=\int_{-1}^{1}\frac{x^2-1}{2}\,dx
=-\frac23.
\]

又

\[
I_2=\int_{-1}^{1}x e^{-\frac12x^2}
\left(\int_{-1}^{x}y e^{-\frac12y^2}dy\right)dx.
\]

因为

\[
\int y e^{-\frac12y^2}dy=-e^{-\frac12y^2},
\]

所以

\[
\int_{-1}^{x}y e^{-\frac12y^2}dy
=e^{-\frac12}-e^{-\frac12x^2}.
\]

于是

\[
I_2=\int_{-1}^{1}x e^{-\frac12x^2}
\left(e^{-\frac12}-e^{-\frac12x^2}\right)dx.
\]

被积函数是奇函数，积分区间关于原点对称，因此

\[
I_2=0.
\]

所以

\[
\boxed{I=-\frac23}.
\]

---

### （4）

题目：

\[
I=\iint_D x^2y\,dxdy,
\]

其中

\[
D=\{(x,y)\mid x^2+y^2\ge 2x,
\ 0\le x\le 2,
\ 0\le y\le x\}.
\]

用极坐标：

\[
x=r\cos\theta,
\qquad
 y=r\sin\theta.
\]

条件 \(0\le y\le x\) 给出

\[
0\le \theta\le \frac\pi4.
\]

条件 \(x^2+y^2\ge 2x\) 变成

\[
r^2\ge 2r\cos\theta,
\]

即

\[
r\ge 2\cos\theta.
\]

又由 \(0\le x\le 2\)，得

\[
r\cos\theta\le 2,
\qquad
r\le 2\sec\theta.
\]

所以

\[
0\le \theta\le \frac\pi4,
\qquad
2\cos\theta\le r\le 2\sec\theta.
\]

被积函数与面积元：

\[
x^2y\,dxdy
=r^2\cos^2\theta\cdot r\sin\theta\cdot r\,drd\theta
=r^4\cos^2\theta\sin\theta\,drd\theta.
\]

于是

\[
I=\int_0^{\pi/4}\int_{2\cos\theta}^{2\sec\theta}
 r^4\cos^2\theta\sin\theta\,drd\theta.
\]

先对 \(r\) 积分：

\[
I=\frac{32}{5}\int_0^{\pi/4}
\left(\sec^3\theta-\cos^7\theta\right)\sin\theta\,d\theta.
\]

其中

\[
\int_0^{\pi/4}\sin\theta\sec^3\theta\,d\theta=\frac12,
\]

\[
\int_0^{\pi/4}\sin\theta\cos^7\theta\,d\theta=\frac{15}{128}.
\]

所以

\[
I=\frac{32}{5}\left(\frac12-\frac{15}{128}\right)
=\frac{49}{20}.
\]

答案：

\[
\boxed{I=\frac{49}{20}}.
\]

---

### （5）

题目：

\[
I=\iint_D (x+y)\,dxdy,
\]

其中 \(D\) 是由圆周

\[
x^2+y^2=x+y
\]

所围成的区域。

配方：

\[
x^2-x+y^2-y=0,
\]

\[
\left(x-\frac12\right)^2+
\left(y-\frac12\right)^2
=\frac12.
\]

所以 \(D\) 是圆心为

\[
\left(\frac12,\frac12\right)
\]

半径为

\[
\frac1{\sqrt2}
\]

的圆盘。

因为区域关于圆心对称，\(x+y\) 在圆盘上的平均值等于圆心处的值：

\[
\overline{x+y}=\frac12+\frac12=1.
\]

圆盘面积为

\[
S=\pi\left(\frac1{\sqrt2}\right)^2=\frac\pi2.
\]

所以

\[
I=1\cdot \frac\pi2=\frac\pi2.
\]

答案：

\[
\boxed{I=\frac\pi2}.
\]

---

### （6）

题目：

\[
I=\iint_D
\frac{\sqrt{1-x^2-y^2}}{\sqrt{1+x^2+y^2}}\,dxdy,
\]

其中 \(D\) 是圆周 \(x^2+y^2=1\) 及坐标轴所围的第一象限区域。

这里取第一象限四分之一圆盘：

\[
0\le r\le 1,
\qquad
0\le \theta\le \frac\pi2.
\]

用极坐标：

\[
I=\int_0^{\pi/2}\int_0^1
\frac{\sqrt{1-r^2}}{\sqrt{1+r^2}}r\,drd\theta.
\]

先积掉 \(\theta\)：

\[
I=\frac\pi2\int_0^1
\frac{r\sqrt{1-r^2}}{\sqrt{1+r^2}}\,dr.
\]

令

\[
t=r^2,
\qquad r\,dr=\frac12dt.
\]

则

\[
I=\frac\pi4\int_0^1
\sqrt{\frac{1-t}{1+t}}\,dt.
\]

计算

\[
\int_0^1\sqrt{\frac{1-t}{1+t}}\,dt.
\]

令

\[
1-t=2\sin^2\varphi.
\]

可得该积分为

\[
\frac\pi2-1.
\]

因此

\[
I=\frac\pi4\left(\frac\pi2-1\right).
\]

答案：

\[
\boxed{I=\frac{\pi^2}{8}-\frac\pi4}.
\]

> 注：如果题目中的区域指上半圆盘而不是第一象限，则结果应乘以 2，即 \(\frac{\pi^2}{4}-\frac\pi2\)。

---

### （7）

题目：

\[
I=\iint_D (\sqrt x+\sqrt y)\,dxdy,
\]

其中 \(D\) 由坐标轴及曲线

\[
\sqrt x+\sqrt y=1
\]

围成。

令

\[
u=\sqrt x,
\qquad
v=\sqrt y.
\]

则

\[
x=u^2,
\qquad
 y=v^2.
\]

区域变成

\[
u\ge 0,
\qquad
v\ge 0,
\qquad
u+v\le 1.
\]

Jacobian 为

\[
\frac{\partial(x,y)}{\partial(u,v)}=4uv.
\]

所以

\[
I=\iint_{u+v\le 1}(u+v)4uv\,dudv.
\]

即

\[
I=4\int_0^1\int_0^{1-u}(u^2v+uv^2)dvdu.
\]

由对称性：

\[
I=8\int_0^1\int_0^{1-u}u^2v\,dvdu.
\]

计算：

\[
I=8\int_0^1 u^2\frac{(1-u)^2}{2}\,du
=4\int_0^1u^2(1-u)^2du.
\]

而

\[
\int_0^1u^2(1-u)^2du=\frac1{30}.
\]

所以

\[
I=\frac{4}{30}=\frac{2}{15}.
\]

答案：

\[
\boxed{I=\frac{2}{15}}.
\]

---

### （8）

题目：

\[
I=\iint_D y\,dxdy,
\]

其中 \(D\) 由直线

\[
x=-2,
\qquad
 y=0,
\qquad
 y=2,
\]

以及曲线

\[
x=-\sqrt{2y-y^2}
\]

围成。

固定 \(y\)：

\[
0\le y\le 2.
\]

横向看，\(x\) 从直线 \(x=-2\) 到曲线

\[
x=-\sqrt{2y-y^2}.
\]

所以

\[
I=\int_0^2\int_{-2}^{-\sqrt{2y-y^2}}y\,dxdy.
\]

先对 \(x\) 积分：

\[
I=\int_0^2y\left(2-\sqrt{2y-y^2}\right)dy.
\]

即

\[
I=\int_0^2 2y\,dy-
\int_0^2 y\sqrt{2y-y^2}\,dy.
\]

第一项：

\[
\int_0^2 2y\,dy=4.
\]

第二项中，令

\[
t=y-1.
\]

则

\[
2y-y^2=1-t^2.
\]

所以

\[
\int_0^2 y\sqrt{2y-y^2}\,dy
=\int_{-1}^{1}(t+1)\sqrt{1-t^2}\,dt.
\]

其中奇函数部分为 0，因此

\[
\int_{-1}^{1}(t+1)\sqrt{1-t^2}\,dt
=\int_{-1}^{1}\sqrt{1-t^2}\,dt
=\frac\pi2.
\]

所以

\[
I=4-\frac\pi2.
\]

答案：

\[
\boxed{I=4-\frac\pi2}.
\]

---

### （9）

题目：

\[
I=\iint_D e^{\frac{x-y}{x+y}}\,dxdy,
\]

其中 \(D\) 由直线

\[
x+y=2,
\qquad
x=0,
\qquad
 y=0
\]

围成。

令

\[
u=x+y,
\qquad
v=x-y.
\]

则

\[
x=\frac{u+v}{2},
\qquad
 y=\frac{u-v}{2}.
\]

Jacobian 为

\[
\left|\frac{\partial(x,y)}{\partial(u,v)}\right|=\frac12.
\]

原区域是第一象限三角形

\[
x\ge 0,
\qquad
 y\ge 0,
\qquad
x+y\le 2.
\]

变成

\[
0\le u\le 2,
\qquad
-u\le v\le u.
\]

所以

\[
I=\int_0^2\int_{-u}^{u}e^{v/u}\cdot \frac12\,dvdu.
\]

先对 \(v\) 积分。令 \(w=v/u\)，则 \(dv=u\,dw\)：

\[
\int_{-u}^{u}e^{v/u}\,dv
=u\int_{-1}^{1}e^w\,dw
=u(e-e^{-1}).
\]

因此

\[
I=\int_0^2\frac12 u(e-e^{-1})du.
\]

所以

\[
I=e-e^{-1}.
\]

答案：

\[
\boxed{I=e-e^{-1}}.
\]

---

### （10）

题目：

\[
I=\iint_D
\frac{\sqrt{x^2+y^2}}{\sqrt{4a^2-x^2-y^2}}\,dxdy,
\]

其中 \(D\) 由曲线

\[
y=\sqrt{a^2-x^2}-a,
\qquad a>0,
\]

和直线

\[
y=x
\]

围成。

曲线可化为

\[
x^2+(y+a)^2=a^2.
\]

这是圆心 \((0,-a)\)、半径 \(a\) 的圆的上半部分。

用极坐标：

\[
x=r\cos\theta,
\qquad
 y=r\sin\theta.
\]

圆变成

\[
r^2+2ar\sin\theta=0,
\]

即

\[
r=-2a\sin\theta.
\]

直线 \(y=x\) 在第三象限对应

\[
\theta=-\frac{3\pi}{4}.
\]

该区域对应

\[
-\pi\le \theta\le -\frac{3\pi}{4},
\qquad
0\le r\le -2a\sin\theta.
\]

被积函数与面积元为

\[
\frac{\sqrt{x^2+y^2}}{\sqrt{4a^2-x^2-y^2}}\,dxdy
=
\frac{r}{\sqrt{4a^2-r^2}}\cdot r\,drd\theta
=
\frac{r^2}{\sqrt{4a^2-r^2}}\,drd\theta.
\]

所以

\[
I=\int_{-\pi}^{-3\pi/4}\int_0^{-2a\sin\theta}
\frac{r^2}{\sqrt{4a^2-r^2}}\,drd\theta.
\]

令

\[
\alpha=\theta+\pi.
\]

则

\[
0\le \alpha\le \frac\pi4,
\qquad
-2a\sin\theta=2a\sin\alpha.
\]

于是

\[
I=\int_0^{\pi/4}\int_0^{2a\sin\alpha}
\frac{r^2}{\sqrt{4a^2-r^2}}\,drd\alpha.
\]

计算内层积分：

\[
\int_0^{2a\sin\alpha}\frac{r^2}{\sqrt{4a^2-r^2}}\,dr
=2a^2(\alpha-\sin\alpha\cos\alpha).
\]

所以

\[
I=2a^2\int_0^{\pi/4}
(\alpha-\sin\alpha\cos\alpha)d\alpha.
\]

因此

\[
I=2a^2\left(
\frac{\alpha^2}{2}-\frac{\sin^2\alpha}{2}
\right)_0^{\pi/4}.
\]

代入端点：

\[
I=a^2\left(\frac{\pi^2}{16}-\frac12\right).
\]

答案：

\[
\boxed{I=a^2\left(\frac{\pi^2}{16}-\frac12\right)}.
\]

## 作业 12.1：第 5（6）题中的代换说明

第（6）题中会出现积分

\[
J=\int_0^1 \sqrt{\frac{1-t}{1+t}}\,dt.
\]

这个积分的关键是处理

\[
\frac{1-t}{1+t}.
\]

看到 \(1-t\) 和 \(1+t\)，可以联想到三角恒等式：

\[
1-\cos 2\varphi=2\sin^2\varphi,
\]

\[
1+\cos 2\varphi=2\cos^2\varphi.
\]

所以令

\[
t=\cos 2\varphi.
\]

于是

\[
1-t=1-\cos 2\varphi=2\sin^2\varphi,
\]

\[
1+t=1+\cos 2\varphi=2\cos^2\varphi.
\]

因此

\[
\sqrt{\frac{1-t}{1+t}}
=\sqrt{\frac{2\sin^2\varphi}{2\cos^2\varphi}}
=\tan\varphi.
\]

再计算微分：

\[
t=\cos 2\varphi,
\]

所以

\[
dt=-2\sin 2\varphi\,d\varphi.
\]

又因为

\[
\sin 2\varphi=2\sin\varphi\cos\varphi,
\]

所以

\[
dt=-4\sin\varphi\cos\varphi\,d\varphi.
\]

接着换上下限。

当 \(t=0\) 时，

\[
\cos 2\varphi=0,
\]

所以

\[
2\varphi=\frac\pi2,
\qquad
\varphi=\frac\pi4.
\]

当 \(t=1\) 时，

\[
\cos 2\varphi=1,
\]

所以

\[
\varphi=0.
\]

于是

\[
J=\int_{\pi/4}^{0}
\tan\varphi\cdot
\left(-4\sin\varphi\cos\varphi\right)d\varphi.
\]

把负号用来交换上下限：

\[
J=\int_0^{\pi/4}
4\tan\varphi\sin\varphi\cos\varphi\,d\varphi.
\]

由于

\[
\tan\varphi=\frac{\sin\varphi}{\cos\varphi},
\]

所以

\[
\tan\varphi\sin\varphi\cos\varphi
=\sin^2\varphi.
\]

因此

\[
J=4\int_0^{\pi/4}\sin^2\varphi\,d\varphi.
\]

再用降幂公式：

\[
\sin^2\varphi=\frac{1-\cos 2\varphi}{2}.
\]

所以

\[
J=4\int_0^{\pi/4}\frac{1-\cos 2\varphi}{2}\,d\varphi.
\]

即

\[
J=2\int_0^{\pi/4}(1-\cos 2\varphi)\,d\varphi.
\]

计算得

\[
J=2\left(\varphi-\frac{\sin 2\varphi}{2}\right)_0^{\pi/4}.
\]

代入端点：

\[
J=2\left(\frac\pi4-\frac12\right)
=\frac\pi2-1.
\]

所以第（6）题中这一步代换的结果是

\[
\boxed{
\int_0^1 \sqrt{\frac{1-t}{1+t}}\,dt
=\frac\pi2-1
}.
\]

这个代换的核心记忆是：

\[
t=\cos 2\varphi
\quad\Longrightarrow\quad
1-t=2\sin^2\varphi,
\qquad
1+t=2\cos^2\varphi.
\]

## 作业 12.1：第 5（7）题的换元做法

原题区域由

\[
\sqrt{x}+\sqrt{y}=1
\]

和两坐标轴围成。

用户提出的换元是：

\[
x=R^2\sin^4 t,
\qquad
 y=R^2\cos^4 t.
\]

这个换元是合理的，因为

\[
\sqrt{x}=R\sin^2t,
\qquad
\sqrt{y}=R\cos^2t.
\]

所以

\[
\sqrt{x}+\sqrt{y}
=R(\sin^2t+\cos^2t)
=R.
\]

因此原来的边界

\[
\sqrt{x}+\sqrt{y}=1
\]

直接变成

\[
R=1.
\]

区域对应为

\[
0\le R\le 1,
\qquad
0\le t\le \frac\pi2.
\]

接下来计算 Jacobian。

由

\[
x=R^2\sin^4t,
\qquad
 y=R^2\cos^4t,
\]

得

\[
\frac{\partial x}{\partial R}=2R\sin^4t,
\qquad
\frac{\partial x}{\partial t}=4R^2\sin^3t\cos t,
\]

\[
\frac{\partial y}{\partial R}=2R\cos^4t,
\qquad
\frac{\partial y}{\partial t}=-4R^2\cos^3t\sin t.
\]

所以

\[
J=rac{\partial(x,y)}{\partial(R,t)}
=egin{vmatrix}
2R\sin^4t & 4R^2\sin^3t\cos t\\
2R\cos^4t & -4R^2\cos^3t\sin t
\end{vmatrix}.
\]

计算得

\[
J=-8R^3\sin^3t\cos^3t.
\]

因此面积元为

\[
dxdy=|J|dRdt
=8R^3\sin^3t\cos^3t\,dRdt.
\]

原积分为

\[
I=\iint_D(\sqrt{x}+\sqrt{y})\,dxdy.
\]

因为

\[
\sqrt{x}+\sqrt{y}=R,
\]

所以

\[
I=\int_0^1\int_0^{\pi/2}
R\cdot 8R^3\sin^3t\cos^3t\,dt dR.
\]

即

\[
I=8\left(\int_0^1R^4\,dR\right)
\left(\int_0^{\pi/2}\sin^3t\cos^3t\,dt\right).
\]

第一项：

\[
\int_0^1R^4\,dR=\frac15.
\]

第二项：

\[
\int_0^{\pi/2}\sin^3t\cos^3t\,dt
=\frac1{12}.
\]

所以

\[
I=8\cdot \frac15\cdot \frac1{12}
=\frac{2}{15}.
\]

答案：

\[
\boxed{I=\frac{2}{15}}.
\]

这个换元的优点是：

\[
\sqrt{x}+\sqrt{y}=R
\]

会直接把曲边界变成直边界 \(R=1\)，和极坐标思想很像。

## 作业 12.1：第 5（8）题的 Beta 函数做法

第（8）题已经化到

\[
I=\int_0^2 y\left(2-\sqrt{2y-y^2}\right)dy.
\]

拆开：

\[
I=\int_0^2 2y\,dy-
\int_0^2 y\sqrt{2y-y^2}\,dy.
\]

第一项为

\[
\int_0^2 2y\,dy=4.
\]

重点是第二项：

\[
K=\int_0^2 y\sqrt{2y-y^2}\,dy.
\]

可以令

\[
y=2t,
\qquad
 dy=2dt.
\]

当 \(y=0\) 时，\(t=0\)；当 \(y=2\) 时，\(t=1\)。

并且

\[
2y-y^2=4t-4t^2=4t(1-t).
\]

所以

\[
\sqrt{2y-y^2}=2\sqrt{t(1-t)}.
\]

代入得

\[
K=\int_0^1 (2t)\cdot 2\sqrt{t(1-t)}\cdot 2\,dt.
\]

即

\[
K=8\int_0^1 t^{3/2}(1-t)^{1/2}\,dt.
\]

用 Beta 函数：

\[
B(p,q)=\int_0^1 t^{p-1}(1-t)^{q-1}dt.
\]

这里

\[
p-1=\frac32,
\qquad
q-1=\frac12.
\]

所以

\[
p=\frac52,
\qquad
q=\frac32.
\]

因此

\[
K=8B\left(\frac52,\frac32\right).
\]

又

\[
B\left(\frac52,\frac32\right)
=\frac{\Gamma(5/2)\Gamma(3/2)}{\Gamma(4)}.
\]

其中

\[
\Gamma\left(\frac52\right)=\frac{3\sqrt\pi}{4},
\qquad
\Gamma\left(\frac32\right)=\frac{\sqrt\pi}{2},
\qquad
\Gamma(4)=3!=6.
\]

所以

\[
B\left(\frac52,\frac32\right)
=\frac{\frac{3\sqrt\pi}{4}\cdot \frac{\sqrt\pi}{2}}{6}
=\frac{\pi}{16}.
\]

于是

\[
K=8\cdot \frac\pi{16}=\frac\pi2.
\]

最后

\[
I=4-K=4-\frac\pi2.
\]

答案：

\[
\boxed{I=4-\frac\pi2}.
\]

这个方法的核心是：

\[
y=2t
\]

把区间 \([0,2]\) 压到 \([0,1]\)，并把

\[
2y-y^2
\]

变成标准 Beta 型的

\[
t(1-t).
\]

## 作业 12.1：第 6--10 题详细解答

### 第 6 题

题目：求四张平面

\[
x=0,\qquad y=0,\qquad x=1,\qquad y=1
\]

所围成的柱体，被平面

\[
z=0
\]

和

\[
2x+3y+z=6
\]

截出的立体体积。

由

\[
2x+3y+z=6
\]

得

\[
z=6-2x-3y.
\]

底面区域为

\[
D=[0,1]\times[0,1].
\]

在这个区域内，上表面是

\[
z=6-2x-3y,
\]

下表面是

\[
z=0.
\]

因为当 \((x,y)\in[0,1]\times[0,1]\) 时，

\[
6-2x-3y\ge 1>0,
\]

所以体积为

\[
V=\iint_D(6-2x-3y)\,dxdy.
\]

即

\[
V=\int_0^1\int_0^1(6-2x-3y)\,dxdy.
\]

计算：

\[
V=6\cdot 1\cdot 1
-2\int_0^1\int_0^1x\,dxdy
-3\int_0^1\int_0^1y\,dxdy.
\]

其中

\[
\int_0^1\int_0^1x\,dxdy=\frac12,
\qquad
\int_0^1\int_0^1y\,dxdy=\frac12.
\]

所以

\[
V=6-2\cdot\frac12-3\cdot\frac12
=6-1-\frac32
=\frac72.
\]

答案：

\[
\boxed{V=\frac72}.
\]

---

### 第 7 题

题目：设 \(f(x)\) 在 \([0,1]\) 上连续，证明

\[
\int_0^1dy\int_y^{\sqrt y}e^y f(x)\,dx
=\int_0^1(e^x-e^{x^2})f(x)\,dx.
\]

原积分对应区域为

\[
0\le y\le 1,
\qquad
 y\le x\le \sqrt y.
\]

由

\[
x\le \sqrt y
\]

两边平方，得

\[
x^2\le y.
\]

又有

\[
y\le x.
\]

所以换成以 \(x\) 为外层变量时，区域为

\[
0\le x\le 1,
\qquad
x^2\le y\le x.
\]

因此交换积分次序：

\[
\int_0^1dy\int_y^{\sqrt y}e^y f(x)\,dx
=
\int_0^1dx\int_{x^2}^{x}e^y f(x)\,dy.
\]

因为 \(f(x)\) 与 \(y\) 无关，所以

\[
=\int_0^1 f(x)\left(\int_{x^2}^{x}e^y\,dy\right)dx.
\]

而

\[
\int_{x^2}^{x}e^y\,dy
=e^x-e^{x^2}.
\]

所以

\[
\int_0^1dy\int_y^{\sqrt y}e^y f(x)\,dx
=\int_0^1(e^x-e^{x^2})f(x)\,dx.
\]

证毕。

---

### 第 8 题

题目：利用二重积分的性质证明 Cauchy 不等式。设 \(f(x)\) 在 \([a,b]\) 上连续，证明

\[
\left(\int_a^b f(x)\,dx\right)^2
\le
(b-a)\int_a^b[f(x)]^2\,dx.
\]

考虑非负函数

\[
[f(x)-f(y)]^2\ge 0.
\]

在正方形区域

\[
D=[a,b]\times[a,b]
\]

上积分，有

\[
\iint_D[f(x)-f(y)]^2\,dxdy\ge 0.
\]

展开：

\[
[f(x)-f(y)]^2=f^2(x)-2f(x)f(y)+f^2(y).
\]

所以

\[
\iint_D[f(x)-f(y)]^2\,dxdy
=
\iint_D f^2(x)\,dxdy
-2\iint_D f(x)f(y)\,dxdy
+
\iint_D f^2(y)\,dxdy.
\]

分别计算。

第一项：

\[
\iint_D f^2(x)\,dxdy
=(b-a)\int_a^b f^2(x)\,dx.
\]

第三项同理：

\[
\iint_D f^2(y)\,dxdy
=(b-a)\int_a^b f^2(y)\,dy.
\]

第二项：

\[
\iint_D f(x)f(y)\,dxdy
=
\left(\int_a^b f(x)\,dx\right)
\left(\int_a^b f(y)\,dy\right)
=
\left(\int_a^b f(x)\,dx\right)^2.
\]

因此

\[
0\le
2(b-a)\int_a^b f^2(x)\,dx
-2\left(\int_a^b f(x)\,dx\right)^2.
\]

两边除以 2，得

\[
\left(\int_a^b f(x)\,dx\right)^2
\le
(b-a)\int_a^b f^2(x)\,dx.
\]

证毕。

---

### 第 9 题

题目：求抛物面

\[
z=6-x^2-y^2
\]

与锥面

\[
z=\sqrt{x^2+y^2}
\]

所围立体的体积。

用柱坐标：

\[
x=r\cos\theta,
\qquad
 y=r\sin\theta.
\]

则抛物面为

\[
z=6-r^2,
\]

锥面为

\[
z=r.
\]

两曲面交线由

\[
6-r^2=r
\]

给出，即

\[
r^2+r-6=0.
\]

解得

\[
r=2
\]

其中正根有效。

所以投影区域是圆盘

\[
0\le r\le 2,
\qquad
0\le \theta\le 2\pi.
\]

上表面是

\[
z=6-r^2,
\]

下表面是

\[
z=r.
\]

因此体积为

\[
V=\int_0^{2\pi}\int_0^2
\left[(6-r^2)-r\right]r\,drd\theta.
\]

即

\[
V=\int_0^{2\pi}\int_0^2
(6r-r^3-r^2)\,drd\theta.
\]

先对 \(r\) 积分：

\[
\int_0^2(6r-r^3-r^2)\,dr
=\left(3r^2-\frac{r^4}{4}-\frac{r^3}{3}\right)_0^2.
\]

代入：

\[
=12-4-\frac83
=\frac{16}{3}.
\]

所以

\[
V=2\pi\cdot\frac{16}{3}
=\frac{32\pi}{3}.
\]

答案：

\[
\boxed{V=\frac{32\pi}{3}}.
\]

---

### 第 10 题

题目：设 \(f(u)\) 在 \([-1,1]\) 上连续，证明

\[
\iint_{|x|+|y|\le 1} f(x+y)\,dxdy
=\int_{-1}^{1}f(u)\,du.
\]

令

\[
u=x+y,
\qquad
v=x-y.
\]

则

\[
x=\frac{u+v}{2},
\qquad
 y=\frac{u-v}{2}.
\]

Jacobian 为

\[
\left|\frac{\partial(x,y)}{\partial(u,v)}\right|
=\frac12.
\]

下面看区域。原区域为

\[
|x|+|y|\le 1.
\]

代入

\[
x=\frac{u+v}{2},
\qquad
 y=\frac{u-v}{2},
\]

有

\[
|x|+|y|
=\frac12\left(|u+v|+|u-v|\right).
\]

利用恒等式

\[
|u+v|+|u-v|=2\max\{|u|,|v|\},
\]

所以

\[
|x|+|y|\le 1
\]

等价于

\[
\max\{|u|,|v|\}\le 1.
\]

即

\[
-1\le u\le 1,
\qquad
-1\le v\le 1.
\]

所以原来的菱形区域变成 \((u,v)\) 平面上的正方形：

\[
[-1,1]\times[-1,1].
\]

因此

\[
\iint_{|x|+|y|\le 1} f(x+y)\,dxdy
=\int_{-1}^{1}\int_{-1}^{1}f(u)\cdot\frac12\,dvdu.
\]

由于 \(f(u)\) 与 \(v\) 无关，先对 \(v\) 积分：

\[
\int_{-1}^{1}\frac12\,dv=1.
\]

所以

\[
\iint_{|x|+|y|\le 1} f(x+y)\,dxdy
=\int_{-1}^{1}f(u)\,du.
\]

证毕。
