<p align="right">
  <a href="README.md">🇨🇳 简体中文</a> | <a href="README_tw.md">🇭🇰 繁體中文</a> | <a href="README_en.md">🇺🇸 English</a> | <a href="README_es.md">🇪🇸 Español</a> | <b>🇯🇵 日本語</b> | <a href="README_ko.md">🇰🇷 한국어</a> | <a href="README_fr.md">🇫🇷 Français</a> | <a href="README_de.md">🇩🇪 Deutsch</a> | <a href="README_ru.md">🇷🇺 Русский</a> | <a href="README_ar.md">🇸🇦 العربية</a> | 🌐 <a href="https://translate.google.com" target="_blank">More</a>
</p>

<p align="center">
  <img src="logo.png" width="220" alt="App Icon">
</p>

<h1 align="center">🌐 Nexus Forum プロジェクト 💬</h1>

<p align="center" style="color: gray; font-size: 16px;">
  シームレスな多端末同期を特徴とする、高性能で最新のマルチプラットフォーム掲示板システム。
</p>

---

## 📱 マルチプラットフォーム対応
*   **モバイル**: iOS 16 ~ iOS 27、Android 12 ~ Android 18
*   **デスクトップ**: Windows 10 / 11 / 12、macOS (Apple & Intel, 10.15 以上)、Linux
*   **レガシーPC専用チャネル**: Windows 7 / 8 / 8.1 ユーザー向けの独立した互換クライアントを提供。

---

## 🔐 主な機能と特徴
1.  **🔄 リアルタイム同期**: スマートフォン、タブレット、PC間で投稿、通知、プロフィールをクラウド経由で即座に同期。
2.  **🛡️ 2段階の安全認証**: ユーザー名/メールアドレスによるログインと、メールで送信される6桁の動的検証コードによる本人確認。
3.  **📲 60秒QRコードかんたんログイン**: PC画面に生成されたQRコードをスマホアプリでスキャンするだけで、パスワード不要でログイン可能。

---

## 🛠️ 技術スタック
*   **クロスプラットフォームUI**: Google Flutter (Dart 言語)
*   **クラウド認証サーバー**: Node.js (Express + JWT セキュリティトークン)
*   **高速キャッシュ**: Redis (5分間のメール検証コードおよび60秒間の動的QRコードのライフサイクル管理用)

---

## 📂 標準化されたマルチプラットフォーム・ディレクトリ構成
本プロジェクトは、単一のリポジトリ内でデザイン資産、クライアント、クラウドサーバーコードを一元管理する Monorepo 構成を採用しています。

```text
nexus_forum_project/         # 📦 プロジェクトルートディレクトリ
├── ui_design/               # 🎨 独立したUIデザイン資産
│   ├── phone_tablet/        # 📱 モバイル（スマホ/タブレット）デザイン案、スライス、レイアウトプロトタイプ
│   └── desktop/             # 💻 デスクトップ（Windows/Mac/Linux）大画面デザイン案
│
├── forum_client/            # 📱💻 Flutter マルチプラットフォームクライアント (純粋なネイティブコンパイル、Web版なし)
│   ├── lib/
│   │   ├── config.dart      # ⚙️ グローバル設定 (LAN内IPおよびポート設定)
│   │   ├── main.dart        # 🚀 端末検出、新規登録/ログインフローの総合エントリーポイント
│   │   ├── desktop_view.dart# 💻 デスクトップ専用: [QRコード] と [フォームログイン] をワンタップで切り替え可能
│   │   └── mobile_view.dart # 📱 モバイル専用: 2段階ログイン、ログイン後にのみ [スキャン機能] を解放
│   └── pubspec.yaml         # 📦 クライアント依存関係 (qr_flutter, mobile_scanner など)
│
└── forum_server/            # 🖥️ Node.js 総合認証クラウドサーバー
    ├── server.js            # 🚀 バックエンドコアサービス (メール検証、2段階認証インターセプト、60秒QRライフサイクル)
    └── package.json         # 📦 サーバー依存関係 (express, bcryptjs, nodemailer, jwt)
```
