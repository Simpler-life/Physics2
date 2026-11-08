# 2023 期中第 3 题：旋转带电球——角分布、电流环面积与积分范围

> **状态：🟡 第一轮独立作答完成，(a) 的角分布结果正确；(b) 面积选择错误；(c) 微元磁场基本算对，积分上下限和最终收尾待修正。尚未独立无提示重做整题。**
>
> **来源：** 2023 期中第 3 题及用户手写两页解答、后续核对题目中 $\sigma(\theta)=dq(\theta)/d\theta$ 的提问。
>
> **重要约定：** 本题使用的 $\sigma(\theta)$ 是**按极角分布的电荷量**，不是普通面电荷密度。关于 $J(\theta)$，本笔记按题目讨论中的“单位极角对应的电流” $J(\theta)=dI/d\theta$ 处理，勿与标准电流密度混淆；若原卷对 $J$ 有其他定义，应以原题为准。

## 1. 模型与三个几何量


<img width="878" height="1128" alt="df4ff2ce3b0ebf00d2ab3ef807d2dba8" src="https://github.com/user-attachments/assets/989fbaea-a318-4c80-8c96-48d0ffad6588" />


半径 $R$ 的薄球壳，表面均匀带总电荷 $Q$，以角速度 $\omega$ 绕穿过球心的轴匀速转动。设极角 $\theta$ 从旋转轴正方向量起，**北极到南极是 $0\le\theta\le\pi$**。

纬度圆环的半径：

```math
r_{\mathrm{ring}}=R\sin\theta
```

球面薄带的球面弧宽：

```math
d\ell=R\,d\theta
```

因此球面薄带面积：

```math
\boxed{dA_{\mathrm{band}}=(2\pi R\sin\theta)(R\,d\theta)
=2\pi R^2\sin\theta\,d\theta}
```

**另一种面积**是某个纬度电流环所围成的平面圆盘面积：

```math
\boxed{A_{\mathrm{loop}}=\pi r_{\mathrm{ring}}^2
=\pi R^2\sin^2\theta}
```

这是本题最核心的区分：

- 求 **薄带带电量**：使用球面薄带面积 $dA_{\mathrm{band}}$。
- 求 **薄环磁偶极矩**：使用电流环围成的面积 $A_{\mathrm{loop}}$，**不是**薄带面积。
- 求 **球心磁场**：把每条纬度环当作**位于球心轴线上**的圆形电流环。

## 2. (a) 正确的 $\sigma(\theta)$ 与 $J(\theta)$


<img width="966" height="1288" alt="image" src="https://github.com/user-attachments/assets/cf0b9760-73b7-4964-9983-93dca2e72de6" />

<img width="928" height="1066" alt="image" src="https://github.com/user-attachments/assets/2a3a809d-371e-45d6-8fc1-085d061e76d0" />


为避免符号相撞，把通常的面电荷密度记作 $\sigma_s$：

```math
\sigma_s=\frac{Q}{4\pi R^2}\qquad [\mathrm{C/m^2}]
```

薄带电荷：

```math
dq=\sigma_s\,dA_{\mathrm{band}}
=\frac Q2\sin\theta\,d\theta
```

**原题截图定义**：

```math
\boxed{\sigma(\theta)=\frac{dq}{d\theta}
=\frac Q2\sin\theta}
```

所以这里 **$\sigma(\theta)\neq dq$**；$\sigma(\theta)$ 是关于角度的分布函数，$dq=\sigma(\theta)d\theta$。弧度视为无量纲时数值上单位可简写 C，但概念上是每单位极角的电荷量。

球转动一圈的周期：

```math
T=\frac{2\pi}{\omega}
```

该薄带等效为电流环：

```math
dI=\frac{dq}{T}
=\frac{Q\omega}{4\pi}\sin\theta\,d\theta
```

若 $J(\theta)$ 按本题讨论理解为电流的角度分布，则：

```math
\boxed{J(\theta)=\frac{dI}{d\theta}
=\frac{Q\omega}{4\pi}\sin\theta}
```

**批改修正记录：** 先前辅导时曾把 $dq,dI$ 当成 (a) 最终要求，并说用户的 $\sigma(\theta),J(\theta)$ 写法不对。用户指出题目给出的 $\sigma(\theta)=dq/d\theta$ 后，确认用户原写的两个**角分布结果正确**。这处不能记成用户犯错。

另外，若讨论的是通常的表面电流密度，则它应记为 $\mathbf K$，大小为：

```math
K(\theta)=\sigma_s\,\omega R\sin\theta
=\frac{Q\omega}{4\pi R}\sin\theta
\qquad [\mathrm{A/m}]
```

它与上面的 $J(\theta)$ **不是同一个物理量**。

## 3. (b) 磁偶极矩：原解误把球面薄带面积代入 $IA$

原解用 $d\mu=J(\theta)\,dA_{\mathrm{band}}$。这里将两种面积、以及角分布函数和电流微元混为一谈。

正确方法：

```math
d\mu=dI\,A_{\mathrm{loop}}
=J(\theta)\,d\theta\cdot\pi R^2\sin^2\theta
```

得：

```math
d\mu=\frac{Q\omega R^2}{4}\sin^3\theta\,d\theta
```

从北极到南极积分：

```math
\mu=\frac{Q\omega R^2}{4}\int_0^\pi\sin^3\theta\,d\theta
```

由于：

```math
\int_0^\pi\sin^3\theta\,d\theta=\frac43
```

最终：

```math
\boxed{\mu=\frac{Q\omega R^2}{3}}
```

对于 $Q>0$，磁偶极矩沿角速度矢量方向；带电量变负时方向相反。

**原解第二个错误：** 把极角 $\theta$ 的范围写为 $0\to2\pi$。$2\pi$ 是方位角绕轴转一整圈的范围；**极角**从北极走到南极只需 $0\to\pi$。

## 4. (c) 球心磁场：中途微元基本正确，最终积分范围不对

每个纬度环的半径：

```math
r_{\mathrm{ring}}=R\sin\theta
```

环的平面到球心的轴向距离为：

```math
z=R\cos\theta
```

圆环轴线上磁场（由 Biot–Savart 定律积分得到）：

```math
dB_z=\frac{\mu_0\,dI\,r_{\mathrm{ring}}^2}
{2(r_{\mathrm{ring}}^2+z^2)^{3/2}}
```

由于 $r_{\mathrm{ring}}^2+z^2=R^2$：

```math
dB_z=\frac{\mu_0\,dI}{2R}\sin^2\theta
=\boxed{\frac{\mu_0Q\omega}{8\pi R}\sin^3\theta\,d\theta}
```

这是用户在第二页已经基本推到的表达式。

**注意：** 这里要先对**每个圆环的全部电流元**完成 Biot–Savart 环积分，才得出沿轴线的 $dB_z$；随后再对不同纬度环的 $\theta$ 积分。不能把环的 $dI$ 误当成 Biot–Savart 原式的线元 $I\,d\boldsymbol\ell$。

最终：

```math
B_z=\frac{\mu_0Q\omega}{8\pi R}
\int_0^\pi\sin^3\theta\,d\theta
=\boxed{\frac{\mu_0Q\omega}{6\pi R}}
```

对于正电荷，方向沿旋转轴。原手写使用 $0\to2\pi$，因而会误得 $\int_0^{2\pi}\sin^3\theta\,d\theta=0$；这也说明上下限检查的重要性。

## 5. 两类「密度 / 微元」与单位检查

| 记号 | 表示什么 | 典型式子 |
|---|---|---|
| $\sigma_s$ | 面电荷密度，$\mathrm{C/m^2}$ | $Q/(4\pi R^2)$ |
| $\sigma(\theta)$ | 单位极角电荷分布 | $dq/d\theta$ |
| $dq$ | 一个球面薄带的电荷 | $\sigma(\theta)d\theta$ |
| $J(\theta)$ | 按本题讨论：单位极角的电流分布 | $dI/d\theta$ |
| $dI$ | 一个纬度圆环的等效电流 | $J(\theta)d\theta$ |
| $K(\theta)$ | 常规定义的面电流密度，$\mathrm{A/m}$ | $\sigma_s\omega R\sin\theta$ |

**考场原则：先看题目如何定义符号，不要仅凭字母 $\sigma$、$J$ 就代入习惯公式。**

## 6. 此题的错误与正确能力

**已表现的能力：**

- 独立想到按纬度切成圆环，正确写出 $r=R\sin\theta$。
- 经提醒补上弧长 $R\,d\theta$ 后，正确写出球面薄带电荷。
- 正确识别旋转周期 $T=2\pi/\omega$，得到 $\sigma(\theta)$、$J(\theta)$ 的角度分布结果。
- (c) 能尝试用 Biot–Savart 与对称性，磁场微元最后得到正确结构。

**待纠正：**

1. (b) 磁偶极矩的 $A$ 是电流环围成的**圆盘面积**，不是球面薄带面积。
2. 极角 $\theta$ 只从 $0$ 到 $\pi$，不要与方位角 $0$ 到 $2\pi$ 混淆。
3. 不能忘记分布函数与微元之间的 $d\theta$。
4. 熟悉球心位于每个纬度环的轴线上，而不位于所有纬度环的圆心。

## 7. 考前 2 分钟复做

不用翻笔记，从半径 $R$、带电 $Q$、角速度 $\omega$ 出发，写出：

1. $dA_{\mathrm{band}}$、$\sigma(\theta)$、$J(\theta)$；
2. $A_{\mathrm{loop}}$、$d\mu$ 与 $\mu$；
3. $dB_z$ 与 $B_z$，并检查三处积分上下限和 $d\theta$。

**状态：** (a) 已核对正确，(b)(c) 订正答案已记录，整题尚待独立复做确认。
