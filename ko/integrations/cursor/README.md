# Cursor 연동

Agency의 전체 에이전트 로스터를 Cursor `.mdc` 룰 파일로 변환합니다. 룰은
**프로젝트 범위**이므로 프로젝트 루트에서 설치해야 합니다.

## 설치

```bash
# 프로젝트 루트에서 실행하세요
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool cursor
```

이 명령은 프로젝트에 `.cursor/rules/<agent-slug>.mdc` 파일들을 생성합니다.

## 룰 활성화

Cursor에서는 프롬프트에 에이전트를 지정하면 됩니다.

```
@frontend-developer Review this React component for performance issues.
```

프론트매터를 수정해 룰을 항상 적용되도록 켤 수도 있습니다.

```yaml
---
description: Expert frontend developer...
globs: "**/*.tsx,**/*.ts"
alwaysApply: true
---
```

## 다시 생성하기

```bash
./scripts/convert.sh --tool cursor
```
