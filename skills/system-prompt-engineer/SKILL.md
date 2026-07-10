---
name: system-prompt-engineer
description: 設計、重構或稽核 Codex 的 AGENTS.md、角色規格、工作規則與提示詞架構。當使用者要求建立系統提示詞、持續性指令、Prompt Architecture 或將 Claude 規則移植到 Codex 時使用。
---

# System Prompt Engineer

## Purpose

建立精簡、分層、無衝突且可執行的 Codex 指令架構，避免把所有資訊塞進單一超長提示詞。

## Use When

- 新建或重構 `AGENTS.md`
- 將 `CLAUDE.md` 移植到 Codex
- 建立企業級 Prompt Architecture
- 排除指令衝突、重複或範圍污染
- 將人格、規則、SOP、任務拆分到正確層級

## Do Not Use When

- 只需改寫一段普通文案
- 需求只涉及單次任務
- 使用者要求的是程式功能而非指令架構
- 未取得既有規則卻要求直接覆寫

## Inputs

- 現有 `AGENTS.md` 或提示詞
- 儲存庫結構
- 使用情境
- 穩定規則
- 部門差異
- 禁止事項
- 驗證方式
- 目標語言

## Output Architecture

優先拆為：

```text
AGENTS.md                 # 跨專案穩定規則
context/*.md              # 企業或領域脈絡
skills/*/SKILL.md         # 重複工作
agents/*.md               # 專責角色
workflows/*.md            # 多步驟交接
task prompt               # 本次任務
```

## Workflow

### 1. Inventory

把原始內容分類：

| 類別 | 放置位置 |
|---|---|
| 永久行為規則 | `AGENTS.md` |
| 部門或企業事實 | `context/` |
| 可重複 SOP | `skills/` |
| 專責角色 | `agents/` |
| 跨角色順序 | `workflows/` |
| 單次目標 | 任務 Prompt |
| 歷史決策 | `memory/decisions/` |

### 2. Remove Prompt Smells

移除或改寫：

- 同義重複
- 互相矛盾
- 無法驗證的形容詞
- 假裝擁有不存在的工具
- 強迫輸出冗長思考過程
- 把短期資訊寫成永久規則
- 把所有任務都要求「最高規格」
- 沒有停止條件的自主執行

### 3. Establish Precedence

明確定義：

- 指令優先級
- 目錄作用域
- 例外處理
- 資訊不足處理
- 高風險人工核准

### 4. Convert to Operational Language

將：

```text
請專業處理
```

改為：

```text
輸出必須包含：目的、輸入、分析、風險、建議與下一步。
所有外部事實標示來源與日期。
```

### 5. Minimize Root Context

根目錄 `AGENTS.md` 只保留跨多數任務有效的規則。

細節下沉：

- 部門規則下沉到部門目錄
- Skill 規則放在 `SKILL.md`
- 專案特定規則放在較近的 `AGENTS.md`

### 6. Validate

檢查：

- 是否有衝突
- 是否有不可執行指令
- 是否過度限制合理解法
- 是否把事實與規則混在一起
- 是否有敏感資料
- 是否定義完成標準

## Output Format

```markdown
# Prompt Architecture Review

## Current Problems
...

## Proposed Structure
...

## Root AGENTS.md
...

## Files to Split Out
...

## Migration Plan
...

## Validation Checklist
...
```

## Quality Checks

- [ ] 永久規則與單次任務分離
- [ ] 角色與流程分離
- [ ] 沒有工具能力幻覺
- [ ] 沒有要求暴露隱藏推理
- [ ] 有資訊不足處理
- [ ] 有高風險限制
- [ ] 有可驗收完成條件
