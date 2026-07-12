<p align="right">
  <a href="README.md">🇨🇳 简体中文</a> | 
  <a href="README_tw.md">🇭🇰 繁體中文</a> | 
  <a href="README_en.md">🇺🇸 English</a> | 
  <a href="README_es.md">🇪🇸 Español</a> | 
  <a href="README_ja.md">🇯🇵 日本語</a> | 
  <a href="README_fr.md">🇫🇷 Français</a> | 
  <a href="README_de.md">🇩🇪 Deutsch</a> | 
  <a href="README_ru.md">🇷🇺 Русский</a> | 
  <a href="README_ar.md">🇸🇦 العربية</a> |
  <b>🇰🇷 한국어</b> |
  🌐 <a href="https://google.com" target="_blank">More </a>
</p>

<p align="center">
  <img src="logo.png" width="220" alt="App Icon">
</p>

<h1 align="center">🌐 넥서스 통합 포럼 (Nexus Forum Project) 💬</h1>

<p align="center" style="color: gray; font-size: 16px;">
  광범위한 인터넷 이용자를 위한 고성능, 전 플랫폼 무시무시한 동기화를 지원하는 현대적인 범용 포럼 시스템입니다.
</p>

---

## 📱 전 플랫폼 디바이스 지원
본 프로젝트는 현대적인 크로스 플랫폼 UI 아키텍처를 채택하여, 이용자가 어떠한 메인스트림 및 구형 기기에서도 부드러운 사용 경험을 얻을 수 있도록 보장합니다:
*   **모바일단 (스마트폰/태블릿)**: iOS 16 ~ iOS 27 (미래 시스템 전면 호환), Android 12 ~ Android 18
*   **현대적인 데스크톱단**: Windows 10 / 11 / 12, macOS (Apple Silicon 및 Intel 칩 완벽 지원, 최소 10.15 ~ 최고 27), Linux
*   **구형 컴퓨터 전용 채널**: 일부 이용자가 여전히 Windows 7 / 8 / 8.1을 사용 중인 현황을 고려하여, 독립적인 하위 버전 호환 클라이언트를 제공함으로써 모든 기기를 빠짐없이 커버합니다.

---

## 🔐 핵심 기능 및 특성

### 1. 🔄 계정 및 데이터 전단 실시간 동기화
*   이용자가 스마트폰, 태블릿, 컴퓨터 중 어떠한 기기로 로그인하든 상관없이 게시글 작성, 댓글, 알림 및 개인 정보가 모두 클라우드를 통해 밀리초(ms) 단위로 멀티 디바이스 실시간 동기화됩니다.

### 2. 🛡️ 2단계 보안 신원 인증 (본인 조작 확인)
*   **다중 자격 증명 로그인**: 사용자 이름(ID), 이메일을 통한 빠른 로그인을 지원합니다.
*   **본인 2차 인증**: 비밀번호가 일치하면 시스템이 연동된 이메일로 6자리 동적 인증 코드를 자동 발송하여, 이용자의 계정 보안을 이중으로 보호하고 계정 도용을 방지합니다.
*   **표준화된 회원가입**: 사용자 이름 중복 검사, 이메일 어뷰징 방지 인증, 비밀번호 이중 확인 등 현대적이고 표준화된 보안 회원가입 프로세스를 제공합니다.

### 3. 📲 60초 크로스 디바이스 QR 코드 비밀번호 없는 빠른 로그인
*   **화면 표시 전용 (데스크톱단)**: Windows, Mac, Linux 컴퓨터 로그인 페이지에서 60초 동안 유효한 높은 보안성의 동적 UUID QR 코드를 실시간으로 생성합니다.
*   **스캔 전용 (모바일/태블릿단)**: 스마트폰 또는 태블릿단 포럼 앱에서 네이티브 카메라를 호출하여 컴퓨터 화면을 원클릭 스캔함으로써, 지연 없이 비밀번호가 필요 없는 데스크톱 로그인 승인을 구현합니다.

---

## 🛠️ 프로젝트 기술 스택
*   **크로스플랫폼 프론트엔드 UI**: Google Flutter (Dart 언어)
*   **클라우드 통합 인증 서버**: Node.js (Express + JWT 보안 토큰)
*   **고속 데이터 캐시**: Redis (5분 이메일 인증 코드 및 60초 동적 QR 코드 생명주기 관리용)

---

## 📂 프로젝트 표준화된 멀티 플랫폼 디렉토리 구조
본 프로젝트는 단일 저장소(Monorepo) 구조를 채택하여 디자인 자산, 클라이언트 및 클라우드 서버 코드를 하나의 리포지토리 내에서 통합 관리합니다:

```text
nexus_forum_project/         # 📦 프로젝트 최상위 루트 디렉토리
├── ui_design/               # 🎨 독립 UI 디자인 자산
│   ├── phone_tablet/        # 📱 모바일(스마트폰/태블릿) 디자인 시안, 슬라이스 및 레이아웃 프로토타입
│   └── desktop/             # 💻 데스크톱(Windows/Mac/Linux) 대화면 디자인 시안
│
├── forum_client/            # 📱💻 Flutter 멀티 플랫폼 클라이언트 (순수 네이티브 컴파일, 웹버전 없음)
│   ├── lib/
│   │   ├── config.dart      # ⚙️ 글로벌 설정 파일 (로컬 LAN IP 및 포트 설정)
│   │   ├── main.dart        # 🚀 크로스 디바이스 감지, 회원가입/로그인 프로세스 통합 메인 엔트리
│   │   ├── desktop_view.dart# 💻 데스크톱 전용: [QR 코드]와 [양식 로그인]의 원클릭 스위칭 지원
│   │   └── mobile_view.dart # 📱 모바일 전용: 2단계 로그인 포함, 로그인 후에만 [스캔 기능] 활성화
│   └── pubspec.yaml         # 📦 클라이언트 종속성 설정 파일 (qr_flutter, mobile_scanner 등)
│
└── forum_server/            # 🖥️ Node.js 통합 인증 클라우드 서버
    ├── server.js            # 🚀 백엔드 핵심 서비스 (이메일 인증, 2단계 인증 인터셉트, 60초 QR 생명주기)
    └── package.json         # 📦 서버 종속성 설정 파일 (express, bcryptjs, nodemailer, jwt)
```
