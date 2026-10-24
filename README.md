# 🎬 DiDiGo StreamRecorder

<p align="center">
  <img src="icons/icon128.png" width="108" height="108" alt="DiDiGo StreamRecorder Logo" />
</p>

<p align="center">
  <b>現代直播串流無人值守下載 & 本機錄製中心</b><br>
  專為 HLS / LL-HLS (<code>#EXT-X-PART</code>) / fMP4 / HTTP-FLV 打造的通用瀏覽器擴充功能與桌面合流引擎
</p>

<p align="center">
  <a href="README.md"><b>繁體中文</b></a> •
  <a href="README_EN.md">English</a> •
  <a href="README_JA.md">日本語</a> •
  <a href="README_DE.md">Deutsch</a> •
  <a href="README_RU.md">Русский</a> •
  <a href="README_ES.md">Español</a> •
  <a href="README_FR.md">Français</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-1.4.0-brightgreen.svg?style=flat-square" alt="Version" />
  <img src="https://img.shields.io/badge/Manifest-V3-blue.svg?style=flat-square" alt="Manifest V3" />
  <img src="https://img.shields.io/badge/Node.js-20%2B-green.svg?style=flat-square" alt="Node" />
  <img src="https://img.shields.io/badge/Platform-Chromium%20%7C%20Firefox-orange.svg?style=flat-square" alt="Platform" />
  <img src="https://img.shields.io/badge/License-MIT-purple.svg?style=flat-square" alt="License" />
</p>

---

## 🌟 亮點功能 (Highlights)

- ⚡ **LL-HLS 微切片完整解析**：原生攔截低延遲微切片 (`#EXT-X-PART`) 與 fMP4 初始化區段 (`#EXT-X-MAP`)，智慧清洗過期參數，平滑錄製不中斷。
- 🕵️ **旗艦級老闆鍵偽裝 (`Alt + B`)**：一鍵將下載頁面 1:1 偽裝為 **Google Sheets / Excel 財務成本分析表**，標題與圖示同步變更，後台下載照常全速運行。
- 🎯 **免開 F12 視覺化元素拾取器**：直接在網頁點擊下播或付費提示框，自動反推 CSS 選擇器並匯出為熱更新規則包。
- 🚀 **Desktop Pro 原生合流雙引擎**：
  - **`DiDiGoHub.exe`**：Windows 原生系統匣常駐啟動器，全自動配置免安裝 FFmpeg。
  - **`DiDiGoMuxer.exe`**：極速影音雙軌無損合併，支援拖曳即合。
- 📦 **自訂大小無損分段存檔**：支援設定 200MB / 500MB / 1GB 或自訂大小自動分卷，各卷皆內嵌初始化頭部，直接播放不損壞。
- 📨 **多通道遠端即時推播**：支援 Discord / Telegram Webhook，開播錄製與切片完成第一時間推播通知。

---

## 🏗️ 三層模組化架構 (Editions & Architecture)

| 模組版本 | 適用情境 | 核心功能 | 啟動與使用方式 |
| :--- | :--- | :--- | :--- |
| **🌐 瀏覽器擴充標準版**<br>*(Standard Extension)* | 免額外軟體、即裝即用 | M3U8 / DASH 嗅探、老闆鍵 (`Alt+B`)、自動靜音巡檢、分段下載 | Chrome / Brave / Edge 載入已解壓擴充功能 |
| **🧩 站台擴充規則包**<br>*(External Add-on Pack)* | 網站改版免升級外掛 | 動態擴充 CDN 白名單、防盜鏈 Headers、開下播 DOM 偵測規則 | 於「存檔庫」頁籤匯入 `.json` 或使用視覺化拾取器 |
| **🚀 本機桌面 Pro 引擎**<br>*(Desktop Pro Engine)* | 長時間無人值守、音畫分離合併 | 獨立 FFmpeg 背景錄製、4x4 十六宮格預覽縮圖、硬碟容量警戒安全封裝 | 執行 `DiDiGoHub.exe` 或啟動本機伺服器 |

---

## 🚀 快速安裝與上手 (Quick Start)

### 1. 安裝瀏覽器擴充功能 (Chromium / Brave / Edge)

1. Clone 或下載專案至本機：
   ```bash
   git clone https://github.com/your-username/DiDiGo.git
