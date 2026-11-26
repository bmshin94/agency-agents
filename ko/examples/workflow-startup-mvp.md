# 멀티 에이전트 워크플로: 스타트업 MVP

> 아이디어부터 출시 가능한 MVP까지, 여러 에이전트를 조율하는 방법을 단계별로 보여주는 예제입니다.

## 시나리오

당신은 SaaS MVP를 만들고 있습니다 — 원격 팀을 위한 팀 회고 도구입니다. 사용자 가입, 핵심 기능, 랜딩 페이지를 갖춘 동작하는 제품을 4주 안에 출시해야 합니다.

## 에이전트 팀

| 에이전트 | 이 워크플로에서의 역할 |
|-------|---------------------|
| Sprint Prioritizer | 프로젝트를 주 단위 스프린트로 분해 |
| UX Researcher | 빠른 사용자 인터뷰로 아이디어 검증 |
| Backend Architect | API와 데이터 모델 설계 |
| Frontend Developer | React 앱 구축 |
| Rapid Prototyper | 첫 버전을 빠르게 동작시키기 |
| Growth Hacker | 개발과 동시에 출시 전략 수립 |
| Reality Checker | 다음 단계로 넘어가기 전 각 마일스톤 검증 |

## 워크플로

### 1주차: 디스커버리 + 아키텍처

**Step 1 — Sprint Prioritizer 활성화**

```
Sprint Prioritizer를 활성화합니다.

프로젝트: RetroBoard — 원격 팀을 위한 실시간 팀 회고 도구.
일정: MVP 출시까지 4주.
핵심 기능: 사용자 인증, 회고 보드 생성, 카드 추가, 투표, 액션 아이템.
제약 조건: 1인 개발자, React + Node.js 스택, Vercel + Railway 배포.

이를 명확한 산출물과 수락 기준을 갖춘 4개의 주간 스프린트로 분해해 주세요.
```

**Step 2 — UX Researcher 활성화 (병렬 진행)**

```
UX Researcher를 활성화합니다.

원격 팀(5~20명)을 위한 팀 회고 도구를 만들고 있습니다.
경쟁 제품: EasyRetro, Retrium, Parabol.

빠른 경쟁 분석을 수행하고 다음을 파악해 주세요:
1. 반드시 갖춰야 하는 기본 기능은 무엇인가
2. 경쟁 제품이 부족한 지점은 어디인가
3. 우리가 확보할 수 있는 차별점 한 가지

1페이지 리서치 브리프로 출력해 주세요.
```

**Step 3 — Backend Architect에게 인계**

```
Backend Architect를 활성화합니다.

우리 스프린트 계획입니다: [paste Sprint Prioritizer output]
우리 리서치 브리프입니다: [paste UX Researcher output]

RetroBoard의 API와 데이터베이스 스키마를 설계해 주세요.
스택: Node.js, Express, PostgreSQL, 실시간 처리는 Socket.io.

산출물:
1. 데이터베이스 스키마 (SQL)
2. REST API 엔드포인트 목록
3. 실시간 보드 업데이트용 WebSocket 이벤트
4. 인증 전략 권고안
```

### 2주차: 핵심 기능 구축

**Step 4 — Frontend Developer + Rapid Prototyper 활성화**

```
Frontend Developer를 활성화합니다.

API 명세입니다: [paste Backend Architect output]

RetroBoard React 앱을 구축해 주세요:
- 스택: React, TypeScript, Tailwind, Socket.io-client
- 페이지: Login, Dashboard, Board view
- 컴포넌트: RetroCard, VoteButton, ActionItem, BoardColumn

Board view부터 시작하세요 — 핵심 경험이 여기에 있습니다.
실시간성에 집중하세요: 한 사용자가 카드를 추가하면 모두가 즉시 봐야 합니다.
```

**Step 5 — 중간 지점에서 리얼리티 체크**

```
Reality Checker를 활성화합니다.

RetroBoard 4주 MVP 개발의 2주차입니다.

지금까지 확보한 것:
- 데이터베이스 스키마: [paste]
- API 엔드포인트: [paste]
- 프론트엔드 컴포넌트: [paste]

평가해 주세요:
1. 남은 2주 안에 현실적으로 출시할 수 있는가?
2. 마감을 맞추려면 무엇을 덜어내야 하는가?
3. 출시 시점에 발목을 잡을 기술 부채가 있는가?
```

### 3주차: 완성도 높이기 + 랜딩 페이지

**Step 6 — Frontend Developer는 계속, Growth Hacker 투입**

```
Growth Hacker를 활성화합니다.

제품: RetroBoard — 팀 회고 도구, 1주 후 출시.
타깃: 원격 우선 기업의 엔지니어링 매니저와 스크럼 마스터.
예산: $0 (오가닉 출시만 진행).

출시 계획을 수립해 주세요:
1. 랜딩 페이지 카피 (히어로, 기능, CTA)
2. 출시 채널 (Product Hunt, Reddit, Hacker News, Twitter)
3. 일자별 출시 시퀀스
4. 출시 첫 주에 추적할 지표
```

### 4주차: 출시

**Step 7 — 최종 리얼리티 체크**

```
Reality Checker를 활성화합니다.

RetroBoard 출시 준비가 끝났습니다. 프로덕션 준비 상태를 평가해 주세요:

- 운영 URL: [url]
- 테스트 계정 생성: 완료
- 에러 모니터링: Sentry 구성 완료
- 데이터베이스 백업: 매일 자동 수행

출시 체크리스트를 전부 점검하고 GO / NO-GO 판정을 내려 주세요.
각 기준마다 근거를 요구하세요.
```

## 핵심 패턴

1. **순차적 인계**: 각 에이전트의 출력이 다음 에이전트의 입력이 됩니다
2. **병렬 작업**: 1주차에 UX Researcher와 Sprint Prioritizer는 동시에 돌릴 수 있습니다
3. **품질 게이트**: 중간 지점과 출시 직전의 Reality Checker가 망가진 코드의 출시를 막아 줍니다
4. **컨텍스트 전달**: 이전 에이전트의 출력을 항상 다음 프롬프트에 붙여 넣으세요 — 에이전트끼리는 기억을 공유하지 않습니다

## 팁

- 에이전트 출력은 단계 사이에 복사해 붙여 넣으세요 — 요약하지 말고 전체 출력을 그대로 쓰세요
- Reality Checker가 문제를 지적하면 해당 전문 에이전트로 되돌아가 수정하세요
- 수동 방식에 익숙해지면 이 흐름을 자동화할 수 있는 Orchestrator 에이전트를 떠올려 보세요
