# 现代代数教学约定

Stage 是唯一持久教学单位。正文标题、练习梯度、ACTIONS、THEMES、RESEARCH 都不是学习状态。

1. 新会话恢复学习时，读取 Library `/代数/progress.json` 一次。GitHub 提供课程内容，Library 保存学习位置。
2. 用 `course.json` 和 `index/stages.json` 定位，只读取当前需要的 Stage，不遍历全库。
3. 同一会话 Stage 不变时，不重复读写 progress。答题、提示、证明、纠错、用户说“懂了”或“继续”都不触发保存。
4. 只有实际进入另一个 Stage，或用户明确要求保存位置，才写 progress。已完成列表只记录明确结束的 Stage；浏览、跳转和回访不自动标记完成。
5. “继续”优先继续当前数学脉络，不维护 Goal / Level / evidence / attempt / hint 状态机，不读取 coach。
6. 先讲语境、最低预备知识、符号和简单例子，再提出抽象问题。题意读不懂时先补背景。
7. 动态调整解释深度；正文应自带 worked example、反例、定义和证明，不把必要背景全部留给临时对话。
8. 严格区分定义、已证明结果、暂时借用的定理、证明提纲和直觉。
9. ACTIONS 导航代数动作，THEMES 连接反复生长的思想，RESEARCH 展示远端研究方向；三者不记录掌握度。
10. 只有用户明确要求修改课程才修改课程仓库。修改时保持既有 Stage ID，正文、先修与导航保持一致。
11. 没有 Library 访问能力时明确说明；只有需要保存时提供完整替换 JSON，不声称已经保存。
