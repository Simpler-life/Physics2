# Chapter 8 Exercise 3：磁场中的方向判定易混点

> 状态：已澄清的方向判定规则（需后续做题巩固）  
> 关键词：magnetic force / motional emf / left-hand rule / right-hand rule / cross product

## 1. 当时混淆了什么？

做第 8 章 Exercise 3 时，容易混淆两种不同的问题：

- **已知电流和磁场，求载流导线所受的磁力**；
- **已知导体棒的运动速度和磁场，求感应电动势的方向**。

高中习惯将前者称为**左手定则**，将后者称为**右手定则**。它们并不是两种互相冲突的物理规律。

## 2. 先判断题目要求什么

| 场景 | 已知 | 要求 | 主要公式 | 高中常用口诀 |
| --- | --- | --- | --- | --- |
| 通电导线受到磁力（电动机效应） | $I,\ \mathbf B$ | 力 $\mathbf F$ | $d\mathbf F=I\,d\boldsymbol\ell\times\mathbf B$ | 左手定则 |
| 导体棒在磁场中运动（动生电动势） | $\mathbf v,\ \mathbf B$ | 正电荷受力、两端极性 / 感应电动势 | $\mathbf F_B=q\mathbf v\times\mathbf B$ | 右手定则（切割磁感线） |

注意：

- 两个场景都可以直接用**右手叉乘法则**计算。叉乘的方向由第一个矢量转向第二个矢量确定。
- $q\mathbf v\times\mathbf B$ 是**磁场对运动电荷的力**，对负电荷要反向；不是“感应电场对电荷的磁力”。
- 运动的导体棒即使没有闭合回路，也可能出现电荷分离和**动生电动势**；但没有闭合通路时，一般没有持续的感应电流。
- **如果问运动导体棒受到的磁力**，即使它也产生感应电动势，仍需要先确定电流，再根据 $I\boldsymbol\ell\times\mathbf B$ 判断受力方向。

## 3. 不死记左右手：统一用叉乘

对于右手坐标系：

```math
\hat{\mathbf x}\times\hat{\mathbf y}=\hat{\mathbf z},\qquad
\hat{\mathbf y}\times\hat{\mathbf z}=\hat{\mathbf x},\qquad
\hat{\mathbf z}\times\hat{\mathbf x}=\hat{\mathbf y}
```

**交换叉乘顺序，符号取反**，例如：

```math
(-\hat{\mathbf x})\times\hat{\mathbf z}
=+\hat{\mathbf y}
```

处理力的方向时，先写清楚：谁是第一个矢量？谁是第二个矢量？电荷是正还是负？

## 4. 应用：Chapter 8 Exercise 3

> 本次做题时确认的磁场区域为 $y\ge a$（$0\le a<R$），磁场沿 $+z$；半径为 $R$ 的圆环位于 $xy$ 平面，电流从 $+z$ 观察为逆时针。

1. **磁场**：$\mathbf B=B\hat{\mathbf z}$（出纸面）。
2. **上方圆弧电流**：从**右端**流向**左端**。逆时针经过圆顶部时，切向速度向左。
3. **两交点**：左端 $A=(-\sqrt{R^2-a^2},a)$，右端 $C=(+\sqrt{R^2-a^2},a)$。
4. **等效位移**：必须沿电流方向从 $C$ 指向 $A$，即沿 $-x$。
5. **合磁力**：$(-x)\times(+z)=+y$。

匀强磁场内，沿曲线的一段导线受到的**合磁力**等于其首尾端点之间、同方向的等效直导线所受的磁力：

```math
\mathbf F=I\int_C^A d\boldsymbol\ell\times\mathbf B
=I(\mathbf r_A-\mathbf r_C)\times\mathbf B
```

```math
\mathbf r_A-\mathbf r_C
=-2\sqrt{R^2-a^2}\,\hat{\mathbf x}
```

```math
\boxed{\mathbf F=2IB\sqrt{R^2-a^2}\,\hat{\mathbf y}}
```

这里等效的是**合力**，不意味着弯曲导线与直线导线有相同的逐点受力，也不意味着力矩必然相同。这一等效使用了所考虑导线部分的**磁场均匀**这一条件。

## 5. 下次三步判断

1. **问的是什么？** 受力 $\mathbf F$，还是感应电动势的极性/感应电流？
2. **先标清实际矢量**：电流方向 $d\boldsymbol\ell$ 或载流子速度 $\mathbf v$，以及磁场 $\mathbf B$（入纸面 $-z$ / 出纸面 $+z$）。
3. **写叉乘再判断**：$I\,d\boldsymbol\ell\times\mathbf B$ 或 $q\mathbf v\times\mathbf B$。不要把**等效导线方向**和**最后的受力方向**混为一谈。

**一句话复盘：左手/右手是高中不同场景的速记；大学物理先写对物理公式，再按叉乘顺序统一用右手法则。**
