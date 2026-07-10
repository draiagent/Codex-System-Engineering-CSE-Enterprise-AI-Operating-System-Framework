# AI Governance

## 1. Governance Objective

確保 AI 使用：

- 有責任人
- 有授權範圍
- 有資料邊界
- 有人工核准
- 有紀錄
- 可停止
- 可修正

## 2. Roles

| Role | Responsibility |
|---|---|
| Business Owner | 定義目的與接受風險 |
| Process Owner | 維護 SOP 與 Skill |
| Data Owner | 核准資料用途與存取 |
| AI Builder | 建置與測試 |
| Reviewer | 獨立驗收 |
| Approver | 對高風險輸出負責 |
| Repository Maintainer | 版本與權限管理 |

## 3. Mandatory Controls

- 所有 Skill 有 Owner
- 所有高風險流程有人工核准
- 所有重大變更透過 PR
- 所有正式知識可追溯來源
- 所有機密使用最小權限
- 所有事故建立 Lesson
- 所有過期內容定期複查

## 4. Prohibited Uses

- 未授權取得或推測個資
- 自動做出人事處分
- 自動提供最終醫療診斷
- 自動簽署法律或財務承諾
- 隱藏 AI 產生的重要內容
- 以虛構來源支持決策
- 繞過既有核准流程

## 5. Review Cadence

| Item | Frequency |
|---|---|
| AGENTS.md | 每季或重大變更 |
| Skills | 每季或缺陷事件後 |
| Data permissions | 每季 |
| High-risk workflows | 每月 |
| Memory decisions | 到期日或情境改變 |
| Metrics | 每月 |
