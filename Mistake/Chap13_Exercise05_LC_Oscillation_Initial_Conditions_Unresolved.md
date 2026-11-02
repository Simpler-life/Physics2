# Chapter 13 Exercise 5：开关切换后的 LC 振荡（尚未学会）

> **状态：🔴 未掌握 / 答案已机械抄写，尚不能独立解题。**
>
> 不能将“已经把解答抄进作业”误记成“已理解、会做”。复习时需要重新从题目出发独立完成。
>
> 对应：[Lecture 13 — 第 1 节：LC 自由振荡](../Lecture_Notes/Lecture13_Alternating_Current_Circuits.md#1-第一步不接电源也不接电阻为什么-lc-会自己振荡)

## 1. 题型与真正没掌握的地方

电池电动势 $\mathcal E$、电阻 $r$、电感 $L$、电容 $C$。开关先闭合很久，$t=0$ 断开，之后理想 LC 振荡。取电感电流 $i_L$ 从 A 到 B 为正，$q$ 为电容连接 A 一侧极板的带符号电荷。

**当前实际学习状态：整道题只是机械地抄了答案，并不意味着学会。**

具体需要回头梳理：

- 为什么开关长期闭合时，电感近似短路、电容近似开路？如何据此找初始值？
- 为什么在这题里 $i_L=-dq/dt$，而其他题里可能写 $i=dq/dt$？该看哪个极板和电流箭头？
- 为什么开关刚断开时电感电流、电容电压不能突变？
- 为什么要设 $q(t)=Q\cos(\omega_0t+\phi)$，怎样用初始条件定出 $Q,\phi$？
- 为什么电容电压能远大于电池电压？如何由电感磁场能量转移到电容电场能量解释？

## 2. 作业答案留档（仅作复习核对，不作为已掌握证据）

### (a) 开关断开前：直流稳态

```math
i_L(0^-)=\frac{\mathcal E}{r},
\qquad q(0^-)=0,\qquad V_A-V_B=0
```

### (b) 开关断开后：理想 LC 振荡

以题目指定电流正向和 A 侧极板电荷定义，有：

```math
i_L=-\frac{dq}{dt}
```

负号的意思是：电流沿 A 到 B 的正方向流动时，A 侧极板的正电荷流出，$q$ 减少，所以 $dq/dt<0$。

```math
L\ddot q+\frac qC=0,\qquad \omega_0=\frac1{\sqrt{LC}}
```

初始条件：

```math
q(0)=0,\qquad i_L(0)=\frac{\mathcal E}{r},
\qquad\dot q(0)=-\frac{\mathcal E}{r}
```

结果：

```math
\boxed{q(t)=-\frac{\mathcal E}{r\omega_0}\sin(\omega_0t)}
```

```math
\boxed{i_L(t)=\frac{\mathcal E}{r}\cos(\omega_0t)}
```

```math
\boxed{V_A-V_B=-\frac{\mathcal E}{r}\sqrt{\frac LC}\sin(\omega_0t)}
```

### (c) 电压振幅与第一次达到峰值

```math
\boxed{|V_A-V_B|_{\max}=\frac{\mathcal E}{r}\sqrt{\frac LC}}
```

```math
\boxed{t_1=\frac{\pi}{2}\sqrt{LC}}
```

按上述符号约定，第一次峰值时 $V_A-V_B<0$，B 端电势较高。

按此前解答给出的 $\mathcal E=12\,\mathrm V,\ r=6.0\,\Omega,\ L=0.20\,\mathrm H,\ C=0.50\,\mu\mathrm F$：

```math
|V_A-V_B|_{\max}\approx1.26\times10^3\,\mathrm V,\qquad
t_1\approx4.97\times10^{-4}\,\mathrm s
```

能量核对：

```math
\frac12L\left(\frac{\mathcal E}{r}\right)^2
=\frac12C V_{\max}^2
```

## 3. 之后如何判断“真的会了”？

不要再照着本页看答案，而是从原始电路图独立完成：

1. 标记开关断开前、刚断开后、断开后任意时刻三个状态。
2. 不看答案画出电流正方向与所研究电容极板，自己决定 $dq/dt$ 前应否有负号。
3. 自己建立 LC 方程并从初始条件写出 $q(t),i(t),V(t)$。
4. 用能量守恒独立求出最大电压，并解释为什么可超过电池电压。

只有能独立完成这些，才从**🔴 未掌握**调整为**🟢 已理解**。
