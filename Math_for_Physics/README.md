# Physics Math Toolkit

这个文件夹只整理《普通物理 II》中真正需要补充的**大学新数学**。高中数学默认已有较扎实基础，因此不再从基础三角函数、普通函数等内容重新讲起。

## 当前状态

符号：

- ✅ 已经结合物理学过
- 🟡 碰到过，但尚未系统整理
- ⬜ 尚未学习 / 待完成

### Lecture 1–3 数学路线

- ✅ **向量与单位方向向量**
  - $\vec r$、$r=|\vec r|$、$\hat r$
  - $\vec r_{12}=\vec r_2-\vec r_1$
  - $\hat r/r^2=\vec r/r^3$

- ✅ **向量分量与对称性**
  - 已在圆盘电场中使用“横向分量抵消、轴向分量相加”

- ✅ **点积 Dot Product**
  - $\vec A\cdot\vec B=AB\cos\theta$
  - 已用于偶极子远场中的 $\vec p\cdot\hat r$
  - Lecture 2 将继续用于电通量

- ✅ **叉积 Cross Product**
  - $|\vec A\times\vec B|=AB\sin\theta$
  - 方向由右手定则决定
  - 已用于 $\vec\tau=\vec p\times\vec E$

- ✅ **极限、远场近似与 leading term**
  - 当观察距离远大于带电体尺寸时，保留主导项
  - 已用于证明远处均匀带电圆盘等效为点电荷

- ✅ **Taylor / binomial approximation（基础一阶）**
  - $|x|\ll1$ 时， $(1+x)^n\approx1+nx$
  - 特别地， $(1+x)^{-1/2}\approx1-x/2$
  - 已用于圆盘远场；更高阶展开和三维矢量场 Taylor 展开仍未系统掌握

- ✅ **从求和到积分**
  - $\sum\rightarrow\int$
  - $dq$
  - $dq=\lambda dl$
  - $dq=\sigma dA$
  - $dq=\rho dV$

- 🟡 **微元的选择**
  - 已学圆环微元 $dA=2\pi r\,dr$
  - 柱坐标、球坐标中的一般微元尚未学

- ⬜ **坐标系与 Jacobian / 体积元**
  - 柱坐标
  - 球坐标
  - $dV=r^2\sin\theta\,dr\,d\theta\,d\phi$

- ⬜ **曲面积分与电通量**
  - $d\vec A$
  - $\int \vec E\cdot d\vec A$
  - $\oint$

- ⬜ **Gauss 定律中对称性的数学处理**

- ⬜ **线积分**
  - $\int_C \vec E\cdot d\vec l$

- ⬜ **保守场与路径无关**

- ⬜ **偏导数与梯度**
  - $\partial/\partial x$
  - $\nabla V$
  - $\vec E=-\nabla V$

- ⬜ **等势面与梯度几何意义**

## 管理方式

- 已经真正学懂的大学数学再整理进本目录。
- 尚未学习的知识统一记在 [`Pending/Knowledge_TODO.md`](../Pending/Knowledge_TODO.md)。
- 未解决题本身存放在 [`Unresolved_Problems/`](../Unresolved_Problems/)；[`Pending/Problems_TODO.md`](../Pending/Problems_TODO.md) 只作为其索引。
- 完整仓库维护规则见 [根目录 README](../README.md)。
