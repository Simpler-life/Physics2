# Chap01 Exercise 3 — Dipole–Dipole Force（未解决）

## 原题

<img width="1152" height="162" alt="image" src="https://github.com/user-attachments/assets/72303894-653a-421e-a2f7-cc76575dfdb0" />

---

## 已经理解的内容

### 1. Electric dipole 的定义

$$
\mathbf p=q\mathbf d
$$

其中 $\mathbf d$ 是从负电荷 $-q$ 指向正电荷 $+q$ 的位移矢量。

### 2. 本题的几何意义

- $\mathbf p_1$：第一个 dipole 的偶极矩。
- $\mathbf p_2$：第二个 dipole 的偶极矩。
- $\mathbf r$：从 dipole 1 中心指向 dipole 2 中心的位置矢量。
- $r=|\mathbf r|$。
- 条件 $r\gg d_1,d_2$ 说明可以使用 dipole 的远场近似。

### 3. dipole 1 的远场

$$
\mathbf E_1(\mathbf r)
=
\frac{1}{4\pi\varepsilon_0 r^3}
\left[
3(\mathbf p_1\cdot\hat{\mathbf r})\hat{\mathbf r}
-\mathbf p_1
\right].
$$

### 4. 为什么只拆 $\mathbf p_2$

$\mathbf p_1$ 作为场源，已有远场公式，可以直接使用。

将 $\mathbf p_2=q_2\mathbf d_2$ 拆成：

- $+q_2$ 位于 $\mathbf r+\mathbf d_2/2$
- $-q_2$ 位于 $\mathbf r-\mathbf d_2/2$

点电荷在电场中的受力仍然只是

$$
\mathbf F=q\mathbf E.
$$

因此：

$$
\mathbf F
=
q_2\left[
\mathbf E_1\left(\mathbf r+\frac{\mathbf d_2}{2}\right)
-
\mathbf E_1\left(\mathbf r-\frac{\mathbf d_2}{2}\right)
\right].
$$

### 5. 当前推到的关键中间式

由于 $d_2\ll r$，对整个电场做一阶 Taylor 展开：

$$
\mathbf E_1\left(\mathbf r\pm\frac{\mathbf d_2}{2}\right)
\approx
\mathbf E_1(\mathbf r)
\pm
\frac12(\mathbf d_2\cdot\nabla)\mathbf E_1(\mathbf r).
$$

相减后：

$$
\mathbf F
\approx
q_2(\mathbf d_2\cdot\nabla)\mathbf E_1
=
(\mathbf p_2\cdot\nabla)\mathbf E_1.
$$

---

## 目前还没有真正掌握的地方

1. **Taylor 一阶近似**
   - 还不熟悉为什么
     $$
     f(x+h)\approx f(x)+hf'(x)
     $$
     以及它在三维矢量场中为什么变成
     $$
     \mathbf E(\mathbf r+\delta\mathbf r)
     \approx
     \mathbf E(\mathbf r)
     +(\delta\mathbf r\cdot\nabla)\mathbf E.
     $$

2. **$\nabla$ 与方向导数**
   - 不熟悉
     $$
     \nabla
     =
     \hat{\mathbf x}\frac{\partial}{\partial x}
     +
     \hat{\mathbf y}\frac{\partial}{\partial y}
     +
     \hat{\mathbf z}\frac{\partial}{\partial z}.
     $$
   - 目前只能暂时理解 $(\mathbf d\cdot\nabla)\mathbf E$ 为“沿 $\mathbf d$ 方向看电场变化多快”。

3. **完整展开**
   - 已知道只展开
     $$
     \left|\mathbf r\pm\frac{\mathbf d_2}{2}\right|^{-3}
     $$
     还不够，因为 dipole 电场里的 $\hat{\mathbf r}$、$\mathbf p_1\cdot\hat{\mathbf r}$ 也会随位置变化。
   - 还没有熟练掌握如何从
     $$
     \mathbf F=(\mathbf p_2\cdot\nabla)\mathbf E_1
     $$
     展开到最终四项矢量表达式。

---

## 最终答案（暂存，待之后真正推懂）

$$
\boxed{
\mathbf F
=
\frac{3}{4\pi\varepsilon_0 r^4}
\left[
(\mathbf p_1\cdot\hat{\mathbf r})\mathbf p_2
+
(\mathbf p_2\cdot\hat{\mathbf r})\mathbf p_1
+
(\mathbf p_1\cdot\mathbf p_2)\hat{\mathbf r}
-
5(\mathbf p_1\cdot\hat{\mathbf r})
(\mathbf p_2\cdot\hat{\mathbf r})
\hat{\mathbf r}
\right]
}
$$

### 考试检查

dipole 远场满足

$$
E\sim r^{-3},
$$

再对空间变化一次，因此 dipole–dipole force 应满足

$$
F\sim r^{-4}.
$$

若最终答案不是 $1/r^4$ 量级，需要检查。
