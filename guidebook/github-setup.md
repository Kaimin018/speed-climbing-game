# 建立 GitHub Repository 並連接 Remote

### 方法一：使用 GitHub CLI (推薦)

如果你已安裝 GitHub CLI (`gh`):

```bash
# 建立新的 GitHub repository (會自動連接 remote)
gh repo create speed-climbing-game --public --source=. --remote=origin --push
```

### 方法二：手動建立

1. **在 GitHub 網站建立新 Repository**
   - 前往 https://github.com/new
   - Repository name: `speed-climbing-game` (或你喜歡的名稱)
   - 選擇 Public 或 Private
   - **不要**勾選 "Initialize this repository with a README" (因為本地已有檔案)
   - 點擊 "Create repository"

2. **連接 Remote 並推送**
   ```bash
   # 將 GitHub repo 設為 remote origin
   git remote add origin https://github.com/YOUR_USERNAME/speed-climbing-game.git
   
   # 或使用 SSH (如果你有設定 SSH key)
   # git remote add origin git@github.com:YOUR_USERNAME/speed-climbing-game.git
   
   # 推送程式碼到 GitHub
   git branch -M main
   git push -u origin main
   ```

   > 將 `YOUR_USERNAME` 替換為你的 GitHub 使用者名稱

### 方法三：使用 Cursor 的 Git 整合

1. 在 Cursor 中，點擊左側的 Source Control (Ctrl+Shift+G)
2. 點擊右上角的 "..." 選單
3. 選擇 "Publish to GitHub"
4. 輸入 Repository 名稱並選擇 Public/Private
5. Cursor 會自動建立 repo 並推送程式碼

