# First-Order Linear ODE：一阶微分方程与 RC / RL 暂态

> 状态：🟡 已开始学习分离变量法及其数学依据；尚未通过独立练习确认熟练掌握。  
> 来源：Chapter 7 RC circuit、RL 暂态讨论。  
> 目标：能从电路方程出发，亲手推出指数衰减、指数增长，并用初始条件确定常数。

## 1. 什么是一阶微分方程？

普通方程求一个数；微分方程求随时间变化的函数，例如电荷 $Q(t)$ 或电流 $I(t)$。

最常见的常系数形式是：

```math
\frac{dy}{dt}+ay=b
```

其中 $a,b$ 为常数，$y=y(t)$。在 RC、RL 暂态中通常 $a>0$。

## 2. 为什么 $dQ/dt$ 好像能够像分数一样移项？

例如：

```math
\frac{dQ}{dt}=-3Q
```

分离变量法常写成：

```math
\frac{1}{Q}\,dQ=-3\,dt
```

**注意：导数不是普通分数，不能对任何微分方程都这样随意拆开。** 此处操作之所以正确，是因为链式法则和换元积分。

严格解释（先假设 $Q(t)\neq0$）：

```math
\frac{1}{Q(t)}\frac{dQ}{dt}=-3
```

因为：

```math
\frac{d}{dt}\ln|Q(t)|
=\frac{1}{Q(t)}\frac{dQ}{dt}
```

所以对时间积分：

```math
\ln|Q(t)|=-3t+C
```

再取指数，并把常数及符号合并：

```math
Q(t)=Ae^{-3t}
```

若已知 $Q(0)=Q_0$，则 $A=Q_0$，所以：

```math
\boxed{Q(t)=Q_0e^{-3t}}
```

**不要漏掉零解：** 分离变量时除以 $Q$，暂时排除了 $Q=0$；原方程还有 $Q(t)\equiv0$ 这个解。将 $A=0$ 纳入最终表达式即可。

### 分离变量法适用的常见结构

如果方程能够写成：

```math
\frac{dy}{dt}=f(y)g(t)
```

那么在 $f(y)\neq0$ 的区间可以写成：

```math
\frac{dy}{f(y)}=g(t)\,dt
```

然后对两边积分；还需检查被除掉的 $f(y)=0$ 对应的常数解。

## 3. 例一：RL 电流自然衰减

理想电感 $L$ 和电阻 $R$ 构成无电源的闭合放电回路，且 $R,L$ 都为正的常数。

Kirchhoff 电压定律：

```math
L\frac{dI}{dt}+RI=0
```

移项：

```math
\frac{dI}{dt}=-\frac{R}{L}I
```

分离变量（先在 $I\neq0$ 的区间）：

```math
\frac{dI}{I}=-\frac{R}{L}\,dt
```

两边积分：

```math
\ln|I|=-\frac{R}{L}t+C
```

取指数，并使用初始条件 $I(0)=I_0$：

```math
\boxed{I(t)=I_0e^{-Rt/L}}
```

其中时间常数：

```math
\boxed{\tau_L=\frac{L}{R}}
```

于是 $I(t)=I_0e^{-t/\tau_L}$。**时间常数是 $L/R$，不是 $LR$。**

## 4. 例二：RL 接通恒定电源后的电流增长

串联电池电动势 $\mathcal E$、电阻 $R$、电感 $L$，电池电压恒定：

```math
\mathcal E=RI+L\frac{dI}{dt}
```

整理后：

```math
\frac{dI}{dt}=\frac{\mathcal E-RI}{L}
```

分离变量：

```math
\frac{dI}{\mathcal E-RI}=\frac{dt}{L}
```

积分时左侧用换元 $u=\mathcal E-RI$，因此 $du=-R\,dI$：

```math
-\frac{1}{R}\ln|\mathcal E-RI|
=\frac{t}{L}+C
```

整理得到：

```math
I(t)=\frac{\mathcal E}{R}+Ae^{-Rt/L}
```

若刚闭合开关时 $I(0)=0$，则：

```math
0=\frac{\mathcal E}{R}+A
\quad\Longrightarrow\quad
A=-\frac{\mathcal E}{R}
```

所以：

```math
\boxed{I(t)=\frac{\mathcal E}{R}\left(1-e^{-Rt/L}\right)}
```

验证：$t=0$ 时 $I=0$；$t\to\infty$ 时 $I\to\mathcal E/R$，符合物理直觉。

特殊情况：若某一步除以 $\mathcal E-RI$，也应检查稳态常数解 $I(t)=\mathcal E/R$；它包含在最终解的 $A=0$ 情况中。

## 5. 考试可复用的通用模板

对于常数 $a>0$、$b$：

```math
\frac{dy}{dt}+ay=b
```

先求稳态（令 $dy/dt=0$）：

```math
y_\infty=\frac{b}{a}
```

再令 $z=y-y_\infty$。因为 $y_\infty$ 是常数：

```math
\frac{dz}{dt}
=\frac{dy}{dt}
=-a(y-y_\infty)
=-az
```

于是回到刚学过的纯衰减方程：

```math
z(t)=z(0)e^{-at}
```

代回 $z=y-y_\infty$，得到：

```math
\boxed{
y(t)=y_\infty+[y(0)-y_\infty]e^{-at}
}
```

定义时间常数 $\tau=1/a$：

```math
\boxed{
y(t)=y_\infty+[y(0)-y_\infty]e^{-t/\tau}
}
```

**考试做题顺序：**

1. 先依据 Kirchhoff 定律或其他物理规律列出微分方程；
2. 确认方程能否写成 $y'+ay=b$，且系数是常数；
3. 求初值 $y(0)$、稳态值 $y_\infty$、时间常数 $\tau=1/a$；
4. 用模板写出解；不放心时按“分离变量 → 积分 → 初始条件”完整推导；
5. 检查 $t=0$ 与 $t\to\infty$ 两个极限。

常见例子：RC 电荷衰减中 $\tau_{RC}=RC$；RL 电流衰减中 $\tau_{RL}=L/R$。**复杂 RLC 二阶电路不一定适用这条一阶指数模板。**

## 6. 自测（尚待独立完成）

给定：

```math
\frac{dQ}{dt}=-3Q,\qquad Q(0)=5
```

不看前文，尝试依次写出：

- 分离变量后的式子；
- 两边积分后的式子；
- 满足初始条件的 $Q(t)$。

**当前掌握状态：** 已理解“为什么能分离变量”的链式法则依据，并看过衰减与增长方程的完整解法；还没有独立完成自测，因此暂不标记为 ✅。
