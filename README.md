# Jinni Vault

這是 Jinni 的個人知識庫,供 AI Agent(Jentor)讀取使用。

---

## 資料夾結構與檔案索引

```
/
  README.md              ← 你正在讀的這份:Vault 索引地圖
  agent-persona.md       ← Jentor 的人格設定(Identity / Soul / Persona 三層)與協作方式
  memory-summary.md      ← 長期記憶摘要:Sticky、重要決策、當前焦點

  /identity
    decision-style.md    ← Jinni 的決策模式、卡點、品質標準,與 Jentor 的回應合約
    voice-and-tone.md    ← 對外文字規則:語感、六條規則、支語禁用表(對外文稿必讀)

  /context
    ilio-overview.md     ← 伊利歐共學團:定位、11 位學生、5 人團隊、課程架構、下半年方向
    ark-overview.md      ← 職人方舟工作坊:年 10 場三季制、行政系統、下半年方向
    foundation.md        ← 傳愛基金會關係與金流規則(收費文件動筆前必讀)

  /memory                ← 重要決策紀錄、會議結論 → 讀 INDEX.md
  /projects              ← 各項目的狀態(含碩士論文)→ 讀 INDEX.md(收官的搬 archive/)

  /sop
    after-action.md      ← 收官流程:寫 memory、更新文件、更新 summary
    git-workflow.md      ← Git 日常同步、換電腦、衝突救援
    vault-audit.md       ← 索引完整性檢查,每月跑一次
    vault-changelog.md   ← 核心檔案更新紀錄的歸檔處
    vault-daily-usage.md ← Vault 日常使用手冊:操作流程、常用指令、維護節奏、異常排除

  /operations
    ilio-refund-policy.md ← 伊利歐共學團退費標準原文(涉及金流,修改前讀 context/foundation.md)
  /people                ← 重要聯絡人背景,尚無檔案
  /skills                ← Jentor 的技能檔案,尚無檔案
```

會堆疊的資料夾(memory/、projects/)各自維護一份 `INDEX.md` 放完整清單;這份 README 只留上面的一行入口。進資料夾前先讀它的 `INDEX.md`。

## 涵蓋範圍

目前涵蓋:伊利歐共學團、職人方舟工作坊(皆屬中華傳愛教育基金會)、碩士論文(耶拿教育研究)。
暫不涵蓋:APLA 協會籌備、台北個人教學品牌(之後視需要加入)。

## Agent 閱讀順序

1. 讀這份 README(了解整體結構)
2. 讀 `agent-persona.md`(了解自己的角色與協作方式)
3. 讀 `memory-summary.md`(掌握近期重要事項)
4. 依任務需要,讀對應資料夾的內容

## 命名規則

- 檔名即索引:用描述性檔名,避免泛稱(`ilio-curriculum-map.md`,不要 `doc1.md`)
- 同分類用 `主題-子項` 格式,主題在前(`ark-registration-sop.md`、`ark-refund-policy.md`)
- memory/ 檔名:`YYYY-MM-DD_主題.md` · projects/ 資料夾:`YYYY-MM-主題/`

## 強制規則(不是建議)

### #1 — 索引同步
- 新增 / 刪除檔案 → 當次 response 內改對應資料夾的 `INDEX.md`(有 INDEX 的資料夾)
- 新增 / 刪除「資料夾」或其他結構性變動 → 改這份 README(資料夾描述 + 底部更新 log)

### #2 — 對外文稿規則
只要這段文字會被 Jinni 以外的人看到(招生文案、家長通知、公開簡報、媒體稿、社群貼文等),撰寫前必須讀 `identity/voice-and-tone.md`。不確定時視為對外。

兩條都是完成任務的必要條件。第二道安全網:收官檢查(after-action)時再確認一次。

## 維護原則

- 一個事實只寫在一個地方(Single Source of Truth)
- 建新檔案前先搜尋有沒有現有的
- 每份文件開頭標注最後更新日期
- 敏感資訊(API key、密碼、學生個資)不進這個 repo

---

*最後更新:2026/07/06(sop/ 新增 vault-daily-usage.md,更新資料夾索引)*
*前次更新:2026/07/06(operations/ 新增 ilio-refund-policy.md,更新資料夾索引)*

*更新 log 規則:只留最新兩條。新增一條時,把被擠掉的那條搬進 `sop/vault-changelog.md`。*
