<p align="right">
  <a href="README.md">🇨🇳 简体中文</a> | <a href="README_tw.md">🇭🇰 繁體中文</a> | <b>🇺🇸 English</b> | <a href="README_es.md">🇪🇸 Español</a> | <a href="README_ja.md">🇯🇵 日本語</a> | <a href="README_fr.md">🇫🇷 Français</a> | <a href="README_de.md">🇩🇪 Deutsch</a> | <a href="README_ru.md">🇷🇺 Русский</a> | <a href="README_ar.md">🇸🇦 العربية</a> | 🌐 <a href="https://google.com" target="_blank">More</a>
</p>

<p align="center">
  <img src="logo.png" width="220" alt="App Icon">
</p>

<h1 align="center">🌐 Nexus Forum Project 💬</h1>

<p align="center" style="color: gray; font-size: 16px;">
  A high-performance, multi-platform forum system for everyone with seamless sync.
</p>

---

## 📱 Multi-Platform Support
Built on a modern cross-platform UI architecture to deliver a smooth experience across mainstream and legacy devices:
*   **Mobile (Phone/Tablet)**: iOS 16 ~ iOS 27 (fully future-ready), Android 12 ~ Android 18
*   **Modern Desktop**: Windows 10 / 11 / 12, macOS (Apple Silicon & Intel, min 10.15 ~ max 27), Linux
*   **Legacy Desktop Channel**: Independent backward-compatible client for users running Windows 7 / 8 / 8.1.

---

## 🔐 Core Features

### 1. 🔄 Seamless Multi-Device Sync
*   Real-time cloud sync for posts, replies, notifications, and profiles across mobile, tablet, and desktop devices.

### 2. 🛡️ Dual-Stage Secure Authentication
*   **Multi-Credential Login**: Fast authentication via username or email.
*   **Two-Step Identity Verification**: Auto-sends a 6-digit dynamic code to the verified email upon correct password entry to prevent account theft.
*   **Standardized Registration**: Secure signup flows including username availability checks and email verification.

### 3. 📲 60-Second Cross-Device QR Login
*   **Display Only (Desktop)**: Windows, Mac, and Linux login screens generate secure 60s dynamic UUID QR codes.
*   **Scan Only (Mobile/Tablet)**: iOS and Android apps utilize native cameras to scan and authorize desktop login instantly without password entry.

---

## 🛠️ Tech Stack
*   **Frontend Cross-Platform UI**: Google Flutter (Dart)
*   **Cloud Authentication Server**: Node.js (Express + JWT)
*   **High-Speed Cache**: Redis (for 5-min email code and 60s QR code lifecycle management)
