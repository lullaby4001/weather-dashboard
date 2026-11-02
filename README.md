# weather-dashboard
# ☕ 暖咖風格 - 雙軸溫濕度與天氣預報系統 (Coffee Weather Dashboard)

這是一個兼具質感與實用性的單頁 Web 應用程式，支援「當前 GPS 自動定位」、「全台/全球地址與地名搜尋」以及「1~16 天靈活預報區間切換」，並透過雙 Y 軸圖表呈現溫度與相對濕度變化。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Build](https://img.shields.io/badge/HTML5-CSS3-orange)
![API](https://img.shields.io/badge/API-Open--Meteo-brightgreen)

## ✨ 核心功能
* 📍 **開頁自動定位**：優先調用瀏覽器 GPS 取得當前位置的即時天氣與濕度。
* 🔍 **全球地址搜尋**：整合 OpenStreetMap 地理編碼，輸入任意地址或城市名稱皆可查詢。
* 🗓️ **靈活預報區間**：支援選擇 1天、3天、7天（1週）、14天（2週）與 16 天氣象模型極限預報。
* 📈 **雙 Y 軸互動圖表**：使用 Chart.js 同時呈現每日「高/低氣溫」與「相對濕度」趨勢。
* ☕ **暖咖質感 UI**：採用拿鐵、焦糖與摩卡色調的響應式設計，兼具視覺舒適度與良好易讀性。

## 🛠️ 使用技術與第三方資源 (Tech Stack & Resources)

### 前端開發
* **HTML5 / CSS3 (CSS Variables, Flexbox, Grid)** - 結構設計與暖咖啡色系 RWD 介面
* **JavaScript (ES6+)** - 原生 DOM 操作與 Fetch API 非同步流程控制

### 第三方 API & 數據庫
* [Open-Meteo API](https://open-meteo.com/) - 氣候數據 API（氣溫、相對濕度、體感溫度、降雨量）
* [OpenStreetMap Nominatim API](https://nominatim.org/) - 地理編碼 API（地名/地址轉經緯度）
* [Web Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API) - 瀏覽器原生定位

### 視覺與圖表庫
* [Chart.js](https://www.chartjs.org/) - 繪製動態雙 Y 軸折線圖
* [Font Awesome 6](https://fontawesome.com/) - 氣象與介面圖示
* [Google Fonts](https://fonts.google.com/) - Noto Serif TC & Outfit 字體

## 🚀 部署平台
* **GitHub Pages** - 靜態網站託管與 HTTPS 連線安全防護
