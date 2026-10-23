## 📖 Introduction & Modular Editions

**DiDiGo StreamRecorder** is a general-purpose browser extension (Manifest V3) and local recording toolkit for modern HLS, LL-HLS (`#EXT-X-PART`), and fMP4 live streams.

| Edition / Module | Target Use Case | Core Capabilities |
| :--- | :--- | :--- |
| **1. 🌐 Standard Browser Extension** | Lightweight, zero-setup stream sniffing & recording inside the browser | M3U8/LL-HLS/DASH detection, `CaptureStream`/`MSE` player capture, **🕵️ Boss/Stealth Mode (`Alt+B`)**, **🔇 Auto-Mute Probed Tabs**, **📨 Discord/Telegram Webhook notifications**, and custom MB/GB auto-split |
| **2. 🧩 External Add-on Rule Pack (`.json`)** | Hot-updatable site adapter rules without reinstalling the extension | Dynamically imports custom CDN proxy domain whitelists (`proxyDomains`), anti-hotlink headers (`headerRules`), and site-specific DOM selectors (`siteRules`), plus a **🎯 Visual Element Picker** (no DevTools needed) |
| **3. 🚀 Desktop Pro Engine (`DiDiGo管理中心.exe`)** | Heavy multi-stream background recording & instant dual-track muxing | Native Windows GUI launcher with system tray support, one-click portable FFmpeg auto-setup, **🖼️ automatic 4x4 preview contact sheet (`_preview.jpg`)**, **💾 Live Disk Space Guard**, and `一鍵合併影音.exe` |

---

## ✨ Key Features

### 1. ⚡ Support for LL-HLS (`#EXT-X-PART`) Streams
- **Micro-segment parsing**: Reliably captures low-latency HLS chunks including `#EXT-X-PART` tags.
- **Clean dynamic polling**: Strips obsolete `HLS_msn` and `HLS_part` blocking parameters to prevent CDN timeouts.
- **Automatic pre-roll ad filtering**: Detects and skips advert tags (`#EXT-X-MOUFLON-ADVERT`) before transitioning to the live stream.

### 2. 📺 Dynamic Stream Quality Adaptation & Resolution Selection
- **Dynamic adaptation**: Quality chips and selectors adapt dynamically to the stream's actual Master Playlist resolutions (e.g. 1080p, 720p, 480p, or custom aspect ratios) rather than enforcing static hardcoded values.
- **Smart multi-variant derivation**: Automatically derives available stream variants if only a single sub-playlist is exposed, defaulting to Best Available Quality.
- **Dynamic quick-switch chips**: Renders clickable chips matching live stream resolutions, with smooth recording transition upon selection.

### 3. 🎯 Multi-Target Tracking & Lightweight 5-Minute Polling (Unattended)
- **Multi-rule management**: Add target URLs or keyword patterns (wildcards supported, e.g. `domain.com/user*`).
- **5-Minute inspection throttle**: Inspects targets once every 5 minutes instead of hammering servers continuously, drastically cutting CPU and RAM usage.
- **Strict anti-recursion**: Enforces a strict one-window lock per page to prevent tab loops.

### 4. 🧠 Smart Screen Monitoring (Live-Start & Private-Stop)
- **Auto-Watch mode**: Starts recording when playback begins; automatically finalizes and downloads if the stream drops or disconnects with multi-second debounce.
- **Private Show avoidance**: Detects private performances (Private, Group, VIP, Ticket shows) and terminates recording with explicit reason logging.

### 5. 📦 Custom File Size Auto-Split (Auto-Split by Size)
- **Configurable thresholds**: Specify split sizes in `MB` or `GB` (e.g. 200 MB, 500 MB, 1 GB; `0` for single file).
- **Standalone compatibility**: Injects `#EXT-X-MAP` initialization headers (`init.mp4`) into the head of each new fMP4 part for compatibility with standard media players.

### 6. 🔕 Silent Auto-Download
- **Zero popups**: Integrates directly with the browser's downloads API (`saveAs: false`) to bypass annoying Save-As dialogs.
- **Normalized filenames**: Organizes files systematically as `[StreamerName]_partX_YYYYMMDD_HHmmss.mp4`.

---

## 🚀 Installation

DiDiGo StreamRecorder is designed for Chromium-based browsers (Brave, Google Chrome, Microsoft Edge). Mozilla Firefox support is currently **experimental / unverified**. For traceable test records, see [`TEST_RECORDS.md`](TEST_RECORDS.md).

### 🦁 Chromium (Brave / Chrome / Edge)
1. Clone or download the repository:
   ```bash
   git clone https://github.com/your-username/DiDiGo.git
   ```
2. Navigate to extensions management:
   - **Brave**: `brave://extensions/`
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
3. Toggle on **Developer mode** in the upper right.
4. Click **Load unpacked** and select the `DiDiGo` directory (containing `manifest.json`).

### 🦊 Mozilla Firefox (Experimental / Unverified)
1. Open Firefox and go to `about:debugging#/runtime/this-firefox`.
2. Click **Load Temporary Add-on...**.
3. Select `manifest.json` from the `DiDiGo` folder.
*Note: Due to Manifest V3 service worker, `declarativeNetRequest`, and download API variances, Firefox support has not undergone full end-to-end verification and remains experimental.*

---

## 💡 Quick Start

### Mode A: Record Current Active Tab
1. Open any video or live stream page.
2. Click the **DiDiGo StreamRecorder** icon in the toolbar.
3. Click **Start Screen Recording** or enable **Auto Detect (Record on Live, Stop on Offline)**.
4. Video will be recorded and saved silently into your default `Downloads/DiDiGo` folder.

### Mode B: Unattended Multi-Target Tracking
1. Open the popup and navigate to the **Target Tracker** tab.
2. Click **Add Current Page to Tracker** or add a custom rule.
3. Choose your inspection interval (default: Every 5 minutes).
4. As long as your browser is open, DiDiGo will automatically record and split files whenever the host goes live!

### Mode C: Local FFmpeg Companion App (`DiDiGo管理中心.exe`) & Add-on Packs
1. Double-click **`DiDiGo管理中心.exe`** (or run from `dist/DiDiGo_Desktop_Pro/`) to start the local companion server on `127.0.0.1:3000` with system tray support and automatic portable FFmpeg setup (`app/bin/ffmpeg.exe`).
2. Click **"🖥️ Send to DiDiGo App (FFmpeg)"** in the extension popup for multi-stream recording and dual-track muxing, or use **`一鍵合併影音.exe`** to merge separate video/audio files.
3. Under the **Library** tab, you can also import external **Add-on Rule Packs (`.json`)** (e.g. `addons/live-sites-addon-pack.json`) to dynamically update CDN domain whitelists and DOM status selectors without reinstalling the extension.

---

## ⚠️ Disclaimer

- This extension is intended strictly for personal technical analysis, network debugging, and personal offline backup.
- Users must abide by their local copyright laws and third-party Terms of Service.
- The developers assume no liability for misuse of this tool.

---

## 📄 License

Released under the [MIT License](LICENSE).
