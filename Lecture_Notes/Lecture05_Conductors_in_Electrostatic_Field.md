# Lecture 5 学习记录：Conductors in Electrostatic Field

> 状态：✅ 已完成当前主线内容到作业可用水平  
> 本 Lecture 核心：静电平衡导体、表面电荷、静电屏蔽、接地与 Method of Image Charges（镜像法）。

## 1. 静电平衡导体的核心性质

导体中存在可以自由移动的电荷载流子。若导体内部仍存在非零电场，自由电子就会继续受到电场力并移动，因此不可能处于静电平衡。

所以静电平衡时：

```math
\boxed{
\vec E_{\text{inside conductor}}=0
}
```

又因为：

```math
\vec E=-\nabla V
```

所以：

```math
\boxed{
V=\text{constant inside the conductor}
}
```

即整个导体是等势体。

注意：

- 等势不代表一定是 $V=0$；
- 只有在接地（grounded）时，通常取导体电势为 $V=0$。

## 2. 为什么导体内部没有净电荷

在导体材料内部任取一个闭合 Gaussian surface。

静电平衡时，该高斯面上处处有：

```math
\vec E=0
```

因此：

```math
\oint \vec E\cdot d\vec A=0
```

由 Gauss' law：

```math
\oint \vec E\cdot d\vec A
=
\frac{Q_{\rm enc}}{\varepsilon_0}
```

得到：

```math
\boxed{
Q_{\rm enc}=0
}
```

因此静电平衡时，导体材料内部没有净体电荷，多余净电荷位于导体表面。

### 我的问题：外面的电荷不是也会给这个高斯面贡献电场吗？

会。

高斯面上的总电场 $\vec E$ 包括内部电荷和外部电荷产生的所有电场。

但是 Gauss' law 的右边只取高斯面内部包住的净电荷：

```math
\boxed{
Q_{\rm enc}
}
```

高斯面外部的电荷虽然会改变高斯面上各点的局部电场，却对整个闭合面的**净通量**贡献为零。

直觉上：

> 外部电荷产生的电场线如果穿入闭合面，最终还必须从别处穿出，因此“进入”的负通量和“离开”的正通量相互抵消。

所以应区分：

```math
\boxed{
\text{外部电荷可以改变局部 }\vec E
}
```

但：

```math
\boxed{
\text{外部电荷对闭合面的净通量为 }0
}
```

## 3. 为什么静电平衡时表面电场一定垂直

外界原本施加到导体上的电场并不一定垂直于表面。

但是若导体表面还存在切向分量：

```math
E_{\parallel}\neq 0
```

那么表面自由电荷会受到切向电场力并继续沿表面移动，这与静电平衡矛盾。

因此静电平衡时必须：

```math
\boxed{
E_{\parallel}=0
}
```

于是导体表面外侧的总电场只能沿法向：

```math
\boxed{
\vec E_{\rm out}=E_{\perp}\hat n
}
```

这也与“导体表面是等势面”完全一致：电场总是垂直于等势面。

## 4. 表面电荷密度与外侧电场

在导体表面跨过边界取一个极薄的 Gaussian pillbox。

导体内部：

```math
\vec E_{\rm in}=0
```

导体外部电场垂直表面，所以侧面的通量为零，仅外侧端面有通量。

Gauss' law 给出：

```math
E_{\rm out}A
=
\frac{\sigma A}{\varepsilon_0}
```

因此：

```math
\boxed{
E_{\rm out}
=
\frac{\sigma}{\varepsilon_0}
}
```

方向沿导体表面法线。

这里的 $\vec E_{\rm out}$ 是**所有电荷共同产生的总电场**，不是只取导体自身表面电荷产生的那一部分。

## 5. Conductor with a Cavity：空腔与静电屏蔽

如果一个导体中存在完全封闭的空腔，且空腔内部没有额外电荷，那么导体材料内部仍满足：

```math
\vec E=0
```

在金属材料中、围绕空腔画 Gaussian surface，可知空腔内表面的净电荷为零。

结合导体内表面等势以及唯一性定理，可以进一步得到空腔内：

```math
\boxed{
\vec E_{\rm cavity}=0
}
```

因此外部静电场不能穿透一个完全封闭的导体空腔，这就是 electrostatic shielding（静电屏蔽）的基本思想。

## 6. Grounding：接地到底改变了什么

接地可以理解为把导体连接到一个巨大的电荷库——地球。

电荷可以在导体和地球之间流动，而地球足够大，其电势变化可以忽略。

通常规定：

```math
\boxed{
V_{\rm ground}=0
}
```

因此接地导体除了满足静电平衡条件外，还额外给出了非常强的边界条件：

```math
\boxed{
V_{\rm conductor}=0
}
```

这正是镜像法能够方便处理 grounded conductor 的关键。

## 7. Method of Image Charges：为什么可以用“假电荷”替代导体

考虑经典问题：

- 无限大接地金属平面位于 $z=0$；
- 真实点电荷 $+q$ 位于 $(0,0,d)$；
- 只求上半空间 $z>0$ 的电势和电场。

真实系统中，金属表面会产生复杂而不均匀的 induced surface charge。

直接求这整片表面电荷分布很困难。

镜像法的想法是：

> 不直接求真实感应电荷，而寻找一个更简单的“辅助电荷系统”，使它在我们关心的求解区域里满足完全相同的物理条件。

### 7.1 构造镜像电荷

删除金属板，在镜像位置 $(0,0,-d)$ 放置一个假电荷：

```math
-q
```

于是辅助系统中有：

```math
+q:(0,0,d)
```

和：

```math
-q:(0,0,-d)
```

取平面 $z=0$ 上任意一点：

```math
P=(x,y,0)
```

该点到两个电荷的距离相同：

```math
r_+=r_-
=
\sqrt{x^2+y^2+d^2}
```

因此：

```math
V(P)
=
\frac{1}{4\pi\varepsilon_0}
\left(
\frac{q}{r_+}
-
\frac{q}{r_-}
\right)
=0
```

而且这个结论对整个平面上的任意 $(x,y)$ 都成立。

所以：

```math
\boxed{
V(x,y,0)=0
}
```

辅助系统成功复现了真实接地金属板的边界条件。

## 8. 为什么只匹配边界，就能保证整个区域里的场相同

### 我的问题：真实系统是一整片感应电荷，镜像系统却只是一个点电荷，它们怎么可能在其他空间也完全一样？

关键不是“两种电荷分布长得一样”，而是 **uniqueness theorem（唯一性定理）**。

在我们关心的上半空间 $z>0$ 中：

1. 两个问题内部都有同一个真实电荷 $+q$；
2. 整个边界平面 $z=0$ 上都有 $V=0$；
3. 无限远处都有 $V\to0$。

在该区域中，电势满足 Poisson equation：

```math
\nabla^2V
=
-\frac{\rho}{\varepsilon_0}
```

区域内部的 $\rho$ 相同，完整边界条件也相同，因此解被唯一确定。

所以：

```math
\boxed{
V_{\rm real}(x,y,z)
=
V_{\rm image}(x,y,z),
\qquad z>0
}
```

进而：

```math
\boxed{
\vec E_{\rm real}
=
\vec E_{\rm image},
\qquad z>0
}
```

所以真正的等效关系是：

```math
\boxed{
\text{真实金属表面的感应电荷}
\equiv
\text{镜像电荷}
\quad
\text{仅在求解区域内}
}
```

镜像电荷本身并不真实存在。

## 9. 唯一性定理中“边界”到底是什么

### 我的问题：是不是只要找两个以上位置电势一样，就能推出处处一样？

不能。

有限个点的电势相同远远不够。

必须满足：

```math
\boxed{
\text{区域内部源相同}
+
\text{整个边界条件相同}
}
```

才能利用唯一性定理。

例如两个函数在两个点都等于 0，并不意味着它们在其他地方相等。

镜像法真正验证的是：

```math
V(x,y,0)=0
```

对整个平面上的任意 $(x,y)$ 都成立，而不是只验证其中几个点。

### 如何确定什么是“边界”

先确定：

> **我到底在哪个空间区域里求解？**

然后：

> **把这个求解区域与外界分开的全部外壳，就是边界。**

对于点电荷 + 无限大接地平面：

```math
\text{求解区域}: z>0
```

它的边界包括：

1. 平面 $z=0$；
2. 因为区域无限大，还要包含无穷远处的条件 $V\to0$。

所以判断边界时可以使用：

```math
\boxed{
\text{先圈定求解区域}
\rightarrow
\text{再找完整外边界}
\rightarrow
\text{匹配所有边界条件}
}
```

## 10. 镜像法的使用框架

看到 grounded conductor 问题时：

1. **先确定求解区域**；
2. **找出整个边界**；
3. 写出真实边界条件，例如 $V=0$；
4. 在求解区域之外放置 image charges；
5. 检查 image system 是否在整个边界上满足相同条件；
6. 若区域内部真实电荷也相同，则由 uniqueness theorem，求解区域内的 $V$ 和 $\vec E$ 与真实问题完全一致。

必须注意：

```math
\boxed{
\text{image charge 不能放在求解区域内}
}
```

否则会改变求解区域本身的真实电荷分布。

## 11. 本 Lecture 的核心图景

静电平衡导体：

```math
\boxed{
\vec E_{\rm metal}=0
\Rightarrow
V_{\rm conductor}=\text{constant}
\Rightarrow
Q_{\rm excess}\text{ lies on surfaces}
}
```

导体表面：

```math
\boxed{
E_{\parallel}=0,
\qquad
E_{\perp}=\frac{\sigma}{\varepsilon_0}
}
```

接地：

```math
\boxed{
V_{\rm conductor}=0
}
```

镜像法：

```math
\boxed{
\text{same sources in solution region}
+
\text{same complete boundary conditions}
\Rightarrow
\text{same }V\text{ and }\vec E
}
```

## 12. 当前理解总结

本 Lecture 最重要的转变不是再去死记一个新公式，而是开始把静电问题理解成一个 **boundary-value problem（边值问题）**：

- 电荷决定区域内部的源；
- 导体表面给出边界条件；
- Poisson/Laplace equation 决定区域内电势；
- 唯一性定理保证满足这些条件的解只有一个；
- 镜像法只是一个聪明的方法，用简单的假电荷去复现正确的完整边界条件。

因此，镜像法的本质不是“假的点电荷真的等于表面电荷”，而是：

> **它在我们关心的区域里制造了完全相同的数学问题，所以得到完全相同的物理解。**
