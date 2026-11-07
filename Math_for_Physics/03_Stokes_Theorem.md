# Stokes' Theorem（斯托克斯定理）

> 本页记录在普通物理 II 的 Maxwell 方程中遇到的 Stokes 定理，以及它与高斯散度定理的区别。这里是当前接触过的核心公式和一个应用，不代表已经系统掌握全部证明。

<img width="1118" height="1224" alt="image" src="https://github.com/user-attachments/assets/74bc2db8-3605-4d23-8440-cd70e293b172" />


## 1. 核心公式

```math
\boxed{
\oint_{\partial S}\vec F\cdot d\vec l
=
\iint_S(\nabla\times\vec F)\cdot d\vec A
}
```

- $S$：带有边界的定向曲面；
- $\partial S=C$：曲面的闭合边界曲线；
- $d\vec l$：沿曲线的切向线元；
- $d\vec A$：带方向的面积元；
- $\nabla\times\vec F$：向量场的旋度（curl）。

**方向约定：** 曲线正向与曲面法向满足右手定则。右手拇指指向 $d\vec A$ 所选法向，四指弯曲方向就是边界 $C$ 的正向。

## 2. 直观含义

> 曲面上所有局部旋转（旋度）的法向分量之和 = 沿曲面边界一圈的总环流。

把曲面分成很多小块，每条内部公共边界被相邻两块以相反方向积分，互相抵消，最终只剩外边界的环流。这与散度定理中“内部贡献相互抵消”的思想相似。

## 3. 在电磁学中的例子

对于稳恒电流，安培环路定律是：

```math
\oint_C\vec B\cdot d\vec l
=\mu_0 I_{\mathrm{enc}}
=\mu_0\iint_S\vec J\cdot d\vec A
```

用 Stokes 定理改写左边：

```math
\iint_S(\nabla\times\vec B)\cdot d\vec A
=\mu_0\iint_S\vec J\cdot d\vec A
```

对任意适当曲面成立，于是得到稳恒电流情形的微分形式：

```math
\boxed{\nabla\times\vec B=\mu_0\vec J}
```

**适用范围提醒：** 如果电场随时间变化，应使用 Maxwell 修正后的安培定律，其中多出位移电流项 $\mu_0\varepsilon_0\,\partial\vec E/\partial t$。

## 4. 与 Gauss 散度定理对比

| | Gauss（散度定理） | Stokes（斯托克斯定理） |
| --- | --- | --- |
| 左边 | 闭合曲面上的通量 | 闭合曲线上的环流 |
| 右边 | 体积内散度积分 | 曲面上旋度通量积分 |
| 核心关系 | 散度 ↔ 通量 | 旋度 ↔ 环流 |

散度定理的详细笔记见 [01_Divergence_Theorem.md](01_Divergence_Theorem.md)。

## 5. 最小记忆版本

```math
\boxed{\oint_C\vec F\cdot d\vec l
=\iint_S(\nabla\times\vec F)\cdot d\vec A}
```

**一句话：沿边界的环流 = 曲面内部旋度的总通量。**
