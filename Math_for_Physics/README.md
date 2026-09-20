# Physics Math Toolkit

这个文件夹专门整理《普通物理 II》里真正会用到的数学工具。目标不是单独学一门高等数学，而是做到：看到物理公式时，知道每个数学符号在表达什么；知道为什么这样写；知道做题时怎么操作。

当前进度：**Lecture 1–3（静电场、Gauss 定律、电势）**

## 学习原则

- 按依赖关系学习，一次只学一个主题。
- 每个主题都包含：直觉 → 数学定义 → 物理里的意义 → 最小例题 → 易错点。
- 不默认已经熟练掌握高数或线代。
- 只讲当前物理课程真正需要的深度；以后遇到新数学工具再扩充。

## Lecture 1–3 数学路线

1. **向量最基础：标量、向量、坐标分量、单位向量**
   - 为什么电场/力必须写成向量
   - i-hat、j-hat、k-hat 与 r-hat
   - 向量的模、加减、分解

2. **三角函数与向量分解**
   - sin(theta)、cos(theta) 的几何意义
   - 为什么常出现 E cos(theta)
   - 对称性导致某些分量抵消

3. **点积 Dot Product**
   - A·B = AB cos(theta)
   - 投影
   - 功 dW = F·ds
   - 电通量 dPhi = E·dA

4. **叉积 Cross Product**
   - A×B
   - 右手定则
   - 面积解释
   - 力矩 tau = p×E

5. **函数、极限与近似**
   - 一元/多元函数
   - “r >> d”到底是什么意思
   - 主导项（leading term）
   - 远场近似

6. **Taylor 展开与常用小量近似**
   - (1+x)^n 的近似
   - sin x ≈ x
   - cos x ≈ 1-x^2/2
   - 电偶极子远场近似

7. **从求和到积分**
   - sum -> integral
   - 微元是什么意思
   - 为什么连续电荷必须积分
   - dq = lambda dl, dq = sigma dA, dq = rho dV

8. **坐标系与微元**
   - 直角坐标、柱坐标、球坐标
   - 坐标变换
   - ds、dA、dV
   - 球坐标体积元

9. **曲面积分与电通量**
   - 面元向量 dA
   - Phi = integral E·dA
   - 闭合曲面与 closed-surface integral
   - Gauss 定律里“积分整个表面”是什么意思

10. **对称性作为计算工具**
    - 球对称、柱对称、平面对称
    - 为什么对称性允许把 E 从积分号里拿出来
    - 什么时候不能这样做

11. **线积分**
    - 路径、微小位移 ds
    - integral_C F·ds
    - 为什么电势差是电场的线积分

12. **保守场与路径无关**
    - 同起点终点，不同路径
    - 闭合回路积分
    - 静电力为什么对应势能/电势

13. **偏导数与梯度 Gradient**
    - V(x,y,z) 是什么
    - partial V / partial x 与普通导数的区别
    - grad V
    - E = -grad V

14. **等势面与梯度的几何意义**
    - 梯度为什么垂直等势面
    - 电场为什么指向电势下降最快方向

## 文件规划

01_Vector_Basics.md  
02_Trigonometry_and_Components.md  
03_Dot_Product.md  
04_Cross_Product.md  
05_Limits_and_Approximations.md  
06_Taylor_Expansion.md  
07_Sum_to_Integral.md  
08_Coordinates_and_Differentials.md  
09_Surface_Integral_and_Flux.md  
10_Symmetry.md  
11_Line_Integral.md  
12_Conservative_Field.md  
13_Partial_Derivatives_and_Gradient.md  
14_Equipotential_and_Gradient.md

> 随学习进度逐个补充，不一次性塞满。
