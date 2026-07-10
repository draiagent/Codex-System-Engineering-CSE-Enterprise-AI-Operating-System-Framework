# Enterprise Codex AI Operating System

> 將「Context → Memory → Skills → Agents」四層架構，移植為可放入 GitHub、可由 Codex 執行、可持續治理的企業 AI 作業系統。

## 1. 專案定位

本儲存庫不是「提示詞收藏」，而是企業可版本控制的 AI 工作方法論：

```text
企業規範 Context
      ↓
企業知識 Memory
      ↓
可重用技能 Skills
      ↓
專責代理 Agents
      ↓
跨部門工作流 Workflows
      ↓
品質、稽核與治理 Governance
```

適用情境：

- 建立企業各部門的 Codex 工作標準
- 將重複工作封裝為 Skill
- 將多人協作流程拆解為專責 Agent
- 將 SOP、知識、審核規則納入 Git 版本控制
- 建立可追蹤、可測試、可回滾的 AI 工作流程

## 2. Codex 版與 Claude 版的關鍵差異

| 原始概念 | Codex 建議實作 | 說明 |
|---|---|---|
| `CLAUDE.md` | `AGENTS.md` | Codex 的持續性專案指令 |
| `memory/*.md` | `memory/` + 明確來源與更新規則 | 不把聊天內容直接當成可信記憶 |
| `skills/*/SKILL.md` | `skills/<skill-name>/SKILL.md` | 一個 Skill 聚焦一項可重複工作 |
| `agents/*.md` | `agents/*.md` + orchestrator workflow | 角色、輸入、輸出、禁止事項分離 |
| Slash command | 明確任務指令或 Skill 觸發語句 | 避免依賴未定義的指令語法 |
| Pipeline | `workflows/*.md` | 定義交接、品質閘門、停止條件 |

## 3. 儲存庫結構

```text
.
├── AGENTS.md
├── README.md
├── context/
│   ├── enterprise-context.md
│   └── department-map.md
├── memory/
│   ├── README.md
│   ├── decisions/
│   │   └── decision-log-template.md
│   └── lessons/
│       └── lesson-template.md
├── skills/
│   ├── AGENTS.md
│   ├── department-workflow-builder/
│   │   └── SKILL.md
│   ├── system-prompt-engineer/
│   │   └── SKILL.md
│   ├── multi-agent-orchestrator/
│   │   └── SKILL.md
│   └── quality-gate/
│       └── SKILL.md
├── agents/
│   ├── strategist.md
│   ├── researcher.md
│   ├── builder.md
│   └── reviewer.md
├── workflows/
│   ├── enterprise-ai-delivery.md
│   └── department-skill-factory.md
├── governance/
│   ├── ai-governance.md
│   ├── risk-classification.md
│   └── definition-of-done.md
├── templates/
│   ├── task-brief.md
│   ├── department-profile.md
│   └── skill-evaluation.md
└── .github/
    ├── pull_request_template.md
    └── ISSUE_TEMPLATE/
        ├── new-skill.md
        └── improve-workflow.md
```

## 4. 快速開始

### 步驟一：填寫企業脈絡

先修改：

- `context/enterprise-context.md`
- `context/department-map.md`

只保留對多數任務長期有效的資訊。不要把一次性專案細節塞進根目錄 `AGENTS.md`。

### 步驟二：建立第一個部門 Skill

複製：

```text
skills/department-workflow-builder/SKILL.md
```

並以一個具體、高頻、可驗證的工作為對象，例如：

- 行銷部：短影音腳本生成
- 業務部：客戶提案初稿
- 研發部：文獻證據表
- 品保部：稽核缺失整理
- 人資部：職缺說明與面試題
- 財務部：月度差異分析

### 步驟三：先建立單一工作流，再建立多代理流程

不要一開始就建立十個 Agent。建議順序：

```text
單一任務成功
→ 寫成 SOP
→ 封裝為 Skill
→ 加入測試案例
→ 再拆為多 Agent
→ 最後才自動化
```

### 步驟四：以 GitHub PR 管理變更

所有下列變更都應透過 Pull Request：

- 修改企業規則
- 新增或變更 Skill
- 調整 Agent 權限
- 修改品質閘門
- 新增外部資料來源
- 改變高風險決策流程

## 5. 企業導入原則

### 原則 A：規則與任務分離

- `AGENTS.md`：穩定、跨任務規則
- `context/`：企業與部門脈絡
- `skills/`：重複工作方法
- `workflows/`：跨角色流程
- 任務 Prompt：本次目標、輸入與限制

### 原則 B：記憶必須可追溯

每一筆正式知識至少標示：

- 來源
- 建立日期
- 更新日期
- 負責人
- 適用範圍
- 信心水準
- 淘汰條件

### 原則 C：高風險任務必須有人類核准

下列輸出不得直接自動發布或執行：

- 法律意見
- 醫療或健康決策
- 財務承諾
- 人事處分
- 對外合約
- 法規聲明
- 大額採購
- 生產與品質放行

### 原則 D：每個 Skill 只處理一種工作

不建立「萬能行銷 Skill」；改為：

- `campaign-brief`
- `short-video-script`
- `seo-article-outline`
- `social-caption`
- `creative-review`

## 6. 成熟度模型

| 等級 | 狀態 | 企業表現 |
|---|---|---|
| L1 Prompt | 個人提示詞 | 高度依賴個人經驗 |
| L2 Context | 共用規則 | 輸出風格較一致 |
| L3 Skill | SOP 封裝 | 工作可重複、可交接 |
| L4 Agent | 專責角色 | 可拆工、可平行處理 |
| L5 Workflow | 跨部門串接 | 有交接與品質閘門 |
| L6 Governance | 可稽核治理 | 有權限、風險與責任 |
| L7 Automation | 系統整合 | 可定時或事件驅動 |
| L8 Intelligence | 決策回饋 | 用 KPI 持續改善流程 |

## 7. 建議第一階段範圍

第一階段只建立 3 個 Skill：

1. 一個高頻內容工作
2. 一個分析工作
3. 一個品質審核工作

成功標準：

- 任務時間下降
- 返工次數下降
- 輸出一致性提高
- 新人可依文件完成工作
- 失敗時能指出是哪一個步驟出錯

## 8. License

可依企業需求選擇 MIT、Apache-2.0 或內部專有授權。若包含企業機密，請勿建立公開儲存庫。
