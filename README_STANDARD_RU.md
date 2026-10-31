# 🎬 DiDiGo StreamRecorder — Стандартное издание расширения для браузера

<p align="center">
  <img src="icons/icon128.png" width="96" height="96" alt="DiDiGo StreamRecorder Logo" />
</p>

<p align="center">
  <b>Легковесное расширение для перехвата и автоматической записи прямых трансляций без сторонних программ</b><br>
  Создано для браузеров на базе Chromium (Google Chrome, Brave, Microsoft Edge)
</p>

<p align="center">
  <a href="README_STANDARD.md">繁體中文</a> | 
  <a href="README_STANDARD_EN.md">English</a> | 
  <a href="README_STANDARD_JA.md">日本語</a> | 
  <a href="README_STANDARD_DE.md">Deutsch</a> | 
  <a href="README_STANDARD_RU.md"><b>Русский</b></a> | 
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

## 📌 Что такое Стандартное издание (Standard Edition)?

**DiDiGo StreamRecorder Standard Edition** — это чисто браузерное расширение стандарта **Manifest V3**. Не требует установки Node.js, Python или FFmpeg на ваш ПК:

- **Перехват потоков в реальном времени**: Автоматически определяет M3U8, Low-Latency LL-HLS (`#EXT-X-PART`), fMP4, DASH и FLV (LIVE).
- **Автоматический мониторинг каналов**: Проверка статуса каждые 5 минут в энергосберегающем режиме с автозапуском записи при начале стрима.
- **Упаковка прямо в браузере**: Сборка фрагментов в формат fMP4 и автоматическое разделение на тома (по МБ / ГБ).
- **Режим маскировки и уведомления**: Мгновенная маскировка под Google Таблицы (`Alt+B`), авто-заглушение звука и уведомления в Discord/Telegram.

> 💡 **Примечание**: Для длительной записи нескольких потоков и склейки раздельных аудио/видео дорожек используйте десктопный движок из [README.md](README.md).

---

## ✨ Основные возможности

1. **⚡ Поддержка LL-HLS (`#EXT-X-PART`)**: Парсинг микрофрагментов и авто-пропуск вступительной рекламы.
2. **📺 Динамический выбор разрешения**: Определение доступных разрешений из Master Playlist (1080p, 720p и т. д.).
3. **🎯 Слежение за каналами без присутствия человека**: Экономичная проверка раз в 5 минут с защитой от дублирования вкладок.
4. **📦 Авто-разбивка на части**: Запись частями по 500 МБ или 1 ГБ с гарантией читаемости каждого отдельного сегмента.
5. **🕵️ Клавиша «Анти-босс» (`Alt + B`)**: Мгновенное превращение вкладки загрузки в отчет Excel / Google Таблицы.
6. **🧩 Внешние пакеты правил (`.json`)**: Обновление CDN и селекторов без переустановки расширения.

---

## 🚀 Установка

1. Склонируйте репозиторий или скачайте архив.
2. Откройте в браузере `chrome://extensions/` (или `brave://extensions/`).
3. Включите **«Режим разработчика»** в правом верхнем углу.
4. Нажмите **«Загрузить распакованное расширение»** и выберите папку проекта.
5. Готово! Закрепите значок DiDiGo и начните запись в один клик.

---

## 🔒 Конфиденциальность и Лицензия

- **Без сбора данных**: Не сохраняет и не передает историю или личные файлы.
- **Правовая информация**: Предназначено для изучения потоковых технологий и создания личных резервных копий. Не предназначено для обхода DRM.
- **Лицензия**: Распространяется под [MIT License](LICENSE).
