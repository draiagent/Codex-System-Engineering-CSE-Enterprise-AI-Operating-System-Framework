# Workflow: Enterprise AI Delivery

## Purpose

從需求到可核准交付物的標準流程。

## Trigger

- 新的企業 AI 任務
- 新文件或素材
- 新分析或提案
- 新 Skill 或 Workflow

## Flow

```text
1. Intake
2. Risk Classification
3. Brief Gate
4. Research
5. Evidence Gate
6. Strategy
7. Strategy Gate
8. Build
9. Quality Review
10. Human Approval
11. Release
12. Retrospective
```

## Detailed Steps

| Step | Owner | Input | Output | Gate |
|---|---|---|---|---|
| Intake | Orchestrator | User request | Task brief | 完整性 |
| Risk | Reviewer | Task brief | Risk level | 是否需專業審核 |
| Research | Researcher | Questions | Evidence table | 來源品質 |
| Strategy | Strategist | Brief + evidence | Direction | 決策清晰 |
| Build | Builder | Approved strategy | Deliverable | 輸出契約 |
| Review | Reviewer | Deliverable | Gate report | 缺陷等級 |
| Approval | Human owner | Final package | Approval record | 責任確認 |
| Release | Owner | Approved output | Published result | 版本紀錄 |
| Retrospective | Team | Metrics + defects | Lesson | 可重用改善 |

## Failure Handling

### 資訊不足

回到 Intake，列出缺少欄位。

### 來源衝突

Researcher 建立衝突表，Strategist 不得直接忽略。

### 重大缺陷

回到 Build；未關閉前不得送核准。

### 法規或資安疑慮

停止流程，交專業人員。

## Stop Conditions

- 使用者取消
- 缺少不可替代輸入
- 權限不足
- 風險超出授權
- 無法驗證關鍵事實
