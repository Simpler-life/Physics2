# Homework #8 · P8-5 — Thin Lens / Lensmaker's Equation（待真正理解）

- 日期：2026-11-21
- 所属：普通物理 II，Lecture 16，Homework #8，P8-5
- 状态：**[ ] 未解决——作业答案直接抄写，尚未真正理解或独立推导**
- 资料来源：用户上传的 `homework08_25.pdf` 第 7 页（P8-5）
- 关联知识：[P8-4 近轴小角近似待补](../Pending/Knowledge_TODO.md)

## 原题目标
<img width="1284" height="464" alt="image" src="https://github.com/user-attachments/assets/9067f34b-a397-40cf-8a5c-6aaaaa107e56" />

A thin lens with index of refraction $n$ is surrounded by medium with refractive index $n_{\mathrm{medium}}$. Show that

```math
\frac{1}{f}=\left(\frac{n}{n_{\mathrm{medium}}}-1\right)\left(\frac{1}{r_1}-\frac{1}{r_2}\right).
```

其中 $r_1$ 和 $r_2$ 分别为靠近物体与远离物体的透镜表面曲率半径。

## 本次学习真实情况

- 已看到 AI 提供的两次球面折射与消去中间像距的推导，并将答案抄写到作业中。
- 在第二次折射列式的选择题中，曾选择 **A（缺少负号）**，正确关系需要第二面物距约为 $-i_1$。
- **尚不能确认自己理解**：为什么第一次折射所得中间像对于第二面是虚物；薄透镜为何可以写 $p_2\approx -i_1$；为什么 $r_1$、$r_2$ 是有符号曲率半径；焦距如何从 $p\to\infty$ 得到。
- 不把“已经抄到答案”误标为“已掌握”。

## 暂存推导（来自辅导答案，尚未独立验证）

第一次折射（周围介质 $\to$ 透镜）：

```math
\frac{n_{\mathrm{medium}}}{p}+\frac{n}{i_1}=\frac{n-n_{\mathrm{medium}}}{r_1}.
```

第二次折射（透镜 $\to$ 周围介质）：

```math
-\frac{n}{i_1}+\frac{n_{\mathrm{medium}}}{i}=\frac{n_{\mathrm{medium}}-n}{r_2}.
```

两式相加消去 $i_1$，得到

```math
\frac{1}{p}+\frac{1}{i}=\left(\frac{n}{n_{\mathrm{medium}}}-1\right)\left(\frac{1}{r_1}-\frac{1}{r_2}\right).
```

对于来自无限远处的轴上物点，取 $p\to\infty$、$i=f$，得到题目目标式。

> 上述仅供下次回顾，不代表用户已经理解；尤其需要检查符号约定与几何图像。

## 下次复习任务

- [ ] 画出两面折射前后的光路图，解释中间像、虚物与负物距。
- [ ] 对双凸透镜分别判断 $r_1$ 与 $r_2$ 的正负号。
- [ ] 不看答案，自己从 P8-4 球面折射公式推导两次折射并相加。
- [ ] 用 $p\to\infty$ 解释焦距定义，而不只是代入。
- [ ] 结合近轴近似的待补知识，解释推导成立条件。
