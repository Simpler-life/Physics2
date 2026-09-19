# Chap01 Exercise 3 — Dipole–Dipole Force（未解决）

## 原题
<img width="1152" height="162" alt="image" src="https://github.com/user-attachments/assets/72303894-653a-421e-a2f7-cc76575dfdb0" />

An electric dipole (mathbf p_2) is located at position (mathbf r) relative to a second dipole (mathbf p_1), with (r) much larger than the size of either dipole. Find the force exerted on (mathbf p_2) by (mathbf p_1), expressed in terms of (mathbf p_1), (mathbf p_2) and (mathbf r).

**Hint:** write (mathbf p_2) as a pair of charges (pm q_2) at
[
mathbf r pm rac{mathbf d_2}{2},
]
and expand the field of (mathbf p_1) to first order in (mathbf d_2), as was done for the dipole field itself in Section 1.4.

> 来源：chap01.pdf, Section 1.6, Exercise 3。PDF 的自动文本抽取有部分符号乱码，因此这里按上下文恢复为标准记号 (r,q_2)。

---

## 已经理解的内容

### 1. Electric dipole 的定义

[
mathbf p=qmathbf d
]

其中 (mathbf d) 是从负电荷 (-q) 指向正电荷 (+q) 的位移矢量。

### 2. 本题的几何意义

- (mathbf p_1)：第一个 dipole 的偶极矩。
- (mathbf p_2)：第二个 dipole 的偶极矩。
- (mathbf r)：从 dipole 1 中心指向 dipole 2 中心的位置矢量。
- (r=|mathbf r|)。
- 条件 (rgg d_1,d_2) 说明可以使用 dipole 的远场近似。

### 3. dipole 1 的远场

[
mathbf E_1(mathbf r)
=
rac{1}{4piarepsilon_0r^3}
left[
3(mathbf p_1cdothat{mathbf r})hat{mathbf r}
-mathbf p_1

ight].
]

### 4. 为什么只拆 (mathbf p_2)

(mathbf p_1) 作为场源，已有远场公式，可以直接使用。

将 (mathbf p_2=q_2mathbf d_2) 拆成：

- (+q_2) 位于 (mathbf r+mathbf d_2/2)
- (-q_2) 位于 (mathbf r-mathbf d_2/2)

点电荷在电场中的受力仍然只是

[
mathbf F=qmathbf E.
]

因此：

[
mathbf F
=
q_2left[
mathbf E_1left(mathbf r+rac{mathbf d_2}{2}
ight)
-
mathbf E_1left(mathbf r-rac{mathbf d_2}{2}
ight)

ight].
]

### 5. 当前推到的关键中间式

由于 (d_2ll r)，对整个电场做一阶 Taylor 展开：

[
mathbf E_1left(mathbf rpmrac{mathbf d_2}{2}
ight)
approx
mathbf E_1(mathbf r)
pm
rac12(mathbf d_2cdot
abla)mathbf E_1(mathbf r).
]

相减后：

[
mathbf F
approx
q_2(mathbf d_2cdot
abla)mathbf E_1
=
(mathbf p_2cdot
abla)mathbf E_1.
]

---

## 目前还没有真正掌握的地方

1. **Taylor 一阶近似**
   - 还不熟悉为什么
   [
   f(x+h)approx f(x)+hf'(x)
   ]
   以及它在三维矢量场中为什么变成
   [
   mathbf E(mathbf r+deltamathbf r)
   approx
   mathbf E(mathbf r)
   +(deltamathbf rcdot
abla)mathbf E.
   ]

2. **(
abla) 与方向导数**
   - 不熟悉
   [
   
abla
   =
   hat{mathbf x}rac{partial}{partial x}
   +
   hat{mathbf y}rac{partial}{partial y}
   +
   hat{mathbf z}rac{partial}{partial z}.
   ]
   - 目前只能暂时理解 ((mathbf dcdot
abla)mathbf E) 为“沿 (mathbf d) 方向看电场变化多快”。

3. **完整展开**
   - 已知道只展开
   [
   |mathbf rpmmathbf d_2/2|^{-3}
   ]
   还不够，因为 dipole 电场里的 (hat{mathbf r})、(mathbf p_1cdothat{mathbf r}) 也会随位置变化。
   - 还没有熟练掌握如何从
   [
   mathbf F=(mathbf p_2cdot
abla)mathbf E_1
   ]
   展开到最终四项矢量表达式。

---

## 最终答案（暂存，待之后真正推懂）

[
oxed{
mathbf F
=
rac{3}{4piarepsilon_0 r^4}
left[
(mathbf p_1cdothat{mathbf r})mathbf p_2
+
(mathbf p_2cdothat{mathbf r})mathbf p_1
+
(mathbf p_1cdotmathbf p_2)hat{mathbf r}
-
5(mathbf p_1cdothat{mathbf r})
(mathbf p_2cdothat{mathbf r})
hat{mathbf r}

ight]
}
]

### 考试检查

dipole 远场满足

[
Esim r^{-3},
]

再对空间变化一次，因此 dipole–dipole force 应满足

[
Fsim r^{-4}.
]

若最终答案不是 (1/r^4) 量级，需要检查。
