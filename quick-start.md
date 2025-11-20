# 快速啟動指南

## 問題診斷

如果直接拖曳 `index.html` 可以執行，但 localhost 不行，可能是以下原因：

### 1. 檢查伺服器是否在正確目錄

**測試方法：**
1. 訪問：`http://localhost:8000/test-server.html`（或你使用的端口）
2. 查看測試結果，確認：
   - 協議是否為 `http:`
   - `index.html` 檔案是否可訪問
   - Three.js 是否能載入

### 2. 確認訪問路徑

**正確的訪問方式：**
```
http://localhost:8000/index.html
```
（如果使用其他端口，請將 8000 替換為對應端口號）

**不要使用：**
- `file:///` 開頭的本地檔案路徑（雖然拖曳可以，但 ES6 模組需要 HTTP）

### 3. 端口被占用問題

**常見情況：**
- 8000 端口被其他程式占用
- 多個伺服器實例同時運行
- 之前的伺服器沒有正確關閉

**解決方法：**

#### 方法 A：使用不同的端口（推薦）

如果 8000 端口被占用，直接使用其他端口：

```powershell
python -m http.server 8080
```

然後訪問：`http://localhost:8080/index.html`

**其他常用端口：**
- 3000: `python -m http.server 3000` → `http://localhost:3000/index.html`
- 5000: `python -m http.server 5000` → `http://localhost:5000/index.html`
- 9000: `python -m http.server 9000` → `http://localhost:9000/index.html`

#### 方法 B：停止占用端口的程式

1. **查找占用端口的程式**：
   ```powershell
   netstat -ano | findstr :8000
   ```

2. **停止該程式**（將 PID 替換為實際的進程 ID）：
   ```powershell
   taskkill /PID <PID> /F
   ```

3. **重新啟動伺服器**：
   ```powershell
   python -m http.server 8000
   ```

#### 方法 C：重新啟動伺服器（確保在正確目錄）

1. **停止現有伺服器**（在終端按 `Ctrl+C`）

2. **確認目錄**：
   ```powershell
   cd "d:\2025 coding project\21_speed_climbing_game"
   Get-Location
   dir index.html
   ```

3. **啟動伺服器**（使用可用端口）：
   ```powershell
   python -m http.server 8080
   ```

4. **訪問頁面**：
   ```
   http://localhost:8080/index.html
   ```

### 4. 檢查瀏覽器控制台

1. 按 `F12` 打開開發者工具
2. 查看 Console 標籤
3. 查看 Network 標籤，確認檔案是否正確載入

### 5. 常見錯誤訊息

**CORS 錯誤：**
- 表示使用了 `file://` 協議
- 解決：使用 `http://localhost:8000/index.html`（或對應端口）

**404 Not Found：**
- 伺服器在錯誤的目錄
- 解決：確認伺服器在包含 `index.html` 的目錄中啟動

**端口被占用錯誤：**
- 錯誤訊息：`OSError: [WinError 10048] 通常每個套接字地址(協議/網路位址/端口)只允許使用一次`
- 解決：使用其他端口（如 8080、3000、5000 等）

**無法載入模組：**
- 網路問題或 CDN 無法訪問
- 解決：檢查網路連線，Three.js 從 unpkg.com 載入

## 推薦啟動流程

1. **確認目錄**：
   ```powershell
   cd "d:\2025 coding project\21_speed_climbing_game"
   ```

2. **啟動伺服器**（優先使用 8080，避免端口衝突）：
   ```powershell
   python -m http.server 8080
   ```

3. **訪問遊戲**：
   ```
   http://localhost:8080/index.html
   ```

4. **如果遇到問題**，訪問測試頁面查看診斷資訊：
   ```
   http://localhost:8080/test-server.html
   ```

## 遊戲操作說明

1. 點擊 **START** 開始遊戲
2. 使用**方向鍵**（↑↓←→）輸入螢幕上顯示的序列
3. 完成 20 個按鍵輸入後，角色會自動下降
4. 完成後會顯示你的完成時間

**停止伺服器**：在終端按 `Ctrl+C`

