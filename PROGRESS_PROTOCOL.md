# 进度协议：Library 中的 progress.json 才是学习状态

## 唯一主记录

`progress.json` 不属于 GitHub 仓库。它单独保存在 ChatGPT Library，并以 **Library 中最新版本**为唯一主记录。

GitHub 中的 `curriculum.json` 和 `INDEX.json` 定义课程 ID、版本、Stage/Goal/Task 与先修；`progress.json` 记录实际学习证据和游标。

每次开始前至少核对：

- `curriculum_id`；
- `curriculum_version`；
- 若记录中有 `curriculum_sha256`，应与当前 `curriculum.json` 一致；
- `revision`；
- 当前 `cursor`；
- 当前 Goal 的状态与相关证据。

课程版本不一致时先处理迁移，不要静默继续。

## 状态

每个能力维度使用：

- `unassessed`：未评估；
- `assisted`：已有练习，但没有满足独立条件的正确证据；
- `independent`：独立正确；
- `retained`：隔一段时间后在实质不同的新变式中仍独立正确；
- `needs_review`：已有能力在后续独立检验中出现问题。

`assisted` 不是“半掌握”。正确与否必须由事件本身记录。

## 什么才算独立证据

升级为 `independent` 至少要求：

- `mode = closed_book`；
- `hint_level = 0`；
- `solution_seen = false`；
- 没有先前完整解答泄露同一道题；
- 本次对应维度被实际核验为 `correct`。

`unverified` 或 `not_checked` 不升级掌握状态。

`retained` 还要求：

- 距离先前独立证据至少 2 天；
- 使用不同 task/variant；
- 题干实质不同，不是只换数字、ID 或措辞；
- 再次无提示、闭卷、独立正确。

后续独立失败不删除旧证据，但相应维度进入 `needs_review`，之后重新建立独立与保持证据。

## Goal 与 Stage 通过

课程默认按六个维度记录：`explain`、`compute`、`construct`、`prove`、`refute`、`transfer`。

一个 Goal 是否通过，应按 `curriculum.json` 中该 Goal 的 `required_dimensions` 判断，而不是看“做了几道题”。

Stage 的所有 Goal 都达到 `independent` 或 `retained` 才视为通过。讲解结束、Level 到 5、用户说“懂了”、看过答案、AI/CAS 算出结果，都不能代替证据。

## attempt 事件

每次真正练习后追加一条事件。沿用当前 `progress.json` 的既有结构，不重写历史事件。典型字段包括：

```json
{
  "id": "unique-attempt-id",
  "type": "attempt",
  "at": "ACTUAL_OFFSET_AWARE_ISO_TIME",
  "goal_id": "S000.G1",
  "task_id": "S000.E1",
  "assessment_type": "diagnostic",
  "mode": "closed_book",
  "hint_level": 0,
  "solution_seen": false,
  "outcomes": {"explain": "correct"},
  "response_excerpt": "足以复核评分的真实作答摘要",
  "verified_by": "tutor_check",
  "verification_note": "为什么这个回答足以支持该维度的判断"
}
```

只在 `outcomes` 中写本次真正评估到的维度。值可为 `correct`、`partial`、`incorrect`、`unverified`。

`verified_by` 可沿用当前记录中的 `tutor_check`、`human_check`、`formal_check`、`not_checked`。可信核验必须写具体理由；模型没有真正运行形式化证明工具时，不得写 `formal_check`。

新变式使用唯一 ID，并把完整题干保存在事件中；不能只写“同类题”。

## 其他常用事件

沿用当前 `progress.json` 已有事件格式；需要时包括：

- `cursor`：更新精确续课位置；
- `session_start` / `session_end`：会话边界；
- `solution_view`：记录完整解答已经被看过；
- `misconception_add` / `misconception_resolve`：记录具体错误判断及后续修正；
- `preferences`：路线偏好；
- `void_attempt`：发现题目错误、评分错误或证据归错目标时作废旧 attempt，但不删除历史。

不要用 `void_attempt` 删除正常失败来美化记录。

## cursor 必须具体

游标至少保留：

- `stage_id`；
- `goal_id`；
- `level`（1–5）；
- `mode`（learning / diagnostic / review）；
- `pending_question`；
- `resume_note`；
- 若正在证明，`proof_checkpoint`。

`resume_note` 不写“继续代数”这种空描述，而应写到下一步动作，例如：“已证明生成，尚未证明线性无关；下一步检查零线性组合”。

游标变化不等于能力升级。

## 每次更新怎样做

1. 读取 Library 中最新 `progress.json`，记住当前 `revision`。
2. 根据本轮真实作答追加事件，重算受影响 Goal/Stage 状态和复习信息。
3. `revision` 增加 1，更新 `updated_at`。
4. 校验：课程 ID/版本、游标引用、Stage/Goal/Task ID、事件 ID 唯一性、时间顺序、独立/保持条件、状态推导是否一致。
5. **有 Library 写入能力**：替换/更新 Library 中同一个 `progress.json`，然后重新读取最新版本确认写入成功。
6. **没有写入能力**：提供完整的更新后 `progress.json`（优先）或清晰的待提交事件，并明确说“尚未保存”。

不要仅在聊天里说“记住了”然后声称进度已保存。

## 并发与冲突

更新前读取的 `revision` 是本次写入的基线。如果写回前 Library 中版本已经变化，不要覆盖：重新读取最新版本，按事件 ID、实际时间和内容合并，再重算状态。

任何修正都通过新增事件留下痕迹，不回写旧事件制造一个更漂亮的历史。

## 课程升级

`progress.json` 中保存的 `curriculum_sha256` 对应 GitHub 当前 `curriculum.json`。若课程文件升级导致版本或 SHA 改变，应显式迁移：

- 判断 Stage/Goal/Task ID 是否仍对应同一能力；
- 只有语义保持不变的证据才能保留；
- 不按 Stage 序号机械迁移；
- 无法确认的旧证据保留历史说明，但不要直接映射成新目标的掌握状态。

## 记录系统不负责的事

进度结构只能保证记录逻辑一致，不能证明数学答案本身正确，也不能证明学习者确实闭卷。教师仍需真实核验数学内容。
