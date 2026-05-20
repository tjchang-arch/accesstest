## Git Issue 建立步驟指南

---

## 步驟一：去 GitHub / GitLab 建立 Issue

當你發現 Bug 或有新需求時，請先到專案的 **Issues** 頁面點擊 **New Issue**。

1. **標題命名**：請統一格式，讓人一眼看出問題模組。
   * *修 Bug*：`[Bug] 購物車 - 點擊結帳按鈕沒反應`
   * *新需求*：`[Feature] 會員中心 - 新增手機驗證碼登入`
2. **填寫內文**：請複製並填寫以下結構：
   * **問題描述**：簡短說明遇到什麼事。
   * **重現步驟**：第 1 步、第 2 步、第 3 步做什麼才會看到錯誤。
   * **環境與截圖**：附上瀏覽器版本、測試環境（Staging/Prod）以及錯誤畫面截圖。
3. **送出 Issue**：送出後，請記下該 Issue 的**專屬編號**（例如：`#42`）。

---

## 步驟二：在本地端建立 Git 分支 (Branch)

負責修復或開發該 Issue 的工程師，請依據 Issue 編號在本地端建立對應的分支。

1. **同步主分支最新程式碼**：

```

```text
File saved successfully at README.md

```bash
   git checkout main
   git pull origin main

```

2. **建立功能分支**（分支名稱必須包含 `issue-{編號}`）：
```bash
# 如果是修 Bug
git checkout -b bugfix/issue-42-fix-cart-button

# 如果是開發新功能
git checkout -b feature/issue-42-sms-login

```



---

##  步驟三：提交 Commit 並推送到遠端

程式碼修改完成後，提交 Commit 訊息時請**標註 Issue 編號**，方便日後追蹤。

1. **提交 Commit**：
```bash
git add .
git commit -m "fix(cart): resolve checkout button click issue (#42)"

```


2. **推送到遠端倉庫**：
```bash
git push origin bugfix/issue-42-fix-cart-button

```



---

##  步驟四：發起 Pull Request (PR) 與自動關閉

1. 回到 GitHub/GitLab 專案頁面，點擊 **Compare & pull request**。
2. **關鍵自動化步驟**：在 PR 的描述（Description）欄位中，寫上：
```markdown
Closes #42

```


*(寫了這行，當 PR 被審查並合併（Merge）後，系統就會**自動關閉**第 42 號 Issue，不需手動去點 Close！)*
3. 指派 Code Reviewer（審查者），等待合併。
"""

file_path = "README.md"
with open(file_path, "w", encoding="utf-8") as f:
f.write(markdown_content)

print(f"File saved successfully at {file_path}")

```
