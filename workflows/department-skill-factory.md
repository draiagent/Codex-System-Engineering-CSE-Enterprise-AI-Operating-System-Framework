# Workflow: Department Skill Factory

## Objective

把一項部門工作從「口傳經驗」轉為「可重用 Codex Skill」。

## Stages

```text
Candidate Selection
→ Workflow Interview
→ First Manual Run
→ SOP Extraction
→ Skill Draft
→ Test Cases
→ Pilot
→ Review
→ Release
→ Metrics
```

## 1. Candidate Selection

評估：

- 頻率
- 時間成本
- 可標準化程度
- 錯誤成本
- 資料可取得性
- 是否有 Owner

## 2. Workflow Interview

訪談實際執行者，不只訪談主管。

蒐集：

- 真正步驟
- 例外情境
- 判斷依據
- 常見錯誤
- 隱性知識
- 審核方式

## 3. First Manual Run

先由 Codex 在明確指令下完成一次，不急著封裝。

目的：

- 找出必要上下文
- 找出工具限制
- 找出輸入缺口
- 建立基準輸出

## 4. SOP Extraction

將成功過程整理成：

```text
Trigger
Inputs
Steps
Checks
Output
Failure handling
Approval
```

## 5. Skill Draft

使用 `department-workflow-builder`。

## 6. Test Cases

至少三組：

- 正常
- 缺資料
- 不應執行

## 7. Pilot

由真實使用者執行 3–5 次，記錄：

- 完成時間
- 返工
- 錯誤
- 主觀負擔
- 人工修正量

## 8. Release Criteria

- 首次通過率達標
- 無 Critical 缺陷
- Owner 核准
- 文件完整
- 資料與權限合規

## 9. Metrics

- Adoption
- Cycle time
- Rework rate
- Error rate
- Human review time
- User satisfaction
