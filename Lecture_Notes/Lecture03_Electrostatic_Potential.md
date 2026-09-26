# Lecture 3 学习记录：Electrostatic Potential

> 状态：✅ 主线已完成到作业可用水平；正在通过 Exercise 2 补充从电势求电场所需的偏导 / gradient 操作。

## 1. Work 与 line integral

电荷 $q$ 在电场中受到：

```math
\vec F=q\vec E
```

沿一小段位移 $d\vec l$ 运动时，电场力做功：

```math
dW=\vec F\cdot d\vec l
```

因此从 $A$ 到 $B$：

```math
W_{A\to B}
=
\int_A^B\vec F\cdot d\vec l
=
q\int_A^B\vec E\cdot d\vec l
```

其中 $d\vec l$ 的方向定义为粒子的实际运动方向。

## 2. 静电场是 conservative field

静电力做功只取决于起点和终点，与具体路径无关。

因此闭合路径满足：

```math
\boxed{
\oint \vec E\cdot d\vec l=0
}
```

这里 $\oint$ 表示闭合积分；由于微元是 $d\vec l$，所以这是闭合曲线积分。

## 3. Electric Potential Energy

势能变化与电场力做功关系：

```math
\boxed{
\Delta U=U_B-U_A=-W_{A\to B}
}
```

所以：

```math
U_B-U_A
=
-q\int_A^B\vec E\cdot d\vec l
```

## 4. Electric Potential

电势定义为单位电荷的电势能：

```math
\boxed{
V=\frac{U}{q}
}
```

因此：

```math
\boxed{
V_B-V_A
=
-\int_A^B\vec E\cdot d\vec l
}
```

$V$ 是标量，没有方向。

对有限电荷系统通常取：

```math
V(\infty)=0
```

## 5. 点电荷的电势

对点电荷 $Q$：

```math
\vec E
=
\frac{1}{4\pi\varepsilon_0}
\frac{Q}{r^2}\hat r
```

其中 $\hat r$ 从源电荷指向观察点。

取从无穷远到 $r$ 的径向路径：

```math
V(r)
=
-\int_\infty^r\vec E\cdot d\vec l
```

得到：

```math
\boxed{
V(r)
=
\frac{1}{4\pi\varepsilon_0}
\frac{Q}{r}
}
```

所以点电荷满足 $E\sim1/r^2$，而 $V\sim1/r$。

## 6. 多个点电荷的电势

因为电势是标量，可以直接代数相加：

```math
\boxed{
V(P)
=
\frac{1}{4\pi\varepsilon_0}
\sum_i\frac{q_i}{r_i}
}
```

其中 $r_i$ 是第 $i$ 个电荷到观察点 $P$ 的距离，没有方向。

## 7. Electric Dipole 的远场电势

偶极矩：

```math
\boxed{
\vec p=q\vec d
}
```

方向：$\vec d$ 与 $\vec p$ 都从 $-q$ 指向 $+q$。

定义：

- $\vec r$：从 dipole 中点指向观察点；
- $r=|\vec r|$：距离；
- $\hat r=\vec r/r$：对应方向；
- $\theta$：$\vec p$ 与 $\vec r$ 的夹角。

远场 $r\gg d$ 时：

```math
r_+
\approx
r-\frac d2\cos\theta
```

```math
r_-
\approx
r+\frac d2\cos\theta
```

这是由几何关系结合一阶 binomial approximation 得到的。

于是：

```math
\boxed{
V_{\rm dipole}
=
\frac{1}{4\pi\varepsilon_0}
\frac{p\cos\theta}{r^2}
}
```

也可写成：

```math
\boxed{
V_{\rm dipole}
=
\frac{1}{4\pi\varepsilon_0}
\frac{\vec p\cdot\hat r}{r^2}
}
```

中垂面上 $\theta=\pi/2$，因此 $V=0$，但 $\vec E$ 一般不为 0。

## 8. Equipotential Surface

等势面定义：

```math
V=\text{constant}
```

沿等势面移动：

```math
\Delta V=0
```

由

```math
\Delta V
=
-\int\vec E\cdot d\vec l
```

可知电场必须垂直于等势面：

```math
\boxed{
\vec E\perp\text{equipotential surface}
}
```

并且：

```math
\boxed{
\text{沿 }\vec E\text{ 方向，}V\text{ 降低}
}
```

## 9. 均匀电场中的电势差

若 $\vec E$ 为常量：

```math
\boxed{
\Delta V
=
-\vec E\cdot\Delta\vec r
}
```

若位移沿电场方向、距离为 $d$：

```math
\boxed{
\Delta V=-Ed
}
```

## 10. 电势与电势能

```math
\boxed{
U=qV
}
```

所以：

```math
\boxed{
\Delta U=q\Delta V
}
```

$V$ 是空间中由源电荷决定的标量场；$U$ 还取决于放入其中的电荷 $q$。

## 11. 多点电荷系统的静电势能

两个点电荷：

```math
\boxed{
U=
\frac{1}{4\pi\varepsilon_0}
\frac{q_1q_2}{r_{12}}
}
```

$N$ 个点电荷：

```math
U
=
\frac{1}{4\pi\varepsilon_0}
\sum_{i=1}^{N}
\sum_{j=i+1}^{N}
\frac{q_iq_j}{r_{ij}}
```

这里用双重求和避免在 GitHub 数学渲染中直接写带有小于号的下标条件。含义仍然是：每一对不同电荷只计算一次。

运动题可结合机械能守恒：

```math
\boxed{
K_i+U_i=K_f+U_f
}
```

## 12. 积分符号辨认

积分符号本身表示累加，真正决定积分对象的是微元：

- $d\vec l$：曲线积分；
- $d\vec A$：曲面积分；
- $dV$：体积分。

小圆圈 $\oint$ 只表示积分对象是闭合的。

## 13. 当前边界

Chapter 3 的 Section 3.3 给出：

```math
\vec E=-\nabla V
```

但课程材料说明 $\nabla$ 这个向量微分算符将在 Chapter 4 系统介绍。

因此目前先通过 Chapter 3 Exercise 2 学会必要的偏导与从 $V(x,y,z)$ 求 $\vec E$ 的操作；更系统的 gradient 理论仍留到 Chapter 4。


## 14. Chap03 Exercise 4：厚球壳题的经典易错点

题型：内半径为 $R_1$、外半径为 $R_2$ 的均匀带电厚球壳，体电荷密度为 $\rho$，求 $V(r)$。

### 易错 1：把 Gauss 定律理解成“直接给出电场”

Gauss 定律直接给出的是电通量：

```math
\oint \vec E\cdot d\vec A
=
\frac{Q_{\rm enc}}{\varepsilon_0}
```

只有在球对称等高对称情形下，才能进一步写成：

```math
E(4\pi r^2)
=
\frac{Q_{\rm enc}}{\varepsilon_0}
```

再由此解出 $E(r)$。

因此逻辑应记为：

```text
Gauss law
→ flux
→ 利用对称性把积分化成 E × 面积
→ 解出 E
```

### 易错 2：把电势积分上下限写反

一般公式：

```math
V(B)-V(A)
=
-\int_A^B\vec E\cdot d\vec l
```

若取：

```math
V(\infty)=0
```

则：

```math
V(r)
=
-\int_\infty^r\vec E\cdot d\vec l
```

也可以等价地写为：

```math
V(r)
=
\int_r^\infty\vec E\cdot d\vec l
```

两者完全等价；交换积分上下限时要同时改变符号。

### 易错 3：把 $Q_{\rm enc}=0$ 直接推出 $E=0$

一般而言：

```math
Q_{\rm enc}=0
```

只能推出：

```math
\oint \vec E\cdot d\vec A=0
```

并不能一般性推出：

```math
\vec E=0
```

在本题空腔区域 $r<R_1$ 中之所以能推出 $E=0$，关键还需要球对称性。

对于与球壳同心、半径为 $r$ 的 Gaussian sphere：

- 球面上 $E$ 大小相同；
- $\vec E$ 沿径向；
- $d\vec A$ 也沿径向。

因此：

```math
\oint \vec E\cdot d\vec A
=
E4\pi r^2
```

又因为 $Q_{\rm enc}=0$：

```math
E4\pi r^2=0
```

所以：

```math
\boxed{E=0}
```

### 易错 4：误以为只有球心 $r=0$ 才能用对称性

本题不是只有球心处 $E=0$。

只要：

```math
r<R_1
```

并且电荷分布保持球对称，就可以选一个与球壳同心的 Gaussian sphere。

由于整个电荷分布在任意转动下都不变，高斯球面上所有位置必须等价，因此 $E$ 在该球面上大小相同并沿径向。

所以空腔内任意位置对应的半径 $r<R_1$ 都有：

```math
\boxed{E(r)=0}
```

### 易错 5：误以为“外部电荷对空腔内部没有作用”

更准确的说法不是“外部电荷没有作用”，而是：

> 均匀球对称壳层各部分在空腔内部产生的电场矢量彼此完全抵消。

单个电荷元当然会对空腔内一点产生电场；只是所有电荷元的矢量和为 0。

### 易错 6：把“不均匀球壳”也套用成内部 $E=0$

如果球壳的电荷分布不再球对称，即使对空腔内某个同心 Gaussian sphere 仍有：

```math
Q_{\rm enc}=0
```

也只能得到：

```math
\oint \vec E\cdot d\vec A=0
```

此时不能把积分化为 $E4\pi r^2$，因为球面上不同位置的 $E$ 可能大小和方向都不同。

因此一般有：

```math
\boxed{
\text{不均匀球壳内部通常 }\vec E\neq0
}
```

### 易错 7：把 $E=0$ 误认为 $V=0$

在空腔内：

```math
\vec E=0
```

结合：

```math
\vec E=-\nabla V
```

说明：

```math
\nabla V=0
```

因此结论是：

```math
\boxed{
V=\text{constant}
}
```

而不是 $V=0$。

这个常数由边界连续性决定：

```math
V(r<R_1)=V(R_1)
```

### 一句话复盘

这道题最容易混淆的逻辑链是：

```text
Q_enc = 0
≠> E = 0

Q_enc = 0
+ 球对称
=> E = 0
=> V = constant
```
