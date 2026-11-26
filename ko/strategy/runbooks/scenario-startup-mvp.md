# 🚀 런북: 스타트업 MVP 구축

> **모드**: NEXUS-Sprint | **기간**: 4~6주 | **에이전트**: 18~22

---

## 시나리오

스타트업 MVP를 만드는 상황입니다. 제품-시장 적합성(PMF)을 빠르게 검증해야 하는 신규 제품입니다. 속도가 중요하지만 품질도 중요합니다. 아이디어에서 실제 사용자가 쓰는 라이브 제품까지 4~6주 안에 도달해야 합니다.

## 에이전트 명단

### 핵심 팀 (항상 활성)
| 에이전트 | 역할 |
|-------|------|
| Agents Orchestrator | 파이프라인 컨트롤러 |
| Senior Project Manager | 명세를 과업으로 변환 |
| Sprint Prioritizer | 백로그 관리 |
| UX Architect | 기술적 기반 |
| Frontend Developer | UI 구현 |
| Backend Architect | API와 데이터베이스 |
| DevOps Automator | CI/CD와 배포 |
| Evidence Collector | 모든 과업의 QA |
| Reality Checker | 최종 품질 게이트 |

### 그로스 팀 (3주차부터 활성)
| 에이전트 | 역할 |
|-------|------|
| Growth Hacker | 유입 전략 |
| Content Creator | 출시 콘텐츠 |
| Social Media Strategist | 소셜 캠페인 |

### 지원 팀 (필요 시)
| 에이전트 | 역할 |
|-------|------|
| Brand Guardian | 브랜드 아이덴티티 |
| Analytics Reporter | 지표와 대시보드 |
| Rapid Prototyper | 빠른 검증 실험 |
| AI Engineer | 제품에 AI 기능이 포함된 경우 |
| Performance Benchmarker | 출시 전 부하 테스트 |
| Infrastructure Maintainer | 프로덕션 환경 구축 |

## 주차별 실행

### 1주차: 디스커버리 + 아키텍처 (Phase 0 + Phase 1 압축)

```
1~2일차: 압축 디스커버리
├── Trend Researcher → 빠른 경쟁사 스캔 (전체 리포트가 아닌 1일 작업)
├── UX Architect → 핵심 사용자 플로우 와이어프레임
└── Senior Project Manager → 명세를 과업 목록으로 변환

3~4일차: 아키텍처
├── UX Architect → CSS 디자인 시스템 + 컴포넌트 아키텍처
├── Backend Architect → 시스템 아키텍처 + 데이터베이스 스키마
├── Brand Guardian → 간결한 브랜드 기반 (색상, 타이포그래피, 보이스)
└── Sprint Prioritizer → RICE 점수 백로그 + 스프린트 플랜

5일차: 기반 세팅
├── DevOps Automator → CI/CD 파이프라인 + 환경
├── Frontend Developer → 프로젝트 스캐폴딩
├── Backend Architect → 데이터베이스 + API 스캐폴드
└── 품질 게이트: 아키텍처 패키지 승인
```

### 2~3주차: 핵심 구현 (Phase 2 + Phase 3)

```
스프린트 1 (2주차):
├── Agents Orchestrator가 Dev↔QA 루프 관리
├── Frontend Developer → 핵심 UI (인증, 주요 화면, 내비게이션)
├── Backend Architect → 핵심 API (인증, CRUD, 비즈니스 로직)
├── Evidence Collector → 완료된 모든 과업 QA
├── AI Engineer → 해당 시 ML 기능
└── 주말에 스프린트 리뷰

스프린트 2 (3주차):
├── 남은 기능에 대해 Dev↔QA 루프 계속
├── Growth Hacker → 바이럴 메커니즘 + 추천 시스템 설계
├── Content Creator → 출시 콘텐츠 제작 착수
├── Analytics Reporter → 트래킹과 대시보드 세팅
└── 주말에 스프린트 리뷰
```

### 4주차: 폴리시 + 하드닝 (Phase 4)

```
1~2일차: 품질 스프린트
├── Evidence Collector → 전체 스크린샷 세트
├── Performance Benchmarker → 부하 테스트
├── Frontend Developer → QA 이슈 수정
├── Backend Architect → API 이슈 수정
└── Brand Guardian → 브랜드 일관성 감사

3~4일차: 리얼리티 체크
├── Reality Checker → 최종 통합 테스트
├── Infrastructure Maintainer → 프로덕션 준비 상태 점검
└── DevOps Automator → 프로덕션 배포 준비

5일차: 게이트 판정
├── Reality Checker 판정
├── NEEDS WORK인 경우: 빠른 수정 사이클 (2~3일)
├── READY인 경우: 출시로 진행
└── Executive Summary Generator → 이해관계자 브리핑
```

### 5~6주차: 출시 + 그로스 (Phase 5)

```
5주차: 출시
├── DevOps Automator → 프로덕션 배포
├── Growth Hacker → 유입 채널 가동
├── Content Creator → 출시 콘텐츠 발행
├── Social Media Strategist → 크로스 플랫폼 캠페인
├── Analytics Reporter → 실시간 모니터링
└── Support Responder → 사용자 지원 가동

6주차: 최적화
├── Growth Hacker → 채널 분석 및 최적화
├── Feedback Synthesizer → 초기 사용자 피드백 수집
├── Experiment Tracker → A/B 테스트 가동
├── Analytics Reporter → 1주차 분석
└── Sprint Prioritizer → 개선 스프린트 계획
```

## 핵심 의사결정

| 의사결정 포인트 | 시점 | 결정 주체 |
|---------------|------|-------------|
| 콘셉트 Go/No-Go | 2일차 종료 시 | Studio Producer |
| 아키텍처 승인 | 4일차 종료 시 | Senior Project Manager |
| MVP 기능 범위 | 스프린트 계획 시 | Sprint Prioritizer |
| 프로덕션 준비 상태 | 4주차 5일차 | Reality Checker |
| 출시 시점 | Reality Checker READY 이후 | Studio Producer |

## 성공 기준

| 지표 | 목표 |
|--------|--------|
| 라이브 제품까지 소요 시간 | 6주 이내 |
| 핵심 기능 완성도 | MVP 범위의 100% |
| 첫 사용자 온보딩 | 출시 후 48시간 이내 |
| 시스템 가동률 | 첫 주 99% 초과 |
| 수집한 사용자 피드백 | 첫 2주간 50건 이상 |

## 자주 빠지는 함정과 대응

| 함정 | 대응 |
|---------|-----------|
| 구현 중 범위 확산 | Sprint Prioritizer가 MoSCoW를 엄격히 적용 — "Won't"는 정말 안 하는 것 |
| 확장성 과잉 설계 | Rapid Prototyper의 마음가짐 — 먼저 검증하고 나중에 확장 |
| 속도 때문에 QA 생략 | Evidence Collector가 모든 과업에 투입 — 예외 없음 |
| 모니터링 없이 출시 | Infrastructure Maintainer가 1주차에 모니터링을 세팅 |
| 피드백 장치 부재 | 분석과 피드백 수집을 스프린트 1에 내장 |
