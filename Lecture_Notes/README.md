# Lecture Notes 阅读导航（Lec01–Lec14）

> 使用方式：这不是一本要求按顺序背完的公式书。每次做题时先问『这是力？场？能量？电流？还是时间变化？』，再跳到对应讲。Lec01–05 为原仓库已有学习记录，Lec06–14 是据课程 PPT 主线与教材补充整理的基础友好版。

## 逐讲入口

- [Lecture 01｜电荷、库仑力、电场](Lecture01_Coulomb_and_Electric_Field.md)
- [Lecture 02｜电通量和高斯定律](Lecture02_Gauss_Law.md)
- [Lecture 03｜电势、电势能、电场](Lecture03_Electrostatic_Potential.md)
- [Lecture 04｜梯度、散度、泊松方程](Lecture04_Triangle_of_Electrostatics.md)
- [Lecture 05｜静电平衡、镜像法](Lecture05_Conductors_in_Electrostatic_Field.md)
- [Lecture 06｜电流、电阻、电容](Lecture06_Resistance_and_Capacitance.md)
- [Lecture 07｜基尔霍夫定律、RC 暂态](Lecture07_DC_Circuits.md)
- [Lecture 08｜洛伦兹力、霍尔效应](Lecture08_The_Magnetic_Field.md)
- [Lecture 09｜电流生磁场、安培定律](Lecture09_Magnetic_Field_of_a_Current.md)
- [Lecture 10｜磁介质、磁化](Lecture10_Magnetic_Properties_of_Materials.md)
- [Lecture 11｜磁通量、电磁感应](Lecture11_Faradays_Law_of_Induction.md)
- [Lecture 12｜电感、自感、RL 暂态](Lecture12_Inductors_and_Inductance.md)
- [Lecture 13｜LC、RLC、交流共振](Lecture13_Alternating_Current_Circuits.md)
- [Lecture 14｜麦克斯韦方程组、电磁波、能量流](Lecture14_Maxwells_Equations_and_EM_Waves.md)

## 先建立一条故事线

1. **Lec01–05：电荷在空间产生什么？** 电荷产生电场；电场可以用电势描述；导体在静电平衡时的场和电势有特殊性质。
2. **Lec06–07：电荷开始流动会怎样？** 电流通过电阻耗散能量，电容储能；电源维持电流，RC 充放电需要时间。
3. **Lec08–10：运动电荷和电流还能产生什么？** 磁场作用于运动电荷；电流也能产生磁场；材料会对磁场做出响应。
4. **Lec11–14：磁场变化后发生什么？** 变化的磁通量使电路出现感应电动势；电感阻碍电流变化；电感和电容能互换能量并振荡；变化的电场和磁场又能共同形成电磁波。

## 易混变量：见字母先问它在哪一讲

| 符号 | 常见含义 | 单位 | 易混提醒 |
|---|---|---|---|
| $q,Q$ | 电荷量 | C | 大小写常用于区别瞬时电荷与固定/初始电荷，具体以本题定义为准 |
| $I$ | 电流 | A | $I=dq/dt$ 的正负由方向约定决定 |
| $V$ | 电势或电势差 | V | 不是体积，体积常写 $\mathcal V$ |
| $E$ | 电场强度 | N/C 或 V/m | 电动势写 $\mathcal E$，二者不是同一量 |
| $B$ | 磁感应强度 | T | 与磁场强度 $H$ 区分 |
| $H$ | 磁场强度 | A/m | 在磁介质里 $\vec B=\mu_0(\vec H+\vec M)$ |
| $M$ | 磁化强度或互感系数 | A/m 或 H | 单位不同；在 Lec12 中 $M$ 多指互感系数 |
| $\mu$ | 磁偶极矩 | A·m² | $\mu_0$ 是真空磁导率，不是磁偶极矩 |
| $R$ | 电阻 | Ω | 有时几何问题 R 是半径，看上下文 |
| $C$ | 电容 | F | 又是库仑单位的符号，须看是否写在数值后 |
| $L$ | 电感 | H | 也可能表示长度，应看是否有线圈 |
| $\Phi_B$ | 磁通量 | Wb | 不是磁场大小；与面积及法线方向有关 |
| $\rho$ | 电荷密度或电阻率 | C/m³ 或 Ω·m | 一定凭单位区分 |
| $\sigma$ | 面电荷密度或电导率 | C/m² 或 S/m | 同一个希腊字母可能在不同章节复用 |
| $\tau$ | 时间常数 | s | RC：$RC$；RL：$L/R$ |
| $\omega$ | 角频率 | rad/s | $\omega=2\pi f$；不是周期 $T$ |

## 公式如何记，而不是死背

- **用定义推**：电流 $I=dq/dt$；电容 $C=Q/V$；电阻 $R=V/I$（后式要注意欧姆元件条件）。
- **用守恒推**：节点电流守恒；闭合回路电压变化之和为零；LC 中电能与磁能交换。
- **用变化率推**：变化磁通量对应感应电动势；变化电流对应自感电动势。
- **用方向推**：洛伦兹力由叉乘定方向，楞次定律先判断磁通量是增还是减。

## 做题时固定五步

1. 写『题目在求什么量』，明确单位。
2. 画图，用箭头规定正方向。
3. 用文字说出物理机制，再挑一条最基本公式。
4. 对照本讲笔记逐个核查变量含义和适用条件。
5. 检查数值、量纲及极限（例如时间很久之后或距离很大时）。

## 来源说明

课程 PPT 是 Lec06–13 的主线参考，配合上传的 `chap06.pdf` 至 `chap14.pdf` 教材。部分简单数值例题和方便记忆的比喻是额外教学补充，并非课件原题。Lec01–05 原记录未改动。
