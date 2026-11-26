# Antigravity 연동

Agency의 전체 에이전트 로스터를 Antigravity 스킬로 설치합니다. 기존 스킬과 충돌하지 않도록
각 에이전트 이름 앞에 `agency-` 접두사가 붙습니다.

## 설치

```bash
./scripts/install.sh --tool antigravity
```

이 명령은 `integrations/antigravity/`의 파일을
`~/.gemini/config/skills/`(전역)로 복사합니다. 프로젝트 범위 스킬이 필요하다면 Antigravity는
`<project>/.agents/skills/`도 함께 읽습니다.

## 스킬 활성화

Antigravity에서는 슬러그로 에이전트를 활성화합니다.

```
Use the agency-frontend-developer skill to review this component.
```

사용 가능한 슬러그는 `agency-<agent-name>` 패턴을 따릅니다. 예를 들면 다음과 같습니다.
- `agency-frontend-developer`
- `agency-backend-architect`
- `agency-reality-checker`
- `agency-growth-hacker`

## 다시 생성하기

에이전트를 수정한 뒤에는 스킬 파일을 다시 생성하세요.

```bash
./scripts/convert.sh --tool antigravity
```

## 파일 형식

각 스킬은 Antigravity 호환 프론트매터를 가진 `SKILL.md` 파일입니다.

```yaml
---
name: agency-frontend-developer
description: Expert frontend developer specializing in...
risk: low
source: community
date_added: '2026-03-08'
---
```
