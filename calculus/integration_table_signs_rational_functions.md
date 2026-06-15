# 积分表、正负号与有理函数积分

## 多项式都能分解，是否意味着都能分成二次去求解？

### 1. 先区分两个层次

“能分解”和“能显式求根”不是一回事。

在复数范围内，代数基本定理说：

\[
P(x)=a_n\prod_{k=1}^n (x-r_k)
\]

也就是说，每个非零复系数多项式都可以分解成一次因子的乘积。

如果多项式有实系数，那么非实复根一定成共轭对出现：

\[
r=\alpha+i\beta,
\qquad
\bar r=\alpha-i\beta.
\]

这两个一次因子相乘：

\[
(x-r)(x-\bar r)
=
(x-\alpha-i\beta)(x-\alpha+i\beta)
=(x-\alpha)^2+\beta^2.
\]

这是一个实系数不可约二次因子。

所以在实数范围内：

\[
P(x)=a_n
\prod_i (x-a_i)^{m_i}
\prod_j (x^2+p_jx+q_j)^{n_j},
\]

其中每个二次因子满足：

\[
p_j^2-4q_j<0.
\]

这句话的意思是：

\[
\boxed{\text{实系数多项式在理论上都能分解成一次因子和不可约二次因子。}}
\]

---

### 2. 但这不等于都能用二次公式求出来

因为要写出这些因子，需要先知道根。

例如五次方程：

\[
x^5-x+1=0.
\]

它当然在复数范围内有五个复根，因此理论上可以写成：

\[
x^5-x+1=\prod_{k=1}^5 (x-r_k).
\]

如果根里有复共轭对，也能合成实二次因子。

但是问题是：

\[
\boxed{\text{一般五次及以上方程没有用根式表达根的通用公式。}}
\]

也就是说：

- 存在分解；
- 但不一定能用有限次加减乘除和开方写出分解；
- 实际积分时不一定能手算出漂亮的部分分式。

---

### 3. 积分课里的“分解分母”是什么意思

有理函数积分理论说：

\[
\int \frac{P(x)}{Q(x)}\,dx
\]

只要能把 \(Q(x)\) 分解成一次因子和不可约二次因子，就可以做部分分式。

也就是说，算法结构是：

\[
\boxed{
\text{分母分解} \rightarrow \text{部分分式} \rightarrow \ln,\arctan,\text{有理项}
}
\]

但如果 \(Q(x)\) 很高次、根很难求，那么“分母分解”本身可能不容易。

所以积分表/教材常用的例子通常是已经能看出分解的：

\[
x^2-1=(x-1)(x+1)
\]

\[
x^3-x=x(x-1)(x+1)
\]

\[
x^4+1=(x^2+\sqrt2x+1)(x^2-\sqrt2x+1)
\]

---

### 4. 为什么实数范围最多只需要二次因子

这是因为复根共轭成对。

如果 \(a+bi\) 是实系数多项式的根，那么 \(a-bi\) 也是根。

二者合并：

\[
(x-(a+bi))(x-(a-bi))
=(x-a)^2+b^2.
\]

展开：

\[
(x-a)^2+b^2=x^2-2ax+a^2+b^2.
\]

这是实系数二次式，而且判别式为：

\[
\Delta=(-2a)^2-4(a^2+b^2)
=4a^2-4a^2-4b^2
=-4b^2<0.
\]

所以它不能再在实数范围内分解成一次因子。

因此：

\[
\boxed{
\text{复数范围：全是一阶因子；实数范围：一阶因子 + 不可约二阶因子。}
}
\]

---

### 5. 这对有理函数积分意味着什么

一次因子：

\[
\frac{A}{x-a}
\]

积分给：

\[
A\ln|x-a|.
\]

重一次因子：

\[
\frac{A_k}{(x-a)^k}
\]

若 \(k=1\)，给 \(\ln\)。

若 \(k>1\)，给有理函数项：

\[
\int\frac{dx}{(x-a)^k}
=-\frac{1}{(k-1)(x-a)^{k-1}}+C.
\]

不可约二次因子：

\[
\frac{Bx+C}{x^2+px+q}.
\]

先把分子拆成：

\[
Bx+C=\lambda(2x+p)+\mu.
\]

于是：

\[
\int\frac{Bx+C}{x^2+px+q}\,dx
=\lambda\ln(x^2+px+q)
+
\mu\int\frac{dx}{x^2+px+q}.
\]

如果二次因子不可约：

\[
p^2-4q<0.
\]

配方后：

\[
x^2+px+q=
\left(x+\frac p2\right)^2+
\left(q-\frac{p^2}{4}\right).
\]

这是平方和，所以给 \(\arctan\)。

因此有理函数积分最终只会出现：

\[
\boxed{
\text{多项式项} + \text{有理项} + \ln + \arctan
}
\]

前提是我们已经完成实因式分解。

---

### 6. 一句话总结

“任何实系数多项式都能分解成一次和不可约二次”是理论结构。

但“实际能不能手算出这个分解”是计算问题。

所以不是说高次方程都能用二次公式求解，而是说：

\[
\boxed{
\text{只要分解已经拿到，有理函数积分就只需要处理一次因子和二次因子。}
}
\]

---

## 积分表整理：正负号问题与三角/双曲函数的关系

### 1. 正负号最容易出错的地方

积分表里的正负号主要来自三类来源：

1. 原函数求导时本身带不带负号。
2. 换元时 \(du\) 是否带负号。
3. 平方恒等式是加号型还是减号型。

最重要的对比是：

\[
(\sin x)'=\cos x,
\qquad
(\cos x)'=-\sin x.
\]

而双曲函数是：

\[
(\sinh x)'=\cosh x,
\qquad
(\cosh x)'=\sinh x.
\]

普通余弦求导有负号，但双曲余弦求导没有负号。

这一个差别会影响很多积分表的符号。

---

### 2. 三角函数的基本积分与正负号

因为：

\[
(\cos x)'=-\sin x,
\]

所以：

\[
\boxed{
\int \sin x\,dx=-\cos x+C
}
\]

这里的负号来自 \(\cos x\) 求导。

因为：

\[
(\sin x)'=\cos x,
\]

所以：

\[
\boxed{
\int \cos x\,dx=\sin x+C
}
\]

没有负号。

---

### 3. 双曲函数的基本积分与正负号

因为：

\[
(\cosh x)'=\sinh x,
\]

所以：

\[
\boxed{
\int \sinh x\,dx=\cosh x+C
}
\]

没有负号。

因为：

\[
(\sinh x)'=\cosh x,
\]

所以：

\[
\boxed{
\int \cosh x\,dx=\sinh x+C
}
\]

也没有负号。

这和普通三角函数不同：

\[
\int \sin x\,dx=-\cos x+C,
\qquad
\int \sinh x\,dx=\cosh x+C.
\]

原因是：

\[
\cos x=\frac{e^{ix}+e^{-ix}}2,
\qquad
\cosh x=\frac{e^x+e^{-x}}2.
\]

三角函数里有 \(i^2=-1\)，所以二阶求导会产生负号：

\[
(\sin x)''=-\sin x.
\]

双曲函数没有这个虚数旋转，二阶求导回到正号：

\[
(\sinh x)''=\sinh x.
\]

---

### 4. tan 和 cot 的积分：负号来自换元

先看：

\[
\tan x=\frac{\sin x}{\cos x}.
\]

积分：

\[
\int \tan x\,dx
=\int \frac{\sin x}{\cos x}\,dx.
\]

令：

\[
u=\cos x.
\]

则：

\[
du=-\sin x\,dx.
\]

所以：

\[
\sin x\,dx=-du.
\]

因此：

\[
\int \frac{\sin x}{\cos x}\,dx
=-\int\frac{du}{u}
=-\ln|u|+C.
\]

代回：

\[
\boxed{
\int \tan x\,dx=-\ln|\cos x|+C
}
\]

也可以写成：

\[
\boxed{
\int \tan x\,dx=\ln|\sec x|+C
}
\]

因为：

\[
-\ln|\cos x|=\ln\left|\frac1{\cos x}\right|=\ln|\sec x|.
\]

负号不是凭空来的，而是来自：

\[
d(\cos x)=-\sin x\,dx.
\]

再看：

\[
\cot x=\frac{\cos x}{\sin x}.
\]

令：

\[
u=\sin x.
\]

则：

\[
du=\cos x\,dx.
\]

所以：

\[
\int \cot x\,dx
=\int\frac{du}{u}
=\ln|u|+C.
\]

即：

\[
\boxed{
\int \cot x\,dx=\ln|\sin x|+C
}
\]

这里没有负号，因为 \(d(\sin x)=\cos x\,dx\)。

---

### 5. tanh 和 coth 的积分：和三角函数对比

双曲正切：

\[
\tanh x=\frac{\sinh x}{\cosh x}.
\]

令：

\[
u=\cosh x.
\]

则：

\[
du=\sinh x\,dx.
\]

所以：

\[
\int \tanh x\,dx
=\int\frac{\sinh x}{\cosh x}\,dx
=\int\frac{du}{u}
=\ln|u|+C.
\]

因此：

\[
\boxed{
\int \tanh x\,dx=\ln\cosh x+C
}
\]

这里没有负号，因为 \((\cosh x)'=\sinh x\)。

对比：

\[
\int \tan x\,dx=-\ln|\cos x|+C,
\]

\[
\int \tanh x\,dx=\ln\cosh x+C.
\]

差别来自：

\[
(\cos x)'=-\sin x,
\qquad
(\cosh x)'=\sinh x.
\]

双曲余切：

\[
\coth x=\frac{\cosh x}{\sinh x}.
\]

令：

\[
u=\sinh x.
\]

则：

\[
du=\cosh x\,dx.
\]

所以：

\[
\boxed{
\int \coth x\,dx=\ln|\sinh x|+C
}
\]

---

### 6. sec、csc 与 sech、csch 的导数符号

普通三角函数：

\[
\sec x=\frac1{\cos x}.
\]

求导：

\[
(\sec x)'
=-\frac{(\cos x)'}{\cos^2x}
=-\frac{-\sin x}{\cos^2x}
=\frac{\sin x}{\cos^2x}
=\sec x\tan x.
\]

所以：

\[
\boxed{
\int \sec x\tan x\,dx=\sec x+C
}
\]

而：

\[
\csc x=\frac1{\sin x}.
\]

求导：

\[
(\csc x)'
=-\frac{(\sin x)'}{\sin^2x}
=-\frac{\cos x}{\sin^2x}
=-\csc x\cot x.
\]

所以：

\[
\boxed{
\int \csc x\cot x\,dx=-\csc x+C
}
\]

双曲函数对应：

\[
\operatorname{sech}x=\frac1{\cosh x}.
\]

求导：

\[
(\operatorname{sech}x)'
=-\frac{(\cosh x)'}{\cosh^2x}
=-\frac{\sinh x}{\cosh^2x}
=-\operatorname{sech}x\tanh x.
\]

所以：

\[
\boxed{
\int \operatorname{sech}x\tanh x\,dx=-\operatorname{sech}x+C
}
\]

而：

\[
\operatorname{csch}x=\frac1{\sinh x}.
\]

求导：

\[
(\operatorname{csch}x)'
=-\frac{(\sinh x)'}{\sinh^2x}
=-\frac{\cosh x}{\sinh^2x}
=-\operatorname{csch}x\coth x.
\]

所以：

\[
\boxed{
\int \operatorname{csch}x\coth x\,dx=-\operatorname{csch}x+C
}
\]

注意对比：

\[
(\sec x)'=+\sec x\tan x,
\]

\[
(\operatorname{sech}x)'=-\operatorname{sech}x\tanh x.
\]

这里符号相反，根源仍然是：

\[
(\cos x)'=-\sin x,
\qquad
(\cosh x)'=+\sinh x.
\]

---

### 7. 反三角函数积分表的正负号

#### 7.1 arcsin 和 arccos

由：

\[
y=\arcsin x
\]

得：

\[
\sin y=x.
\]

求导：

\[
\cos y\cdot y'=1.
\]

所以：

\[
y'=\frac1{\cos y}=\frac1{\sqrt{1-x^2}}.
\]

因此：

\[
\boxed{
(\arcsin x)'=\frac1{\sqrt{1-x^2}}
}
\]

而：

\[
y=\arccos x
\]

得：

\[
\cos y=x.
\]

求导：

\[
-\sin y\cdot y'=1.
\]

所以：

\[
y'=-\frac1{\sin y}=-\frac1{\sqrt{1-x^2}}.
\]

因此：

\[
\boxed{
(\arccos x)'=-\frac1{\sqrt{1-x^2}}
}
\]

所以同一个被积函数有两种写法：

\[
\int\frac{dx}{\sqrt{1-x^2}}
=\arcsin x+C
\]

也可以写成：

\[
\int\frac{dx}{\sqrt{1-x^2}}
=-\arccos x+C.
\]

因为：

\[
\arcsin x+\arccos x=\frac\pi2.
\]

二者只差一个常数。

---

#### 7.2 arctan 和 arccot

由：

\[
(\arctan x)'=\frac1{1+x^2}.
\]

所以：

\[
\boxed{
\int\frac{dx}{1+x^2}=\arctan x+C
}
\]

若用 \(\operatorname{arccot}x\)，常见约定下：

\[
(\operatorname{arccot}x)'=-\frac1{1+x^2}.
\]

因此：

\[
\int\frac{dx}{1+x^2}=-\operatorname{arccot}x+C.
\]

正负号来自反函数选的是 \(\tan\) 还是 \(\cot\)。

---

### 8. 反双曲函数积分表的正负号

#### 8.1 arsinh

由：

\[
y=\operatorname{arsinh}x
\]

得：

\[
\sinh y=x.
\]

求导：

\[
\cosh y\cdot y'=1.
\]

所以：

\[
y'=\frac1{\cosh y}.
\]

由于：

\[
\cosh^2y-\sinh^2y=1,
\]

得到：

\[
\cosh y=\sqrt{1+x^2}.
\]

所以：

\[
\boxed{
(\operatorname{arsinh}x)'=\frac1{\sqrt{1+x^2}}
}
\]

因此：

\[
\boxed{
\int\frac{dx}{\sqrt{1+x^2}}
=\operatorname{arsinh}x+C
}
\]

没有负号。

---

#### 8.2 arcosh

由：

\[
y=\operatorname{arcosh}x
\]

得：

\[
\cosh y=x.
\]

求导：

\[
\sinh y\cdot y'=1.
\]

所以：

\[
y'=\frac1{\sinh y}.
\]

由于：

\[
\sinh y=\sqrt{x^2-1},
\qquad y\ge0,
\]

所以：

\[
\boxed{
(\operatorname{arcosh}x)'=\frac1{\sqrt{x^2-1}}
}
\]

因此：

\[
\boxed{
\int\frac{dx}{\sqrt{x^2-1}}
=\operatorname{arcosh}x+C
}
\]

也没有负号。

---

#### 8.3 artanh

由：

\[
\operatorname{artanh}x=rac12\ln\frac{1+x}{1-x}
\]

可得：

\[
(\operatorname{artanh}x)'=\frac1{1-x^2}.
\]

所以：

\[
\boxed{
\int\frac{dx}{1-x^2}=\operatorname{artanh}x+C
}
\]

这里是 \(1-x^2\)，不是 \(x^2-1\)。

因为：

\[
\frac1{x^2-1}=-\frac1{1-x^2}.
\]

所以：

\[
\int\frac{dx}{x^2-1}
=-\operatorname{artanh}x+C.
\]

在对数形式下：

\[
\operatorname{artanh}x=rac12\ln\left|\frac{1+x}{1-x}\right|.
\]

因此：

\[
-\operatorname{artanh}x
=\frac12\ln\left|\frac{1-x}{1+x}\right|.
\]

而部分分式常给：

\[
\int\frac{dx}{x^2-1}
=\frac12\ln\left|\frac{x-1}{x+1}\right|+C.
\]

这和上式只差常数/绝对值内部的符号处理，本质一致。

---

### 9. 带参数的积分表与符号

#### 9.1 平方和

\[
\boxed{
\int\frac{dx}{x^2+a^2}
=\frac1a\arctan\frac{x}{a}+C
}
\]

检查：

\[
\frac{d}{dx}\left(\frac1a\arctan\frac{x}{a}\right)
=\frac1a\cdot\frac1{1+(x/a)^2}\cdot\frac1a.
\]

化简：

\[
\frac1{a^2}\cdot\frac{a^2}{a^2+x^2}
=\frac1{x^2+a^2}.
\]

这里没有负号。

---

#### 9.2 平方差：\(a^2-x^2\)

\[
\boxed{
\int\frac{dx}{a^2-x^2}
=\frac1a\operatorname{artanh}\frac{x}{a}+C
}
\]

检查：

\[
\frac{d}{dx}\left(\frac1a\operatorname{artanh}\frac{x}{a}\right)
=\frac1a\cdot\frac1{1-(x/a)^2}\cdot\frac1a.
\]

化简：

\[
\frac1{a^2}\cdot\frac{a^2}{a^2-x^2}
=\frac1{a^2-x^2}.
\]

没有负号，因为分母正好是 \(a^2-x^2\)。

---

#### 9.3 平方差：\(x^2-a^2\)

因为：

\[
x^2-a^2=-(a^2-x^2),
\]

所以：

\[
\frac1{x^2-a^2}=-\frac1{a^2-x^2}.
\]

因此：

\[
\int\frac{dx}{x^2-a^2}
=-\frac1a\operatorname{artanh}\frac{x}{a}+C.
\]

用对数写：

\[
\boxed{
\int\frac{dx}{x^2-a^2}
=\frac1{2a}\ln\left|\frac{x-a}{x+a}\right|+C
}
\]

这和 \(-\frac1a\operatorname{artanh}(x/a)\) 等价。

正负号的关键是：

\[
a^2-x^2
\quad\text{和}\quad
x^2-a^2
\]

差一个整体负号。

---

### 10. 根式积分表与符号

#### 10.1 圆型根式

\[
\boxed{
\int\frac{dx}{\sqrt{a^2-x^2}}
=\arcsin\frac{x}{a}+C
}
\]

也可以写成：

\[
-
\arccos\frac{x}{a}+C.
\]

因为 \(\arccos\) 的导数带负号。

---

#### 10.2 双曲正弦型根式

\[
\boxed{
\int\frac{dx}{\sqrt{x^2+a^2}}
=\operatorname{arsinh}\frac{x}{a}+C
}
\]

没有负号。

对数形式：

\[
\operatorname{arsinh}\frac{x}{a}
=\ln\left|x+\sqrt{x^2+a^2}\right|+C_a.
\]

其中 \(C_a\) 可吸收到积分常数里。

---

#### 10.3 双曲余弦型根式

\[
\boxed{
\int\frac{dx}{\sqrt{x^2-a^2}}
=\operatorname{arcosh}\frac{x}{a}+C
}
\]

对数形式：

\[
\operatorname{arcosh}\frac{x}{a}
=\ln\left|x+\sqrt{x^2-a^2}\right|+C_a.
\]

没有负号。

如果写成：

\[
\int\frac{dx}{\sqrt{a^2-x^2}},
\]

那是圆型，给 \(\arcsin\)。

如果写成：

\[
\int\frac{dx}{\sqrt{x^2-a^2}},
\]

那是双曲型，给 \(\operatorname{arcosh}\)。

两者不是只差一个负号，而是几何结构不同。

---

### 11. 对数积分表里的符号检查方法

凡是看到对数形式，最稳的方法是直接求导。

例如：

\[
F(x)=\frac1{2a}\ln\left|\frac{x-a}{x+a}\right|.
\]

展开：

\[
F(x)=\frac1{2a}\left(\ln|x-a|-\ln|x+a|\right).
\]

求导：

\[
F'(x)=\frac1{2a}\left(\frac1{x-a}-\frac1{x+a}\right).
\]

通分：

\[
F'(x)=\frac1{2a}\cdot\frac{(x+a)-(x-a)}{(x-a)(x+a)}.
\]

分子：

\[
(x+a)-(x-a)=2a.
\]

所以：

\[
F'(x)=\frac1{x^2-a^2}.
\]

因此这个符号是对的。

如果换成：

\[
G(x)=\frac1{2a}\ln\left|\frac{x+a}{x-a}\right|,
\]

那么：

\[
G'(x)=-\frac1{x^2-a^2}
=\frac1{a^2-x^2}.
\]

所以分子分母调换，会改变整体符号。

---

### 12. 最小符号记忆表

#### 12.1 三角 vs 双曲

\[
(\cos x)'=-\sin x,
\qquad
(\cosh x)'=+\sinh x.
\]

所以：

\[
\int\sin x\,dx=-\cos x+C,
\qquad
\int\sinh x\,dx=+\cosh x+C.
\]

\[
\int\tan x\,dx=-\ln|\cos x|+C,
\qquad
\int\tanh x\,dx=+\ln\cosh x+C.
\]

#### 12.2 反函数

\[
(\arcsin x)'=+\frac1{\sqrt{1-x^2}},
\qquad
(\arccos x)'=-\frac1{\sqrt{1-x^2}}.
\]

\[
(\arctan x)'=+\frac1{1+x^2}.
\]

\[
(\operatorname{arsinh}x)'=+\frac1{\sqrt{1+x^2}}.
\]

\[
(\operatorname{arcosh}x)'=+\frac1{\sqrt{x^2-1}}.
\]

\[
(\operatorname{artanh}x)'=+\frac1{1-x^2}.
\]

#### 12.3 平方差

\[
\int\frac{dx}{a^2-x^2}
=+\frac1a\operatorname{artanh}\frac{x}{a}+C.
\]

\[
\int\frac{dx}{x^2-a^2}
=-\frac1a\operatorname{artanh}\frac{x}{a}+C.
\]

或者：

\[
\int\frac{dx}{x^2-a^2}
=\frac1{2a}\ln\left|\frac{x-a}{x+a}\right|+C.
\]

---

### 13. 实用检查规则

遇到正负号不确定时：

1. 如果是三角函数，先检查 \((\cos x)'=-\sin x\)。
2. 如果是双曲函数，记住 \((\cosh x)'=+\sinh x\)。
3. 如果是 \(\tan\) 或 \(\tanh\)，看分母的导数是否带负号。
4. 如果是反函数积分，直接对候选原函数求导。
5. 如果是对数形式，先拆开对数，再求导通分。
6. 如果是 \(a^2-x^2\) 和 \(x^2-a^2\)，先看它们差一个整体负号。

最稳的原则：

\[
\boxed{
\text{不要背符号，直接对候选原函数求导检查。}
}
\]

---



## 双曲函数名称和读法

- `sinh` 是 `hyperbolic sine` 的缩写，读作 “shine” 或 “sinch”。数学课里更正式地读作 “hyperbolic sine”。
- `cosh` 是 `hyperbolic cosine` 的缩写，常读作 “cosh”，也可正式读作 “hyperbolic cosine”。
- `tanh` 是 `hyperbolic tangent` 的缩写，常读作 “tanch” 或 “tanh”，正式读作 “hyperbolic tangent”。
- `coth` 是 `hyperbolic cotangent` 的缩写，读作 “coth” 或正式读作 “hyperbolic cotangent”。
- `sech` 是 `hyperbolic secant` 的缩写，读作 “sech” 或正式读作 “hyperbolic secant”。
- `csch` 是 `hyperbolic cosecant` 的缩写，读作 “cosech” / “csch”，正式读作 “hyperbolic cosecant”。

反函数前面的 `ar` 或 `arc` 表示反函数：

- `arsinh` / `asinh`：inverse hyperbolic sine，反双曲正弦。
- `arcosh` / `acosh`：inverse hyperbolic cosine，反双曲余弦。
- `artanh` / `atanh`：inverse hyperbolic tangent，反双曲正切。

注意：不同教材写法不同。

常见写法：

- 欧洲/一些数学教材：`arsinh`, `arcosh`, `artanh`。
- 计算器/编程语言：`asinh`, `acosh`, `atanh`。
- 英文口语中也常说：inverse sinh, inverse cosh, inverse tanh。

---
