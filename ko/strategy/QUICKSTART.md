# ⚡ NEXUS 퀵스타트 가이드

> **5분 안에 아무것도 없는 상태에서 오케스트레이션된 멀티 에이전트 파이프라인까지.**

---

## NEXUS란?

**NEXUS**(Network of EXperts, Unified in Strategy)는 Agency의 AI 전문가들을 하나의 조율된 파이프라인으로 묶습니다. 에이전트를 하나씩 호출하고 서로 잘 맞물리기를 기대하는 대신, NEXUS는 누가 무엇을 언제 하고 각 단계에서 품질을 어떻게 검증하는지 명확하게 정의합니다.

## 모드 선택하기

| 하고 싶은 일 | 사용할 모드 | 에이전트 수 | 기간 |
|-------------|-----|--------|------|
| 완성된 제품을 처음부터 만들기 | **NEXUS-Full** | 전체 | 12~24주 |
| 기능 또는 MVP 만들기 | **NEXUS-Sprint** | 15~25 | 2~6주 |
| 특정 과업 수행 (버그 수정, 캠페인, 감사) | **NEXUS-Micro** | 5~10 | 1~5일 |

---

## 🚀 NEXUS-Full: 완전한 프로젝트 시작하기

**이 프롬프트를 복사해 전체 파이프라인을 가동하세요:**

```
Agents Orchestrator를 NEXUS-Full 모드로 활성화합니다.

프로젝트: [YOUR PROJECT NAME]
명세: [DESCRIBE YOUR PROJECT OR LINK TO SPEC]

NEXUS 파이프라인 전체를 실행하세요:
- Phase 0: 디스커버리 (Trend Researcher, Feedback Synthesizer, UX Researcher, Analytics Reporter, Legal Compliance Checker, Tool Evaluator)
- Phase 1: 전략 (Studio Producer, Senior Project Manager, Sprint Prioritizer, UX Architect, Brand Guardian, Backend Architect, Finance Tracker)
- Phase 2: 기반 구축 (DevOps Automator, Frontend Developer, Backend Architect, UX Architect, Infrastructure Maintainer)
- Phase 3: 구현 (Dev↔QA 루프 — 전체 엔지니어링 + Evidence Collector)
- Phase 4: 하드닝 (Reality Checker, Performance Benchmarker, API Tester, Legal Compliance Checker)
- Phase 5: 출시 (Growth Hacker, Content Creator, 전체 마케팅 에이전트, DevOps Automator)
- Phase 6: 운영 (Analytics Reporter, Infrastructure Maintainer, Support Responder, 상시)

모든 단계 사이에 품질 게이트를 둡니다. 모든 평가에는 증거가 필요합니다.
에스컬레이션 전까지 과업당 최대 3회 재시도합니다.
```

---

## 🏃 NEXUS-Sprint: 기능 또는 MVP 만들기

**이 프롬프트를 복사하세요:**

```
Agents Orchestrator를 NEXUS-Sprint 모드로 활성화합니다.

기능/MVP: [DESCRIBE WHAT YOU'RE BUILDING]
기간: [TARGET WEEKS]
Phase 0은 생략합니다 (시장 검증 완료).

스프린트 팀:
- PM: Senior Project Manager, Sprint Prioritizer
- 디자인: UX Architect, Brand Guardian
- 엔지니어링: Frontend Developer, Backend Architect, DevOps Automator
- QA: Evidence Collector, Reality Checker, API Tester
- 지원: Analytics Reporter

아키텍처와 스프린트 계획이 있는 Phase 1부터 시작하세요.
모든 구현 과업은 Dev↔QA 루프로 진행합니다.
출시 전에 Reality Checker의 승인이 필요합니다.
```

---

## 🎯 NEXUS-Micro: 특정 과업 수행하기

**시나리오를 고르고 프롬프트를 복사하세요:**

### 버그 수정
```
Backend Architect를 활성화해 [BUG DESCRIPTION]을 조사하고 수정하세요.
수정 후 API Tester를 활성화해 수정 내용을 검증하세요.
그다음 Evidence Collector를 활성화해 시각적 회귀가 없는지 확인하세요.
```

### 마케팅 캠페인 실행
```
Social Media Strategist를 [CAMPAIGN DESCRIPTION]의 캠페인 리드로 활성화하세요.
팀: Content Creator, Twitter Engager, Instagram Curator, Reddit Community Builder.
Brand Guardian이 발행 전에 모든 콘텐츠를 검토합니다.
Analytics Reporter가 매일 성과를 추적합니다.
Growth Hacker가 매주 채널을 최적화합니다.
```

### 컴플라이언스 감사 수행
```
전면적인 컴플라이언스 감사를 위해 Legal Compliance Checker를 활성화하세요.
범위: [GDPR / CCPA / HIPAA / ALL]
감사 후 Executive Summary Generator를 활성화해 이해관계자 보고서를 작성하세요.
```

### 성능 문제 조사
```
Performance Benchmarker를 활성화해 성능 문제를 진단하세요.
범위: [API response times / Page load / Database queries / All]
진단 후 Infrastructure Maintainer를 활성화해 최적화를 진행하세요.
DevOps Automator가 인프라 변경 사항을 배포합니다.
```

### 시장 조사
```
[DOMAIN]에 대한 시장 정보 수집을 위해 Trend Researcher를 활성화하세요.
산출물: 경쟁 구도, 시장 규모 추정, 트렌드 전망.
조사 후 Executive Summary Generator를 활성화해 경영진 브리프를 작성하세요.
```

### UX 개선
```
UX Researcher를 활성화해 [FEATURE/PRODUCT]의 사용성 문제를 찾아내세요.
조사 후 UX Architect를 활성화해 개선안을 설계하세요.
Frontend Developer가 변경 사항을 구현합니다.
Evidence Collector가 개선 결과를 검증합니다.
```

---

## 📁 전략 문서

| 문서 | 용도 | 위치 |
|----------|---------|----------|
| **마스터 전략** | NEXUS 교리 전문 | `strategy/nexus-strategy.md` |
| **Phase 0 플레이북** | 디스커버리 및 정보 수집 | `strategy/playbooks/phase-0-discovery.md` |
| **Phase 1 플레이북** | 전략 및 아키텍처 | `strategy/playbooks/phase-1-strategy.md` |
| **Phase 2 플레이북** | 기반 구축 및 스캐폴딩 | `strategy/playbooks/phase-2-foundation.md` |
| **Phase 3 플레이북** | 구현 및 반복 | `strategy/playbooks/phase-3-build.md` |
| **Phase 4 플레이북** | 품질 및 하드닝 | `strategy/playbooks/phase-4-hardening.md` |
| **Phase 5 플레이북** | 출시 및 그로스 | `strategy/playbooks/phase-5-launch.md` |
| **Phase 6 플레이북** | 운영 및 발전 | `strategy/playbooks/phase-6-operate.md` |
| **활성화 프롬프트** | 즉시 사용 가능한 에이전트 프롬프트 | `strategy/coordination/agent-activation-prompts.md` |
| **핸드오프 템플릿** | 표준화된 핸드오프 포맷 | `strategy/coordination/handoff-templates.md` |
| **스타트업 MVP 런북** | 4~6주 MVP 구축 | `strategy/runbooks/scenario-startup-mvp.md` |
| **엔터프라이즈 기능 런북** | 엔터프라이즈 기능 개발 | `strategy/runbooks/scenario-enterprise-feature.md` |
| **마케팅 캠페인 런북** | 멀티채널 캠페인 | `strategy/runbooks/scenario-marketing-campaign.md` |
| **인시던트 대응 런북** | 프로덕션 인시던트 대응 | `strategy/runbooks/scenario-incident-response.md` |

---

## 🔑 30초로 보는 핵심 개념

1. **품질 게이트** — 증거 기반 승인 없이는 어떤 단계도 다음으로 넘어가지 않습니다
2. **Dev↔QA 루프** — 모든 과업은 구현 후 테스트합니다. PASS면 진행, FAIL이면 재시도(최대 3회)
3. **핸드오프** — 에이전트 간 구조화된 컨텍스트 전달 (맨바닥에서 시작하는 일은 없습니다)
4. **Reality Checker** — 최종 품질 결정권자. 기본값은 "NEEDS WORK"
5. **Agents Orchestrator** — 전체 흐름을 관리하는 파이프라인 컨트롤러
6. **주장보다 증거** — 스크린샷, 테스트 결과, 데이터. 말뿐인 단언은 안 됩니다

---

## 🎭 한눈에 보는 에이전트

```
엔지니어링          │ 디자인              │ 마케팅
Frontend Developer  │ UI Designer         │ Growth Hacker
Backend Architect   │ UX Researcher       │ Content Creator
Mobile App Builder  │ UX Architect        │ Twitter Engager
AI Engineer         │ Brand Guardian      │ TikTok Strategist
DevOps Automator    │ Visual Storyteller  │ Instagram Curator
Rapid Prototyper    │ Whimsy Injector     │ Reddit Community Builder
Senior Developer    │ Image Prompt Eng.   │ App Store Optimizer
                    │                     │ Social Media Strategist
────────────────────┼─────────────────────┼──────────────────────
제품                │ 프로젝트 관리       │ 테스팅
Sprint Prioritizer  │ Studio Producer     │ Evidence Collector
Trend Researcher    │ Project Shepherd    │ Reality Checker
Feedback Synthesizer│ Studio Operations   │ Test Results Analyzer
                    │ Experiment Tracker  │ Performance Benchmarker
                    │ Senior Project Mgr  │ API Tester
                    │                     │ Tool Evaluator
                    │                     │ Workflow Optimizer
────────────────────┼─────────────────────┼──────────────────────
지원                │ 공간 컴퓨팅         │ 전문 분야
Support Responder   │ XR Interface Arch.  │ Agents Orchestrator
Analytics Reporter  │ macOS Spatial/Metal │ Analytics Reporter
Finance Tracker     │ XR Immersive Dev    │ LSP/Index Engineer
Infra Maintainer    │ XR Cockpit Spec.    │ Sales Data Extraction
Legal Compliance    │ visionOS Spatial    │ Data Consolidation
Exec Summary Gen.   │ Terminal Integration│ Report Distribution
```

---

<div align="center">

**모드를 고르세요. 플레이북을 따르세요. 파이프라인을 신뢰하세요.**

`strategy/nexus-strategy.md` — 교리 전문

</div>
