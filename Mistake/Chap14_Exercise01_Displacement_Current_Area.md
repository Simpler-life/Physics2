# Chapter 14 Exercise 1｜安培环路包围面积误判

> 状态：✅ 错误已定位，正确方法已讲解；**尚未独立重做验证**。  
> 来源：Chapter 14, Exercise 1（第 7 次作业）。  
> 关联：[Lecture 14](../Lecture_Notes/Lecture14_Maxwells_Equations_and_EM_Waves.md)。

## 1. 题目和错误

圆形平行板电容器的极板半径为 $a$，极板电荷随时间变化：

```math
q(t)=q_0\sin(\omega t)
```

忽略边缘场，求位移电流密度、总位移电流以及极板间距轴线 $r<a$ 处的磁场。

**本次实际错误：** 在求 $r<a$ 处的磁场时，误用整个极板面积 $\pi a^2$，而没有使用所选半径 $r$ 的安培环路包围面积 $\pi r^2$。

- $a$ 是**极板半径**，决定 $J_d$ 的大小。
- $r$ 是**磁场求值点距轴线的距离**，也是所选安培环路半径。
- $r<a$ 时，环路只圈住一部分位移电流。

## 2. 正确推导

极板面积 $A=\pi a^2$，因此：

```math
E(t)=\frac{q(t)}{\varepsilon_0\pi a^2}
```

位移电流密度：

```math
\boxed{
J_d=\varepsilon_0\frac{dE}{dt}
=\frac{q_0\omega}{\pi a^2}\cos(\omega t)
}
```

总位移电流：

```math
\boxed{I_d=J_d\pi a^2=q_0\omega\cos(\omega t)}
```

**磁场这一步必须重新选面积。** 对半径 $r<a$ 的同轴圆形环路，极板间的积分面只有位移电流，没有传导电流：

```math
I_{d,\mathrm{enc}}
=\int_{S_r}\vec J_d\cdot d\vec A
=J_d\pi r^2
=I_d\frac{r^2}{a^2}
```

安培–麦克斯韦定律：

```math
\oint_C\vec B\cdot d\vec l
=\mu_0 I_{c,\mathrm{enc}}+\mu_0 I_{d,\mathrm{enc}}
=\mu_0 I_{d,\mathrm{enc}}
```

由圆柱对称性：

```math
B_\phi(2\pi r)=\mu_0 J_d\pi r^2
```

得到：

```math
B_\phi(r,t)=\frac{\mu_0 q_0\omega r}{2\pi a^2}\cos(\omega t)
\qquad (0<r<a)
```

方向沿环向，由右手定则判断。

## 3. 这道题的关键辨析

- **总位移电流** $I_d=J_d\pi a^2$：积分区域是**整块极板**。
- **被环路包围的位移电流** $I_{d,\mathrm{enc}}=J_d\pi r^2$：积分区域是**环路所围圆面**。
- 之所以没有传导电流项，是因为这里选的积分面位于**极板间**；并不是位移电流消失。

## 4. 下一次遇到同类题的检查清单

1. 先画安培环路，半径是 $r$ 还是 $a$？
2. 明确积分面究竟覆盖哪个区域。
3. 写 $I_{\mathrm{enc}}=\int_S\vec J\cdot d\vec A$，再代面积。
4. 检查 $r\to0$ 时 $B\to0$；在 $r=a$ 时 $B(a)=\mu_0 I_d/(2\pi a)$。

**一句话复盘：** 电流密度乘的面积，永远是所选积分面实际覆盖的面积，不能直接套题目给出的总面积。

## 5. 复盘进度

- [x] 已发现误用 $\pi a^2$ 的错误。
- [x] 已通过讲解定位原因、获得正确推导。
- [ ] 待独立重做 $r<a$ 的磁场推导，确认真正掌握。
