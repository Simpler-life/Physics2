# Chapter 13 Exercise 2：复阻抗与串并联 RLC 电路

> 状态：已完成，后续复习重点是识别电路结构与复阻抗运算，而非强行从零推导所有公式。  
> 对应笔记：[Lecture 13 — 5.4 从平方根公式到复阻抗](../Lecture_Notes/Lecture13_Alternating_Current_Circuits.md#54-从平方根公式走向复阻抗不是新公式而是把直角三角形写完整)

## 1. 题目与当时的困惑

<img width="1420" height="696" alt="image" src="https://github.com/user-attachments/assets/ad6a3b9f-9db3-41d0-9054-55ee9f6165df" />


电源电压振幅 $150\,\mathrm V$、频率 $60\,\mathrm{Hz}$；$3\,\mu\mathrm F$ 电容和 $0.2\,\mathrm H$ 电感串联，后接 $1\,\mathrm H$ 电感与 $100\,\Omega$ 电阻的并联支路。求**通过 $100\,\Omega$ 电阻的电流振幅**。

- 不熟悉 $Z_L=j\omega L$、$Z_C=1/(j\omega C)$，不知道 $j$ 是什么。
- 不知道为什么 $1/j=-j$。
- 不确定复阻抗如何串、并联，以及为什么不能直接套单纯串联 RLC 的平方根公式。
- 希望先能记住公式、完成作业，之后再系统推导。

## 2. 最少记住的四组公式

以下均以**线性交流电路的正弦稳态**为前提。

**角频率：**

```math
\omega=2\pi f
```

**单个理想元件：**

```math
Z_R=R,\qquad Z_L=j\omega L,\qquad
Z_C=\frac1{j\omega C}=-\frac{j}{\omega C}
```

**串联：**

```math
Z_{\mathrm{series}}=Z_1+Z_2+\cdots
```

**并联：**

```math
\frac1{Z_{\mathrm{parallel}}}=\frac1{Z_1}+\frac1{Z_2}+\cdots
```

两个元件并联也可以直接用：

```math
Z_{\mathrm{parallel}}=\frac{Z_1Z_2}{Z_1+Z_2}
```

这里的 $Z$ 是**复阻抗**，不是只表示正数大小的 $|Z|$。

## 3. 为什么会有 $j$，它和原来的平方根式有什么关系？

$j$ 是虚数单位：$j^2=-1$，电路中不用 $i$ 是为了避免与电流 $i$ 混淆。

```math
\frac1j=\frac{j}{j^2}=-j
```

复数的实部、虚部可保存两个相差 $90^\circ$ 的相位分量。对串联 RLC：

```math
Z=R+j(X_L-X_C)
```

它的模（只看大小）就是笔记原来的公式：

```math
|Z|=\sqrt{R^2+(X_L-X_C)^2}
```

**不是从一个公式突然变出很多公式，而是原来的平方根式只保存大小；复阻抗还保存相位。**

## 4. Exercise 2 快速解题

```math
\omega=2\pi(60)\approx377\ \mathrm{rad/s}
```

各元件阻抗：

```math
Z_C\approx-j884.2\ \Omega,\quad
Z_{L1}\approx j75.4\ \Omega,\quad
Z_{L2}\approx j377.0\ \Omega
```

右侧电阻与 $1\,\mathrm H$ 电感并联：

```math
Z_p=\frac{100(j377)}{100+j377}
\approx93.43+j24.78\ \Omega
```

整个电路（左侧电容、电感与右侧并联等效阻抗串联）：

```math
Z_{\mathrm{total}}=Z_C+Z_{L1}+Z_p
\approx93.43-j784.0\ \Omega
```

总电流振幅：

```math
I_m=\frac{150}{|Z_{\mathrm{total}}|}
\approx0.190\ \mathrm A
```

并联部分电压振幅：

```math
V_{p,m}=I_m|Z_p|\approx18.36\ \mathrm V
```

题目求的是**电阻支路**，所以：

```math
\boxed{I_{R,m}=\frac{V_{p,m}}{100\,\Omega}\approx0.184\ \mathrm A}
```

## 5. 易错提醒与复习策略

1. **先判串并联拓扑**：并联分流后，总电流不等于每一支路电流。
2. **先算复阻抗，再取模**：$|3+4j|=5$，不是 $7$；复阻抗不能先取模后按普通电阻并联。
3. **振幅与有效值不同**：题目给电压振幅、求电流振幅，不需要额外除以 $\sqrt2$。
4. **串联平方根式有范围限制**：$|Z|=\sqrt{R^2+(X_L-X_C)^2}$ 适用于简单串联 RLC；混合串并联先化简复阻抗。
5. **当前学习目标**：先熟记 $R,j\omega L,1/(j\omega C)$ 和串并联规则，能正确代入计算；复习时再挑一个元件从微分关系推导复阻抗，不必每道作业都重新推导。

**一句话复盘：复阻抗把大小和相位一起算；先串并联复数，最后取模，并分清题目要总电流还是支路电流。**
