# 🔄 Phase 6 플레이북 — 운영 및 발전

> **기간**: 상시 | **에이전트**: 12명 이상 (순환) | **거버넌스**: Studio Producer

---

## 목표

지속적인 개선을 동반한 상시 운영입니다. 제품이 살아 움직이기 시작했습니다 — 이제 번창하게 만들 차례입니다. 이 단계에는 종료일이 없으며, 제품이 시장에 있는 동안 계속됩니다.

## 사전 조건

- [ ] Phase 5 품질 게이트 통과 (안정적인 출시)
- [ ] Phase 5 핸드오프 패키지 수령
- [ ] 운영 주기 확립
- [ ] 기준선 지표 문서화

## 운영 주기

### 상시 (항상 활성)

| 에이전트 | 책임 | SLA |
|-------|---------------|-----|
| **Infrastructure Maintainer** | 시스템 가동률, 성능, 보안 | 가동률 99.9%, MTTR 30분 미만 |
| **Support Responder** | 고객 지원, 이슈 해결 | 최초 응답 4시간 미만 |
| **DevOps Automator** | 배포 파이프라인, 핫픽스 | 하루 여러 번 배포 가능 |

### 매일

| 에이전트 | 활동 | 산출물 |
|-------|----------|--------|
| **Analytics Reporter** | KPI 대시보드 갱신 | 일일 지표 스냅샷 |
| **Support Responder** | 이슈 분류 및 해결 | 지원 티켓 요약 |
| **Infrastructure Maintainer** | 시스템 상태 점검 | 상태 리포트 |

### 매주

| 에이전트 | 활동 | 산출물 |
|-------|----------|--------|
| **Analytics Reporter** | 주간 성과 분석 | 주간 분석 리포트 |
| **Feedback Synthesizer** | 사용자 피드백 종합 | 주간 피드백 요약 |
| **Sprint Prioritizer** | 백로그 정리 + 스프린트 계획 | 스프린트 플랜 |
| **Growth Hacker** | 그로스 채널 최적화 | 그로스 지표 리포트 |
| **Project Shepherd** | 부서 간 조율 | 주간 상태 업데이트 |

### 격주

| 에이전트 | 활동 | 산출물 |
|-------|----------|--------|
| **Feedback Synthesizer** | 심층 피드백 분석 | 격주 인사이트 리포트 |
| **Experiment Tracker** | A/B 테스트 분석 | 실험 결과 요약 |
| **Content Creator** | 콘텐츠 캘린더 실행 | 발행 콘텐츠 리포트 |

### 매월

| 에이전트 | 활동 | 산출물 |
|-------|----------|--------|
| **Executive Summary Generator** | 경영진 보고 | 월간 경영진 요약 |
| **Finance Tracker** | 재무 성과 검토 | 월간 재무 리포트 |
| **Legal Compliance Checker** | 규제 모니터링 | 컴플라이언스 현황 리포트 |
| **Trend Researcher** | 시장 정보 업데이트 | 월간 시장 브리프 |
| **Brand Guardian** | 브랜드 일관성 감사 | 브랜드 건강도 리포트 |

### 분기별

| 에이전트 | 활동 | 산출물 |
|-------|----------|--------|
| **Studio Producer** | 전략 포트폴리오 검토 | 분기 전략 리뷰 |
| **Workflow Optimizer** | 프로세스 효율 감사 | 최적화 리포트 |
| **Performance Benchmarker** | 성능 회귀 테스트 | 분기 성능 리포트 |
| **Tool Evaluator** | 기술 스택 검토 | 기술 부채 평가서 |

## 지속적 개선 루프

```
측정 (Analytics Reporter)
    │
    ▼
분석 (Feedback Synthesizer + Analytics Reporter)
    │
    ▼
계획 (Sprint Prioritizer + Studio Producer)
    │
    ▼
구현 (Phase 3 Dev↔QA 루프 — 미니 사이클)
    │
    ▼
검증 (Evidence Collector + Reality Checker)
    │
    ▼
배포 (DevOps Automator)
    │
    ▼
측정 (처음으로 돌아감)
```

### Phase 6에서의 기능 개발

새 기능은 압축된 NEXUS 사이클을 따릅니다:

```
1. Sprint Prioritizer가 백로그에서 기능을 선정
2. 적절한 개발 에이전트가 구현
3. Evidence Collector가 검증 (Dev↔QA 루프)
4. DevOps Automator가 배포 (피처 플래그 또는 직접 배포)
5. Experiment Tracker가 모니터링 (해당 시 A/B 테스트)
6. Analytics Reporter가 임팩트를 측정
7. Feedback Synthesizer가 사용자 반응을 수집
```

## 인시던트 대응 프로토콜

### 심각도 레벨

| 레벨 | 정의 | 대응 시간 | 결정 권한 |
|-------|-----------|--------------|-------------------|
| **P0 — 치명적** | 서비스 중단, 데이터 유실, 보안 침해 | 즉시 | Studio Producer |
| **P1 — 높음** | 주요 기능 장애, 심각한 성능 저하 | 1시간 미만 | Project Shepherd |
| **P2 — 중간** | 사소한 기능 이슈, 우회 방법 존재 | 4시간 미만 | Agents Orchestrator |
| **P3 — 낮음** | 외형상 문제, 경미한 불편 | 다음 스프린트 | Sprint Prioritizer |

### 인시던트 대응 순서

```
감지 (Infrastructure Maintainer 또는 Support Responder)
    │
    ▼
분류 (Agents Orchestrator)
    ├── 심각도 분류 (P0~P3)
    ├── 대응 팀 배정
    └── 이해관계자 통보
    │
    ▼
대응
    ├── P0: Infrastructure Maintainer + DevOps Automator + Backend Architect
    ├── P1: 해당 개발 에이전트 + DevOps Automator
    ├── P2: 해당 개발 에이전트
    └── P3: 스프린트 백로그에 추가
    │
    ▼
해결
    ├── 수정 구현 및 배포
    ├── Evidence Collector가 수정 사항 검증
    └── Infrastructure Maintainer가 안정성 확인
    │
    ▼
포스트모템
    ├── Workflow Optimizer가 회고 주도
    ├── 근본 원인 분석 문서화
    ├── 재발 방지 조치 식별
    └── 프로세스 개선 적용
```

## 그로스 운영

### 월간 그로스 리뷰 (Growth Hacker 주도)

```
1. 채널 성과 분석
   - 채널별 유입 (오가닉, 유료, 추천, 소셜)
   - 채널별 CAC
   - 퍼널 단계별 전환율
   - LTV:CAC 비율 추세

2. 실험 결과
   - 완료된 A/B 테스트와 결과
   - 통계적 유의성 검증
   - 승자 적용 현황
   - 신규 실험 파이프라인

3. 리텐션 분석
   - 코호트 리텐션 곡선
   - 이탈 리스크 식별
   - 재참여 캠페인 결과
   - 기능 사용률 지표

4. 그로스 로드맵 갱신
   - 다음 달 그로스 실험
   - 채널 예산 재배분
   - 신규 채널 탐색
   - 바이럴 계수 최적화
```

### 콘텐츠 운영 (Content Creator + Social Media Strategist)

```
매주:
- 콘텐츠 캘린더 실행
- 소셜 미디어 참여
- 커뮤니티 관리
- 성과 추적

매월:
- 콘텐츠 성과 검토
- 에디토리얼 캘린더 기획
- 플랫폼 알고리즘 변화 반영
- 콘텐츠 전략 정교화

플랫폼별:
- Twitter Engager → 매일 소통, 주간 스레드
- Instagram Curator → 주 3~5건 게시, 매일 스토리
- TikTok Strategist → 주 3~5편 영상
- Reddit Community Builder → 매일 진정성 있는 소통
```

## 재무 운영

### 월간 재무 리뷰 (Finance Tracker)

```
1. 매출 분석
   - MRR/ARR 추적
   - 세그먼트/플랜별 매출
   - 업셀 매출
   - 이탈이 매출에 미친 영향

2. 비용 분석
   - 인프라 비용
   - 채널별 마케팅 지출
   - 팀/자원 비용
   - 도구 및 서비스 비용

3. 유닛 이코노믹스
   - CAC 추세
   - LTV 추세
   - LTV:CAC 비율
   - 투자 회수 기간

4. 전망
   - 매출 전망 (3개월 롤링)
   - 비용 전망
   - 현금 흐름 예측
   - 예산 차이 분석
```

## 컴플라이언스 운영

### 월간 컴플라이언스 점검 (Legal Compliance Checker)

```
1. 규제 모니터링
   - 제품에 영향을 주는 신규 규제
   - 기존 규제의 변경 사항
   - 업계 내 제재 사례
   - 컴플라이언스 기한 추적

2. 프라이버시 준수
   - 정보주체 요청 처리
   - 동의 관리의 실효성
   - 데이터 보존 정책 준수
   - 국외 이전 준수

3. 보안 준수
   - 취약점 스캔 결과
   - 패치 관리 현황
   - 접근 제어 검토
   - 인시던트 로그 검토

4. 감사 대비
   - 문서 최신성
   - 증거 수집 현황
   - 교육 이수율
   - 정책 동의 확인 추적
```

## 전략적 발전

### 분기 전략 리뷰 (Studio Producer)

```
1. 시장 포지션 평가
   - 경쟁 구도 변화 (Trend Researcher 입력)
   - 시장 점유율 변화
   - 브랜드 인식 (Brand Guardian 입력)
   - 고객 만족도 추세 (Feedback Synthesizer 입력)

2. 제품 전략
   - 기능 로드맵 검토
   - 기술 부채 평가 (Tool Evaluator 입력)
   - 플랫폼 확장 기회
   - 파트너십 검토

3. 그로스 전략
   - 채널 효율 검토
   - 신규 시장 기회
   - 가격 전략 평가
   - 확장 계획

4. 조직 건강도
   - 프로세스 효율 (Workflow Optimizer 입력)
   - 팀 성과 지표
   - 자원 배분 최적화
   - 역량 개발 필요 사항

산출물: 분기 전략 리뷰 → 갱신된 로드맵과 우선순위
```

## Phase 6 성공 지표

| 범주 | 지표 | 목표 | 담당 |
|----------|--------|--------|-------|
| **신뢰성** | 시스템 가동률 | 99.9% 초과 | Infrastructure Maintainer |
| **신뢰성** | MTTR | 30분 미만 | Infrastructure Maintainer |
| **그로스** | 전월 대비 사용자 성장 | 20% 초과 | Growth Hacker |
| **그로스** | 활성화율 | 60% 초과 | Analytics Reporter |
| **리텐션** | 7일 리텐션 | 40% 초과 | Analytics Reporter |
| **리텐션** | 30일 리텐션 | 20% 초과 | Analytics Reporter |
| **재무** | LTV:CAC 비율 | 3:1 초과 | Finance Tracker |
| **재무** | 포트폴리오 ROI | 25% 초과 | Studio Producer |
| **품질** | NPS 점수 | 50 초과 | Feedback Synthesizer |
| **품질** | 지원 해결 시간 | 4시간 미만 | Support Responder |
| **컴플라이언스** | 규제 준수율 | 98% 초과 | Legal Compliance Checker |
| **효율** | 배포 빈도 | 하루 여러 번 | DevOps Automator |
| **효율** | 프로세스 개선 | 분기당 20% | Workflow Optimizer |

---

*Phase 6에는 종료일이 없습니다. 제품이 시장에 있는 동안 계속되며, 지속적 개선 사이클이 제품을 앞으로 밀고 나갑니다. 중요한 신규 기능이나 피보팅이 필요할 때는 NEXUS 파이프라인(NEXUS-Sprint 또는 NEXUS-Micro)을 다시 가동할 수 있습니다.*
