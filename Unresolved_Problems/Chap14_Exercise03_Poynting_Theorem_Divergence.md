# Chapter 14 Exercise 3(b)｜坡印廷定理与柱坐标散度

> 状态：⏳ 待理解、待独立完成。作业答案已参考辅导直接誊写，**不能视为已经掌握**。  
> 来源：第 7 次作业，Chapter 14 Exercise 3(b)。  
> 相关主线：[Lecture 14](../Lecture_Notes/Lecture14_Maxwells_Equations_and_EM_Waves.md)。

## 1. 题目目标与已知条件

一根无限长、半径 $a$ 的均匀电阻圆柱导线，电阻率为 $\rho_e$，稳恒电流 $I$ 沿 $+z$ 方向均匀分布。在导线内部 $r<a$，第 (a) 问已得到：

```math
\vec j=\frac{I}{\pi a^2}\hat z,\qquad
\vec E=\frac{\rho_e I}{\pi a^2}\hat z,\qquad
\vec B=\frac{\mu_0 I r}{2\pi a^2}\hat\phi
```

由 $\hat z\times\hat\phi=-\hat r$ 可得：

```math
\vec S=\frac{1}{\mu_0}\vec E\times\vec B
=-\frac{\rho_e I^2 r}{2\pi^2 a^4}\hat r
```

第 (b) 问要求验证：

```math
\nabla\cdot\vec S=-\rho_e j^2=-\vec j\cdot\vec E
```

## 2. 当前卡点

**已直接誊写答案，尚未理解：**

- 为什么柱坐标下只有径向分量的场，其散度是 $(1/r)\,\partial(rS_r)/\partial r$，而不是简单地 $\partial S_r/\partial r$？
- 为什么 $\nabla\cdot\vec S<0$ 代表电磁能量净流入？
- 如何把最终式子和焦耳热功率密度 $\vec j\cdot\vec E=\rho_e j^2$ 联系起来？

不要把“已经看过推导”记成“已能独立做出”。

## 3. 暂存参考解（尚未独立验证）

柱坐标散度的一般形式：

```math
\nabla\cdot\vec A
=\frac1r\frac{\partial(rA_r)}{\partial r}
+\frac1r\frac{\partial A_\phi}{\partial\phi}
+\frac{\partial A_z}{\partial z}
```

本题 $\vec S=S_r(r)\hat r$，所以：

```math
\nabla\cdot\vec S
=\frac1r\frac{\partial(rS_r)}{\partial r}
=\frac1r\frac{\partial}{\partial r}
\left(-\frac{\rho_e I^2r^2}{2\pi^2a^4}\right)
=-\frac{\rho_e I^2}{\pi^2a^4}
```

由于 $j=I/(\pi a^2)$ 且 $\vec E=\rho_e\vec j$：

```math
\boxed{
\nabla\cdot\vec S
=-\rho_e j^2
=-\vec j\cdot\vec E
}
```

物理意义：稳态时局部场能不变；进入导线的电磁能量转化为电流耗散的焦耳热。

## 4. 期中前复习：最短补学任务

- [ ] 看懂柱坐标散度式中的 $r$ 因子从何而来（圆柱壳侧面积随半径变化）。
- [ ] 不看答案，对 $S_r=-Cr$（$C>0$ 为常量）独立计算 $\nabla\cdot\vec S$。
- [ ] 用一句话解释 $\nabla\cdot\vec S<0$ 的能量流入含义。
- [ ] 独立复算本题 (b)，再标记完成。

> 备注：这道题先留在 Pending；理解并能独立复算后，再按仓库规则从 `Pending/Problems_TODO.md` 移除。
