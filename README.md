<p align="right">
  <b>🇨🇳 简体中文</b> | 
  <a href="README_tw.md">🇭🇰 繁體中文</a> | 
  <a href="README_en.md">🇺🇸 English</a> | 
  <a href="README_es.md">🇪🇸 Español</a> | 
  <a href="README_ja.md">🇯🇵 日本語</a> | 
  <a href="README_ko.md">🇰🇷 한국어</a> | 
  <a href="README_fr.md">🇫🇷 Français</a> | 
  <a href="README_de.md">🇩🇪 Deutsch</a> | 
  <a href="README_ru.md">🇷🇺 Русский</a> | 
  <a href="README_ar.md">🇸🇦 العربية</a> |
  🌐 <a href="https://google.com" target="_blank">More (全球语言翻译)</a>
</p>

<p align="center">
  <img src="logo.png" width="220" alt="App Icon">
</p>

<h1 align="center">🌐 互联综合论坛 (Nexus Forum Project) 💬</h1>

<p align="center" style="color: gray; font-size: 16px;">
  一款面向广大网民的、高性能、全平台无缝同步的现代化通用论坛系统。
</p>

---

## 📱 全平台设备支持
本项目采用现代跨平台 UI 架构，确保用户在任何主流和老旧设备上都能获得丝滑的使用体验：
*   **移动端（手机/平板）**：iOS 16 ~ iOS 27（全面适配未来系统）、Android 12 ~ Android 18
*   **现代桌面端**：Windows 10 / 11 / 12、macOS（完美支持 M系列及 Intel 芯片，最低 10.15 ~ 最高 27）、Linux
*   **老旧电脑专属通道**：针对部分用户仍在使用 Windows 7 / 8 / 8.1 的现状，提供独立的低版本兼容客户端，确保全设备覆盖。

---

## 🔐 核心功能特性

### 1. 🔄 账号与数据全端实时同步
*   用户不论在手机、平板还是电脑上登录，发帖、回帖、消息通知以及个人资料全部实现云端多端实时同步。

### 2. 🛡️ 双阶段安全身份验证（确保本人操作）
*   **多凭证登录**：支持用户名、邮箱快速登录。
*   **本人二次验证**：密码正确后，系统会自动向绑定邮箱发送 6 位数动态验证码，双重保障用户的账号安全，防止被盗。
*   **规范化注册**：提供用户名重名检查、邮箱防刷验证、双重密码确认等标准的现代化安全注册流程。

### 3. 📲 60秒跨端二维码免密快捷登录
*   **只显不扫（电脑端）**：Windows、Mac、Linux 电脑登录页实时生成 60 秒高安全动态二维码。
*   **只扫不显（手机/平板）**：手机或平板端论坛 App 原生调取摄像头，一键扫描电脑屏幕，实现秒级免密授权登录。

---

## 🛠️ 项目技术栈
*   **前端全端 UI**：Google Flutter (Dart 语言)
*   **云端综合认证服务器**：Node.js (Express + JWT 安全令牌)
*   **数据高速缓存**：Redis（用于 5 分钟邮件验证码及 60 秒动态二维码的生命周期管理）

---

## 📂 项目规范化多端目录架构
本项目采用 Monorepo（单仓多包）结构，在同一个仓库内统一管理设计资产、客户端及云端服务端代码：

```text
nexus_forum_project/         # 📦 项目总根目录
├── ui_design/               # 🎨 独立UI设计资产
│   ├── phone_tablet/        # 📱 移动端（手机/平板）设计稿、切图及布局原型
│   └── desktop/             # 💻 桌面端（Windows/Mac/Linux）大屏版设计稿
│
├── forum_client/            # 📱💻 Flutter 多端通用客户端（纯原生编译，无网页端）
│   ├── lib/
│   │   ├── config.dart      # ⚙️ 全局配置文件（局域网 IP 与端口配置）
│   │   ├── main.dart        # 🚀 跨端设备检测、注册登录流综合主入口
│   │   ├── desktop_view.dart# 💻 桌面端专用：支持【显示二维码】与【表单登录】一键切换
│   │   └── mobile_view.dart # 📱 移动端专用：包含两阶段登录，且【登录后方可唤起扫一扫】
│   └── pubspec.yaml         # 📦 客户端依赖配置文件（qr_flutter, mobile_scanner等）
│
└── forum_server/            # 🖥️ Node.js 综合认证云服务器
    ├── server.js            # 🚀 后端核心服务（包含邮箱验证、双阶登录拦截、60秒二维码生命周期）
    └── package.json         # 📦 服务端依赖配置文件（express, bcryptjs, nodemailer, jwt）
```
