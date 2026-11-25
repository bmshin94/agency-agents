# 🔍 Phase 0 플레이북 — 정보 수집 및 디스커버리

> **기간**: 3~7일 | **에이전트**: 6 | **게이트 키퍼**: Executive Summary Generator

---

## 목표

자원을 투입하기 전에 기회를 검증합니다. 문제, 시장, 규제 환경을 이해하기 전에는 아무것도 만들지 않습니다.

## 사전 조건

- [ ] 프로젝트 브리프 또는 초기 콘셉트가 존재함
- [ ] 이해관계자 스폰서가 정해짐
- [ ] 디스커버리 단계 예산이 승인됨

## 에이전트 활성화 순서

### 웨이브 1: 병렬 가동 (1일차)

#### 🔍 Trend Researcher — 시장 정보 수집 리드
```
[PROJECT DOMAIN]에 대한 시장 정보 수집을 위해 Trend Researcher를 활성화합니다.

필요한 산출물:
1. 경쟁 구도 분석 (직접 + 간접 경쟁자)
2. 시장 규모 추정: 방법론을 포함한 TAM, SAM, SOM
3. 트렌드 라이프사이클 매핑: 이 시장은 수용 곡선의 어디에 있는가?
4. 신뢰 구간을 포함한 3~6개월 트렌드 전망
5. 해당 영역의 투자 및 펀딩 동향

출처: 검증된 고유 출처 최소 15개
포맷: 경영진 요약이 포함된 전략 리포트
기간: 3일
```

#### 💬 Feedback Synthesizer — 사용자 니즈 분석
```
[PROJECT DOMAIN]에 대한 사용자 니즈 분석을 위해 Feedback Synthesizer를 활성화합니다.

필요한 산출물:
1. 멀티채널 피드백 수집 계획 (설문, 인터뷰, 리뷰, 소셜)
2. 기존 사용자 접점 전반의 감성 분석
3. 페인 포인트 식별 및 우선순위화 (RICE 점수)
4. 비즈니스 가치 추정이 포함된 기능 요청 분석
5. 피드백 패턴에서 도출한 이탈 리스크 지표

포맷: 우선순위 매트릭스가 포함된 피드백 종합 리포트
기간: 3일
```

#### 🔍 UX Researcher — 사용자 행동 분석
```
[PROJECT DOMAIN]에 대한 사용자 행동 분석을 위해 UX Researcher를 활성화합니다.

필요한 산출물:
1. 사용자 인터뷰 계획 (타깃 사용자 5~10명)
2. 퍼소나 정의 (주요 퍼소나 3~5개)
3. 주요 사용자 플로우의 여정 지도
4. 경쟁 제품의 사용성 휴리스틱 평가
5. 통계적으로 검증된 행동 인사이트

포맷: 퍼소나와 여정 지도가 포함된 리서치 결과 리포트
기간: 5일
```

### 웨이브 2: 병렬 가동 (1일차, 웨이브 1과 독립적으로)

#### 📊 Analytics Reporter — 데이터 환경 평가
```
[PROJECT DOMAIN]에 대한 데이터 환경 평가를 위해 Analytics Reporter를 활성화합니다.

필요한 산출물:
1. 기존 데이터 소스 감사 (어떤 데이터를 쓸 수 있는가?)
2. 시그널 식별 (무엇을 측정할 수 있는가?)
3. 기준선 지표 설정
4. 완전성 점수를 포함한 데이터 품질 평가
5. 분석 인프라 권고 사항

포맷: 시그널 지도가 포함된 데이터 감사 리포트
기간: 2일
```

#### ⚖️ Legal Compliance Checker — 규제 스캔
```
[PROJECT DOMAIN]에 대한 규제 스캔을 위해 Legal Compliance Checker를 활성화합니다.

필요한 산출물:
1. 적용되는 규제 프레임워크 (GDPR, CCPA, HIPAA 등)
2. 데이터 처리 요구사항과 제약
3. 타깃 시장별 관할권 매핑
4. 심각도 등급이 포함된 컴플라이언스 리스크 평가
5. 발목을 잡는 이슈와 관리 가능한 이슈 구분

포맷: 컴플라이언스 요구사항 매트릭스
기간: 3일
```

#### 🛠️ Tool Evaluator — 기술 환경 조사
```
[PROJECT DOMAIN]에 대한 기술 환경 평가를 위해 Tool Evaluator를 활성화합니다.

필요한 산출물:
1. 해당 문제 영역에 맞는 기술 스택 평가
2. 핵심 구성 요소의 구축 vs 구매 분석
3. 기존 시스템과의 연동 타당성
4. 오픈소스 vs 상용 솔루션 평가
5. 기술 리스크 평가

포맷: 권고 매트릭스가 포함된 기술 스택 평가서
기간: 2일
```

## 수렴 지점 (5~7일차)

여섯 에이전트 모두가 리포트를 제출합니다. Executive Summary Generator가 이를 종합합니다:

```
Phase 0 결과를 종합하기 위해 Executive Summary Generator를 활성화합니다.

입력 문서:
1. Trend Researcher → 시장 분석 리포트
2. Feedback Synthesizer → 피드백 종합 리포트
3. UX Researcher → 리서치 결과 리포트
4. Analytics Reporter → 데이터 감사 리포트
5. Legal Compliance Checker → 컴플라이언스 요구사항 매트릭스
6. Tool Evaluator → 기술 스택 평가서

산출물: 경영진 요약 (500단어 이하, SCQA 포맷)
필요한 결정: GO / NO-GO / PIVOT
포함 항목: 정량화된 시장 기회, 검증된 사용자 니즈, 규제 경로, 기술 타당성
```

## 품질 게이트 체크리스트

| # | 기준 | 증거 출처 | 상태 |
|---|-----------|----------------|--------|
| 1 | TAM이 최소 성립 기준을 넘는 시장 기회 검증 | Trend Researcher 리포트 | ☐ |
| 2 | 근거 데이터가 있는 검증된 사용자 페인 포인트 3개 이상 | Feedback Synthesizer + UX Researcher | ☐ |
| 3 | 발목을 잡는 컴플라이언스 이슈 없음 | Legal Compliance Checker 매트릭스 | ☐ |
| 4 | 핵심 지표와 데이터 소스 식별 완료 | Analytics Reporter 감사 결과 | ☐ |
| 5 | 기술 스택의 타당성 검토 및 평가 완료 | Tool Evaluator 평가서 | ☐ |
| 6 | GO/NO-GO 권고가 담긴 경영진 요약 전달 완료 | Executive Summary Generator | ☐ |

## 게이트 판정

- **GO**: Phase 1 — 전략 및 아키텍처로 진행
- **NO-GO**: 결과를 보관하고 배운 점을 기록한 뒤 자원을 다른 곳으로 돌림
- **PIVOT**: 결과에 따라 범위/방향을 수정하고 표적 디스커버리를 다시 수행

## Phase 1로의 핸드오프

```markdown
## Phase 0 → Phase 1 핸드오프 패키지

### 다음 단계로 넘기는 문서:
1. 시장 분석 리포트 (Trend Researcher)
2. 피드백 종합 리포트 (Feedback Synthesizer)
3. 사용자 퍼소나와 여정 지도 (UX Researcher)
4. 데이터 감사 리포트 (Analytics Reporter)
5. 컴플라이언스 요구사항 매트릭스 (Legal Compliance Checker)
6. 기술 스택 평가서 (Tool Evaluator)
7. GO 결정이 담긴 경영진 요약 (Executive Summary Generator)

### 식별된 핵심 제약 조건:
- [Legal Compliance Checker가 찾은 규제 제약]
- [Tool Evaluator가 찾은 기술 제약]
- [Trend Researcher가 찾은 시장 타이밍 제약]

### 우선순위 사용자 니즈 (Sprint Prioritizer용):
1. [페인 포인트 1 — Feedback Synthesizer]
2. [페인 포인트 2 — UX Researcher]
3. [페인 포인트 3 — Feedback Synthesizer]
```

---

*Phase 0은 Executive Summary Generator가 여섯 디스커버리 에이전트의 증거를 근거로 GO 결정을 내릴 때 완료됩니다.*
