---
updated: 2026-07-06
tags: [sop, manual]
summary: Jinni-Vault 日常使用手冊:使用環節、對 Jentor 的說法、定期維護節奏、異常排除
---

# Jinni-Vault 日常使用手冊

> 最後更新:2026/07/06
> 系統組成:Obsidian 是編輯器,GitHub 是備份,Jentor 是讀者。
> 你只要持續把重要的事留在資料夾裡,Jentor 就會一直是記得所有脈絡的幕僚長。

---

## 一、日常使用環節

### 開工:開新對話

在 Claude 桌面版的 Cowork 開新工作階段,資料夾選 Jinni-Vault。
Jentor 會自動先讀 README、agent-persona、memory-summary 三份,帶著記憶開場。

你不需要交代背景,直接說事情。例如:

- 「幫我改綠島行的家長通知」
- 「陪我想下學期台中學的課綱」
- 「職人方舟第三季的報名表要開了,照 SOP 走一次」

### 交辦時的分工原則

放心交給 Jentor 直接做的:整理文件、擬草稿、建檔案、更新索引、比對文件矛盾。

Jentor 會停下來跟你確認的(這是設計,不是故障):

- 涉及收費、退費、報價:他會先問金流路徑(旅學不經基金會,其餘經基金會)
- 任何對外發送的內容:他只給草稿,不代你發出
- 修改 identity/、context/ 的核心內容

### 收工:收官流程(整套系統的引擎)

做完重要的事,對 Jentor 說一句:**「跑收官」**。

他會照 sop/after-action.md 把這件事寫進 memory/、更新相關文件、更新 memory-summary。

什麼算「重要的事」:

- 拍板了一個決策(定價、課程方向、人事)
- 一場活動或一個專案階段結束
- 踩了一個坑、學到一個教訓
- 任何「三個月後會想回頭查」的事

原則:做了不記等於沒做。Jentor 也會主動提醒,但你自己記得這個開關,系統才會越用越聰明。

### 平時:自己動手改

Vault 就是普通的 Markdown 資料夾,你隨時可以在 Obsidian 裡直接讀寫任何檔案。
改完不用做任何事,Obsidian Git 每 30 分鐘自動備份到 GitHub。
想立即備份:Cmd + P,輸入 git,選 Create backup。

---

## 二、常用的一句話指令

| 情境 | 對 Jentor 說 |
|------|-------------|
| 收納新文件進 Vault | 「把這份收進 Vault 適合的位置」(他會選資料夾、命名、同步索引) |
| 任務結束 | 「跑收官」 |
| 檢查索引有沒有漏 | 「跑一次 vault audit」 |
| 寫對外文字 | 直接交辦即可,他會自動先讀 voice-and-tone.md |
| 重要決策前 | 「幫我整理要跟大田討論的重點」 |
| 卡住、不知道從哪開始 | 「幫我拆出最小的第一步」 |
| 調整 Jentor 的行為 | 「把 persona 裡的某條改成……」(persona 是活的文件) |

---

## 三、定期維護節奏

### 隨手(每次新增檔案時)

由 Jentor 依強制規則自動執行,你只要抽查:

- 新檔案有 frontmatter(updated、tags、summary 三欄)
- 對應的 INDEX.md 或 README 索引同步更新了

### 每週(約 5 分鐘)

打開 memory-summary.md 清洗一次:

- Sticky Reminders:已解決的直接刪掉,不留「已完成」
- 重要決策表:補上結果欄
- 當前焦點:還是這三件事嗎?不是就改

### 每月(約 10 分鐘)

對 Jentor 說「跑一次 vault audit」。他會比對實際檔案與索引,回報差異,經你同意後才修。
跑完他會把日期記在 memory-summary,方便判斷下次何時該跑。

### 每季(約 30 分鐘)

- 重讀 agent-persona.md 和 identity/ 兩份檔案:規則還合身嗎?decision-style 的「待補充」段有沒有可以回填的觀察?
- 檢查 context/ 三份 overview 的數字與現況(學生人數、團隊、策略方向)是否過期
- projects/ 裡收官的專案搬進 archive/

### 檔案長大後的訊號

- 某資料夾超過約 10 個檔案且還在長:給它一份 INDEX.md,README 縮成一行入口
- README 底部更新紀錄超過兩條:舊的搬 sop/vault-changelog.md
- Jentor 開始讀錯檔案:代表索引不夠清楚,該優化了

---

## 四、異常排除

| 狀況 | 處理 |
|------|------|
| Jentor 說讀不到 Vault | 確認是在 Cowork 且工作資料夾指向 Jinni-Vault;換過電腦要重設 Global Instructions |
| 同步失敗或衝突 | 讀 sop/git-workflow.md 的「同步衝突發生時」;修不了就先備份再處理,不要硬 reset |
| 不確定系統有沒有在備份 | 開 GitHub 的 Jinni-Vault 頁面,看最新 commit 時間 |
| Jentor 的行為不像設定的 | 檢查 Global Instructions 還在不在(每台電腦各自設定,不會同步) |
| 換新電腦 | 照 sop/git-workflow.md 的「換電腦:完整安裝流程」,再補設 Global Instructions |

---

## 五、三條底線(不管多熟練都要守)

1. 學生個資、API key、密碼不進 Vault。學生一律用代稱。
2. 收費相關文件,動筆前確認金流路徑(context/foundation.md)。
3. 對外文字,發出前自己讀一遍。Jentor 給的是草稿,最後的語氣由你把關。
