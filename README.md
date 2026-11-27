# 이광호 (Gwangho Lee)

**Backend Developer** · Infra & Systems · 경희대학교 컴퓨터공학부 · 제28대 컴퓨터공학부 학생회장

> **노력하면 안 되는 건 없다!**<br/>
> 사람과 일을 조율하고, 꾸준히 만들고, 먼저 나서서 함께 해내는 개발자 이광호입니다.

<a href="mailto:ghlee9883@gmail.com"><img src="https://img.shields.io/badge/Gmail-EA4335?style=flat-square&logo=gmail&logoColor=white"/></a>
<a href="https://app.notion.com/p/GwanghoLee-s-Portfolio-12da1ef891b380a99132e5c136c2ebd5"><img src="https://img.shields.io/badge/Portfolio-000000?style=flat-square&logo=notion&logoColor=white"/></a>

<br/>

## 💻 Projects

### 🔍 Glasspod — 컨테이너 안 앱의 실제 상태를 보고 쿠버네티스에 조치하는 개발 도구
`2026.11 ~ 진행 중` · **1인 (설계 · 전체 개발)** · `Node.js` `TypeScript` `WebSocket` `SSE` `Kubernetes` `Docker` `React`

- 앱에 넣는 **SDK**가 앱 상태를 모으고, 서버가 **쿠버네티스 Pod 상태와 합쳐 판단**한 뒤 재시작 · 격리 · 스케일 조치를 실행
- 이벤트 루프가 20초 막혀도 쿠버네티스는 재시작하지 않았지만, Glasspod는 **5초 만에** 막힘을 잡아냄
- `preStop` 적용으로 rollout restart 중 요청 실패 **60건 → 0건**, Pod 격리 조치 중 부하 실패 **0건**
- 감시 namespace로 한정한 **RBAC 최소 권한** · Pod Security Standards restricted · 테스트 **380개**
- 📦 [GitHub](https://github.com/gwangholee507/glasspod) · 📄 [상세](https://app.notion.com/p/Glasspod-412a1ef891b380c7a2d1fb456dfee6c6)

### ⚙️ Optimeter — C · C++ · Rust 컴파일러 최적화 레벨 비교 웹앱
`2026.08 ~ 진행 중 (v0.3.0)` · **1인 (기획 · 백엔드 · 프론트엔드)** · `Java` `Spring Boot` `React` `GitHub Actions`

- `-O0 ~ -O3` 레벨별 어셈블리 · 오브젝트 크기 · 컴파일/실행 시간을 나란히 비교, clang · GCC · rustc **5종 컴파일러** 지원
- 컴파일러가 남긴 최적화 기록(clang Rpass, GCC fopt-info)을 읽어 **"8행 함수 호출을 인라인했다"** 처럼 소스 줄과 함께 표시
- 레벨 병렬 컴파일로 비교 시간 **4.9초 → 1.3초**, 파이프 버퍼 교착 · DNS 리바인딩 문제 해결
- Ubuntu · macOS · Windows **3개 OS CI**, 테스트 **231개**, PR 29개
- 📦 [GitHub](https://github.com/gwangholee507/optimeter) · 📄 [상세](https://app.notion.com/p/Optimeter-40ca1ef891b380a6804ecec11a02c598)

### 🎙️ On-Device Speech Transcriber — 캡스톤디자인
`2026.09 ~ 진행 중` · **3인 팀 (앱 서버 · 웹앱 단독 담당)** · `Node.js` `TypeScript` `Express` `PostgreSQL` `SSE` `React` `Rubik Pi`

- Rubik Pi 3 보드의 NPU에서 Whisper 한국어 모델을 돌려, **인터넷 없이** 실시간 자막과 기록을 보여 주는 음성 기록기
- **SSE** 실시간 자막 스트림 + `Last-Event-ID` 이어 받기, STT를 어댑터 뒤에 두고 mock으로 전체 흐름부터 완성
- 서버 재시작 후 정상 복귀 시간 **14초 → 0~1초**, 확정 문장 **로그 = 화면 = DB 16/16 일치**
- 📦 [GitHub](https://github.com/khu-cse-capstone-26h2-transcriber/web-app) · 📄 [상세](https://app.notion.com/p/On-Device-Speech-Transcriber-416a1ef891b38054b380cd1a8530c5c2)
<!-- 🎬 데모 영상이 생기면 위 줄에 추가: · 🎬 [데모 영상](링크) -->

### 🎨 Promboard — 비전문가용 AI 이미지 · 영상 제작 데스크톱 앱
`2026.09 ~ 2026.10` · **4인 팀 (백엔드)** · `Node.js` `TypeScript` `Python` `Electron` `SQLite`

- 클라우드 SaaS를 **내 PC에 설치하는 데스크톱 앱**으로 바꾸는 과정에서 백엔드 담당
- 플러그인마다 격리된 Python 환경 + 사이드카 프로세스로 실행하는 **플러그인 실행 서버** 설계
- 로컬 AI 배경 제거 '빠름' 모드로 처리 시간 · 메모리 **약 10배 감소** (33~49초 · 7.05GB → 3.6초 · 721MB)
- 플러그인 다운로드 경로 위장 **보안 결함 발견 · 수정**, macOS 설치본 공개 Release (v1.0.7)
- 🎤 2026.11 경희대학교 「예술적인 소프트웨어」 최종 발표 · 전시
- 🌐 [promboard.kr](https://promboard.kr) · 📦 [Releases](https://github.com/promboard-app/releases) · 📄 [상세](https://app.notion.com/p/Promboard-40ca1ef891b38033a279fba3dc6b868e)

### 📚 Online-Study-Platform — 일정 · 목표 · 벌금 · 회의 기록을 한곳에서 관리하는 스터디 플랫폼
`2022.07 ~ 2022.08` · **5인 팀 (백엔드)** · `Node.js` `Express` `MongoDB`

- 1학년 동아리 첫 팀 프로젝트, 그룹 목표 조회 · 수정 API 작성
- 🏅 2022 경희대학교 컴퓨터공학부 동아리 대항전 **장려상**
- 📦 [GitHub](https://github.com/KHU-RETURN/Online-Study-Platform) · 📄 [상세 + 지금 다시 본 내 코드](https://app.notion.com/p/Online-Study-Platform-40ca1ef891b3807e8aecc73b02c071fc)

<br/>

## 🧭 Activities

| 기간 | 활동 |
| --- | --- |
| 2026.01 ~ 2026.12 | 경희대학교 제28대 컴퓨터공학부 학생회 **학생회장** |
| 2023.09 ~ 2023.12 | 컴퓨터공학부 학술동아리 T.G.winG **기획부장** |
| 2023.01 ~ 2023.12 | 경희대학교 제2대 컴퓨터공학부 학생회 **부학생회장** |
| 2022.03 ~ 2022.12 | 경희대학교 제1대 컴퓨터공학부 학생회 집행부원 |

## 📜 Certificates

| 자격증 | 취득일 | 주관 |
| --- | --- | --- |
| SQLD | 2025.09.19 | 데이터자격검정 |
| 프로그래밍기능사 (정보처리기능사) | 2024.01.22 | 한국산업인력공단 |

## 🎓 Education

- **경희대학교 컴퓨터공학과** 재학 (2022.03 ~) · 학점 3.76 / 4.5
- **독일 자를란트 대학교** 해외 전공연수 · Triathlon Program (2026.07)

<br/>

## 🛠️ Tech Stack

**Backend**<br/>
<img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white"/>
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white"/>

**Infra / DevOps**<br/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white"/>
<img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white"/>

**Language**<br/>
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white"/>
<img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white"/>

**Frontend / App**<br/>
<img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black"/>
<img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white"/>
<img src="https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white"/>
