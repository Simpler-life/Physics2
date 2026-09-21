# Physics2

普通物理 II 学习仓库。这个仓库不是资料堆放区，而是一个可持续维护的学习系统。

## 目录职责

### `Lecture_Notes/`
按课程 Lecture 组织的**主线学习笔记**。

只写已经真正讲过、理解过或明确确认过的内容。  
不要把“以后要学”的知识提前写成已掌握内容。

当前：
- [Lecture 1：Coulomb's Law and Electric Field](Lecture_Notes/Lecture01_Coulomb_and_Electric_Field.md)

### `Math_for_Physics/`
物理中遇到的**大学新数学工具**。

适合放：
- 向量微积分
- 多重积分 / 曲面积分 / 线积分
- Taylor 展开与近似
- 梯度、散度、旋度
- 坐标系与微元
- 其他在物理中实际用到、且高中阶段未系统学习的数学

高中数学默认基础较扎实，不把普通三角函数、基础代数等重复整理成独立数学笔记。

当前入口：
- [Physics Math Toolkit](Math_for_Physics/README.md)

### `Unresolved_Problems/`
**尚未真正解决的具体题目**，是所有“待做题目”的唯一来源（source of truth）。

每道未解决题应有自己的 Markdown 文件，里面可以保存：
- 原题 / 原题截图链接
- 已经理解的部分
- 当前推导
- 卡住的位置
- 暂存答案（若有，必须标明尚未真正理解）
- 需要补的知识

规则：
- `Pending/Problems_TODO.md` 只索引这里已经存在的题目文件。
- 不允许仅凭聊天里出现过一道题，就直接把它写进 `Problems_TODO.md`。
- TODO 中不复制题目全文，避免与题目笔记产生两个版本。

### `Pending/`
**学习暂存区 / 索引区**，不作为详细知识或题目的主内容存储位置。

- [Knowledge_TODO.md](Pending/Knowledge_TODO.md)：尚未学习、尚未补完的知识。
- [Problems_TODO.md](Pending/Problems_TODO.md)：仅索引 `Unresolved_Problems/` 中的未解决题。
- [README.md](Pending/README.md)：Pending 使用说明。

## AI 维护规则

以下规则供之后所有 AI / Codex 修改本仓库时遵守。

### 1. 先读后改
在修改仓库前：
1. 先读取根目录 `README.md`。
2. 再读取目标目录的 README（若存在）。
3. 修改已有文件前，必须先读取当前内容，避免覆盖用户已有笔记。

### 2. 单一信息源
同一内容只保留一个“详细正文”来源。

- Lecture 知识正文 → `Lecture_Notes/`
- 数学工具正文 → `Math_for_Physics/`
- 未解决题正文 → `Unresolved_Problems/`
- 待办列表 → `Pending/`，只做索引和状态，不复制长正文

### 3. 已学与未学必须分开
- 只有用户已经学过、确认理解或正在系统学习的内容，才能写进主线笔记。
- 尚未学习但已发现的重要知识，写入 `Pending/Knowledge_TODO.md`。
- 不得把模型自己的补充知识伪装成“用户已掌握”。

### 4. 未解决题管理
新增待解决题时：
1. 先在 `Unresolved_Problems/` 创建独立题目文件。
2. 再在 `Pending/Problems_TODO.md` 添加相对链接。
3. TODO 只保留：题目名、状态、链接、极短备注。
4. 如果没有对应的 `Unresolved_Problems/` 文件，则不能出现在 `Problems_TODO.md`。

题目解决后：
- 从 `Pending/Problems_TODO.md` 删除该条目。
- 不要直接丢失解题记录；若以后建立 solved/archive 目录，再按目录规则迁移。未建立前，先保留原题文件并把标题/状态改为“已解决”，但它不再属于 TODO 索引。

### 5. 删除规则
AI 不应随意删除有学习价值的正文。

可以自主删除：
- 明确重复的索引项
- 已失效的 TODO 引用
- 因 AI 自己误写造成的错误/重复内容

以下情况不要直接删除正文，除非用户明确要求：
- 用户的学习记录
- 题目推导过程
- 错题复盘
- 原题来源信息
- 已形成的知识笔记

### 6. 更新规则
每次用户学习进度发生变化时：
- 已学新知识 → 更新对应 Lecture 笔记
- 学懂新的大学数学 → 更新 `Math_for_Physics/`
- 暂时跳过的知识 → 更新 `Pending/Knowledge_TODO.md`
- 新增未解决题 → 先建 `Unresolved_Problems/` 文件，再更新 `Problems_TODO.md`
- 题目完成 → 从 `Problems_TODO.md` 移除

### 7. 链接规则
仓库内部优先使用**相对链接**，例如：

```markdown
[Chap01 Exercise 3](../Unresolved_Problems/Chap01_Exercise03_Dipole_Dipole_Force.md)
```

不要把完整 GitHub URL 当作内部唯一导航方式，以便仓库 clone 到本地后仍能正常跳转。

### 8. Markdown / LaTeX 规则
- 行内公式使用 `$...$`。
- GitHub 块级公式统一使用：

````markdown
```math
E=mc^2
```
````

- 不要转义 fenced code/math block 的反引号。
- 修改后应检查 GitHub 实际渲染格式，避免裸 LaTeX。

### 9. 命名规则
- Lecture：`LectureXX_Topic.md`
- 未解决题：`ChapXX_ExerciseYY_Short_Title.md`
- 数学专题：建议 `XX_Topic.md`
- 文件名使用英文/数字/下划线，正文可中文。

### 10. 修改完成后的最低检查
AI 每次写入后至少确认：
- 文件放在正确目录
- 没有重复正文
- TODO 链接指向真实文件
- 已学/未学状态没有混淆
- LaTeX 没有被错误转义
- 没有无意覆盖用户已有内容
