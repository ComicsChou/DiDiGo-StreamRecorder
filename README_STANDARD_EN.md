# 🎬 DiDiGo StreamRecorder — Standard Browser Extension Edition

<p align="center">
  <img src="icons/icon128.png" width="96" height="96" alt="DiDiGo StreamRecorder Logo" />
</p>

<p align="center">
  <b>Zero-setup, lightweight modern stream sniffer & unattended live recording extension</b><br>
  Designed for Chromium browsers (Google Chrome, Brave, Microsoft Edge)
</p>

<p align="center">
  <a href="README_STANDARD.md">繁體中文</a> | 
  <a href="README_STANDARD_EN.md"><b>English</b></a> | 
  <a href="README_STANDARD_JA.md">日本語</a> | 
  <a href="README_STANDARD_DE.md">Deutsch</a> | 
  <a href="README_STANDARD_RU.md">Русский</a> | 
  <a href="README_STANDARD_ES.md">Español</a> | 
  <a href="README_STANDARD_FR.md">Français</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-1.4.2-brightgreen.svg" alt="Version 1.4.2" />
  <img src="https://img.shields.io/badge/Manifest-V3-blue.svg" alt="Manifest V3" />
  <img src="https://img.shields.io/badge/Platform-Chrome%20%7C%20Brave%20%7C%20Edge-brightgreen.svg" alt="Platform" />
  <img src="https://img.shields.io/badge/Languages-7%20Languages-yellow.svg" alt="7 Languages" />
  <img src="https://img.shields.io/badge/License-MIT-purple.svg" alt="License MIT" />
</p>

---

## 📌 What is the Standard Edition?

**DiDiGo StreamRecorder Standard Edition** is a pure browser extension built with modern **Manifest V3** standards. Without installing Node.js, Python, or external binaries on your operating system, you can immediately achieve:

- **Real-Time Stream Sniffing**: Automatically intercepts M3U8, Low-Latency LL-HLS (`#EXT-X-PART`), fMP4, DASH, and FLV (LIVE) streams.
- **Unattended Scheduled Polling**: Monitor live URLs with a 5-minute lightweight interval; launches a dedicated background downloader tab automatically upon broadcast start.
- **In-Browser Demuxing & Segment Packaging**: Muxes chunks directly into standard fMP4 inside the browser and auto-splits by MB/GB seamlessly.
- **Stealth & Notifications**: Includes one-click Boss Mode spreadsheet disguise (`Alt+B`), auto-mute during inspection, and Discord / Telegram webhook notifications.

> 💡 **Note**: For heavy multi-stream recording, automated local dual-track lossless muxing, or generating 4x4 preview contact sheets via local FFmpeg, refer to the full [README.md](README.md). The Standard Edition extension runs 100% standalone inside your browser.

---

## ✨ Key Features & Capabilities

### 1. ⚡ Modern LL-HLS (`#EXT-X-PART`) & Micro-segment Support
- **Micro-segment Assembly**: Intercepts and parses `#EXT-X-PART` tags along with `#EXT-X-MAP` initialization headers (`init.mp4`).
- **Obsolete Parameter Stripping**: Automatically cleans up expired `HLS_msn` and `HLS_part` blocking parameters to prevent CDN request timeouts.
- **Pre-roll Ad Filtering**: Automatically skips opening ad segments (e.g. `#EXT-X-MOUFLON-ADVERT`) and connects cleanly once the main live stream begins.

### 2. 📺 Dynamic Stream Quality Adaptation
- Dynamically parses available resolutions from the stream's Master Playlist (1080p, 720p, 480p, or custom aspect ratios).
- Renders dynamic quality buttons in the popup, defaulting to "🌟 Best Quality" with one-click instant switching.

### 3. 🎯 Multi-Target Unattended Monitoring (5-Minute Throttle)
- Supports wildcard URL matching (e.g., `example.com/channel*`) to manage multiple target channels.
- Enforces strict **5-minute throttling** and **one-window state locking** to eliminate CPU/RAM spikes caused by runaway tabs.

### 4. 📦 Auto-Split & Silent Save
- Custom split threshold by MB or GB (e.g., 200 MB, 500 MB, 1 GB per part; set to 0 for a single continuous file).
- Each fMP4 segment includes an independent initialization header, ensuring partial files are fully playable even if recording is interrupted.
- Writes silently into your default browser Downloads folder via the Chrome Downloads API without popup confirmation prompts.

### 5. 🕵️ Stealth & Productivity Tools
- **🕵️ Boss Key Disguise (`Alt + B`)**: Instantly transforms the downloader tab into a 1:1 authentic **Google Sheets / Excel Cloud Cost Report** with matched green icon and disguised page title, while background recording continues uninterrupted.
- **🔇 Auto-Mute Inspected Tabs**: Background probe tabs are muted by default to prevent unexpected noise during late-night monitoring.
- **📨 Remote Webhook Notifications**: Integrates with Discord and Telegram webhooks for real-time alerts when streams start or files are saved.

### 6. 🧩 External Add-on Rule Packs (`.json`)
- If target sites update their CDN structures or anti-hotlinking headers, update rules dynamically via `.json` files without reinstalling the extension.
- Built-in **🎯 Visual Element Picker**: Click directly on an offline or paid notice on any live page to compute CSS selectors automatically.

---

## 🚀 Installation Guide

### Recommended Environment
- **Browser**: Google Chrome, Brave, Microsoft Edge, or Chromium-based browsers (version 109+ recommended).
- **Permissions**: Requests minimal necessary permissions (`storage`, `downloads`, `alarms`, `webRequest`). Zero telemetry or data collection.

### Manual Installation (Developer Mode)
1. Clone or download this repository:
   ```bash
   git clone https://github.com/ComicsChou/DiDiGo-StreamRecorder.git
   ```
2. Navigate to your browser's extension management page:
   - **Chrome**: `chrome://extensions/`
   - **Brave**: `brave://extensions/`
   - **Edge**: `edge://extensions/`
3. Toggle on **Developer mode** in the top right corner.
4. Click **Load unpacked** in the top left corner.
5. Select the project directory containing `manifest.json`.
6. Installation complete! Click the DiDiGo icon in your extension bar and pin it for easy access.

---

## 💡 How to Use

### Scenario 1: Record Current Live Stream
1. Open any public live streaming page.
2. Click the **DiDiGo icon** in the browser toolbar.
3. Review detected M3U8 / FLV / DASH stream cards:
   - Click **"🚀 Download Stream"**: Launches the standalone downloader tab with LL-HLS and auto-split.
   - Or click **"🎥 Capture Stream"**: Directly captures the web video player DOM stream in real time.

### Scenario 2: Unattended Tracking for Favorite Channels
1. Open DiDiGo popup and switch to **"🎯 Multi-Target Tracker"**.
2. Click **"➕ Add Current Tab"** or paste the channel URL manually.
3. Configure auto-split size (e.g. `500` MB) and optional recording duration limits.
4. Keep browser running; DiDiGo inspects targets every 5 minutes and automatically launches downloader tabs when live.

### Scenario 3: Boss Mode & Remote Webhook Alerts
- **Boss Mode**: Press `Alt + B` inside the downloader tab to disguise it as a spreadsheet report; press again to toggle back.
- **Webhook Alerts**: Enter your Discord or Telegram Webhook URL in the settings panel to receive alerts on mobile devices.

---

## 🔒 Privacy & Compliance

- **Zero Data Collection**: DiDiGo does not collect, track, or transmit your browsing history, cookies, or personal identifiers.
- **Local Execution**: All stream parsing, segment fetching, and packaging occur entirely inside your local browser instance.
- **Policy Compliance**: Fully compliant with Chrome Web Store Developer Program policies; contains no remote executable code (`unsafe-eval`).
- **Legal & Ethical Usage**: Intended for public technical study, stream debugging, and personal fair-use archiving. Does not bypass DRM or paywalls.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
