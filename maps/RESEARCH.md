# RESEARCH · 经典结构继续长向哪里

这是一张远端生长地图，不是必须全部修完的高级目录。七个链接到正文的入口已经有具体计算；其余路线仅标示后续方向，不制造空 Stage，也不表示已具备全部先修。所有研究分支都要在现有 [Core](CORE.md)、[Focus](FOCUS.md) 上继续补相应工具。

<a id="r1"></a>
## R1 · Higher Algebra

范畴 → 链同伦 $\to dg/ A\infty \to$ stable ∞-category → monoidal ∞-category $\to E_{n}/ E\infty$ 代数 → higher Morita。

入口：[HA00 · 从链同伦到高阶代数](../research/HA00.md)。先计算可缩复形与 $\operatorname{Hom}$ 复形，观察只保留同伦类时丢掉的数据。进一步需要同伦论、映射空间、谱与高阶相容性；dg 模型是桥梁，不是所有 ∞-范畴的定义。来源：[Higher Algebra](../SOURCES.md#higher-algebra)。

<a id="r2"></a>
## R2 · Derived Deformation

双数 → 一阶变形 → 导子 / 切空间 → 提升障碍 $\to \operatorname{Ext} \to$ 余切复形 → formal moduli。

入口：[DD00 · 从双数点到导出形变](../research/DD00.md)。贯穿节点 $xy=0$，一阶可动与二阶受阻都能手算。后续需小扩张、形变函子、dg Lie 与次数约定；具体问题的控制复形必须说明。来源：[余切复形](../SOURCES.md#cotangent)、[Formal Moduli](../SOURCES.md#formal-moduli)。

<a id="r3"></a>
## R3 · Derived / Spectral Geometry

重复方程 $\to \operatorname{Tor} \to$ 导出张量 → 导出交集 → simplicial / E∞ 环 → derived / spectral geometry。

入口：[DA00 · 用导出交集保存重复约束](../research/DA00.md)。先比较两轴横交与同一轴自交；高次项记录约束之间的依赖。后续要补下降、导出环及谱，不能把“多算一个 $\operatorname{Tor}$”直接称为完整 spectral geometry。来源：[Higher Algebra](../SOURCES.md#higher-algebra)。

<a id="r4"></a>
## R4 · Derived Moduli / Shifted Symplectic

模问题的函子 → 自同构与群胚 → stacks → derived moduli → 余切复形 → shifted symplectic / virtual geometry。

由 [DD00](../research/DD00.md)、[S101](../stages/S101.md) 出发，先问为什么分类集合丢失对象的自同构。还需下降、栈、导出微分形式；shifted symplectic 的“闭”含高阶相容数据，不只是移位一个双线性配对。来源：[PTVV](../SOURCES.md#shifted)。本路线尚无独立 Stage。

<a id="r5"></a>
## R5 · Categorical / Geometric Representation

箭图与 $\operatorname{Ext} \to$ 最高权范畴 / category $O \to$ 导出等价 → perverse sheaves / D-modules → geometric Satake → categorification / KLR。

入口：[CR00 · 从箭图的 Grothendieck 群看范畴化](../research/CR00.md)。先明确 $K_{0}$ 忘记了哪个非分裂连接。不同后续分支另需层论、旗簇或量子群；这不是唯一线性先修链。来源：[Khovanov–Lauda](../SOURCES.md#klr)。

<a id="r6"></a>
## R6 · Cluster / Calabi–Yau / Higher AR

箭图表示 → mutation → cluster algebra / cluster category $\to 2-$Calabi–Yau → higher Auslander–Reiten。

从 [S049](../stages/S049.md)、[S050](../stages/S050.md) 的秩和扩张开始，新的问题是改变生成数据时怎样追踪表示与不变量。需补 mutation 规则、三角范畴与 AR 三角；不能把普通箭头反向自动叫 mutation。本路线尚无独立 Stage。

<a id="r7"></a>
## R7 · dg / A∞ / Noncommutative Geometry

结合代数 → 模范畴 → Morita → 导出范畴 $\to dg/ A\infty$ 代数 → Calabi–Yau 范畴。

从 [S048](../stages/S048.md) 与 [HA00](../research/HA00.md) 比较“环不同但模论相同”和“复形不同但同伦等价”。后续需 dg 增强与高阶乘法；普通 Morita 等价不自动给任意几何结论。来源：[Higher Algebra](../SOURCES.md#higher-algebra)。本路线尚无独立 Stage。

<a id="r8"></a>
## R8 · Stability / Wall Crossing

曲线线丛与次数 → 向量丛斜率 $\to t-$structure → Bridgeland stability → wall / chamber $\to DT$ 型不变量。

从 [S106](../stages/S106.md)、[S109](../stages/S109.md)、[S096](../stages/S096.md) 汇合。需要补稳定性、Harder–Narasimhan 滤过、心与中心荷；“维数相同”远不足以比较稳定性。本路线尚无独立 Stage。

<a id="r9"></a>
## R9 · Modern Arithmetic Geometry

赋值与完备域 $\to p-$adic Hodge 问题 → perfectoid / tilting → diamonds 与 Fargues–Fontaine 曲线；另一路从 Frobenius 与 δ 环进入 prismatic cohomology。

入口：[PA00 · 从 Frobenius 缺口进入 perfectoid 与棱柱](../research/PA00.md)。先手算等特征根塔；后续需非阿基米德几何、étale 上同调与混合特征工具。这些方向相互连接，但 diamonds、棱柱并非彼此的简单线性先修。来源：[Perfectoid Spaces](../SOURCES.md#perfectoid)、[Prisms](../SOURCES.md#prisms)。

<a id="r10"></a>
## R10 · Condensed / Solid

拓扑交换群 → profinite 测试空间 → 层式编码 → condensed groups → solid modules → 解析与 p 进应用。

入口：[CS00 · 把拓扑对象编码成凝聚层](../research/CS00.md)。具体计算连续 $\mathbb Z_{p}\to \mathbb F_{p}$ 的函数如何通过有限精度因子化。进入 solid 需补凝聚交换群的代数与适当完备张量，不把所有凝聚模都称为 solid。来源：[Condensed Mathematics](../SOURCES.md#condensed)。

<a id="r11"></a>
## R11 · K-Theory / THH / TC

投射模 $\to K_{0} \to$ higher K-theory；Hochschild / cyclic 思想 → THH $\to TC \to$ 与 K 理论的 cyclotomic trace 及算术比较。

入口：[KT00 · 从投射模计数到 K 理论与 THH](../research/KT00.md)。先计算 $K_{0}(k\times k)$，再追问形式差忘掉哪些同伦信息。后续需谱、循环作用和 cyclotomic 结构。来源：[Weibel K-book](../SOURCES.md#kbook)、[BMS](../SOURCES.md#thh)。

<a id="r12"></a>
## R12 · Motivic Homotopy

概形 → Nisnevich 下降与 $A^{1}$ 不变性 → motivic spaces → motivic spectra → 广义上同调与六函子。

从 [S100](../stages/S100.md)、[S110](../stages/S110.md)、[HA00](../research/HA00.md) 汇合。经典问题是哪些不变量在乘 $A^{1}$ 后不改变；真正进入需补模型化同伦与拓扑选择，不能把 Zariski 层直接称为 motivic space。本路线尚无独立 Stage。

<a id="r13"></a>
## R13 · Tensor Triangular Geometry

导出范畴 → 张量三角范畴 → thick tensor ideals → Balmer spectrum → 支撑与重建。

从 [S070](../stages/S070.md)、[S096](../stages/S096.md)、[KT00](../research/KT00.md) 问：能否不直接看环，只用完美复形及张量恢复素谱？还需厚子范畴、张量理想和支撑理论。本路线尚无独立 Stage。

<a id="r14"></a>
## R14 · Geometric / Local Langlands

表示与 Hecke 思想 + 层与模空间 + 导出范畴 + 局部域与 p 进几何，汇入不同版本的 Langlands 问题。

从 [CR00](../research/CR00.md)、[PA00](../research/PA00.md)、[S108](../stages/S108.md) 的多个接口进入；这些入口只是起点，还需大量表示与几何先修。来源：[Fargues–Scholze](../SOURCES.md#langlands)。本路线不是课程唯一终点，也尚无独立 Stage。
