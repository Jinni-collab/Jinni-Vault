---
updated: 2026-07-06
tags: [sop]
summary: 索引完整性檢查流程,每月或大量變動後跑
---

# Vault Audit — 索引完整性檢查

> 定期檢查 vault 索引(root README.md 與各資料夾 INDEX.md)是否跟實際檔案結構一致。

## 什麼時候跑

- 使用者主動要求:「跑一次 vault audit」
- Agent 主動建議:最近大量檔案變動、一陣子沒跑
- 建議頻率:每月一次,或發現 Agent 找的檔案你不認得時

## 怎麼跑(Agent 行為)

1. 列出實際檔案:
   ```bash
   cd "[Vault 路徑]"
   find . -type f -name "*.md" -not -path "./.obsidian/*" -not -path "./.git/*" | sort
   ```
2. 讀 root README.md(與各資料夾 INDEX.md),列出已 index 的檔案
3. 比對差異:
   - 有檔案但沒 index → 需要補
   - 有 index 但檔案不存在 → 過時,需移除
4. 產出報告(摘要 + 兩類清單 + 建議)
5. 使用者決定後,Agent 才更新索引

## 關鍵原則

1. 不自動修改 README,只回報差異
2. 暫存檔可以不 index,但必須在報告裡列出
3. 每次跑完,在 memory-summary.md 留下「最後 audit 日期」
4. audit 結果不寫進 memory/(操作行為,非決策)

## 忽略清單

- root 的暫存協調檔、一次性 deliverable
- skills/ 內主 skill 檔以外的支援檔
- .obsidian/、.git/ 等系統目錄
