# M06：2025–2026 秋期中第 4 题——交变电流环、涡电流圆盘、磁偶极矩和磁场力

> 状态：**需独立复做**。(1) 法拉第定律思路正确，但误用电流环圆心磁场；(2) 通过红笔订正已正确完成环形微元和磁偶极矩积分；(3) 混淆磁力矩与磁场力，磁偶极近似中的梯度受力经讲解掌握，尚未独立重做。
> 来源：2025–2026 秋 CC/LLK 班期中同学**回忆/拟解析**第 4 大题、用户三轮手写解答和 2026-11-09 追问。不是已核验的正式卷面。

## 1. 题目模型

半径 $R$ 的大圆形电流环在 $xy$ 平面，通以 $I(t)=I_0\cos(\omega t)$；轴线上 $z=h$ 处放置半径 $a$、厚度 $w$、电导率 $\sigma$ 的小导体圆盘，$w\ll a$ 且 $a\ll R,h$。忽略高阶感应效应，近似认为大电流环产生的轴向磁场在小盘内均匀。

求：(1) 涡电流密度 $\vec J(r,t)$；(2) 等效磁偶极矩 $\vec m(t)$；(3) 圆盘受外场的瞬时磁力。

约定正向的大环电流产生 $+\hat z$ 方向磁场，盘中正环流方向为 $+\hat\phi$。

## 2. (1) 环上磁场 → 感应电场 → 电流密度

**用户最初错误：** 用圆心磁场 $B(0)=\mu_0 I/(2R)$ 代替轴线上高度 $h$ 的磁场。圆心公式只是 $h=0$ 的特例；实际应由 Biot–Savart 定律得到

```math
\boxed{B_z(z,t)=\frac{\mu_0 I_0R^2}{2(R^2+z^2)^{3/2}}\cos(\omega t)}
```

选择圆盘内半径为 $r$ 的环路，$a\ll R,h$ 使近似均匀磁场成立：

```math
2\pi r E_\phi(r,t)=-\frac{d}{dt}[\pi r^2B_z(h,t)]
```

```math
\boxed{E_\phi(r,t)=\frac{\mu_0 I_0R^2\omega r}{4(R^2+h^2)^{3/2}}\sin(\omega t)}
```

利用微观欧姆定律 $\vec J=\sigma\vec E$：

```math
\boxed{\vec J(r,t)=\frac{\sigma\mu_0 I_0R^2\omega r}{4(R^2+h^2)^{3/2}}\sin(\omega t)\,\hat{\boldsymbol\phi}}
```

**用户做对：** 使用法拉第环路积分 $\oint\vec E\cdot d\vec\ell=-d\Phi_B/dt$，知道 $J=\sigma E$，并找到了 $J\propto r$。复做时需首先判断观察点是环心还是轴上任意点。

## 3. (2) 涡电流环的磁偶极矩

一个环形电流具有磁偶极矩 $\vec m=IA\hat n$。圆盘可分成半径 $r$、径向宽 $dr$ 的同心薄电流环。**两种面积必须分清：**

- 电流截面积（垂直于环向电流）：$dA_\perp=w\,dr$，故 $dI=J_\phi(r,t)w\,dr$。
- 该薄环围成的面积：$A_{\rm loop}=\pi r^2$，故 $dm_z=\pi r^2dI$。

```math
m_z(t)=\pi w\int_0^a J_\phi(r,t)r^2\,dr
```

```math
\boxed{\vec m(t)=\frac{\pi\sigma\mu_0 I_0R^2\omega w a^4}{16(R^2+h^2)^{3/2}}\sin(\omega t)\,\hat z}
```

**用户表现：** 最初把电流密度关系写成类似 $dJ/dA=J$，红笔已改对 $dI=Jw\,dr$，并独立算出 $\int_0^a r^3dr=a^4/4$。

## 4. (3) 区分磁力矩与磁场力

磁力矩：

```math
\vec\tau=\vec m\times\vec B
```

本题 $\vec m\parallel\vec B$（或反向），所以 $\vec\tau=0$；不能将二者模长直接相乘而遗漏叉乘方向。

小磁偶极子在**非均匀**外磁场中的瞬时净力（固定该时刻的偶极矩取空间梯度）：

```math
\vec F=\left.\nabla_{\vec x}(\vec m\cdot\vec B_{\mathrm{ext}})\right|_{\vec m\ \mathrm{fixed}}
```

本题沿轴线，因此

```math
F_z(t)=m_z(t)\left.\frac{\partial B_z(z,t)}{\partial z}\right|_{z=h}
```

轴上磁场梯度：

```math
\left.\frac{\partial B_z}{\partial z}\right|_{h}=-\frac{3\mu_0I_0R^2h}{2(R^2+h^2)^{5/2}}\cos(\omega t)
```

乘上已求得的 $m_z(t)$：

```math
\boxed{\vec F(t)=-\frac{3\pi\sigma\mu_0^2 I_0^2R^4\omega w a^4h}{32(R^2+h^2)^4}\sin(\omega t)\cos(\omega t)\,\hat z}
```

等价地：

```math
\boxed{\vec F(t)=-\frac{3\pi\sigma\mu_0^2 I_0^2R^4\omega w a^4h}{64(R^2+h^2)^4}\sin(2\omega t)\,\hat z}
```

在本题线性、准静态、忽略高阶反馈的模型中一个完整周期的时间平均力为零。

### 4.1 用户追问：为什么求导不作用于 $m$？

这是区分**空间梯度**与**时间变化**的关键：本题 $m_z=m_z(t)$，在确定时刻的受力计算中作为给定偶极矩，空间导数 $\partial m_z(t)/\partial z=0$。于是

```math
\frac{\partial}{\partial z}\big[m_z(t)B_z(z,t)\big]=m_z(t)\frac{\partial B_z(z,t)}{\partial z}
```

如果研究圆盘移动到不同位置后感应电流如何重新变化，则 $m=m(z,t)$ 也可能依位置变化；不能直接把 $U=-m(z,t)B(z,t)$ 当作完整机械势能再做普通乘积求导，额外的电磁能量交换需另行分析。

### 4.2 为什么安培力法更难？

用户尝试 $d\vec F=I\,d\vec\ell\times\vec B$，但如果把整个小盘处的磁场都视为相同的均匀矢量，闭合电流环净力会是零。实际轴向净力依赖外磁场的**空间不均匀性**（尤其是轴附近的径向磁场分量）；直接用小磁偶极近似更高效。

## 5. 课件范围说明与复做

- 毕奥–萨伐尔定律、法拉第电磁感应定律、电流密度、磁偶极矩和磁力矩属已学课程知识。
- $\vec F=\nabla(\vec m\cdot\vec B)$ 用户反馈课件并未直接作为核心公式讲解，曾由 $U=-\vec m\cdot\vec B$ 与 $\vec F=-\nabla U$ 解释；不应将其误记作已经独立学会。
- 当前应试优先掌握：磁力矩管转动、磁场梯度管净力；两个面积 $w\,dr$ 与 $\pi r^2$ 不混淆；轴线磁场不是圆心磁场。

**闭卷复做目标：** 先写出轴上 $B_z(h,t)$；在半径 $r$ 处列法拉第环路方程；使用 $dI=Jwdr$ 计算 $\vec m$；区分 $\vec\tau$ 与 $\vec F$ 并写对求导变量。 
