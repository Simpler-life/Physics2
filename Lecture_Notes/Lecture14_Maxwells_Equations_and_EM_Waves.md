# Lecture 14｜Maxwell's Equations and Electromagnetic Waves

> **学习状态：** 已完成一轮核心概念梳理及 Exercise 14.1、14.3、14.4 的讲解；公式的独立推导和限时做题熟练度**尚未逐项检验**。  
> **资料来源：** 上传教材 `chap14.pdf`，Chapter 14，pp.125–135（14.1–14.5）。  
> **本次目标：** 以期中复习、快速完成作业为主；会辨认公式、选取积分面/环路、判断方向、完成典型题，不要求一开始熟练掌握所有矢量微积分推导。

## 0. 一张知识地图

- **14.1 麦克斯韦方程组：** 电荷产生电场；不存在已证实的磁单极子；变化磁场产生涡旋电场；电流及变化电场产生涡旋磁场。
- **14.2 Magnetic Charge：** 当前麦克斯韦理论采用磁荷为零的描述；这一节偏概念。
- **14.3 电磁波：** 真空中的麦克斯韦方程给出波动方程；波速为光速；平面波中 $\vec E,\vec B,\hat k$ 互相垂直且同相。
- **14.4 能量输运：** 电磁场储存并运输能量；坡印廷矢量 $\vec S$；平均光强、辐射压。
- **14.5 作业：** Exercise 1 是位移电流及磁场，Exercise 3 是电阻导线能量流，Exercise 4 是磁场消失引起转矩与角动量。

**本章最短逻辑链：** 旧安培定律不适用于任意变化电荷 → 添加位移电流 → 麦克斯韦方程组自洽 → 真空中有传播的电磁波 → 电磁波有能量流与动量。

## 1. 14.1 麦克斯韦方程组：积分与微分形式

在真空中使用 SI 单位。$\rho$ 为**体电荷密度**（C/m³），$\vec J$ 为传导电流密度（A/m²），$Q_{\mathrm{enc}}$ 为封闭曲面所包围的净电荷。下表积分形式的闭合环路及跨越曲面均视为静止。

| 物理定律 | 积分形式 | 微分形式 |
|---|---|---|
| 电场高斯定律 | $\displaystyle\oint_{\partial V}\vec E\cdot d\vec A=\frac{Q_{\mathrm{enc}}}{\varepsilon_0}$ | $\displaystyle\nabla\cdot\vec E=\frac{\rho}{\varepsilon_0}$ |
| 法拉第定律 | $\displaystyle\oint_C\vec E\cdot d\vec l=-\frac{d\Phi_B}{dt}$ | $\displaystyle\nabla\times\vec E=-\frac{\partial\vec B}{\partial t}$ |
| 磁场高斯定律 | $\displaystyle\oint_{\partial V}\vec B\cdot d\vec A=0$ | $\displaystyle\nabla\cdot\vec B=0$ |
| 安培–麦克斯韦定律 | $\displaystyle\oint_C\vec B\cdot d\vec l=\mu_0I_{\mathrm{enc}}+\mu_0\varepsilon_0\frac{d\Phi_E}{dt}$ | $\displaystyle\nabla\times\vec B=\mu_0\vec J+\mu_0\varepsilon_0\frac{\partial\vec E}{\partial t}$ |

这里磁、电通量为：

```math
\Phi_B=\int_S\vec B\cdot d\vec A,\qquad
\Phi_E=\int_S\vec E\cdot d\vec A.
```

**一眼分辨两类运算：**

- **散度 $\nabla\cdot$** ↔ **封闭曲面通量 $\oint\vec F\cdot d\vec A$**（高斯散度定理）。
- **旋度 $\nabla\times$** ↔ **闭合曲线环流 $\oint\vec F\cdot d\vec l$**（斯托克斯定理）。
- 只有环路围成的定向曲面与环路的正向按**右手规则**匹配，符号才正确。

相关数学定理：

```math
\oint_{\partial V}\vec F\cdot d\vec A
=\int_V(\nabla\cdot\vec F)\,dV
```

```math
\oint_C\vec F\cdot d\vec l
=\int_S(\nabla\times\vec F)\cdot d\vec A
```

**静态/稳恒特殊情形：** $\partial_t\vec B=0$ 时 $\nabla\times\vec E=0$；$\partial_t\vec E=0$ 时安培–麦克斯韦定律简化为 $\nabla\times\vec B=\mu_0\vec J$。不要把这些特殊式子当成任意时变场都成立。

### 1.1 为什么要引入位移电流？

对旧安培定律 $\nabla\times\vec B=\mu_0\vec J$ 两边取散度，利用“旋度的散度恒为零”，得到 $\nabla\cdot\vec J=0$。但是**电荷守恒**要求：

```math
\nabla\cdot\vec J=-\frac{\partial\rho}{\partial t}
```

当电荷分布随时间变化时，二者不兼容。麦克斯韦加入：

```math
\boxed{\vec J_d=\varepsilon_0\frac{\partial\vec E}{\partial t}}
```

因为高斯定律给出 $\varepsilon_0\nabla\cdot\vec E=\rho$，于是：

```math
\nabla\cdot(\vec J+\vec J_d)
=\nabla\cdot\vec J+\frac{\partial\rho}{\partial t}=0.
```

新定律与电荷守恒相容。

**充电平行板电容器（忽略边缘场）**：

```math
E=\frac{Q}{\varepsilon_0 A}
\quad\Rightarrow\quad
I_d=\varepsilon_0\frac{d(EA)}{dt}
=\frac{dQ}{dt}=I.
```

- 导线中有传导电流 $I$；
- 极板间无电荷跨越绝缘间隙，却有变化的电场；
- 通过极板间截面的位移电流 $I_d$ 与导线的传导电流 $I$ 相等（理想模型）。
- **切忌：** $J_d$ 不是电荷穿越真空的真实运动；$J_d$ 取决于 $\partial_t E$，不取决于 $E$ 是否很大。

一般定义：

```math
\boxed{I_d=\int_S\vec J_d\cdot d\vec A
=\varepsilon_0\frac{d\Phi_E}{dt}}
```

> 在不同截面上，传导电流与位移电流的贡献可以不同；在理想电容器例子里比较的是相应的截面总量，而不是声称所有位置的 $J_d=J$。

### 1.2 与 $\vec J$ 相关的常用公式

| 公式 | 条件与物理意义 |
|---|---|
| $I=\int_S\vec J\cdot d\vec A$ | 面上的总传导电流 |
| $\vec J=nq\vec v_d$ | 单类载流子的漂移电流 |
| $\vec J=\sigma\vec E$ | 线性各向同性欧姆导体 |
| $\vec J_d=\varepsilon_0\partial_t\vec E$ | 真空位移电流密度 |
| $\nabla\cdot\vec J=-\partial_t\rho$ | 局部电荷守恒 |
| $\vec f=\vec J\times\vec B$ | 电流受到的磁力密度（仅磁力部分） |
| $p=\vec J\cdot\vec E=\rho_e J^2$ | 欧姆导体的焦耳热功率密度；$\rho_e=1/\sigma$ 为电阻率 |

**符号防混淆：** $\rho$ 指体电荷密度；$\rho_e$ 指电阻率；$\sigma$ 在这里是电导率（有些章节会以 $\sigma$ 指面电荷密度），一定看单位。

### 1.3 14.2 磁荷

电场高斯定律允许电荷作为源，而 $\nabla\cdot\vec B=0$ 表示标准麦克斯韦理论中没有磁单极子。教材指出磁单极子的存在与电荷量子化的理论联系，但**尚无确证的磁单极子**。本节以概念理解为主；Exercise 6 讨论假设磁荷存在时的修改，当前可留作提高题。

## 2. 14.3 电磁波是怎样从方程中出现的？

真空无电荷、无电流：$\rho=0,\vec J=0$。

```math
\nabla\cdot\vec E=0,\quad
\nabla\times\vec E=-\partial_t\vec B,\quad
\nabla\cdot\vec B=0,\quad
\nabla\times\vec B=\mu_0\varepsilon_0\partial_t\vec E.
```

对法拉第定律取旋度并代入安培–麦克斯韦定律，再利用：

```math
\nabla\times(\nabla\times\vec A)
=\nabla(\nabla\cdot\vec A)-\nabla^2\vec A
```

可得：

```math
\boxed{\nabla^2\vec E
=\mu_0\varepsilon_0\frac{\partial^2\vec E}{\partial t^2}}
\qquad
\boxed{\nabla^2\vec B
=\mu_0\varepsilon_0\frac{\partial^2\vec B}{\partial t^2}}.
```

和标准波动方程 $\nabla^2 F=(1/v^2)\partial_t^2F$ 比较：

```math
\boxed{c=\frac1{\sqrt{\mu_0\varepsilon_0}}
\approx2.998\times10^8\ {\rm m/s}}.
```

这就是光速：**光是电磁波**。一维波可以写成 $F_1(x-ct)+F_2(x+ct)$，分别沿 $+x/-x$ 传播。

### 2.1 真空平面波的方向、相位、振幅

设沿 $+x$ 传播，$\theta=kx-\omega t+\phi$，则可以选：

```math
\vec E=E_0\cos\theta\,\hat y,\qquad
\vec B=B_0\cos\theta\,\hat z,
\qquad \omega=ck.
```

用 $\nabla\cdot\vec E=\nabla\cdot\vec B=0$ 知 $\vec E$、$\vec B$ 均垂直传播方向；再由法拉第定律得 $kE_0=\omega B_0$，所以：

```math
\boxed{B_0=\frac{E_0}{c}},\qquad
\boxed{\vec B=\frac1c\hat k\times\vec E}.
```

**三条核心结论：** $\vec E\perp\vec B$、二者均垂直传播方向；二者**同相**；传播方向由 $\vec E\times\vec B$ 给出（右手定则）。

通用波参量：

```math
c=\lambda f=\frac{\omega}{k},\qquad
\omega=2\pi f,\qquad
k=\frac{2\pi}{\lambda}.
```

教材 14.3.1：**加速电荷产生电磁辐射**，以振荡偶极天线为例。电磁波谱从无线电波、微波、红外、可见光（约 400–700 nm）、紫外到 X 射线、伽马射线；本质相同，频率/波长不同。

## 3. 14.4 电磁场能量与坡印廷矢量

真空电、磁能量密度：

```math
u_E=\frac12\varepsilon_0 E^2,\qquad
u_B=\frac{B^2}{2\mu_0},\qquad
u=u_E+u_B.
```

局部能量守恒（坡印廷定理）：

```math
\boxed{\frac{\partial u}{\partial t}
+\nabla\cdot\vec S=-\vec J\cdot\vec E},
\qquad
\boxed{\vec S=\frac1{\mu_0}\vec E\times\vec B}.
```

- $\vec S$ 单位 **W/m²**：单位面积、单位时间的能量流；**不是**电流密度 $\vec J$（A/m²）。
- $-\vec J\cdot\vec E$ 是电磁场向电荷做功的能量损失项。
- $\vec S$ 的方向由叉乘确定；平面行波中就是波的传播方向。

**坡印廷矢量的来源（会认，不要求死背完整推导）：** 对 $u$ 求时间导数，用两条旋度方程代换 $\partial_t\vec E,\partial_t\vec B$，再用 $\nabla\cdot(\vec E\times\vec B)=\vec B\cdot(\nabla\times\vec E)-\vec E\cdot(\nabla\times\vec B)$，即得能量守恒式。

对于真空正弦平面波，$\vec E$ 与 $\vec B$ 同相且 $B=E/c$，瞬时强度为 $S(t)=\varepsilon_0cE_0^2\cos^2\theta$。周期平均 $\langle\cos^2\theta\rangle=1/2$：

```math
\boxed{I_{\rm wave}=\langle S\rangle
=\frac{E_0B_0}{2\mu_0}
=\frac12\varepsilon_0 c E_0^2
=\frac{c B_0^2}{2\mu_0}}.
```

这里 **$I_{\rm wave}$ 是光强**（W/m²），不是导线里的电流（A）。理想真空平面波还满足 $u_E=u_B$（瞬时相等）。

### 3.1 球面波（14.4.1）

各向同性点源总辐射功率为 $P$，能量均匀通过半径 $r$ 的球面：

```math
\boxed{I(r)=\frac{P}{4\pi r^2}}.
```

### 3.2 辐射压（14.4.2）

电磁波携带动量；垂直入射、时间平均强度为 $I$：

```math
\boxed{p_{\rm absorb}=\frac{I}{c}},\qquad
\boxed{p_{\rm reflect}=\frac{2I}{c}}.
```

其中 $p$ 是**压强**（Pa），不是电偶极矩。完全反射的动量改变是完全吸收的两倍。斜入射情形参见 Exercise 9。

## 4. 作业题型：已讲解过的 Exercise 1、3、4

> 以下保留此前辅导中使用的解题路线；“已讲解”不代表已经独立做对。练习条件以教材 14.5 原题为准。

### Exercise 1｜交流充电电容器中的位移电流和磁场

圆板半径 $a$，$q(t)=q_0\sin\omega t$，忽略边缘效应，$\omega a\ll c$（准静态近似）。

```math
E(t)=\frac{q_0\sin\omega t}{\varepsilon_0\pi a^2},
\qquad
\boxed{J_d=\frac{q_0\omega}{\pi a^2}\cos\omega t}
```

```math
\boxed{I_d=q_0\omega\cos\omega t}.
```

对 $r<a$ 的同轴安培环路，包围的位移电流为 $J_d\pi r^2$：

```math
B_\phi(2\pi r)=\mu_0 J_d\pi r^2
\quad\Rightarrow\quad
\boxed{B_\phi(r,t)=\frac{\mu_0q_0\omega r}{2\pi a^2}\cos\omega t}.
```

**考点：** 先求 $J_d$ 再乘“环路圈住的面积”，不是总极板面积；符号由选定的环向正方向确定。

### Exercise 3｜通电圆柱导线里的电磁能量流

导线半径 $a$，电阻率 $\rho_e$，均匀稳恒电流 $I$ 沿 $+z$ 方向。**只考虑导线内部 $r<a$**：

```math
J=\frac{I}{\pi a^2},\qquad
\boxed{\vec E=\rho_e\frac{I}{\pi a^2}\hat z},\qquad
\boxed{\vec B=\frac{\mu_0Ir}{2\pi a^2}\hat\phi}.
```

```math
\boxed{\vec S=\frac{\vec E\times\vec B}{\mu_0}
=-\frac{\rho_e I^2r}{2\pi^2a^4}\hat r}.
```

**核心：** $\hat z\times\hat\phi=-\hat r$，电磁能量**从侧面进入导线**，在那里变成焦耳热。

稳态 $\partial_t u=0$，柱坐标：

```math
\nabla\cdot\vec S
=\frac1r\frac{\partial(r S_r)}{\partial r}
=-\frac{\rho_e I^2}{\pi^2a^4}
=-\rho_e J^2=-\vec J\cdot\vec E.
```

### Exercise 4｜球形电容器、衰减磁场与角动量

内外同心**绝缘球壳**半径 $r_1<r_2$，带电 $+q$、$-q$，刚性连接、总转动惯量 $J_{\rm rot}$；初始均匀磁场 $\vec B=B_0\hat z$ 随后缓慢降为 0。忽略球壳自身转动产生的磁场。

以到 $z$ 轴距离 $s$ 为半径取圆形回路，法拉第定律：

```math
E_\phi(2\pi s)=-\pi s^2\frac{dB}{dt}
\quad\Rightarrow\quad
E_\phi=-\frac{s}{2}\frac{dB}{dt}.
```

球壳处 $s=R\sin\theta$，对均匀球面电荷有 $\langle\sin^2\theta\rangle=2/3$，因此一个半径 $R$、带电量 $Q$ 的壳的 $z$ 向力矩：

```math
\tau_z=-\frac{QR^2}{3}\frac{dB}{dt}.
```

内外壳合起来，对 $B:B_0\to0$ 积分：

```math
\boxed{\Omega_f
=\frac{qB_0(r_1^2-r_2^2)}{3J_{\rm rot}}
=-\frac{qB_0(r_2^2-r_1^2)}{3J_{\rm rot}}}.
```

若 $B_0>0,q>0$，$\Omega_f<0$，从 $+z$ 端看沿顺时针方向。此结果用到题目中的“均匀磁场覆盖球壳”等理想条件。

**核心解题链：** $\partial_t B\to E_\phi$ → $dq$ 受切向电场力 → 对每个壳积分力矩 → 角动量定理求 $\Omega_f$。

## 5. 其他 Exercise 速览（待练，不标作已掌握）

| 教材题号 | 主题 | 复习状态 |
|---|---|---|
| 14.2 | 给定正弦平面电场，求波长、传播方向、磁场 | 待独立练习，**建议优先** |
| 14.5 | 弱导电介质电容器放电，传导/位移电流抵消、焦耳热和能流 | 待练，综合题 |
| 14.6 | 假设有磁单极子、修改法拉第定律 | 拓展 |
| 14.7 | 两个反向平面波叠加、能流与守恒 | 拓展 |
| 14.8 | 振荡电流片辐射的边界条件和功率 | 拓展 |
| 14.9 | 太阳帆、辐射压 | 拓展 |

## 6. 考试前 3 分钟清单

- [ ] 能默写四条麦克斯韦方程的**微分形式**，并辨认积分形式。
- [ ] 能解释旧安培定律为何需要 $\vec J_d=\varepsilon_0\partial_t\vec E$。
- [ ] 看到充电电容器能计算 $I_d$，并用安培环路求 $B_\phi$。
- [ ] 能说明“散度↔闭合曲面通量；旋度↔闭合线环流”。
- [ ] 知道波速来自真空波动方程 $c=1/\sqrt{\mu_0\varepsilon_0}$。
- [ ] 会用 $\vec B=(\hat k\times\vec E)/c$、$c=\omega/k$ 判方向、求磁场。
- [ ] 会用 $\vec S=(\vec E\times\vec B)/\mu_0$ 和 $\langle S\rangle=\varepsilon_0cE_0^2/2$。
- [ ] 知道坡印廷定理 $\partial_tu+\nabla\cdot\vec S=-\vec J\cdot\vec E$。
- [ ] 会判断辐射压吸收 $I/c$、反射 $2I/c$。
- [ ] 至少自己重做 Exercise 14.1 和 14.2；如果仍有时间，再复做 14.3 / 14.4。

### 需要会推导到什么程度？

**优先会：** 位移电流的电容器推法；比较波动方程得 $c$；平面波法拉第定律得 $B_0=E_0/c$；给出坡印廷矢量来源与意义。  
**可以稍后：** 从矢量恒等式完整推导坡印廷定理、磁荷假设及辐射边界条件；不能凭此推断老师绝不会考这些内容。

## 7. 常见错误

1. 把位移电流当作电子穿过极板间真空。
2. 看到 $E\ne0$ 就断定 $J_d\ne0$；真正条件是 $\partial_tE\ne0$。
3. 用 $I_{\rm enc}=I$ 求半径小于极板半径的电容器内部磁场，而忘记按面积比例取电流。
4. 在电磁波题把 $E$、$B$ 想成不同相位，或把波的传播方向写成 $\vec B\times\vec E$。
5. 把 $\vec S$（W/m²）和 $\vec J$（A/m²）混淆。
6. 忘了光强 $\langle S\rangle$ 有周期平均的 $1/2$。
7. 将 $\nabla\times\vec B=\mu_0\vec J$ 误用于任意时变电场。
8. 在角动量题只算一个带电壳，或者遗漏内外壳带电符号相反。

---
*备注：14.1、14.3、14.4 的解题路线已在对话中演示；本文件不代表所有内容都已独立掌握。后续按实际做题表现更新状态。*
