# tmp.md 归档：微分形式、方向、Green/Stokes/Gauss 与 Jacobian（2026-06-10）

本文件由 `tmp.md` 中上一批概念问答整理归档而来。归档后，`tmp.md` 已用于新的黑板内容。

---

# 旋度、散度、Green 公式与边界法向量的关系

## 1. 先区分两类边界积分

在三维向量分析里，常见有两类边界积分。

第一类是沿边界曲线的切向积分，也就是环流：

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\oint_{\partial S}\mathbf F\cdot\mathbf T\,ds.
$$

这里

$$
d\mathbf r=(dx,dy,dz)=\mathbf T\,ds
$$

是切向位移元。

这种积分由 Stokes 公式转换成曲面积分：

$$
\boxed{
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
}
$$

所以：

$$
\boxed{
\text{切向环流} \longleftrightarrow \text{旋度通量}.
}
$$

第二类是穿过边界曲面的法向通量：

$$
\iint_{\partial\Omega}\mathbf F\cdot\mathbf n\,dS.
$$

这种积分由 Gauss 公式转换成体积分：

$$
\boxed{
\iint_{\partial\Omega}\mathbf F\cdot\mathbf n\,dS
=\iiint_\Omega\nabla\cdot\mathbf F\,dV.
}
$$

所以：

$$
\boxed{
\text{法向通量} \longleftrightarrow \text{散度体积分}.
}
$$

---

## 2. 散度公式里的边界法向量怎么得到

如果 $\Omega$ 是三维体区域，那么边界 $\partial\Omega$ 是二维曲面。

Gauss 公式规定方向取外侧，所以法向量是

$$
\mathbf n=\text{outward unit normal}.
$$

具体怎么求？常见有三种方式。

---

### 2.1 参数化曲面：用叉乘

若曲面参数化为

$$
\mathbf r(u,v)=(x(u,v),y(u,v),z(u,v)),
$$

则两个切向量是

$$
\mathbf r_u,
\qquad \mathbf r_v.
$$

有向面积元为

$$
\mathbf n\,dS=\mathbf r_u\times\mathbf r_v\,du\,dv.
$$

如果

$$
\mathbf r_u\times\mathbf r_v
$$

指向外侧，就直接用；如果指向内侧，就取负号。

展开叉乘：

$$
\mathbf r_u\times\mathbf r_v\,du\,dv
=(dy\,dz,dz\,dx,dx\,dy).
$$

因此第二型曲面积分

$$
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

就是

$$
(P,Q,R)\cdot(\mathbf r_u\times\mathbf r_v)\,du\,dv.
$$

---

### 2.2 图形曲面：直接用公式

若曲面是

$$
z=f(x,y),
$$

取上侧方向，则

$$
\mathbf r(x,y)=(x,y,f(x,y)).
$$

所以

$$
\mathbf r_x\times\mathbf r_y=(-f_x,-f_y,1).
$$

因此

$$
\mathbf n\,dS=(-f_x,-f_y,1)dx\,dy.
$$

如果取下侧方向，就改成

$$
\mathbf n\,dS=(f_x,f_y,-1)dx\,dy.
$$

同理：

若

$$
x=g(y,z),
$$

取 $x$ 正向侧，则

$$
\mathbf n\,dS=(1,-g_y,-g_z)dy\,dz.
$$

若

$$
y=h(z,x),
$$

取 $y$ 正向侧，则

$$
\mathbf n\,dS=(-h_x,1,-h_z)dz\,dx
$$

注意变量顺序要和所用投影面一致。

---

### 2.3 隐式曲面：用梯度

若曲面由

$$
G(x,y,z)=0
$$

给出，那么

$$
\nabla G
$$

垂直于曲面。

单位法向可取

$$
\mathbf n=\pm {\nabla G\over |\nabla G|}.
$$

符号由方向决定：

- 封闭曲面取外侧；
- 开曲面按题目给定方向；
- 若题目说“上侧”，取 $z$ 分量为正；
- 若题目说“下侧”，取 $z$ 分量为负。

---

## 3. 高维里也是同一个规律吗

是的。

在 $n$ 维中，散度定理是

$$
\int_\Omega \operatorname{div}\mathbf F\,dV
=\int_{\partial\Omega}\mathbf F\cdot\mathbf n\,dS.
$$

这里 $\Omega$ 是 $n$ 维区域，$\partial\Omega$ 是 $n-1$ 维边界。

所以你说的

$$
\text{散度是 }(n-1)\text{ 维边界积分换成 }n\text{ 维体积分}
$$

是对的。

在高维中，边界上的法向量仍然由边界的切空间正交方向给出。若边界用 $n-1$ 个参数表示，那么法向面积元由 Jacobi 矩阵的余子式决定。

三维中的

$$
\mathbf r_u\times\mathbf r_v
$$

就是这个“余子式法向量”在三维中的特殊写法。

---

## 4. 方向如何确定

方向不是随便定的。

### 4.1 Gauss 公式

对体区域 $\Omega$，边界方向默认取外法向：

$$
\mathbf n=\mathbf n_{\text{out}}.
$$

所以如果参数化得到的

$$
\mathbf r_u\times\mathbf r_v
$$

指向内侧，就要改成

$$
\mathbf r_v\times\mathbf r_u
$$

或整体加负号。

### 4.2 Stokes 公式

对曲面 $S$，先选法向量 $\mathbf n$。

边界方向由右手定则决定：

- 大拇指指向 $\mathbf n$；
- 四指弯曲方向就是边界正方向。

如果题目给了边界方向，就反过来选择与它匹配的 $\mathbf n$。

---

## 5. Green 公式是旋度积分的特殊情形吗

是，但要注意 Green 公式有两种常见形式。

---

### 5.1 环流形式的 Green 公式：二维 Stokes

平面中设

$$
\mathbf F=(P,Q).
$$

边界积分

$$
\oint_{\partial D}P\,dx+Q\,dy
$$

是切向积分，因为

$$
(dx,dy)=\mathbf T\,ds.
$$

二维旋度是标量：

$$
\operatorname{curl}(P,Q)=Q_x-P_y.
$$

因此

$$
\boxed{
\oint_{\partial D}P\,dx+Q\,dy
=\iint_D(Q_x-P_y)\,dx\,dy.
}
$$

这就是 Green 公式的环流形式。

它确实是三维 Stokes 公式的特殊情形。

因为可以把平面向量场看成三维向量场

$$
(P,Q,0),
$$

取曲面为 $xy$ 平面区域 $D$，法向为

$$
\mathbf k=(0,0,1).
$$

则

$$
\nabla\times(P,Q,0)=(0,0,Q_x-P_y).
$$

所以

$$
(\nabla\times\mathbf F)\cdot\mathbf k=Q_x-P_y.
$$

---

### 5.2 通量形式的 Green 公式：二维 Gauss

平面中还有另一种 Green 公式：

$$
\boxed{
\oint_{\partial D}P\,dy-Q\,dx
=\iint_D(P_x+Q_y)\,dx\,dy.
}
$$

这是二维散度定理。

为什么？

若边界正向为逆时针，则单位切向量满足

$$
(dx,dy)=\mathbf T\,ds.
$$

外法向量满足

$$
\mathbf n\,ds=(dy,-dx).
$$

因此

$$
(P,Q)\cdot\mathbf n\,ds
=P\,dy-Q\,dx.
$$

所以

$$
\oint_{\partial D}P\,dy-Q\,dx
$$

是法向通量积分。

它对应的是散度：

$$
\operatorname{div}(P,Q)=P_x+Q_y.
$$

---

## 6. 所以 Green 公式到底属于旋度还是散度

要看你写的是哪种边界积分。

如果边界积分是

$$
P\,dx+Q\,dy,
$$

它是切向环流，所以对应旋度：

$$
Q_x-P_y.
$$

如果边界积分是

$$
P\,dy-Q\,dx,
$$

它是法向通量，所以对应散度：

$$
P_x+Q_y.
$$

因此：

$$
\boxed{
Pdx+Qdy \Rightarrow \text{旋度 Green 公式};
}
$$

$$
\boxed{
Pdy-Qdx \Rightarrow \text{散度 Green 公式}.
}
$$

---

## 7. 总结

- 旋度：把边界上的切向环流换成内部曲面上的旋度通量。

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

- 散度：把边界上的法向通量换成内部体区域上的散度积分。

$$
\iint_{\partial\Omega}\mathbf F\cdot\mathbf n\,dS
=\iiint_\Omega\nabla\cdot\mathbf F\,dV.
$$

- 法向量通常通过参数化叉乘、图形曲面公式或隐式曲面梯度得到。

- Green 公式中，$Pdx+Qdy$ 是旋度型；$Pdy-Qdx$ 是散度型。

---

# 梯度、散度、旋度的本质、维度差异与严格小量推导

## 1. 先纠正：增长方向是梯度，不是散度

若 $f(x,y,z)$ 是标量函数，那么它的增长方向由梯度给出：

$$
\nabla f=(f_x,f_y,f_z).
$$

梯度满足一阶 Taylor 展开：

$$
f(\mathbf x+\Delta\mathbf x)-f(\mathbf x)
=\nabla f(\mathbf x)\cdot\Delta\mathbf x+o(|\Delta\mathbf x|).
$$

当 $|\Delta\mathbf x|$ 固定时，由 Cauchy-Schwarz 不等式，

$$
\nabla f\cdot\Delta\mathbf x
$$

在 $\Delta\mathbf x$ 与 $\nabla f$ 同方向时最大。

所以：

$$
\boxed{\nabla f\text{ 才是函数增长最快的方向。}}
$$

---

## 2. 散度不是增长方向，而是净流出密度

设向量场

$$
\mathbf F=(P,Q,R).
$$

散度是

$$
\nabla\cdot\mathbf F=P_x+Q_y+R_z.
$$

它是一个标量，不是向量。

几何意义是单位体积内的净流出量密度：

$$
\boxed{
\nabla\cdot\mathbf F
=\lim_{V\to0}{1\over V}\iint_{\partial V}\mathbf F\cdot\mathbf n\,dS.
}
$$

所以散度描述的是：

- 正值：局部像源头，往外流；
- 负值：局部像汇点，往内流；
- 零：局部无净源汇。

---

## 3. 散度的严格小盒子推导

取一个以点 $(x,y,z)$ 为中心的小长方体：

$$
\Delta x\times\Delta y\times\Delta z.
$$

先看 $x$ 方向通量。

右侧面在

$$
x+{\Delta x\over2},
$$

外法向为 $+\mathbf i$，通量近似为

$$
P\left(x+{\Delta x\over2},y,z\right)\Delta y\Delta z.
$$

左侧面在

$$
x-{\Delta x\over2},
$$

外法向为 $-\mathbf i$，通量近似为

$$
-P\left(x-{\Delta x\over2},y,z\right)\Delta y\Delta z.
$$

两侧相加：

$$
\left[
P\left(x+{\Delta x\over2},y,z\right)
-P\left(x-{\Delta x\over2},y,z\right)
\right]\Delta y\Delta z.
$$

由 Taylor 展开：

$$
P\left(x+{\Delta x\over2},y,z\right)
-P\left(x-{\Delta x\over2},y,z\right)
=P_x\Delta x+o(\Delta x).
$$

所以 $x$ 方向净通量为

$$
P_x\Delta x\Delta y\Delta z+o(\Delta x\Delta y\Delta z).
$$

同理，$y,z$ 方向分别给出

$$
Q_y\Delta x\Delta y\Delta z+o(\Delta x\Delta y\Delta z),
$$

$$
R_z\Delta x\Delta y\Delta z+o(\Delta x\Delta y\Delta z).
$$

总净通量为

$$
(P_x+Q_y+R_z)\Delta x\Delta y\Delta z+o(\Delta V).
$$

除以体积

$$
\Delta V=\Delta x\Delta y\Delta z,
$$

再令小盒子收缩到点，得到

$$
\boxed{
\nabla\cdot\mathbf F=P_x+Q_y+R_z.
}
$$

这说明散度公式不是纯直觉，而是由 Taylor 展开的一阶主项严格推出的；高阶无穷小除以体积后趋于零。

---

## 4. 旋度不是增长方向，而是局部环流密度

三维中旋度是

$$
\nabla\times\mathbf F.
$$

它的方向表示局部旋转轴方向，满足右手定则；它的大小表示垂直于该方向的小面积上的单位面积环流密度。

严格定义是：给定单位法向量 $\mathbf n$，有

$$
\boxed{
(\nabla\times\mathbf F)\cdot\mathbf n
=\lim_{A\to0}{1\over A}\oint_{\partial S}\mathbf F\cdot d\mathbf r.
}
$$

其中 $S$ 是法向为 $\mathbf n$ 的小曲面片，面积为 $A$。

所以旋度不是“增长方向”，而是“局部绕某方向旋转的强度”。

---

## 5. 旋度的小矩形 Taylor 推导

先在 $xy$ 平面中看一个小矩形，边长为

$$
\Delta x,
\qquad \Delta y.
$$

设

$$
\mathbf F=(P,Q,R).
$$

只看沿矩形边界的环流：

$$
\oint P\,dx+Q\,dy+R\,dz.
$$

因为矩形在 $xy$ 平面内，所以

$$
dz=0.
$$

因此只剩

$$
\oint P\,dx+Q\,dy.
$$

取逆时针方向。

上下两条边贡献主要来自 $P\,dx$。

下边在

$$
y-{\Delta y\over2},
$$

方向向右，贡献近似

$$
P\left(x,y-{\Delta y\over2}\right)\Delta x.
$$

上边在

$$
y+{\Delta y\over2},
$$

方向向左，贡献近似

$$
-P\left(x,y+{\Delta y\over2}\right)\Delta x.
$$

两者相加：

$$
-\left[
P\left(x,y+{\Delta y\over2}\right)
-P\left(x,y-{\Delta y\over2}\right)
\right]\Delta x.
$$

由 Taylor 展开：

$$
P\left(x,y+{\Delta y\over2}\right)
-P\left(x,y-{\Delta y\over2}\right)
=P_y\Delta y+o(\Delta y).
$$

所以上下边贡献为

$$
-P_y\Delta x\Delta y+o(\Delta x\Delta y).
$$

左右两条边贡献来自 $Q\,dy$。

右边方向向上，贡献近似

$$
Q\left(x+{\Delta x\over2},y\right)\Delta y.
$$

左边方向向下，贡献近似

$$
-Q\left(x-{\Delta x\over2},y\right)\Delta y.
$$

两者相加：

$$
\left[
Q\left(x+{\Delta x\over2},y\right)
-Q\left(x-{\Delta x\over2},y\right)
\right]\Delta y.
$$

由 Taylor 展开：

$$
Q\left(x+{\Delta x\over2},y\right)
-Q\left(x-{\Delta x\over2},y\right)
=Q_x\Delta x+o(\Delta x).
$$

所以左右边贡献为

$$
Q_x\Delta x\Delta y+o(\Delta x\Delta y).
$$

总环流为

$$
(Q_x-P_y)\Delta x\Delta y+o(\Delta x\Delta y).
$$

除以面积

$$
\Delta A=\Delta x\Delta y,
$$

得到

$$
\boxed{
(\nabla\times\mathbf F)_z=Q_x-P_y.
}
$$

同理，在 $yz$ 平面的小矩形得到

$$
\boxed{
(\nabla\times\mathbf F)_x=R_y-Q_z.
}
$$

在 $zx$ 平面的小矩形得到

$$
\boxed{
(\nabla\times\mathbf F)_y=P_z-R_x.
}
$$

因此

$$
\boxed{
\nabla\times\mathbf F=(R_y-Q_z,\ P_z-R_x,\ Q_x-P_y).
}
$$

---

## 6. 行列式和叉乘只是记忆形式

三维中常写

$$
\nabla\times\mathbf F
=\begin{vmatrix}
\mathbf i&\mathbf j&\mathbf k\\
\partial_x&\partial_y&\partial_z\\
P&Q&R
\end{vmatrix}.
$$

这个行列式不是普通数值行列式，而是一个记忆工具。

它展开后给出：

$$
\nabla\times\mathbf F
=\left(
R_y-Q_z,
P_z-R_x,
Q_x-P_y
\right).
$$

也可以写成形式上的叉乘：

$$
\nabla\times\mathbf F=\nabla\times(P,Q,R).
$$

但要记住：

$$
\nabla=(\partial_x,\partial_y,\partial_z)
$$

是微分算子，不是普通向量。

所以这个“叉乘”是按照叉乘展开规则组织偏导数。

---

## 7. 不同维度下旋度怎么选择

### 7.1 二维旋度

在二维中

$$
\mathbf F=(P,Q).
$$

没有真正的三维旋转轴，但可以把它嵌入三维：

$$
\tilde{\mathbf F}=(P,Q,0).
$$

于是

$$
\nabla\times\tilde{\mathbf F}=(0,0,Q_x-P_y).
$$

所以二维旋度通常定义为标量：

$$
\boxed{
\operatorname{curl}(P,Q)=Q_x-P_y.
}
$$

它表示垂直于平面的旋转强度。

---

### 7.2 三维旋度

三维中旋度是向量：

$$
\boxed{
\nabla\times(P,Q,R)=(R_y-Q_z,\ P_z-R_x,\ Q_x-P_y).
}
$$

它的方向是局部旋转轴方向，大小是单位面积环流密度的最大值。

---

### 7.3 更高维旋度

在更高维中，旋度一般不再自然是一个向量。

设

$$
\mathbf F=(F_1,F_2,\dots,F_n).
$$

更本质的对象是反对称偏导数组：

$$
\boxed{
\Omega_{ij}=\partial_iF_j-\partial_jF_i.
}
$$

它描述每一个坐标平面 $(x_i,x_j)$ 内的局部环流密度。

从微分形式看，

$$
\omega=F_1dx_1+F_2dx_2+\cdots+F_ndx_n.
$$

则

$$
d\omega=\sum_{i<j}(\partial_iF_j-\partial_jF_i)dx_i\wedge dx_j.
$$

这就是高维的“旋度”。

三维中，因为 $2$-形式可以通过 Hodge 对偶对应到向量，所以我们才把旋度写成一个向量。

二维中，$2$-形式只有一个分量，所以旋度是标量。

---

## 8. 投影面积和高阶无穷小的严格来源

曲面积分里经常说

$$
\mathbf n\,dS=(dy\,dz,dz\,dx,dx\,dy).
$$

这也不是纯直觉。

设曲面参数化为

$$
\mathbf r(u,v).
$$

在点 $(u,v)$ 附近取小增量 $\Delta u,\Delta v$。

Taylor 展开：

$$
\mathbf r(u+\Delta u,v)
=\mathbf r(u,v)+\mathbf r_u\Delta u+o(\Delta u),
$$

$$
\mathbf r(u,v+\Delta v)
=\mathbf r(u,v)+\mathbf r_v\Delta v+o(\Delta v).
$$

所以这个小曲面片一阶近似为由

$$
\mathbf r_u\Delta u
$$

和

$$
\mathbf r_v\Delta v
$$

张成的小平行四边形。

它的有向面积向量为

$$
(\mathbf r_u\Delta u)\times(\mathbf r_v\Delta v)
=(\mathbf r_u\times\mathbf r_v)\Delta u\Delta v.
$$

曲面的弯曲造成的误差是更高阶小量，除以面积量级

$$
\Delta u\Delta v
$$

后趋于 $0$。

因此在积分极限中，曲面片的有向面积元就是

$$
\boxed{
\mathbf n\,dS=\mathbf r_u\times\mathbf r_v\,du\,dv.
}
$$

展开叉乘后就是

$$
\boxed{
\mathbf n\,dS=(dy\,dz,dz\,dx,dx\,dy).
}
$$

这就是投影面积公式的严格来源。

---

## 9. 总结

- 梯度给出标量函数增长最快方向。
- 散度是向量场单位体积净流出密度，是标量。
- 旋度是向量场单位面积环流密度；三维中可表示成向量，二维中是标量，高维中本质上是反对称 $2$-形式。
- 行列式和叉乘是三维中记忆旋度分量的工具。
- 投影面积和法向面积元来自曲面参数化的一阶 Taylor 近似；剩余误差是高阶无穷小。

---

# 怎么理解 \(dx,dy,dz\) 以及方向从哪里来

## 1. \(dx,dy,dz\) 本身不是普通数字

在积分里，

$$
dx,dy,dz
$$

不是孤立的普通数。

更准确地说，它们是坐标函数的微分。

比如

$$
dx
$$

表示“沿当前对象移动时，$x$ 坐标的微小变化”。

但这个“变化”到底是正还是负，取决于你沿什么方向移动。

所以单独看

$$
dx
$$

没有完整方向信息；它必须被拉回到某个有向参数上。

---

## 2. 曲线情形：方向由参数 \(t\) 决定

若曲线参数化为

$$
\mathbf r(t)=(x(t),y(t),z(t)),
\qquad \alpha\le t\le\beta,
$$

并且方向是 $t$ 增大的方向，那么

$$
dx=x'(t)dt,
\qquad
 dy=y'(t)dt,
\qquad
 dz=z'(t)dt.
$$

此时

$$
(dx,dy,dz)=(x'(t),y'(t),z'(t))dt
=\mathbf r'(t)dt.
$$

这就是切向位移元

$$
d\mathbf r.
$$

所以曲线积分里的方向和正负由参数方向决定。

如果把参数反过来，积分会变号。

---

## 3. 曲面情形：方向由参数 \((u,v)\) 的顺序决定

若曲面参数化为

$$
\mathbf r(u,v)=(x(u,v),y(u,v),z(u,v)),
$$

则有向面积元由

$$
\mathbf r_u\times\mathbf r_v\,du\,dv
$$

决定。

如果把参数顺序换成 $(v,u)$，则

$$
\mathbf r_v\times\mathbf r_u
=-\mathbf r_u\times\mathbf r_v.
$$

所以曲面的方向会反过来。

因此

$$
dy\,dz,
\qquad dz\,dx,
\qquad dx\,dy
$$

的正负也不是凭空来的，而是由

$$
{\partial(y,z)\over\partial(u,v)},
\qquad
{\partial(z,x)\over\partial(u,v)},
\qquad
{\partial(x,y)\over\partial(u,v)}
$$

这些 Jacobian 的符号决定。

---

## 4. 不显式写参数时，方向从题目约定来

很多题不显式写 $t$ 或 $(u,v)$，但题目会给方向约定，例如：

- 平面闭曲线正向：默认逆时针；
- 封闭曲面：默认外侧；
- 开曲面：上侧、下侧、外侧、内侧；
- 空间曲线：从某轴正方向看为逆时针。

这些方向约定等价于替你选好了参数方向或法向方向。

所以计算时可以不显式写参数，而直接使用公式。

例如曲面

$$
z=f(x,y)
$$

取上侧时，直接用

$$
\mathbf n\,dS=(-f_x,-f_y,1)dxdy.
$$

这其实背后就是参数化

$$
\mathbf r(x,y)=(x,y,f(x,y))
$$

以及参数顺序 $(x,y)$。

---

## 5. 为什么有时不写参数也能算

因为很多公式已经把参数化和方向编码好了。

例如：

### 曲线积分

若直接参数化，就算

$$
\int \mathbf F(\mathbf r(t))\cdot\mathbf r'(t)dt.
$$

如果不想硬算曲线参数，可以用 Green 或 Stokes：

$$
\oint_{\partial S}\mathbf F\cdot d\mathbf r
=\iint_S(\nabla\times\mathbf F)\cdot\mathbf n\,dS.
$$

### 曲面积分

若直接参数化，就算

$$
\iint \mathbf F(\mathbf r(u,v))\cdot(\mathbf r_u\times\mathbf r_v)du\,dv.
$$

如果是封闭曲面，可以用 Gauss：

$$
\iint_{\partial\Omega}\mathbf F\cdot\mathbf n\,dS
=\iiint_\Omega\nabla\cdot\mathbf F\,dV.
$$

这时看起来像是“直接求导组合然后做 $n$ 重积分”。

本质上是外微分和广义 Stokes 公式在起作用。

---

## 6. 所以你的理解可以整理成这样

可以这样理解：

$$
\boxed{
 dx,dy,dz\text{ 本身只是坐标微分；方向和正负由有向参数或题目方向决定。}
}
$$

如果显式使用 $t$ 或 $(u,v)$，就是直接硬算。

如果不显式使用参数，一般就是利用：

- 题目给定的方向；
- Green/Stokes/Gauss 公式；
- 图形曲面公式；
- 隐式曲面法向公式；
- 对称性或投影面积公式。

最后把问题变成普通重积分。

---

## 7. 一句话总结

$$
\boxed{
\text{微分元负责记录“沿什么对象取变化”；参数或方向约定负责决定正负；积分定理负责避免显式参数化。}
}
$$

---

# Green、Stokes、Gauss 中顺序和反号从哪里来

## 1. 先固定总方向顺序

在平面中，默认正方向面积元是

$$
dx\,dy.
$$

在三维中，默认正方向体积元是

$$
dx\,dy\,dz.
$$

微分形式里更严格写作

$$
dx\wedge dy,
\qquad
 dx\wedge dy\wedge dz.
$$

核心规则是：交换两个微分符号会变号。

例如

$$
dy\wedge dx=-dx\wedge dy.
$$

三维中，循环排列不变号：

$$
dx\wedge dy\wedge dz
=dy\wedge dz\wedge dx
=dz\wedge dx\wedge dy.
$$

但交换一次会变号，例如

$$
dx\wedge dz\wedge dy=-dx\wedge dy\wedge dz.
$$

所有 Green、Stokes、Gauss 里的反号都来自这个顺序规则。

---

## 2. Green 的环流形式为什么是 \(Q_x-P_y\)

Green 环流形式是

$$
\oint_{\partial D}P\,dx+Q\,dy
=\iint_D(Q_x-P_y)\,dx\,dy.
$$

左边是 1-形式

$$
\omega=P\,dx+Q\,dy.
$$

对它求外微分：

$$
d\omega=dP\wedge dx+dQ\wedge dy.
$$

其中

$$
dP=P_xdx+P_ydy,
$$

所以

$$
dP\wedge dx
=(P_xdx+P_ydy)\wedge dx.
$$

第一项

$$
P_xdx\wedge dx=0,
$$

因为同一个微分符号楔两次为零。

第二项

$$
P_ydy\wedge dx=-P_y dx\wedge dy.
$$

再看 $Q$：

$$
dQ=Q_xdx+Q_ydy.
$$

所以

$$
dQ\wedge dy
=(Q_xdx+Q_ydy)\wedge dy
=Q_xdx\wedge dy.
$$

因此

$$
d\omega=(Q_x-P_y)dx\wedge dy.
$$

这就是为什么 Green 公式里出现

$$
Q_x-P_y.
$$

反号来自

$$
dy\wedge dx=-dx\wedge dy.
$$

---

## 3. Green 的散度形式为什么边界上有反号

二维散度形式是

$$
\oint_{\partial D}P\,dy-Q\,dx
=\iint_D(P_x+Q_y)dxdy.
$$

这里右边是散度：

$$
P_x+Q_y.
$$

看起来没有反号。

但反号藏在左边的法向通量表达式里。

若边界 $\partial D$ 取逆时针方向，则切向位移元是

$$
(dx,dy)=\mathbf T\,ds.
$$

此时外法向面积元是

$$
\mathbf n\,ds=(dy,-dx).
$$

所以

$$
(P,Q)\cdot\mathbf n\,ds
=(P,Q)\cdot(dy,-dx)
=P\,dy-Q\,dx.
$$

因此 Green 散度形式左边必须写成

$$
P\,dy-Q\,dx.
$$

这个负号不是散度本身产生的，而是由“逆时针边界对应外法向”产生的。

如果用内法向，符号会反过来。

---

## 4. 三维散度为什么是 \(P_x+Q_y+R_z\)，没有交叉反号

三维通量形式是

$$
\eta=P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy.
$$

严格写作

$$
\eta=P\,dy\wedge dz+Q\,dz\wedge dx+R\,dx\wedge dy.
$$

对它求外微分：

$$
d\eta=dP\wedge dy\wedge dz+dQ\wedge dz\wedge dx+dR\wedge dx\wedge dy.
$$

先看第一项：

$$
dP=P_xdx+P_ydy+P_zdz.
$$

所以

$$
dP\wedge dy\wedge dz
=P_xdx\wedge dy\wedge dz.
$$

含 $dy\wedge dy$ 或 $dz\wedge dz$ 的项都为零。

因此只剩缺失变量 $x$ 的导数 $P_x$。

第二项：

$$
dQ\wedge dz\wedge dx
=Q_y dy\wedge dz\wedge dx.
$$

而

$$
dy\wedge dz\wedge dx=dx\wedge dy\wedge dz
$$

是循环排列，不变号。

所以第二项是

$$
Q_y dx\wedge dy\wedge dz.
$$

第三项：

$$
dR\wedge dx\wedge dy
=R_z dz\wedge dx\wedge dy.
$$

而

$$
dz\wedge dx\wedge dy=dx\wedge dy\wedge dz
$$

也是循环排列，不变号。

所以第三项是

$$
R_z dx\wedge dy\wedge dz.
$$

合起来：

$$
d\eta=(P_x+Q_y+R_z)dx\wedge dy\wedge dz.
$$

因此散度公式里是

$$
\boxed{P_x+Q_y+R_z}.
$$

它没有交叉反号，是因为通量形式特意采用了循环顺序：

$$
dy\,dz,
\qquad dz\,dx,
\qquad dx\,dy.
$$

这些顺序和

$$
dx\,dy\,dz
$$

都是同向的循环排列。

---

## 5. 如果写成 \(Q\,dx\,dz\) 会怎样

注意：通量形式中第二项写的是

$$
Q\,dz\,dx,
$$

不是

$$
Q\,dx\,dz.
$$

因为

$$
dx\wedge dz=-dz\wedge dx.
$$

如果写成

$$
Q\,dx\,dz,
$$

那就等于

$$
-Q\,dz\,dx.
$$

对应的 $y$ 方向面积元符号会反。

所以标准形式

$$
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

就是为了让三个方向和标准体积方向

$$
dx\,dy\,dz
$$

匹配，从而散度是全加号。

---

## 6. 旋度为什么有叉乘过程

旋度来自对 1-形式

$$
\omega=P\,dx+Q\,dy+R\,dz
$$

求外微分。

计算会得到一个 2-形式：

$$
d\omega
=(R_y-Q_z)dy\,dz+(P_z-R_x)dz\,dx+(Q_x-P_y)dx\,dy.
$$

它的三个分量分别对应三个坐标平面的环流密度。

在三维中，2-形式可以用法向量表示：

$$
(dy\,dz,dz\,dx,dx\,dy).
$$

所以这个 2-形式可以对应成向量

$$
(R_y-Q_z,\ P_z-R_x,\ Q_x-P_y).
$$

这正是

$$
\nabla\times(P,Q,R).
$$

三维中刚好可以把这个过程写成叉乘形式：

$$
\nabla\times\mathbf F
=\begin{vmatrix}
\mathbf i&\mathbf j&\mathbf k\\
\partial_x&\partial_y&\partial_z\\
P&Q&R
\end{vmatrix}.
$$

所以叉乘不是额外多出来的东西，而是三维里把“1-形式的外微分”整理成向量的记忆法。

---

## 7. 为什么散度像是“按剩下的方向求导”

看通量形式：

$$
P\,dy\,dz.
$$

它缺 $x$，所以对它求外微分时，只有 $P_xdx$ 能补成完整体积元：

$$
P_xdx\,dy\,dz.
$$

$P_y$ 项会产生

$$
dy\,dy\,dz=0,
$$

$P_z$ 项会产生

$$
dz\,dy\,dz=0.
$$

因此 $P\,dy\,dz$ 只留下 $P_x$。

同理：

$$
Q\,dz\,dx
$$

缺 $y$，所以留下 $Q_y$；

$$
R\,dx\,dy
$$

缺 $z$，所以留下 $R_z$。

因此

$$
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

求外微分后就是

$$
(P_x+Q_y+R_z)dx\,dy\,dz.
$$

这就是“按剩下的方向求导”的严格原因。

---

## 8. 总结

- Green 环流形式的反号来自

$$
dy\,dx=-dx\,dy.
$$

- Green 散度形式的反号来自外法向和逆时针切向的关系：

$$
\mathbf n\,ds=(dy,-dx).
$$

- 三维散度形式用

$$
Pdy\,dz+Qdz\,dx+Rdx\,dy
$$

而不是乱序，是为了和

$$
dx\,dy\,dz
$$

保持同向循环顺序，所以得到

$$
P_x+Q_y+R_z.
$$

- 旋度有叉乘，是因为三维中 1-形式的外微分得到 2-形式，而 2-形式又可以通过有向面积元对应成向量。

---

# 微分形式的积分是怎么定义的，有什么用，本质是什么

## 1. 先说一句话定义

一个 $k$-形式就是一种可以在 $k$ 维有向对象上积分的东西。

也就是说：

- $1$-形式积分在曲线上；
- $2$-形式积分在曲面上；
- $3$-形式积分在三维体区域上；
- 一般地，$k$-形式积分在 $k$ 维有向流形上。

记作

$$
\int_M \omega,
$$

其中 $M$ 是 $k$ 维有向区域，$\omega$ 是 $k$-形式。

---

## 2. 什么是 \(k\)-形式

在三维中：

### 0-形式

普通函数

$$
f(x,y,z)
$$

是 $0$-形式。

### 1-形式

形如

$$
\omega=P\,dx+Q\,dy+R\,dz
$$

的是 $1$-形式。

它可以沿曲线积分。

### 2-形式

形如

$$
\eta=P\,dy\wedge dz+Q\,dz\wedge dx+R\,dx\wedge dy
$$

的是 $2$-形式。

它可以在曲面上积分。

### 3-形式

形如

$$
\mu=f\,dx\wedge dy\wedge dz
$$

的是 $3$-形式。

它可以在三维体区域上积分。

---

## 3. 积分怎么严格定义：拉回到参数区域

设 $M$ 是一个 $k$ 维曲面或区域，用参数化

$$
\Phi(u_1,\dots,u_k)
$$

表示。

这里

$$
(u_1,
\dots,u_k)\in U\subset\mathbb R^k.
$$

如果 $\omega$ 是一个 $k$-形式，那么定义

$$
\int_M\omega
:=\int_U\Phi^*\omega.
$$

这里

$$
\Phi^*\omega
$$

叫做 $\omega$ 在参数区域上的拉回。

直观说，就是把

$$
x,y,z,dx,dy,dz
$$

全部用

$$
u_1,
\dots,u_k,du_1,
\dots,du_k
$$

表示。

最后就变成普通多重积分。

---

## 4. 例子一：1-形式沿曲线积分

设

$$
\omega=P\,dx+Q\,dy+R\,dz.
$$

曲线参数化为

$$
\mathbf r(t)=(x(t),y(t),z(t)),
\qquad a\le t\le b.
$$

拉回时：

$$
dx=x'(t)dt,
\qquad dy=y'(t)dt,
\qquad dz=z'(t)dt.
$$

所以

$$
\mathbf r^*\omega
=\left[P(\mathbf r(t))x'(t)+Q(\mathbf r(t))y'(t)+R(\mathbf r(t))z'(t)\right]dt.
$$

因此

$$
\int_L\omega
=\int_a^b\left[P x'+Q y'+R z'\right]dt.
$$

这就是第二型曲线积分。

---

## 5. 例子二：2-形式在曲面上积分

设

$$
\eta=P\,dy\wedge dz+Q\,dz\wedge dx+R\,dx\wedge dy.
$$

曲面参数化为

$$
\mathbf r(u,v)=(x(u,v),y(u,v),z(u,v)).
$$

拉回时：

$$
dy\wedge dz
={\partial(y,z)\over\partial(u,v)}du\wedge dv,
$$

$$
dz\wedge dx
={\partial(z,x)\over\partial(u,v)}du\wedge dv,
$$

$$
dx\wedge dy
={\partial(x,y)\over\partial(u,v)}du\wedge dv.
$$

所以

$$
\mathbf r^*\eta
=\left[
P{\partial(y,z)\over\partial(u,v)}
+Q{\partial(z,x)\over\partial(u,v)}
+R{\partial(x,y)\over\partial(u,v)}
\right]du\wedge dv.
$$

这就是

$$
\iint_S P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy.
$$

它等价于通量：

$$
\iint_S\mathbf F\cdot\mathbf n\,dS.
$$

---

## 6. 例子三：3-形式在体区域上积分

设

$$
\mu=f\,dx\wedge dy\wedge dz.
$$

那么

$$
\int_\Omega\mu
=\iiint_\Omega f\,dx\,dy\,dz.
$$

这就是普通三重积分。

如果做变量替换

$$
(x,y,z)=\Phi(u,v,w),
$$

那么

$$
dx\wedge dy\wedge dz
={\partial(x,y,z)\over\partial(u,v,w)}du\wedge dv\wedge dw.
$$

也就是普通换元公式中的 Jacobian。

---

## 7. 外微分 \(d\) 是什么

外微分是把 $k$-形式变成 $(k+1)$-形式的操作：

$$
d:\Omega^k\to\Omega^{k+1}.
$$

它统一了：

- 函数的梯度；
- 向量场的旋度；
- 向量场的散度。

例如：

### 对 0-形式

$$
f
$$

有

$$
df=f_xdx+f_ydy+f_zdz.
$$

这对应梯度。

### 对 1-形式

$$
\omega=Pdx+Qdy+Rdz
$$

有

$$
d\omega
=(R_y-Q_z)dy\,dz+(P_z-R_x)dz\,dx+(Q_x-P_y)dx\,dy.
$$

这对应旋度。

### 对 2-形式

$$
\eta=Pdy\,dz+Qdz\,dx+Rdx\,dy
$$

有

$$
d\eta=(P_x+Q_y+R_z)dx\,dy\,dz.
$$

这对应散度。

---

## 8. 它有什么用

### 用处一：统一积分公式

广义 Stokes 公式：

$$
\boxed{
\int_M d\omega=\int_{\partial M}\omega
}
$$

统一了：

- Newton-Leibniz：

$$
\int_a^b f'(x)dx=f(b)-f(a);
$$

- Green 公式；
- Stokes 公式；
- Gauss 公式。

### 用处二：自动处理方向和正负号

因为

$$
dx\wedge dy=-dy\wedge dx,
$$

所以微分形式天然记录方向。

很多 Green/Stokes/Gauss 里的反号，不用死记，都是由楔积顺序推出的。

### 用处三：自动产生 Jacobian

换元时，

$$
dx\wedge dy
={\partial(x,y)\over\partial(u,v)}du\wedge dv,
$$

$$
dx\wedge dy\wedge dz
={\partial(x,y,z)\over\partial(u,v,w)}du\wedge dv\wedge dw.
$$

所以 Jacobian 不是额外发明的，而是微分形式被拉回时自然出现的。

### 用处四：适合高维

三维里有叉乘，但高维里没有普通叉乘。

微分形式不依赖叉乘，所以可以自然推广到任意维度。

---

## 9. 本质是什么

微分形式的本质可以这样理解：

$$
\boxed{
\text{微分形式是“带方向的可积分密度”。}
}
$$

更具体地说：

- $dx$ 测量沿某方向的 $x$ 变化；
- $dx\wedge dy$ 测量带方向的投影面积；
- $dx\wedge dy\wedge dz$ 测量带方向的体积；
- $Pdx+Qdy+Rdz$ 测量向量场沿曲线切向的累积；
- $Pdy\,dz+Qdz\,dx+Rdx\,dy$ 测量向量场穿过曲面的通量。

外微分 $d$ 的本质是：

$$
\boxed{
\text{从局部密度中提取边界累积的无穷小变化率。}
}
$$

广义 Stokes 公式说明：

$$
\boxed{
\text{内部无穷小变化率的总和}=\text{边界上的总累积。}
}
$$

---

## 10. 一句话总结

微分形式积分就是：

$$
\boxed{
\text{把带方向的密度拉回到参数区域，然后做普通积分。}
}
$$

它的价值是统一方向、Jacobian、Green/Stokes/Gauss 以及高维推广。

---

# 二维参数到三维空间的 Jacobian：曲面积分里的面积元怎么来

## 1. Jacobian 矩阵可以是长方形的

设曲面参数化为

$$
\mathbf r(u,v)=(x(u,v),y(u,v),z(u,v)).
$$

这是一个映射：

$$
\mathbf r: \mathbb R^2\to\mathbb R^3.
$$

它的 Jacobian 矩阵是

$$
J=
\begin{pmatrix}
 x_u & x_v\\
 y_u & y_v\\
 z_u & z_v
\end{pmatrix}.
$$

这是一个 $3\times2$ 矩阵。

所以 Jacobian 矩阵当然可以是二维到三维的。

只是这时它不是方阵，不能直接取普通行列式。

---

## 2. 面积缩放不是普通行列式，而是 Gram 行列式

$J$ 的两列正是两个切向量：

$$
\mathbf r_u=(x_u,y_u,z_u),
\qquad
\mathbf r_v=(x_v,y_v,z_v).
$$

参数平面中的小矩形

$$
du\,dv
$$

被映到空间中后，一阶近似为由

$$
\mathbf r_u\,du
$$

和

$$
\mathbf r_v\,dv
$$

张成的小平行四边形。

这个小平行四边形的面积是

$$
|\mathbf r_u\times\mathbf r_v|\,du\,dv.
$$

因此曲面面积元为

$$
\boxed{
dS=|\mathbf r_u\times\mathbf r_v|\,du\,dv.
}
$$

如果不用叉乘，也可以用 Gram 行列式：

$$
\boxed{
dS=\sqrt{\det(J^TJ)}\,du\,dv.
}
$$

因为

$$
J^TJ=
\begin{pmatrix}
\mathbf r_u\cdot\mathbf r_u & \mathbf r_u\cdot\mathbf r_v\\
\mathbf r_v\cdot\mathbf r_u & \mathbf r_v\cdot\mathbf r_v
\end{pmatrix}.
$$

所以

$$
\det(J^TJ)
=|\mathbf r_u|^2|\mathbf r_v|^2-(\mathbf r_u\cdot\mathbf r_v)^2.
$$

而这正好等于

$$
|\mathbf r_u\times\mathbf r_v|^2.
$$

因此

$$
\sqrt{\det(J^TJ)}=|\mathbf r_u\times\mathbf r_v|.
$$

---

## 3. 第一型曲面积分用面积大小

第一型曲面积分是

$$
\iint_S f(x,y,z)\,dS.
$$

代入参数化后：

$$
\boxed{
\iint_S f\,dS
=\iint_D f(\mathbf r(u,v))|\mathbf r_u\times\mathbf r_v|\,du\,dv.
}
$$

这里用的是面积大小，所以取模：

$$
|\mathbf r_u\times\mathbf r_v|.
$$

---

## 4. 第二型曲面积分用有向面积向量

第二型曲面积分是通量：

$$
\iint_S\mathbf F\cdot\mathbf n\,dS.
$$

它需要方向，所以不用取模，而是用有向面积向量：

$$
\mathbf n\,dS=\mathbf r_u\times\mathbf r_v\,du\,dv.
$$

于是

$$
\boxed{
\iint_S\mathbf F\cdot\mathbf n\,dS
=\iint_D\mathbf F(\mathbf r(u,v))\cdot(\mathbf r_u\times\mathbf r_v)\,du\,dv.
}
$$

如果叉乘方向和题目要求相反，就整体加负号，或者交换参数顺序：

$$
\mathbf r_v\times\mathbf r_u=-\mathbf r_u\times\mathbf r_v.
$$

---

## 5. \((dy\,dz,dz\,dx,dx\,dy)\) 就是叉乘的三个余子式

展开

$$
\mathbf r_u\times\mathbf r_v
$$

得到

$$
\mathbf r_u\times\mathbf r_v
=\left(
{\partial(y,z)\over\partial(u,v)},
{\partial(z,x)\over\partial(u,v)},
{\partial(x,y)\over\partial(u,v)}
\right).
$$

所以

$$
\mathbf r_u\times\mathbf r_v\,du\,dv
=(dy\,dz,dz\,dx,dx\,dy).
$$

这说明第二型曲面积分中的

$$
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

本质就是

$$
(P,Q,R)\cdot(\mathbf r_u\times\mathbf r_v)du\,dv.
$$

---

## 6. 和普通换元 Jacobian 的关系

普通二重积分换元是

$$
(u,v)\mapsto(x,y),
$$

这是

$$
\mathbb R^2\to\mathbb R^2.
$$

Jacobian 矩阵是 $2\times2$ 方阵，所以面积缩放是

$$
\left|{\partial(x,y)\over\partial(u,v)}\right|.
$$

曲面参数化是

$$
(u,v)\mapsto(x,y,z),
$$

这是

$$
\mathbb R^2\to\mathbb R^3.
$$

Jacobian 矩阵是 $3\times2$ 长方形矩阵，面积缩放就变成

$$
\sqrt{\det(J^TJ)}
$$

或者在三维中写成

$$
|\mathbf r_u\times\mathbf r_v|.
$$

---

## 7. 更高维的一般规律

若

$$
\Phi:\mathbb R^k\to\mathbb R^n,
\qquad k\le n,
$$

它的 Jacobian 矩阵是

$$
J\in\mathbb R^{n\times k}.
$$

那么 $k$ 维体积元的缩放因子是

$$
\boxed{
\sqrt{\det(J^TJ)}.
}
$$

这叫 Gram 行列式。

三维曲面积分中的叉乘公式只是 $k=2,n=3$ 的特殊情况。

---

## 8. 一句话总结

$$
\boxed{
\mathbb R^2\to\mathbb R^3\text{ 的 Jacobian 是 }3\times2\text{ 矩阵；曲面面积缩放用 }|\mathbf r_u\times\mathbf r_v|=\sqrt{\det(J^TJ)}.
}
$$

第一型曲面积分用这个长度；第二型曲面积分用带方向的叉乘向量。
