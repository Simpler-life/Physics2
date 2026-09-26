# Lecture 4 学习记录：Triangle of Electrostatics

> 状态：✅ 已完成当前主线内容到作业可用水平  
> 本 Lecture 核心：用向量微积分把 electric potential $V$、electric field $\vec E$ 与 charge density $\rho$ 连起来。

## 1. Electrostatics Triangle

本 Lecture 的三条核心关系：

```math
\boxed{
\vec E=-\nabla V
}
```

```math
\boxed{
\nabla\cdot\vec E
=
\frac{\rho}{\varepsilon_0}
}
```

```math
\boxed{
\nabla^2V
=
-\frac{\rho}{\varepsilon_0}
}
```

可以理解为：

```math
V
\longrightarrow
\vec E
\longrightarrow
\rho
```

以及：

```math
V
\longrightarrow
\rho
```

## 2. Gradient

在 Cartesian coordinates 中：

```math
\boxed{
\nabla
=
\hat x\frac{\partial}{\partial x}
+
\hat y\frac{\partial}{\partial y}
+
\hat z\frac{\partial}{\partial z}
}
```

对标量函数 $f(x,y,z)$：

```math
\boxed{
\nabla f
=
\frac{\partial f}{\partial x}\hat x
+
\frac{\partial f}{\partial y}\hat y
+
\frac{\partial f}{\partial z}\hat z
}
```

### 偏导的含义

例如：

```math
f(x,y,z)=x^2+3y^2+5z
```

则：

```math
\frac{\partial f}{\partial x}=2x
```

```math
\frac{\partial f}{\partial y}=6y
```

```math
\frac{\partial f}{\partial z}=5
```

所以：

```math
\nabla f
=
2x\hat x+6y\hat y+5\hat z
```

### Gradient 的方向

```math
\boxed{
\nabla f
\text{ 指向 }f\text{ 增长最快的方向}
}
```

并且 $\nabla f$ 垂直于：

```math
f=\text{constant}
```

这样的等值面。

## 3. 从 Electric Potential 得到 Electric Field

Lecture 3 已知：

```math
dV
=
-\vec E\cdot d\vec r
```

而 gradient 满足：

```math
dV
=
\nabla V\cdot d\vec r
```

对任意 $d\vec r$ 比较两式：

```math
\boxed{
\vec E=-\nabla V
}
```

因此：

- $\nabla V$ 指向电势上升最快的方向；
- $\vec E$ 指向电势下降最快的方向；
- 二者方向相反。

在 Cartesian coordinates：

```math
\boxed{
\vec E
=
-\frac{\partial V}{\partial x}\hat x
-\frac{\partial V}{\partial y}\hat y
-\frac{\partial V}{\partial z}\hat z
}
```

这也是 Chapter 3 Exercise 2 中从 $V(x,y,z)$ 求 $\vec E$ 的直接公式。

## 4. Divergence

若：

```math
\vec A
=
A_x\hat x+A_y\hat y+A_z\hat z
```

则 divergence 定义为：

```math
\boxed{
\nabla\cdot\vec A
=
\frac{\partial A_x}{\partial x}
+
\frac{\partial A_y}{\partial y}
+
\frac{\partial A_z}{\partial z}
}
```

对电场：

```math
\boxed{
\nabla\cdot\vec E
=
\frac{\partial E_x}{\partial x}
+
\frac{\partial E_y}{\partial y}
+
\frac{\partial E_z}{\partial z}
}
```

divergence 是标量。

### 物理意义

可以把 $\nabla\cdot\vec E$ 理解为：

> 某一点附近，单位体积内电场的“净流出程度”。

- 正散度：像源头，电场整体向外发散；
- 负散度：像汇，电场整体向内汇聚；
- 零散度：没有局部净流出。

## 5. Differential Form of Gauss' Law

Lecture 2 的积分形式：

```math
\oint \vec E\cdot d\vec A
=
\frac{Q_{\rm enc}}{\varepsilon_0}
```

局部化后得到：

```math
\boxed{
\nabla\cdot\vec E
=
\frac{\rho}{\varepsilon_0}
}
```

其中 $\rho$ 是该位置的体电荷密度。

因此：

```math
\rho>0
\Rightarrow
\nabla\cdot\vec E>0
```

```math
\rho<0
\Rightarrow
\nabla\cdot\vec E<0
```

```math
\rho=0
\Rightarrow
\nabla\cdot\vec E=0
```

但注意：

```math
\boxed{
\nabla\cdot\vec E=0
\not\Rightarrow
\vec E=0
}
```

这与 Lecture 2 中 $Q_{\rm enc}=0$ 不一定推出局部 $E=0$ 的思想一致。

## 6. 一个简单 divergence 例子

若：

```math
\vec E
=
ax\hat x+by\hat y+cz\hat z
```

则：

```math
\nabla\cdot\vec E
=
a+b+c
```

所以：

```math
\boxed{
\rho
=
\varepsilon_0(a+b+c)
}
```

## 7. Laplacian

定义：

```math
\boxed{
\nabla^2
=
\nabla\cdot\nabla
}
```

在 Cartesian coordinates 中，对标量函数 $V$：

```math
\boxed{
\nabla^2V
=
\frac{\partial^2V}{\partial x^2}
+
\frac{\partial^2V}{\partial y^2}
+
\frac{\partial^2V}{\partial z^2}
}
```

## 8. Poisson's Equation

由：

```math
\vec E=-\nabla V
```

和：

```math
\nabla\cdot\vec E
=
\frac{\rho}{\varepsilon_0}
```

得到：

```math
\nabla\cdot(-\nabla V)
=
\frac{\rho}{\varepsilon_0}
```

所以：

```math
\boxed{
\nabla^2V
=
-\frac{\rho}{\varepsilon_0}
}
```

这就是 Poisson's equation。

## 9. Laplace's Equation

如果某区域没有体电荷：

```math
\rho=0
```

则 Poisson's equation 退化为：

```math
\boxed{
\nabla^2V=0
}
```

这就是 Laplace's equation。

## 10. Curl

对 vector field $\vec A$，可以定义：

```math
\nabla\times\vec A
```

称为 curl。

静电场满足：

```math
\boxed{
\nabla\times\vec E=0
}
```

原因是：

```math
\vec E=-\nabla V
```

而 gradient 的 curl 恒为 0：

```math
\nabla\times(\nabla V)=0
```

所以静电场是 irrotational field。

这与 Lecture 3 的闭合线积分关系：

```math
\oint \vec E\cdot d\vec l=0
```

是同一物理性质的不同表达。

## 11. Lecture 4 作业识别框架

看到题目时优先判断已知量：

1. 已知 $V(x,y,z)$，求 $\vec E$：

```math
\boxed{
\vec E=-\nabla V
}
```

2. 已知 $\vec E(x,y,z)$，求 $\rho$：

```math
\boxed{
\rho
=
\varepsilon_0\nabla\cdot\vec E
}
```

3. 已知 $V(x,y,z)$，直接求 $\rho$：

```math
\boxed{
\rho
=
-\varepsilon_0\nabla^2V
}
```

4. 无电荷区域：

```math
\boxed{
\nabla^2V=0
}
```

5. 判断静电场的基本性质：

```math
\boxed{
\nabla\times\vec E=0
}
```

## 12. 本 Lecture 的核心图景

```math
\boxed{
V
\overset{-\nabla}{\longrightarrow}
\vec E
}
```

```math
\boxed{
\vec E
\overset{\nabla\cdot}{\longrightarrow}
\rho
}
```

```math
\boxed{
V
\overset{\nabla^2}{\longrightarrow}
\rho
}
```

这三条关系构成课程所说的 Triangle of Electrostatics。
