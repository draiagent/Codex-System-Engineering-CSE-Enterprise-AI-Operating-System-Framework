---
name: department-workflow-builder
description: 將企業部門的一項重複工作，拆解成可執行、可驗收、可版本控制的 Codex Skill。當使用者要求把 SOP、工作方法、部門流程或重複任務封裝成 Skill 時使用。
---

# Department Workflow Builder

## Purpose

把模糊的部門工作，轉為具有明確輸入、輸出、步驟、品質閘門與人工核准點的 Skill 規格。

## Use When

- 使用者說「把這個流程做成 Skill」
- 某項工作已重複兩次以上
- 部門 SOP 需要移植到 Codex
- 新人需要依文件完成工作
- 輸出可以被明確驗收

## Do Not Use When

- 工作只會執行一次
- 工作高度依賴未公開的人際或政治判斷
- 沒有明確輸入
- 沒有可驗證輸出
- 涉及不可逆高風險決策且沒有人工核准

## Required Inputs

至少取得：

1. 部門
2. 任務名稱
3. 任務目的
4. 觸發時機
5. 使用者或客戶
6. 必要輸入
7. 預期輸出
8. 現行 SOP
9. 成功標準
10. 禁止事項
11. 審核者
12. 常見失敗

資訊不足時，先列出缺口，不得自行創造關鍵商業規則。

## Outputs

產生：

```text
skills/<skill-name>/
└── SKILL.md
```

必要時可加入：

```text
references/
examples/
scripts/
assets/
```

只有當額外檔案能提升可靠性時才新增。

## Workflow

### Step 1 — Define the Job

用一句話描述：

```text
當 <觸發條件> 發生時，
根據 <輸入>，
產生 <輸出>，
供 <使用者> 執行 <決策或行動>。
```

### Step 2 — Determine Boundaries

列出：

- 包含範圍
- 不包含範圍
- 前置條件
- 停止條件
- 人工核准點

### Step 3 — Normalize Inputs

把輸入分為：

| 類型 | 說明 |
|---|---|
| Required | 缺少就不能執行 |
| Optional | 可提高品質 |
| Derived | 可由既有資料推導 |
| Forbidden | 不應提供或處理 |

### Step 4 — Define Output Contract

輸出契約至少包含：

- 格式
- 欄位
- 長度
- 語言
- 引用要求
- 不確定性標記
- 審核狀態

### Step 5 — Write the Procedure

每一步都用：

```text
Input → Action → Output → Check
```

避免使用「適當處理」「視情況優化」等不可驗收描述。

### Step 6 — Add Quality Gates

至少包含：

- 完整性
- 正確性
- 一致性
- 法規／品牌
- 來源
- 敏感資料
- 人工核准

### Step 7 — Add Failure Handling

定義：

- 缺少資料
- 來源衝突
- 格式錯誤
- 高風險內容
- 無法驗證
- 工具不可用

### Step 8 — Add Examples

至少建立：

1. 正常案例
2. 資訊不足案例
3. 拒絕或轉人工案例

### Step 9 — Evaluate

使用 `templates/skill-evaluation.md` 評估，未達標不得宣稱完成。

## Quality Checks

- [ ] Skill 只負責一種工作
- [ ] description 可被自然語句觸發
- [ ] 輸入有 Required／Optional 區分
- [ ] 輸出有固定契約
- [ ] 每一步可驗收
- [ ] 有至少一個人工核准點或明確說明不需要
- [ ] 有不應使用情境
- [ ] 有失敗處理
- [ ] 沒有機密資訊
- [ ] 沒有虛構的系統能力

## Failure Handling

若資料不足，輸出：

```markdown
## 無法完成封裝

### 缺少資訊
- ...

### 暫時假設
- ...

### 建議下一步
- ...
```

不得以看似完整的文件掩蓋資訊缺口。

## Example Trigger Phrases

- 「把業務提案 SOP 做成 Codex Skill」
- 「將每週社群內容流程封裝」
- 「把研發文獻整理變成可重複技能」
