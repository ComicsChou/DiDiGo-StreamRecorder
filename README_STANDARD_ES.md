# 🎬 DiDiGo StreamRecorder — Edición Estándar (Extensión de Navegador)

<p align="center">
  <img src="icons/icon128.png" width="96" height="96" alt="DiDiGo StreamRecorder Logo" />
</p>

<p align="center">
  <b>Extensión ligera para detección y grabación desatendida de transmisiones en vivo sin software adicional</b><br>
  Diseñado para navegadores basados en Chromium (Google Chrome, Brave, Microsoft Edge)
</p>

<p align="center">
  <a href="README_STANDARD.md">繁體中文</a> | 
  <a href="README_STANDARD_EN.md">English</a> | 
  <a href="README_STANDARD_JA.md">日本語</a> | 
  <a href="README_STANDARD_DE.md">Deutsch</a> | 
  <a href="README_STANDARD_RU.md">Русский</a> | 
  <a href="README_STANDARD_ES.md"><b>Español</b></a> | 
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

## 📌 ¿Qué es la Edición Estándar?

**DiDiGo StreamRecorder Edición Estándar** es una extensión de navegador pura construida con el estándar **Manifest V3**. Sin necesidad de instalar Node.js, Python o ejecutables externos en su sistema operativo, puede realizar de inmediato:

- **Detección de flujos en tiempo real**: Intercepta automáticamente M3U8, Low-Latency LL-HLS (`#EXT-X-PART`), fMP4, DASH y FLV (LIVE).
- **Monitoreo programado desatendido**: Inspecciona canales cada 5 minutos en modo de bajo consumo e inicia automáticamente la grabación al comenzar la transmisión.
- **Empaquetado directo en el navegador**: Ensambla fragmentos en formato fMP4 y los divide de forma segura por MB o GB.
- **Modo Sigilo y Notificaciones**: Disfraz instantáneo a Hoja de cálculo de Google (`Alt+B`), silenciamiento automático y webhooks para Discord/Telegram.

> 💡 **Nota**: Para grabaciones masivas o fusión de pistas de audio y video con FFmpeg local, consulte el archivo principal [README.md](README.md).

---

## ✨ Características Principales

1. **⚡ Compatibilidad con LL-HLS (`#EXT-X-PART`)**: Procesamiento de microfragmentos y omisión automática de anuncios iniciales.
2. **📺 Selección Dinámica de Calidad**: Lee las resoluciones disponibles directamente desde el Master Playlist (1080p, 720p, etc.).
3. **🎯 Monitoreo de Múltiples Canales**: Soporta comodines (`canal*`) con intervalo de 5 minutos y bloqueo de pestañas duplicadas.
4. **📦 División Automática y Guardado Silencioso**: División por tamaño (p. ej. cada 500 MB) asegurando que cada segmento sea reproducible por separado.
5. **🕵️ Modo Antijefe (`Alt + B`)**: Camufla al instante la pestaña de descarga como una hoja de cálculo financiera de Google Sheets.
6. **🧩 Paquetes de Reglas Externos (`.json`)**: Actualización de dominios CDN y selectores sin necesidad de reinstalar la extensión.

---

## 🚀 Instalación Rápida

1. Clone o descargue este repositorio en su equipo.
2. Vaya a `chrome://extensions/` (o `brave://extensions/`) en su navegador.
3. Active el **Modo de desarrollador** en la esquina superior derecha.
4. Haga clic en **Cargar descomprimida** y seleccione la carpeta del proyecto.
5. ¡Listo! Fije el icono de DiDiGo y comience a grabar transmisiones en vivo.

---

## 🔒 Privacidad y Licencia

- **Cero recolección de datos**: No almacena ni envía historiales, cookies ni datos personales.
- **Aviso legal**: Destinado exclusivamente a estudio técnico y respaldo personal de transmisiones abiertas. No elude DRM.
- **Licencia**: Publicado bajo licencia [MIT License](LICENSE).
