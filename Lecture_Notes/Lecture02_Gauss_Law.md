# Lecture 2 学习记录：Electric Flux and Gauss' Law

> 状态：✅ 已完成到作业可用水平  
> 核心目标：会用对称性选择 Gaussian surface，并处理球对称、柱对称和平面对称的典型题。

## 1. Electric Flux

电通量定义：

```math
\Phi_E=\int \vec E\cdot d\vec A
```

对于闭合曲面：

```math
\Phi_E=\oint \vec E\cdot d\vec A
```

### 面积向量的方向

```math
d\vec A=\hat n\,dA
```

其中：

- $dA$ 是小面积，没有方向；
- $d\vec A$ 是面积向量；
- 对于闭合曲面，$d\vec A$ 规定为**沿曲面外法线方向指向外侧**。

### 点积的意义

```math
\vec E\cdot d\vec A
=
E\,dA\cos\theta
```

其中 $\theta$ 是 $\vec E$ 与 $d\vec A$ 之间的夹角。

因此：

- 电场向外穿出表面：通量为正；
- 电场向内穿入表面：通量为负；
- 电场沿表面切向掠过：通量为 0。

## 2. 如何理解曲面积分

积分的统一思想：

> 积分就是把很多很小的贡献加起来。

因此：

```math
\int dA
```

表示把所有小面积 $dA$ 加起来。

对一个半径为 $r$ 的球面：

```math
\oint dA=4\pi r^2
```

如果由于球对称性，球面上电场大小处处相同，且 $\vec E$ 与 $d\vec A$ 同向，则：

```math
\oint \vec E\cdot d\vec A
=
\oint E\,dA
=
E\oint dA
=
E(4\pi r^2)
```

这里能把 $E$ 提到积分号外，是因为同一个 Gaussian sphere 上 $E$ 的大小相同。

## 3. Gauss' Law

```math
\boxed{
\oint \vec E\cdot d\vec A
=
\frac{Q_{\rm enc}}{\varepsilon_0}
}
```

其中 $Q_{\rm enc}$ 是闭合 Gaussian surface 内包住的净电荷。

重要：

```math
Q_{\rm enc}=0
```

只能直接推出：

```math
\oint \vec E\cdot d\vec A=0
```

**不能一般性地直接推出 $\vec E=0$。**

只有在额外对称性足够强，使得 $E$ 可以从积分中提出时，才能进一步得到局部电场。

## 4. 均匀带电 spherical shell

设半径为 $R$ 的球壳，总电荷 $Q$ 均匀分布在球壳表面。

### 4.1 壳外：$r>R$

取与球壳同心、半径为 $r$ 的 Gaussian sphere。

由于球对称性：

- $\vec E$ 只能沿径向；
- 同一个半径 $r$ 上，$E$ 的大小相同；
- $d\vec A$ 沿径向向外。

所以：

```math
\oint \vec E\cdot d\vec A
=
E(4\pi r^2)
```

此时：

```math
Q_{\rm enc}=Q
```

Gauss 定律给出：

```math
E(4\pi r^2)
=
\frac{Q}{\varepsilon_0}
```

因此：

```math
\boxed{
E(r)
=
\frac{1}{4\pi\varepsilon_0}
\frac{Q}{r^2}
}
\qquad (r>R)
```

方向：

- $Q>0$：沿 $\hat r$ 径向向外；
- $Q<0$：与 $\hat r$ 反向，径向向内。

其中 $\hat r$ 定义为**从球心指向观察点**。

### 4.2 壳内：$r<R$

取与球壳同心、半径为 $r$ 的 Gaussian sphere。

因为所有真实电荷都在半径 $R$ 的球壳表面，所以：

```math
Q_{\rm enc}=0
```

Gauss 定律：

```math
\oint \vec E\cdot d\vec A=0
```

但这里不能只凭 $Q_{\rm enc}=0$ 就直接说 $E=0$。

关键还要使用**球对称性**：

- 球面上所有点等价，因此 $E$ 的大小处处相同；
- 若存在电场，方向只能沿径向；
- 因而 $\vec E\parallel d\vec A$。

所以：

```math
\oint \vec E\cdot d\vec A
=
E\oint dA
=
E(4\pi r^2)
```

结合 Gauss 定律：

```math
E(4\pi r^2)=0
```

由于 $r>0$ 时 $4\pi r^2\neq0$，得到：

```math
\boxed{E=0}
\qquad (r<R)
```

最重要的逻辑：

```math
\boxed{
Q_{\rm enc}=0
+
\text{spherical symmetry}
\Rightarrow
E=0
}
```

而不是错误地记成：

```math
Q_{\rm enc}=0\Rightarrow E=0
```

后者对于一般电场分布并不成立。

## 5. 当前 Gauss 题解题框架

```math
\text{判断对称性}
\rightarrow
\text{选 Gaussian surface}
\rightarrow
\text{判断 }\vec E\text{ 与 }d\vec A\text{ 的方向}
\rightarrow
\oint\vec E\cdot d\vec A
\rightarrow
Q_{\rm enc}
```

使用 Gauss 定律真正的关键，是选到一个能利用对称性把 $E$ 从积分中提出的 Gaussian surface。


## 6. 典型对称体系补充

### 均匀带电实心球

球外 $r>R$：

```math
E(r)=\frac{1}{4\pi\varepsilon_0}\frac{Q}{r^2}
```

球内 $r<R$ 时，均匀体电荷给出

```math
Q_{\rm enc}=Q\frac{r^3}{R^3}
```

所以

```math
\boxed{
E(r)=\frac{1}{4\pi\varepsilon_0}\frac{Q}{R^3}r
}
```

因此实心球内部 $E\propto r$。

### 无限长线电荷

线电荷密度为 $\lambda$。$\hat r$ 定义为从轴线垂直指向观察点。取同轴 Gaussian cylinder，只有侧面有通量：

```math
E(2\pi rL)=\frac{\lambda L}{\varepsilon_0}
```

因此

```math
\boxed{
E=\frac{\lambda}{2\pi\varepsilon_0r}
}
```

即 $E\propto 1/r$。

### 无限大带电平面

面电荷密度为 $\sigma$。电场垂直于平面。取 pillbox：

```math
2EA=\frac{\sigma A}{\varepsilon_0}
```

因此

```math
\boxed{
E=\frac{|\sigma|}{2\varepsilon_0}
}
```

方向：$\sigma>0$ 时两侧都远离平面，$\sigma<0$ 时两侧都指向平面。

理想无限平面的场强与距离无关。

### 两个无限平行带电平面

对 $+\sigma$ 与 $-\sigma$：

```math
\boxed{
E_{\rm inside}=\frac{\sigma}{\varepsilon_0},
\qquad
E_{\rm outside}=0
}
```

板间方向从正板指向负板。

## 7. Gauss 定律何时好用

Gauss 定律始终成立，但只有对称性足够强时才方便直接求 $E$。

典型匹配：

- spherical symmetry $\rightarrow$ sphere
- cylindrical symmetry $\rightarrow$ coaxial cylinder
- planar symmetry $\rightarrow$ pillbox

核心不是“有高斯面就能求 $E$”，而是能否利用对称性把 $E$ 从曲面积分中提出。

## 8. 作业识别框架

1. 判断对称性。
2. 选择匹配的 Gaussian surface。
3. 明确 $d\vec A$ 的方向。
4. 判断哪些表面通量为 0，哪些能写成 $E\,dA$。
5. 计算真正的 $Q_{\rm enc}$。
6. 最后用 Gauss 定律求 $E$。
