<p align="right">
  <a href="README.md">🇨🇳 简体中文</a> | <b>🇭🇰 繁體中文</b> | <a href="README_en.md">🇺🇸 English</a> | <a href="README_es.md">🇪🇸 Español</a> | <a href="README_ja.md">🇯🇵 日本語</a> | <a href="README_fr.md">🇫🇷 Français</a> | <a href="README_de.md">🇩🇪 Deutsch</a> | <a href="README_ru.md">🇷🇺 Русский</a> | <a href="README_ar.md">🇸🇦 العربية</a> | 🌐 <a href="https://google.com" target="_blank">More</a>
</p>

<p align="center">
  <img src="logo.png" width="220" alt="App Icon">
</p>

<h1 align="center">🌐 互聯綜合論壇 (Nexus Forum Project) 💬</h1>

<p align="center" style="color: gray; font-size: 16px;">
  一款面向廣大網民的、高性能、全平台無縫同步的現代化通用論壇系統。
</p>

---

## 📱 全平台設備支援
本項目採用現代跨平台 UI 架構，確保用戶在任何主流和老舊設備上都能獲得絲滑的使用體驗：
*   **移動端（手機/平板）**：iOS 16 ~ iOS 27（全面適配未來系統）、Android 12 ~ Android 18
*   **現代桌面端**：Windows 10 / 11 / 12、macOS（完美支援 M系列及 Intel 晶片，最低 10.15 ~ 最高 27）、Linux
*   **老舊電腦專屬通道**：針對部分用戶仍在使用 Windows 7 / 8 / 8.1 的現狀，提供獨立的低版本相容客戶端，確保全設備覆蓋。

---

## 🔐 核心功能特性

### 1. 🔄 帳號與數據全端即時同步
*   用戶不論在手機、平板還是電腦上登錄，發帖、回帖、消息通知以及個人資料全部實現雲端多端即時同步。

### 2. 🛡️ 雙階段安全身份驗證（確保本人操作）
*   **多憑證登錄**：支援用戶名、郵箱快速登錄。
*   **本人二次驗證**：密碼正確後，系統會自動向綁定郵箱發送 6 位數動態驗證碼，雙重保障用戶的帳號安全，防止被盜。
*   **規範化註冊**：提供用戶名重名檢查、郵箱防刷驗證、雙重密碼確認等標準的現代化安全註冊流程。

### 3. 📲 60秒跨端二維碼免密快捷登錄
*   **只顯不掃（電腦端）**：Windows、Mac、Linux 電腦登錄頁即時生成 60 秒高安全動態二維碼。
*   **只掃不顯（手機/平板）**：手機或平板端論壇 App 原生調取攝像頭，一鍵掃描電腦屏幕，實現秒級免密授權登錄。

---

## 🛠️ 項目技術棧
*   **前端全端 UI**：Google Flutter (Dart 語言)
*   **雲端綜合認證服務器**：Node.js (Express + JWT 安全令牌)
*   **數據高速緩存**：Redis（用於 5 分鐘郵件驗證碼及 60 秒動態二維碼的生命週期管理）

---

## 📂 項目規範化多端目錄架構
本項目採用 Monorepo（單倉多包）結構，在同一個倉庫內統一管理設計資產、客戶端及雲端服務端代碼：

```text
nexus_forum_project/         # 📦 項目總根目錄
├── ui_design/               # 🎨 獨立UI設計資產
│   ├── phone_tablet/        # 📱 移動端（手機/平板）設計稿、切圖及布局原型
│   └── desktop/             # 💻 桌面端（Windows/Mac/Linux）大屏版設計稿
│
├── forum_client/            # 📱💻 Flutter 多端通用客戶端（純原生編譯，無網頁端）
│   ├── lib/
│   │   ├── config.dart      # ⚙️ 全局配置文件（局域網 IP 與端口配置）
│   │   ├── main.dart        # 🚀 跨端設備檢測、注冊登錄流綜合主入口
│   │   ├── desktop_view.dart# 💻 桌面端專用：支持【顯示二維碼】與【表單登錄】一鍵切換
│   │   └── mobile_view.dart # 📱 移動端專用：包含兩階段登錄，且【登錄後方可喚起掃一掃】
│   └── pubspec.yaml         # 📦 客戶端依賴配置文件（qr_flutter, mobile_scanner等）
│
└── forum_server/            # 🖥️ Node.js 綜合認證雲服務器
    ├── server.js            # 🚀 後端核心服務（包含郵箱驗證、雙階登錄攔截、60秒二維碼生命周期）
    └── package.json         # 📦 服務端依賴配置文件（express, bcryptjs, nodemailer, jwt）
```
