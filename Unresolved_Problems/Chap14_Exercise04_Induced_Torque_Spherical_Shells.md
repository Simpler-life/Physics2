# Chapter 14 Exercise 4｜变化磁场下的球壳感应力矩

> **状态：未解决 / 待系统补学。** 已听过一遍讲解，但用户反馈“完全不会”；不能标记为已掌握。  
> 来源：第 7 次作业 Chapter 14 Exercise 4。  
> 关联：[Lecture 14](../Lecture_Notes/Lecture14_Maxwells_Equations_and_EM_Waves.md)。

## 1. 题目条件（辅导时的整理）

两个同心绝缘球壳，半径 $r_1<r_2$，分别均匀带电 $+q$ 与 $-q$，刚性连接，可绕 $z$ 轴转动，总转动惯量 $J$。初始存在沿 $+z$ 方向的均匀磁场 $B_0$，之后缓慢降为零。求最终角速度与转动方向。

## 2. 当前确切状态和卡点

- **用户反馈：整道题完全不会。** 暂时不假定任何步骤已经理解。
- 待理解：为什么变化磁场可以产生沿球面切向的感应电场。
- 待理解：法拉第环路为什么取绕 $z$ 轴的圆，圆半径为何是 $s=R\sin\theta$。
- 待理解：对球面电荷求绕 $z$ 轴力矩时，力臂为何是 $s$，而不是 $R$。
- 待理解：如何在整个球面上积分，尤其 $\langle\sin^2\theta\rangle=2/3$ 的来源。
- 待理解：内外壳电荷符号相反，合力矩如何求和，再利用角动量定理积分。

## 3. 暂存参考解（**未独立完成，供之后核对**）

以下为本次对话使用的理想化模型推导，不代表已掌握。

法拉第定律对轴线为 $z$、半径 $s$ 的圆：

```math
E_\phi 2\pi s=-\pi s^2\frac{dB}{dt}
\qquad\Rightarrow\qquad
E_\phi=-\frac{s}{2}\frac{dB}{dt}
```

球面半径 $R$，极角 $\theta$ 处 $s=R\sin\theta$，一个电荷元 $dq$ 的轴向力矩：

```math
d\tau_z=s E_\phi\,dq
=-\frac{R^2\sin^2\theta}{2}\frac{dB}{dt}\,dq
```

对均匀带电球面有：

```math
\int\sin^2\theta\,dq=\frac{2Q}{3}
\qquad\Rightarrow\qquad
\tau_z=-\frac{QR^2}{3}\frac{dB}{dt}
```

两球壳分别取 $(Q,R)=(+q,r_1)$、$(-q,r_2)$：

```math
\tau_z=\frac{q(r_2^2-r_1^2)}{3}\frac{dB}{dt}
```

用 $J\,d\Omega/dt=\tau_z$，从初始静止、$B=B_0$ 积分至 $B=0$：

```math
\boxed{
\vec\Omega_f=-\frac{q B_0(r_2^2-r_1^2)}{3J}\hat z
}
```

当 $q>0,B_0>0$ 时，从 $+z$ 端观察为顺时针方向。上述结果依赖题目中的均匀磁场及缓慢变化等假设。

## 4. 下次复习的最短路线

- [ ] 画图：$z$ 轴、两个球壳、角度 $\theta$、力臂 $s=R\sin\theta$。
- [ ] 单独练：由法拉第定律推 $E_\phi=-s\dot B/2$。
- [ ] 单独练：从 $d\tau_z=sE_\phi dq$ 积分得到 $-QR^2\dot B/3$。
- [ ] 最后自己完成两壳合力矩与角动量积分。
- [ ] 能在不看参考解的情况下复做整题，再移出 Pending。

> 本文是未解决题目记录，**不要**因参考答案已写出就把它移动到 Mistake 或标为完成。
