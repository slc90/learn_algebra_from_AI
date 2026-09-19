# 学习位置

Library `/代数/progress.json` 是实际位置的唯一记录，不提交到 GitHub。

```json
{
  "course": "modern-algebra-pathway",
  "current_stage": "S000",
  "completed_stages": []
}
```

`current_stage` 必须存在于索引；`completed_stages` 是不重复的 Stage ID 列表。回访已完成 Stage 时，当前 Stage 可以同时出现在列表中。可选 `current_track` 必须是 course 中的路线名。完成只表示学习者明确结束该 Stage，不是能力评级。

新会话恢复、确实需要定位、用户要求查看进度时读取。同一会话位置已知时直接使用，不重复读取。

仅在实际切换 Stage 或用户明确要求保存位置时写入。同一 Stage 内的练习、提示、证明、讨论、“懂了”“继续”、解释深度变化，通常产生零次写入。切换不等于完成，浏览不等于完成，不自动把编号更小的 Stage 加入完成列表。

需要保存而无 Library 写入能力时，提供完整 JSON 并说“尚未保存到 Library”。不要每轮输出待保存状态。

如果现有 Library 记录仍是旧格式，先保留原记录，只提取明确的当前 Stage 和已完成 Stage，整理成上面的格式；不要根据旧评分推断完成。位置不明确时先与学习者核对。
