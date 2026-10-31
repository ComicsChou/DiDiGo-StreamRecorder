# 🎬 DiDiGo StreamRecorder — ブラウザ拡張機能 標準版 (Standard Edition)

<p align="center">
  <img src="icons/icon128.png" width="96" height="96" alt="DiDiGo StreamRecorder Logo" />
</p>

<p align="center">
  <b>追加ソフト不要ですぐに使える、最新ストリーム検出＆無人自動録画拡張機能</b><br>
  Chromium 系ブラウザ専用設計（Google Chrome、Brave、Microsoft Edge）
</p>

<p align="center">
  <a href="README_STANDARD.md">繁體中文</a> | 
  <a href="README_STANDARD_EN.md">English</a> | 
  <a href="README_STANDARD_JA.md"><b>日本語</b></a> | 
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

## 📌 標準版（Standard Edition）とは？

**DiDiGo StreamRecorder 標準版** は、最新の **Chrome Manifest V3** 仕様に準拠した純ブラウザ完結型の拡張機能です。Node.js、Python、外部バイナリを PC にインストールすることなく、以下の機能が即座に利用可能です：

- **リアルタイムストリーム検出**：M3U8、低遅延 LL-HLS (`#EXT-X-PART`)、fMP4、DASH、FLV (LIVE) を自動インターセプト。
- **無人自動巡回モニタリング**：お気に入りチャンネルを登録すると、5分間隔で省電力巡回。配信開始時に自動でバックグラウンド作業タブを立ち上げ録画開始。
- **ブラウザ内デマックス＆自動分割保存**：ブラウザ内部で切片を fMP4 に自動パッケージングし、MB/GB 単位で安全に分割ダウンロード。
- **高度なプライバシー＆通知**：ワンタッチで Google スプレッドシートに偽装できるボス判定モード (`Alt+B`)、巡回タブ自動ミュート、Discord / Telegram 通知に対応。

> 💡 **備考**：長時間の複数ストリーム同時録画や、ローカル FFmpeg による音声・映像トラックの自動無損失結合、4x4 タイムラインプレビュー生成が必要な場合は、フル版の [README.md](README.md) をご覧ください。標準版拡張機能は単体で 100% 動作します。

---

## ✨ 主な機能と特徴

### 1. ⚡ 最新の低遅延 LL-HLS (`#EXT-X-PART`) 対応
- **マイクロセグメント解析**：`#EXT-X-PART` タグおよび `#EXT-X-MAP` 初期化ヘッダー (`init.mp4`) を正確に組み立てて保存。
- **期限切れパラメータの自動クリーンアップ**：M3U8 ポーリングURLに含まれるタイムアウト原因となる不要なパラメータを自動除去。
- **オープニング広告の自動スキップ**：広告セグメントを検出し、本編ストリームが開始するまで待機して録画を開始。

### 2. 📺 画質の動的アダプテーション（解像度セレクター）
- 配信の Master Playlist から利用可能な解像度（1080p、720p、480p 等）を動的に自動取得。
- ポップアップ上に解像度ボタンを動的生成し、「🌟 最高画質自動優先」とワンクリック切り替えをサポート。

### 3. 🎯 複数ターゲット無人追跡（5分ごとの省電力巡回）
- ワイルドカード（例：`example.com/channel*`）による柔軟なチャンネル管理。
- **5分間隔のスロットリング** と **重複起動防止ロック機構** により、CPU やメモリの過負荷を防止。

### 4. 📦 自動サイズ分割＆サイレント保存
- MB または GB 単位での分割しきい値設定（例：200 MB、500 MB、1 GB ごと。0 に設定した場合は単一ファイル）。
- 各セグメントに独立した初期化ヘッダーを付与するため、途中で録画を終了しても既存ファイルは正常に再生可能。
- Chrome Downloads API を利用し、保存ダイアログの確認なしでダウンロードフォルダに自動保存。

### 5. 🕵️ ボス判定偽装＆遠隔通知
- **🕵️ ボス判定モード (`Alt + B`)**：ダウンロード作業画面を一瞬で本物そっくりの **Google スプレッドシート / クラウド費用分析表** に偽装。録画は裏でそのまま継続。
- **🔇 巡回タブの自動ミュート**：深夜のバックグラウンド確認時に音が突然鳴るのを防ぐため、自動で消音。
- **📨 Discord / Telegram 通知**：Webhook を登録しておけば、配信開始や録画完了をスマホにリアルタイム通知。

### 6. 🧩 外部アドオンルールパック (`.json`)
- サイト側の仕様変更や CDN ドメイン変更時も、拡張機能を再インストールすることなく `.json` ファイルからルールを熱更新。
- **🎯 視覚的エレメントピッカー**：Web 画面上のオフライン告知や有料告知をクリックするだけで CSS セレクターを自動抽出。

---

## 🚀 インストール手順

### 推奨動作環境
- **ブラウザ**：Google Chrome、Brave、Microsoft Edge などの Chromium 系ブラウザ（バージョン 109 以降推奨）。
- **権限について**：`storage`, `downloads`, `alarms`, `webRequest` など最小限の権限のみ使用。外部へのデータ収集は一切行いません。

### 手動インストール（デベロッパーモード）
1. プロジェクトのリポジトリを取得：
   ```bash
   git clone https://github.com/ComicsChou/DiDiGo-StreamRecorder.git
   ```
2. ブラウザの拡張機能管理ページを開く：
   - **Chrome**: `chrome://extensions/`
   - **Brave**: `brave://extensions/`
   - **Edge**: `edge://extensions/`
3. 右上の **「デベロッパーモード」** をオンにする。
4. 左上の **「パッケージ化されていない拡張機能を読み込む」** をクリック。
5. 本プロジェクトのディレクトリ（`manifest.json` があるフォルダ）を選択。
6. インストール完了！ツールバーの DiDiGo アイコンをピン留めしてお使いください。

---

## 🔒 プライバシーとコンプライアンス

- **個人情報収集ゼロ**：閲覧履歴や Cookie、アカウント情報を収集または送信することはありません。
- **ローカル処理完結**：すべてのパケット解析、切片ダウンロード、ファイル変換はブラウザ内でローカルに実行されます。
- **ポリシー遵守**：Chrome ウェブストアの規約に準拠し、外部からのコード動的実行は行いません。
- **利用目的**：本ツールはストリーム技術の学習、デバッグ、個人的な正当バックアップを目的としています。DRM の回避や有料コンテンツの不正取得には対応していません。

---

## 📄 ライセンス

本プロジェクトは [MIT License](LICENSE) のもとで公開されています。
