# 🎬 DiDiGo StreamRecorder — 瀏覽器擴充功能標準版 (Standard Edition)

<p align="center">
  <img src="icons/icon128.png" width="96" height="96" alt="DiDiGo StreamRecorder Logo" />
</p>

<p align="center">
  <b>免安裝額外軟體、即裝即用的現代串流嗅探與無人值守直播錄製擴充功能</b><br>
  專為 Chromium 核心瀏覽器打造（Google Chrome、Brave、Microsoft Edge）
</p>

<p align="center">
  <a href="README_STANDARD.md"><b>繁體中文</b></a> | 
  <a href="README_STANDARD_EN.md">English</a> | 
  <a href="README_STANDARD_JA.md">日本語</a> | 
  <a href="README_STANDARD_DE.md">Deutsch</a> | 
  <a href="README_STANDARD_RU.md">Русский</a> | 
  <a href="README_STANDARD_ES.md">Español</a> | 
  <a href="README_STANDARD_FR.md">Français</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-1.4.0-brightgreen.svg" alt="Version 1.4.0" />
  <img src="https://img.shields.io/badge/Manifest-V3-blue.svg" alt="Manifest V3" />
  <img src="https://img.shields.io/badge/Platform-Chrome%20%7C%20Brave%20%7C%20Edge-brightgreen.svg" alt="Platform" />
  <img src="https://img.shields.io/badge/Languages-7%20Languages-yellow.svg" alt="7 Languages" />
  <img src="https://img.shields.io/badge/License-MIT-purple.svg" alt="License MIT" />
</p>

---

## 📌 什麼是標準版 (Standard Edition)？

**DiDiGo StreamRecorder 標準版** 是一個採用最新 **Chrome Manifest V3** 規範建構的純瀏覽器端擴充功能。無需在電腦上安裝 Node.js、Python 或任何第三方編譯軟體，點擊安裝後即可在瀏覽器內直接完成：

- **即時串流嗅探**：自動攔截 M3U8、低延遲 LL-HLS (`#EXT-X-PART`)、fMP4、DASH 與 FLV (LIVE) 串流。
- **無人值守排程巡檢**：設定追蹤網址，每 5 分鐘輕量探測，開播自動建立背景工作台拉取切片。
- **純瀏覽器解碼與分段封裝**：以 fMP4 格式在瀏覽器內合併切片，自動依 MB/GB 分段安全下載存檔。
- **進階隱私與通知**：具備一鍵老闆鍵試算表偽裝 (`Alt+B`)、後台自動靜音與 Discord/Telegram 遠端通知。

> 💡 **註**：如需長達數十小時重度掛機錄影、自動將音畫分離串流無損壓製合併或產出 4x4 縮圖，可搭配本機桌面輔助工具（詳見主專案 [README.md](README.md)）。標準版擴充功能本身完全獨立，可 100% 離線在瀏覽器運作。

---

## ✨ 核心特色與功能亮點

### 1. ⚡ 支援現代低延遲 LL-HLS (`#EXT-X-PART`) 與微切片解析
- **微切片自動重組**：自動攔截並解析 `#EXT-X-PART` 與 `#EXT-X-MAP` 初始化檔頭 (`init.mp4`)，確保影片在播放器中精準還原。
- **過期參數自動清洗**：移除 M3U8 輪詢中可能導致連線超時的 `HLS_msn` 與 `HLS_part` 阻礙參數。
- **前導廣告與過渡標籤過濾**：自動跳過廣告切片，待進入正片串流後無縫啟動下載。

### 2. 📺 畫質動態適配 (Dynamic Quality Picker)
- 根據直播來源的 Master Playlist 即時解析可用解析度（如 1080p、720p、480p 或特殊比例）。
- 彈窗介面動態渲染畫質按鈕，支援「🌟 自動最高畫質 (Best)」優先與一鍵即時切換。

### 3. 🎯 多目標無人值守追蹤 (每 5 分鐘節流巡檢)
- 支援通配符（如 `example.com/channel*`）管理多個追蹤頻道。
- 嚴格落實 **5 分鐘節流** 與 **單一網頁排重鎖定機制**，杜絕頻繁開關分頁導致的 CPU / 記憶體爆量問題。

### 4. 📦 自訂大小自動分段存檔 (Auto-Split & Silent Save)
- 支援自訂分段大小（如每 200 MB、500 MB、1 GB 存為一卷，設 0 代表單檔完整存檔）。
- 每個分卷自動附加完整 fMP4 檔頭，即使中途停止錄製，已下載的分卷依然能夠完美播放。
- 透過瀏覽器 Downloads API 靜默寫入預設下載資料夾，免去重複確認另存新檔視窗的困擾。

### 5. 🕵️ 旗艦級隱私與工作輔助
- **🕵️ 老闆鍵偽裝 (`Alt + B`)**：一鍵將下載工作台瞬間偽裝為 **Google Sheets / Excel 雲端成本分析報表**，更換分頁 Favicon 與標題，背景錄製完全不中斷。
- **🔇 背景探測自動靜音**：無人值守探測時自動將巡檢分頁靜音，避免夜間掛機突然爆音。
- **📨 遠端推播**：支援 Discord 與 Telegram Webhook，開播、錄製與分段完成即時傳送訊息到手機。

### 6. 🧩 外部站台擴充規則包 (Add-on Pack)
- 遇網站改版或防盜鏈更新時，無需重新安裝擴充功能。
- 在「存檔庫」頁籤直接匯入 `.json` 規則檔，即可熱更新 CDN 代理白名單與 DOM 選擇器。
- 內建 **🎯 視覺化元素拾取器**：在直播網頁上點一下離線提示，自動計算 CSS Selector 並保存。

---

## 🚀 快速安裝步驟

### 推薦環境
- **瀏覽器**：Google Chrome、Brave、Microsoft Edge 或其他 Chromium 核心瀏覽器（建議版本 109+）。
- **權限說明**：僅要求 `storage`、`downloads`、`alarms`、`webRequest` 等最低限度必要權限，無任何資料外洩風險。

### 手動載入安裝（開發人員模式）
1. 下載或 Clone 本專案原始碼至本機：
   ```bash
   git clone https://github.com/ComicsChou/DiDiGo-StreamRecorder.git
   ```
2. 開啟瀏覽器並前往擴充功能管理頁面：
   - **Chrome**: `chrome://extensions/`
   - **Brave**: `brave://extensions/`
   - **Edge**: `edge://extensions/`
3. 開啟右上角 **「開發人員模式 (Developer mode)」** 切換開關。
4. 點擊左上角 **「載入未封裝項目 (Load unpacked)」** 按鈕。
5. 選擇本專案資料夾（包含 `manifest.json` 的目錄）。
6. 安裝成功！瀏覽器右上角擴充功能清單即可看到 **DiDiGo StreamRecorder** 圖示，建議點擊「圖釘」固定於工具列。

---

## 💡 使用教學

### 情境 1：直接錄製當前正在觀看的直播
1. 前往任意公開直播頁面。
2. 點擊工具列上的 **DiDiGo 圖示** 開啟主面板。
3. 系統會自動列出嗅探到的 M3U8 / FLV / DASH 串流卡片：
   - 點擊 **「🚀 下載此串流」**：開啟獨立下載工作台（支援 LL-HLS 與自動分段）。
   - 或點擊 **「🎥 錄製畫面 (CaptureStream)」**：直接對網頁播放器畫面進行即時錄影。

### 情境 2：設定主播頻道無人值守追蹤
1. 開啟 DiDiGo 面板，切換至 **「🎯 自訂多個追蹤頁」** 分頁。
2. 點擊 **「➕ 加入目前瀏覽的網頁」** 或手動貼上直播頻道網址。
3. 設定自動分段大小（如 `500` MB）與錄製時長上限。
4. 只要瀏覽器主程序保持開啟，DiDiGo 每 5 分鐘便會自動巡檢；開播時立即自動建立下載工作台執行錄製。

### 情境 3：啟用老闆鍵與遠端推播
- **老闆鍵**：在下載工作台按下快捷鍵 `Alt + B`，介面立即切換為試算表報表樣式；再按一次即可切回。
- **Webhook 設定**：在主面板「設定」區塊填入 Discord 或 Telegram Webhook URL，開播與存檔時即可在手機接收即時推播。

---

## 📁 檔案結構說明 (標準版擴充功能核心)

```text
DiDiGo/
├── manifest.json              # Chrome MV3 擴充功能設定清單
├── background.js              # 背景 Service Worker (封包嗅探、巡檢排程、白名單過濾)
├── content.js                 # Content Script (分頁通訊與安全校驗)
├── inject.js                  # 網頁 MAIN 執行環境腳本 (防抖狀態機、DOM 監測)
├── popup.html / popup.js      # 擴充功能主控制面板、追蹤設定與存檔庫
├── downloader.html / .js      # 獨立 M3U8 / LL-HLS 切片下載工作台與 fMP4 封裝
├── i18n.js                    # 多國語系支援模組
├── mp4merge.js                # 瀏覽器端 MP4 初始化檔頭與分段封裝處理
├── partner.js                 # 贊助與推廣支援模組 (合規混淆防護)
├── _locales/                  # 7 國語系設定檔 (zh_TW, en, ja, de, ru, es, fr)
├── icons/                     # 擴充功能各尺寸 Logo 圖示
├── PRIVACY.md                 # 隱私權政策與資料安全聲明
└── LICENSE                    # MIT 開源授權條款
```

---

## 🔒 隱私與安全性聲明 (Privacy & Compliance)

- **無資料蒐集**：本擴充功能不蒐集、不上傳任何使用者的瀏覽歷史、私人 Cookie 或身分識別資訊。
- **純本機執行**：所有串流解析、切片下載與分段封裝皆在使用者本機瀏覽器內完成。
- **遵循安全規範**：完全符合 Chrome Web Store 開發者計畫政策，不含外部動態執行代碼 (`unsafe-eval`)。
- **技術學習與合理備份**：本工具僅供公開技術學習、網路串流除錯與個人合理備份之用；請勿用於侵犯版權或繞過 DRM 加密保護之用途。

---

## 📄 授權條款 (License)

本專案採用 [MIT License](LICENSE) 條款開放原始碼。
