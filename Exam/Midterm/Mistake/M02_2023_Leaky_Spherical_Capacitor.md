# 2023 期中第 2 题：漏电球形电容器——面积、介电常数、积分常数与功率

> 状态：🟡 已独立完成第一轮手写解答，物理建模和一阶微分方程分离变量思路正确；存在系数、介电常数、初值及功率概念错误，待遮住答案独立复做。
>
> 来源：2023 年期中卷第 2 题；用户 2026-11-08 两页手写解答及后续提问。
>
> 复盘重点：**先确认球形面积、材料参数、初始条件、Power（功率）与 Energy（能量）究竟是哪一个。**

## 一、题目模型与当前反馈

两个同心球形电极，半径 $a<b$。两电极间填充均匀介质，电导率为 $\sigma$、相对介电常数为 $\varepsilon_r$。初始电荷为 $Q_0$，电荷通过介质逐渐泄漏。

- (a) 求球形电容器的电容 $C$ 和径向漏电电阻 $R$。
- (b) 求电荷随时间的变化 $Q(t)$。
- (c) 求焦耳热的**瞬时功率** $P(t)$（Power，而非累计热量）。

这里的 $R$ 指电阻，不是球半径；积分时径向坐标统一使用 $r$。

## 二、第一轮做对的地方

1. 知道使用高斯定律从球对称电场出发，积分电势差，再根据 $C=Q/U$ 求电容。
2. 知道径向漏电可把介质分为薄球壳，写出 $dR=dr/(\sigma A(r))$ 再积分。
3. 能列出正确的一阶衰减结构 $dQ/dt=-Q/(RC)$，并能分离变量、积分，认识指数衰减。

这些是已经展现出来的**解题思路**，并不等于整题计算完成。

## 三、错误 1：球面积写成 $\pi r^2$，漏了系数 4

球形高斯面和径向漏电流所穿过的面积都是：

```math
\boxed{A(r)=4\pi r^2}
```

不是圆盘的截面积 $\pi r^2$。

对于介质为均匀、线性、各向同性的模型：

```math
\varepsilon=\varepsilon_0\varepsilon_r
```

故两球之间电场为：

```math
E(r)=\frac{Q}{4\pi\varepsilon_0\varepsilon_r r^2},
\qquad a<r<b
```

电势差取内球电势减外球电势：

```math
U=V(a)-V(b)=\int_a^b E(r)\,dr
=\frac{Q}{4\pi\varepsilon_0\varepsilon_r}
\left(\frac1a-\frac1b\right)
```

于是：

```math
\boxed{C=\frac{4\pi\varepsilon_0\varepsilon_r ab}{b-a}}
```

**易混：** 相对介电常数是比值 $\varepsilon_r=\varepsilon/\varepsilon_0$，没有单位。不能因为过去在真空计算中过多使用 $\varepsilon_0$ 就漏掉 $\varepsilon_r$；但也不能脱离均匀线性介质的适用条件，在所有电磁学公式中随意替换。

## 四、错误 2：径向电阻的面积仍然是球面积

用户的“微元电阻求和”方法是正确的，但需要使用：

```math
dR=\frac{dr}{\sigma\,4\pi r^2}
```

所以：

```math
R=\int_a^b\frac{dr}{4\pi\sigma r^2}
=\frac{1}{4\pi\sigma}\left(\frac1a-\frac1b\right)
```

即：

```math
\boxed{R=\frac{b-a}{4\pi\sigma ab}}
```

非常重要的相互验证：

```math
\boxed{RC=\frac{\varepsilon_0\varepsilon_r}{\sigma}}
```

几何参数 $a,b$ 在乘积 $RC$ 中抵消。单位必须是时间。

## 五、错误 3：一阶微分方程解漏积分常数和初始电荷

选择 $Q(t)$ 为内球剩余电荷，漏电流的正大小为 $I=-dQ/dt$（假设初始 $Q_0>0$）。

电压与电流：

```math
\frac{Q}{C}=IR=-R\frac{dQ}{dt}
```

故：

```math
\frac{dQ}{Q}=-\frac{dt}{RC}
```

积分时不能直接漏掉常数：

```math
\ln|Q|=-\frac{t}{RC}+K
```

由初始条件 $Q(0)=Q_0$ 得：

```math
\boxed{
Q(t)=Q_0e^{-t/(RC)}
=Q_0e^{-\sigma t/(\varepsilon_0\varepsilon_r)}
}
```

**错误自检：** 第一轮写的 $e^{-t/(RC)}$ 在 $t=0$ 时为 1，而不是题目要求的 $Q_0$；量纲上它也只是无量纲数字，不能直接当有单位的电荷。

## 六、错误 4：Power 不是累计 Energy；而且焦耳热功率是 $I^2R$

原题 (c) 要求 Power（瞬时功率），单位是 W：

```math
\boxed{P(t)=I(t)^2R}
```

注意：原手写开头的 $\int IR^2\,dt$ 既不符合功率定义，形式上也不是正确的焦耳热能量公式。

由 (b)：

```math
I(t)=\left|-\frac{dQ}{dt}\right|
=\frac{Q_0}{RC}e^{-t/(RC)}
```

因此：

```math
\boxed{
P(t)=\frac{Q_0^2}{RC^2}e^{-2t/(RC)}
}
```

代入 (a)：

```math
\boxed{
P(t)=
\frac{\sigma Q_0^2(b-a)}
{4\pi(\varepsilon_0\varepsilon_r)^2ab}
e^{-2\sigma t/(\varepsilon_0\varepsilon_r)}
}
```

**易错点：** 电流指数为 $e^{-t/(RC)}$，功率与电流平方成正比，因此功率指数是 $e^{-2t/(RC)}$。

如果问的是从 0 到 $t$ 放出的**热量/能量**，才需要积分：

```math
W(0\to t)=\int_0^t P(t')\,dt'
=\frac{Q_0^2}{2C}\left(1-e^{-2t/(RC)}\right)
```

这一附加公式用于区分物理量，**不是原题 (c) 所要求的答案**。

## 七、考场 30 秒检查清单

1. **几何**：是球面 $4\pi r^2$，还是圆面 $\pi r^2$？
2. **介质**：题目给了 $\varepsilon_r$ 吗？是否写了 $\varepsilon=\varepsilon_0\varepsilon_r$？
3. **方向**：电势差与漏电流正方向是否自洽？
4. **微分方程**：积分常数是否保留？是否代入 $Q(0)=Q_0$？
5. **单位**：$C$ 为 F，$R$ 为 $\Omega$，$RC$ 为 s，$Q$ 为 C，$P$ 为 W。
6. **读题**：Power 是瞬时功率 $I^2R$；Energy/Heat 才考虑积分。
7. **衰减率**：电荷一次方指数，功率因平方使指数系数变为 2。

## 八、待独立重做的小测

- 不看正文，写出 $C$、$R$、$RC$。
- 从 $Q/C=-R\,dQ/dt$ 写出满足 $Q(0)=Q_0$ 的 $Q(t)$。
- 写出 $P(t)$，并回答它与累计热量在单位上的区别。

**记录状态：** 数学分离变量法已能主动使用，但独立完成时仍漏初始条件；本题未完成无提示纠错复做，暂不标记为“已纠正”。
