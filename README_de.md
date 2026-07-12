<p align="right">
  <a href="README.md">🇨🇳 简体中文</a> | <a href="README_tw.md">🇭🇰 繁體中文</a> | <a href="README_en.md">🇺🇸 English</a> | <a href="README_es.md">🇪🇸 Español</a> | <a href="README_ja.md">🇯🇵 日本語</a> | <a href="README_ko.md">🇰🇷 한국어</a> | <a href="README_fr.md">🇫🇷 Français</a> | <b>🇩🇪 Deutsch</b> | <a href="README_ru.md">🇷🇺 Русский</a> | <a href="README_ar.md">🇸🇦 العربية</a> | 🌐 <a href="https://google.com" target="_blank">More</a>
</p>

<p align="center">
  <img src="logo.png" width="220" alt="App Icon">
</p>

<h1 align="center">🌐 Nexus Forum Projekt 💬</h1>

<p align="center" style="color: gray; font-size: 16px;">
  Ein leistungsstarkes, modernes Multi-Plattform-Forum-System mit nahtloser Echtzeitsynchronisation.
</p>

---

## 📱 Plattform-Unterstützung
*   **Mobil**: iOS 16 ~ iOS 27, Android 12 ~ Android 18
*   **Desktop**: Windows 10 / 11 / 12, macOS (Apple & Intel, mind. 10.15), Linux
*   **Legacy PC Channel**: Unabhängiger kompatibler Client für Windows 7 / 8 / 8.1.

---

## 🔐 Kernfunktionen
1.  **🔄 Echtzeitsynchronisation**: Cloud-Synchronisation für Beiträge und Benachrichtigungen zwischen Smartphones, Tablets und PCs.
2.  **🛡️ Sichere Zwei-Faktor-Authentifizierung**: Passwortprüfung in Kombination mit einem 6-stelligen dynamischen Bestätigungscode per E-Mail.
3.  **📲 60-Sekunden QR-Code-Login**: QR-Code mit der mobilen App scannen, um sich sofort passwortlos auf dem PC anzumelden.

---

## 🛠️ Technologie-Stack
*   **Multi-Plattform Frontend UI**: Google Flutter (Programmiersprache Dart)
*   **Cloud-Authentifizierungsserver**: Node.js (Express + Sicheres JWT-Token)
*   **Hochgeschwindigkeitscache**: Redis (Zur Verwaltung des Lebenszyklus von 5-Minuten-E-Mail-Codes und dynamischen 60-Sekunden-QR-Codes)

---

## 📂 Standardisierte Multi-Plattform-Verzeichnisstruktur
Dieses Projekt verwendet eine Monorepo-Struktur, um Design-Assets, Client- und Cloud-Server-Code zentral in einem einzigen Repository zu verwalten:

```text
nexus_forum_project/         # 📦 Projekt-Wurzelverzeichnis
├── ui_design/               # 🎨 Unabhängige UI-Design-Assets
│   ├── phone_tablet/        # 📱 Design-Entwürfe, Slices und Layout-Prototypen für Mobilgeräte (Smartphone/Tablet)
│   └── desktop/             # 💻 Großbild-Design-Entwürfe für Desktop (Windows/Mac/Linux)
│
├── forum_client/            # 📱💻 Flutter Multi-Plattform-Client (Reine native Kompilierung, KEINE Web-Version)
│   ├── lib/
│   │   ├── config.dart      # ⚙️ Globale Konfiguration (LAN-IP- und Port-Setup)
│   │   ├── main.dart        # 🚀 Geräteerkennung, Haupteinstiegspunkt für Registrierungs- und Login-Flows
│   │   ├── desktop_view.dart# 💻 Exklusiv für Desktop: Ein-Klick-Wechsel zwischen [QR-Code] & [Formular-Login]
│   │   └── mobile_view.dart # 📱 Exklusiv für Mobilgeräte: Zweistufiger Login, [Scannen] erst NACH dem Login freigeschaltet
│   └── pubspec.yaml         # 📦 Client-Abhängigkeiten (qr_flutter, mobile_scanner usw.)
│
└── forum_server/            # 🖥️ Integrierter Node.js-Authentifizierungs-Cloud-Server
    ├── server.js            # 🚀 Kern-Backend-Dienste (E-Mail-Verifizierung, zweistufiges Abfangen, 60s QR-Lebenszyklus)
    └── package.json         # 📦 Server-Abhängigkeiten (express, bcryptjs, nodemailer, jwt)
```
