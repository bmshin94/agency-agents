# 🔌 연동

이 디렉토리에는 The Agency의 연동 파일과, 지원되는 에이전틱 코딩 툴용으로 변환된
포맷들이 들어 있습니다.

## 지원 툴

- **[Claude Code](#claude-code)** — `.md` 에이전트, 리포지토리를 그대로 사용
- **[GitHub Copilot](#github-copilot)** — `.md` 에이전트, 리포지토리를 그대로 사용
- **[Antigravity](#antigravity)** — `antigravity/`에 에이전트별 `SKILL.md`
- **[Gemini CLI](#gemini-cli)** — `gemini-cli/agents/`의 `.md` 에이전트 파일
- **[OpenCode](#opencode)** — `opencode/`의 `.md` 에이전트 파일
- **[OpenClaw](#openclaw)** — `SOUL.md` + `AGENTS.md` + `IDENTITY.md` 워크스페이스
- **[Cursor](#cursor)** — `cursor/`의 `.mdc` 룰 파일
- **[Aider](#aider)** — `aider/`의 `CONVENTIONS.md`
- **[Windsurf](#windsurf)** — `windsurf/`의 `.windsurfrules`
- **[Kimi Code](#kimi-code)** — `kimi/`의 YAML 에이전트 명세
- **[Qwen Code](#qwen-code)** — `.qwen/agents/`의 프로젝트 범위 `.md` SubAgent
- **[Codex](#codex)** — `codex/`의 `.toml` 커스텀 에이전트
- **[Mistral Vibe](vibe/README.md)** — `vibe/`에 생성되는 `.toml` 에이전트 + 프롬프트 파일
- **Osaurus** -- `osaurus/`에 생성되는 `SKILL.md` 스킬
- **[Hermes](hermes/README.md)** -- `hermes/`에 생성되는 지연 라우터 플러그인

## 빠른 설치

```bash
# 감지된 모든 툴에 자동으로 설치
./scripts/install.sh

# 홈 디렉토리 범위 툴을 개별 설치
./scripts/install.sh --tool antigravity
./scripts/install.sh --tool copilot
./scripts/install.sh --tool openclaw
./scripts/install.sh --tool claude-code
./scripts/install.sh --tool codex
./scripts/install.sh --tool osaurus
./scripts/install.sh --tool hermes

# Gemini CLI는 새로 클론한 경우 생성된 연동 파일이 필요합니다
./scripts/convert.sh --tool gemini-cli
./scripts/install.sh --tool gemini-cli

# Qwen Code도 새로 클론한 경우 생성된 SubAgent 파일이 필요합니다
./scripts/convert.sh --tool qwen
./scripts/install.sh --tool qwen
```

OpenClaw를 설치하는데 게이트웨이가 이미 실행 중이라면, 설치 후 재시작하세요.

```bash
openclaw gateway restart
```

OpenCode, Cursor, Aider, Windsurf, Qwen Code처럼 프로젝트 범위인 툴은
아래 툴별 섹션에서 설명한 대로 설치하려는 프로젝트 루트에서 설치 스크립트를
실행하세요.

## 연동 파일 다시 생성하기

에이전트를 추가하거나 수정했다면 모든 연동 파일을 다시 생성하세요.

```bash
./scripts/convert.sh
```

---

## Claude Code

The Agency는 원래 Claude Code를 위해 설계되었습니다. 에이전트는 변환 없이 네이티브로
동작합니다.

```bash
cp -r <category>/*.md ~/.claude/agents/
# 또는 한 번에 전부 설치:
./scripts/install.sh --tool claude-code
```

자세한 내용은 [claude-code/README.md](claude-code/README.md)를 참고하세요.

---

## GitHub Copilot

The Agency는 GitHub Copilot에서도 네이티브로 동작합니다. 에이전트를 변환 없이
`~/.github/agents/`와 `~/.copilot/agents/`로 바로 복사할 수 있습니다.

```bash
./scripts/install.sh --tool copilot
```

자세한 내용은 [github-copilot/README.md](github-copilot/README.md)를 참고하세요.

---

## Antigravity

스킬은 `~/.gemini/config/skills/`에 설치됩니다. 이름 충돌을 피하기 위해 각 에이전트는
`agency-` 접두사가 붙은 별도 스킬이 됩니다.

```bash
./scripts/install.sh --tool antigravity
```

자세한 내용은 [antigravity/README.md](antigravity/README.md)를 참고하세요.

---

## Gemini CLI

에이전트는 Gemini CLI 서브에이전트로 패키징됩니다.
서브에이전트는 `~/.gemini/agents/`에 설치됩니다.
에이전트 파일은 생성되는 산출물이므로, 새로 클론한 경우 설치 전에
`./scripts/convert.sh --tool gemini-cli`를 실행하세요.

```bash
./scripts/convert.sh --tool gemini-cli
./scripts/install.sh --tool gemini-cli
```

자세한 내용은 [gemini-cli/README.md](gemini-cli/README.md)를 참고하세요.

---

## OpenCode

각 에이전트는 `.opencode/agents/`에 들어가는 프로젝트 범위 `.md` 파일이 됩니다.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool opencode
```

자세한 내용은 [opencode/README.md](opencode/README.md)를 참고하세요.

---

## OpenClaw

각 에이전트는 `SOUL.md`, `AGENTS.md`, `IDENTITY.md`를 담은 OpenClaw 워크스페이스가
됩니다.

설치 전에 OpenClaw 워크스페이스를 먼저 생성하세요.

```bash
./scripts/convert.sh --tool openclaw
```

그다음 설치합니다.

```bash
./scripts/install.sh --tool openclaw
```

자세한 내용은 [openclaw/README.md](openclaw/README.md)를 참고하세요.

---

## Cursor

각 에이전트는 `.mdc` 룰 파일이 됩니다. 룰은 프로젝트 범위이므로 프로젝트 루트에서
설치 스크립트를 실행하세요.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool cursor
```

자세한 내용은 [cursor/README.md](cursor/README.md)를 참고하세요.

---

## Aider

모든 에이전트가 하나의 `CONVENTIONS.md` 파일로 통합되며, Aider는 이 파일이 프로젝트
루트에 있으면 자동으로 읽어 들입니다.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool aider
```

자세한 내용은 [aider/README.md](aider/README.md)를 참고하세요.

---

## Windsurf

모든 에이전트가 프로젝트 루트용 `.windsurfrules` 파일 하나로 통합됩니다.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool windsurf
```

자세한 내용은 [windsurf/README.md](windsurf/README.md)를 참고하세요.

---

## Kimi Code

각 에이전트는 Kimi Code CLI 에이전트 명세(YAML 형식 + 별도 시스템 프롬프트 파일)로
변환됩니다. 에이전트는 `~/.config/kimi/agents/`에 설치됩니다.

Kimi 에이전트 파일은 원본 마크다운에서 생성되므로, 새로 클론한 경우 설치 전에
`./scripts/convert.sh --tool kimi`를 실행하세요.

```bash
./scripts/convert.sh --tool kimi
./scripts/install.sh --tool kimi
```

### 사용법

설치가 끝나면 `--agent-file` 플래그로 에이전트를 사용합니다.

```bash
kimi --agent-file ~/.config/kimi/agents/frontend-developer/agent.yaml
```

특정 프로젝트에서 사용할 때는 이렇게 합니다.

```bash
cd /your/project
kimi --agent-file ~/.config/kimi/agents/frontend-developer/agent.yaml \
     --work-dir /your/project
```

자세한 내용은 [kimi/README.md](kimi/README.md)를 참고하세요.

---

## Qwen Code

각 에이전트는 `.qwen/agents/`에 들어가는 프로젝트 범위 `.md` SubAgent 파일이 됩니다.

새로 클론한 경우, 먼저 Qwen 파일을 생성하세요.

```bash
./scripts/convert.sh --tool qwen
```

그다음 프로젝트 루트에서 설치합니다.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool qwen
```

자세한 내용은 [qwen/README.md](qwen/README.md)를 참고하세요.

---

## Codex

각 에이전트는 독립 Codex 커스텀 에이전트 TOML 파일로 변환되어 `~/.codex/agents/`에
설치됩니다.

Codex는 원본 마크다운을 직접 쓰는 대신 생성된 TOML 파일을 사용하므로, 새로 클론한
경우 설치 전에 변환기를 실행하세요.

```bash
./scripts/convert.sh --tool codex
./scripts/install.sh --tool codex
```

자세한 내용은 [codex/README.md](codex/README.md)를 참고하세요.
