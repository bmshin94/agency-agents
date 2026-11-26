# 🏗️ Phase 1 플레이북 — 전략 및 아키텍처

> **기간**: 5~10일 | **에이전트**: 8 | **게이트 키퍼**: Studio Producer + Reality Checker

---

## 목표

코드를 한 줄도 쓰기 전에 무엇을 만들지, 어떤 구조로 만들지, 성공이 어떤 모습인지 정의합니다. 모든 아키텍처 결정은 문서로 남깁니다. 모든 기능에는 우선순위가 매겨집니다. 모든 비용은 근거가 있습니다.

## 사전 조건

- [ ] Phase 0 품질 게이트 통과 (GO 결정)
- [ ] Phase 0 핸드오프 패키지 수령
- [ ] 프로젝트 범위에 대한 이해관계자 합의

## 에이전트 활성화 순서

### STEP 1: 전략 프레이밍 (1~3일차, 병렬)

#### 🎬 Studio Producer — 전략적 포트폴리오 정렬
```
[PROJECT]의 전략적 포트폴리오 정렬을 위해 Studio Producer를 활성화합니다.

입력: Phase 0 경영진 요약 + 시장 분석 리포트
필요한 산출물:
1. 프로젝트 포지셔닝이 포함된 전략 포트폴리오 플랜
2. 비전, 목표, ROI 목표치
3. 자원 배분 전략
4. 리스크/보상 평가
5. 성공 기준과 마일스톤 정의

정렬 대상: 조직의 전략 목표
포맷: 전략 포트폴리오 플랜 템플릿
기간: 3일
```

#### 🎭 Brand Guardian — 브랜드 아이덴티티 시스템
```
[PROJECT]의 브랜드 아이덴티티 개발을 위해 Brand Guardian을 활성화합니다.

입력: Phase 0 UX 리서치 (퍼소나, 여정 지도)
필요한 산출물:
1. 브랜드 기반 (목적, 비전, 미션, 가치, 퍼스널리티)
2. 비주얼 아이덴티티 시스템 (CSS 변수 형태의 색상, 타이포그래피, 간격)
3. 브랜드 보이스와 메시징 아키텍처
4. 로고 시스템 명세 (신규 브랜드인 경우)
5. 브랜드 사용 가이드라인

포맷: 브랜드 아이덴티티 시스템 문서
기간: 3일
```

#### 💰 Finance Tracker — 예산 및 자원 계획
```
[PROJECT]의 재무 계획을 위해 Finance Tracker를 활성화합니다.

입력: Studio Producer 전략 플랜 + Phase 0 기술 스택 평가서
필요한 산출물:
1. 항목별 내역이 포함된 종합 프로젝트 예산
2. 자원 비용 전망 (에이전트, 인프라, 도구)
3. 손익분기 분석이 포함된 ROI 모델
4. 현금 흐름 타임라인
5. 예비비를 포함한 재무 리스크 평가

포맷: ROI 전망이 포함된 재무 계획
기간: 2일
```

### STEP 2: 기술 아키텍처 (3~7일차, 병렬, STEP 1 산출물이 나온 뒤)

#### 🏛️ UX Architect — 기술 아키텍처 + UX 기반
```
[PROJECT]의 기술 아키텍처를 위해 UX Architect를 활성화합니다.

입력: Brand Guardian 비주얼 아이덴티티 + Phase 0 UX 리서치
필요한 산출물:
1. CSS 디자인 시스템 (변수, 토큰, 스케일)
2. 레이아웃 프레임워크 (Grid/Flexbox 패턴, 반응형 브레이크포인트)
3. 컴포넌트 아키텍처 (네이밍 규칙, 계층 구조)
4. 정보 구조 (페이지 흐름, 콘텐츠 계층)
5. 테마 시스템 (라이트/다크/시스템 전환)
6. 접근성 기반 (WCAG 2.1 AA 베이스라인)

생성할 파일:
- css/design-system.css
- css/layout.css
- css/components.css
- docs/ux-architecture.md

포맷: 개발자가 바로 쓸 수 있는 기반 패키지
기간: 4일
```

#### 🏗️ Backend Architect — 시스템 아키텍처
```
[PROJECT]의 시스템 아키텍처를 위해 Backend Architect를 활성화합니다.

입력: Phase 0 기술 스택 평가서 + 컴플라이언스 요구사항
필요한 산출물:
1. 시스템 아키텍처 명세
   - 아키텍처 패턴 (마이크로서비스/모놀리식/서버리스/하이브리드)
   - 통신 패턴 (REST/GraphQL/gRPC/이벤트 드리븐)
   - 데이터 패턴 (CQRS/Event Sourcing/CRUD)
2. 인덱싱 전략이 포함된 데이터베이스 스키마 설계
3. 버저닝이 포함된 API 설계 명세
4. 인증 및 인가 아키텍처
5. 보안 아키텍처 (심층 방어)
6. 확장 계획 (수평 확장 전략)

포맷: 시스템 아키텍처 명세
기간: 4일
```

#### 🤖 AI Engineer — ML 아키텍처 (해당 시)
```
[PROJECT]의 ML 시스템 아키텍처를 위해 AI Engineer를 활성화합니다.

입력: Backend Architect 시스템 아키텍처 + Phase 0 데이터 감사 결과
필요한 산출물:
1. ML 시스템 설계
   - 모델 선정 및 학습 전략
   - 데이터 파이프라인 아키텍처
   - 추론 전략 (실시간/배치/엣지)
2. AI 윤리 및 안전 프레임워크
3. 모델 모니터링 및 재학습 계획
4. 메인 애플리케이션과의 연동 지점
5. ML 인프라 비용 전망

조건: 프로젝트에 AI/ML 기능이 포함된 경우에만 활성화
포맷: ML 시스템 설계 문서
기간: 3일
```

#### 👔 Senior Project Manager — 명세를 과업으로 변환
```
[PROJECT]의 과업 목록 작성을 위해 Senior Project Manager를 활성화합니다.

입력: Phase 0 문서 전체 + 아키텍처 명세 (확보된 범위)
필요한 산출물:
1. 종합 과업 목록
   - 명세의 요구사항을 원문 그대로 인용 (과한 기능 추가 금지)
   - 각 과업에 명확한 완료 기준 부여
   - 과업 간 의존 관계 매핑
   - 공수 추정 (스토리 포인트 또는 시간)
2. 작업 분해 구조(WBS)
3. 크리티컬 패스 식별
4. 구현 리스크 레지스터

규칙:
- 명세에 없는 기능은 추가하지 마세요
- 요구사항 원문을 그대로 인용하세요
- 공수 추정은 현실적으로 하세요

포맷: 완료 기준이 포함된 과업 목록
기간: 3일
```

### STEP 3: 우선순위화 (7~10일차, 순차, STEP 2 이후)

#### 🎯 Sprint Prioritizer — 기능 우선순위화
```
[PROJECT]의 백로그 우선순위화를 위해 Sprint Prioritizer를 활성화합니다.

입력:
- Senior Project Manager → 과업 목록
- Backend Architect → 시스템 아키텍처
- UX Architect → UX 아키텍처
- Finance Tracker → 예산 프레임워크
- Studio Producer → 전략 플랜

필요한 산출물:
1. RICE 점수 백로그 (Reach, Impact, Confidence, Effort)
2. 벨로시티 기반 추정이 반영된 스프린트 배정
3. 크리티컬 패스가 포함된 의존 관계 지도
4. MoSCoW 분류 (Must/Should/Could/Won't)
5. 마일스톤이 매핑된 릴리스 계획

검증: Studio Producer가 전략적 정렬을 확인
포맷: 우선순위 스프린트 계획
기간: 2일
```

## 품질 게이트 체크리스트

| # | 기준 | 증거 출처 | 상태 |
|---|-----------|----------------|--------|
| 1 | 아키텍처가 명세 요구사항의 100%를 포괄 | Senior PM 과업 목록과 아키텍처 교차 대조 | ☐ |
| 2 | 브랜드 시스템 완비 (로고, 색상, 타이포그래피, 보이스) | Brand Guardian 산출물 | ☐ |
| 3 | 모든 기술 구성 요소에 구현 경로 존재 | Backend Architect + UX Architect 명세 | ☐ |
| 4 | 예산이 승인되고 제약 범위 내에 있음 | Finance Tracker 계획 | ☐ |
| 5 | 스프린트 계획이 벨로시티 기반이며 현실적임 | Sprint Prioritizer 백로그 | ☐ |
| 6 | 보안 아키텍처 정의 완료 | Backend Architect 보안 명세 | ☐ |
| 7 | 컴플라이언스 요구사항이 아키텍처에 반영됨 | 법적 요구사항이 기술 결정에 매핑됨 | ☐ |

## 게이트 판정

**양측 승인 필요**: Studio Producer (전략) + Reality Checker (기술)

- **APPROVED**: 전체 아키텍처 패키지와 함께 Phase 2로 진행
- **REVISE**: 특정 항목 재작업 필요 (해당 STEP으로 회귀)
- **RESTRUCTURE**: 근본적인 아키텍처 문제 (Phase 1 재시작)

## Phase 2로의 핸드오프

```markdown
## Phase 1 → Phase 2 핸드오프 패키지

### 아키텍처 패키지:
1. 전략 포트폴리오 플랜 (Studio Producer)
2. 브랜드 아이덴티티 시스템 (Brand Guardian)
3. 재무 계획 (Finance Tracker)
4. CSS 디자인 시스템 + UX 아키텍처 (UX Architect)
5. 시스템 아키텍처 명세 (Backend Architect)
6. ML 시스템 설계 (AI Engineer — 해당 시)
7. 종합 과업 목록 (Senior Project Manager)
8. 우선순위 스프린트 계획 (Sprint Prioritizer)

### DevOps Automator에게:
- Backend Architect의 배포 아키텍처
- 시스템 아키텍처에서 도출된 환경 요구사항
- 인프라 요구에서 도출된 모니터링 요구사항

### Frontend Developer에게:
- UX Architect의 CSS 디자인 시스템
- Brand Guardian의 브랜드 아이덴티티
- UX Architect의 컴포넌트 아키텍처
- Backend Architect의 API 명세

### Backend Architect에게 (계속 진행):
- 배포 준비가 된 데이터베이스 스키마
- 구현 준비가 된 API 스캐폴드
- 정의된 인증 시스템 아키텍처
```

---

*Phase 1은 Studio Producer와 Reality Checker가 모두 아키텍처 패키지를 승인할 때 완료됩니다.*
