# Lecture 1 学习记录：Coulomb's Law and Electric Field

> 状态：✅ 已完成到作业可用水平  
> 学习目标：能识别并处理点电荷、连续电荷、远场近似、电偶极子与均匀电场中的典型问题。

## 1. 电荷与基本关系

电荷量子化：

```math
q=ne
```

其中 $e$ 为基本电荷。

电荷守恒：总电荷不会凭空产生或消失。

## 2. Coulomb 定律

两点电荷之间的静电力：

```math
\vec F_{12}
=
\frac{1}{4\pi\varepsilon_0}
\frac{q_1q_2}{r_{12}^2}
\hat r_{12}
```

### 方向记号

若采用“从 1 指向 2”的约定：

```math
\vec r_{12}=\vec r_2-\vec r_1
```

```math
r_{12}=|\vec r_{12}|
```

```math
\hat r_{12}
=
\frac{\vec r_{12}}{|\vec r_{12}|}
```

要区分：

- $\vec r$：位置/位移向量，有方向
- $r=|\vec r|$：距离/长度，没有方向
- $\hat r$：单位方向向量，表示方向

并且：

```math
\frac{\hat r}{r^2}
=
\frac{\vec r}{r^3}
```

## 3. 叠加原理

多个点电荷共同作用时，总力或总电场是各自贡献的**向量和**：

```math
\vec F_{\text{total}}=\sum_i \vec F_i
```

```math
\vec E_{\text{total}}=\sum_i \vec E_i
```

## 4. 电场定义

```math
\vec E=\frac{\vec F}{q_0}
```

反过来：

```math
\vec F=q\vec E
```

点电荷 $Q$ 产生的电场：

```math
\vec E
=
\frac{1}{4\pi\varepsilon_0}
\frac{Q}{r^2}\hat r
```

### 方向

这里 $\hat r$ 定义为**从源电荷 $Q$ 指向观察点**。

- $Q>0$：$\vec E$ 与 $\hat r$ 同向，电场向外。
- $Q<0$：$\vec E$ 与 $\hat r$ 反向，电场指向负电荷。

## 5. 连续电荷：从求和到积分

核心思想：

> 把连续带电体切成无穷多个小电荷 $dq$，计算每个 $dq$ 产生的 $d\vec E$，再全部相加。

```math
d\vec E
=
\frac{1}{4\pi\varepsilon_0}
\frac{dq}{r^2}\hat r
```

```math
\vec E=\int d\vec E
```

三种常见电荷密度：

### 线电荷

```math
\lambda=\frac{dq}{dl}
\qquad\Rightarrow\qquad
dq=\lambda\,dl
```

### 面电荷

```math
\sigma=\frac{dq}{dA}
\qquad\Rightarrow\qquad
dq=\sigma\,dA
```

### 体电荷

```math
\rho=\frac{dq}{dV}
\qquad\Rightarrow\qquad
dq=\rho\,dV
```

## 6. 对称性

连续电荷积分中，不能只对电场大小直接求和，因为电场是向量。

常见做法：

1. 先判断哪些方向的分量由于对称性两两抵消；
2. 只保留不会抵消的分量；
3. 对该分量积分。

## 7. 均匀带电圆盘轴线上电场

半径 $R$、面电荷密度 $\sigma$ 的均匀带电圆盘，在中心轴线上距离中心 $z$ 的位置求电场。

把圆盘切成半径 $r$、厚度 $dr$ 的同心圆环：

```math
dA=2\pi r\,dr
```

```math
dq=\sigma dA=2\pi\sigma r\,dr
```

观察点到圆环任一点的距离：

```math
s=\sqrt{z^2+r^2}
```

由于横向分量对称抵消，只剩 $z$ 分量：

```math
dE_z=dE\cos\theta
```

```math
\cos\theta=\frac{z}{\sqrt{z^2+r^2}}
```

因此

```math
dE_z
=
\frac{\sigma z}{2\varepsilon_0}
\frac{r\,dr}{(z^2+r^2)^{3/2}}
```

积分得到：

```math
\boxed{
\vec E
=
\frac{\sigma}{2\varepsilon_0}
\left(
1-\frac{z}{\sqrt{z^2+R^2}}
\right)\hat z
}
```

连续电荷题的通用流程：

```math
\text{选微元}
\rightarrow
dq
\rightarrow
d\vec E
\rightarrow
\text{利用对称性取分量}
\rightarrow
\int d\vec E
```

## 8. 远场近似与 leading term

当 $z\gg R$ 时：

```math
\frac{R^2}{z^2}\ll1
```

使用二项式近似：

```math
(1+x)^n\approx1+nx,\qquad |x|\ll1
```

于是：

```math
\left(1+\frac{R^2}{z^2}\right)^{-1/2}
\approx
1-\frac{R^2}{2z^2}
```

代回圆盘电场：

```math
E_z
\approx
\frac{\sigma R^2}{4\varepsilon_0z^2}
```

又因为

```math
Q=\sigma\pi R^2
```

所以：

```math
\boxed{
E_z
\approx
\frac{1}{4\pi\varepsilon_0}
\frac{Q}{z^2}
}
```

物理意义：当观察距离远大于带电体尺寸时，远处主要“看见”总电荷，圆盘可近似为点电荷。

## 9. Electric Dipole

电偶极子由两个等量异号电荷 $-q$ 与 $+q$ 构成。

偶极矩定义：

```math
\boxed{\vec p=q\vec d}
```

### 方向定义

**$\vec d$ 从 $-q$ 指向 $+q$，因此 $\vec p$ 也从负电荷指向正电荷。**

设偶极子中心为参考点，观察点的位置向量定义为：

```math
\vec r=\text{从 dipole 中心指向观察点}
```

```math
r=|\vec r|,
\qquad
\hat r=\frac{\vec r}{r}
```

其中：

- $\vec r$ 有方向；
- $r$ 只是距离；
- $\hat r$ 给出从偶极子中心到观察点的方向。

远场 $r\gg d$ 时：

```math
\boxed{
\vec E(\vec r)
=
\frac{1}{4\pi\varepsilon_0r^3}
\left[
3(\vec p\cdot\hat r)\hat r-\vec p
\right]
}
```

因此：

```math
E_{\text{dipole}}\sim \frac1{r^3}
```

### 轴线上

观察点位于 $\vec p$ 所在直线上。

若观察点在 $\vec p$ 指向的一侧：

```math
\boxed{
\vec E_{\rm axial}
=
\frac{1}{4\pi\varepsilon_0}
\frac{2p}{r^3}\hat r
}
```

方向沿偶极矩向外的一侧；若观察点在另一侧，应结合 $\hat r$ 和完整矢量式判断。

### 中垂线上（equatorial line）

此时：

```math
\vec p\perp\vec r
```

所以：

```math
\vec p\cdot\hat r=0
```

完整矢量结果：

```math
\boxed{
\vec E_{\rm equatorial}
=
-\frac{1}{4\pi\varepsilon_0}
\frac{\vec p}{r^3}
}
```

因此大小：

```math
E_{\rm equatorial}
=
\frac{1}{4\pi\varepsilon_0}
\frac{p}{r^3}
```

方向：**与 $\vec p$ 反向。**

## 10. 带电粒子在均匀电场中

核心关系：

```math
\boxed{\vec F=q\vec E}
```

方向：

- $q>0$：$\vec F$ 与 $\vec E$ 同向；
- $q<0$：$\vec F$ 与 $\vec E$ 反向。

若电场均匀：

```math
\vec a=\frac{q\vec E}{m}
```

若粒子初速度与电场垂直：

```math
x=v_0t
```

```math
y=\frac12\frac{qE}{m}t^2
```

消去 $t$：

```math
\boxed{
y=\frac{qE}{2mv_0^2}x^2
}
```

轨迹为抛物线；若 $q<0$，弯曲方向与电场方向相反。

## 11. 偶极子在均匀电场中的力矩

均匀电场中，$+q$ 与 $-q$ 所受电场力大小相等、方向相反，所以净力为 0，但一般有力矩。

两个电荷相对偶极子中心的位置：

```math
\vec r_+=\frac{\vec d}{2},
\qquad
\vec r_-=-\frac{\vec d}{2}
```

受力：

```math
\vec F_+=q\vec E,
\qquad
\vec F_-=-q\vec E
```

单个电荷的力矩都带有 $1/2$：

```math
\vec\tau_+
=
\frac{\vec d}{2}\times q\vec E
```

```math
\vec\tau_-
=
\left(-\frac{\vec d}{2}\right)\times(-q\vec E)
```

两者方向相同，相加后 $1/2$ 消失：

```math
\vec\tau
=
q\vec d\times\vec E
```

利用 $\vec p=q\vec d$：

```math
\boxed{
\vec\tau=\vec p\times\vec E
}
```

大小：

```math
\boxed{
\tau=pE\sin\theta
}
```

其中 $\theta$ 是从 $\vec p$ 转到 $\vec E$ 的夹角。

方向：由 $\vec p\times\vec E$ 的**右手定则**确定。

这个力矩会使偶极子趋向于让 $\vec p$ 与 $\vec E$ 同向。

势能：

```math
\boxed{
U=-\vec p\cdot\vec E=-pE\cos\theta
}
```

稳定平衡：$\vec p\parallel\vec E$。

## 12. 本 Lecture 用到的向量运算

点积：

```math
\vec A\cdot\vec B=AB\cos\theta
```

结果是标量，用于描述两个向量沿彼此方向的投影关系。

叉积：

```math
|\vec A\times\vec B|=AB\sin\theta
```

结果是向量，方向由右手定则决定。

Lecture 1 中最直接的应用：

```math
\vec\tau=\vec p\times\vec E
```

## 13. 作业识别框架

看到题目先判断：

1. **离散点电荷**：$\vec E=\sum_i\vec E_i$
2. **连续带电体**：$dq\rightarrow d\vec E\rightarrow$ 对称性 $\rightarrow\int$
3. **远场**：检查“观察距离 $\gg$ 源尺寸”，考虑小量展开
4. **偶极子**：先写 $\vec p=q\vec d$，并标清 $\vec p$ 的方向
5. **粒子运动**：$\vec F=q\vec E$，再用牛顿运动学
6. **偶极子在均匀场中**：净力为 0，一般有 $\vec\tau=\vec p\times\vec E$

> 之后遇到任何有方向的物理量，笔记必须同时写清：**方向如何定义、单位向量指向哪里、最后结果方向如何判断**。
