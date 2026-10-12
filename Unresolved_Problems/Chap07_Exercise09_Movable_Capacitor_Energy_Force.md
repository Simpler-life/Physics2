# Chap07 Exercise 9 — Movable Parallel-Plate Capacitor（待处理）

## 题目概述

一个真空平行板电容器，极板面积为 $A$，板间距为 $d$。下板固定，上板可以沿垂直极板方向缓慢移动。忽略边缘效应，并规定“增大 $d$”的方向为力 $F$ 的正方向。

题目分两种情况：

1. 两极板隔离，电荷固定为 $+Q$ 和 $-Q$；
2. 两极板接理想电池，电势差固定为 $V$。

要求比较两种情况下电容器储能与电场力，并特别解释：为什么固定电压时直接使用

```math
F=-\frac{dU}{dd}
```

会给出错误符号。

---

## 已经理解的内容

平行板电容：

```math
C(d)=\frac{\varepsilon_0 A}{d}.
```

### (a) 隔离极板：固定 $Q$

电容器能量：

```math
U(d)
=
\frac{Q^2}{2C}
=
\frac{Q^2d}{2\varepsilon_0 A}.
```

因此：

```math
\frac{dU}{dd}
=
\frac{Q^2}{2\varepsilon_0 A}.
```

由于此时没有电池与系统交换能量，电场力为：

```math
F
=
-\frac{dU}{dd}
=
-\frac{Q^2}{2\varepsilon_0 A}.
```

负号表示电场力使 $d$ 减小，即两极板相互吸引。

### (b) 接理想电池：固定 $V$

电容器能量：

```math
U(d)
=
\frac12CV^2
=
\frac{\varepsilon_0 A V^2}{2d}.
```

因此：

```math
dU
=
-\frac{\varepsilon_0 A V^2}{2d^2}\,dd.
```

同时：

```math
Q=CV=\frac{\varepsilon_0 A V}{d},
```

所以：

```math
dQ
=
-\frac{\varepsilon_0 A V}{d^2}\,dd.
```

电池做功：

```math
dW_B
=
V\,dQ
=
-\frac{\varepsilon_0 A V^2}{d^2}\,dd.
```

用能量守恒：

```math
dU=dW_B+dW_{\rm ext},
```

而

```math
dW_{\rm ext}=-F\,dd.
```

所以：

```math
dU=dW_B-F\,dd.
```

得到：

```math
F
=
-\frac{\varepsilon_0 A V^2}{2d^2}.
```

---

## 当前真正需要后续处理的概念

虽然目前可以完成代数推导，但以下概念还没有完全吃透：

1. **为什么固定 $Q$ 时可以直接使用 $F=-dU/dd$，固定 $V$ 时却不行。**
2. **系统边界的选择：**
   - 只把“电容器”当系统时，固定 $V$ 情况下电池会与它交换能量；
   - 因此电容器储能 $U$ 的变化不再等于机械功的负值。
3. **电池做功 $dW_B=V\,dQ$ 的符号意义：**
   - 当 $d$ 增大时 $dQ<0$；
   - 因而 $dW_B<0$，表示能量从电容器/电场回到电池。
4. **为什么直接计算**
   
```math
-\frac{dU}{dd}
```

   在固定 $V$ 情况下会得到正号，错误地暗示斥力。
5. **更一般的能量法：**
   - 在有外部电源保持某个物理量固定时，怎样正确选择“势能”或完整系统能量；
   - 固定电荷与固定电势边界条件为什么会导致不同的能量表达和求力方法。

---

## 当前结论

固定电荷：

```math
\boxed{
F=-\frac{Q^2}{2\varepsilon_0 A}
}
```

固定电压：

```math
\boxed{
F=-\frac{\varepsilon_0 A V^2}{2d^2}
}
```

利用

```math
Q=CV=\frac{\varepsilon_0 A}{d}V
```

可验证两种表达在同一瞬间描述的是同一个吸引力。

后续复习重点不是重新算公式，而是彻底理解：

> **什么时候可以直接使用 $F=-dU/dx$，什么时候必须把外部能量源的功也计入能量守恒。**
