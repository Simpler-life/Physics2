# Chapter 6 Exercise 7：界面电荷与高斯面符号

> 状态：✅ 已解决  
> 主题：steady current / current density / conductivity / electric-field discontinuity / Gaussian pillbox

## 1. 原题结构

<img width="1422" height="450" alt="image" src="https://github.com/user-attachments/assets/dfd1ba05-9cc0-46d1-89b4-4534f007220a" />


两根长棒沿 $x$ 方向首尾相接，横截面积相同为 $A$，电导率分别为 $\sigma_1$ 和 $\sigma_2$。

稳恒电流 $I>0$ 沿 $+x$ 方向从材料 1 流向材料 2。

需要理解两件事：

1. 为什么同一个稳恒电流经过两种材料时，电场可以不同；
2. 为什么两边电场不同会意味着界面上存在自由电荷，以及这个电荷的正负如何判断。

---

## 2. 第一步：同一个电流不代表同一个电场

因为两根棒横截面积相同，而且是 steady current，所以两边电流密度相同：

```math
j_1=j_2=\frac{I}{A}
```

微观欧姆定律：

```math
\vec j=\sigma\vec E
```

因此：

```math
E_1=\frac{I}{A\sigma_1}
```

```math
E_2=\frac{I}{A\sigma_2}
```

所以即使 $j$ 相同，只要：

```math
\sigma_1\neq\sigma_2
```

就会有：

```math
E_1\neq E_2
```

### 易错点 1：同一个稳恒电流，所以电场也应该一样

这是错误的。

真正连续的是 steady current 下的电流（以及这里因为面积相同而相同的 $j$），不是 $E$。

材料不同，$\sigma$ 不同，为了维持同样的 $j$，所需的 $E$ 就可以不同。

---

## 3. 为什么 $E$ 的突变意味着界面有电荷

这里不要先死背边界公式，直接从最原始的 Gauss' law 出发：

```math
\oint \vec E\cdot d\vec A
=
\frac{q_{\rm enc}}{\varepsilon_0}
```

在材料 1 和材料 2 的界面上放一个极薄的 Gaussian pillbox，两个端面面积都为 $A$。

取统一的正方向为从材料 1 指向材料 2，也就是 $+x$。

由于 pillbox 很薄，侧面通量趋于 0，只需看两个端面。

---

## 4. 本题最重要的错误：为什么是 $E_2-E_1$，不是 $E_1-E_2$

### 我当时的疑问

我一开始把正负理解成：

> “指入 pillbox 的是不是减少，指出 pillbox 的是不是增加？”

这个理解不对。

高斯通量的正负**不是由‘流入/流出代表增加或减少’决定的**。

真正决定正负的是：

```math
\boxed{
\vec E\cdot d\vec A
}
```

而对于闭合曲面：

```math
\boxed{
d\vec A\text{ 永远取该处的外法线方向}
}
```

这才是判断正负的唯一可靠方法。

### 材料 2 一侧

pillbox 在材料 2 一侧端面的外法线沿 $+x$。

$E_2$ 也沿 $+x$，所以：

```math
\vec E_2\cdot d\vec A
=
+E_2A
```

### 材料 1 一侧

pillbox 在材料 1 一侧端面的外法线沿 $-x$。

但 $E_1$ 仍沿 $+x$，两者反向，所以：

```math
\vec E_1\cdot d\vec A
=
-E_1A
```

因此总通量是：

```math
\Phi
=
E_2A-E_1A
```

由 Gauss' law：

```math
(E_2-E_1)A
=
\frac{q}{\varepsilon_0}
```

所以界面自由电荷为：

```math
\boxed{
q
=
\varepsilon_0A(E_2-E_1)
}
```

代入 $E_1,E_2$：

```math
\boxed{
q
=
\varepsilon_0 I
\left(
\frac{1}{\sigma_2}
-
\frac{1}{\sigma_1}
\right)
}
```

---

## 5. 为什么换一个法向，公式看起来会反过来

如果统一把法向改成从材料 2 指向材料 1，那么前后的符号会一起改变。

因此不能孤立地背：

```math
E_2-E_1
```

真正应该记的是：

```math
\boxed{
\text{先选定法向}
\rightarrow
\text{每一面都用 }\vec E\cdot d\vec A
\rightarrow
\text{再决定正负}
}
```

也就是说，$2-1$ 不是一个神秘规定，而是当前法向约定的结果。

---

## 6. 和 Lecture 5 导体表面公式的关系

之前见过：

```math
E_{\rm out}
=
\frac{\sigma_f}{\varepsilon_0}
```

当时很容易把它当成一个独立公式。

其实它只是当前一般界面关系的特殊情况。

一般来说：

```math
E_{2,\perp}-E_{1,\perp}
=
\frac{\sigma_f}{\varepsilon_0}
```

而导体静电平衡时内部：

```math
E_{\rm in}=0
```

所以才退化成：

```math
E_{\rm out}
=
\frac{\sigma_f}{\varepsilon_0}
```

### 易错点 2：把 $E_{\rm out}=\sigma/\varepsilon_0$ 当成只需要死记的新公式

更稳妥的方法是记住它来自 Gauss' law。

如果忘记边界公式，可以现场用 pillbox 重新推一遍。

---

## 7. 易错点 3：看到 $E_2\neq E_1$ 就只说“因为 $E$ 突变，所以有电荷”

这个方向直觉上没错，但考试里最好再补上物理依据：

```math
\oint\vec E\cdot d\vec A
=
\frac{q_{\rm enc}}{\varepsilon_0}
```

跨界面的极薄 pillbox 有非零净通量：

```math
(E_2-E_1)A\neq0
```

因此它包围的界面电荷必然非零：

```math
q\neq0
```

所以更完整的逻辑是：

```math
\boxed{
E_{\perp}\text{ 在界面发生跳变}
\Rightarrow
\text{pillbox 有非零净通量}
\Rightarrow
\text{界面存在表面电荷}
}
```

---

## 8. 如何判断界面电荷是正还是负

由：

```math
q
=
\varepsilon_0 I
\left(
\frac{1}{\sigma_2}
-
\frac{1}{\sigma_1}
\right)
```

因为 $\varepsilon_0>0$、$I>0$，所以 $q$ 的正负只看括号。

如果：

```math
\sigma_1>\sigma_2
```

则：

```math
\frac{1}{\sigma_1}
<
\frac{1}{\sigma_2}
```

所以：

```math
\boxed{
q>0
}
```

直观上，材料 2 电导率更低，为维持同样电流，需要更强的电场：

```math
E_2>E_1
```

于是沿 1 到 2 的方向，法向电场出现正跳变，对应正表面电荷。

---

## 9. 本题以后最稳的解题框架

遇到“两种材料交界 + 稳恒电流 + 求界面电荷”时：

1. 先用 $j=I/A$；
2. 再用 $j=\sigma E$ 得到两边 $E$；
3. 跨界面画一个极薄 Gaussian pillbox；
4. 不背符号，逐面计算 $\vec E\cdot d\vec A$；
5. 用 Gauss' law 得到界面电荷。

最应该记住的一句：

```math
\boxed{
\text{高斯通量的正负看 }\vec E\cdot d\vec A，
\text{不是凭“流入/流出”语言猜符号。}
}
```
