<p align="right">
  <a href="README.md">🇨🇳 简体中文</a> | <a href="README_tw.md">🇭🇰 繁體中文</a> | <a href="README_en.md">🇺🇸 English</a> | <a href="README_es.md">🇪🇸 Español</a> | <a href="README_ja.md">🇯🇵 日本語</a> | <a href="README_ko.md">🇰🇷 한국어</a> | <b>🇫🇷 Français</b> | <a href="README_de.md">🇩🇪 Deutsch</a> | <a href="README_ru.md">🇷🇺 Русский</a> | <a href="README_ar.md">🇸🇦 العربية</a> | 🌐 <a href="https://translate.google.com" target="_blank">More</a>
</p>

<p align="center">
  <img src="logo.png" width="220" alt="App Icon">
</p>

<h1 align="center">🌐 Projet Nexus Forum 💬</h1>

<p align="center" style="color: gray; font-size: 16px;">
  Un système de forum moderne, performant et multiplateforme avec synchronisation instantanée.
</p>

---

## 📱 Support Multiplateforme
*   **Mobile**: iOS 16 ~ iOS 27, Android 12 ~ Android 18
*   **Bureau**: Windows 10 / 11 / 12, macOS (Apple & Intel, min 10.15), Linux
*   **Versions Obsolètes**: Client compatible indépendant pour Windows 7 / 8 / 8.1.

---

## 🔐 Fonctionnalités Clés
1.  **🔄 Synchronisation Instantanée**: Cloud sync en temps réel pour les messages et notifications entre tous vos appareils.
2.  **🛡️ Authentication Sécurisée en Deux Étapes**: Protection par mot de passe couplée à un code de validation dynamique à 6 chiffres envoyé par e-mail.
3.  **📲 Connexion par Code QR en 60s**: Scannez le code QR sur l'écran du PC avec votre téléphone pour vous connecter sans mot de passe.

---

## 🛠️ Stack Technique
*   **UI Frontend Multiplateforme**: Google Flutter (Langage Dart)
*   **Serveur d'Authentification Cloud**: Node.js (Express + Jeton Sécurisé JWT)
*   **Cache Haute Vitesse**: Redis (Pour la gestion du cycle de vie du code e-mail de 5 min et du code QR dynamique de 60s)

---

## 📂 Structure de Répertoire Multiplateforme Standardisée
Ce projet utilise une structure Monorepo pour centraliser la gestion des actifs de conception, du client et du code du serveur cloud au sein d'un seul dépôt :

```text
nexus_forum_project/         # 📦 Répertoire Racine du Projet
├── ui_design/               # 🎨 Actifs de Conception d'Interface Indépendants
│   ├── phone_tablet/        # 📱 Maquettes de conception, découpes et prototypes de mise en page pour mobiles (Téléphone/Tablette)
│   └── desktop/             # 💻 Maquettes de conception grand écran pour bureau (Windows/Mac/Linux)
│
├── forum_client/            # 📱💻 Client Multiplateforme Flutter (Compilation native pure, SANS édition Web)
│   ├── lib/
│   │   ├── config.dart      # ⚙️ Configuration Globale (Configuration de l'IP LAN et du port)
│   │   ├── main.dart        # 🚀 Détection d'appareil, point d'entrée pour les flux d'inscription/connexion
│   │   ├── desktop_view.dart# 💻 Exclusif Bureau: Bascule en un clic entre [Code QR] et [Connexion Formulaire]
│   │   └── mobile_view.dart # 📱 Exclusif Mobile: Connexion en deux étapes, [Scanner] déverrouillé UNIQUEMENT après connexion
│   └── pubspec.yaml         # 📦 Dépendances du Client (qr_flutter, mobile_scanner, etc.)
│
└── forum_server/            # 🖥️ Serveur Cloud d'Authentification Intégré Node.js
    ├── server.js            # 🚀 Services Backend Centraux (Vérification d'e-mail, interception en deux étapes, cycle QR de 60s)
    └── package.json         # 📦 Dépendances du Serveur (express, bcryptjs, nodemailer, jwt)
```
