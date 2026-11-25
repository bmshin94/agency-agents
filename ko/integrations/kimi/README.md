# Kimi Code CLI 연동

Agency의 모든 에이전트를 Kimi Code CLI 에이전트 명세로 변환합니다. 각 에이전트는
`agent.yaml`(에이전트 명세)과 `system.md`(시스템 프롬프트)를 담은 디렉토리가 됩니다.

## 설치

### 사전 준비

- [Kimi Code CLI](https://github.com/MoonshotAI/kimi-cli) 설치

### 설치하기

```bash
# 연동 파일 생성 (새로 클론한 경우 필수)
./scripts/convert.sh --tool kimi

# 에이전트 설치
./scripts/install.sh --tool kimi
```

이 명령은 에이전트를 `~/.config/kimi/agents/`로 복사합니다.

## 사용법

### 에이전트 활성화

`--agent-file` 플래그로 특정 에이전트를 로드합니다.

```bash
kimi --agent-file ~/.config/kimi/agents/frontend-developer/agent.yaml
```

### 프로젝트에서 사용하기

```bash
cd /your/project
kimi --agent-file ~/.config/kimi/agents/frontend-developer/agent.yaml \
     --work-dir /your/project \
     "Review this React component for performance issues"
```

### 설치된 에이전트 목록 보기

```bash
ls ~/.config/kimi/agents/
```

## 에이전트 구조

각 에이전트 디렉토리는 다음을 담고 있습니다.

```
~/.config/kimi/agents/frontend-developer/
├── agent.yaml    # 에이전트 명세 (도구, 서브에이전트)
└── system.md     # 성격과 지침이 담긴 시스템 프롬프트
```

### agent.yaml 형식

```yaml
version: 1
agent:
  name: frontend-developer
  extend: default  # Kimi 기본 내장 에이전트를 상속합니다
  system_prompt_path: ./system.md
  tools:
    - "kimi_cli.tools.shell:Shell"
    - "kimi_cli.tools.file:ReadFile"
    # ... 기본 도구 전체
```

## 다시 생성하기

원본 에이전트를 수정한 뒤에는 다음을 실행하세요.

```bash
./scripts/convert.sh --tool kimi
./scripts/install.sh --tool kimi
```

## 문제 해결

### 에이전트 파일을 찾을 수 없음

`install.sh` 전에 `convert.sh`를 실행했는지 확인하세요.

```bash
./scripts/convert.sh --tool kimi
```

### Kimi CLI가 감지되지 않음

`kimi`가 PATH에 있는지 확인하세요.

```bash
which kimi
kimi --version
```

### 잘못된 YAML

생성된 파일을 검증해 보세요.

```bash
python3 -c "import yaml; yaml.safe_load(open('integrations/kimi/frontend-developer/agent.yaml'))"
```
