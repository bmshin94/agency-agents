# OpenCode 연동

> **❌ 이렇게 하지 마세요:**
>
> ```bash
> # 잘못된 방법 — 스키마 검증 오류로 실패합니다
> cp agency-agents/engineering/*.md .opencode/agents/
> ```
>
> **✅ 대신 이렇게 하세요:**
>
> ```bash
> /path/to/agency-agents/scripts/install.sh --tool opencode
> ```
>
> 원본 파일은 색상 이름과 `tools` 필드를 쓰는데, OpenCode는 이를 받아들이지 않습니다.
> 설치 스크립트가 색상을 `#RRGGBB` 16진수로 변환하고 호환되지 않는 필드를
> 자동으로 제거해 줍니다.

OpenCode 에이전트는 `.opencode/agents/`에 저장되는 YAML 프론트매터가 붙은 `.md`
파일입니다. 변환기는 색상 이름을 16진수 코드로 매핑하고 `mode: subagent`를 추가해,
에이전트가 기본 에이전트 선택 목록을 어지럽히지 않고 `@agent-name`으로 필요할 때
호출되도록 만듭니다.

## 설치

```bash
# 프로젝트 루트에서 실행하세요
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool opencode
```

이 명령은 프로젝트 디렉토리에 `.opencode/agents/<slug>.md` 파일들을 생성합니다.

## 에이전트 활성화

OpenCode에서는 `@` 접두사로 서브에이전트를 호출합니다.

```
@frontend-developer help build this component.
```

```
@reality-checker review this PR.
```

OpenCode UI의 에이전트 선택기에서 골라도 됩니다.

## 에이전트 형식

생성된 각 에이전트 파일은 다음을 담고 있습니다.

```yaml
---
name: Frontend Developer
description: Expert frontend developer specializing in modern web technologies...
mode: subagent
color: "#00FFFF"
---
```

- **mode: subagent** — 필요할 때 호출할 수 있고, Tab으로 순환하는 기본 목록에는 표시되지 않습니다
- **color** — 16진수 코드 (원본 파일의 색상 이름은 자동으로 변환됩니다)

## 프로젝트 범위 vs 전역 범위

`.opencode/agents/`에 있는 에이전트는 **프로젝트 범위**입니다. 모든 프로젝트에서 전역으로
쓰고 싶다면, 먼저 에이전트 파일을 생성한 다음 `--path`를 지정해 설치하세요.

```bash
./scripts/convert.sh --tool opencode
./scripts/install.sh --tool opencode --path ~/.config/opencode/agents
```

## 다시 생성하기

```bash
./scripts/convert.sh --tool opencode
```
