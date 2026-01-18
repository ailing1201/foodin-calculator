# FoodIn 智能報價計算器 (Premium Dark Edition)

> 專為 FoodIn 打造的頂級黑金風格報價系統，整合 AI 智能顧問與即時報價功能。

## ✨ 最新特色 (v2.0)

- **🎨 Premium Dark 黑金風格**：採用與 FoodIn 官網一致的黑金配色 (`#C8AA6E`) 與襯線字體。
- **🤖 AI 智能顧問**：內建 Gemini AI，可根據客戶需求推薦服務組合（神秘紫金配色）。
- **📱 手機體驗優化**：新增底部懸浮總價列，隨時掌握預算。
- **📖 新增服務分類**：加入「外送平台套餐」、「菜單設計」、「動態短影片」等完整服務。
- **📸 一鍵截圖**：自動生成高解析度 PNG 報價單。

## 📁 檔案結構

```
calculator/
├── index.html      # 主頁面 (引入 Noto Serif TC 字體)
├── styles.css      # 樣式表 (黑金風格、RWD、動畫)
├── app.js          # 核必邏輯 (資料、AI、截圖、RWD)
└── README.md       # 本說明文件
```

## 🚀 快速部署

### 方式一：GitHub Pages (推薦)
1. 將 `calculator` 資料夾上傳至 GitHub Repository。
2. 開啟 GitHub Pages 功能。
3. 網址範例：`https://foodin-tw.github.io/foodin-calculator/`

### 方式二：整合至官網
將 `calculator` 資料夾放入網站根目錄，透過 iframe 或直接連結即可。

## ⚙️ 設定說明

### 1. 修改 AI API Key (必要)
若要啟用 AI 顧問功能，請在 `app.js` 中設定您的 Google Gemini API Key：
```javascript
// app.js 約第 230 行
const apiKey = "YOUR_GEMINI_API_KEY";
```

### 2. 修改服務項目與價格
所有服務資料位於 `app.js` 開頭的 `categories` 陣列中：
```javascript
const categories = [
  {
    id: 'platform',
    title: '外送平台專用套餐',
    items: [
      { id: 'pl1', name: '【熱銷】入門套餐', price: 2500, ... }
    ]
  },
  // ...
];
```

### 3. 修改 LINE 帳號
在 `index.html` 中搜尋 `@foodin` 即可修改顯示的 LINE ID 與連結。

## 🎨 設計系統 (Design System)

本專案使用 CSS Variables 定義主題色，方便統一調整：

```css
:root {
  /* Premium Gold Palette */
  --gold-400: #C8AA6E; /* 主題金 */
  
  /* Dark Mode Palette */
  --bg-dark: #0a0a0a;  /* 背景黑 */
  --bg-card: #141414;  /* 卡片深灰 */
  
  /* Fonts */
  font-family: 'Noto Serif TC', serif; /* 標題 */
  font-family: 'Noto Sans TC', sans-serif; /* 內文 */
}
```

## 📱 手機版懸浮總價
`app.js` 會自動偵測是否包含 `.sticky-footer` 元素，若無則自動生成。
相關樣式位於 `styles.css` 底部。

## 📞 支援
如有程式碼修改問題，請聯繫 FoodIn 技術團隊。
