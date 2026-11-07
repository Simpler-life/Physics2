# 2023 期中第 1 题：导体球、电势符号与镜像法错题复盘

> 状态：🟡 已经独立重做 (d) 并得到正确表达式；(a)、(b)、(c) 在讲解/批注后得到纠正，尚待再次独立完整重做。
>
> 来源：用户手写 2023 年期中第 1 题两轮解答（2026-11-07）。原题完整参数和图示以原卷为准。
>
> 主题：Gauss 定律、电势积分符号、静电平衡、孤立与接地导体、镜像法、余弦定理。

## 一、题目模型与符号

<img width="860" height="1108" alt="870c7c218e465e1b3bcea8eec89e2d4c" src="https://github.com/user-attachments/assets/4bfceb4a-35a2-4746-ad65-9c46bbb5eb2e" />


- 半径 $R$ 的球形导体，初始净电荷 $Q$；无穷远电势为零。
- (a) 单独存在时求球内外电场与电势。
- (b) 球外距离球心 $d>R$ 处放真实点电荷 $+q$，导体保持孤立，求球心电场与电势。
- (c) 导体接地，求最终球面总电荷 $Q_2$，以及 $Q-Q_2$。
- (d) 用镜像法表示球外任一点 $P$ 的电势。
- 用 $k=1/(4\pi\varepsilon_0)$；球心到观察点的距离记为 $\rho=OP$，避免与球半径 $R$ 混淆；角 $\theta$ 是 $\overrightarrow{OP}$ 与指向真实电荷方向的夹角。

## 二、最初的错误与订正

<img width="818" height="1180" alt="image" src="https://github.com/user-attachments/assets/c0d099d3-a01a-423e-aea4-51720af736c0" />
<img width="926" height="1028" alt="image" src="https://github.com/user-attachments/assets/793f25e5-b169-40d6-9576-f5d10876831a" />


### 错误 1：电势积分漏负号

最初写法等价于：

```math
V(r)=V(R)+\int_R^r E(l)\,dl
```

错误原因：电势沿电场方向降低，应使用：

```math
V(r)-V(R)=-\int_R^r\vec E\cdot d\vec l
```

对于 $r>R$，在单独带电的球外：

```math
E(r)=\frac{kQ}{r^2}
```

因此：

```math
V(r)=\frac{kQ}{R}-\int_R^r\frac{kQ}{l^2}\,dl
=\frac{kQ}{R}+kQ\left(\frac1r-\frac1R\right)
=\boxed{\frac{kQ}{r}}
```

球内（$r<R$）：

```math
\boxed{\vec E=0,\qquad V=\frac{kQ}{R}}
```

考场自检：对于 $Q>0$，$V(r)$ 应在球外随 $r$ 增大而下降，并在无穷远趋向零。

### 错误 2：将外部点电荷的电场误作球心总电场

最初 (b) 写成：

```math
E_{\mathrm{center}}=\frac{kq}{d^2}
```

错因：只算了外部真实点电荷贡献，漏掉导体表面自由电荷的重新分布及其电场。静电平衡时导体内部总电场为零：

```math
\boxed{\vec E_{\mathrm{center}}=0}
```

但球心电势的原结果是对的：

```math
\boxed{V_{\mathrm{center}}=k\left(\frac{Q}{R}+\frac{q}{d}\right)}
```

原因：孤立导体球总电荷仍是 $Q$；球面任意微元到球心的距离都是 $R$，所以球面分布即使不均匀，球面电荷在中心产生的电势仍是 $kQ/R$。再叠加外部点电荷贡献 $kq/d$。

考场自检：导体静电平衡时，“内部电场为零”和“内部电势为常数”不能混同为“内部电势为零”。

### 错误 3：接地后只写 $V_{\mathrm{surface}}=0$，未继续求 $Q_2$

已正确识别：**接地边界条件是球面电势为零，但不等于球面没有电荷。**

外部点电荷 $q>0$ 存在时，即使导体未接地，表面电荷已重新分布；接地后还能与大地交换电荷，因此总电荷不再固定为 $Q$。

半径 $R$ 的接地导体球，对应镜像法：

```math
q'=-\frac{qR}{d},\qquad a=\frac{R^2}{d}
```

其中虚构镜像电荷 $q'$ 位于球内、球心与真实电荷连线上。它用于重建**球外**电势，不是真实存在于导体球中的点电荷。

对于这个标准接地球模型，由高斯定律或远场等价性可知球面净感应电荷等于镜像电荷：

```math
\boxed{Q_2=q'=-\frac{qR}{d}}
```

从原始孤立球净电荷 $Q$ 变化到接地后的净电荷 $Q_2$：

```math
\boxed{Q-Q_2=Q+\frac{qR}{d}}
```

这是题目所定义的代数差；若要求电子流向或某方向的电荷流量，需单独交代正负方向。

特别注意：未接地的孤立球若总电荷固定为 $Q$，它的镜像系统通常还需要在球心增加一个等效电荷以满足总电荷条件。详细理论见 [Chapter 5 Exercise 3 镜像法误区](../../../Mistake/Chap05_Exercise03_Image_Charge_Mistakes.md)。

## 三、(d) 用户独立重做：判定正确

第二轮手写解答中，已经正确写出镜像电荷、利用余弦定理计算两段距离，并写出了球外观察点 $P$ 的电势。

令 $\rho=OP$ 且 $\rho\ge R$，$P$ 不与真实点电荷重合：

```math
r_{\mathrm{real}}
=\sqrt{\rho^2+d^2-2\rho d\cos\theta}
```

```math
r_{\mathrm{image}}
=\sqrt{\rho^2+a^2-2\rho a\cos\theta}
```

由叠加原理：

```math
V(P)
=\frac{1}{4\pi\varepsilon_0}
\left(
\frac{q}{r_{\mathrm{real}}}
+\frac{q'}{r_{\mathrm{image}}}
\right)
```

代入镜像参数：

```math
\boxed{
V(P)=\frac{1}{4\pi\varepsilon_0}
\left[
\frac{q}{\sqrt{\rho^2+d^2-2\rho d\cos\theta}}
-
\frac{qR/d}{\sqrt{\rho^2+(R^2/d)^2-2\rho(R^2/d)\cos\theta}}
\right]
}
```

**(d) 完成正确。** 题目若没有给出 $OP$ 的具体数值，不影响答案：题目要求的是电势表达式（关于观察点位置的函数），不是数值电势。

补充边界检查：当 $\rho=R$，由 $r_{\mathrm{image}}=(R/d)r_{\mathrm{real}}$ 可得整个球面 $V=0$，满足接地条件。

## 四、考试复盘清单

1. 电势差写成 $V(B)-V(A)=-\int_A^B\vec E\cdot d\vec l$，特别检查负号。
2. 带电导体遇到外部电荷后，一般不再保持均匀表面电荷；导体内部静电总电场仍为零。
3. 电势是标量：球心处所有球面电荷到中心等距，可用总量求球面电荷的电势贡献。
4. 先分清接地（$V=0$）还是孤立给定净电荷（总量固定，$V$ 不一定为零）。
5. 镜像法先定求解区域与边界，再构造球内虚电荷；它只保证球外等效。
6. 没有指定 $OP$ 数值并不影响求函数 $V(P)$，引入 $\rho$ 和 $\theta$ 即可。
7. 第 (d) 部分已独立做对；(a)–(c) 纠正后应再遮住笔记复做一次，不提前标记全部掌握。

## 五、短自测（待独立重做）

- 不看资料，从 $E(r)=kQ/r^2$ 推出球外 $V(r)$，检查负号。
- 在外部电荷 $q$ 存在时，解释为什么孤立球中心 $\vec E=0$，却有 $V=k(Q/R+q/d)$。
- 不看笔记，写出接地球的 $q'$、$a$、$Q_2$，并解释为什么没有 $OP$ 的具体数字仍能写出 $V(P)$。
