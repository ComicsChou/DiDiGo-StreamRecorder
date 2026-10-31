# 🎬 DiDiGo StreamRecorder — Édition Standard (Extension de Navigateur)

<p align="center">
  <img src="icons/icon128.png" width="96" height="96" alt="DiDiGo StreamRecorder Logo" />
</p>

<p align="center">
  <b>Extension légère d'interception et d'enregistrement automatisé de flux en direct, sans logiciel tiers</b><br>
  Conçue pour les navigateurs Chromium (Google Chrome, Brave, Microsoft Edge)
</p>

<p align="center">
  <a href="README_STANDARD.md">繁體中文</a> | 
  <a href="README_STANDARD_EN.md">English</a> | 
  <a href="README_STANDARD_JA.md">日本語</a> | 
  <a href="README_STANDARD_DE.md">Deutsch</a> | 
  <a href="README_STANDARD_RU.md">Русский</a> | 
  <a href="README_STANDARD_ES.md">Español</a> | 
  <a href="README_STANDARD_FR.md"><b>Français</b></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-1.4.2-brightgreen.svg" alt="Version 1.4.2" />
  <img src="https://img.shields.io/badge/Manifest-V3-blue.svg" alt="Manifest V3" />
  <img src="https://img.shields.io/badge/Platform-Chrome%20%7C%20Brave%20%7C%20Edge-brightgreen.svg" alt="Platform" />
  <img src="https://img.shields.io/badge/Languages-7%20Languages-yellow.svg" alt="7 Languages" />
  <img src="https://img.shields.io/badge/License-MIT-purple.svg" alt="License MIT" />
</p>

---

## 📌 Qu'est-ce que l'Édition Standard ?

**DiDiGo StreamRecorder Édition Standard** est une extension purement basée sur les spécifications **Manifest V3**. Sans installer Node.js, Python ou d'exécutables externes, vous bénéficiez immédiatement de :

- **Interception de flux en temps réel** : Détecte automatiquement les flux M3U8, Low-Latency LL-HLS (`#EXT-X-PART`), fMP4, DASH et FLV (LIVE).
- **Surveillance autonome** : Analyse légère toutes les 5 minutes et lancement automatique de l'onglet de téléchargement au début du direct.
- **Empaquetage direct dans le navigateur** : Assemble les segments au format fMP4 et découpe les fichiers par Mo ou Go en toute sécurité.
- **Mode Furtif & Alertes** : Camouflage en feuille de calcul Google Sheets (`Alt+B`), coupure automatique du son et notifications Discord/Telegram.

> 💡 **Remarque** : Pour les enregistrements lourds ou la fusion audio/vidéo avec FFmpeg local, consultez le [README.md](README.md) principal.

---

## ✨ Points Clés

1. **⚡ Prise en charge de LL-HLS (`#EXT-X-PART`)** : Analyse des micro-segments et exclusion automatique des publicités initiales.
2. **📺 Sélection Dynamique de Résolution** : Détection automatique des qualités réelles depuis la Master Playlist (1080p, 720p, etc.).
3. **🎯 Surveillance Multi-Canaux** : Gestion par motifs (`chaine*`), intervalle de 5 minutes et verrouillage contre les doublons.
4. **📦 Découpage Automatique & Enregistrement Silencieux** : Sauvegarde par seuils (ex. 500 Mo) avec en-têtes fMP4 garantissant la lisibilité de chaque fichier.
5. **🕵️ Mode Anti-Patron (`Alt + B`)** : Déguise instantanément l'onglet de téléchargement en rapport financier Google Sheets.
6. **🧩 Packs de Règles Externes (`.json`)** : Mise à jour des domaines CDN et sélecteurs DOM sans réinstaller l'extension.

---

## 🚀 Installation & Utilisation

1. Téléchargez ou clonez le dépôt.
2. Rendez-vous sur `chrome://extensions/` (ou `brave://extensions/`) dans votre navigateur.
3. Activez le **Mode développeur** en haut à droite.
4. Cliquez sur **Charger l'extension non empaquetée** et sélectionnez le dossier du projet.
5. Épinglez l'icône DiDiGo et lancez vos enregistrements en un clic !

---

## 🔒 Confidentialité & Licence

- **Aucune collecte de données** : Ni historique, ni cookies, ni identifiants ne sont collectés.
- **Avertissement légal** : Destiné à l'étude technique et à la sauvegarde personnelle de flux ouverts. Ne contourne pas les DRM.
- **Licence** : Sous licence [MIT License](LICENSE).
