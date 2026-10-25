# 🎬 DiDiGo StreamRecorder — Standard-Browser-Erweiterungsedition

<p align="center">
  <img src="icons/icon128.png" width="96" height="96" alt="DiDiGo StreamRecorder Logo" />
</p>

<p align="center">
  <b>Leichtgewichtige Streaming-Sniffer- und unbeaufsichtigte Live-Aufnahme-Erweiterung ohne zusätzliche Software</b><br>
  Entwickelt für Chromium-basierte Browser (Google Chrome, Brave, Microsoft Edge)
</p>

<p align="center">
  <a href="README_STANDARD.md">繁體中文</a> | 
  <a href="README_STANDARD_EN.md">English</a> | 
  <a href="README_STANDARD_JA.md">日本語</a> | 
  <a href="README_STANDARD_DE.md"><b>Deutsch</b></a> | 
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

## 📌 Was ist die Standard-Edition?

Die **DiDiGo StreamRecorder Standard-Edition** ist eine reine Browser-Erweiterung basierend auf dem modernen **Manifest V3**-Standard. Ohne die Installation von Node.js, Python oder externen Binärdateien können Sie sofort folgende Funktionen nutzen:

- **Echtzeit-Stream-Erkennung**: Automatisches Abfangen von M3U8, Low-Latency LL-HLS (`#EXT-X-PART`), fMP4, DASH und FLV (LIVE).
- **Unbeaufsichtigte Überwachung**: Zielkanäle eintragen; alle 5 Minuten ressourcenschonend prüfen und bei Sendebeginn automatisch im Hintergrund aufnehmen.
- **Direktes Demuxing im Browser**: Segmente werden lokal im Browser zu fMP4 zusammengefügt und nach MB/GB automatisch aufgeteilt.
- **Tarnung & Benachrichtigungen**: 1-Klick-Chef-Modus (`Alt+B`) zur Tarnung als Google Tabellenkalkulation, automatisches Stummschalten und Discord/Telegram-Webhooks.

> 💡 **Hinweis**: Für extrem lange Multi-Stream-Aufnahmen, automatische Audio/Video-Zusammenführung über FFmpeg oder 4x4-Vorschaubilder nutzen Sie bitte die Desktop-Version im Haupt-Repository ([README.md](README.md)).

---

## ✨ Wichtige Funktionen

1. **⚡ LL-HLS (`#EXT-X-PART`) & Mikro-Segment-Unterstützung**: Präzise Verarbeitung von Low-Latency-Streams und automatisches Ausfiltern von Werbesegmenten.
2. **📺 Dynamische Qualitätsauswahl**: Automatische Ermittlung der tatsächlichen Auflösungen (1080p, 720p usw.) aus der Master-Playlist.
3. **🎯 Multi-Kanal-Überwachung**: Verwaltung mit Platzhaltern (`channel*`), 5-Minuten-Drosselung und Tab-Sperre gegen Speicherüberlastung.
4. **📦 Automatische Teilung & Stilles Speichern**: Einstellbare Schwellenwerte (z. B. alle 500 MB) mit eigenem fMP4-Header für jedes Teilsegment.
5. **🕵️ Privatsphäre & Tarnung**: Boss-Taste (`Alt+B`) tarnt den Download-Tab sofort als Excel-/Sheets-Kostenanalyse.
6. **🧩 Externe Add-on-Regelpakete (`.json`)**: Schnelle Anpassung an geänderte Webseiten-Selektoren ohne Neuinstallation.

---

## 🚀 Installation & Nutzung

1. Repository klonen oder als ZIP herunterladen.
2. Im Browser `chrome://extensions/` (oder `brave://extensions/`) aufrufen.
3. **Entwicklermodus** oben rechts aktivieren.
4. Auf **Entpackte Erweiterung laden** klicken und den Projektordner auswählen.
5. Das DiDiGo-Symbol anheften und mit einem Klick auf Live-Streams aufnehmen!

---

## 🔒 Datenschutz & Lizenz

- **100% Lokal**: Keine Erfassung oder Übertragung von Verlauf, Cookies oder personenbezogenen Daten.
- **Rechtlicher Hinweis**: Ausschließlich für technische Lernzwecke und persönliche Backups unverschlüsselter Streams. Umgeht kein DRM.
- **Lizenz**: Lizenziert unter der [MIT License](LICENSE).
