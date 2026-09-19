# Modern Algebra Pathway

以代数内容、具体模型和不断生长的数学思想为中心的 AI 可教学教材。保留 **S000–S111 共 112 个经典 Stage**，另有 **7 个有具体计算的研究入口**。Stage 是唯一正式教学与持久位置单位。

## 四条学习线索

| 入口 | 回答的问题 |
| --- | --- |
| [Core](maps/CORE.md) / [Focus](maps/FOCUS.md) 中的 Stage | 现在学什么：语境、预备知识、例子、定义、例解、证明与练习 |
| [ACTIONS](maps/ACTIONS.md) | 怎样做代数：生成、取商、找映射、换底、局部化、追踪正合 |
| [THEMES](maps/THEMES.md) | 同一个思想怎样跨越不同对象并不断深化 |
| [RESEARCH](maps/RESEARCH.md) | 经典问题通向哪些现代研究语言，还需要补什么 |

从 [S000 · 数学句子到底在说什么](stages/S000.md) 开始；已有基础时按实际先修选择位置。[Core 路线](maps/CORE.md) 给出先修顺序，编号不要求机械递增。Focus 分为表示与非交换 / Lie、域与算术、交换与计算、同调与导出、代数几何五条路线。

## 恢复学习只需少量读取

1. 读取 [AGENTS.md](AGENTS.md)。
2. 新会话恢复时读取 Library `/代数/progress.json` 一次。
3. 用 [course.json](course.json) 和 [index/stages.json](index/stages.json) 定位，只读取当前 Stage。
4. “继续”延续当前数学脉络。同一 Stage 内答题、提示、证明与纠错都不更新进度。

只有实际切换 Stage，或明确要求保存位置，才写进度。进度仅含课程、当前 Stage、已完成 Stage，可选路线；**实际 progress 不放在仓库**。格式见 [进度协议](PROGRESS_PROTOCOL.md)。

[Project 指令](PROJECT_INSTRUCTIONS.md) 可直接复制到 ChatGPT Project。[教学协议](TEACHING_PROTOCOL.md) 说明怎样用正文讲授，[进度协议](PROGRESS_PROTOCOL.md) 说明学习位置的保存规则。无法访问 Library 时，AI 应明确说明。

## 正文与研究入口

每篇提供进入说明、最低先修与符号、简单模型、结构例、失败例、完整 worked example、定理或证明机制及练习。基础论证直接展开；借用的高级定理明确标注。旧教师材料中的数学计算与条件辨析已迁入公开正文，练习不再绑定评分或提示历史。

第一批研究入口：[形变 DD00](research/DD00.md)、[高阶代数 HA00](research/HA00.md)、[导出交集 DA00](research/DA00.md)、[范畴化 CR00](research/CR00.md)、[Perfectoid / Prismatic PA00](research/PA00.md)、[Condensed / Solid CS00](research/CS00.md)、[K 理论 / THH KT00](research/KT00.md)。这些是有边界的进入模型，不是整个研究领域的缩写教材。

来源与使用范围见 [SOURCES](SOURCES.md)。
