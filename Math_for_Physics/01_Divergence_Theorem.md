# Divergence Theorem（散度定理）

> 这一页记录在普通物理中已经实际用到的散度定理，以及它如何把“整体的通量”转换成“局部的散度”。

## 1. 核心公式

散度定理（Divergence Theorem / Gauss's Theorem）：

```math
\iiint_V (\nabla\cdot\vec F)\,dV
=
\oiint_S \vec F\cdot d\vec A
```

其中：

- $V$ 是一个体积；
- $S$ 是包围 $V$ 的闭合曲面；
- $d\vec A$ 默认指向闭合曲面的外侧；
- $\nabla\cdot\vec F$ 表示向量场 $\vec F$ 在某一点的 divergence（散度）。

直观理解：

> 把一个体积内部每一点的“向外发散程度”全部加起来，等于这个向量场穿过整个边界向外流出的总量。

---

## 2. 为什么会有这个定理

可以把一个大体积分成很多很小的小盒子。

相邻小盒子的公共面上，一个盒子“流出去”的量正好是另一个盒子“流进来”的量，因此内部公共面的贡献会互相抵消。

最后只剩下最外层边界上的净流出量。

所以：

```math
\text{内部所有局部净流出之和}
=
\text{整个边界的总净流出}
```

---

## 3. 和 Gauss's Law 的关系

Gauss's law 的积分形式是：

```math
\oiint_S \vec E\cdot d\vec A
=
\frac{Q_{\mathrm{enc}}}{\varepsilon_0}
```

而体积中的总电荷为：

```math
Q_{\mathrm{enc}}
=
\iiint_V \rho\,dV
```

因此：

```math
\oiint_S \vec E\cdot d\vec A
=
\iiint_V \frac{\rho}{\varepsilon_0}\,dV
```

对左边使用散度定理：

```math
\iiint_V (\nabla\cdot\vec E)\,dV
=
\iiint_V \frac{\rho}{\varepsilon_0}\,dV
```

因为体积 $V$ 可以任意选择，所以得到 Gauss's law 的微分形式：

```math
\boxed{
\nabla\cdot\vec E
=
\frac{\rho}{\varepsilon_0}
}
```

物理意义：电荷是电场的“源”。

---

## 4. 和 Continuity Equation 的关系

电荷守恒的整体形式是：

```math
\frac{d}{dt}
\iiint_V \rho\,dV
=
-
\oiint_S \vec J\cdot d\vec A
```

其中：

- 左边是区域内总电荷的变化率；
- 右边是“净流出电流”的负值。

对右边使用散度定理：

```math
\oiint_S \vec J\cdot d\vec A
=
\iiint_V (\nabla\cdot\vec J)\,dV
```

于是：

```math
\iiint_V
\left(
\frac{\partial\rho}{\partial t}
+
\nabla\cdot\vec J
\right)dV
=
0
```

因为体积 $V$ 可以任意选择，所以：

```math
\boxed{
\frac{\partial\rho}{\partial t}
+
\nabla\cdot\vec J
=
0
}
```

也就是：

```math
\boxed{
\frac{\partial\rho}{\partial t}
=
-
\nabla\cdot\vec J
}
```

物理意义：

> 如果某一点附近的电流在向外发散，那里储存的电荷密度就会下降。

---

## 5. 和之前几种积分的区分

### 线积分

```math
\int_C \vec E\cdot d\vec l
```

沿一条路径累加，例如用来计算 potential difference。

### 曲面积分

```math
\int_S \vec J\cdot d\vec A
```

计算穿过一个面的电流。

### 闭合曲面积分

```math
\oiint_S \vec E\cdot d\vec A
```

计算穿过整个闭合曲面的 electric flux。

散度定理连接的是：

```math
\boxed{
\text{闭合曲面积分}
\longleftrightarrow
\text{体积分中的 divergence}
}
```

---

## 6. 当前需要记住的最小版本

```math
\boxed{
\iiint_V (\nabla\cdot\vec F)\,dV
=
\oiint_S \vec F\cdot d\vec A
}
```

以及一句话：

> **局部净流出全部加起来 = 整个边界的总净流出。**
