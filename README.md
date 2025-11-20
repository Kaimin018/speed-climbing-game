# IFSC Speed Climbing Simulator

這是一個基於 Three.js 的速度攀岩模擬遊戲。

## 文件

- [建立 GitHub Repository 指南](guidebook/github-setup.md)

## 部署說明 (Deployment)

此專案已配置為可直接部署至 [Vercel](https://vercel.com)。

### 步驟

1. 確保程式碼已推送到 GitHub Repository。
2. 在 Vercel 中選擇 "Add New Project"。
3. 匯入剛剛建立的 GitHub Repository。
4. Vercel 會自動偵測並部署靜態網站 (Static Site)。
   - **Framework Preset**: Other (或是自動偵測)
   - **Root Directory**: `./` (預設)

## 本地開發 (Local Development)

### 方法一：使用專案提供的伺服器腳本 (推薦)

在專案根目錄執行：

```bash
python server.py
```

或指定端口：

```bash
python server.py 8000
```

然後打開瀏覽器訪問 `http://localhost:8000`（會自動載入 index.html）

### 方法二：使用 Python 內建伺服器

在專案根目錄執行：

```bash
# Python 3
python -m http.server 8000
```

然後打開瀏覽器訪問 `http://localhost:8000/index.html`（注意：需要加上 `/index.html`）

### 方法二：使用 VS Code Live Server

1. 安裝 VS Code 的 "Live Server" 擴充功能
2. 在 `index.html` 上點擊右鍵
3. 選擇 "Open with Live Server"

### 方法三：使用 Node.js (http-server)

```bash
# 安裝 http-server (全域)
npm install -g http-server

# 在專案目錄執行
http-server -p 8000
```

然後訪問 `http://localhost:8000`

### 方法四：使用 PHP

```bash
php -S localhost:8000
```

### 注意事項

⚠️ **重要**：由於使用了 ES6 模組 (`import`)，必須透過 HTTP 伺服器執行，不能直接用 `file://` 協議打開 `index.html`，否則會出現 CORS 錯誤。

## 檔案結構

- `index.html`: 遊戲主程式 (包含 CSS, JS 和 HTML)。
- `vercel.json`: Vercel 的部署配置。

