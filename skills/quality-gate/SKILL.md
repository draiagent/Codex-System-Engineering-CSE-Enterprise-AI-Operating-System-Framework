---
name: quality-gate
description: 對企業 AI 產出進行結構化驗收，檢查完整性、事實、來源、品牌、法規、資安與可執行性。當文件、提案、Skill、Workflow 或對外內容準備進入下一階段前使用。
---

# Quality Gate

## Purpose

把「看起來不錯」改成可重複的品質判定。

## Inputs

- 待審輸出
- 原始需求
- 適用規則
- 風險等級
- 來源資料
- 驗收者

## Gate Levels

| 等級 | 用途 | 結果 |
|---|---|---|
| G0 Draft | 初稿自檢 | 可繼續修改 |
| G1 Functional | 結構與功能 | 可交內部審閱 |
| G2 Evidence | 事實與來源 | 可進專業審核 |
| G3 Compliance | 品牌、法規、資安 | 可送核准 |
| G4 Approval | 人類負責人核准 | 可發布或執行 |

## Review Dimensions

### Completeness

- 是否覆蓋需求
- 是否缺少必要欄位
- 是否有明確下一步

### Correctness

- 數字是否一致
- 邏輯是否成立
- 是否混淆事實與推論
- 是否有過期資訊

### Evidence

- 重要主張是否有來源
- 引用是否真的支持主張
- 是否標示日期
- 是否超出來源可支持範圍

### Brand and Communication

- 語調是否符合品牌
- 是否誇大
- 是否對受眾可理解
- 是否使用不必要術語

### Risk and Compliance

- 是否包含敏感資料
- 是否有未經核准宣稱
- 是否涉及醫療、法律、財務或人事風險
- 是否有人工核准點

### Operability

- 接手者是否知道怎麼做
- 輸入與輸出是否明確
- 是否能判定完成
- 失敗時是否知道如何處理

## Result Format

```markdown
# Quality Gate Report

## Decision
PASS / PASS WITH CONDITIONS / FAIL

## Critical Defects
1. ...

## Major Defects
1. ...

## Minor Defects
1. ...

## Required Corrections
1. ...

## Human Approval Required
- Yes / No
- Approver:
- Reason:
```

## Decision Rules

### PASS

- 無 Critical
- 無未處理 Major
- 必要人工核准已完成

### PASS WITH CONDITIONS

- 無 Critical
- Major 有明確 Owner 與期限
- 不影響目前階段用途

### FAIL

- 存在重大事實錯誤
- 缺少必要來源
- 有未處理資安或法規風險
- 輸出不符合原始目的
