# Codex 연동

Agency의 모든 에이전트를 Codex 커스텀 에이전트 TOML 파일로 변환합니다. 원본 에이전트
하나가 Codex에서 필수로 요구하는 최소 필드인 `name`, `description`,
`developer_instructions`만 담은 독립 `.toml` 파일 하나가 됩니다.

## 설치

### 사전 준비

- [Codex](https://developers.openai.com/codex/overview) 설치

### 변환 및 설치

```bash
# 연동 파일 생성 (새로 클론한 경우 필수)
./scripts/convert.sh --tool codex

# 에이전트 설치
./scripts/install.sh --tool codex
```

이 명령은 생성된 에이전트 파일을 `~/.codex/agents/`로 복사합니다.

## 생성 형식

생성된 파일은 다음 위치에 만들어집니다.

```text
integrations/codex/agents/<slug>.toml
```

매핑은 의도적으로 최소한으로 유지했습니다.

- `name`은 원본 프론트매터에서 그대로 복사합니다
- `description`도 원본 프론트매터에서 그대로 복사합니다
- `developer_instructions`에는 마크다운 본문 전체가 변경 없이 들어갑니다

`color`, `emoji`, `vibe`처럼 원본에만 있는 메타데이터와 그 외 지원되지 않는 프론트매터
필드는 제외됩니다.

## 사용법

설치가 끝나면 Codex에서 커스텀 에이전트를 이름으로 지정하면 됩니다.

```text
Use the Frontend Developer agent to review this component.
```

Codex는 TOML 파일 안의 `name` 필드를 기준으로 삼기 때문에, 생성된 파일명 슬러그는
파일시스템 안전성을 위한 것일 뿐입니다.

## 다시 생성하기

원본 에이전트를 수정한 뒤에는 다음을 실행하세요.

```bash
./scripts/convert.sh --tool codex
./scripts/install.sh --tool codex
```

## 문제 해결

### Codex 연동 파일을 찾을 수 없음

설치 전에 Codex 산출물을 먼저 생성하세요.

```bash
./scripts/convert.sh --tool codex
```

### Codex가 감지되지 않음

`codex`가 PATH에 있는지, 또는 `~/.codex/`가 이미 존재하는지 확인하세요.

```bash
which codex
codex --help
```
