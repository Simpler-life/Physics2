# First-Order Linear ODE：RC 电路中的标准形式

> 状态：🟡 已遇到并会识别，但尚未系统掌握  
> 来源：Chapter 7 RC circuit  
> 当前目标：先能识别标准形式并用于作业；“为什么解一定含指数函数”与完整求解方法留待后续补齐。

## 1. 当前遇到的标准形式

在 RC 电路中，整理 Kirchhoff 方程后出现：

```math
\frac{dQ}{dt}
+
\frac{1}{\tau}Q
=
\text{constant}
```

它属于一阶线性常微分方程（first-order linear ODE）。

更一般地可以写成：

```math
y'(t)+ay=b
```

其中 $a,b$ 为常数。

## 2. 为什么引入 $\tau$

当方程中 $Q$ 前面的系数为某个常数 $a$ 时，可以定义：

```math
\frac{1}{\tau}=a
```

于是：

```math
\tau=\frac{1}{a}
```

在 RC 电路中，$\tau$ 称为 time constant（时间常数），通常具有：

```math
\tau=R_{\rm effective}C
```

的结构。

因此 $\tau$ 不是突然出现的新物理量，而是把微分方程写成容易识别的标准形式后定义出来的。

## 3. 当前会使用的解形式

对于：

```math
\frac{dQ}{dt}
+
\frac{1}{\tau}Q
=
\frac{Q_\infty}{\tau}
```

若初始值为 $Q(0)$，解可以写成：

```math
Q(t)
=
Q_\infty
+
\bigl(Q(0)-Q_\infty\bigr)e^{-t/\tau}
```

若电容初始未充电：

```math
Q(0)=0
```

则：

```math
\boxed{
Q(t)
=
Q_\infty
\left(
1-e^{-t/\tau}
\right)
}
```

## 4. 当前的物理识别方式

看到：

```math
\frac{dQ}{dt}
+
\frac{1}{\tau}Q
=
\frac{Q_\infty}{\tau}
```

可以先理解为：

> “变化率 + 当前状态 = 常数驱动”。

在 RC charging 中：

- $Q_\infty$ 是长时间后的最终电荷；
- $\tau$ 控制靠近最终状态的快慢；
- $e^{-t/\tau}$ 描述随时间衰减的“还没达到最终状态的部分”。

## 5. 尚未解决

目前只是会识别和套用，还没有系统掌握以下内容：

- 为什么这种方程的解一定出现 $e^{-t/\tau}$；
- 如何从微分方程本身推导通解；
- integrating factor（积分因子）方法；
- 齐次解 + 特解的结构；
- 初始条件如何严格决定积分常数。

这些内容保留在 [Pending/Knowledge_TODO.md](../Pending/Knowledge_TODO.md) 中，后续需要时再系统学习。
