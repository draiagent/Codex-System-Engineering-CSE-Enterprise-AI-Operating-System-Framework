# Department Map

## 1. 部門與 AI 能力對照

| 部門 | 高頻工作 | 建議 Skills | 建議 Agents | 主要風險 |
|---|---|---|---|---|
| 經營策略 | 市場分析、決策摘要 | strategy-brief, scenario-analysis | strategist, reviewer | 錯誤假設 |
| 行銷 | 文案、活動、內容再製 | campaign-brief, social-caption | marketer, reviewer | 品牌與法規 |
| 業務 | 提案、跟進、CRM 摘要 | proposal-draft, account-summary | sales-analyst | 客戶機密 |
| 研發 | 文獻、規格、競品 | evidence-table, product-concept | researcher | 引用失真 |
| 品保 | 稽核、CAPA、SOP | audit-summary, capa-draft | quality-reviewer | 放行責任 |
| 財務 | 預算、差異、成本 | variance-analysis, cost-model | finance-analyst | 數值錯誤 |
| 人資 | JD、面試、訓練 | job-description, interview-kit | hr-specialist | 歧視與個資 |
| 法務 | 條款比較、風險摘要 | clause-comparison | legal-reviewer | 非律師意見 |
| 客服 | FAQ、回覆草稿 | support-response, issue-triage | support-agent | 個資與承諾 |
| 資訊 | 開發、測試、文件 | code-change, code-review | builder, reviewer | 資安與相容性 |

## 2. Skill 優先級評估

使用下列公式判斷是否值得建立 Skill：

```text
優先分數 =
頻率 × 時間成本 × 標準化程度 × 風險可控性
```

每項以 1–5 分計。

優先建立：

- 每週至少執行一次
- 輸入格式大致固定
- 輸出可被明確驗收
- 失敗不會直接造成不可逆損失
- 有現成優良案例可作為基準

暫緩建立：

- 一年一次
- 高度依賴未明說的政治判斷
- 沒有可驗證的完成標準
- 涉及高風險決策且無人工審核
