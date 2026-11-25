# 🔨 Phase 3 플레이북 — 구현 및 반복

> **기간**: 2~12주 (범위에 따라 다름) | **에이전트**: 15~30명 이상 | **게이트 키퍼**: Agents Orchestrator

---

## 목표

지속적인 Dev↔QA 루프로 모든 기능을 구현합니다. 모든 과업은 다음 과업이 시작되기 전에 검증됩니다. 작업량의 대부분이 여기서 발생하며, NEXUS의 오케스트레이션이 가장 큰 가치를 내는 지점입니다.

## 사전 조건

- [ ] Phase 2 품질 게이트 통과 (기반 검증 완료)
- [ ] RICE 점수가 매겨진 Sprint Prioritizer 백로그 확보
- [ ] CI/CD 파이프라인 가동
- [ ] 디자인 시스템과 컴포넌트 라이브러리 준비 완료
- [ ] 인증 시스템을 갖춘 API 스캐폴드 준비 완료

## Dev↔QA 루프 — 핵심 메커니즘

Agents Orchestrator는 모든 과업을 이 사이클로 관리합니다:

```
FOR EACH task IN sprint_backlog (RICE 점수 순):

  1. 적절한 개발 에이전트에 과업을 ASSIGN (배정 매트릭스 참조)
  2. 개발자가 과업을 IMPLEMENT
  3. Evidence Collector가 과업을 TEST
     - 시각 스크린샷 (데스크톱, 태블릿, 모바일)
     - 완료 기준 대조 기능 검증
     - 브랜드 일관성 점검
  4. IF 판정 == PASS:
       과업을 완료 처리
       다음 과업으로 이동
     ELIF 판정 == FAIL AND 시도 < 3:
       QA 피드백을 개발자에게 전달
       개발자가 지적된 문제를 FIX
       3단계로 복귀
     ELIF 시도 >= 3:
       Agents Orchestrator로 ESCALATE
       Orchestrator가 결정: 재배정, 분해, 연기, 또는 수용
  5. 파이프라인 상태 리포트를 UPDATE
```

## 에이전트 배정 매트릭스

### 주 개발자 배정

| 과업 범주 | 주 에이전트 | 백업 에이전트 | QA 에이전트 |
|--------------|--------------|-------------|----------|
| **React/Vue/Angular UI** | Frontend Developer | Rapid Prototyper | Evidence Collector |
| **REST/GraphQL API** | Backend Architect | Senior Developer | API Tester |
| **데이터베이스 작업** | Backend Architect | — | API Tester |
| **모바일 (iOS/Android)** | Mobile App Builder | — | Evidence Collector |
| **ML 모델/파이프라인** | AI Engineer | — | Test Results Analyzer |
| **CI/CD·인프라** | DevOps Automator | Infrastructure Maintainer | Performance Benchmarker |
| **프리미엄/복잡한 기능** | Senior Developer | Backend Architect | Evidence Collector |
| **빠른 프로토타입/POC** | Rapid Prototyper | Frontend Developer | Evidence Collector |
| **WebXR/몰입형** | XR Immersive Developer | — | Evidence Collector |
| **visionOS** | visionOS Spatial Engineer | macOS Spatial/Metal Engineer | Evidence Collector |
| **콕핏 컨트롤** | XR Cockpit Interaction Specialist | XR Interface Architect | Evidence Collector |
| **CLI/터미널 도구** | Terminal Integration Specialist | — | API Tester |
| **코드 인텔리전스** | LSP/Index Engineer | — | Test Results Analyzer |
| **성능 최적화** | Performance Benchmarker | Infrastructure Maintainer | Performance Benchmarker |

### 전문 지원 (필요 시 활성화)

| 전문 에이전트 | 활성화 시점 | 트리거 |
|-----------|-----------------|---------|
| UI Designer | 컴포넌트에 시각적 정교화가 필요할 때 | 개발자가 디자인 가이드를 요청 |
| Whimsy Injector | 기능에 즐거움/개성이 필요할 때 | UX 리뷰에서 기회를 발견 |
| Visual Storyteller | 비주얼 내러티브 콘텐츠가 필요할 때 | 콘텐츠에 비주얼 자산이 필요 |
| Brand Guardian | 브랜드 일관성이 우려될 때 | QA에서 브랜드 이탈을 발견 |
| XR Interface Architect | 공간 인터랙션 설계가 필요할 때 | XR 기능에 UX 가이드가 필요 |
| Analytics Reporter | 심층 데이터 분석이 필요할 때 | 기능에 분석 연동이 필요 |

## 병렬 구현 트랙

NEXUS-Full 배치에서는 네 개 트랙이 동시에 돌아갑니다:

### 트랙 A: 핵심 제품 개발
```
관리: Agents Orchestrator (Dev↔QA 루프)
에이전트: Frontend Developer, Backend Architect, AI Engineer,
        Mobile App Builder, Senior Developer
QA: Evidence Collector, API Tester, Test Results Analyzer

스프린트 주기: 2주 스프린트
매일: 과업 구현 + QA 검증
스프린트 종료: 스프린트 리뷰 + 회고
```

### 트랙 B: 그로스 & 마케팅 준비
```
관리: Project Shepherd
에이전트: Growth Hacker, Content Creator, Social Media Strategist,
        App Store Optimizer

스프린트 주기: 트랙 A 마일스톤에 맞춤
활동:
- Growth Hacker → 바이럴 루프와 추천 메커니즘 설계
- Content Creator → 출시 콘텐츠 파이프라인 구축
- Social Media Strategist → 크로스 플랫폼 캠페인 기획
- App Store Optimizer → 스토어 리스팅 준비 (모바일인 경우)
```

### 트랙 C: 품질 & 운영
```
관리: Agents Orchestrator
에이전트: Evidence Collector, API Tester, Performance Benchmarker,
        Workflow Optimizer, Experiment Tracker

상시 활동:
- Evidence Collector → 모든 과업에 대한 스크린샷 QA
- API Tester → 모든 API 과업에 대한 엔드포인트 검증
- Performance Benchmarker → 주기적인 부하 테스트
- Workflow Optimizer → 프로세스 개선 지점 식별
- Experiment Tracker → 검증된 기능에 대한 A/B 테스트 세팅
```

### 트랙 D: 브랜드 & 경험 폴리시
```
관리: Brand Guardian
에이전트: UI Designer, Brand Guardian, Visual Storyteller,
        Whimsy Injector

트리거 기반 활동:
- UI Designer → QA가 시각적 문제를 찾으면 컴포넌트 정교화
- Brand Guardian → 주기적인 브랜드 일관성 감사
- Visual Storyteller → 기능이 완성되는 대로 비주얼 내러티브 자산 제작
- Whimsy Injector → 마이크로 인터랙션과 즐거운 순간 추가
```

## 스프린트 실행 템플릿

### 스프린트 계획 (1일차)

```
Sprint Prioritizer 활성화:
1. 갱신된 RICE 점수로 백로그 검토
2. 팀 벨로시티에 맞춰 스프린트 과업 선정
3. 개발 에이전트에 과업 배정
4. 의존 관계와 순서 식별
5. 스프린트 목표와 성공 기준 설정

산출물: 과업 배정이 포함된 스프린트 플랜
```

### 일일 실행 (2일차 ~ N-1일차)

```
Agents Orchestrator 관리:
1. 현재 과업 상태 점검
2. Dev↔QA 루프 실행
3. 블로커 식별 및 해소
4. 진행 상황 추적 및 보고

상태 리포트 포맷:
- 오늘 완료한 과업: [목록]
- QA 중인 과업: [목록]
- 개발 중인 과업: [목록]
- 막힌 과업: [사유와 함께 목록]
- QA 통과율: [X/Y]
```

### 스프린트 리뷰 (N일차)

```
Project Shepherd 진행:
1. 완성된 기능 데모
2. 과업별 QA 증거 검토
3. 이해관계자 피드백 수집
4. 배운 점을 반영해 백로그 갱신

참여자: 모든 활성 에이전트 + 이해관계자
산출물: 스프린트 리뷰 요약
```

### 스프린트 회고

```
Workflow Optimizer 진행:
1. 무엇이 잘됐는가?
2. 무엇을 개선할 수 있는가?
3. 다음 스프린트에서 무엇을 바꿀 것인가?
4. 프로세스 효율 지표

산출물: 회고 액션 아이템
```

## Orchestrator 판정 로직

### 과업 실패 처리

```
과업이 QA에서 실패하면:
  IF 시도 == 1:
    → 구체적인 QA 피드백을 개발자에게 전달
    → 개발자는 지적된 문제만 수정
    → QA에 재제출
    
  IF 시도 == 2:
    → 누적된 QA 피드백 전달
    → 검토: 이 개발 에이전트가 적합한가?
    → 개발자가 추가 컨텍스트와 함께 수정
    → QA에 재제출
    
  IF 시도 == 3:
    → 에스컬레이션
    → 선택지:
      a) 다른 개발 에이전트에게 재배정
      b) 과업을 더 작은 하위 과업으로 분해
      c) 접근 방식/아키텍처 수정
      d) 알려진 한계를 감수하고 수용 (문서화)
      e) 향후 스프린트로 연기
    → 결정과 근거를 기록
```

### 병렬 과업 관리

```
여러 과업에 의존 관계가 없을 때:
  → 서로 다른 개발 에이전트에 동시 배정
  → 각각 독립적인 Dev↔QA 루프를 실행
  → Orchestrator가 모든 루프를 동시에 추적
  → 완료된 과업을 의존 순서대로 병합

과업에 의존 관계가 있을 때:
  → 선행 과업이 QA를 통과할 때까지 대기
  → 그 후 의존 과업을 배정
  → 핸드오프에 선행 과업 컨텍스트를 포함
```

## 품질 게이트 체크리스트

| # | 기준 | 증거 출처 | 상태 |
|---|-----------|----------------|--------|
| 1 | 모든 스프린트 과업 QA 통과 (완료율 100%) | 과업별 Evidence Collector 스크린샷 | ☐ |
| 2 | 모든 API 엔드포인트 검증 완료 | API Tester 회귀 테스트 리포트 | ☐ |
| 3 | 성능 기준선 충족 (P95 < 200ms) | Performance Benchmarker 리포트 | ☐ |
| 4 | 브랜드 일관성 확인 (준수율 95% 이상) | Brand Guardian 감사 결과 | ☐ |
| 5 | 치명적 버그 없음 (미해결 P0/P1 0건) | Test Results Analyzer 요약 | ☐ |
| 6 | 모든 완료 기준 충족 | 과업별 검증 결과 | ☐ |
| 7 | 모든 PR에 코드 리뷰 완료 | Git 이력 증거 | ☐ |

## 게이트 판정

**게이트 키퍼**: Agents Orchestrator

- **PASS**: 기능이 완성된 애플리케이션 → Phase 4 활성화
- **CONTINUE**: 스프린트가 더 필요함 → Phase 3 계속 진행
- **ESCALATE**: 구조적 문제 발생 → Studio Producer 개입

## Phase 4로의 핸드오프

```markdown
## Phase 3 → Phase 4 핸드오프 패키지

### Reality Checker에게:
- 완성된 애플리케이션 (모든 기능 구현 완료)
- Dev↔QA 루프에서 나온 모든 QA 증거
- API Tester 회귀 테스트 결과
- Performance Benchmarker 기준선 데이터
- Brand Guardian 일관성 감사 결과
- 알려진 이슈 목록 (수용한 한계가 있는 경우)

### Legal Compliance Checker에게:
- 데이터 처리 구현 상세
- 개인정보 처리방침 구현 내용
- 동의 관리 구현 내용
- 적용된 보안 조치

### Performance Benchmarker에게:
- 부하 테스트용 애플리케이션 URL
- 예상 트래픽 패턴
- 아키텍처에 정의된 성능 예산

### Infrastructure Maintainer에게:
- 프로덕션 환경 요구사항
- 확장 설정 요구사항
- 모니터링 알림 임계값
```

---

*Phase 3은 모든 스프린트 과업이 QA를 통과하고, 모든 API 엔드포인트가 검증되고, 성능 기준선이 충족되며, 미해결 치명적 버그가 없을 때 완료됩니다.*
