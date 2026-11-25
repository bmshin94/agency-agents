# Gemini CLI 연동

Agency의 모든 에이전트를 Gemini CLI 서브에이전트로 패키징합니다. 이 에이전트들은
`~/.gemini/agents/`에 설치됩니다.

## 설치

```bash
# 먼저 Gemini CLI 에이전트 파일을 생성합니다
./scripts/convert.sh --tool gemini-cli

# 그다음 ~/.gemini/agents/ 로 설치합니다
./scripts/install.sh --tool gemini-cli
```

## 에이전트 사용

Gemini CLI에서는 프롬프트에 에이전트를 이름으로 지정하면 됩니다.

```
Use the frontend-developer agent to help me build this UI.
```

사용 중인 Gemini CLI 버전이 지원한다면 에이전트를 직접 호출할 수도 있습니다.

```bash
gemini --agent frontend-developer "How should I structure this React component?"
```

## 구조

```
~/.gemini/agents/
  frontend-developer.md
  backend-architect.md
  reality-checker.md
  ...
```

## 다시 생성하기

```bash
./scripts/convert.sh --tool gemini-cli
```
