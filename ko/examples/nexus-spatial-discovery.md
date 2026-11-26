# Nexus Spatial: 전사 디스커버리 연습

> **연습 유형:** 멀티 에이전트 제품 디스커버리
> **일자:** 2026년 3월 5일
> **투입 에이전트:** 8명 (동시 투입)
> **소요 시간:** 실제 경과 시간 약 10분
> **목적:** 기회 발굴부터 종합 기획까지, 전사 오케스트레이션을 시연합니다

---

## 목차

1. [기회](#1-기회)
2. [시장 검증](#2-시장-검증)
3. [시스템 아키텍처](#3-시스템-아키텍처)
4. [브랜드 전략](#4-브랜드-전략)
5. [고투마켓과 성장](#5-고투마켓과-성장)
6. [고객 지원 설계도](#6-고객-지원-설계도)
7. [UX 리서치와 디자인 방향](#7-ux-리서치와-디자인-방향)
8. [프로젝트 실행 계획](#8-프로젝트-실행-계획)
9. [공간 인터페이스 아키텍처](#9-공간-인터페이스-아키텍처)
10. [에이전트 간 종합](#10-에이전트-간-종합)

---

## 1. 기회

### 어떻게 발견했는가

여러 출처를 대상으로 한 웹 리서치에서 세 가지 흐름이 한 지점으로 수렴하고 있다는 것을 확인했습니다.

- **AI 인프라/오케스트레이션**은 가장 빠르게 성장하는 소프트웨어 카테고리입니다 (AI 오케스트레이션 시장은 2026년 약 135억 달러 규모, 연평균 성장률 22% 이상)
- **공간 컴퓨팅**(Vision Pro, WebXR)은 성숙해지고 있지만 엔터프라이즈 킬러 앱이 없습니다
- 기존 AI 워크플로 도구(LangSmith, n8n, Flowise, CrewAI)는 모두 **평면 2D 대시보드**입니다

### 컨셉: Nexus Spatial

공간 컴퓨팅 환경의 AI 에이전트 커맨드 센터 — AI 에이전트를 오케스트레이션하고, 모니터링하고, 직접 다룰 수 있는 몰입형 3D 커맨드 센터를 제공하는 VisionOS + WebXR 애플리케이션입니다. 사용자는 에이전트 파이프라인을 3D 노드 그래프로 시각화하고, 공간 패널에서 실시간 출력을 모니터링하고, 3D 공간에서 드래그 앤 드롭으로 워크플로를 구성하고, 공유된 공간 환경에서 협업합니다.

### 왜 이 에이전시가 특별히 유리한가

이 에이전시는 깊은 공간 컴퓨팅 전문성(XR 개발자, VisionOS 엔지니어, Metal 전문가, 인터페이스 아키텍트)과 함께 엔지니어링, 디자인, 마케팅, 운영 전 영역을 갖추고 있습니다. 공간 컴퓨팅 숙련도와 엔터프라이즈 소프트웨어의 엄격함을 동시에 요구하는 제품에서는 좀처럼 보기 힘든 조합입니다.

### 출처

- [Profitable SaaS Ideas 2026 (273K+ Reviews)](https://bigideasdb.com/profitable-saas-micro-saas-ideas-2026)
- [2026 SaaS and AI Revolution: 20 Top Trends](https://fungies.io/the-2026-saas-and-ai-revolution-20-top-trends/)
- [Top 21 Underserved Markets 2026](https://mktclarity.com/blogs/news/list-underserved-niches)
- [Fastest Growing Products 2026 - G2](https://www.g2.com/best-software-companies/fastest-growing)
- [PwC 2026 AI Business Predictions](https://www.pwc.com/us/en/tech-effect/ai-analytics/ai-predictions.html)

---

## 2. 시장 검증

**담당 에이전트:** Product Trend Researcher

### 판정: CONDITIONAL GO — 2D 우선, 공간은 그다음

### 시장 규모

| 세그먼트 | 2026년 규모 | 성장률 |
|---------|-----------|--------|
| AI 오케스트레이션 도구 | $13.5B | 연평균 22.3% |
| 자율 AI 에이전트 | $8.5B | 연평균 45.8%, 2030년까지 $50.3B |
| 확장 현실(XR) | $10.64B | 연평균 40.95% |
| 공간 컴퓨팅 (광의) | $170-220B | 정의에 따라 상이 |

### 경쟁 지형

**AI 에이전트 오케스트레이션 (전부 2D):**

| 도구 | 강점 | UX 공백 |
|------|----------|--------|
| LangChain/LangSmith | 그래프 기반 오케스트레이션, 사용자당 월 $39 | 평면 대시보드. 그래프가 커지면 읽을 수 없음 |
| CrewAI | 10만 명 이상의 개발자, 빠른 실행 | CLI 우선, 시각적 도구가 빈약 |
| Microsoft Agent Framework | 엔터프라이즈 통합 | Azure 포털에 내장, 독립 UI 없음 |
| n8n | 비주얼 워크플로 빌더, 월 $20-50 | 2D 캔버스가 에이전트 간 관계를 담아내지 못함 |
| Flowise | 드래그 앤 드롭 AI 플로 | 선형 플로에 한정, 멀티 에이전트 모니터링 없음 |

**"미션 컨트롤" 제품군 (신규 등장, 전부 2D):**
- cmd-deck: AI 코딩 에이전트용 칸반 보드
- Supervity Agent Command Center: 엔터프라이즈 옵저버빌리티
- OpenClaw Command Center: 에이전트 플릿 관리
- Mission Control AI: 합성 워커 관리
- Mission Control HQ: 스쿼드 기반 협업

**공백:** 제품들은 공간적이지만 AI에 초점이 없거나, AI에 초점이 있지만 평면 2D입니다. 그 교차점에 있는 제품은 없습니다.

### Vision Pro 현실 점검

- 설치 기반: 전 세계 약 100만 대 (출시 시점 대비 판매 95% 감소)
- Apple은 경량 AR 글래스로 초점을 옮겼습니다
- VisionOS 전용 앱은 약 3,000개뿐입니다
- **시사점:** VisionOS를 앞세우지 **마세요**. 웹으로 시작하고, WebXR을 더하고, 네이티브 VisionOS는 마지막에 붙이세요.

### 유통의 돌파구가 될 WebXR

- Safari가 2025년 말 WebXR Device API를 채택했습니다
- 2026년 WebXR 채택률이 40% 증가했습니다
- WebGPU는 브라우저에서 네이티브에 가까운 렌더링을 제공합니다
- Android XR은 WebXR과 OpenXR 표준을 지원합니다

### 타깃 페르소나와 가격

| 티어 | 가격 | 타깃 |
|------|-------|--------|
| Explorer | 무료 | 개발자, 1인 빌더 (에이전트 3개, WebXR 뷰어) |
| Pro | 사용자당 월 $99 | 소규모 팀 (에이전트 25개, 협업 기능) |
| Team | 사용자당 월 $249 | 미드마켓 AI 팀 (에이전트 무제한, 분석) |
| Enterprise | 별도 협의 (월 $2K-10K) | 대기업 (SSO, RBAC, 온프레미스, SLA) |

### 권장 단계별 전략

1. **1~6개월:** Three.js로 2.5D 역량을 더한 프리미엄 2D 웹 대시보드를 구축합니다. 목표: 유료 팀 50곳, MRR $60K.
2. **6~12개월:** 선택형 WebXR 공간 모드(브라우저 기반)를 추가합니다. 목표: 팀 200곳, MRR $300K.
3. **12~18개월:** 공간 수요가 검증된 경우에만 네이티브 VisionOS 앱을 만듭니다. 목표: 팀 500곳, MRR $1M+.

### 핵심 리스크

| 리스크 | 심각도 |
|------|----------|
| Vision Pro 설치 기반이 치명적으로 작음 | HIGH |
| "문제를 찾아 헤매는 공간 솔루션" — 3D가 정말 2D보다 10배 나은가? | HIGH |
| 이미 5개 이상 제품이 있는 혼잡한 "미션 컨트롤" 포지셔닝 | MODERATE |
| 엔터프라이즈 공간 컴퓨팅 도입이 아직 초기 단계 | MODERATE |
| AI 프레임워크 전반에 걸친 통합 복잡도 | MODERATE |

### 출처

- [MarketsandMarkets - AI Orchestration Market](https://www.marketsandmarkets.com/Market-Reports/ai-orchestration-market-148121911.html)
- [Deloitte - AI Agent Orchestration Predictions 2026](https://www.deloitte.com/us/en/insights/industry/technology/technology-media-and-telecom-predictions/2026/ai-agent-orchestration.html)
- [Mordor Intelligence - Extended Reality Market](https://www.mordorintelligence.com/industry-reports/extended-reality-xr-market)
- [Fintool - Vision Pro Production Halted](https://fintool.com/news/apple-vision-pro-production-halt)
- [MadXR - WebXR Browser-Based Experiences 2026](https://www.madxr.io/webxr-browser-immersive-experiences-2026.html)

---

## 3. 시스템 아키텍처

**담당 에이전트:** Backend Architect

### 시스템 개요

소유 경계가 명확한 8개 서비스 아키텍처로, 수평 확장과 공급자 중립적인 AI 통합을 목표로 설계했습니다.

```
+------------------------------------------------------------------+
|                     CLIENT TIER                                   |
|  VisionOS Native (Swift/RealityKit)  |  WebXR (React Three Fiber) |
+------------------------------------------------------------------+
                              |
+-----------------------------v------------------------------------+
|                      API GATEWAY (Kong / AWS API GW)              |
|  Rate limiting | JWT validation | WebSocket upgrade | TLS        |
+------------------------------------------------------------------+
                              |
+------------------------------------------------------------------+
|                      SERVICE TIER                                 |
|  Auth | Workspace | Workflow | Orchestration (Rust) |             |
|  Collaboration (Yjs CRDT) | Streaming (WS) | Plugin | Billing    |
+------------------------------------------------------------------+
                              |
+------------------------------------------------------------------+
|                      DATA TIER                                    |
|  PostgreSQL 16 | Redis 7 Cluster | S3 | ClickHouse | NATS        |
+------------------------------------------------------------------+
                              |
+------------------------------------------------------------------+
|                    AI PROVIDER TIER                                |
|  OpenAI | Anthropic | Google | Local Models | Custom Plugins      |
+------------------------------------------------------------------+
```

### 기술 스택

| 구성 요소 | 기술 | 선택 이유 |
|-----------|------------|-----------|
| 오케스트레이션 엔진 | **Rust** | 1ms 미만 스케줄링, GC 멈춤 없음, 에이전트 샌드박싱을 위한 메모리 안전성 |
| API 서비스 | TypeScript / NestJS | CRUD 비중이 큰 서비스에서의 개발 속도 |
| VisionOS 클라이언트 | Swift 6, SwiftUI, RealityKit | Liquid Glass를 활용한 일급 공간 컴퓨팅 |
| WebXR 클라이언트 | TypeScript, React Three Fiber | React 컴포넌트 모델을 쓰는 프로덕션급 WebXR |
| 메시지 브로커 | NATS JetStream | 가볍고, exactly-once 전달, Kafka보다 단순함 |
| 협업 | Yjs (CRDT) + WebRTC | 충돌 없는 동시 3D 그래프 편집 |
| 주 데이터베이스 | PostgreSQL 16 | 유연한 설정을 위한 JSONB, 테넌트 격리를 위한 Row-Level Security |

### 핵심 데이터 모델

다음을 담은 14개 테이블:
- **아이덴티티와 접근 제어:** users, workspaces, team_memberships, api_keys
- **워크플로:** workflows, workflow_versions, nodes, edges
- **실행:** executions, execution_steps, step_output_chunks
- **협업:** collaboration_sessions, session_participants
- **자격 증명:** provider_credentials (AES-256-GCM 암호화)
- **빌링:** subscriptions, usage_records
- **감사:** audit_log (추가 전용)

### 노드 타입 레지스트리

```
Built-in Node Types:
  ai_agent          -- 프롬프트와 함께 AI 공급자를 호출
  prompt_template   -- 변수를 넣어 템플릿을 렌더링
  conditional       -- 식(expression)에 따라 분기
  transform         -- 샌드박스에서 실행되는 코드 조각 (JS/Python)
  input / output    -- 워크플로 진입/종료 지점
  human_review      -- 사람의 승인을 기다리며 일시 정지
  loop              -- 서브그래프를 반복
  parallel_split    -- 여러 분기로 팬아웃
  parallel_join     -- 분기들의 완료를 대기
  webhook_trigger   -- 외부 HTTP 트리거
  delay             -- 시간 기반 일시 정지
```

### WebSocket 채널

WSS를 통한 실시간 스트리밍, 다음을 포함합니다:
- 순서 보장을 위한 채널별 시퀀스 번호
- 재전송 요청과 함께하는 누락 감지
- 1,000개 이상 이벤트가 뒤처진 경우 스냅샷 복구
- 저사양 디바이스를 위한 클라이언트 측 스로틀링

### 보안 아키텍처

| 계층 | 메커니즘 |
|-------|-----------|
| 사용자 인증 | OAuth 2.0 (GitHub, Google, Apple) + 이메일/비밀번호 + 선택적 TOTP MFA |
| API 키 | SHA-256 해시, 범위 제한, 선택적 만료 |
| 서비스 간 통신 | 서비스 메시를 통한 mTLS |
| WebSocket 인증 | 30초 만료의 일회용 티켓 |
| 자격 증명 저장 | 엔벨로프 암호화 (AES-256-GCM + AWS KMS) |
| 코드 샌드박싱 | gVisor/Firecracker 마이크로VM (네트워크 차단, RAM 256MB, CPU 30초) |
| 테넌트 격리 | PostgreSQL Row-Level Security + S3 IAM 정책 + NATS subject 범위 제한 |

### 확장 목표

| 지표 | 1년차 | 2년차 |
|--------|--------|--------|
| 동시 에이전트 실행 수 | 5,000 | 50,000 |
| WebSocket 연결 수 | 10,000 | 100,000 |
| P95 API 지연 시간 | < 150ms | < 100ms |
| P95 WS 이벤트 지연 시간 | < 80ms | < 50ms |

### MVP 단계

1. **1~6주차:** 2D 웹 에디터, 순차 실행, OpenAI + Anthropic 어댑터
2. **7~12주차:** WebXR 3D 모드, 병렬 실행, 핸드 트래킹, RBAC
3. **13~20주차:** 다중 사용자 협업, VisionOS 네이티브, 빌링
4. **21~30주차:** 엔터프라이즈 SSO, 플러그인 SDK, SOC 2, 확장 안정화

---

## 4. 브랜드 전략

**담당 에이전트:** Brand Guardian

### 포지셔닝

**카테고리 경쟁이 아니라 카테고리 창출.** Nexus Spatial은 혼잡한 AI 옵저버빌리티 대시보드 시장에서 자리를 다투는 대신, 새로운 카테고리 — **공간 AI 운영(Spatial AI Operations, SpatialAIOps)** — 를 정의합니다.

**포지셔닝 선언문:** 복잡한 AI 에이전트 워크플로를 운영하는 기술 팀에게, Nexus Spatial은 에이전트 오케스트레이션에 대한 공간적 인식을 제공하는 몰입형 3D 커맨드 센터입니다. 평면 2D 대시보드와 달리, 공간 컴퓨팅은 모니터링을 "대시보드를 읽는 일"에서 "자신의 인프라 안에 머무르는 일"로 바꿔 놓기 때문입니다.

### 이름 검증

"Nexus Spatial"은 **강한 이름으로 검증되었습니다:**
- "Nexus"는 NEXUS 오케스트레이션 프레임워크(Network of EXperts, Unified in Strategy)와 연결됩니다
- "Nexus"는 그 자체로 "중심 연결점"을 뜻하며, 커맨드 센터에 완벽하게 맞습니다
- "Spatial"은 Apple과 업계가 표준으로 정착시킨 업계 공용 수식어입니다
- 음성적으로 균형이 좋습니다: 3음절 다음 2음절
- **필요한 조치:** 니스 분류 9류, 42류, 38류에 대한 상표 클리어런스

### 브랜드 퍼스널리티: The Commander

| 특성 | 표현 방식 | 피하는 것 |
|-------|------------|--------|
| **권위 있음** | 명확하고, 직접적이고, 기술적으로 정확하게 | 과대 선전, 최상급 표현, 모호한 미래주의 |
| **침착함** | 깔끔한 디자인, 절제된 리듬, 여백 | 급할 것도 없이 급한 척, 혼란스러움 |
| **개척자적임** | 조용한 자부심, 새로운 패러다임에 대한 담담한 언급 | "혁명적", "게임 체인저" |
| **정밀함** | 정확한 스펙, 실제 지표, 솔직한 요구사항 | 모호한 주장, 마케팅 유행어 |
| **다가가기 쉬움** | 자연스러운 상호작용 언어, 공간 비유 | 깔보는 태도, 문턱 세우기 |

### 태그라인 (순위순)

1. **"Mission Control for the Agent Era"** — 추천 1순위
2. "See Your Agents in Space"
3. "Orchestrate in Three Dimensions"
4. "Where AI Operations Become Spatial"
5. "Command Center. Reimagined in Space."
6. "The Dimension Your Dashboards Are Missing"
7. "AI Agents Deserve More Than Flat Screens"

### 컬러 시스템

| 컬러 | Hex | 용도 |
|-------|-----|-------|
| Deep Space Indigo | `#1B1F3B` | 기반이 되는 다크 캔버스, 배경 |
| Nexus Blue | `#4A7BF7` | 시그니처 브랜드 컬러, 주요 액션 |
| Signal Cyan | `#00D4FF` | 공간 하이라이트, 데이터 연결선 |
| Command Green | `#00E676` | 정상 상태, 성공 |
| Alert Amber | `#FFB300` | 경고, 주의 필요 |
| Critical Red | `#FF3D71` | 오류, 실패 |

사용 비율: Deep Space Indigo 60%, Nexus Blue 25%, Signal Cyan 10%, 의미 컬러 5%.

### 타이포그래피

- **기본:** Inter (UI, 본문, 라벨)
- **고정폭:** JetBrains Mono (코드, 로그, 에이전트 출력)
- **디스플레이:** Space Grotesk (마케팅 헤드라인 전용)

### 로고 컨셉

탐색할 세 가지 방향:

1. **The Spatial Nexus Mark** — 은근한 원근 깊이와 함께, 빛나는 중심 노드에서 만나는 수렴선
2. **The Dimensional Window** — 원근선으로 3D 공간을 들여다보는 효과를 만드는 양식화된 뷰포트
3. **The Orbital Array** — 중심점을 둘러싼 궤도 링으로, 조율되어 움직이는 에이전트들을 암시

### 브랜드 가치

- **공간적 진실성** — 시스템 상태를 정직하게 표현하고, 보기 좋게 다듬어 숨기지 않습니다
- **운영의 중력** — 데모가 아니라 프로덕션을 위해 만듭니다
- **차원의 관대함** — WebXR로 공간적 가치를 누구나 누릴 수 있게 합니다
- **복잡함 앞의 침착함** — 시스템이 복잡해질수록 인터페이스는 더 차분해집니다

### 디자인 토큰

```css
:root {
  --nxs-deep-space:       #1B1F3B;
  --nxs-blue:             #4A7BF7;
  --nxs-cyan:             #00D4FF;
  --nxs-green:            #00E676;
  --nxs-amber:            #FFB300;
  --nxs-red:              #FF3D71;
  --nxs-void:             #0A0E1A;
  --nxs-slate-900:        #141829;
  --nxs-slate-700:        #2A2F45;
  --nxs-slate-500:        #4A5068;
  --nxs-slate-300:        #8B92A8;
  --nxs-slate-100:        #C8CCE0;
  --nxs-cloud:            #E8EBF5;
  --nxs-white:            #F8F9FC;
  --nxs-font-primary:     'Inter', sans-serif;
  --nxs-font-mono:        'JetBrains Mono', monospace;
  --nxs-font-display:     'Space Grotesk', sans-serif;
}
```

---

## 5. 고투마켓과 성장

**담당 에이전트:** Growth Hacker

### 노스 스타 지표

**주간 활성 파이프라인(Weekly Active Pipelines, WAP)** — 지난 7일 안에 공간 상호작용이 한 번 이상 있었던 고유 에이전트 파이프라인 수. 생성과 참여를 동시에 포착하고, 가치와 상관관계가 있으며, 조작하기 어렵습니다.

### 가격

| 티어 | 연간 | 월간 | 대상 |
|------|--------|---------|--------|
| Explorer | 무료 | 무료 | 파이프라인 3개, WebXR 프리뷰, 커뮤니티 |
| Pro | 사용자당 월 $29 | 사용자당 월 $39 | 파이프라인 무제한, VisionOS, 30일 이력 |
| Team | 사용자당 월 $59 | 사용자당 월 $79 | 협업, RBAC, SSO, 90일 이력 |
| Enterprise | 별도 협의 (~$150+) | 별도 협의 | 전용 인프라, SLA, 온프레미스 옵션 |

전략: 14일 역방향 트라이얼(Pro 기능을 먼저 쓰고 이후 Free로 전환). 무료→유료 전환율 5~8% 목표.

### 3단계 GTM

**1단계: 창업자 주도 영업 (1~3개월)**
- 타깃: LangChain/CrewAI를 쓰면서 Vision Pro를 보유한 스타트업의 개별 AI 엔지니어
- 전술: 영향력 있는 AI 엔지니어 200명에게 DM, 주간 빌드 인 퍼블릭 게시물, 30초 데모 클립
- 채널: X/Twitter, LinkedIn, AI 중심 Discord 서버, Reddit

**2단계: 개발자 커뮤니티 (4~6개월)**
- Product Hunt 론칭 (1단계가 아니라 이 시점에 맞춤)
- Hacker News Show HN, Dev.to 글, 콘퍼런스 발표
- 인기 AI 프레임워크와의 통합 발표

**3단계: 엔터프라이즈 (7~12개월)**
- Apple 엔터프라이즈 리퍼럴 파이프라인, LinkedIn ABM 캠페인
- 엔터프라이즈 사례 연구, 애널리스트 브리핑 (Gartner, Forrester)
- 첫 엔터프라이즈 AE 채용, SOC 2 컴플라이언스

### 성장 루프

1. **"와우 팩터" 데모 루프** — 공간 데모는 본질적으로 공유를 부릅니다. 원클릭 "Share Spatial Preview"가 WebXR 링크나 영상을 생성합니다. 목표 K = 0.3~0.5.
2. **템플릿 마켓플레이스** — 파워 유저가 파이프라인 템플릿을 공개하고, 검색으로 발견되어 신규 가입을 끌어옵니다.
3. **협업 시트 확장** — 엔지니어 한 명이 도입해 팀원과 공유하고, 팀이 유료 플랜으로 확장됩니다 (Slack/Figma 플레이북).
4. **통합 주도 발견** — LangChain, n8n, OpenAI/Anthropic 파트너 디렉토리 등재.

### 오픈소스 전략

**오픈소스로 공개 (Apache 2.0):**
- `nexus-spatial-sdk` — 에이전트 프레임워크 연결용 TypeScript/Python SDK
- `nexus-webxr-components` — 3D 파이프라인을 위한 React Three Fiber 컴포넌트 라이브러리
- `nexus-agent-schemas` — 에이전트 파이프라인을 3D로 표현하기 위한 표준 스키마

**비공개 유지:** VisionOS 네이티브 앱, 협업 엔진, 엔터프라이즈 기능, 호스팅 인프라.

### 매출 목표

| 지표 | 6개월 | 12개월 |
|--------|---------|----------|
| MRR | $8K-15K | $50K-80K |
| 무료 계정 | 5,000 | 15,000 |
| 유료 시트 | 300 | 1,200 |
| Discord 멤버 | 2,000 | 5,000 |
| GitHub 스타 (SDK) | 500 | 2,000 |

### 첫 $50K 예산

| 항목 | 금액 | % |
|----------|--------|---|
| 콘텐츠 제작 | $12,000 | 24% |
| 개발자 관계 | $10,000 | 20% |
| 유료 획득 테스트 | $8,000 | 16% |
| 커뮤니티와 도구 | $5,000 | 10% |
| Product Hunt와 론칭 | $3,000 | 6% |
| 오픈소스 유지보수 | $3,000 | 6% |
| PR과 아웃리치 | $4,000 | 8% |
| 파트너십 | $2,000 | 4% |
| 예비비 | $3,000 | 6% |

### 핵심 파트너십

- **Tier 1 (필수):** Anthropic, OpenAI — 일급 API 통합, 파트너 프로그램 등재
- **Tier 2 (도입 확산):** LangChain, CrewAI, n8n — 프레임워크 통합, 커뮤니티 상호 유입
- **Tier 3 (플랫폼):** Apple — Vision Pro 개발자 키트, App Store 피처링, WWDC
- **Tier 4 (에코시스템):** GitHub, Hugging Face, Docker — 개발자 플랫폼 통합

### 출처

- [AI Orchestration Market Size - MarketsandMarkets](https://www.marketsandmarkets.com/Market-Reports/ai-orchestration-market-148121911.html)
- [Spatial Computing Market - Precedence Research](https://www.precedenceresearch.com/spatial-computing-market)
- [How to Price AI Products - Aakash Gupta](https://www.news.aakashg.com/p/how-to-price-ai-products)
- [Product Hunt Launch Guide 2026](https://calmops.com/indie-hackers/product-hunt-launch-guide/)

---

## 6. 고객 지원 설계도

**담당 에이전트:** Support Responder

### 지원 티어 구조

| 항목 | Explorer (무료) | Builder (Pro) | Command (Enterprise) |
|-----------|-----------------|---------------|---------------------|
| 최초 응답 SLA | 최선 노력 (48시간) | 4시간 (업무 시간 기준) | 30분 (P1), 2시간 (P2) |
| 해결 SLA | 영업일 5일 | 24시간 (P1/P2), 72시간 (P3) | 4시간 (P1), 12시간 (P2) |
| 채널 | 커뮤니티, KB, AI 어시스턴트 | + 라이브 챗, 이메일, 화상 (월 2회) | + 전용 Slack, 전담 CSE, 24/7 |
| 범위 | 일반 문의, 문서 | 기술 트러블슈팅, 통합 | 전체 통합, 맞춤 설계, 컴플라이언스 |

### 우선순위 정의

- **P1 Critical:** 오케스트레이션 중단, 데이터 유실 위험, 보안 침해
- **P2 High:** 주요 기능 저하, 우회 방법 존재
- **P3 Medium:** 작업을 막지 않는 문제, 경미한 결함
- **P4 Low:** 기능 요청, 외형상 문제

### The Nexus Guide: AI 기반 제품 내 지원

가장 눈에 띄는 설계 결정: 지원 에이전트가 **사용자의 공간 워크스페이스 안에** 보이는 노드로 존재합니다. 사용자의 레이아웃, 활성 에이전트, 최근 오류에 대한 전체 컨텍스트를 갖고 있습니다.

**역량:**
- 기능에 대한 자연어 질의응답
- 실시간 에이전트 진단 ("Agent X는 왜 느린가요?")
- 설정 제안 ("현재 토폴로지는 메시 구조로 바꾸면 성능이 더 좋아집니다")
- 안내형 공간 트러블슈팅 워크스루
- 컨텍스트가 자동 첨부되는 티켓 생성

**자가 치유:**

| 상황 | 감지 방법 | 자동 해결 |
|----------|-----------|-----------------|
| 에이전트 무한 루프 | CPU/토큰 급증 | 종료 후 마지막 정상 설정으로 재시작 |
| 렌더링 프레임 드롭 | FPS가 임계값 미만 | 시각 품질을 낮추고 패널 닫기를 제안 |
| 자격 증명 만료 | API 401 응답 | 재인증을 유도하고 에이전트를 정상적으로 일시 중단 |
| 통신 타임아웃 | 지연 시간 급증 | 대체 경로로 메시지 우회 |

### 온보딩 플로

사용자 프로파일링에 따른 적응형 온보딩:

| AI 경험 | 공간 컴퓨팅 경험 | 경로 |
|---------------|-------------------|------|
| 낮음 | 낮음 | 전체 안내 투어 (20분) |
| 높음 | 낮음 | 공간 중심 (12분) |
| 낮음 | 높음 | 에이전트 중심 (12분) |
| 높음 | 높음 | 빠른 설정 (5분) |

결정적인 첫 단계: 제품을 조작하기 전에 60초 공간 캘리브레이션(핸드 트래킹, 시선, 편안함 점검)을 수행합니다.

**활성화 마일스톤** (다음을 모두 달성하면 "온보딩 완료"로 봅니다):
- 커스텀 에이전트를 최소 하나 생성
- 두 개 이상의 에이전트를 토폴로지로 연결
- 모니터링 대시보드를 최소 하나 고정(앵커)
- 세 번째 세션으로 복귀

### 팀 구성

| 단계 | 인원 | 역할 |
|-------|-----------|-------|
| 0~6개월 | 4명 | Head of CX, 지원 엔지니어 2명, 테크니컬 라이터 |
| 6~12개월 | 8명 | + 지원 엔지니어 2명, CSE, 커뮤니티 매니저, 운영 애널리스트 |
| 12~24개월 | 16명 | + 엔지니어 4명(24/7), 공간 컴퓨팅 전문가, 통합 전문가, KB 매니저, 엔지니어링 매니저 |

### 커뮤니티: Discord 우선

```
NEXUS SPATIAL DISCORD
  정보: #announcements, #changelog, #status
  지원: #help-getting-started, #help-agents, #help-spatial
  토론: #general, #show-your-workspace, #feature-requests
  플랫폼: #visionos, #webxr, #api-and-sdk
  이벤트: office-hours (주간 음성), community-demos (월간)
  PRO 멤버: #pro-lounge, #beta-testing
  엔터프라이즈: 고객별 비공개 채널
```

**챔피언 프로그램("Nexus Navigators"):** 초기 파워 유저 5~10명에게 Navigator 배지, 제품팀과의 직통 Slack, Pro 티어 무료 제공, 신기능 선공개, 연례 서밋을 제공합니다.

---

## 7. UX 리서치와 디자인 방향

**담당 에이전트:** UX Researcher

### 사용자 페르소나

**Maya Chen — AI 플랫폼 엔지니어 (32세, 샌프란시스코)**
- 활성 에이전트 워크플로 15~30개를 운영하며 n8n + LangSmith 사용
- 업무 시간의 40%를 로그를 들여다보며 에이전트 장애를 디버깅하는 데 씀
- 공간 컴퓨팅에 회의적: "이게 정말 더 빠른 건가요, 아니면 그냥 멋있기만 한 건가요?"
- 주된 니즈: 평균 진단 시간을 45분에서 10분 미만으로 줄이기

**David Okoro — 테크니컬 프로덕트 매니저 (38세, 런던)**
- 에이전트 워크플로 설계를 검토·승인하고 C레벨에 발표
- 도구가 코드 수준의 이해를 요구하기 때문에 워크플로 리뷰에 제대로 기여할 수 없음
- 주된 니즈: 코드를 읽지 않고도 에이전트 아키텍처를 이해하고 설명하기

**Dr. Amara Osei — 연구 과학자 (45세, 취리히)**
- A/B 비교가 들어간 멀티 에이전트 연구 워크플로를 설계
- 같은 파이프라인의 변형 12개를 갖고 있지만 비교할 마땅한 방법이 없음
- 주된 니즈: 3D 공간에서 변형 파이프라인을 나란히 놓고 비교하기

**Jordan Rivera — 크리에이티브 테크놀로지스트 (27세, 오스틴)**
- Vision Pro를 매일 사용하며 AI 기반 아트 인스톨레이션을 제작
- 대시보드가 아니라 악기처럼 느껴지는 도구를 원함
- 주된 니즈: 즉각적인 공간 피드백과 함께 에이전트 워크플로를 빠르게 구성하기

### 핵심 발견: 디버깅이 킬러 유즈케이스다

워크플로 구조 위에 런타임 트레이스를 공간적으로 겹쳐 보여주는 방식은, 어떤 2D 도구도 제대로 다루지 못하는 실제적이고 수치로 확인된 고통을 해결합니다. 이 워크플로에 디자인과 엔지니어링 투자를 가장 많이 배분해야 합니다.

### 결정적인 디자인 통찰

공간은 **구조적** 작업(노드를 배치하고, 연결하고, 재배열하기)에서 가치를 더하지만, **파라미터** 작업(텍스트 입력, 설정)에서는 마찰을 만듭니다. 인터페이스는 공간 모드와 2D 모드를 매끄럽게 섞어야 합니다 — 공간상의 위치에 고정된 2D 패널 형태로요.

### 7가지 디자인 원칙

1. **공간은 그 자리를 스스로 증명해야 한다** — 2D가 더 명확하면 2D를 쓰세요. 모든 리뷰에서 물어야 합니다: "이건 평면이 더 낫지 않을까?"
2. **들여다보기 전에 한눈에** — 중요한 정보는 색, 크기, 움직임, 위치로 2초 안에 지각될 수 있어야 합니다
3. **핸즈프리가 기본선** — 시선 + 음성으로 모든 읽기/탐색 조작이 가능해야 하고, 손은 정밀도를 더하지만 필수는 아닙니다
4. **인지적 중력을 존중하라** — 2D 멘탈 모델(왼쪽에서 오른쪽으로 흐르는 구조)을 대체하지 말고 확장하세요. z축은 레이어를 더합니다
5. **공간적 복잡도는 점진적으로** — 신규 사용자는 거의 2D에서 시작하고, 자신감이 쌓이면서 공간 역량이 드러납니다
6. **물리적 비유, 디지털 역량** — 노드는 "집어 들" 수 있으면서(물리적) 복제와 버전 관리도 됩니다(디지털)
7. **고요함도 기능이다** — 정상인 시스템은 차분하게 느껴지고, 색과 움직임은 정상에서 벗어났다는 신호입니다

### 내비게이션 패러다임: 4단계 시맨틱 줌

| 단계 | 보이는 것 |
|-------|-------------|
| Fleet View | 모든 워크플로를 상태별 색으로 구분한 추상 도형으로 표시 |
| Workflow View | 라벨과 연결선이 있는 노드 그래프 |
| Node View | 펼쳐진 설정, 최근 입출력, 상태 지표 |
| Trace View | 데이터 조회가 가능한 전체 실행 트레이스 |

### 경쟁 UX 요약

| 역량 | n8n | Flowise | LangSmith | Langflow | Nexus Spatial 목표 |
|-----------|-----|---------|-----------|----------|---------------------|
| 비주얼 워크플로 구성 | A | B+ | N/A | A | A+ (공간) |
| 디버깅/트레이싱 | C+ | C | A | B | A+ (공간 오버레이) |
| 모니터링 | B | C | A | B | A (공간 플릿 뷰) |
| 협업 | D | D | C | D | A (공간 공동 현존) |
| 대규모 워크플로 확장성 | C | C | B | C | A (3D 공간) |

### 접근성 요구사항

- 모든 상호작용은 최소 두 가지 방식으로 수행할 수 있어야 합니다
- 색만으로 정보를 전달하지 않습니다
- 고대비 모드, 모션 감소 모드, 깊이 평탄화 모드 제공
- 공간 요소에 대한 설명을 포함한 스크린 리더 호환성
- 20~30분마다 세션 길이 경고
- 모든 핵심 작업은 앉은 자세로, 한 손으로, 30도 이동 범위 안에서 완료할 수 있어야 합니다

### 리서치 계획 (16주)

| 단계 | 주차 | 연구 |
|-------|-------|---------|
| 기초 조사 | 1~4주 | 멘탈 모델 인터뷰 (참가자 15~20명), 경쟁 제품 과업 분석 |
| 컨셉 검증 | 5~8주 | Wizard-of-Oz 공간 프로토타입 테스트, 정보 구조를 위한 3D 카드 소트 |
| 사용성 테스트 | 9~14주 | 첫 사용 경험 (사용자 20명), 4주 종단 다이어리 연구, 2인 협업 테스트 |
| 접근성 감사 | 12~16주 | 전문가 휴리스틱 평가, 장애가 있는 사용자 대상 테스트 |

---
