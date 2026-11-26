# Hermes Agency Agents 라우터 플러그인

`scripts/convert.sh --tool hermes`로 생성됩니다.

이 연동은 수백 개의 생성된 스킬을 `skills.external_dirs`에 추가하는 대신,
`agency-agents-router`라는 Hermes 플러그인 하나만 설치합니다. Hermes는 시작 시
작고 고정된 도구 표면만 보게 되고, 전체 Agency 로스터는 디스크의 `data/agents.json`에
저장되어 필요할 때 지연 검색·로드됩니다.

생성된 에이전트 수: 279

## Hermes에 노출되는 도구

- `agency_agents_search` — 쿼리/디비전으로 적합한 전문가를 찾습니다.
- `agency_agents_inspect` — 특정 전문가의 메타데이터나 본문 전체를 확인합니다.
- `agency_agents_load` — 현재 작업에 맞게 전문가 프롬프트 하나를 구성합니다.
- `agency_agents_delegate` — Hermes의 공개 서브에이전트 라이프사이클을 통해 위임합니다.

각 도구는 이름, 설명, JSON `parameters`를 포함한 Hermes의 완전한 함수 도구 스키마로
등록됩니다. 사용할 수 있는 인수는 다음과 같습니다.

| 도구 | 인수 |
| --- | --- |
| `agency_agents_search` | `query`(필수), 선택 항목 `division`과 `limit` |
| `agency_agents_inspect` | `agent` 또는 `slug`, 선택 항목 `include_body` |
| `agency_agents_load` | `agent` 또는 `slug`, 선택 항목 `task` |
| `agency_agents_delegate` | `agent` 또는 `slug`, `task`(필수) |

일반적인 흐름은 이렇습니다. 역량으로 검색하고, 반환된 `slug`를 받아, 그 전문가를
확인(inspect)하거나 로드(load)하거나 위임(delegate)합니다. Hermes에게 자연어로
요청해도 되며, 도구를 직접 호출할 필요는 없습니다.

## Hermes용 전문가 활용 지침

Hermes 프로젝트에서 Agency 전문가가 필요할 때는 `agency-agents-router`
플러그인/라우터를 사용하도록 명시적으로 요청하고, 현재 단계에 필요한 전문가만
로드하게 하세요. 전체 Agency 로스터를 스킬로 설치하거나 미리 로드하도록 요청하지 마세요.

권장하는 프로젝트 지침은 다음과 같습니다.

```text
Use the agency-agents-router plugin. Search the Agency roster for the right
specialists, then load or delegate only the specific agents needed for each
part of the project. For multi-discipline projects, use multiple selected
specialists across the project, but keep routing lazy: do not preload the
full Agency roster and do not add agency-agents to skills.external_dirs.
```

예시:

```text
For this Data Swami build, use the agency-agents-router plugin to pick
relevant Agency specialists. Search first, then delegate to selected agents
such as frontend, backend, UX, QA, data engineering, and product strategy as
needed. Load/delegate each specialist on demand rather than loading all
Agency agents at startup.
```

## 설치

```bash
./scripts/convert.sh --tool hermes
./scripts/install.sh --tool hermes
```

설치 스크립트는 생성된 플러그인을 다음 위치로 복사합니다.

```text
${HERMES_HOME:-~/.hermes}/plugins/agency-agents-router
```

그다음 Hermes 설정의 `plugins.enabled` 아래에 `agency-agents-router`를 활성화합니다.
`skills.external_dirs`에는 **아무것도 쓰지 않습니다.**

플러그인과 도구 스키마가 로드되도록, 설치 후 Hermes를 재시작하거나 새 세션을 시작하세요.
Hermes가 이 도구들을 문서에 적힌 인수 없이 표시한다면, 최신 Agency Agents 체크아웃에서
플러그인을 다시 생성해 재설치한 뒤 Hermes를 재시작하세요.
