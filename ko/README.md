# 🎭 The Agency: 당신의 워크플로를 바꿀 AI 전문가들

> 📘 이 문서는 [영문 원본 README](../README.md)의 한국어 번역판입니다.

> **완전한 AI 에이전시를 손끝에서** - 프론트엔드 마법사부터 레딧 커뮤니티 닌자까지, 위미시 인젝터부터 현실 점검 담당까지. 각 에이전트는 개성과 프로세스, 검증된 산출물을 갖춘 전문가입니다.

[![GitHub stars](https://img.shields.io/github/stars/msitarzewski/agency-agents?style=social)](https://github.com/msitarzewski/agency-agents)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://makeapullrequest.com)
[![Sponsor](https://img.shields.io/badge/Sponsor-%E2%9D%A4-pink?logo=github)](https://github.com/sponsors/msitarzewski)
[![Download the app](https://img.shields.io/github/v/release/msitarzewski/agency-agents-app?label=Download%20app&color=2563eb)](https://github.com/msitarzewski/agency-agents-app/releases/latest)

> ### 🆕 이제 앱이 있습니다
>
> **[Agency Agents](https://agencyagents.app)**는 **macOS, Linux, Windows**용 네이티브 앱입니다. 전체 로스터를 둘러보고 클릭 한 번으로 Claude Code, Cursor, Codex, Gemini, Osaurus 등에 설치해 줍니다. 클론도, 스크립트도 필요 없고 자동 업데이트까지 됩니다.
>
> **→ [최신 릴리스 다운로드](https://github.com/msitarzewski/agency-agents-app/releases/latest) · [agencyagents.app](https://agencyagents.app)**

---

## 🚀 이게 뭔가요?

레딧 스레드에서 시작해 수개월에 걸쳐 다듬어 온 **The Agency**는 정성껏 만든 AI 에이전트 페르소나를 계속 늘려 가는 모음집입니다. 각 에이전트는 이런 특징을 갖습니다.

- **🎯 전문화**: 자기 도메인에 대한 깊은 전문성 (일반적인 프롬프트 템플릿이 아닙니다)
- **🧠 개성 중심**: 고유한 목소리, 커뮤니케이션 스타일, 접근 방식
- **📋 산출물 중심**: 실제 코드, 프로세스, 측정 가능한 성과
- **✅ 프로덕션 준비 완료**: 실전에서 검증된 워크플로와 성공 지표

**이렇게 생각하세요**: 드림팀을 꾸리는 것. 단, 잠들지도 않고, 불평하지도 않고, 늘 결과를 내놓는 AI 전문가들로요.

---

## ⚡ 빠른 시작

### 옵션 1: 앱 설치 (추천)

가장 빠른 길입니다. 클론도, 터미널도 필요 없습니다. [**Agency Agents**](https://agencyagents.app)는 네이티브 데스크톱 앱(macOS · Linux · Windows)으로, 전체 로스터를 둘러보고 Claude Code, Cursor, Codex, Gemini CLI, OpenCode, Qwen, Osaurus에 에이전트를 설치해 준 다음 계속 최신 상태로 유지해 줍니다.

**[⬇ 최신 릴리스 다운로드](https://github.com/msitarzewski/agency-agents-app/releases/latest)** — 또는 Mac에서는:

```bash
brew install --cask msitarzewski/agency-agents/agency-agents
```

커맨드라인이 더 편하신가요? 아래 스크립트 기반 옵션도 같은 에이전트를 설치합니다.

### 옵션 2: Claude Code와 함께 쓰기

```bash
# 모든 에이전트를 Claude Code 디렉토리에 설치
./scripts/install.sh --tool claude-code

# 또는 하나의 디비전만 원하면 해당 카테고리를 직접 복사
cp engineering/*.md ~/.claude/agents/

# 그다음 Claude Code 세션에서 원하는 에이전트를 활성화하세요:
# "Hey Claude, activate Frontend Developer mode and help me build a React component"
```

### 옵션 3: 참고 자료로 쓰기

각 에이전트 파일에는 다음이 담겨 있습니다.
- 정체성과 성격 특성
- 핵심 미션과 워크플로
- 코드 예시가 포함된 기술 산출물
- 성공 지표와 커뮤니케이션 스타일

아래 에이전트들을 둘러보고 필요한 것을 복사하거나 변형해서 쓰세요!

### 옵션 4: 다른 도구와 함께 쓰기 (GitHub Copilot, Antigravity, Gemini CLI, OpenCode, OpenClaw, Cursor, Aider, Windsurf, Kimi Code, Codex, Osaurus, Hermes, Mistral Vibe)

```bash
# 1단계 -- 지원되는 모든 도구용 통합 파일 생성
./scripts/convert.sh

# 2단계 -- 대화형으로 설치 (설치된 도구를 자동 감지)
./scripts/install.sh

# 또는 특정 도구를 직접 지정
./scripts/install.sh --tool antigravity
./scripts/install.sh --tool gemini-cli
./scripts/install.sh --tool opencode
./scripts/install.sh --tool copilot
./scripts/install.sh --tool openclaw
./scripts/install.sh --tool cursor
./scripts/install.sh --tool aider
./scripts/install.sh --tool windsurf
./scripts/install.sh --tool kimi
./scripts/install.sh --tool codex
./scripts/install.sh --tool osaurus
./scripts/install.sh --tool hermes
./scripts/install.sh --tool vibe
```

**필요한 팀만 설치하세요** (모두가 모든 디비전을 원하는 건 아니니까요):

```bash
./scripts/install.sh                                    # 대화형 위저드: 도구 + 팀 선택
./scripts/install.sh --tool claude-code --division engineering,security
./scripts/install.sh --tool cursor --agent frontend-developer,ui-designer
./scripts/install.sh --list teams                       # 모든 팀 + 에이전트 수 보기
./scripts/install.sh --tool opencode --division engineering --dry-run
```

> **OpenCode 참고:** OpenCode 런타임은 현재 약 119개의 에이전트만 등록하고 나머지는 조용히 버립니다([업스트림 버그](https://github.com/anomalyco/opencode/issues/27988)). `--division`으로 일부만 설치하면 이 한계 아래로 유지됩니다. 선택한 범위가 한계를 넘으면 설치 스크립트가 경고해 줍니다.

자세한 내용은 아래 [멀티 도구 통합](#-멀티-도구-통합) 섹션을 참고하세요.

---

## 🎨 The Agency 로스터

### 💻 엔지니어링 디비전

커밋 하나하나로 미래를 만듭니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🎨 [Frontend Developer](engineering/engineering-frontend-developer.md) | React/Vue/Angular, UI 구현, 성능 | 모던 웹 앱, 픽셀 단위로 정확한 UI, Core Web Vitals 최적화 |
| 🏗️ [Backend Architect](engineering/engineering-backend-architect.md) | API 설계, 데이터베이스 아키텍처, 확장성 | 서버 사이드 시스템, 마이크로서비스, 클라우드 인프라 |
| 📱 [Mobile App Builder](engineering/engineering-mobile-app-builder.md) | iOS/Android, React Native, Flutter | 네이티브 및 크로스 플랫폼 모바일 애플리케이션 |
| 🤖 [AI Engineer](engineering/engineering-ai-engineer.md) | ML 모델, 배포, AI 통합 | 머신러닝 기능, 데이터 파이프라인, AI 기반 앱 |
| 🚀 [DevOps Automator](engineering/engineering-devops-automator.md) | CI/CD, 인프라 자동화, 클라우드 운영 | 파이프라인 개발, 배포 자동화, 모니터링 |
| 🌐 [Network Engineer](engineering/engineering-network-engineer.md) | Cisco IOS/IOS-XE, Juniper Junos, Palo Alto PAN-OS | 라우터/스위치/방화벽 설정, BGP/OSPF, ACL, show 출력 기반 트러블슈팅 |
| ⚡ [Rapid Prototyper](engineering/engineering-rapid-prototyper.md) | 빠른 POC 개발, MVP | 신속한 개념 증명, 해커톤 프로젝트, 빠른 반복 |
| 💎 [Senior Developer](engineering/engineering-senior-developer.md) | Laravel/Livewire, 고급 패턴 | 복잡한 구현, 아키텍처 의사결정 |
| 🔧 [Filament Optimization Specialist](engineering/engineering-filament-optimization-specialist.md) | Filament PHP 어드민 UX, 폼 구조 재설계, 리소스 최적화 | 더 빠르고 깔끔한 어드민 워크플로를 위한 Filament 리소스/폼/테이블 재구성 |
| ⚡ [Autonomous Optimization Architect](engineering/engineering-autonomous-optimization-architect.md) | LLM 라우팅, 비용 최적화, 섀도 테스팅 | 지능적인 API 선택과 비용 가드레일이 필요한 자율 시스템 |
| 🔩 [Embedded Firmware Engineer](engineering/engineering-embedded-firmware-engineer.md) | 베어메탈, RTOS, ESP32/STM32/Nordic 펌웨어 | 프로덕션급 임베디드 시스템과 IoT 기기 |
| 🚨 [Incident Response Commander](engineering/engineering-incident-response-commander.md) | 장애 관리, 포스트모템, 온콜 | 프로덕션 장애 대응과 장애 대비 체계 구축 |
| ⛓️ [Solidity Smart Contract Engineer](engineering/engineering-solidity-smart-contract-engineer.md) | EVM 컨트랙트, 가스 최적화, DeFi | 안전하고 가스 효율적인 스마트 컨트랙트와 DeFi 프로토콜 |
| 🧭 [Codebase Onboarding Engineer](engineering/engineering-codebase-onboarding-engineer.md) | 빠른 개발자 온보딩, 읽기 전용 코드베이스 탐색, 사실 기반 설명 | 코드를 읽고 코드 경로를 추적하며 구조와 동작에 대한 사실을 전달해, 새 개발자가 낯선 리포지토리를 빠르게 이해하도록 돕기 |
| 📚 [Technical Writer](engineering/engineering-technical-writer.md) | 개발자 문서, API 레퍼런스, 튜토리얼 | 명확하고 정확한 기술 문서 |
| 💬 [WeChat Mini Program Developer](engineering/engineering-wechat-mini-program-developer.md) | 위챗(WeChat) 생태계, 미니 프로그램, 결제 연동 | 위챗 생태계를 위한 고성능 앱 개발 |
| 👁️ [Code Reviewer](engineering/engineering-code-reviewer.md) | 건설적인 코드 리뷰, 보안, 유지보수성 | PR 리뷰, 코드 품질 게이트, 리뷰를 통한 멘토링 |
| 🗄️ [Database Optimizer](engineering/engineering-database-optimizer.md) | 스키마 설계, 쿼리 최적화, 인덱싱 전략 | PostgreSQL/MySQL 튜닝, 느린 쿼리 디버깅, 마이그레이션 계획 |
| 🌿 [Git Workflow Master](engineering/engineering-git-workflow-master.md) | 브랜칭 전략, 컨벤셔널 커밋, 고급 Git | Git 워크플로 설계, 히스토리 정리, CI 친화적 브랜치 관리 |
| 🏛️ [Software Architect](engineering/engineering-software-architect.md) | 시스템 설계, DDD, 아키텍처 패턴, 트레이드오프 분석 | 아키텍처 의사결정, 도메인 모델링, 시스템 진화 전략 |
| 🛡️ [SRE](engineering/engineering-sre.md) | SLO, 에러 버짓, 옵저버빌리티, 카오스 엔지니어링 | 프로덕션 신뢰성, 토일 감소, 용량 계획 |
| 🧬 [AI Data Remediation Engineer](engineering/engineering-ai-data-remediation-engineer.md) | 자가 치유 파이프라인, 에어갭 SLM, 시맨틱 클러스터링 | 데이터 손실 없이 대규모로 깨진 데이터 복구 |
| 🔧 [Data Engineer](engineering/engineering-data-engineer.md) | 데이터 파이프라인, 레이크하우스 아키텍처, ETL/ELT | 신뢰할 수 있는 데이터 인프라와 웨어하우스 구축 |
| 🔗 [Feishu Integration Developer](engineering/engineering-feishu-integration-developer.md) | 페이슈(飞书)/Lark 오픈 플랫폼, 봇, 워크플로 | 페이슈 생태계용 연동 개발 |
| 🧱 [CMS Developer](engineering/engineering-cms-developer.md) | WordPress·Drupal 테마, 플러그인/모듈, 콘텐츠 아키텍처 | 코드 중심의 CMS 구현과 커스터마이징 |
| 📧 [Email Intelligence Engineer](engineering/engineering-email-intelligence-engineer.md) | 이메일 파싱, MIME 추출, AI 에이전트용 구조화 데이터 | 원본 이메일 스레드를 추론 가능한 컨텍스트로 변환 |
| 🎙️ [Voice AI Integration Engineer](engineering/engineering-voice-ai-integration-engineer.md) | 음성 인식 파이프라인, Whisper, ASR, 화자 분리 | 엔드투엔드 전사 파이프라인, 오디오 전처리, 구조화된 전사 결과 제공 |
| 🖧 [IT Service Manager](engineering/engineering-it-service-manager.md) | ITIL 4 서비스 관리 | 인시던트/문제/변경 관리, SLA, CMDB |
| 🪡 [Minimal Change Engineer](engineering/engineering-minimal-change-engineer.md) | 최소한의 변경 디프 | 요청받은 것만 수정, 스코프 확장 없음 |
| 📜 [OrgScript Engineer](engineering/engineering-orgscript-engineer.md) | OrgScript 문법 및 AST 검증 | OrgScript 비즈니스 로직 정의 설계·파싱 |
| 🧬 [Prompt Engineer](engineering/engineering-prompt-engineer.md) | LLM 프롬프트 설계·최적화 | 모호한 지시를 믿을 수 있는 AI 동작으로 바꾸기 |
| 🕸️ [Multi-Agent Systems Architect](engineering/engineering-multi-agent-systems-architect.md) | 멀티 에이전트 파이프라인 설계와 거버넌스 | 에이전트 시스템의 토폴로지, 컨텍스트, 신뢰, 장애 복구 |
| 🛒 [Drupal Shopping Cart Engineer](engineering/engineering-drupal-shopping-cart.md) | Drupal Commerce 스토어프런트 | Drupal 10/11에서의 카탈로그, 결제, 체크아웃, 주문 |
| 🛍️ [WordPress Shopping Cart Engineer](engineering/engineering-wordpress-shopping-cart.md) | WooCommerce 스토어프런트 | WordPress에서의 카탈로그, 결제, 체크아웃, 전환 |
| 💳 [Payments & Billing Engineer](engineering/engineering-payments-billing-engineer.md) | PSP 연동, 멱등성 있는 결제 플로, 구독 과금 | Stripe/Adyen/Braintree 연동, 웹훅 처리, 미납 독촉(dunning), 정산 대조 |
| 🌍 [Internationalization Engineer](engineering/engineering-i18n-engineer.md) | ICU MessageFormat, RTL/양방향 레이아웃, CLDR 포매팅, 의사 현지화 | 번역 가능한 앱 만들기, 로케일 인식 포매팅, RTL 지원, i18n 감사 |
| ⚡ [Drupal Performance Engineer](engineering/engineering-drupal-performance.md) | Drupal 성능과 Core Web Vitals | 캐싱, DB/쿼리 튜닝, 렌더 파이프라인, 대규모 트래픽 Drupal 프로파일링 |
| ⚡ [WordPress Performance Engineer](engineering/engineering-wordpress-performance.md) | WordPress 성능과 Core Web Vitals | 캐싱, 쿼리/에셋 최적화, 플러그인 튜닝, 대규모 트래픽 WP 프로파일링 |
| ♿ [Section 508 Accessibility Specialist](engineering/engineering-section-508-specialist.md) | 미국 연방 508조 / WCAG 접근성 | ARIA, 스크린 리더 테스트, VPAT/ACR 작성, 개선 작업 |
| 🏛️ [USWDS Developer](engineering/engineering-uswds-developer.md) | US Web Design System (미 연방) | 접근성 있는 공공 UI 컴포넌트와 디자인 시스템 패턴 |
| 🔎 [Search Relevance Engineer](engineering/engineering-search-relevance-engineer.md) | 검색 랭킹과 연관성 | 쿼리 이해, 임베딩, 랭킹/평가, 연관성 튜닝 |
| 🔐 [Identity & Access Engineer](engineering/engineering-identity-access-engineer.md) | 인증/인가와 IAM | OAuth/OIDC/SAML, SSO, RBAC/ABAC, 토큰·세션 보안 |
| 🤝 [Realtime Collaboration Engineer](engineering/engineering-realtime-collaboration-engineer.md) | 실시간 동기화와 프레즌스 | CRDT/OT, 충돌 해결, 라이브 커서, 오프라인 동기화 |
| 💻 [Desktop App Engineer](engineering/engineering-desktop-app-engineer.md) | 크로스 플랫폼 데스크톱 앱 | Electron/Tauri, 네이티브 연동, 패키징, 자동 업데이트 |
| 🚀 [Mobile Release Engineer](engineering/engineering-mobile-release-engineer.md) | 모바일 릴리스와 CI/CD | App Store/Play 심사 제출, 서명, 단계적 롤아웃, 크래시 분류 |
| 🎬 [Video Streaming Engineer](engineering/engineering-video-streaming-engineer.md) | 비디오 스트리밍과 트랜스코딩 | HLS/DASH, ABR, 코덱, CDN 전송, 저지연 스트리밍 |
| 💰 [FinOps Engineer](engineering/engineering-finops-engineer.md) | 클라우드 비용 엔지니어링 | 비용 배분, 라이트사이징, 단위 경제성, 예산·이상치 관리 |
| 🧩 [WebAssembly Engineer](engineering/engineering-webassembly-engineer.md) | WebAssembly와 WASI | Rust/C++→WASM, 샌드박싱, 호스트 바인딩, 성능 |
| 🔌 [API Platform Engineer](engineering/engineering-api-platform-engineer.md) | API 게이트웨이와 플랫폼 | 게이트웨이 설계, 버저닝, 레이트 리밋, 개발자 포털 |
| 🛟 [Database Reliability Engineer](engineering/engineering-database-reliability-engineer.md) | 데이터베이스 신뢰성 (DBRE) | HA/복제, 자동 페일오버, PITR 백업, 무중단 운영 |
| 🛠️ [Developer Tooling Engineer](engineering/engineering-developer-tooling-engineer.md) | CLI와 개발자 도구 | 커맨드라인 도구, 내부 DX, 빌드/개발 워크플로 |
| 📡 [IoT Fleet Engineer](engineering/engineering-iot-fleet-engineer.md) | IoT와 엣지 플릿 | 기기 프로비저닝/신원, MQTT 텔레메트리, OTA 업데이트 |
| 🔍 [RAG Pipeline Engineer](engineering/engineering-rag-pipeline-engineer.md) | 프로덕션 RAG 파이프라인 | 청킹, 검색 품질, 하이브리드 검색, 리랭킹, 평가 기반 반복 개선 |
| 🗄️ [GaussDB Expert Engineer](engineering/engineering-gaussdb-expert.md) | 화웨이 GaussDB OLTP | 화웨이 GaussDB에서의 엔터프라이즈 OLTP 성능, HA, 마이그레이션 |
| 🕵️ [Privacy Engineer](engineering/engineering-privacy-engineer.md) | PII 탐색, 데이터 최소화, 동의 집행, DSAR/삭제 파이프라인 | 코드로 구현하는 프라이버시, 서비스 전반의 잊힐 권리, 보관 기간 자동화 |
| 🦀 [Rust Refactoring Specialist](engineering/engineering-rust-refactoring-specialist.md) | 동작을 이해한 Rust 리팩터링 | 근거 기반·동작 보존 변경으로 crate/trait/모듈 재구성 |
| 🧪 [LLM Post-Training Engineer](engineering/engineering-llm-post-training-engineer.md) | 포스트 트레이닝 스택 (SFT/DPO/GRPO/RLVR) | 근거 기반 실험 게이팅, 체크포인트 무결성, 실패 분류 |
| 📈 [Data Visualization Engineer](engineering/engineering-data-visualization-engineer.md) | 지각적으로 정직한 데이터 시각화 | 차트 유형 선택, 색각 이상 안전 팔레트, 성능 좋은 D3/Vega 렌더링 |
| 🧠 [Knowledge Graph Engineer](engineering/engineering-knowledge-graph-engineer.md) | 지식 그래프, 엔터티-관계 추출, 그래프 강화 RAG | LangGraph로 문서를 질의 가능한 Neo4j 그래프로 구조화. 출처 추적, 모순 추적, 서브그래프 검색 |
| 🌏 [China Network Engineer](engineering/engineering-china-network-engineer.md) | 화웨이 VRP, H3C Comware, Ruijie RGOS, Hillstone StoneOS | 라우팅/스위칭/방화벽 설계, NAT, MLPS 2.0 준수 경계, 롤백 계획이 있는 변경 작업 창 |
| 🛤️ [Platform Engineer](engineering/engineering-platform-engineer.md) | 내부 개발자 플랫폼, 골든 패스, IDP, 셀프서비스 인프라 | 포장도로형 스캐폴딩, 개발자 경험 측정, 제품으로서의 플랫폼 로드맵 |
| 📑 [PDF Engine Architect](engineering/engineering-pdf-engine-architect.md) | 결정론적 HTML→PDF 컴파일, 태그 PDF/UA 및 PDF/A | Playwright 렌더 풀, 동적 페이지 크기 조정, 보존용 품질의 문서 출력 |
| 🎯 [ATS Validator Architect](engineering/engineering-ats-validator-architect.md) | 이력서 파싱 가능성, ATS 수집 파이프라인 | BM25/TF-IDF 연관성 점수, 레이아웃 선형화 감사, EU AI Act 및 NYC LL144 준수 |
| 📑 [Universal Document Compiler](engineering/engineering-universal-document-compiler.md) | 스키마에 구애받지 않는 문서 AST, 데이터 형태 기반 레이아웃 추론, 페이지 단위 퍼블리싱 | 임의의 YAML 트리를 제안서, 기술 명세, 임원용 보고서로 컴파일 |

### 🎨 디자인 디비전

아름답고, 쓰기 쉽고, 즐겁게 만듭니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🎯 [UI Designer](design/design-ui-designer.md) | 비주얼 디자인, 컴포넌트 라이브러리, 디자인 시스템 | 인터페이스 제작, 브랜드 일관성, 컴포넌트 디자인 |
| 🔍 [UX Researcher](design/design-ux-researcher.md) | 사용자 테스트, 행동 분석, 리서치 | 사용자 이해, 사용성 테스트, 디자인 인사이트 |
| 🏛️ [UX Architect](design/design-ux-architect.md) | 기술 아키텍처, CSS 시스템, 구현 | 개발자 친화적 기반 설계, 구현 가이드 |
| 🎭 [Brand Guardian](design/design-brand-guardian.md) | 브랜드 아이덴티티, 일관성, 포지셔닝 | 브랜드 전략, 아이덴티티 개발, 가이드라인 |
| 📖 [Visual Storyteller](design/design-visual-storyteller.md) | 비주얼 내러티브, 멀티미디어 콘텐츠 | 설득력 있는 비주얼 스토리, 브랜드 스토리텔링 |
| ✨ [Whimsy Injector](design/design-whimsy-injector.md) | 개성, 즐거움, 장난기 있는 인터랙션 | 재미 더하기, 마이크로 인터랙션, 이스터에그, 브랜드 개성 |
| 📷 [Image Prompt Engineer](design/design-image-prompt-engineer.md) | AI 이미지 생성 프롬프트, 사진 | Midjourney, DALL-E, Stable Diffusion용 사진 프롬프트 |
| 🌈 [Inclusive Visuals Specialist](design/design-inclusive-visuals-specialist.md) | 대표성, 편향 완화, 진정성 있는 이미지 | 문화적으로 정확한 AI 이미지·영상 생성 |
| 🎭 [Persona Walkthrough Specialist](design/design-persona-walkthrough.md) | 페르소나 기반 인지적 워크스루 | 스크롤 위치마다 사용자 반응과 마찰 지점 시뮬레이션 |
| 🧱 [UI Finish-Gate Reviewer](design/design-ui-finish-gate-reviewer.md) | 흔해 빠진 UI를 막는 마감 게이트 | 증거와 문서화된 디자인 계약으로 출시 전 교체 가능한 UI 걸러내기 |

### 💰 유료 미디어 디비전

광고비를 측정 가능한 비즈니스 성과로 바꿉니다.

| 에이전트 | 전문 분야 | 사용 시점 |
| --- | --- | --- |
| 💰 [PPC Campaign Strategist](paid-media/paid-media-ppc-strategist.md) | Google/Microsoft/Amazon Ads, 계정 구조, 입찰 | 계정 구축, 예산 배분, 확장, 성과 진단 |
| 🔍 [Search Query Analyst](paid-media/paid-media-search-query-analyst.md) | 검색어 분석, 제외 키워드, 인텐트 매핑 | 검색어 감사, 낭비되는 지출 제거, 키워드 발굴 |
| 📋 [Paid Media Auditor](paid-media/paid-media-auditor.md) | 200개 이상 항목의 계정 감사, 경쟁 분석 | 계정 인수, 분기 리뷰, 경쟁 피치 |
| 📡 [Tracking & Measurement Specialist](paid-media/paid-media-tracking-specialist.md) | GTM, GA4, 전환 추적, CAPI | 신규 구축, 추적 감사, 플랫폼 마이그레이션 |
| ✍️ [Ad Creative Strategist](paid-media/paid-media-creative-strategist.md) | RSA 카피, Meta 크리에이티브, Performance Max 에셋 | 크리에이티브 출시, 테스트 프로그램, 광고 피로도 리프레시 |
| 📺 [Programmatic & Display Buyer](paid-media/paid-media-programmatic-buyer.md) | GDN, DSP, 파트너 미디어, ABM 디스플레이 | 디스플레이 기획, 파트너 발굴, ABM 프로그램 |
| 📱 [Paid Social Strategist](paid-media/paid-media-paid-social-strategist.md) | Meta, LinkedIn, TikTok, 크로스 플랫폼 소셜 | 소셜 광고 프로그램, 플랫폼 선정, 오디언스 전략 |

### 💼 세일즈 디비전

CRM 잡무가 아니라 실력으로 파이프라인을 매출로 바꿉니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🎯 [Outbound Strategist](sales/sales-outbound-strategist.md) | 시그널 기반 프로스펙팅, 멀티채널 시퀀스, ICP 타게팅 | 물량이 아니라 리서치 기반 아웃리치로 파이프라인 만들기 |
| 🔍 [Discovery Coach](sales/sales-discovery-coach.md) | SPIN, Gap Selling, Sandler — 질문 설계와 콜 구조 | 디스커버리 콜 준비, 기회 검증, 영업 담당 코칭 |
| ♟️ [Deal Strategist](sales/sales-deal-strategist.md) | MEDDPICC 검증, 경쟁 포지셔닝, 수주 계획 | 딜 점수화, 파이프라인 리스크 노출, 수주 전략 수립 |
| 🛠️ [Sales Engineer](sales/sales-engineer.md) | 기술 데모, POC 범위 설정, 경쟁 배틀카드 | 프리세일즈 기술 승리, 데모 준비, 경쟁 포지셔닝 |
| 🏹 [Proposal Strategist](sales/sales-proposal-strategist.md) | RFP 대응, 수주 테마, 내러티브 구조 | 요건만 채우는 게 아니라 설득하는 제안서 쓰기 |
| 📊 [Pipeline Analyst](sales/sales-pipeline-analyst.md) | 예측, 파이프라인 건강도, 딜 속도, RevOps | 파이프라인 리뷰, 예측 정확도, 레비뉴 오퍼레이션 |
| 🗺️ [Account Strategist](sales/sales-account-strategist.md) | 랜드 앤 익스팬드, QBR, 이해관계자 맵핑 | 사후 확장, 어카운트 플래닝, NRR 성장 |
| 🏋️ [Sales Coach](sales/sales-coach.md) | 담당자 역량 개발, 콜 코칭, 파이프라인 리뷰 진행 | 체계적인 코칭으로 모든 담당자와 모든 딜을 더 좋게 만들기 |
| 🎯 [Sales Outreach](specialized/sales-outreach.md) | 콜드 프로스펙팅, 멀티터치 케이던스, 반론 처리, 제안서 | 콜드 이메일부터 디스커버리 콜 예약까지, B2B 퍼널 상단 아웃리치 |
| 🧲 [Offer & Lead Gen Strategist](sales/sales-offer-lead-gen-strategist.md) | 오퍼와 리드 마그넷 | 퍼널 상단 오퍼 설계와 리드 제너레이션 |

### 📢 마케팅 디비전

진정성 있는 상호작용 하나하나로 오디언스를 키웁니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🚀 [Growth Hacker](marketing/marketing-growth-hacker.md) | 빠른 유저 확보, 바이럴 루프, 실험 | 폭발적 성장, 유저 확보, 전환 최적화 |
| 📝 [Content Creator](marketing/marketing-content-creator.md) | 멀티 플랫폼 콘텐츠, 에디토리얼 캘린더 | 콘텐츠 전략, 카피라이팅, 브랜드 스토리텔링 |
| 🐦 [Twitter Engager](marketing/marketing-twitter-engager.md) | 실시간 인게이지먼트, 소트 리더십 | 트위터 전략, LinkedIn 캠페인, 프로페셔널 소셜 |
| 🛰️ [X/Twitter Intelligence Analyst](marketing/marketing-x-twitter-intelligence-analyst.md) | 소셜 리스닝, 트렌드 탐지, 계정 모니터링 | X/Twitter에서의 브랜드 리스크, 경쟁사, 오디언스 인텔리전스 |
| 📱 [TikTok Strategist](marketing/marketing-tiktok-strategist.md) | 바이럴 콘텐츠, 알고리즘 최적화 | TikTok 성장, 바이럴 콘텐츠, Z세대/밀레니얼 오디언스 |
| 📸 [Instagram Curator](marketing/marketing-instagram-curator.md) | 비주얼 스토리텔링, 커뮤니티 구축 | 인스타그램 전략, 미감 개발, 비주얼 콘텐츠 |
| 🤝 [Reddit Community Builder](marketing/marketing-reddit-community-builder.md) | 진정성 있는 참여, 가치 중심 콘텐츠 | 레딧 전략, 커뮤니티 신뢰, 진정성 있는 마케팅 |
| 📱 [App Store Optimizer](marketing/marketing-app-store-optimizer.md) | ASO, 전환 최적화, 발견 가능성 | 앱 마케팅, 스토어 최적화, 앱 성장 |
| 🌐 [Social Media Strategist](marketing/marketing-social-media-strategist.md) | 크로스 플랫폼 전략, 캠페인 | 전체 소셜 전략, 멀티 플랫폼 캠페인 |
| 📕 [Xiaohongshu Specialist](marketing/marketing-xiaohongshu-specialist.md) | 라이프스타일 콘텐츠, 트렌드 기반 전략 | 샤오홍슈(小红书) 성장, 감각적인 스토리텔링, Z세대 오디언스 |
| 💬 [WeChat Official Account Manager](marketing/marketing-wechat-official-account.md) | 구독자 인게이지먼트, 콘텐츠 마케팅 | 위챗(WeChat) 공식 계정 전략, 커뮤니티 구축, 전환 최적화 |
| 🧠 [Zhihu Strategist](marketing/marketing-zhihu-strategist.md) | 소트 리더십, 지식 기반 인게이지먼트 | 즈후(知乎) 권위 구축, Q&A 전략, 리드 제너레이션 |
| 🇨🇳 [Baidu SEO Specialist](marketing/marketing-baidu-seo-specialist.md) | 바이두 최적화, 중국 SEO, ICP 준수 | 바이두 상위 노출과 중국 검색 시장 공략 |
| 🎬 [Bilibili Content Strategist](marketing/marketing-bilibili-content-strategist.md) | 빌리빌리(B站) 알고리즘, 단무(弹幕) 문화, UP주(UP主) 성장 | 커뮤니티 우선 콘텐츠로 빌리빌리 오디언스 키우기 |
| 🎠 [Carousel Growth Engine](marketing/marketing-carousel-growth-engine.md) | TikTok/Instagram 캐러셀, 자율 퍼블리싱 | 바이럴 캐러셀 콘텐츠 생성과 발행 |
| 💼 [LinkedIn Content Creator](marketing/marketing-linkedin-content-creator.md) | 퍼스널 브랜딩, 소트 리더십, 프로페셔널 콘텐츠 | LinkedIn 성장, 전문가 오디언스 구축, B2B 콘텐츠 |
| 🛒 [China E-Commerce Operator](marketing/marketing-china-ecommerce-operator.md) | 타오바오, 티몰, 핀둬둬, 라이브 커머스 | 중국에서 멀티 플랫폼 이커머스 운영 |
| 🎥 [Kuaishou Strategist](marketing/marketing-kuaishou-strategist.md) | 콰이쇼우(快手), 라오톄(老铁) 커뮤니티, 풀뿌리 성장 | 하위 티어 도시 시장에서 진정성 있는 오디언스 구축 |
| 🔍 [SEO Specialist](marketing/marketing-seo-specialist.md) | 테크니컬 SEO, 콘텐츠 전략, 링크 빌딩 | 지속 가능한 오가닉 검색 성장 견인 |
| 📘 [Book Co-Author](marketing/marketing-book-co-author.md) | 소트 리더십 도서, 대필, 출판 | 창업자와 전문가를 위한 전략적 도서 공동 작업 |
| 🌏 [Cross-Border E-Commerce Specialist](marketing/marketing-cross-border-ecommerce.md) | Amazon, Shopee, Lazada, 크로스보더 풀필먼트 | 풀퍼널 크로스보더 이커머스 전략 |
| 🎵 [Douyin Strategist](marketing/marketing-douyin-strategist.md) | 더우인(抖音) 플랫폼, 숏폼 영상 마케팅, 알고리즘 | 중국 1위 숏폼 영상 플랫폼에서 오디언스 키우기 |
| 🎙️ [Livestream Commerce Coach](marketing/marketing-livestream-commerce-coach.md) | 호스트 교육, 라이브룸 최적화, 전환 | 성과 높은 라이브 커머스 운영 체계 구축 |
| 🎧 [Podcast Strategist](marketing/marketing-podcast-strategist.md) | 팟캐스트 콘텐츠 전략, 플랫폼 최적화 | 중국 팟캐스트 시장 전략과 운영 |
| 🔒 [Private Domain Operator](marketing/marketing-private-domain-operator.md) | 위컴(WeCom), 사적 트래픽, 커뮤니티 운영 | 기업용 위챗 사적 도메인 생태계 구축 |
| 🎬 [Short-Video Editing Coach](marketing/marketing-short-video-editing-coach.md) | 후반 작업, 편집 워크플로, 플랫폼 규격 | 실습 중심 숏폼 영상 편집 교육과 최적화 |
| 🔥 [Weibo Strategist](marketing/marketing-weibo-strategist.md) | 시나 웨이보(微博), 실시간 트렌드, 팬 인게이지먼트 | 웨이보 전방위 운영과 성장 |
| 🎙️ [Global Podcast Strategist](marketing/marketing-global-podcast-strategist.md) | 쇼 포지셔닝, 오디언스 성장, 수익화 | 팟캐스트 런치, 플랫폼 알고리즘, 스폰서십, 커뮤니티 구축 |
| 🔮 [AI Citation Strategist](marketing/marketing-ai-citation-strategist.md) | AEO/GEO, AI 추천 가시성, 인용 감사 | ChatGPT, Claude, Gemini, Perplexity 전반에서 브랜드 가시성 높이기 |
| 🇨🇳 [China Market Localization Strategist](marketing/marketing-china-market-localization-strategist.md) | 풀스택 중국 시장 현지화, 더우인/샤오홍슈/위챗 GTM | 트렌드 시그널을 실행 가능한 중국 진출 전략으로 전환 |
| 🎬 [Video Optimization Specialist](marketing/marketing-video-optimization-specialist.md) | 유튜브 알고리즘 전략, 챕터링, 썸네일 컨셉 | 유튜브 채널 성장, 비디오 SEO, 시청 지속률 최적화 |
| 🏗️ [AEO Foundations Architect](marketing/marketing-aeo-foundations.md) | AI 엔진 최적화 인프라 | llms.txt, AI를 고려한 robots.txt, 에이전트 디스커버리 파일 |
| 🤖 [Agentic Search Optimizer](marketing/marketing-agentic-search-optimizer.md) | WebMCP와 에이전틱 작업 완수 | AI 브라우징 에이전트가 쓸 수 있는 사이트 만들기 |
| 📧 [Email Marketing Strategist](marketing/marketing-email-strategist.md) | 라이프사이클 이메일과 도달률 | CRM 캠페인, 자동화, 세그멘테이션 |
| 📡 [Multi-Platform Publisher](marketing/marketing-multi-platform-publisher.md) | 원클릭 중국 멀티 플랫폼 퍼블리싱 | 하나의 글을 知乎/小红书/CSDN/B站/公众号/掘金으로 분배 |
| 📣 [PR & Communications Manager](marketing/marketing-pr-communications-manager.md) | PR, 미디어 관계, 위기 커뮤니케이션 | 보도자료, 소트 리더십, 평판 관리 |

### 📊 프로덕트 디비전

맞는 것을, 맞는 때에 만듭니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🎯 [Sprint Prioritizer](product/product-sprint-prioritizer.md) | 애자일 플래닝, 기능 우선순위 결정 | 스프린트 플래닝, 리소스 배분, 백로그 관리 |
| 🔍 [Trend Researcher](product/product-trend-researcher.md) | 시장 인텔리전스, 경쟁 분석 | 시장 조사, 기회 평가, 트렌드 식별 |
| 💬 [Feedback Synthesizer](product/product-feedback-synthesizer.md) | 사용자 피드백 분석, 인사이트 추출 | 피드백 분석, 사용자 인사이트, 제품 우선순위 |
| 🧠 [Behavioral Nudge Engine](product/product-behavioral-nudge-engine.md) | 행동 심리학, 넛지 설계, 인게이지먼트 | 행동과학으로 사용자 동기 극대화 |
| 🧭 [Product Manager](product/product-manager.md) | 전체 라이프사이클 제품 오너십 | 디스커버리, PRD, 로드맵 기획, GTM, 성과 측정 |

### 🎬 프로젝트 관리 디비전

열차가 제때, 예산 안에서 달리게 합니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🎬 [Studio Producer](project-management/project-management-studio-producer.md) | 상위 수준 오케스트레이션, 포트폴리오 관리 | 다중 프로젝트 관리, 전략적 정렬, 리소스 배분 |
| 🐑 [Project Shepherd](project-management/project-management-project-shepherd.md) | 직능 간 조율, 일정 관리 | 엔드투엔드 프로젝트 조율, 이해관계자 관리 |
| ⚙️ [Studio Operations](project-management/project-management-studio-operations.md) | 일상 업무 효율, 프로세스 최적화 | 운영 엑설런스, 팀 지원, 생산성 |
| 🧪 [Experiment Tracker](project-management/project-management-experiment-tracker.md) | A/B 테스트, 가설 검증 | 실험 관리, 데이터 기반 의사결정, 테스팅 |
| 👔 [Senior Project Manager](project-management/project-manager-senior.md) | 현실적인 범위 설정, 태스크 전환 | 명세를 태스크로 변환, 스코프 관리 |
| 📋 [Jira Workflow Steward](project-management/project-management-jira-workflow-steward.md) | Git 워크플로, 브랜치 전략, 추적성 | Jira와 연결된 Git 규율과 딜리버리 집행 |
| 📋 [Meeting Notes Specialist](project-management/project-management-meeting-notes-specialist.md) | 구조화된 회의 요약 | 결정 사항, 액션 아이템, 미해결 질문 추출 |

### 🧪 테스팅 디비전

사용자가 겪지 않도록 먼저 깨뜨립니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 📸 [Evidence Collector](testing/testing-evidence-collector.md) | 스크린샷 기반 QA, 시각적 증거 | UI 테스트, 시각적 검증, 버그 문서화 |
| 🔍 [Reality Checker](testing/testing-reality-checker.md) | 증거 기반 인증, 품질 게이트 | 프로덕션 준비도, 품질 승인, 릴리스 인증 |
| 📊 [Test Results Analyzer](testing/testing-test-results-analyzer.md) | 테스트 평가, 지표 분석 | 테스트 출력 분석, 품질 인사이트, 커버리지 리포팅 |
| ⚡ [Performance Benchmarker](testing/testing-performance-benchmarker.md) | 성능 테스트, 최적화 | 속도 테스트, 부하 테스트, 성능 튜닝 |
| 🔌 [API Tester](testing/testing-api-tester.md) | API 검증, 통합 테스트 | API 테스트, 엔드포인트 검증, 통합 QA |
| 🛠️ [Tool Evaluator](testing/testing-tool-evaluator.md) | 기술 평가, 도구 선정 | 도구 평가, 소프트웨어 추천, 기술 의사결정 |
| 🔄 [Workflow Optimizer](testing/testing-workflow-optimizer.md) | 프로세스 분석, 워크플로 개선 | 프로세스 최적화, 효율 향상, 자동화 기회 발굴 |
| ♿ [Accessibility Auditor](testing/testing-accessibility-auditor.md) | WCAG 감사, 보조 기술 테스트 | 접근성 준수, 스크린 리더 테스트, 인클루시브 디자인 검증 |
| 🎭 [Test Automation Engineer](testing/testing-test-automation-engineer.md) | Playwright/Cypress E2E, 플레이키 테스트 제거, CI 병렬화 | 브라우저 테스트 스위트, 결정론적 파이프라인, 트레이스 기반 실패 디버깅 |

### 🔒 보안 디비전

시큐어 바이 디자인 아키텍처부터 침해 대응까지, 스택 전체를 방어합니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🛡️ [Security Architect](security/security-architect.md) | 위협 모델링, 시큐어 바이 디자인, 신뢰 경계 | 시스템 보안 모델, 아키텍처 리뷰, 다층 방어 |
| 🔐 [Application Security Engineer](security/security-appsec-engineer.md) | SDLC 보안, SAST/DAST, 보안 코드 리뷰 | 개발 라이프사이클 보안, 코드 수준 취약점 |
| 🗡️ [Penetration Tester](security/security-penetration-tester.md) | 허가된 모의 침투, 레드팀 작전, 공격 실행 | 공격자보다 먼저 악용 가능한 약점 찾기 |
| ☁️ [Cloud Security Architect](security/security-cloud-security-architect.md) | 제로 트러스트, 클라우드 네이티브 다층 방어 | 클라우드 인프라와 아키텍처 보안 |
| 🚨 [Incident Responder](security/security-incident-responder.md) | DFIR, 침해 조사, 위협 차단 | 진행 중인 침해, 포렌식, 위기 대응 |
| 🔍 [Threat Intelligence Analyst](security/security-threat-intelligence-analyst.md) | 공격자 추적, 캠페인 맵핑, ATT&CK | 누가 어떻게 공격하는지 파악하기 |
| 🎯 [Threat Detection Engineer](security/security-threat-detection-engineer.md) | SIEM 룰, 위협 헌팅, ATT&CK 맵핑 | 탐지 계층 구축과 위협 헌팅 |
| 🛡️ [Senior SecOps Engineer](security/security-senior-secops.md) | 시크릿 스캐닝, 기본값으로 안전한 제출물 | 모든 변경에 적용되는 방어적 코드 수준 보안 |
| 📋 [Compliance Auditor](security/security-compliance-auditor.md) | SOC 2, ISO 27001, HIPAA, PCI-DSS | 조직의 컴플라이언스 인증 획득 안내 |
| 🛡️ [Blockchain Security Auditor](security/security-blockchain-security-auditor.md) | 스마트 컨트랙트 감사, 익스플로잇 분석 | 배포 전에 컨트랙트 취약점 찾기 |
| 🔎 [AI-Generated Code Security Auditor](security/security-ai-generated-code-auditor.md) | AI/바이브 코딩 앱 보안 리뷰 | 하드코딩된 시크릿, 망가진 RLS, 프롬프트 인젝션 싱크 |
| 🔑 [Secrets & Credential Hygiene Engineer](security/security-secrets-credential-engineer.md) | 시크릿·자격 증명 라이프사이클 | 탐지, 볼팅, 교체, 유출 대응 |

### 🛟 서포트 디비전

조직 운영의 근간입니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 💬 [Support Responder](support/support-support-responder.md) | 고객 응대, 이슈 해결 | 고객 지원, 사용자 경험, 서포트 운영 |
| 📊 [Analytics Reporter](support/support-analytics-reporter.md) | 데이터 분석, 대시보드, 인사이트 | 비즈니스 인텔리전스, KPI 추적, 데이터 시각화 |
| 💰 [Finance Tracker](support/support-finance-tracker.md) | 재무 계획, 예산 관리 | 재무 분석, 현금 흐름, 사업 성과 |
| 🏗️ [Infrastructure Maintainer](support/support-infrastructure-maintainer.md) | 시스템 신뢰성, 성능 최적화 | 인프라 관리, 시스템 운영, 모니터링 |
| ⚖️ [Legal Compliance Checker](support/support-legal-compliance-checker.md) | 컴플라이언스, 규제, 법무 검토 | 법규 준수, 규제 요건, 리스크 관리 |
| 📑 [Executive Summary Generator](support/support-executive-summary-generator.md) | 경영진 커뮤니케이션, 전략 요약 | 임원 보고, 전략 커뮤니케이션, 의사결정 지원 |

### 🥽 공간 컴퓨팅 디비전

몰입형 미래를 만듭니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🏗️ [XR Interface Architect](spatial-computing/xr-interface-architect.md) | 공간 인터랙션 디자인, 몰입형 UX | AR/VR/XR 인터페이스 디자인, 공간 컴퓨팅 UX |
| 💻 [macOS Spatial/Metal Engineer](spatial-computing/macos-spatial-metal-engineer.md) | Swift, Metal, 고성능 3D | macOS 공간 컴퓨팅, Vision Pro 네이티브 앱 |
| 🌐 [XR Immersive Developer](spatial-computing/xr-immersive-developer.md) | WebXR, 브라우저 기반 AR/VR | 브라우저 기반 몰입형 경험, WebXR 앱 |
| 🎮 [XR Cockpit Interaction Specialist](spatial-computing/xr-cockpit-interaction-specialist.md) | 콕핏 기반 컨트롤, 몰입형 시스템 | 콕핏 제어 시스템, 몰입형 제어 인터페이스 |
| 🍎 [visionOS Spatial Engineer](spatial-computing/visionos-spatial-engineer.md) | Apple Vision Pro 개발 | Vision Pro 앱, 공간 컴퓨팅 경험 |
| 🔌 [Terminal Integration Specialist](spatial-computing/terminal-integration-specialist.md) | 터미널 통합, 커맨드라인 도구 | CLI 도구, 터미널 워크플로, 개발자 도구 |

### 🎯 스페셜라이즈드 디비전

틀에 들어가지 않는 독특한 전문가들입니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🎭 [Agents Orchestrator](specialized/agents-orchestrator.md) | 멀티 에이전트 조율, 워크플로 관리 | 여러 에이전트의 협업이 필요한 복잡한 프로젝트 |
| 🔍 [LSP/Index Engineer](specialized/lsp-index-engineer.md) | Language Server Protocol, 코드 인텔리전스 | 코드 인텔리전스 시스템, LSP 구현, 시맨틱 인덱싱 |
| 📥 [Sales Data Extraction Agent](specialized/sales-data-extraction-agent.md) | 엑셀 모니터링, 영업 지표 추출 | 영업 데이터 수집, MTD/YTD/연말 지표 |
| 📈 [Data Consolidation Agent](specialized/data-consolidation-agent.md) | 영업 데이터 집계, 대시보드 리포트 | 지역별 요약, 담당자 성과, 파이프라인 스냅샷 |
| 📬 [Report Distribution Agent](specialized/report-distribution-agent.md) | 자동 리포트 발송 | 지역 기반 리포트 배포, 예약 발송 |
| 🔐 [Agentic Identity & Trust Architect](specialized/agentic-identity-trust.md) | 에이전트 신원, 인증, 신뢰 검증 | 멀티 에이전트 신원 시스템, 에이전트 인가, 감사 추적 |
| 🔗 [Identity Graph Operator](specialized/identity-graph-operator.md) | 멀티 에이전트 시스템을 위한 공유 신원 해석 | 엔터티 중복 제거, 병합 제안, 에이전트 간 신원 일관성 |
| 💸 [Accounts Payable Agent](specialized/accounts-payable-agent.md) | 지급 처리, 벤더 관리, 감사 | 암호화폐, 법정화폐, 스테이블코인 전반의 자율 지급 실행 |
| 🌍 [Cultural Intelligence Strategist](specialized/specialized-cultural-intelligence-strategist.md) | 글로벌 UX, 대표성, 문화적 배제 | 소프트웨어가 여러 문화권에서 공감을 얻게 만들기 |
| 🗣️ [Developer Advocate](specialized/specialized-developer-advocate.md) | 커뮤니티 구축, DX, 개발자 콘텐츠 | 제품과 개발자 커뮤니티를 잇기 |
| 🔬 [Model QA Specialist](specialized/specialized-model-qa.md) | ML 감사, 피처 분석, 해석 가능성 | 머신러닝 모델의 엔드투엔드 QA |
| 🗃️ [ZK Steward](specialized/zk-steward.md) | 지식 관리, 제텔카스텐, 노트 | 연결되고 검증된 지식 베이스 구축 |
| 🔌 [MCP Builder](specialized/specialized-mcp-builder.md) | Model Context Protocol 서버, AI 에이전트 툴링 | AI 에이전트 역량을 확장하는 MCP 서버 구축 |
| 📄 [Document Generator](specialized/specialized-document-generator.md) | 코드로 PDF, PPTX, DOCX, XLSX 생성 | 전문적인 문서 제작, 리포트, 데이터 시각화 |
| ⚙️ [Automation Governance Architect](specialized/automation-governance-architect.md) | 자동화 거버넌스, n8n, 워크플로 감사 | 대규모 비즈니스 자동화 평가와 거버넌스 |
| 📚 [Corporate Training Designer](specialized/corporate-training-designer.md) | 기업 교육, 커리큘럼 개발 | 교육 체계와 학습 프로그램 설계 |
| 🌱 [Personal Growth Mentor](specialized/personal-growth-mentor.md) | 목표 명확화, 습관 시스템, 책임 관리, 인생 전략 | 자기계발 구호 없이 여러 영역을 아우르는 성장 지원 |
| 🏛️ [Government Digital Presales Consultant](specialized/government-digital-presales-consultant.md) | 중국 ToG 프리세일즈, 디지털 전환 | 정부 디지털 전환 제안과 입찰 |
| ⚕️ [Healthcare Marketing Compliance](specialized/healthcare-marketing-compliance.md) | 중국 의료 광고 규제 준수 | 헬스케어 마케팅 규제 컴플라이언스 |
| 🎯 [Recruitment Specialist](specialized/recruitment-specialist.md) | 인재 확보, 리크루팅 운영 | 채용 전략, 소싱, 채용 프로세스 |
| 🎓 [Study Abroad Advisor](specialized/study-abroad-advisor.md) | 국제 교육, 지원 계획 | 미국·영국·캐나다·호주 유학 계획 |
| 🔗 [Supply Chain Strategist](specialized/supply-chain-strategist.md) | 공급망 관리, 조달 전략 | 공급망 최적화와 조달 기획 |
| 🗺️ [Workflow Architect](specialized/specialized-workflow-architect.md) | 워크플로 발굴, 맵핑, 명세화 | 코드를 쓰기 전에 시스템의 모든 경로를 그려 두기 |
| ☁️ [Salesforce Architect](specialized/specialized-salesforce-architect.md) | 멀티 클라우드 Salesforce 설계, 거버너 리밋, 연동 | 엔터프라이즈 Salesforce 아키텍처, 조직 전략, 배포 파이프라인 |
| 🇫🇷 [French Consulting Market Navigator](specialized/specialized-french-consulting-market.md) | ESN/SI 생태계, 포르타주 살라리알, 단가 포지셔닝 | 프랑스 IT 시장에서의 프리랜스 컨설팅 |
| 🇰🇷 [Korean Business Navigator](specialized/specialized-korean-business-navigator.md) | 한국 비즈니스 문화, 품의 프로세스, 관계의 작동 방식 | 한국 비즈니스 관계를 헤쳐 나가는 외국인 전문가 |
| 🏗️ [Civil Engineer](specialized/specialized-civil-engineer.md) | 구조 해석, 지반 설계, 각국 건축 기준 | Eurocode, ACI, AISC 등 여러 표준을 아우르는 구조 엔지니어링 |
| 🎧 [Customer Service](specialized/customer-service.md) | 옴니채널 지원, 불만 처리, 리텐션, 에스컬레이션 | 모든 업종의 고객 지원 — 리테일, SaaS, 호스피탈리티, 금융, 물류 |
| 🏥 [Healthcare Customer Service](specialized/healthcare-customer-service.md) | HIPAA를 고려한 환자 지원, 수납, 보험, 응급 라우팅 | 규정을 준수하면서 공감하는 환자 지원이 필요한 의료 기관 |
| 🏨 [Hospitality Guest Services](specialized/hospitality-guest-services.md) | 예약, 컨시어지, 불만 회복, 로열티, 이벤트 | 호텔, 리조트, 레스토랑, 이벤트 베뉴 |
| 🤝 [HR Onboarding](specialized/hr-onboarding.md) | 입사 전 준비, 컴플라이언스, 복리후생 등록, 30-60-90일 계획 | 스타트업부터 대기업까지, 신규 입사자를 온보딩하는 모든 회사 |
| 🌐 [Language Translator](specialized/language-translator.md) | 스페인어 ↔ 영어 번역, 방언 인식, 문화적 맥락 | 여행, 비즈니스, 의료, 법률 번역 수요 |
| ⏱️ [Legal Billing & Time Tracking](specialized/legal-billing-time-tracking.md) | 시간 기록, 청구 내역 작성, IOLTA 준수, 수납 | 수익 회수와 청구 정확도를 극대화하는 법무법인 |
| 📋 [Legal Client Intake](specialized/legal-client-intake.md) | 잠재 고객 검증, 이해충돌 심사, 상담 일정 조정 | 문의를 수임 고객으로 전환하는 법무법인 |
| ⚖️ [Legal Document Review](specialized/legal-document-review.md) | 계약 검토, 리스크 표시, 버전 비교, 컴플라이언스 | 모든 업무 분야에서 변호사가 바로 쓸 수 있는 1차 검토 |
| 🏦 [Loan Officer Assistant](specialized/loan-officer-assistant.md) | 차주 접수, TRID 준수, 파이프라인 추적, 클로징 조율 | 모기지 및 소비자 금융 팀 |
| 🏠 [Real Estate Buyer & Seller](specialized/real-estate-buyer-seller.md) | 매수/매도 대리, 오퍼, 거래 조율 | 주거용 및 투자용 부동산 거래 |
| 🛒 [Retail Customer Returns](specialized/retail-customer-returns.md) | 반품 처리, 사기 방지, 교환, 벤더 반품 | 오프라인, 이커머스, 옴니채널 리테일 |
| ♟️ [Business Strategist](specialized/business-strategist.md) | 경영 컨설팅식 전략 | 경쟁 분석, 시장 진입, 성장 기획 |
| 🔄 [Change Management Consultant](specialized/change-management-consultant.md) | ADKAR/Kotter/Prosci 변화 관리 | 조직의 전환과 정착 안내 |
| 🧭 [Chief of Staff](specialized/specialized-chief-of-staff.md) | 경영진 업무 조율 | 노이즈 걸러내기, 프로세스 오너십, 의사결정 라우팅 |
| 🌟 [Customer Success Manager](specialized/customer-success-manager.md) | 온보딩, 헬스 스코어, 리텐션 | QBR, 이탈 방지, 갱신과 확장 |
| 📝 [Grant Writer](specialized/grant-writer.md) | 보조금 제안서와 자금 조달 | 비영리/연구 기관을 위한 LOI, 제안서, 예산 |
| 🏥 [Medical Billing & Coding Specialist](specialized/medical-billing-coding-specialist.md) | ICD-10/CPT/HCPCS와 수익 사이클 | 청구, 거절 관리, RCM 최적화 |
| 💰 [Pricing Analyst](specialized/specialized-pricing-analyst.md) | 가격 모델과 마진 최적화 | 경쟁사/원가 분석, 가치 기반 가격 책정 |
| 💼 [Chief Financial Officer](specialized/chief-financial-officer.md) | 자본 배분과 재무 전략 | 자금 관리, FP&A, M&A 재무, 투자자·이사회 보고 |
| 🌱 [ESG & Sustainability Officer](specialized/esg-sustainability-officer.md) | ESG 프로그램과 정보 공시 | 지속가능성 전략, 탈탄소화, 보고 |
| 🔐 [Data Privacy Officer](specialized/data-privacy-officer.md) | GDPR/CCPA 프라이버시 컴플라이언스 | 데이터 매핑, DPIA, 동의, 침해 대응 |
| ⚙️ [Operations Manager](specialized/operations-manager.md) | 린/식스 시그마 운영 | 프로세스 맵핑, 용량 계획, KPI 거버넌스 |
| 🤝 [M&A Integration Manager](specialized/ma-integration-manager.md) | 인수 후 통합 | Day 1·100일 계획, 시너지 추적, TSA 관리 |
| 🧠 [Organizational Psychologist](specialized/organizational-psychologist.md) | 팀 역학과 조직 문화 건강도 | 심리적 안전감, 번아웃 리스크, 고성과 팀 |
| ⚔️ [Strategy Duel Agent](specialized/specialized-strategy-duel-agent.md) | 게임 이론과 36계 | 턴제 전략 대결, 적대적 시나리오 시뮬레이션 |
| 🛡️ [FedRAMP & RMF Compliance Engineer](specialized/specialized-fedramp-rmf-compliance.md) | 미 연방 클라우드 승인(ATO) | NIST 800-53, FedRAMP Rev5/20x, SSP/POA&M, ConMon, OSCAL |
| 🏺 [Codebase Archaeologist](specialized/specialized-codebase-archaeologist.md) | 멀티 도구 코드베이스 드리프트 감사 | Claude/Cursor/Copilot/Windsurf 편집 전반의 조용한 드리프트 탐지 |
| 🧾 [Resume Tailor](specialized/resume-tailor.md) | 지원자 관점의 이력서 최적화 | JD 매핑, ATS 키워드 정렬, 경력과 요건 매칭 |
| 🧡 [Aging Parent Care Companion](specialized/healthcare-aging-parent-care-companion.md) | 가족 간병인 의사결정 지원 | 진료·복약 조율, 케어팀 커뮤니케이션, 간병인 웰빙 (HIPAA 준수 지향) |
| 🏛️ [Master Plan Architect](specialized/specialized-master-plan-architect.md) | 아키텍처 교육, 레드팀식 계획 비판 | 깊이 있는 아키텍처 교육, 리스크 비판, 종합적인 마크다운 구현 계획 (코드 실행 없음) |
| 🎧 [Focus Music Architect](specialized/specialized-focus-music-architect.md) | 집중용 인스트루멘털 음악 프롬프트 엔지니어링, 뉴로어쿠스틱스 | 사운드스케이프 설계, BPM 커브, 생성형 오디오 모델용 바이노럴 레이어 |

### 💵 파이낸스 디비전

회계, 재무 분석, 세무 전략, 투자 리서치 전문가들입니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 📒 [Bookkeeper & Controller](finance/finance-bookkeeper-controller.md) | 월말 결산, 계정 대조, GAAP 준수, 내부 통제 | 일상 회계 업무, 감사 대비, 재무 기록 관리 |
| 📊 [Financial Analyst](finance/finance-financial-analyst.md) | 재무 모델링, 예측, 시나리오 분석, 의사결정 지원 | 3표 연계 모델, 차이 분석, 데이터 기반 비즈니스 인텔리전스 |
| 📈 [FP&A Analyst](finance/finance-fpa-analyst.md) | 예산 수립, 롤링 포캐스트, 차이 분석, 비즈니스 리뷰 | 연간 운영 계획, 월간 비즈니스 리뷰, 전략적 자원 배분 |
| 🔍 [Investment Researcher](finance/finance-investment-researcher.md) | 실사, 포트폴리오 분석, 자산 평가, 주식 리서치 | 투자 논리 개발, 리스크 평가, 시장 조사 |
| 🏛️ [Tax Strategist](finance/finance-tax-strategist.md) | 세무 최적화, 다국가 컴플라이언스, 이전가격 | 법인 구조 설계, ETR 분석, 세무조사 대응, 전략적 세무 기획 |

### 🎮 게임 개발 디비전

주요 엔진 전반에서 세계와 시스템, 경험을 만듭니다.

#### 엔진 공통 에이전트 (엔진 무관)

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🎯 [Game Designer](game-development/game-designer.md) | 시스템 설계, GDD 작성, 경제 밸런싱, 게임플레이 루프 | 게임 메커닉과 성장 시스템 설계, 디자인 문서 작성 |
| 🗺️ [Level Designer](game-development/level-designer.md) | 레이아웃 이론, 페이싱, 인카운터 설계, 환경 스토리텔링 | 레벨 제작, 인카운터 흐름 설계, 공간 내러티브 |
| 🎨 [Technical Artist](game-development/technical-artist.md) | 셰이더, VFX, LOD 파이프라인, 아트→엔진 최적화 | 아트와 엔지니어링 잇기, 셰이더 작성, 성능 안전한 에셋 파이프라인 |
| 🔊 [Game Audio Engineer](game-development/game-audio-engineer.md) | FMOD/Wwise, 적응형 음악, 공간 음향, 오디오 예산 | 인터랙티브 오디오 시스템, 동적 음악, 오디오 성능 |
| 📖 [Narrative Designer](game-development/narrative-designer.md) | 스토리 시스템, 분기 대화, 로어 아키텍처 | 분기 내러티브 작성, 대화 시스템 구현, 세계관 로어 |
| 💰 [Economy Designer](game-development/economy-designer.md) | 가상 화폐, 소스/싱크, 수익화 모델링, 인플레이션 통제 | 인게임 경제 설계, F2P 수익화 밸런싱, 라이브 경제 튜닝 |

#### Unity

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🏗️ [Unity Architect](game-development/unity/unity-architect.md) | ScriptableObject, 데이터 주도 모듈화, DOTS/ECS | 대규모 Unity 프로젝트, 데이터 주도 시스템 설계, ECS 성능 작업 |
| ✨ [Unity Shader Graph Artist](game-development/unity/unity-shader-graph-artist.md) | Shader Graph, HLSL, URP/HDRP, Renderer Feature | 커스텀 Unity 머티리얼, VFX 셰이더, 포스트 프로세싱 패스 |
| 🌐 [Unity Multiplayer Engineer](game-development/unity/unity-multiplayer-engineer.md) | Netcode for GameObjects, Unity Relay/Lobby, 서버 권한, 예측 | 온라인 Unity 게임, 클라이언트 예측, Unity Gaming Services 연동 |
| 🛠️ [Unity Editor Tool Developer](game-development/unity/unity-editor-tool-developer.md) | EditorWindow, AssetPostprocessor, PropertyDrawer, 빌드 검증 | 커스텀 Unity 에디터 툴링, 파이프라인 자동화, 콘텐츠 검증 |

#### Unreal Engine

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| ⚙️ [Unreal Systems Engineer](game-development/unreal-engine/unreal-systems-engineer.md) | C++/블루프린트 혼용, GAS, Nanite 제약, 메모리 관리 | 복잡한 Unreal 게임플레이 시스템, Gameplay Ability System, 엔진 수준 C++ |
| 🎨 [Unreal Technical Artist](game-development/unreal-engine/unreal-technical-artist.md) | Material Editor, Niagara, PCG, Substrate | Unreal 머티리얼, Niagara VFX, 절차적 콘텐츠 생성 |
| 🌐 [Unreal Multiplayer Architect](game-development/unreal-engine/unreal-multiplayer-architect.md) | 액터 리플리케이션, GameMode/GameState 계층, 데디케이티드 서버 | Unreal 온라인 게임, 리플리케이션 그래프, 서버 권한 기반 Unreal |
| 🗺️ [Unreal World Builder](game-development/unreal-engine/unreal-world-builder.md) | World Partition, 랜드스케이프, HLOD, LWC | 대규모 오픈월드 Unreal 레벨, 스트리밍 시스템, 대규모 지형 |

#### Godot

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 📜 [Godot Gameplay Scripter](game-development/godot/godot-gameplay-scripter.md) | GDScript 2.0, 시그널, 컴포지션, 정적 타이핑 | Godot 게임플레이 시스템, 씬 컴포지션, 성능을 고려한 GDScript |
| 🌐 [Godot Multiplayer Engineer](game-development/godot/godot-multiplayer-engineer.md) | MultiplayerAPI, ENet/WebRTC, RPC, 권한 모델 | 온라인 Godot 게임, 씬 리플리케이션, 서버 권한 기반 Godot |
| ✨ [Godot Shader Developer](game-development/godot/godot-shader-developer.md) | Godot 셰이딩 언어, VisualShader, RenderingDevice | 커스텀 Godot 머티리얼, 2D/3D 이펙트, 포스트 프로세싱, 컴퓨트 셰이더 |

#### Blender

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🧩 [Blender Addon Engineer](game-development/blender/blender-addon-engineer.md) | Blender Python(`bpy`), 커스텀 오퍼레이터/패널, 에셋 검증기, 익스포터, 파이프라인 자동화 | Blender 애드온 제작, 에셋 준비 도구, 익스포트 워크플로, DCC 파이프라인 자동화 |

#### Roblox Studio

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| ⚙️ [Roblox Systems Scripter](game-development/roblox-studio/roblox-systems-scripter.md) | Luau, RemoteEvent/Function, DataStore, 서버 권한 모듈 아키텍처 | 안전한 Roblox 게임 시스템 구축, 클라이언트-서버 통신, 데이터 영속성 |
| 🎯 [Roblox Experience Designer](game-development/roblox-studio/roblox-experience-designer.md) | 인게이지먼트 루프, 수익화, D1/D7 리텐션, 온보딩 플로 | Roblox 게임 루프, 게임 패스, 일일 보상, 플레이어 리텐션 설계 |
| 👗 [Roblox Avatar Creator](game-development/roblox-studio/roblox-avatar-creator.md) | UGC 파이프라인, 액세서리 리깅, Creator Marketplace 등록 | Roblox UGC 아이템, HumanoidDescription 커스터마이징, 경험 내 아바타 숍 |

### 📚 아카데믹 디비전

세계관 구축, 스토리텔링, 내러티브 설계에 학술적 엄밀함을 더합니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🌍 [Anthropologist](academic/academic-anthropologist.md) | 문화 체계, 친족 관계, 의례, 신앙 체계 | 내적 논리를 갖춘, 문화적으로 일관된 사회 설계 |
| 🌐 [Geographer](academic/academic-geographer.md) | 자연·인문 지리, 기후, 지도학 | 현실적인 지형과 정착지를 갖춘 지리적으로 일관된 세계 구축 |
| 📚 [Historian](academic/academic-historian.md) | 역사 분석, 시대 구분, 물질 문화 | 역사적 일관성 검증, 시대에 맞는 진짜 디테일로 배경 풍부하게 하기 |
| 📜 [Narratologist](academic/academic-narratologist.md) | 서사 이론, 이야기 구조, 캐릭터 아크 | 정립된 이론적 틀로 이야기 구조 분석·개선 |
| 🧠 [Psychologist](academic/academic-psychologist.md) | 성격 이론, 동기, 인지 패턴 | 연구에 기반한 심리적으로 설득력 있는 캐릭터 구축 |
| 📊 [Statistician](academic/academic-statistician.md) | 통계적 추론과 실험 설계 | 가설 검정, 인과 추론, 표본 설계, 엄밀한 분석 |

---

### 🌍 GIS 디비전

지구를 지도로 옮기고, 건설된 세계를 분석하고, 지리공간 데이터에서 인텔리전스를 뽑아냅니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🧠 [Technical Consultant](gis/gis-technical-consultant.md) | GIS 전략, 격차 분석, 기술 로드맵, 디지털 전환 | 비즈니스 요구 파악, 적합한 지리공간 스택 선정, 다단계 GIS 프로그램 기획 |
| 🔧 [Solution Engineer](gis/gis-solution-engineer.md) | Esri + FOSS4G 프로토타입 제작, PoC 전달, 기술 타당성 | 동작하는 데모 제작, 기술 접근 검증, 프리세일즈 지원 |
| 🖥️ [GIS Analyst](gis/gis-analyst.md) | 지도 제작, 데이터 QC, 심볼로지, 레이아웃, 공간 질의 | 일상적인 GIS 업무, 발행 가능한 품질의 지도 제작, 데이터 정합성 유지 |
| 📦 [Spatial Data Engineer](gis/gis-spatial-data-engineer.md) | 지리공간 ETL, 포맷 변환, CRS 재투영, 자동화 파이프라인 | 출처가 다양한 지저분한 데이터 수집, 반복 가능한 데이터 변환 파이프라인 구축 |
| ⚙️ [Geoprocessing Specialist](gis/gis-geoprocessing-specialist.md) | ArcPy, Python Toolbox(.pyt), Model Builder, 배치 자동화 | 반복적인 GIS 워크플로 자동화, 커스텀 지오프로세싱 도구 제작 |
| ✅ [GIS QA Engineer](gis/gis-qa-engineer.md) | 토폴로지 검증, 메타데이터 감사, CRS 일관성, 정확도 평가 | 데이터 발행 전 품질 게이트, 규정 준수 확인, 데이터 정합성 감사 |
| 🤖 [GeoAI/ML Engineer](gis/gis-geoai-ml-engineer.md) | 피처 추출, 객체 탐지, 시맨틱 분할, 토지 피복 분류 | 영상에서 건물/도로/차량 추출, 변화 탐지, 환경 모니터링 |
| 🏗️ [BIM/GIS Specialist](gis/gis-bim-specialist.md) | Revit/IFC → GIS, 실내 매핑, 디지털 트윈 아키텍처, 시설 관리 | 스마트 캠퍼스, 공항 디지털 트윈, 실내 내비게이션, 건물 운영 |
| 🏔️ [3D & Scene Developer](gis/gis-3d-scene-developer.md) | Cesium, ArcGIS Scene Viewer, 3D Tiles, 포인트 클라우드, 지형 시각화 | 3D 도시 씬, 지형 플라이오버, 포인트 클라우드 웹 뷰어, OAuth로 보호된 씬 공유 |
| 📊 [Spatial Data Scientist](gis/gis-spatial-data-scientist.md) | 공간 통계, 클러스터링, 회귀, 보간, 점 패턴 분석 | 핫스팟 탐지, 공간 모델링, 예측 분석, 연구 수준의 분석 |
| 🛸 [Drone/Reality Mapping](gis/gis-drone-reality-mapping.md) | 사진측량, 정사영상, DTM/DSM, 포인트 클라우드 분류, 3D 메시 | 드론 측량 처리, 리얼리티 캡처, 건설 현장 모니터링, 환경 매핑 |
| 🌐 [Web GIS Developer](gis/gis-web-gis-developer.md) | MapLibre GL JS, ArcGIS JS API, Leaflet, 실시간 대시보드, REST API | 인터랙티브 웹 지도, 운영 대시보드, 실시간 데이터 시각화 구축 |
| 🎨 [Cartography Designer](gis/gis-cartography-designer.md) | 색채 이론, 타이포그래피, 베이스맵 디자인, 시각적 위계, 인쇄·웹 미감 | 아름답고 읽기 쉬운 지도, 색각 이상 안전 팔레트, 전문적인 지도 레이아웃 |

---

### 🏥 헬스케어 디비전

규제가 적용되는 임상 환경과 국가 주도 보건 맥락을 위한 AI 에이전트를 만듭니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🩺 [Clinical Evidence Agent](healthcare/healthcare-clinical-evidence-agent.md) | 근거 기준, 검증된 주장과 검증되지 않은 주장, 진단 권한의 경계 | 진단 권한을 넘지 않으면서 임상적 주장을 신뢰성 있게 제시하기 |
| 🌍 [Sovereign Health Systems Agent](healthcare/healthcare-sovereign-health-systems-agent.md) | 정부 보건 정책 의무, UHC 정책, 신흥시장 도입 | 국가 보건 인프라와 주권적 보건 정책이 교차하는 지점에서 일하는 헬스테크 팀 |
| 🧭 [Healthcare Innovation Strategist](healthcare/healthcare-innovation-strategist.md) | 투자자·규제기관·정부·임상 청중을 아우르는 헬스케어 창업자용 내러티브 설계 | 임상적·재무적 복잡성을 자본을 움직이고 신뢰를 쌓는 언어로 번역해야 하는 헬스케어 창업자 |

---

### 🔍 리서치 디비전

새로운 1차 데이터를 만들기보다, 기존 근거를 찾아 평가하고 종합합니다.

| 에이전트 | 전문 분야 | 사용 시점 |
|-------|-----------|-------------|
| 🔍 [Research Synthesist](research/research-synthesist.md) | 문헌 검토, 출처 평가, 인용 추적, 근거 종합 | 흩어진 자료 더미를 근거가 뒷받침하는 바에 대한 구조적이고 정직하게 가중된 지도로 바꾸기 |

---
## 🎯 실제 활용 사례

### 시나리오 1: 스타트업 MVP 만들기

**팀 구성**:
1. 🎨 **Frontend Developer** - React 앱 구축
2. 🏗️ **Backend Architect** - API와 데이터베이스 설계
3. 🚀 **Growth Hacker** - 유저 확보 계획
4. ⚡ **Rapid Prototyper** - 빠른 반복 사이클
5. 🔍 **Reality Checker** - 출시 전 품질 확보

**결과**: 모든 단계에 전문성이 붙어 더 빠르게 출시합니다.

---

### 시나리오 2: 마케팅 캠페인 런치

**팀 구성**:
1. 📝 **Content Creator** - 캠페인 콘텐츠 개발
2. 🐦 **Twitter Engager** - 트위터 전략과 실행
3. 📸 **Instagram Curator** - 비주얼 콘텐츠와 스토리
4. 🤝 **Reddit Community Builder** - 진정성 있는 커뮤니티 참여
5. 📊 **Analytics Reporter** - 성과 추적과 최적화

**결과**: 플랫폼별 전문성을 갖춘 멀티채널 통합 캠페인이 완성됩니다.

---

### 시나리오 3: 엔터프라이즈 기능 개발

**팀 구성**:
1. 👔 **Senior Project Manager** - 범위 설정과 태스크 기획
2. 💎 **Senior Developer** - 복잡한 구현
3. 🎨 **UI Designer** - 디자인 시스템과 컴포넌트
4. 🧪 **Experiment Tracker** - A/B 테스트 기획
5. 📸 **Evidence Collector** - 품질 검증
6. 🔍 **Reality Checker** - 프로덕션 준비도 확인

**결과**: 품질 게이트와 문서를 갖춘 엔터프라이즈급 딜리버리가 나옵니다.

---

### 시나리오 4: 유료 미디어 계정 인수

**팀 구성**:

1. 📋 **Paid Media Auditor** - 종합적인 계정 진단
2. 📡 **Tracking & Measurement Specialist** - 전환 추적 정확도 검증
3. 💰 **PPC Campaign Strategist** - 계정 구조 재설계
4. 🔍 **Search Query Analyst** - 검색어에서 낭비되는 지출 정리
5. ✍️ **Ad Creative Strategist** - 모든 광고 카피와 확장 소재 교체
6. 📊 **Analytics Reporter** (서포트 디비전) - 리포팅 대시보드 구축

**결과**: 추적 검증, 낭비 제거, 구조 최적화, 크리에이티브 리프레시까지 — 첫 30일 안에 체계적인 계정 인수를 끝냅니다.

---

### 시나리오 5: 에이전시 전체가 참여하는 제품 디스커버리

**팀 구성**: 8개 디비전이 하나의 미션을 두고 동시에 움직입니다.

**[Nexus Spatial Discovery Exercise](examples/nexus-spatial-discovery.md)**를 보세요. 8명의 에이전트(Product Trend Researcher, Backend Architect, Brand Guardian, Growth Hacker, Support Responder, UX Researcher, Project Shepherd, XR Interface Architect)를 동시에 투입해 소프트웨어 기회를 평가하고, 시장 검증부터 기술 아키텍처, 브랜드 전략, 고 투 마켓, 서포트 체계, UX 리서치, 프로젝트 실행, 공간 UI 디자인까지 아우르는 통합 제품 계획을 만든 완전한 예시입니다.

**결과**: 단 한 세션에서 직능을 넘나드는 종합 제품 설계도가 나옵니다. [더 많은 예시](examples/).

---

### 시나리오 6: 스마트 캠퍼스 디지털 트윈

**팀 구성**:

1. 🧠 **Technical Consultant** - 디지털 트윈 전략 정의: 건물은 BIM, 캠퍼스는 GIS, 실시간은 IoT
2. 🏗️ **BIM/GIS Specialist** - Revit 건물 모델을 GIS 씬 레이어로 변환, 실내 평면도 설계
3. 🛸 **Drone/Reality Mapping** - 캠퍼스 비행 촬영, 맥락 제공용 정사영상과 3D 메시 생성
4. 🌐 **Web GIS Developer** - MapLibre, 건물 레이어, 강의실 찾기 기능을 갖춘 캠퍼스 대시보드 구축
5. 🏔️ **3D & Scene Developer** - 지형, 건물, 플라이오버 투어가 담긴 몰입형 3D 씬 제작
6. 🤖 **GeoAI/ML Engineer** - 드론 영상에서 건물 외곽선과 수목 캐노피 추출
7. ✅ **GIS QA Engineer** - 데이터 정확도 검증, 토폴로지 점검, CRS 일관성 확인

**결과**: BIM의 디테일, 드론 리얼리티 캡처, 3D 시각화, 웹 접근성을 결합한 캠퍼스 디지털 트윈을 전문가들이 하나의 파이프라인으로 조율해 완성합니다.

---

## 🤝 기여하기

기여를 환영합니다! 이렇게 도울 수 있습니다.

### 새 에이전트 추가

1. 리포지토리를 포크합니다
2. 적합한 카테고리에 새 에이전트 파일을 만듭니다
3. 에이전트 템플릿 구조를 따릅니다:
   - name, description, color가 담긴 프론트매터
   - Identity & Memory 섹션
   - Core Mission
   - Critical Rules (도메인별)
   - 예시가 포함된 Technical Deliverables
   - Workflow Process
   - Success Metrics
4. 에이전트와 함께 PR을 제출합니다

### 기존 에이전트 개선

- 실제 사례 추가
- 코드 샘플 보강
- 성공 지표 업데이트
- 워크플로 개선

### 성공 사례 공유

이 에이전트들을 성공적으로 활용하셨나요? [Discussions](https://github.com/msitarzewski/agency-agents/discussions)에서 이야기를 들려주세요!

---

## 📖 에이전트 설계 철학

각 에이전트는 다음을 염두에 두고 설계했습니다.

1. **🎭 강한 개성**: 일반적인 템플릿이 아니라, 진짜 캐릭터와 목소리
2. **📋 명확한 산출물**: 막연한 조언이 아니라 구체적인 결과물
3. **✅ 성공 지표**: 측정 가능한 성과와 품질 기준
4. **🔄 검증된 워크플로**: 실제로 통하는 단계별 프로세스
5. **💡 학습 메모리**: 패턴 인식과 지속적인 개선

---

## 🎁 무엇이 특별한가요?

### 일반적인 AI 프롬프트와 달리:
- ❌ "개발자처럼 행동해" 같은 뻔한 프롬프트
- ✅ 개성과 프로세스를 갖춘 깊은 전문성

### 프롬프트 라이브러리와 달리:
- ❌ 일회성 프롬프트 모음
- ✅ 워크플로와 산출물을 갖춘 종합적인 에이전트 시스템

### AI 도구와 달리:
- ❌ 커스터마이징할 수 없는 블랙박스 도구
- ✅ 투명하고, 포크할 수 있고, 변형할 수 있는 에이전트 페르소나

---

## 🎨 에이전트 개성 하이라이트

> "저는 코드를 그냥 테스트하지 않습니다. 기본적으로 3~5개의 문제를 찾아내고, 모든 것에 시각적 증거를 요구합니다."
>
> -- **Evidence Collector** (테스팅 디비전)

> "당신은 레딧에서 마케팅을 하는 게 아닙니다. 마침 브랜드를 대표하게 된, 커뮤니티가 소중히 여기는 구성원이 되는 겁니다."
>
> -- **Reddit Community Builder** (마케팅 디비전)

> "모든 장난기 있는 요소는 기능적이거나 정서적인 목적을 가져야 합니다. 주의를 흐트러뜨리지 않고 더해 주는 즐거움을 디자인하세요."
>
> -- **Whimsy Injector** (디자인 디비전)

> "작업 완료 불안을 40% 줄여 주는 축하 애니메이션을 하나 넣어 볼게요"
>
> -- **Whimsy Injector** (UX 리뷰 중)

---

## 📊 통계

- 🎭 디비전 전체에 걸친 **230개 이상의 전문 에이전트**
- 📝 개성, 프로세스, 코드 예시 **1만 줄 이상**
- ⏱️ 실제 사용에서 나온 **수개월의 반복 개선**
- 🌟 프로덕션 환경에서 **실전 검증**
- 💬 레딧 공개 후 **첫 12시간 동안 50건 이상의 요청**

---

## 🔌 멀티 도구 통합

The Agency는 Claude Code에서 기본으로 동작하며, 변환·설치 스크립트를 함께 제공해 주요 에이전틱 코딩 도구 전반에서 같은 에이전트를 쓸 수 있게 해 줍니다.

### 지원 도구

- **[Claude Code](https://claude.ai/code)** — 네이티브 `.md` 에이전트, 변환 불필요 → `~/.claude/agents/`
- **[GitHub Copilot](https://github.com/copilot)** — 네이티브 `.md` 에이전트, 변환 불필요 → `~/.github/agents/` + `~/.copilot/agents/`
- **[Antigravity](https://github.com/google-gemini/antigravity)** — 에이전트별 `SKILL.md` → `~/.gemini/config/skills/`
- **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** -- `.md` 에이전트 파일 -> `~/.gemini/agents/`
- **[OpenCode](https://opencode.ai)** — `.md` 에이전트 파일 → `.opencode/agents/`
- **[Cursor](https://cursor.sh)** — `.mdc` 룰 파일 → `.cursor/rules/`
- **[Aider](https://aider.chat)** — 단일 `CONVENTIONS.md` → `./CONVENTIONS.md`
- **[Windsurf](https://codeium.com/windsurf)** — 단일 `.windsurfrules` → `./.windsurfrules`
- **[OpenClaw](https://github.com/openclaw/openclaw)** — 에이전트별 `SOUL.md` + `AGENTS.md` + `IDENTITY.md`
- **[Qwen Code](https://github.com/QwenLM/qwen-code)** — `.md` SubAgent 파일 → `~/.qwen/agents/`
- **[Kimi Code](https://github.com/MoonshotAI/kimi-cli)** — YAML 에이전트 스펙 → `~/.config/kimi/agents/`
- **[Codex](https://developers.openai.com/codex/overview)** — TOML 커스텀 에이전트 → `~/.codex/agents/`
- **Osaurus** -- `SKILL.md` 스킬 -> `~/.osaurus/skills/`
- **[Hermes](integrations/hermes/README.md)** -- 지연 라우터 플러그인 -> `~/.hermes/plugins/`

---

### ⚡ 빠른 설치

**1단계 -- 통합 파일 생성:**
```bash
./scripts/convert.sh
# 더 빠르게 (병렬 처리, 출력 순서는 달라질 수 있음): ./scripts/convert.sh --parallel
```

**2단계 -- 설치 (대화형, 설치된 도구를 자동 감지):**
```bash
./scripts/install.sh
# 더 빠르게 (병렬 처리, 출력 순서는 달라질 수 있음): ./scripts/install.sh --no-interactive --parallel
```

설치 스크립트가 시스템에 설치된 도구를 탐색해 체크박스 UI를 보여 주고, 설치할 항목을 정확히 고르게 해 줍니다.

```
  +------------------------------------------------+
  |   The Agency -- Tool Installer                 |
  +------------------------------------------------+

  System scan: [*] = detected on this machine

  [x]  1)  [*]  Claude Code     (claude.ai/code)
  [x]  2)  [*]  Copilot         (~/.github + ~/.copilot)
  [x]  3)  [*]  Antigravity     (~/.gemini/antigravity)
  [ ]  4)  [ ]  Gemini CLI      (~/.gemini/agents)
  [ ]  5)  [ ]  OpenCode        (opencode.ai)
  [ ]  6)  [ ]  OpenClaw        (~/.openclaw/agency-agents)
  [x]  7)  [*]  Cursor          (.cursor/rules)
  [ ]  8)  [ ]  Aider           (CONVENTIONS.md)
  [ ]  9)  [ ]  Windsurf        (.windsurfrules)
  [ ] 10)  [ ]  Qwen Code       (~/.qwen/agents)
  [ ] 11)  [ ]  Kimi Code       (~/.config/kimi/agents)
  [ ] 12)  [ ]  Codex           (~/.codex/agents)
  [ ] 13)  [ ]  Osaurus         (~/.osaurus/skills)
  [ ] 14)  [ ]  Hermes          (~/.hermes/plugins)

  [1-14] toggle   [a] all   [n] none   [d] detected
  [Enter] install   [q] quit
```

**또는 특정 도구를 직접 설치:**
```bash
./scripts/install.sh --tool cursor
./scripts/install.sh --tool opencode
./scripts/install.sh --tool openclaw
./scripts/install.sh --tool antigravity
./scripts/install.sh --tool codex
./scripts/install.sh --tool osaurus
./scripts/install.sh --tool hermes
```

**비대화형 (CI/스크립트):**
```bash
./scripts/install.sh --no-interactive --tool all
```

**더 빠른 실행 (병렬)** — 멀티코어 머신에서는 `--parallel`을 써서 도구별로 병렬 처리하세요. 도구 간 출력 순서는 비결정적입니다. 대화형과 비대화형 설치 모두에서 동작합니다. 예: `./scripts/install.sh --interactive --parallel`(도구를 고른 뒤 병렬 설치) 또는 `./scripts/install.sh --no-interactive --parallel`. 작업 수는 기본적으로 `nproc`(Linux), `sysctl -n hw.ncpu`(macOS), 또는 4를 따르며, `--jobs N`으로 덮어쓸 수 있습니다.

```bash
./scripts/convert.sh --parallel                    # 모든 도구를 병렬로 변환
./scripts/convert.sh --parallel --jobs 8           # 병렬 작업 수 제한
./scripts/install.sh --no-interactive --parallel   # 감지된 모든 도구를 병렬로 설치
./scripts/install.sh --interactive --parallel      # 도구를 고른 뒤 병렬로 설치
./scripts/install.sh --no-interactive --parallel --jobs 4
```

---

### 도구별 사용법

<details>
<summary><strong>Claude Code</strong></summary>

에이전트가 리포지토리에서 `~/.claude/agents/`로 그대로 복사됩니다 — 변환이 필요 없습니다.

```bash
./scripts/install.sh --tool claude-code
```

그다음 Claude Code에서 활성화합니다:
```
Use the Frontend Developer agent to review this component.
```

자세한 내용은 [integrations/claude-code/README.md](integrations/claude-code/README.md)를 참고하세요.
</details>

<details>
<summary><strong>GitHub Copilot</strong></summary>

에이전트가 리포지토리에서 `~/.github/agents/`와 `~/.copilot/agents/`로 그대로 복사됩니다 — 변환이 필요 없습니다.

```bash
./scripts/install.sh --tool copilot
```

그다음 GitHub Copilot에서 활성화합니다:
```
Use the Frontend Developer agent to review this component.
```

자세한 내용은 [integrations/github-copilot/README.md](integrations/github-copilot/README.md)를 참고하세요.
</details>

<details>
<summary><strong>Antigravity (Gemini)</strong></summary>

각 에이전트가 `~/.gemini/config/skills/agency-<slug>/`의 스킬이 됩니다.

```bash
./scripts/install.sh --tool antigravity
```

Antigravity가 적용된 Gemini에서 활성화합니다:
```
@agency-frontend-developer review this React component
```

자세한 내용은 [integrations/antigravity/README.md](integrations/antigravity/README.md)를 참고하세요.
</details>

<details>
<summary><strong>Gemini CLI</strong></summary>

Gemini CLI 서브에이전트로 설치됩니다.
새로 클론한 경우, 설치 스크립트를 실행하기 전에 Gemini 에이전트 파일을 먼저 생성하세요.

```bash
./scripts/convert.sh --tool gemini-cli
./scripts/install.sh --tool gemini-cli
```

자세한 내용은 [integrations/gemini-cli/README.md](integrations/gemini-cli/README.md)를 참고하세요.
</details>

<details>
<summary><strong>OpenCode</strong></summary>

에이전트가 프로젝트 루트의 `.opencode/agents/`에 설치됩니다(프로젝트 범위).

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool opencode
```

또는 전역으로 설치:
```bash
mkdir -p ~/.config/opencode/agents
cp integrations/opencode/agents/*.md ~/.config/opencode/agents/
```

OpenCode에서 활성화합니다:
```
@backend-architect design this API.
```

자세한 내용은 [integrations/opencode/README.md](integrations/opencode/README.md)를 참고하세요.
</details>

<details>
<summary><strong>Cursor</strong></summary>

각 에이전트가 프로젝트의 `.cursor/rules/`에 `.mdc` 룰 파일로 만들어집니다.

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool cursor
```

Cursor가 프로젝트에서 룰을 감지하면 자동으로 적용됩니다. 명시적으로 참조하려면:
```
Use the @security-engineer rules to review this code.
```

자세한 내용은 [integrations/cursor/README.md](integrations/cursor/README.md)를 참고하세요.
</details>

<details>
<summary><strong>Aider</strong></summary>

모든 에이전트가 하나의 `CONVENTIONS.md` 파일로 컴파일되며, Aider가 이를 자동으로 읽습니다.

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool aider
```

그다음 Aider 세션에서 에이전트를 참조합니다:
```
Use the Frontend Developer agent to refactor this component.
```

자세한 내용은 [integrations/aider/README.md](integrations/aider/README.md)를 참고하세요.
</details>

<details>
<summary><strong>Windsurf</strong></summary>

모든 에이전트가 프로젝트 루트의 `.windsurfrules`로 컴파일됩니다.

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool windsurf
```

Windsurf의 Cascade에서 에이전트를 참조합니다:
```
Use the Reality Checker agent to verify this is production ready.
```

자세한 내용은 [integrations/windsurf/README.md](integrations/windsurf/README.md)를 참고하세요.
</details>

<details>
<summary><strong>OpenClaw</strong></summary>

각 에이전트가 `~/.openclaw/agency-agents/` 안에서 `SOUL.md`, `AGENTS.md`, `IDENTITY.md`를 갖춘 워크스페이스가 됩니다.

```bash
./scripts/convert.sh --tool openclaw
./scripts/install.sh --tool openclaw
```

`openclaw` CLI를 쓸 수 있는 환경이면 설치 스크립트가 각 워크스페이스를 자동으로 등록합니다.
설치 후 `openclaw gateway restart`를 실행해 새 에이전트를 활성화하세요.

자세한 내용은 [integrations/openclaw/README.md](integrations/openclaw/README.md)를 참고하세요.

</details>

<details>
<summary><strong>Qwen Code</strong></summary>

SubAgent가 프로젝트 루트의 `.qwen/agents/`에 설치됩니다(프로젝트 범위).

```bash
# 변환 후 설치 (프로젝트 루트에서 실행)
cd /your/project
./scripts/convert.sh --tool qwen
./scripts/install.sh --tool qwen
```

**Qwen Code에서 사용하기:**
- 이름으로 참조: `Use the frontend-developer agent to review this component`
- 또는 Qwen이 작업 맥락에 따라 자동으로 위임하게 두기
- 대화형 모드에서 `/agents` 명령으로 관리

> 📚 [Qwen SubAgents 문서](https://qwenlm.github.io/qwen-code-docs/en/users/features/sub-agents/)

</details>

<details>
<summary><strong>Kimi Code</strong></summary>

에이전트가 Kimi Code CLI 형식(YAML + 시스템 프롬프트)으로 변환되어 `~/.config/kimi/agents/`에 설치됩니다.

```bash
# 변환 후 설치
./scripts/convert.sh --tool kimi
./scripts/install.sh --tool kimi
```

**Kimi Code와 함께 사용하기:**
```bash
# 에이전트 사용
kimi --agent-file ~/.config/kimi/agents/frontend-developer/agent.yaml

# 프로젝트 안에서
kimi --agent-file ~/.config/kimi/agents/frontend-developer/agent.yaml \
     --work-dir /your/project \
     "Review this React component"
```

자세한 내용은 [integrations/kimi/README.md](integrations/kimi/README.md)를 참고하세요.

</details>

<details>
<summary><strong>Codex</strong></summary>

각 에이전트가 Codex 커스텀 에이전트 TOML 파일로 변환되어 `~/.codex/agents/`에 설치됩니다.

```bash
./scripts/convert.sh --tool codex
./scripts/install.sh --tool codex
```

그다음 Codex에서 커스텀 에이전트를 이름으로 참조합니다:
```
Use the Frontend Developer agent to review this component.
```

자세한 내용은 [integrations/codex/README.md](integrations/codex/README.md)를 참고하세요.
</details>

---

### 변경 후 다시 생성하기

새 에이전트를 추가하거나 기존 에이전트를 수정했다면, 모든 통합 파일을 다시 생성하세요.

```bash
./scripts/convert.sh                    # 전체 다시 생성 (순차)
./scripts/convert.sh --parallel         # 전체 병렬로 다시 생성 (더 빠름)
./scripts/convert.sh --tool codex       # 한 도구만 다시 생성
./scripts/convert.sh --tool cursor      # 한 도구만 다시 생성
```

---

## 🗺️ 로드맵

- [ ] 인터랙티브 에이전트 선택 웹 도구
- [x] 멀티 에이전트 워크플로 예시 -- [examples/](examples/) 참고
- [x] 멀티 도구 통합 스크립트 (Claude Code, GitHub Copilot, Antigravity, Gemini CLI, OpenCode, OpenClaw, Cursor, Aider, Windsurf, Qwen Code, Kimi Code, Codex, Osaurus, Hermes)
- [ ] 에이전트 설계 영상 튜토리얼
- [ ] 커뮤니티 에이전트 마켓플레이스
- [ ] 프로젝트 매칭용 에이전트 "성격 테스트"
- [ ] "이번 주의 에이전트" 쇼케이스 시리즈

---

## 🌐 커뮤니티 번역 및 현지화

커뮤니티가 관리하는 번역과 지역별 적응판입니다. 각각 독립적으로 관리되므로, 포함 범위와 버전 호환성은 해당 리포지토리를 확인하세요.

| 언어 | 관리자 | 링크 | 비고 |
|----------|-----------|------|-------|
| 🇨🇳 简体中文 (zh-CN) | [@jnMetaCode](https://github.com/jnMetaCode) | [agency-agents-zh](https://github.com/jnMetaCode/agency-agents-zh) | 번역된 에이전트 141개 + 중국 시장용 오리지널 46개 |
| 🇨🇳 简体中文 (zh-CN) | [@dsclca12](https://github.com/dsclca12) | [agent-teams](https://github.com/dsclca12/agent-teams) | 빌리빌리, 위챗, 샤오홍슈 현지화가 포함된 독립 번역 |
| 🇧🇷 Português brasileiro (pt-BR) | [@jnMetaCode](https://github.com/jnMetaCode) | [agency-agents-pt-BR](https://github.com/jnMetaCode/agency-agents-pt-BR) | 업스트림 에이전트 184개 번역 완료. 브라질 시장용 PR 환영 |
| 🇷🇺 Русский (ru) | [@jnMetaCode](https://github.com/jnMetaCode) | [agency-agents-ru](https://github.com/jnMetaCode/agency-agents-ru) | 업스트림 에이전트 184개 번역 완료. 러시아 시장용 PR 환영 |
| 🇮🇩 Bahasa Indonesia (id) | [@jnMetaCode](https://github.com/jnMetaCode) | [agency-agents-id](https://github.com/jnMetaCode/agency-agents-id) | 업스트림 에이전트 184개 번역 완료. 인도네시아 시장용 PR 환영 |
| 🇸🇦 العربية (ar) | [@jnMetaCode](https://github.com/jnMetaCode) | [agency-agents-ar](https://github.com/jnMetaCode/agency-agents-ar) | 업스트림 에이전트 184개 번역 완료. 아랍어권 시장용 PR 환영 |
| 🇰🇷 한국어 (ko) | [@jnMetaCode](https://github.com/jnMetaCode) | [agency-agents-ko](https://github.com/jnMetaCode/agency-agents-ko) | 업스트림 에이전트 184개 전체 번역 완료. 한국 특화 PR 환영 |
| 🇯🇵 日本語 (ja-JP) | [@sscodeai](https://github.com/sscodeai) | [agency-agents-ja](https://github.com/sscodeai/agency-agents-ja) | 일본 현지화 에이전트 281개 + 일본 시장용 오리지널 97개 + 워크플로 27개 |
| 🇻🇳 Tiếng Việt (vi-VN) | [@rodonguyen](https://github.com/rodonguyen) | [agency-agents](https://github.com/rodonguyen/agency-agents) | README, 빠른 시작, 자주 쓰는 문서를 중심으로 한 베트남어 초기 현지화 |

번역을 추가하고 싶으신가요? 이슈를 열어 주시면 여기에 링크해 드립니다.

---

## 🔗 관련 자료

- [awesome-openclaw-agents](https://github.com/mergisi/awesome-openclaw-agents) — 커뮤니티가 관리하는 OpenClaw 에이전트 모음집 (이 리포지토리에서 파생)

---

## 📜 라이선스

MIT 라이선스 - 상업적으로든 개인적으로든 자유롭게 사용하세요. 출처 표기는 환영하지만 필수는 아닙니다.

---

## 🙏 감사의 말

AI 에이전트 전문화에 대한 레딧 스레드로 시작한 것이 지금은 꽤 놀라운 것이 되었습니다. **모든 디비전에 걸친 230개 이상의 에이전트**, 그리고 세계 곳곳의 기여자들이 이루는 커뮤니티가 함께하고 있습니다. 이 리포지토리의 모든 에이전트는 누군가 충분히 마음을 써서 쓰고, 테스트하고, 공유했기에 존재합니다.

PR을 열고, 이슈를 남기고, Discussion을 시작하고, 또는 그저 에이전트를 써 보고 무엇이 잘 통했는지 알려 주신 모든 분께 감사합니다. The Agency가 계속 좋아지는 건 여러분 덕분입니다.

---

## 💬 커뮤니티

- **GitHub Discussions**: [성공 사례 공유하기](https://github.com/msitarzewski/agency-agents/discussions)
- **Issues**: [버그 신고 또는 기능 요청](https://github.com/msitarzewski/agency-agents/issues)
- **Reddit**: r/ClaudeAI에서 대화에 참여하세요
- **Twitter/X**: #TheAgency로 공유해 주세요

---

## 🚀 시작하기

1. 위 에이전트들을 **둘러보고** 필요에 맞는 전문가를 찾으세요
2. Claude Code와 연동하려면 에이전트를 `~/.claude/agents/`로 **복사**하세요
3. Claude와의 대화에서 에이전트를 참조해 **활성화**하세요
4. 에이전트의 개성과 워크플로를 필요에 맞게 **커스터마이징**하세요
5. 결과를 **공유**하고 커뮤니티에 기여해 주세요

---

<div align="center">

**🎭 The Agency: 당신의 AI 드림팀이 기다립니다 🎭**

[⭐ 이 리포지토리에 스타 주기](https://github.com/msitarzewski/agency-agents) • [🍴 포크하기](https://github.com/msitarzewski/agency-agents/fork) • [🐛 이슈 신고하기](https://github.com/msitarzewski/agency-agents/issues) • [❤️ 스폰서하기](https://github.com/sponsors/msitarzewski)

커뮤니티가 커뮤니티를 위해 ❤️를 담아 만들었습니다

</div>
