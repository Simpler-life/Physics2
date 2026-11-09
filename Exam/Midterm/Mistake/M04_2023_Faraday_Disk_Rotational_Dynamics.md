# 2023 期中第 4 题：法拉第圆盘——运动电动势、制动力矩与转速衰减

> 状态：🟡 已独立完成两轮推导；第二轮能正确列出感应电动势、电流、分布磁力矩和角动量积分关系，但一阶微分方程转换及求解经过提示完成。待独立复做。
>
> 来源：2023 年期中第 4 题及用户 2026-11-08 至 2026-11-09 的两页手写解答和后续交流。精确方向、符号及圆盘参数以原卷为准。
>
> 核心失误：**径向变量漏积分、把分布力当成集中力、不了解力矩如何改变角速度、积分方程求导时漏掉 $dt$。**

## 一、模型和符号

<img width="874" height="828" alt="fd0bda2c839ea20015a59aaceabebf07" src="https://github.com/user-attachments/assets/af9a59bb-5f01-450f-bc7f-a579797a18d2" />


半径为 $a$ 的导体圆盘绕轴以角速度 $\omega$ 旋转，处在垂直盘面、大小为 $B$ 的均匀磁场中。通过中心与边缘的滑动触点接外电阻 $R$（以下理想化忽略盘内电阻及其他损耗）。

- $r$：盘上某点到转轴的径向距离，$0\le r\le a$。
- $R$：电路电阻，**不是圆盘半径**。
- $J$：圆盘对转轴的转动惯量。
- $\omega_0$：初始角速度。
- 本文主要给出大小；方向要另用 $\vec v\times\vec B$ 和楞次定律判断。

<img width="960" height="1308" alt="image" src="https://github.com/user-attachments/assets/71c66e11-8cc8-4f95-8d04-c616a7d3add4" />
<img width="964" height="1484" alt="image" src="https://github.com/user-attachments/assets/8f42a848-6a24-4c30-92d7-5b5ea5f03b02" />
<img width="928" height="578" alt="image" src="https://github.com/user-attachments/assets/64c2a082-eb52-4a6f-984d-8eb076e27c53" />


## 二、(a) 开路：电荷分离、电场及电势差

磁场对随盘运动的电荷作用：

```math
\vec F_B=q\vec v\times\vec B,\qquad v(r)=\omega r
```

开路达到静电平衡时：

```math
q(\vec E+\vec v\times\vec B)=0
\quad\Longrightarrow\quad
\boxed{\vec E=-\vec v\times\vec B}
```

因为速度与磁场垂直，径向电场的**大小**为：

```math
\boxed{|E_r(r)|=B|\omega|r}
```

**第一轮错误：** 已写出 $E(r)=B\omega r$，但最后把电势差写成 $B\omega a$，漏掉对 $r$ 的积分；它的量纲也不对（V/m 而非 V）。

正确的中心—边缘电势差大小：

```math
\boxed{
|\Delta V|=\int_0^a B|\omega|r\,dr
=\frac12B|\omega|a^2
}
```

若定义有向运动电动势，则：

```math
\mathcal E_{\mathrm{mot}}
=\int_{\mathrm{center}}^{\mathrm{rim}}
(\vec v\times\vec B)\cdot d\vec\ell
```

其符号由 $\vec\omega$、$\vec B$ 的相对方向决定。不能忽略符号约定，直接把 $V_{\rm center}-V_{\rm rim}$ 认作恒正。

**概念：** “切割磁感线”不是切断电流，而是运动电荷受到 $q\vec v\times\vec B$；开路时建立电势差，但没有持续的闭合电路电流。圆盘整体磁通量不变也能有这种运动电动势。

## 三、(b) 闭路：电流、磁阻力矩与维持匀速的外力矩

电路闭合且忽略盘内电阻：

```math
|\mathcal E|=\frac12B|\omega|a^2,
\qquad
\boxed{|I|=\frac{B|\omega|a^2}{2R}}
```

**第一轮错误：** 使用 $F_B=BIa$ 后又将全部力矩写为 $\tau=F_Ba$，相当于把径向分布的磁力当成集中在盘边缘的力。

实际在径向电流微元 $dr$ 上：

```math
dF=IB\,dr,\qquad
d\tau=r\,dF=IBr\,dr
```

积分：

```math
|\tau_{\rm mag}|=\int_0^a IBr\,dr
=\frac12IBa^2
```

代入电流：

```math
\boxed{|\tau_{\rm mag}|=\frac{B^2a^4}{4R}|\omega|}
```

磁力矩**阻碍原旋转方向**；要保持匀速，外加力矩应与其相反。在取初始旋转方向为正且 $\omega>0$ 时：

```math
\boxed{\tau_{\rm mag}=-\frac{B^2a^4}{4R}\omega},
\qquad
\tau_{\rm ext}=+\frac{B^2a^4}{4R}\omega
```

快速校验：理想匀速发电时机械输入功率等于外电阻耗散功率：

```math
\tau_{\rm ext}\omega=I^2R
```

用此式可直接检查结果中的 $1/4$ 与 $a^4$。

## 四、(c) 自由减速：用户第二轮做到哪里？

第二轮手写已正确复现：

```math
\mathcal E(t)=\frac12Ba^2\omega(t)
```

```math
I(t)=\frac{Ba^2}{2R}\omega(t)
```

```math
|\tau_{\rm mag}(t)|
=\frac{B^2a^4}{4R}\omega(t)
```

并主动选用角冲量定理：

```math
J\omega_0-J\omega(t)
=\frac{B^2a^4}{4R}
\int_0^t\omega(t')\,dt'
```

**这一行正确**（取正初始转向，左边表示角动量减少量）。

真正卡住的地方：把积分方程改写成微分关系时只写了类似 $d(J\omega_0-J\omega(t))=\text{常数}\cdot\omega(t)$，没有明确对**两边求时间导数**，也漏了微分 $dt$ 的对应。

正确方法：同时对 $t$ 求导，利用微积分基本定理：

```math
-J\frac{d\omega}{dt}
=\frac{B^2a^4}{4R}\omega(t)
```

整理：

```math
\boxed{
\frac{d\omega}{dt}
=-\frac{B^2a^4}{4JR}\omega
}
```

这与 RC 放电中的 $dQ/dt=-Q/(RC)$ 是同一类常系数一阶衰减方程。分离变量：

```math
\frac{d\omega}{\omega}
=-\frac{B^2a^4}{4JR}\,dt
```

积分（保留常数）：

```math
\ln|\omega|
=-\frac{B^2a^4}{4JR}t+C
```

代入 $\omega(0)=\omega_0$：

```math
\boxed{
\omega(t)=\omega_0
\exp\!\left(-\frac{B^2a^4}{4JR}t\right)
}
```

### 更快的考场写法

不用先列角冲量积分，直接写固定轴、恒定转动惯量的转动版牛顿第二定律：

```math
\boxed{\tau_{\rm net}=J\frac{d\omega}{dt}}
```

和上述负磁力矩联立即可。$J$ 表示转动惯量，单位 $\mathrm{kg\,m^2}$，不要与电感 $L$ 混淆。

### 如果题目没有给转动惯量怎么办？

**不要凭空指定 $J$ 的数值。**

- 若给出圆盘质量 $M$ 并说明是均匀实心圆盘，绕中心垂直盘面轴有：

```math
J=\frac12Ma^2
```

代入后：

```math
\boxed{
\omega(t)=\omega_0
\exp\!\left(-\frac{B^2a^2}{2MR}t\right)
}
```

- 如果题目直接用 $J$ 表示转动惯量，但不给数值，保留上述带 $J$ 的表达式即可。
- 如果连 $J$ 或决定它的质量分布都没给出，则无法求唯一数值衰减时间，只能在答案中**明确引入 $J$ 作为必要物理参数**。完整原题条件需以原卷为准。

## 五、考前易错点清单

1. 半径位置变化：$v(r)=\omega r$，不是整个盘都用边缘速度 $\omega a$。
2. 电势差必须沿半径积分：$\int_0^a B\omega r\,dr=\frac12B\omega a^2$。
3. 力矩来自分布力：$d\tau=rIB\,dr$，不是全部受力乘边缘距离。
4. 开路时有电势差但无持续电流；闭路才能用 $I=\mathcal E/R$。
5. 制动力矩方向与旋转相反，运动方程要有负号。
6. 正确区分力矩和角动量：$\tau=dL_{\rm ang}/dt$，$L_{\rm ang}=J\omega$。
7. 对含定积分的等式两边求导，右边用微积分基本定理；不要只写一个孤立的 $d$。
8. 分离变量积分后保留常数，并代入 $\omega(0)=\omega_0$。
9. 题目未给 $J$ 时不要造数；先判断是否可由质量、几何条件求出。
10. 维持匀速用 $\tau_{\rm ext}\omega=I^2R$；自由减速可用 $-d(\frac12J\omega^2)/dt=I^2R$。

## 六、待独立复做

遮住上面的解答，用不超过 10 分钟写出：

- $E_r(r)$ 和 $|\mathcal E|$；
- $I$、$\tau_{\rm ext}$；
- $J\,d\omega/dt=\tau_{\rm mag}$ 并求 $\omega(t)$；
- 解释两个负号：电场平衡的方向、磁制动的方向。

**完成状态说明：** 已经独立建立主要电磁模型和角冲量积分；推导中使用过讲解，故尚不能标记为“独立完全正确”。相关数学补充可见 [一阶微分方程与分离变量法](../../../Math_for_Physics/02_First_Order_Linear_ODE_RC.md)。

## 七、2024–2025 期中第 3 题复测：同一个微分方程错误再次出现（2026-11-09）

> **复测状态：前两问独立做对；第三问电磁推导和角冲量方程正确，但分离变量积分仍出错。数学卡点尚未通过独立复做验证。**
>
> 来源：用户《24期中.pdf》第 3 题及其两页手写计算。本题与 2023 年第 4 题为同型法拉第圆盘问题；因此直接补记在 M04，不另建重复的错题正文。

### 1. 本次正确到哪一步？

用户这次能独立写出：

```math
\mathcal E=\frac12B\omega a^2,\qquad
I=\frac{B\omega a^2}{2R},\qquad
\tau_{\rm brake,mag}=\frac{B^2a^4}{4R}\omega
```

并进一步使用角动量关系：

```math
J\omega_0-J\omega(t)
=\frac{B^2a^4}{4R}\int_0^t\omega(t')\,dt'
```

两边对时间求导得到：

```math
\frac{d[J\omega_0-J\omega(t)]}{dt}
=\frac{B^2a^4}{4R}\omega(t)
```

**到这一步均正确。** 这表明电磁感应、分布力矩及转动动力学建模已经明显进步。

### 2. 本次新增的核心错误：把 \omega 与 \omega_0-\omega 混同

用户接下来写成类似：

```math
\frac{d[\omega_0-\omega(t)]}{\omega(t)}
=\frac{B^2a^4}{4RJ}\,dt
```

这一式**作为微分形式仍是正确的**，因为分子 $d[\omega_0-\omega(t)]=-d\omega$。错误出在下一步：把左边当作

```math
\frac{d[\omega_0-\omega(t)]}{\omega_0-\omega(t)}
```

来求对数，于是得到错误的 $\ln|\omega_0-\omega(t)|$。

**根本原因：** 分离变量时，分子中的微分属于 $\omega_0-\omega$，分母却是 $\omega$；两者不是同一个变量，不能套用 $\int du/u=\ln|u|$。

正确处理有两种：

- 直接用 $d(\omega_0-\omega)=-d\omega$，回到 $-d\omega/\omega$；
- 或者先把微分方程整理为 $d\omega/dt=-k\omega$ 再分离变量，更不容易混乱。

### 3. 最推荐的完整计算模板（定积分，避免常数错误）

定义：

```math
k=\frac{B^2a^4}{4RJ}>0
```

由上面的正确积分方程两边求导：

```math
-J\frac{d\omega}{dt}
=\frac{B^2a^4}{4R}\omega
\quad\Longrightarrow\quad
\frac{d\omega}{dt}=-k\omega
```

分离变量并立刻代入积分上下限：

```math
\int_{\omega_0}^{\omega(t)}
\frac{d\omega'}{\omega'}
=-k\int_0^t dt'
```

```math
\ln\!\frac{\omega(t)}{\omega_0}=-kt
```

```math
\boxed{\omega(t)=\omega_0
\exp\!\left(-\frac{B^2a^4}{4RJ}t\right)}
```

以上假定初始角速度为正并一直以相同旋向减速；一般带符号角速度也满足这个线性方程。

### 4. 为什么错误答案可以被初值直接否定？

本次手写最后出现类似：

```math
\omega_0-\omega(t)=A e^{-kt}
```

代入 $t=0$，左边是 $0$，右边是 $A$，所以必须有 $A=0$。这样会推得所有时刻 $\omega(t)=\omega_0$，完全没有减速，与有磁制动力矩的物理情形矛盾。

**做题时立即检查：**

- $t=0$：$\omega(0)=\omega_0$；
- $t\to\infty$：$\omega(t)\to0$；
- $t>0$：角速度应单调减小（$k>0$）。

这三个条件能迅速识别“衰减的对象写错”的解。

### 5. 关联的同类方程

```math
\frac{dy}{dt}=-ky,\quad y(0)=y_0
\quad\Longrightarrow\quad
\boxed{y(t)=y_0e^{-kt}}
```

同一数学模板适用于 RC 放电、RL 自由衰减和磁阻尼圆盘。相关工具笔记见 [一阶微分方程与分离变量法](../../../Math_for_Physics/02_First_Order_Linear_ODE_RC.md)。

**下一次只复测这一处，不必重做全部电磁计算：**

```math
\frac{dx}{dt}=-3x,\qquad x(0)=5
```

目标：闭卷推导 $x(t)$ 并用初值验证，不能仅看完答案就标记为已纠正。
