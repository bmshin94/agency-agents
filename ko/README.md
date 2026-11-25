# 🎭 The Agency: 당신의 워크플로를 바꿀 AI 전문가들

> 📘 이 문서는 [영문 원본 README](../README.md)의 한국어 번역판입니다.

> **완전한 AI 에이전시를 손끝에서** - 프론트엔드 마법사부터 레딧 커뮤니티 닌자까지, 위미시 인젝터부터 현실 점검 담당까지. 각 에이전트는 개성과 프로세스, 검증된 산출물을 갖춘 전문가입니다.

[![GitHub stars](https://img.shields.io/github/stars/msitarzewski/agency-agents?style=social)](https://github.com/msitarzewski/agency-agents)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://makeapullrequest.com)
[![Sponsor](https://img.shields.io/badge/Sponsor-%E2%9D%A4-pink?logo=github)](https://github.com/sponsors/msitarzewski)
[![Download the app](https://img.shields.io/github/v/release/msitarzewski/agency-agents-app?label=Download%20app&color=2563eb)](https://github.com/msitarzewski/agency-agents-app/releases/latest)

> ### 🆕 이제 앱이 있습니다
>
> **[Agency Agents](https://agencyagents.app)**는 **macOS, Linux, Windows**용 네이티브 앱입니다. 전체 로스터를 둘러보고 클릭 한 번으로 Claude Code, Cursor, Codex, Gemini, Osaurus 등에 설치해 줍니다. 클론도, 스크립트도 필요 없고 자동 업데이트까지 됩니다.
>
> **→ [최신 릴리스 다운로드](https://github.com/msitarzewski/agency-agents-app/releases/latest) · [agencyagents.app](https://agencyagents.app)**

---

## 🚀 이게 뭔가요?

레딧 스레드에서 시작해 수개월에 걸쳐 다듬어 온 **The Agency**는 정성껏 만든 AI 에이전트 페르소나를 계속 늘려 가는 모음집입니다. 각 에이전트는 이런 특징을 갖습니다.

- **🎯 전문화**: 자기 도메인에 대한 깊은 전문성 (일반적인 프롬프트 템플릿이 아닙니다)
- **🧠 개성 중심**: 고유한 목소리, 커뮤니케이션 스타일, 접근 방식
- **📋 산출물 중심**: 실제 코드, 프로세스, 측정 가능한 성과
- **✅ 프로덕션 준비 완료**: 실전에서 검증된 워크플로와 성공 지표

**이렇게 생각하세요**: 드림팀을 꾸리는 것. 단, 잠들지도 않고, 불평하지도 않고, 늘 결과를 내놓는 AI 전문가들로요.

---

## ⚡ 빠른 시작

### 옵션 1: 앱 설치 (추천)

가장 빠른 길입니다. 클론도, 터미널도 필요 없습니다. [**Agency Agents**](https://agencyagents.app)는 네이티브 데스크톱 앱(macOS · Linux · Windows)으로, 전체 로스터를 둘러보고 Claude Code, Cursor, Codex, Gemini CLI, OpenCode, Qwen, Osaurus에 에이전트를 설치해 준 다음 계속 최신 상태로 유지해 줍니다.

**[⬇ 최신 릴리스 다운로드](https://github.com/msitarzewski/agency-agents-app/releases/latest)** — 또는 Mac에서는:

```bash
brew install --cask msitarzewski/agency-agents/agency-agents
```

커맨드라인이 더 편하신가요? 아래 스크립트 기반 옵션도 같은 에이전트를 설치합니다.

### 옵션 2: Claude Code와 함께 쓰기

```bash
# 모든 에이전트를 Claude Code 디렉토리에 설치
./scripts/install.sh --tool claude-code

# 또는 하나의 디비전만 원하면 해당 카테고리를 직접 복사
cp engineering/*.md ~/.claude/agents/

# 그다음 Claude Code 세션에서 원하는 에이전트를 활성화하세요:
# "Hey Claude, activate Frontend Developer mode and help me build a React component"
```

### 옵션 3: 참고 자료로 쓰기

각 에이전트 파일에는 다음이 담겨 있습니다.
- 정체성과 성격 특성
- 핵심 미션과 워크플로
- 코드 예시가 포함된 기술 산출물
- 성공 지표와 커뮤니케이션 스타일

아래 에이전트들을 둘러보고 필요한 것을 복사하거나 변형해서 쓰세요!

### 옵션 4: 다른 도구와 함께 쓰기 (GitHub Copilot, Antigravity, Gemini CLI, OpenCode, OpenClaw, Cursor, Aider, Windsurf, Kimi Code, Codex, Osaurus, Hermes, Mistral Vibe)

```bash
# 1단계 -- 지원되는 모든 도구용 통합 파일 생성
./scripts/convert.sh

# 2단계 -- 대화형으로 설치 (설치된 도구를 자동 감지)
./scripts/install.sh

# 또는 특정 도구를 직접 지정
./scripts/install.sh --tool antigravity
./scripts/install.sh --tool gemini-cli
./scripts/install.sh --tool opencode
./scripts/install.sh --tool copilot
./scripts/install.sh --tool openclaw
./scripts/install.sh --tool cursor
./scripts/install.sh --tool aider
./scripts/install.sh --tool windsurf
./scripts/install.sh --tool kimi
./scripts/install.sh --tool codex
./scripts/install.sh --tool osaurus
./scripts/install.sh --tool hermes
./scripts/install.sh --tool vibe
```

**필요한 팀만 설치하세요** (모두가 모든 디비전을 원하는 건 아니니까요):

```bash
./scripts/install.sh                                    # 대화형 위저드: 도구 + 팀 선택
./scripts/install.sh --tool claude-code --division engineering,security
./scripts/install.sh --tool cursor --agent frontend-developer,ui-designer
./scripts/install.sh --list teams                       # 모든 팀 + 에이전트 수 보기
./scripts/install.sh --tool opencode --division engineering --dry-run
```

> **OpenCode 참고:** OpenCode 런타임은 현재 약 119개의 에이전트만 등록하고 나머지는 조용히 버립니다([업스트림 버그](https://github.com/anomalyco/opencode/issues/27988)). `--division`으로 일부만 설치하면 이 한계 아래로 유지됩니다. 선택한 범위가 한계를 넘으면 설치 스크립트가 경고해 줍니다.

자세한 내용은 아래 [멀티 도구 통합](#-멀티-도구-통합) 섹션을 참고하세요.

---
