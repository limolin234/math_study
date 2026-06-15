# tmp.md 归档：微分形式、方向、Green/Stokes/Gauss 与曲面 Jacobian（2026-06-10）

本文件由 `tmp.md` 中关于微分元方向、外微分、Green/Stokes/Gauss、旋度散度、投影面积和二维参数到三维曲面 Jacobian 的讨论整理归档而来。归档后 `tmp.md` 已清空。

---

# 二维到三维的 Jacobian 与曲面积分面积元

## 1. Jacobian 矩阵可以是二维到三维的吗

可以。

如果有参数化曲面：

$$
\mathbf r(u,v)=(x(u,v),y(u,v),z(u,v)),
$$

这就是一个从二维参数平面到三维空间的映射：

$$
(u,v)\mapsto (x,y,z).
$$

它的 Jacobian 矩阵不是方阵，而是 $3	imes 2$ 矩阵：

$$
J=rac{\partial(x,y,z)}{\partial(u,v)}
=
egin{pmatrix}
 x_u & x_v\
 y_u & y_v\
 z_u & z_v
\end{pmatrix}.
$$

这个矩阵的两列正是曲面上的两个切向量：

$$
\mathbf r_u=(x_u,y_u,z_u),
\qquad
\mathbf r_v=(x_v,y_v,z_v).
$$

所以二维到三维的 Jacobian 存在，只是它不是行列式形式的面积缩放因子，因为它不是方阵。

---

## 2. 面积元为什么要叉乘

在普通二重积分换元中，映射是

$$
(u,v)\mapsto (x,y),
$$

Jacobian 是 $2	imes2$ 方阵，面积缩放因子是

$$
\left|rac{\partial(x,y)}{\partial(u,v)}
ight|.
$$

但曲面参数化是

$$
(u,v)\mapsto (x,y,z),
$$

Jacobian 是 $3	imes2$，不能直接取普通行列式。

此时一个小矩形

$$
du\,dv
$$

在三维空间中被映到由

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
|\mathbf r_u	imes\mathbf r_v|\,du\,dv.
$$

因此第一型曲面积分面积元为

$$
oxed{
dS=|\mathbf r_u	imes\mathbf r_v|\,du\,dv.
}
$$

如果要有方向，则用有向面积元：

$$
oxed{
\mathbf n\,dS=\mathbf r_u	imes\mathbf r_v\,du\,dv.
}
$$

---

## 3. 这和非方阵 Jacobian 的关系

虽然 $3	imes2$ Jacobian 不能取普通行列式，但面积缩放因子可以用 Gram 行列式表示。

令

$$
J=(\mathbf r_u\ \mathbf r_v),
$$

这是 $3	imes2$ 矩阵。

那么

$$
J^TJ
=
egin{pmatrix}
\mathbf r_u\cdot\mathbf r_u & \mathbf r_u\cdot\mathbf r_v\
\mathbf r_v\cdot\mathbf r_u & \mathbf r_v\cdot\mathbf r_v
\end{pmatrix}.
$$

面积缩放因子是

$$
oxed{
\sqrt{\det(J^TJ)}.
}
$$

在三维中有恒等式：

$$
\sqrt{\det(J^TJ)}=|\mathbf r_u	imes\mathbf r_v|.
$$

所以叉乘公式本质上就是非方阵 Jacobian 的面积缩放公式。

---

## 4. 第二型曲面积分为什么用叉乘向量

第二型曲面积分是通量积分：

$$
\iint_S \mathbf F\cdot\mathbf n\,dS.
$$

代入有向面积元：

$$
\mathbf n\,dS=\mathbf r_u	imes\mathbf r_v\,du\,dv.
$$

得到

$$
oxed{
\iint_S \mathbf F\cdot\mathbf n\,dS
=\iint_D \mathbf F(\mathbf r(u,v))\cdot(\mathbf r_u	imes\mathbf r_v)\,du\,dv.
}
$$

这就是参数化计算第二型曲面积分的基本公式。

---

## 5. 和 \(dy\,dz,dz\,dx,dx\,dy\) 的关系

展开叉乘：

$$
\mathbf r_u	imes\mathbf r_v
=
\left(
{\partial(y,z)\over\partial(u,v)},
{\partial(z,x)\over\partial(u,v)},
{\partial(x,y)\over\partial(u,v)}

ight).
$$

所以

$$
\mathbf r_u	imes\mathbf r_v\,du\,dv
=(dy\,dz,dz\,dx,dx\,dy).
$$

因此

$$
P\,dy\,dz+Q\,dz\,dx+R\,dx\,dy
$$

就是

$$
(P,Q,R)\cdot(\mathbf r_u	imes\mathbf r_v)\,du\,dv.
$$

---

## 6. 方向怎么决定

方向由参数顺序决定。

如果使用

$$
(u,v),
$$

则有向面积元是

$$
\mathbf r_u	imes\mathbf r_v\,du\,dv.
$$

如果换成

$$
(v,u),
$$

则变成

$$
\mathbf r_v	imes\mathbf r_u\,dv\,du
=-\mathbf r_u	imes\mathbf r_v\,du\,dv.
$$

方向反过来。

因此：

- 第一型曲面积分只用面积大小 $dS$，方向无关；
- 第二型曲面积分用 $\mathbf n dS$，方向会影响正负。

如果题目指定外侧、上侧、下侧，就要检查

$$
\mathbf r_u	imes\mathbf r_v
$$

是否符合方向；不符合就取负号。

---

## 7. 一句话总结

二维到三维的 Jacobian 是 $3	imes2$ 矩阵。

它的两列是曲面两个切向量。

面积缩放不是普通行列式，而是

$$
oxed{|\mathbf r_u	imes\mathbf r_v|}
$$

或等价地

$$
oxed{\sqrt{\det(J^TJ)}}.
$$

第二型曲面积分要保留方向，所以使用

$$
oxed{\mathbf r_u	imes\mathbf r_v\,du\,dv}
$$

作为有向面积元。
