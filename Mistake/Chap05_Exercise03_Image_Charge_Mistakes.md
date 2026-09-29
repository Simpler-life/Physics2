# Chapter 5 Exercise 3：非接地导体球壳的镜像法误区复盘

> 状态：✅ 已解决  
> 主题：Method of Image Charges / grounded vs. isolated conductor / uniqueness theorem / Gauss' law

## 1. 原题

A point charge $Q$ is located outside a thin spherical conducting shell of radius $R$. The distance from the point charge to the center of the shell is $d$. The spherical shell is not grounded and has total charge $Q_0$. Find the force exerted on $Q$ by the shell.

其中：

- 球壳半径：$R$
- 点电荷到球心距离：$d>R$
- 外部真实点电荷：$Q$
- 球壳总电荷：$Q_0$

---

## 2. 我一开始想错的地方

### 误区 1：静电平衡 = 导体总电荷为 0

这是错误的。

静电平衡只意味着导体中的自由电荷不再继续移动，因此：

```math
\vec E_{\text{conductor}}=0
```

以及：

```math
V_{\text{conductor}}=\text{constant}
```

但导体完全可以带净正电或净负电。

尤其是 grounded conductor 可以和大地交换电荷，所以总电荷并不固定。

---

### 误区 2：一个导体只能等效成一个镜像电荷

错误。

镜像法不是：

```math
\text{一个真实物体}
\Longleftrightarrow
\text{一个假电荷}
```

而是：

> 可以使用任意数量的辅助镜像电荷，只要它们在求解区域中复现正确的源和边界条件。

本题最终需要两个镜像电荷，它们承担不同任务。

---

### 误区 3：镜像电荷必须和真实表面电荷分布一模一样

错误。

真实球壳上的感应电荷是连续的表面分布，而镜像法可以用几个点电荷代替它。

要求的是：

```math
\boxed{
\text{在求解区域中产生相同的 }V\text{ 和 }\vec E
}
```

而不是电荷分布的形状相同。

---

### 误区 4：先想镜像电荷放哪里，却没有先确定求解区域

这题要求的是球壳对外部点电荷 $Q$ 的作用力，因此真正需要的是球外区域的电场：

```math
r>R
```

所以球面：

```math
r=R
```

是求解区域的边界之一。

镜像电荷必须放在求解区域之外，也就是球内。

判断顺序应该是：

```math
\boxed{
\text{先确定求解区域}
\to
\text{确定完整边界}
\to
\text{再设计镜像电荷}
}
```

---

### 误区 5：把“球壳内部”当成边界

边界不是一整块球内空间，而是把求解区域和非求解区域分开的表面。

本题求解区域是 $r>R$，所以边界是球面 $r=R$，另一个条件来自无穷远处。

---

### 误区 6：认为未接地时也应该让球面满足 $V=0$

不对。

grounded conductor 的条件是：

```math
V=0
```

而未接地静电平衡导体只要求：

```math
\boxed{
V=\text{constant}
}
```

这个常数不需要等于 0。

本题还额外给出了：

```math
\boxed{
Q_{\text{shell}}=Q_0
}
```

所以本题同时有两个条件：

1. 球面必须是等势面；
2. 球壳总电荷必须是 $Q_0$。

---

### 误区 7：认为“镜像系统总电荷必须相同”是镜像法额外强加的规则

更准确的理解是：

如果球外的电场真的完全等效，那么在球面外画一个 Gaussian surface，两种系统的通量必须相同。

真实球壳：

```math
\oint \vec E\cdot d\vec A
=
\frac{Q_0}{\varepsilon_0}
```

镜像系统：

```math
\oint \vec E\cdot d\vec A
=
\frac{Q_{\text{image,total}}}{\varepsilon_0}
```

既然同一个外部区域中的 $\vec E$ 相同，就必然有：

```math
\boxed{
Q_{\text{image,total}}=Q_0
}
```

接地球看起来“不要求总电荷”，只是因为接地时真实导体的总电荷本来就没有预先指定，而是解的一部分。

---

## 3. 正确的镜像构造

### 第一步：先解决“球面等势”的问题

先借用对应 grounded sphere 的镜像解。

真实电荷 $Q$ 在球心外距离 $d$ 处。

在球内同一直线上放偏心镜像电荷 $Q'$，位置距球心为 $d'$。

要求整个球面满足零电势：

```math
\frac{Q}{r_1}
+
\frac{Q'}{r_2}
=0
```

最终得到：

```math
\boxed{
d'=\frac{R^2}{d}
}
```

以及：

```math
\boxed{
Q'=-\frac{R}{d}Q
}
```

这个 $Q'$ 的作用是消除真实电荷 $Q$ 在球面上造成的电势位置差异。

---

## 4. 我没想到的关键：再在球心加一个电荷

原来的 $Q'$ 已经让球面成为等势面，但它对应的总电荷一般不等于题目给定的 $Q_0$。

所以在球心再放一个镜像电荷 $Q_c$。

为什么一定选球心？

因为球面上任意一点到球心的距离都等于 $R$，所以它对整个球面增加的电势都是同一个常数：

```math
V_c
=
\frac{1}{4\pi\varepsilon_0}
\frac{Q_c}{R}
```

它不会破坏已经建立好的等势性，只会把整个球面的电势统一抬高或降低。

所以两个镜像电荷的分工是：

```math
\boxed{
Q'：消除球面电势的空间变化
}
```

```math
\boxed{
Q_c：调整总电荷，同时只给球面增加常数电势
}
```

由总电荷条件：

```math
Q'+Q_c=Q_0
```

得到：

```math
\boxed{
Q_c
=
Q_0+\frac{R}{d}Q
}
```

注意：这不是说真实的 $Q_0$ 被物理地分成了两团电荷，而只是镜像系统中的数学分解。

---

## 5. 为什么偏心镜像的位置和大小是这些值

取球面上两个最方便的点：

- 靠近 $Q$ 的点：$x=R$
- 远离 $Q$ 的点：$x=-R$

两点都必须满足 $V=0$。

因此：

```math
\frac{Q}{d-R}
+
\frac{Q'}{R-d'}
=0
```

以及：

```math
\frac{Q}{d+R}
+
\frac{Q'}{R+d'}
=0
```

消去 $Q'/Q$：

```math
\frac{R-d'}{d-R}
=
\frac{R+d'}{d+R}
```

解得：

```math
\boxed{
d'=\frac{R^2}{d}
}
```

再代回得到：

```math
\boxed{
Q'=-\frac{R}{d}Q
}
```

重要提醒：

> 只在两个点满足边界条件，一般不能证明整个边界都满足。

这里之所以可以用两个对称点解出参数，是因为球对称结构已经把镜像位置限制在球心—真实电荷的连线上；求出参数后仍应验证整个球面。

对球面任意点，可以证明：

```math
r_2=\frac{R}{d}r_1
```

从而：

```math
\frac{Q}{r_1}
+
\frac{Q'}{r_2}
=0
```

确实对整个球面成立。

---

## 6. 求力

真实电荷 $Q$ 受到球壳的力，等于两个镜像电荷对 $Q$ 的库仑力之和。

取 $\hat{\mathbf r}$ 为从球心指向真实电荷 $Q$ 的方向。

球心电荷的贡献：

```math
\vec F_c
=
\frac{1}{4\pi\varepsilon_0}
\frac{Q}{d^2}
\left(
Q_0+\frac{R}{d}Q
\right)
\hat{\mathbf r}
```

偏心镜像与真实电荷的距离：

```math
d-d'
=
d-\frac{R^2}{d}
=
\frac{d^2-R^2}{d}
```

因此：

```math
\vec F'
=
-
\frac{1}{4\pi\varepsilon_0}
\frac{RdQ^2}{(d^2-R^2)^2}
\hat{\mathbf r}
```

最终：

```math
\boxed{
\vec F
=
\frac{1}{4\pi\varepsilon_0}
\left[
\frac{Q}{d^2}
\left(
Q_0+\frac{R}{d}Q
\right)
-
\frac{RdQ^2}{(d^2-R^2)^2}
\right]
\hat{\mathbf r}
}
```

---

## 7. 下次遇到镜像法题目的检查清单

1. 我要求哪一块空间里的 $V$ 或 $\vec E$？
2. 这个求解区域的完整边界是什么？
3. 导体是 grounded，还是 isolated / given total charge？
4. 边界要求是 $V=0$，还是仅仅 $V=\text{constant}$？
5. 镜像电荷是否全部位于求解区域之外？
6. 我是不是误以为“一个导体只能对应一个镜像电荷”？
7. 是否可以用 superposition，把不同约束交给不同镜像电荷处理？
8. 若导体总电荷已给定，镜像系统对应的总电荷是否匹配？
9. 我验证的是整个边界，还是只验证了几个点？
10. 最后求力时，只计算镜像电荷对真实电荷的力，不计算真实电荷对自己的作用。

## 8. 一句话复盘

```math
\boxed{
\text{镜像法的核心不是猜“一个等效电荷”，而是构造满足全部边界条件的等效场。}
}
```
