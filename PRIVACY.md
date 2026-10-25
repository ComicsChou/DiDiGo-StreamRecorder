# Privacy Policy (隱私權政策 / プライバシーポリシー / Datenschutzerklärung)

**Language Navigation / 語言切換 / 言語切り替え / Sprachauswahl**:
- [繁體中文 (Traditional Chinese)](#繁體中文-traditional-chinese)
- [English](#english)
- [日本語 (Japanese)](#日本語-japanese)
- [Deutsch (German)](#deutsch-german)

---

## 繁體中文 (Traditional Chinese)

**生效日期**：2026 年 10 月 22 日  
**專案名稱**：DiDiGo StreamRecorder

DiDiGo 非常重視您的隱私權。本政策旨在向您說明本工具如何處理資料、網路請求流向，以及本機與第三方網站之間的互動邊界。

### 1. 資料處理範圍與外部請求區分 (Data Scope and Network Requests)

DiDiGo 是一款於**使用者本機端 (Client-side) 運作**的開源工具。為確保資訊透明，我們明確區分**「不傳送至 DiDiGo 自有伺服器」**與**「對使用者指定之直播站台／CDN 發出請求」**兩種行為：

#### A. 絕不傳送至 DiDiGo 自有或第三方分析伺服器
- **無自有遠端伺服器**：本專案不設有任何開發者自有雲端伺服器、資料庫或遠端遙測端點。
- **不蒐集個人識別資訊 (PII)**：我們不會蒐集、上傳或儲存您的姓名、電子郵件、帳號密碼、付款資訊或一般無關之瀏覽紀錄。
- **無追蹤與廣告 SDK**：本專案不包含任何第三方分析工具（如 Google Analytics）、行為追蹤器或廣告 SDK，亦絕不將任何使用者資料販售或分享予第三方。

#### B. 向使用者選擇之直播站台／CDN 發出的必要網路請求
當您主動在直播網頁使用本擴充功能、開啟「下載工作台」、啟用「定時追蹤巡檢」，或使用「本機 FFmpeg 管理中心」進行錄製時，為取得影音串流資料，**您的瀏覽器或本機 FFmpeg 程序會直接向您所選擇的目標直播網站及其影音內容傳遞網路 (CDN) 發出標準 HTTP/HTTPS 請求**：
- **可能傳送給目標站台／CDN 的資料**：
  1. **串流與播放清單網址 (M3U8 / MPD / FLV / 媒體切片 URL)**：用於向目標 CDN 請求播放清單與影音分段資料（該網址可能包含目標站台原本核發於網址列中的動態連線參數或時效性 Token）。
  2. **必要的來源標頭 (Referer / Origin / User-Agent)**：為通過目標站台 CDN 的防盜鏈檢查（避免 HTTP 403 拒絕存取），擴充功能或本機 FFmpeg 會向該串流所屬之站台／CDN 附帶對應的 `Referer`、`Origin` 與標準瀏覽器 `User-Agent` 標頭。
  3. **定時追蹤頁面請求**：若您主動啟用「自訂多個追蹤頁」自動巡檢功能，瀏覽器會依您設定的週期（預設每 5 分鐘）向您指定的目標直播網址發起連線以檢查是否開播。
- 上述請求均為**您的電腦直接與目標直播站台／CDN 通訊**，不會經過任何 DiDiGo 伺服器中轉。目標站台／CDN 對該等請求的處理，受各該目標網站自身的隱私權政策與服務條款規範。

#### C. 本機端讀取與儲存的資料項目
1. **當前瀏覽分頁媒體網址與中繼資訊**：在您瀏覽網頁時，於本機記憶體中解析 M3U8/MPD/FLV 串流資訊、畫質解析度、編碼與分段序號，供介面選擇與本地封裝。
2. **自訂偏好與追蹤規則**：於瀏覽器本機 `chrome.storage.local` 儲存您的分段大小、儲存子資料夾、優先畫質及自訂追蹤清單。
3. **本機下載歷史記錄**：於本機記錄已完成存檔的檔名、資料夾、主播名稱、時間戳記與大小（最多保留 100 筆），僅供擴充功能彈出視窗檢視，您可隨時一鍵清空。

### 2. 瀏覽器權限使用說明 (Permissions)

DiDiGo 遵循最小權限原則，僅請求實現串流偵測、本機下載與排程巡檢所必需的權限：
- `webRequest`：於瀏覽器本機偵測當前分頁發出的 HLS/M3U8、DASH 與 FLV 播放清單請求網址。
- `declarativeNetRequest`：在向支援的直播 CDN 拉取串流切片時，於本機瀏覽器附加對應站台的 `Referer` / `Origin` / `User-Agent` 標頭，以避免 403 阻擋。
- `downloads`：將錄製或下載完成的影音檔案儲存至使用者本機的「下載 (Downloads)」資料夾。
- `storage`：在本機儲存分段大小、追蹤規則、下載目錄、畫質偏好與本機下載歷史。
- `tabs` / `activeTab`：識別當前播放分頁、更新擴充功能徽章計數，以及開啟與管理下載工作台分頁。
- `alarms`：用於背景定時巡檢排程（預設每 5 分鐘一次），檢查使用者自訂的追蹤規則。
- `notifications`：於追蹤目標開始錄製或完成時顯示本機桌面通知。
- `host_permissions` (`<all_urls>`)：因各直播站台與影音 CDN 網域經常動態變更，需此權限以在使用者瀏覽的頁面上偵測串流並向目標 CDN 下載切片。

### 3. 本機管理中心通訊與安全授權說明 (Local Companion App)

- DiDiGo 提供選用的本機 FFmpeg 管理中心（`app/server.js` 或 `DiDiGoHub.exe`），僅綁定並監聽於本機迴路位址 `127.0.0.1:3000`，不對外網開放。
- **資料流向**：
  1. 當使用者在擴充功能點擊「傳送至 DiDiGo App」時，擴充功能會向 `http://127.0.0.1:3000` 傳送任務名稱、串流網址與來源網站 Origin。
  2. 本機管理中心會呼叫您電腦上的 FFmpeg 程序，由 FFmpeg 直接向該串流所屬之直播站台／CDN 拉取影音資料並寫入本機 `recordings/` 目錄。
  3. 管理中心內建日誌去敏機制（自動隱去網址查詢參數中的敏感 Token），避免在控制台介面或終端機完整暴露。
- **授權鎖定機制 (`allowedExtensionIds`)**：
  - 管理中心支援以 Chrome Extension ID 白名單限制可呼叫 API 的擴充功能來源。
  - 首次透過擴充功能傳送任務時會自動嘗試配對鎖定，使用者亦可於 `http://127.0.0.1:3000` 管理介面一鍵鎖定或手動設定。
  - 若 `allowedExtensionIds` 保持空白（未鎖定寬鬆模式），本機瀏覽器內安裝的任何其他擴充功能皆可能呼叫本機 API；管理介面會明確標示「尚未鎖定」警告並引導使用者完成綁定。

### 4. 資料安全與移除 (Data Security & Removal)

所有設定、下載歷史與暫存緩衝均保存在您的個人電腦本機。當您從瀏覽器移除 DiDiGo 擴充功能時，`chrome.storage` 中的本機設定與歷史紀錄將由瀏覽器自動清除；已儲存至本機硬碟的影片檔案則由您自行管理。

### 5. 政策變更與聯絡方式 (Contact)

若本政策有任何更新，將同步發布於本專案之開源倉庫。如對本隱私權政策有任何疑問，請透過專案 GitHub Issues 與我們聯繫。

---

## English

**Effective Date**: October 22, 2026  
**Project Name**: DiDiGo StreamRecorder

DiDiGo deeply respects your privacy. This policy outlines how this tool processes data, network request behaviors, and the boundaries of interaction between your local machine and third-party websites.

### 1. Data Processing Scope & External Request Boundaries

DiDiGo is an open-source tool operating **strictly client-side on the user's machine**. To ensure total transparency, we distinguish between **"No data sent to DiDiGo servers"** and **"Direct requests sent to user-selected live stream sites/CDNs"**:

#### A. Never Sent to DiDiGo Servers or Third-Party Analytics
- **No Remote Backend**: This project has no developer-owned cloud servers, databases, or remote telemetry endpoints.
- **No PII Collected**: We never collect, transmit, or store personally identifiable information (PII) such as your name, email, credentials, payment information, or unrelated web browsing history.
- **No Trackers or Ad SDKs**: This project contains no third-party tracking scripts (such as Google Analytics), telemetry, or advertisement SDKs. We will never sell or share user data.

#### B. Direct Network Requests to User-Selected Stream Sites & CDNs
When you actively use this extension on live streaming websites, open the "Stream Downloader Workbench", enable "Automatic Periodic Polling", or record via the "Local FFmpeg Hub", **your browser or local FFmpeg process issues direct standard HTTP/HTTPS requests to the target streaming site and its Content Delivery Network (CDN)**:
- **Data potentially transmitted to the target site/CDN**:
  1. **Stream & Playlist URLs (M3U8 / MPD / FLV / Media Segments)**: Used to fetch playlist files and video segments from the host CDN (these URLs may include dynamic session tokens issued by the host site).
  2. **Essential Request Headers (Referer / Origin / User-Agent)**: To pass anti-hotlink validations of target CDNs and prevent HTTP 403 errors, the extension or local FFmpeg attaches the corresponding `Referer`, `Origin`, and browser `User-Agent` headers.
  3. **Periodic Polling Requests**: If you enable automatic live tracking rules, your browser periodically connects to your chosen stream URLs (default: every 5 minutes) to detect if the broadcaster has started streaming.
- All requests above are **direct communication between your computer and the target streaming service/CDN**, without routing through any DiDiGo proxy. Handling of such requests is subject to each respective website's privacy policy and terms of service.

#### C. Data Processed and Stored Locally
1. **Current Tab Media URLs & Metadata**: In-memory inspection of M3U8/MPD/FLV stream information, resolutions, codecs, and sequence numbers for user selection and local muxing.
2. **User Preferences & Tracking Rules**: Saved locally in browser `chrome.storage.local`, including chunk split size, destination folder, preferred quality, and tracking lists.
3. **Local Download History**: Logs completed filenames, destination folders, streamer names, timestamps, and file sizes (up to 100 entries) in local storage. You can clear this history anytime with one click.

### 2. Browser Extension Permissions

DiDiGo adheres to the principle of least privilege, requesting only permissions necessary for stream sniffing, local downloading, and scheduled tracking:
- `webRequest`: Sniffing HLS, DASH, and FLV playlist requests from the active tab.
- `declarativeNetRequest`: Attaching necessary `Referer`, `Origin`, and `User-Agent` headers when requesting stream segments to prevent HTTP 403 errors.
- `downloads`: Saving completed video recordings and merged files to your local "Downloads" directory.
- `storage`: Storing settings, split thresholds, tracking rules, and download history locally.
- `tabs` / `activeTab`: Identifying the current active media tab, badge updates, and opening the workbench tab.
- `alarms`: Scheduling periodic background checks for user-defined tracking rules.
- `notifications`: Showing local desktop alerts when tracked targets start or finish recording.
- `host_permissions` (`<all_urls>`): Needed because streaming media CDNs frequently rotate domain names dynamically.

### 3. Local Desktop Companion App Security (`DiDiGoHub.exe` / `app/server.js`)

- The optional local companion app binds exclusively to the local loopback interface `127.0.0.1:3000` and does not accept remote network connections.
- **Data Flow**:
  1. Clicking "Send to DiDiGo App" sends the task title, stream URL, and origin to `http://127.0.0.1:3000`.
  2. The local server spawns the system FFmpeg process, which downloads the stream directly from the CDN to your local `recordings/` folder.
  3. Server logs redact sensitive query parameters and tokens to prevent accidental disclosure in the console.
- **Extension ID Authorization (`allowedExtensionIds`)**:
  - The local server allows whitelisting specific Chrome Extension IDs.
  - Initial connection can automatically pair and lock down the authorized ID.
  - If left blank (unlocked mode), an explicit warning is shown on the dashboard guiding you to pair your extension.

### 4. Data Security and Removal

All preferences, download histories, and temporary segment buffers are stored locally on your machine. When you uninstall DiDiGo from your browser, all extension storage is purged automatically by the browser. You maintain full ownership and control over video files saved to your disk.

### 5. Policy Updates and Contact

Any updates to this policy will be committed directly to this open-source repository. For inquiries, please open an issue on our GitHub repository.

---

## 日本語 (Japanese)

**発効日**: 2026 年 10 月 22 日  
**プロジェクト名**: DiDiGo StreamRecorder

DiDiGo は利用者のプライバシーを尊重します。本ポリシーは、本ツールにおけるデータの取り扱い、通信経路、および外部サービスとの相互作用について説明するものです。

### 1. データ処理の範囲と外部通信の明確化

DiDiGo は**ユーザーのローカル環境（クライアント側）でのみ動作する**オープンソースツールです。

#### A. 開発者サーバーへの送信は一切行いません
- **外部サーバーの非保持**: 開発者独自のクラウドサーバー、データベース、リモートテレメトリは存在しません。
- **個人情報の非収集**: 氏名、メールアドレス、パスワード、決済情報、無関係な閲覧履歴などを収集または保存することはありません。
- **解析・広告 SDK の非搭載**: Google Analytics や第三者広告トラッカー等は一切含まれておらず、ユーザー情報を第三者に販売・提供することもありません。

#### B. ユーザーが指定した配信サイト／CDN への直接通信
本拡張機能やローカル FFmpeg を用いて配信を録画・ダウンロードする際、**お使いのブラウザまたはローカル FFmpeg は、対象の配信プラットフォームおよびその動画配信網 (CDN) に対して直接 HTTP/HTTPS リクエストを送信します**：
- **送信される情報**:
  1. **ストリーム URL（M3U8 / MPD / FLV / セグメント URL）**: 配信データを取得するために送信されます（配信元が発行した一時的なアクセストークン等が含まれる場合があります）。
  2. **必要なリクエストヘッダー（Referer / Origin / User-Agent）**: 配信元 CDN の不正アクセス防止（HTTP 403 エラー）を回避するため、適切なヘッダーを付与します。
  3. **自動巡回チェック**: 追跡ルールを有効化した場合、指定した間隔（デフォルト 5 分）で対象ページにアクセスし開播状態を確認します。
- これらはすべて**お使いの PC と配信元サーバー間の直接通信**であり、DiDiGo サーバーを経由することはありません。

#### C. ローカル保存されるデータ
- ブラウザの `chrome.storage.local` に保存される設定（保存先フォルダ名、分割サイズ、画質設定、追跡ルール、ローカル履歴など）。
- いつでも拡張機能ポップアップからワンクリックで履歴を消去できます。

### 2. 使用するブラウザ権限

- `webRequest` / `declarativeNetRequest`: ストリーム検出および 403 防止ヘッダー付与。
- `downloads`: 録画・ダウンロードした動画ファイルをローカルの「ダウンロード」フォルダに保存。
- `storage`: 設定や録画ルールのローカル保存。
- `tabs` / `activeTab`: 再生中タブの検出とワークベンチタブの管理。
- `alarms`: 開播自動チェックの定期実行。
- `notifications`: 録画開始・完了のデスクトップ通知。
- `host_permissions` (`<all_urls>`): 頻繁にドメインが切り替わる配信 CDN に対応するため。

### 3. ローカル管理サーバー（`DiDiGoHub.exe` / `app/server.js`）

- ローカルホスト `127.0.0.1:3000` にのみバインドし、外部ネットワークには公開されません。
- Extension ID のホワイトリスト登録（ペアリング）に対応しており、不正な拡張機能からの API 呼び出しを遮断できます。

---

## Deutsch (German)

**Inkrafttreten**: 22. Oktober 2026  
**Projekt**: DiDiGo StreamRecorder

DiDiGo respektiert Ihre Privatsphäre vollumfänglich. Diese Richtlinie beschreibt die Verarbeitung von Daten und Netzwerkinteraktionen.

### 1. Datenverarbeitung und Netzwerkkommunikation

DiDiGo ist ein Open-Source-Werkzeug, das **ausschließlich lokal auf dem Computer des Nutzers** ausgeführt wird.

#### A. Keine Datenübertragung an DiDiGo-Server
- **Keine eigenen Server**: Es existieren keine Entwickler-Server, Datenbanken oder Telemetrie-Endpunkte.
- **Keine personenbezogenen Daten**: Es werden weder Namen, E-Mail-Adressen, Passwörter, Zahlungsdaten noch Surf-Chroniken erfasst.
- **Keine Tracker oder Werbe-SDKs**: Keine Analyse-Dienste (wie Google Analytics) und kein Verkauf von Nutzerdaten.

#### B. Direkte Anfragen an vom Nutzer ausgewählte Streaming-Dienste/CDNs
Wenn Sie Streams aufzeichnen oder herunterladen, **sendet Ihr Browser oder der lokale FFmpeg-Prozess direkte Anfragen an die ausgewählten Streaming-Websites und deren CDNs**:
- **Übermittelte Daten**:
  1. **Stream- und Playlist-URLs (M3U8 / MPD / FLV)** zum Laden der Videosegmente.
  2. **Notwendige HTTP-Header (Referer, Origin, User-Agent)** zur Vermeidung von 403-Zugriffsfehlern (Hotlink-Schutz).
  3. **Geplante Überprüfungen**, falls Sie die automatische Stream-Verfolgung aktivieren.
- Diese Kommunikation erfolgt **direkt zwischen Ihrem Rechner und den Ziel-Servern** ohne Zwischenschaltung von DiDiGo-Servern.

#### C. Lokale Speicherung
Alle Benutzereinstellungen (Speicherordner, Segmentgrößen, Verfolgungsregeln und Download-Verlauf) verbleiben ausschließlich im lokalen `chrome.storage.local` Ihres Browsers und können jederzeit mit einem Klick gelöscht werden.

### 2. Lokale Desktop-Anwendung (`DiDiGoHub.exe` / `app/server.js`)

- Bindet sich ausschließlich an die Loopback-Adresse `127.0.0.1:3000` und ist über externe Netzwerke nicht erreichbar.
- Unterstützt Whitelisting autorisierter Chrome-Erweiterungs-IDs zum Schutz vor unberechtigtem Zugriff.
