# AGENTS.md — Skill Authoring Rules

本目錄內所有 Skill 必須符合以下要求。

## 1. Scope

- 一個 Skill 只處理一種工作。
- Skill 名稱使用小寫 kebab-case。
- 目錄名稱與 front matter 的 `name` 一致。
- description 必須同時說明「做什麼」與「何時使用」。

## 2. Required Sections

每份 `SKILL.md` 至少包含：

1. Purpose
2. Use When
3. Do Not Use When
4. Inputs
5. Outputs
6. Workflow
7. Quality Checks
8. Failure Handling
9. Examples

## 3. Reliability

- 能用明確檢查表，就不要只寫抽象原則。
- 能提供範例輸入輸出，就不要要求模型自行猜測。
- 外部資料必須標明來源與日期。
- 不得把高風險專業判斷完全交給 Skill。
- 有人工核准點時，必須明確寫出。

## 4. Evaluation

新增或修改 Skill 時，至少準備：

- 1 個正常案例
- 1 個資訊不足案例
- 1 個不應使用案例
- 預期輸出欄位
- 失敗條件
