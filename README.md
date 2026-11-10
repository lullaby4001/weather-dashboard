# weather-dashboard
# 🌤️ 雙軸溫濕度與智慧生活氣象站 (Weather Dashboard)

一個兼具高雅質感與實用功能的單頁 Web 氣象應用程式。採用暖咖啡色系（Warm Coffee Palette）視覺風格，支援「GPS 自動定位」、「全台 22 縣市平鋪選單」、「全球地址/地名搜尋」、「1~60 天靈活預測區間（含歷史氣候虛線推估）」以及「智慧生活與穿著建議系統」，並以 Chart.js 雙 Y 軸互動圖表精準呈現每日溫濕度趨勢。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![HTML5](https://img.shields.io/badge/HTML5-CSS3-orange.svg)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-v3.x-38bdf8.svg)
![API](https://img.shields.io/badge/API-Open--Meteo-brightgreen.svg)
![Hosting](https://img.shields.io/badge/Hosting-GitHub_Pages-success.svg)

---

## ✨ 核心功能特色 (Features)

### 1. 📍 智慧定位與彈性地點切換
* **HTML5 GPS 自動定位**：初次開啟自動請求 GPS 位置，精準讀取當前所在地氣象（全站採 HTTPS 部署確保存取順暢）。
* **台灣 22 縣市完整選單**：收錄全台 6 直轄市、3 省轄市、13 縣及離島（澎湖、金門、馬祖），一鍵快速切換。
* **全球地址與地名搜尋**：整合 OpenStreetMap 地理編碼 API，支援輸入任意地址、知名景點或國外城市。
* **近期搜尋歷史**：自動紀錄最近查詢地點，方便快速點擊重測。

### 2. 👔 智慧生活與穿搭建議系統 (Smart Weather & Outfit Advice)
* **雨具提示**：當降雨機率或累積雨量達到標準時，主動提醒隨身攜帶雨傘/雨衣。
* **防曬防暑**：高溫（$\ge 27^\circ\text{C}$）或強烈陽光時提示補充水分與防曬。
* **洋蔥式穿搭 / 禦寒保暖**：針對日夜溫差（$\ge 7^\circ\text{C}$）或低溫情境，提供彈性穿脫外套建議。
* **體感防潮與補水**：結合相對濕度評估，提供除濕機開啟或喉嚨保濕指引。
* **每日小標籤**：每日預報卡片自動標註 `☂️ 記得帶傘`、`☀️ 做好防曬`、`🧥 洋蔥穿搭` 等便利標籤。

### 3. 🗓️ 1 ~ 60 天預測區間（實線 / 虛線氣候推估）
* **1 ~ 16 天（數值預報 - 實線）**：串接 Open-Meteo 高精準氣象模型數據，圖表以**實線**呈現。
* **17 ~ 60 天（歷史氣候推估 - 虛線）**：當選擇 30 天或 60 天長週期時，第 17 天起自動聯立 Open-Meteo Historical Archive API 撈取去年同期數據進行氣候統計推估，圖表自動無縫轉為**動態虛線**，卡片右上角特別標註「歷史推估」標籤。

### 4. 📈 雙 Y 軸互動式趨勢圖表
* 左軸為**氣溫 (°C)**（高溫/低溫折線），右軸為**相對濕度 (%)**（面域填充圖）。
* 支援「雙軸對比」、「僅看氣溫」、「僅看濕度」三種圖表視角切換。
* 支援懸停細節展示，並明確標註該數據點屬於「數值預報」或「歷史推估」。

### 5. ☕ 暖咖質感 UI Design
* 採用拿鐵乳白（Latte `#faf7f2`）、焦糖暖橘（Caramel `#c88a58`）、烤摩卡棕（Mocha `#8c6239`）與濃縮咖啡（Espresso `#4a3324`）色調。
* 響應式排版（RWD），在手機、平板與電腦上皆有極佳的視覺與操作體驗。

---

## 🛠️ 使用技術與第三方資源 (Tech Stack & Resources)

| 類別 | 技術 / 資源名稱 | 說明與用途 |
| :--- | :--- | :--- |
| **前端架構** | **HTML5 / Single-Page Application** | 無需複雜前端框架，單一檔案即開即用 |
| **樣式設計** | **Tailwind CSS (v3.x CDN)** | 現代化 Utility-First CSS 框架，建構暖咖風格 RWD 介面 |
| **程式邏輯** | **JavaScript (ES6+)** | Async/Await 非同步控制、DOM 操作、LocalStorage 搜尋紀錄 |
| **氣象數據 API** | [Open-Meteo API](https://open-meteo.com/) | 免金鑰氣象 API，提供即時氣溫、濕度、風速與 1-16 天數值預報 |
| **歷史數據 API** | [Open-Meteo Archive API](https://open-meteo.com/en/docs/historical-weather-api) | 撈取歷史氣候資料庫，用作 17-60 天氣候趨勢推估 |
| **地理編碼 API** | [OpenStreetMap Nominatim](https://nominatim.org/) | 文字地址 / 地名轉座標，以及 GPS 座標反向轉地名 |
| **圖表繪製** | [Chart.js (v4.x)](https://www.chartjs.org/) | 繪製雙 Y 軸動態折線圖、Segment 虛線分段控制 |
| **圖示與字型** | Font Awesome 6 / Google Fonts | Noto Sans TC / Plus Jakarta Sans 字型與向量天氣圖示 |
| **託管部署** | **GitHub Pages** | 免費靜態網站託管，並提供免費 HTTPS 憑證 (GPS 定位必備) |

---

## 🚀 快速開始與本地執行 (Quick Start)

1. **複製專案**：
   ```bash
   git clone https://github.com/lullaby4001/weather-dashboard.git
   cd weather-dashboard
   ```

2. **開啟網頁**：
   因為本專案為純前端應用，無需安裝 `node_modules` 或啟動伺服器，直接在瀏覽器中雙擊打開 `index.html` 即可運作！

> 💡 **提示**：由於瀏覽器安全機制（Geolocation Security Standard），GPS 自動定位功能需要在 **HTTPS 網域**（如 GitHub Pages）或本地 `localhost` 環境下才能正常存取。

---

## 🌐 部署至 GitHub Pages (Hosting)

1. 將 `index.html` 與 `README.md` 推送至你的 GitHub Repository。
2. 進入 Repository 頁面 $\rightarrow$ 點擊 **Settings** 頁籤。
3. 在左側欄位點選 **Pages**。
4. 在 **Branch** 選項中將 `None` 改為 `main`（或 `master`），目錄維持 `/(root)`。
5. 按下 **Save**，約 1~3 分鐘後即可透過 GitHub Pages 提供的免費 HTTPS 網址訪問您的網頁！

---

## 📜 授權條款 (License)

本專案採用 [MIT License](LICENSE) 條款開源，歡迎自由修改、擴充與學習交流。
