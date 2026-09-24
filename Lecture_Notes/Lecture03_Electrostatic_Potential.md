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
\boxed{
U=
\frac{1}{4\pi\varepsilon_0}
\sum_{i<j}
\frac{q_iq_j}{r_{ij}}
}
```

每一对电荷只计算一次。

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
