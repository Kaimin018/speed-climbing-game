# IFSC Speed Climbing Simulator

這是一個基於 Three.js 的速度攀岩模擬遊戲。

## 部署說明 (Deployment)

此專案已配置為可直接部署至 [Vercel](https://vercel.com)。

### 步驟

1. 將此資料夾上傳至 GitHub Repository。
2. 在 Vercel 中選擇 "Add New Project"。
3. 匯入剛剛建立的 GitHub Repository。
4. Vercel 會自動偵測並部署靜態網站 (Static Site)。
   - **Framework Preset**: Other (或是自動偵測)
   - **Root Directory**: `./` (預設)

## 本地開發 (Local Development)

若要在本地執行，請使用任何靜態伺服器，例如 VS Code 的 "Live Server" 擴充功能，或是使用 Python:

```bash
# Python 3
python -m http.server 8000
```

然後打開瀏覽器訪問 `http://localhost:8000`。

## 檔案結構

- `index.html`: 遊戲主程式 (包含 CSS, JS 和 HTML)。
- `vercel.json`: Vercel 的部署配置。

