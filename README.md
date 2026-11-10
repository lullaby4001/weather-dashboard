# weather-dashboard
# ☕ 天氣助手 - 雙軸溫濕度與智慧生活預報系統 (Weather Dashboard)

一個兼具高視覺質感與實用工程思維的響應式 Web 應用程式。整合原生地理定位、全球地址搜尋、數值氣象模型與歷史氣候大數據，提供 1 至 60 天的極限氣候趨勢分析與智慧穿著生活建議。

![License](https://img.shields.io/badge/license-MIT-brown.svg)
![Frontend](https://img.shields.io/badge/JavaScript-ES6+-f7df1e)
![CSS3](https://img.shields.io/badge/CSS3-Variables--RWD-blue)
![API](https://img.shields.io/badge/API-Open--Meteo-brightgreen)
![Data](https://img.shields.io/badge/Data-OpenStreetMap-green)

---

## 🌟 產品亮點與使用者體驗 (UX Highlights)

* 🎨 **暖咖美學介面 (Coffee Palette RWD)**：採用拿鐵奶白、焦糖暖橘與烤摩卡棕色調，打造舒緩無壓力的閱讀體驗。
* 📍 **無感定位與全台直達**：支援 HTML5 GPS 自動定位、全台 22 縣市快速切換選單，以及 Nominatim 全球地址動態搜尋。
* 🧥 **智慧穿衣與生活建議 (Advice Engine)**：自動分析高低溫、日夜溫差、降雨機率與相對濕度，生成即時與未來逐日的帶傘、防曬、洋蔥式穿搭指引。
* 📈 **1~60 天實線/虛線長期趨勢圖**：獨創「預報+歷史統計」雙模架構，前 16 天為高精準數值模型預報（實線），第 17~60 天採用氣候大數據歷史統計推估（虛線）。

---

## 🛠️ 技術架構與資源 (Tech Stack & Resources)

| 分類 | 技術 / 資源名稱 | 用途與說明 |
| :--- | :--- | :--- |
| **前端架構** | Vanilla JavaScript (ES6+) | 無框架依賴（Zero-dependency），極致輕量化與首屏載入速度 |
| **樣式系統** | CSS3 Custom Properties | 原生 CSS 變數維護咖啡主題色系，配合 Flexbox/Grid 響應式排版 |
| **圖表繪製** | Chart.js (v4.x) | 採用雙 Y 軸（氣溫/濕度）繪製互動折線圖，運用 Segment API動態轉換虛實線 |
| **氣象 API** | Open-Meteo Forecast API | 免費開放式 API，提供未來 16 天高精度氣溫、體感溫度、相對濕度與 WMO 天氣代碼 |
| **歷史 API** | Open-Meteo Archive API | 提供歷史氣象資料庫，用於第 17~60 天的去同期歷史氣候統計推估 |
| **地理編碼** | OpenStreetMap Nominatim API | 將使用者輸入的文字地址/地名轉換為精確經緯度座標 |
| **定位與圖示**| HTML5 Geolocation API / FontAwesome | 原生定位與語意化氣象 SVG 圖示 |
| **雲端部署** | GitHub Pages | 自動化靜態託管與 HTTPS 安全憑證，確保 Geolocation API 授權順利 |

---

## 🧠 核心開發邏輯 (Technical Logic)

1. **混合式預報資料拼接算法 (Hybrid Data Merging)**：
   * `1 ~ 16 天`：呼叫 `forecast` 節點取得數值氣象模型算出的逐日數據。
   * `17 ~ 60 天`：開啟非同步 `fetch` 讀取去年同期的 `archive` 氣候資料，兩者在前端數據層進行串接與日期重排。
2. **Chart.js 動態線條樣式控制 (Segment BorderDash)**：
   * 透過 Chart.js 的 `segment` 屬性，實時監聽資料點 Index。當 Index $\ge 15$（即第 16 天過後），折線自動轉為 `[6, 6]` 虛線渲染。
3. **多因子智慧建議引擎 (Multi-factor Decision Engine)**：
   * 綜合計算 **WMO 天氣代碼 (Weather Code)**、**最高/最低溫**、**溫差 ($\Delta T > 7^\circ\text{C}$)** 與 **相對濕度 ($RH$)**，判斷是否輸出雨具、防曬、洋蔥式穿搭或保濕除濕建議。

---

## 🚀 快速上手 (Getting Started)

1. Clone 本儲存庫：
   ```bash
   git clone [https://github.com/](https://github.com/)<lullaby4001>/weather-dashboard.git
