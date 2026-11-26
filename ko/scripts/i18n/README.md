# 🇨🇳 중국어(zh-CN) 현지화

YAML 프론트매터의 에이전트 `name`과 `description` 필드를 간체 중국어로 현지화합니다. 이렇게 하면 중국어 사용자가 Copilot Chat의 에이전트 선택기에서 에이전트 이름을 읽을 수 있습니다.

## 파일

| 파일 | 설명 |
|------|-------------|
| `agent-names-zh.json` | 영문 에이전트 이름 → 중국어 번역 매핑(130개 이상) |
| `localize-agents-zh.ps1` | JSON을 읽어 설치된 에이전트 파일을 수정하는 PowerShell 스크립트 |

## 사용법

`install.sh --tool copilot`으로 에이전트를 설치한 뒤에 실행합니다.

```powershell
# 에이전트 이름을 중국어로 현지화
powershell -ExecutionPolicy Bypass -File scripts/i18n/localize-agents-zh.ps1
```

기본적으로 스크립트가 처리하는 경로는 다음과 같습니다.
- `%USERPROFILE%\.github\agents\`
- `%USERPROFILE%\.copilot\agents\`

필요하면 다른 경로를 직접 전달하세요.

```powershell
powershell -File scripts/i18n/localize-agents-zh.ps1 -TargetDirs @("C:\custom\path\agents")
```

## 동작 방식

1. 번역 맵으로 사용할 `agent-names-zh.json`(UTF-8 인코딩)을 읽습니다
2. 대상 디렉터리의 각 `.md` 파일에 대해:
   - YAML 프론트매터에서 `name:` 필드를 추출합니다
   - 해당하는 중국어 번역을 찾습니다
   - `name:`과 `description:` 필드를 교체합니다
   - UTF-8로 다시 씁니다

## 결과

변경 전:
```yaml
---
name: Security Engineer
description: Threat modeling, secure code review, security architecture
---
```

변경 후:
```yaml
---
name: 安全工程师
description: 威胁建模、安全代码审查与应用安全架构专家
---
```

## 참고 사항

- **설치된 사본**(`~/.github/agents/`)만 수정하며, 원본 소스 파일은 건드리지 않습니다
- `install.sh`를 업데이트할 때마다 다시 실행하세요(영문 원본으로 덮어쓰기 때문입니다)
- 번역의 단일 기준(single source of truth)은 JSON 파일입니다 — 새 에이전트는 여기에 추가하세요
- 스크립트는 순수 ASCII로 작성되어 있습니다(PowerShell 인코딩 문제를 피하기 위함). 모든 중국어 텍스트는 JSON에 들어 있습니다
