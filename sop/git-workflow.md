---
updated: 2026-07-06
tags: [sop]
summary: Git 日常同步、換電腦安裝、衝突救援、敏感檔案移除
---

# Git Workflow SOP — 日常與救火

> 日常同步、第二台機器設定、衝突發生時怎麼救。忘記步驟時翻這份。

---

## 日常同步(自動)

裝了 Obsidian Git 外掛後,每 30 分鐘自動 commit + push。不用跑任何指令。

立即同步:在 Obsidian 按 `Ctrl + P` → 輸入 `git` → 選 **Create backup**。

---

## 手動同步(備用)

外掛出問題時,在 Vault 資料夾打開終端機:

```bash
cd "[Vault 路徑]"
git add .
git commit -m "manual sync"
git push
```

---

## 換電腦:完整安裝流程

1. 安裝 Git(https://git-scm.com),設定身份:
   ```bash
   git config --global user.email "GitHub 信箱"
   git config --global user.name "GitHub 帳號"
   ```
2. 安裝 Obsidian(https://obsidian.md)
3. Clone Vault:
   ```bash
   cd Documents
   git clone https://github.com/[帳號]/[repo].git
   ```
4. Obsidian →「開啟資料夾作為儲存庫」→ 指向 clone 下來的資料夾
5. 裝 Obsidian Git 外掛,Auto commit-and-sync interval 設 30

---

## 同步衝突發生時

最常見:電腦 A 改了檔案 X,電腦 B 沒先同步又改了同個檔案,push 被拒絕。

1. 停止在衝突的機器上編輯
2. 打開受影響的檔案,Git 會留下衝突標記:
   ```
   <<<<<<< HEAD
   本機的版本
   =======
   遠端的版本
   >>>>>>> origin/main
   ```
3. 手動選擇要保留什麼,刪掉標記
4. 存檔 → Commit all changes → Push

修不了:先把本機 copy 備份到別處,再 `git reset --hard origin/main` 重置成遠端版本,從備份手動 apply 修改。沒備份不要 reset。

---

## 看修改歷史

- GitHub repo → commits
- 單一檔案:GitHub 打開檔案 → History
- 本機:Obsidian `Ctrl + P` → `git: open history view`

---

## 把敏感檔案從歷史移除

1. 先加到 `.gitignore`
2. `git rm --cached path/to/file` → commit → push
3. 注意:過去的 commit 還有它。如果是 API key 等真敏感資料,請直接輪替憑證,當作已公開

---

## 卡住時的安全診斷指令

```bash
git status
git log --oneline -10
```

把輸出貼給 AI,通常就能診斷出問題。
