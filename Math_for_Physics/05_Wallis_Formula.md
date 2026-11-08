# 05 点火公式（Wallis 公式）

> 主题：三角函数幂的定积分。常用区间为 $[0,\pi/2]$。

## 1. 公式

设 $n$ 为非负整数，定义

$$
I_n=\int_0^{\pi/2}\sin^n x\,dx
=\int_0^{\pi/2}\cos^n x\,dx.
$$

递推关系为

$$
\boxed{I_n=\frac{n-1}{n}I_{n-2}\quad(n\ge2)}
$$

初值为 $I_0=\pi/2$，$I_1=1$。

- **偶数 $n=2m$**：

$$
\boxed{I_{2m}=\frac{(2m-1)!!}{(2m)!!}\cdot\frac{\pi}{2}}
$$

- **奇数 $n=2m+1$**：

$$
\boxed{I_{2m+1}=\frac{(2m)!!}{(2m+1)!!}}
$$

这里 $k!!$ 表示双阶乘：例如 $5!!=5\cdot3\cdot1$，$6!!=6\cdot4\cdot2$。

## 2. 例题

**例 1：偶数次幂**

$$
\int_0^{\pi/2}\sin^6x\,dx
=\frac56\cdot\frac34\cdot\frac12\cdot\frac\pi2
=\boxed{\frac{5\pi}{32}}.
$$

**例 2：奇数次幂**

$$
\int_0^{\pi/2}\cos^5x\,dx
=\frac45\cdot\frac23
=\boxed{\frac8{15}}.
$$

## 3. 为什么成立（分部积分）

对 $n\ge2$，

$$
\begin{aligned}
I_n
&=\int_0^{\pi/2}\sin^{n-1}x\,\sin x\,dx\\
&=\left[-\sin^{n-1}x\cos x\right]_0^{\pi/2}
+(n-1)\int_0^{\pi/2}\sin^{n-2}x\cos^2x\,dx\\
&=(n-1)(I_{n-2}-I_n).
\end{aligned}
$$

所以 $nI_n=(n-1)I_{n-2}$，得到递推关系。正弦与余弦积分相等，可通过代换 $t=\pi/2-x$ 得到。

## 4. 快速记忆与易错点

- 从 $n$ 开始：$\frac{n-1}{n}\cdot\frac{n-3}{n-2}\cdots$，每次上下都减 2。
- **偶数**最后到 $\frac12$，还要乘 $\frac\pi2$。
- **奇数**最后到 $\frac23$，还要乘初值 $I_1=1$。
- 不能把这个公式直接套用到任意积分区间；先检查上下限，必要时利用对称性或换元转化。
- 公式针对单独的 $\sin^n x$ 或 $\cos^n x$；含其他因子时通常需要先化简。
