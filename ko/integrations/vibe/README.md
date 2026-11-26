# Mistral Vibe 연동

Mistral Vibe는 에이전트마다 두 개의 파일을 사용합니다.
- TOML 설정 파일 (`~/.vibe/agents/<slug>.toml`)
- 마크다운 프롬프트 파일 (`~/.vibe/prompts/<slug>.md`)

생성되는 파일은 `scripts/convert.sh --tool vibe`가 만들어 주며, 이 스크립트는 agency
에이전트마다 TOML 에이전트 설정 하나와 마크다운 프롬프트 파일 하나를 각각
`integrations/vibe/agents/`와 `integrations/vibe/prompts/`에 씁니다.

## 생성

리포지토리 루트에서 실행합니다.

```bash
./scripts/convert.sh --tool vibe
```

## 설치

설치하려는 디렉토리에서 설치 스크립트를 실행하세요.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool vibe
```

이 명령은 생성된 파일들을 다음 위치로 복사합니다.

```text
~/.vibe/agents/<slug>.toml
~/.vibe/prompts/<slug>.md
```

`VIBE_HOME` 환경변수로 설치 위치를 바꿀 수 있습니다.

```bash
VIBE_HOME=~/.config/vibe ./scripts/install.sh --tool vibe
```

## 생성 형식

생성된 에이전트 파일 쌍은 다음 위치에 만들어집니다.

```text
integrations/vibe/agents/<slug>.toml
integrations/vibe/prompts/<slug>.md
```

### 에이전트 TOML 파일

최소한의 Vibe 에이전트 설정입니다.

```toml
agent_type = "agent"
system_prompt_id = "<slug>"
```

에이전트 TOML 파일에 `active_model`을 직접 지정할 수도 있고, Vibe 설정의 기본 모델을
그대로 써도 됩니다.

### 프롬프트 마크다운 파일

프롬프트 파일은 다음을 담고 있습니다.
- 에이전트 이름이 들어간 제목 헤더
- 에이전트 설명
- 원본 에이전트의 마크다운 본문 전체

## 사용법

설치가 끝나면 Mistral Vibe에서 시스템 프롬프트 ID(파일명 슬러그와 동일)로 에이전트를
지정하면 됩니다.

예시:
```text
Use the Code Reviewer agent to analyze this pull request.
```

## 선택 설치

특정 디비전이나 특정 에이전트만 설치할 수 있습니다.

```bash
# Division 1의 에이전트만 설치
./scripts/install.sh --tool vibe --division 1

# code-reviewer 에이전트만 설치
./scripts/install.sh --tool vibe --agent code-reviewer
```

## 다시 생성하기

원본 에이전트를 수정한 뒤에는 다음을 실행하세요.

```bash
./scripts/convert.sh --tool vibe
./scripts/install.sh --tool vibe
```

## 문제 해결

### Mistral Vibe가 감지되지 않음

`vibe`가 PATH에 있는지, 또는 `~/.vibe/`가 이미 존재하는지 확인하세요.

```bash
which vibe
vibe --version
```

### 연동 파일이 생성되지 않음

설치 전에 Vibe 산출물을 먼저 생성하세요.

```bash
./scripts/convert.sh --tool vibe
```
