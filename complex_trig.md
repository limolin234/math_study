# 复数输入下的三角函数

## 1. 问题

实数输入时，三角函数是熟悉的周期函数：

\[
\sin x,\quad \cos x
\]

如果输入纯虚数，例如 \( ix \)，会出现双曲函数：

\[
\sin(ix)=i\sinh x
\]

\[
\cos(ix)=\cosh x
\]

那么一般复数输入

\[
z=a+bi
\]

时会得到什么？

---

## 2. 用合角公式推导

令

\[
z=a+bi
\]

则

\[
\sin z=\sin(a+bi)
\]

用合角公式：

\[
\sin(a+bi)=\sin a\cos(bi)+\cos a\sin(bi)
\]

又因为

\[
\cos(bi)=\cosh b
\]

\[
\sin(bi)=i\sinh b
\]

所以

\[
\boxed{\sin(a+bi)=\sin a\cosh b+i\cos a\sinh b}
\]

也就是说：

\[
\operatorname{Re}(\sin(a+bi))=\sin a\cosh b
\]

\[
\operatorname{Im}(\sin(a+bi))=\cos a\sinh b
\]

---

## 3. 纯实数与纯虚数是特殊情况

### 纯实数输入

令 \( b=0 \)，有：

\[
\sin(a+0i)=\sin a\cosh 0+i\cos a\sinh 0
\]

因为

\[
\cosh 0=1,\quad \sinh 0=0
\]

所以

\[
\sin a
\]

这就是普通的实数三角函数。

### 纯虚数输入

令 \( a=0 \)，有：

\[
\sin(0+bi)=\sin 0\cosh b+i\cos 0\sinh b
\]

因此

\[
\boxed{\sin(bi)=i\sinh b}
\]

注意这里前面有一个 \( i \)。

---

## 4. 余弦函数

同理：

\[
\cos(a+bi)=\cos a\cos(bi)-\sin a\sin(bi)
\]

所以

\[
\boxed{\cos(a+bi)=\cos a\cosh b-i\sin a\sinh b}
\]

纯虚数输入时：

\[
\cos(bi)=\cosh b
\]

---

## 5. 用欧拉公式理解

复数三角函数可以用指数函数定义：

\[
\sin z=\frac{e^{iz}-e^{-iz}}{2i}
\]

\[
\cos z=\frac{e^{iz}+e^{-iz}}{2}
\]

如果

\[
z=a+bi
\]

那么

\[
e^{iz}=e^{i(a+bi)}=e^{-b}e^{ia}
\]

其中：

- \( e^{ia} \) 表示旋转；
- \( e^{-b} \) 表示指数缩放。

所以复数输入下的三角函数，本质上是：

> 实轴方向的周期振荡 + 虚轴方向的指数增长/衰减。

---

## 6. 直观总结

对于

\[
z=a+bi
\]

有：

\[
\sin(a+bi)=\sin a\cosh b+i\cos a\sinh b
\]

其中：

- \( a \) 控制普通三角函数部分；
- \( b \) 控制双曲函数部分；
- 一般结果是复数；
- 纯实数输入退化为普通 \( \sin x \)；
- 纯虚数输入变成 \( i\sinh x \)。
