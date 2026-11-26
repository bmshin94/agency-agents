# 멀티 에이전트 워크플로: 영속 메모리를 갖춘 스타트업 MVP

> [workflow-startup-mvp.md](workflow-startup-mvp.md)와 동일한 스타트업 MVP 워크플로지만, MCP 메모리 서버가 에이전트 사이의 상태를 관리합니다. 복사·붙여넣기 인계는 더 이상 필요 없습니다.

## 수동 인계의 문제

표준 워크플로에서는 에이전트 간 전환이 매번 이런 모습입니다.

```
Backend Architect를 활성화합니다.

우리 스프린트 계획은 다음과 같습니다: [Sprint Prioritizer 산출물 붙여넣기]
우리 리서치 브리프는 다음과 같습니다: [UX Researcher 산출물 붙여넣기]

RetroBoard의 API와 데이터베이스 스키마를 설계하세요.
...
```

접착제 역할은 사용자입니다. 에이전트 사이로 산출물을 복사·붙여넣기 하고, 무엇이 끝났는지 추적하며, 그 과정에서 컨텍스트를 잃지 않기를 바라야 합니다. 작은 프로젝트라면 통하지만, 다음 상황에서는 무너집니다.

- 세션이 타임아웃되어 산출물을 잃어버립니다
- 여러 에이전트가 동일한 컨텍스트를 필요로 합니다
- QA가 실패해 이전 상태로 되돌려야 합니다
- 프로젝트가 여러 세션에 걸쳐 며칠, 몇 주씩 이어집니다

## 해결 방법

MCP 메모리 서버를 설치하면 에이전트가 산출물을 메모리에 저장하고 필요한 것을 알아서 가져옵니다. 인계는 이렇게 바뀝니다.

```
Backend Architect를 활성화합니다.

프로젝트: RetroBoard. 이 프로젝트의 이전 컨텍스트를 recall한 뒤
API와 데이터베이스 스키마를 설계하세요.
```

에이전트는 메모리에서 RetroBoard 관련 컨텍스트를 검색해 이전 에이전트들이 저장해 둔 스프린트 계획과 리서치 브리프를 찾아내고, 그 지점부터 이어서 작업합니다.

## 설정

`remember`, `recall`, `rollback` 동작을 지원하는 MCP 호환 메모리 서버를 설치하세요. 설정 방법은 [integrations/mcp-memory/README.md](../integrations/mcp-memory/README.md)를 참고하세요.

## 시나리오

표준 워크플로와 동일합니다. SaaS 팀 회고 도구(RetroBoard), MVP까지 4주, 1인 개발자.

## 에이전트 팀

| 에이전트 | 이 워크플로에서의 역할 |
|-------|---------------------|
| Sprint Prioritizer | 프로젝트를 주간 스프린트로 분할 |
| UX Researcher | 빠른 사용자 인터뷰로 아이디어 검증 |
| Backend Architect | API와 데이터 모델 설계 |
| Frontend Developer | React 앱 구축 |
| Rapid Prototyper | 첫 버전을 빠르게 동작시키기 |
| Growth Hacker | 개발과 병행해 출시 전략 수립 |
| Reality Checker | 다음 단계로 넘어가기 전 각 마일스톤 게이트 심사 |

각 에이전트의 프롬프트에는 Memory Integration 섹션이 있습니다(추가 방법은 [integrations/mcp-memory/README.md](../integrations/mcp-memory/README.md) 참고).

## 워크플로

### 1주차: 디스커버리 + 아키텍처

**1단계 — Sprint Prioritizer 활성화**

```
Sprint Prioritizer를 활성화합니다.

프로젝트: RetroBoard — 원격 팀을 위한 실시간 팀 회고 도구.
일정: MVP 출시까지 4주.
핵심 기능: 사용자 인증, 회고 보드 생성, 카드 추가, 투표, 액션 아이템.
제약: 1인 개발자, React + Node.js 스택, Vercel + Railway 배포.

명확한 산출물과 수용 기준을 갖춘 4개의 주간 스프린트로 분할하세요.
완료하면 스프린트 계획을 이 프로젝트 태그를 붙여 remember하세요.
```

Sprint Prioritizer는 스프린트 계획을 만들어 `sprint-prioritizer`, `retroboard`, `sprint-plan` 태그를 붙여 메모리에 저장합니다.

**2단계 — UX Researcher 활성화(병렬)**

```
UX Researcher를 활성화합니다.

원격 팀(5~20명)을 위한 팀 회고 도구를 만들고 있습니다.
경쟁 제품: EasyRetro, Retrium, Parabol.

빠른 경쟁 분석을 수행하고 다음을 찾아내세요.
1. 기본으로 갖춰야 할 기능은 무엇인가
2. 경쟁 제품이 부족한 지점은 어디인가
3. 우리가 선점할 수 있는 차별점 하나

1페이지 리서치 브리프로 출력하세요. 완료하면 이 프로젝트 태그를 붙여 remember하세요.
```

UX Researcher는 리서치 브리프를 `ux-researcher`, `retroboard`, `research-brief` 태그를 붙여 저장합니다.

**3단계 — Backend Architect에게 인계**

```
Backend Architect를 활성화합니다.

프로젝트: RetroBoard. 이전 에이전트들이 남긴 스프린트 계획과 리서치 브리프를 recall하세요.
스택: Node.js, Express, PostgreSQL, 실시간은 Socket.io.

다음을 설계하세요.
1. 데이터베이스 스키마(SQL)
2. REST API 엔드포인트 목록
3. 실시간 보드 업데이트용 WebSocket 이벤트
4. 인증 전략 권고안

각 산출물을 이 프로젝트와 frontend-developer를 대상으로 태그해 remember하세요.
```

Backend Architect는 메모리에서 스프린트 계획과 리서치 브리프를 자동으로 recall합니다. 복사·붙여넣기가 없습니다. 그리고 스키마와 API 명세를 `backend-architect`, `retroboard`, `api-spec`, `frontend-developer` 태그를 붙여 저장합니다.

### 2주차: 핵심 기능 구축

**4단계 — Frontend Developer + Rapid Prototyper 활성화**

```
Frontend Developer를 활성화합니다.

프로젝트: RetroBoard. Backend Architect가 남긴 API 명세와 스키마를 recall하세요.

RetroBoard React 앱을 구축하세요.
- 스택: React, TypeScript, Tailwind, Socket.io-client
- 페이지: 로그인, 대시보드, 보드 화면
- 컴포넌트: RetroCard, VoteButton, ActionItem, BoardColumn

핵심 경험인 보드 화면부터 시작하세요.
실시간에 집중하세요. 한 사용자가 카드를 추가하면 모두가 볼 수 있어야 합니다.
진행 상황을 이 프로젝트 태그를 붙여 remember하세요.
```

Frontend Developer는 메모리에서 API 명세를 가져와 그에 맞춰 개발합니다.

**5단계 — 중간 지점에서 리얼리티 체크**

```
Reality Checker를 활성화합니다.

프로젝트: RetroBoard. 4주 MVP 개발의 2주차입니다.

이 프로젝트에서 이전 에이전트들이 남긴 모든 산출물을 recall하세요.

다음을 평가하세요.
1. 남은 2주 안에 현실적으로 출시할 수 있는가?
2. 마감을 맞추려면 무엇을 덜어내야 하는가?
3. 출시 때 발목을 잡을 기술 부채가 있는가?

판정 결과를 이 프로젝트 태그를 붙여 remember하세요.
```

Reality Checker는 지금까지 만들어진 모든 것 — 스프린트 계획, 리서치 브리프, 스키마, API 명세, 프론트엔드 진행 상황 — 을 사용자가 모아서 붙여넣지 않아도 전부 들여다볼 수 있습니다.

### 3주차: 다듬기 + 랜딩 페이지

**6단계 — Frontend Developer는 계속, Growth Hacker 투입**

```
Growth Hacker를 활성화합니다.

제품: RetroBoard — 팀 회고 도구, 1주 후 출시.
타깃: 원격 우선 기업의 엔지니어링 매니저와 스크럼 마스터.
예산: $0(오가닉 출시만).

프로젝트 컨텍스트와 Reality Checker의 판정 결과를 recall하세요.

출시 계획을 만드세요.
1. 랜딩 페이지 카피(히어로, 기능, CTA)
2. 출시 채널(Product Hunt, Reddit, Hacker News, Twitter)
3. 일자별 출시 시퀀스
4. 1주차에 추적할 지표

출시 계획을 이 프로젝트 태그를 붙여 remember하세요.
```

### 4주차: 출시

**7단계 — 최종 리얼리티 체크**

```
Reality Checker를 활성화합니다.

프로젝트: RetroBoard, 출시 준비 완료.

모든 프로젝트 컨텍스트, 이전 판정 결과, 출시 계획을 recall하세요.

프로덕션 준비 상태를 평가하세요.
- 운영 URL: [url]
- 테스트 계정 생성: 완료
- 에러 모니터링: Sentry 구성 완료
- 데이터베이스 백업: 매일 자동

출시 체크리스트를 점검하고 GO / NO-GO 결정을 내리세요.
각 기준마다 근거를 요구하세요.
```

### QA가 실패했을 때: 롤백

표준 워크플로에서는 Reality Checker가 산출물을 반려하면 담당 에이전트에게 돌아가 무엇이 잘못됐는지 설명해야 합니다. 메모리가 있으면 복구 루프가 훨씬 촘촘해집니다.

```
Backend Architect를 활성화합니다.

프로젝트: RetroBoard. Reality Checker가 API 설계에 문제를 제기했습니다.
Reality Checker의 피드백과 당신이 이전에 만든 API 명세를 recall하세요.
마지막으로 정상 동작이 확인된 스키마로 roll back한 뒤 제기된 문제를 구체적으로 해결하세요.
완료하면 갱신된 산출물을 remember하세요.
```

Backend Architect는 Reality Checker가 무엇을 지적했는지 정확히 확인하고, 자신의 이전 작업을 recall하고, 체크포인트로 롤백해 수정안을 만들어 냅니다 — 사용자가 버전을 손으로 추적할 필요가 전혀 없습니다.

## 도입 전과 후

| 항목 | 표준 워크플로 | 메모리 적용 |
|--------|------------------|-------------|
| **인계** | 에이전트 사이로 전체 산출물을 복사·붙여넣기 | 에이전트가 필요한 것을 알아서 recall |
| **컨텍스트 손실** | 세션 타임아웃으로 전부 날아감 | 메모리가 세션을 넘어 유지됨 |
| **멀티 에이전트 컨텍스트** | N개 에이전트의 컨텍스트를 손으로 취합 | 에이전트가 프로젝트 태그로 메모리를 검색 |
| **QA 실패 복구** | 무엇이 잘못됐는지 손으로 설명 | 에이전트가 피드백을 recall하고 롤백 |
| **여러 날 걸리는 프로젝트** | 매 세션마다 컨텍스트를 다시 세팅 | 에이전트가 중단 지점부터 이어감 |
| **필요한 설정** | 없음 | MCP 메모리 서버 설치 |

## 핵심 패턴

1. **모든 것에 프로젝트 이름을 태그하세요**: recall이 동작하게 만드는 핵심입니다. 모든 메모리에 `retroboard`(또는 각자의 프로젝트 이름) 태그가 붙습니다.
2. **산출물은 받는 에이전트를 대상으로 태그하세요**: Backend Architect가 API 명세를 완성하면 메모리에 `frontend-developer` 태그를 붙여, Frontend Developer가 recall할 때 찾을 수 있게 합니다.
3. **Reality Checker는 전체를 들여다봅니다**: 모든 에이전트가 작업물을 메모리에 저장하므로, Reality Checker는 사용자가 취합하지 않아도 프로젝트의 모든 내용을 recall할 수 있습니다.
4. **롤백이 수동 되돌리기를 대체합니다**: 무언가 실패하면 무엇이 바뀌었는지 추적하려 애쓰는 대신 마지막 체크포인트로 롤백하세요.

## 팁

- 모든 에이전트를 한 번에 수정할 필요는 없습니다. 가장 많이 쓰는 에이전트에 Memory Integration을 먼저 추가하고 거기서 확장해 나가세요.
- 메모리 지침은 코드가 아니라 프롬프트입니다. LLM이 이를 해석해 필요할 때 MCP 도구를 호출합니다. 문구는 각자의 스타일에 맞게 조정해도 됩니다.
- `remember`, `recall`, `rollback`, `search` 도구를 지원하는 MCP 호환 메모리 서버라면 어떤 것이든 이 워크플로와 함께 동작합니다.
