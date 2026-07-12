<p align="right">
  <a href="README.md">🇨🇳 简体中文</a> | <a href="README_tw.md">🇭🇰 繁體中文</a> | <a href="README_en.md">🇺🇸 English</a> | <b>🇪🇸 Español</b> | <a href="README_ja.md">🇯🇵 日本語</a> | <a href="README_ko.md">🇰🇷 한국어</a> | <a href="README_fr.md">🇫🇷 Français</a> | <a href="README_de.md">🇩🇪 Deutsch</a> | <a href="README_ru.md">🇷🇺 Русский</a> | <a href="README_ar.md">🇸🇦 العربية</a> | 🌐 <a href="https://translate.google.com" target="_blank">More</a>
</p>

<p align="center">
  <img src="logo.png" width="220" alt="App Icon">
</p>

<h1 align="center">🌐 Proyecto Nexus Forum 💬</h1>

<p align="center" style="color: gray; font-size: 16px;">
  Un sistema de foro multiplataforma moderno, de alto rendimiento y sincronización en tiempo real.
</p>

---

## 📱 Soporte Multiplataforma
*   **Móvil**: iOS 16 ~ iOS 27, Android 12 ~ Android 18
*   **Escritorio**: Windows 10 / 11 / 12, macOS (Apple & Intel, mín 10.15), Linux
*   **Sistemas Heredados**: Cliente independiente compatible con Windows 7 / 8 / 8.1.

---

## 🔐 Características Principales
1.  **🔄 Sincronización en Tiempo Real**: Sincronización en la nube para publicaciones, notificaciones y perfiles entre todos los dispositivos.
2.  **🛡️ Autenticación Segura de Doble Etapa**: Verificación mediante contraseña combinada con un código dinámico de 6 dígitos enviado por correo electrónico.
3.  **📲 Inicio de Sesión por QR en 60 Segundos**: Escanee el código QR desde la app móvil para iniciar sesión de forma segura en la computadora sin contraseñas.

---

## 🛠️ Stack Tecnológico
*   **UI Frontend Multiplataforma**: Google Flutter (Lenguaje Dart)
*   **Servidor de Autenticación en la Nube**: Node.js (Express + Token Seguro JWT)
*   **Caché de Alta Velocidad**: Redis (Para la gestión del ciclo de vida del código de correo de 5 min y código QR dinámico de 60s)

---

## 📂 Estructura de Directorios Multiplataforma Estandarizada
Este proyecto utiliza una estructura Monorepo para gestionar de forma centralizada los activos de diseño, el cliente y el código del servidor en la nube dentro de un único repositorio:

```text
nexus_forum_project/         # 📦 Directorio Raíz del Proyecto
├── ui_design/               # 🎨 Activos de Diseño de Interfaz Independientes
│   ├── phone_tablet/        # 📱 Diseños, recortes y prototipos de diseño para móviles (Teléfono/Tableta)
│   └── desktop/             # 💻 Diseños de pantalla grande para escritorio (Windows/Mac/Linux)
│
├── forum_client/            # 📱💻 Cliente Multiplataforma Flutter (Compilación nativa pura, SIN edición Web)
│   ├── lib/
│   │   ├── config.dart      # ⚙️ Configuración Global (Configuración de IP de LAN y puerto)
│   │   ├── main.dart        # 🚀 Detección de dispositivos, punto de entrada para flujos de registro/inicio de sesión
│   │   ├── desktop_view.dart# 💻 Exclusivo de Escritorio: Alternancia de un toque entre [Código QR] y [Formulario]
│   │   └── mobile_view.dart # 📱 Exclusivo de Móviles: Inicio de sesión de doble etapa, [Escanear] desbloqueado SOLO tras loguearse
│   └── pubspec.yaml         # 📦 Dependencias del Cliente (qr_flutter, mobile_scanner, etc.)
│
└── forum_server/            # 🖥️ Servidor en la Nube de Autenticación Integrada Node.js
    ├── server.js            # 🚀 Servicios Backend Centrales (Verificación de correo, intercepción de doble etapa, ciclo QR de 60s)
    └── package.json         # 📦 Dependencias del Servidor (express, bcryptjs, nodemailer, jwt)
```
