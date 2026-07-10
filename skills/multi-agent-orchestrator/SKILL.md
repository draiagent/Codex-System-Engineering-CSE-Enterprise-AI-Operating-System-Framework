---
name: multi-agent-orchestrator
description: 將複雜任務拆成多個專責 Agent 的工作包，設計平行處理、交接、整合與品質閘門。當任務跨研究、策略、製作與審核，且可拆為相對獨立工作時使用。
---

# Multi-Agent Orchestrator

## Purpose

用最少必要的 Agent 完成複雜任務，避免角色重疊、無效討論與責任模糊。

## Use When

- 任務包含研究、策略、製作與審核
- 子任務可以平行進行
- 需要不同專業觀點
- 需要獨立 Reviewer
- 交付物有明確整合規則

## Do Not Use When

- 單一 Agent 可在短流程內完成
- 子任務高度相依，平行化反而增加成本
- 只是為了「看起來進階」
- 沒有清楚的總交付物

## Core Principle

```text
One agent = one responsibility
One handoff = one explicit contract
One workflow = one accountable owner
```

## Inputs

- 最終交付物
- 截止條件
- 可用來源
- 子任務
- 風險
- 核准者
- 不可平行項目

## Standard Roles

| Agent | 責任 | 不負責 |
|---|---|---|
| Strategist | 定義問題與判斷框架 | 不撰寫最終素材 |
| Researcher | 蒐集與驗證證據 | 不做無來源決策 |
| Builder | 依規格產出交付物 | 不自行改變策略 |
| Reviewer | 找錯、驗收、標示風險 | 不靜默重寫需求 |
| Orchestrator | 分工、交接、整合 | 不取代專業核准者 |

## Workflow

### 1. Decompose by Deliverable

不要按「人物」拆分，按「可驗收成果」拆分。

錯誤：

- Agent A 想想看
- Agent B 補充
- Agent C 再優化

正確：

- Researcher：證據表
- Strategist：決策框架
- Builder：正式草案
- Reviewer：缺陷報告

### 2. Determine Parallelism

可平行：

- 多市場資料蒐集
- 多競品分析
- 不同素材版本
- 獨立品質審核

不可平行：

- 尚未確定策略就製作正式素材
- 尚未確認輸入就做最終計算
- 同一檔案多人同時改寫且無合併規則

### 3. Define Handoff Contract

每次交接必須包含：

```markdown
## Handoff
- From:
- To:
- Deliverable:
- Required fields:
- Evidence:
- Open questions:
- Risks:
- Acceptance criteria:
```

### 4. Add Quality Gates

推薦流程：

```text
Brief Gate
→ Evidence Gate
→ Strategy Gate
→ Build Gate
→ Review Gate
→ Human Approval
```

### 5. Consolidate

整合時：

- 不以多數決取代證據
- 衝突必須列出
- 不確定性不得被刪除
- Reviewer 的重大缺陷未關閉前不得標記完成

## Outputs

- Agent roster
- Work breakdown
- Dependency map
- Parallel plan
- Handoff contracts
- Quality gates
- Final integration rule

## Quality Checks

- [ ] 每個 Agent 責任不重疊
- [ ] 每個子任務有交付物
- [ ] 每次交接有驗收條件
- [ ] 已標明可平行與不可平行工作
- [ ] 有獨立 Reviewer
- [ ] 有最終 Owner
- [ ] 高風險決策有人類核准
