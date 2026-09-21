# Lecture 1 学习记录：Coulomb's Law and Electric Field

> 状态：学习中  
> 当前停点：均匀带电圆盘轴线上电场；远场近似暂未继续。

## 1. 电荷与基本关系

电荷量子化：

\`\`\`math
q=ne
\`\`\`

其中 $e$ 为基本电荷。

电荷守恒：总电荷不会凭空产生或消失。

## 2. Coulomb 定律

两点电荷之间的静电力：

\`\`\`math
\vec F_{12}
=
\frac{1}{4\pi\varepsilon_0}
\frac{q_1q_2}{r_{12}^2}
\hat r_{12}
\`\`\`

### 方向记号

若采用“从 1 指向 2”的约定：

\`\`\`math
\vec r_{12}=\vec r_2-\vec r_1
\`\`\`

\`\`\`math
r_{12}=|\vec r_{12}|
\`\`\`

\`\`\`math
\hat r_{12}
=
\frac{\vec r_{12}}{|\vec r_{12}|}
\`\`\`

要区分：

- $\vec r$：位置/位移向量
- $r=|\vec r|$：长度
- $\hat r$：单位方向向量

并且：

\`\`\`math
\frac{\hat r}{r^2}
=
\frac{\vec r}{r^3}
\`\`\`

## 3. 叠加原理

多个点电荷共同作用时，总力或总电场是各自贡献的**向量和**：

\`\`\`math
\vec F_{\text{total}}=\sum_i \vec F_i
\`\`\`

\`\`\`math
\vec E_{\text{total}}=\sum_i \vec E_i
\`\`\`

## 4. 电场定义

\`\`\`math
\vec E=\frac{\vec F}{q_0}
\`\`\`

反过来：

\`\`\`math
\vec F=q\vec E
\`\`\`

点电荷 $Q$ 产生的电场：

\`\`\`math
\vec E
=
\frac{1}{4\pi\varepsilon_0}
\frac{Q}{r^2}\hat r
\`\`\`

## 5. 连续电荷：从求和到积分

核心思想：

> 把连续带电体切成无穷多个小电荷 $dq$，计算每个 $dq$ 产生的 $d\vec E$，再全部相加。

\`\`\`math
d\vec E
=
\frac{1}{4\pi\varepsilon_0}
\frac{dq}{r^2}\hat r
\`\`\`

\`\`\`math
\vec E=\int d\vec E
\`\`\`

三种常见电荷密度：

### 线电荷

\`\`\`math
\lambda=\frac{dq}{dl}
\qquad\Rightarrow\qquad
dq=\lambda\,dl
\`\`\`

### 面电荷

\`\`\`math
\sigma=\frac{dq}{dA}
\qquad\Rightarrow\qquad
dq=\sigma\,dA
\`\`\`

### 体电荷

\`\`\`math
\rho=\frac{dq}{dV}
\qquad\Rightarrow\qquad
dq=\rho\,dV
\`\`\`

## 6. 对称性

连续电荷积分中，不能只对电场大小直接求和，因为电场是向量。

常见做法：

1. 先判断哪些方向的分量由于对称性两两抵消；
2. 只保留不会抵消的分量；
3. 对该分量积分。

## 7. 均匀带电圆盘轴线上电场

半径 $R$、面电荷密度 $\sigma$ 的均匀带电圆盘，在中心轴线上距离中心 $z$ 的位置求电场。

把圆盘切成半径 $r$、厚度 $dr$ 的同心圆环。

小圆环面积：

\`\`\`math
dA=2\pi r\,dr
\`\`\`

所以：

\`\`\`math
dq=\sigma\,dA
=
2\pi\sigma r\,dr
\`\`\`

观察点到该圆环任一点的距离：

\`\`\`math
s=\sqrt{z^2+r^2}
\`\`\`

由于横向分量对称抵消，只剩 $z$ 分量：

\`\`\`math
dE_z=dE\cos\theta
\`\`\`

其中：

\`\`\`math
\cos\theta=\frac{z}{\sqrt{z^2+r^2}}
\`\`\`

得到：

\`\`\`math
dE_z
=
\frac{1}{4\pi\varepsilon_0}
\frac{z\,dq}{(z^2+r^2)^{3/2}}
\`\`\`

代入 $dq$：

\`\`\`math
dE_z
=
\frac{\sigma z}{2\varepsilon_0}
\frac{r\,dr}{(z^2+r^2)^{3/2}}
\`\`\`

积分：

\`\`\`math
E_z
=
\frac{\sigma z}{2\varepsilon_0}
\int_0^R
\frac{r\,dr}{(z^2+r^2)^{3/2}}
\`\`\`

令：

\`\`\`math
u=z^2+r^2
\`\`\`

则：

\`\`\`math
du=2r\,dr
\`\`\`

最终：

\`\`\`math
\boxed{
\vec E
=
\frac{\sigma}{2\varepsilon_0}
\left(
1-\frac{z}{\sqrt{z^2+R^2}}
\right)\hat z
}
\`\`\`

## 8. 当前理解重点

目前已经掌握的核心不是“背最后答案”，而是连续电荷题的通用流程：

\`\`\`math
\text{选微元}
\rightarrow
dq
\rightarrow
d\vec E
\rightarrow
\text{利用对称性取分量}
\rightarrow
\int d\vec E
\`\`\`

## 9. 暂停点

以下内容暂时不继续，统一放入仓库根目录的 \`Pending/\` 中管理：

- 远场近似
- Taylor / binomial approximation
- Lecture 1 后续尚未系统补齐的大学数学工具
