# Windsurf 연동

Agency의 전체 에이전트 로스터가 하나의 `.windsurfrules` 파일로 통합됩니다. 룰은
**프로젝트 범위**이므로 프로젝트 루트에서 설치해야 합니다.

## 설치

```bash
# 프로젝트 루트에서 실행하세요
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool windsurf
```

## 에이전트 활성화

Windsurf에서는 프롬프트에 에이전트를 이름으로 지정하면 됩니다.

```
Use the Frontend Developer agent to build this component.
```

## 다시 생성하기

```bash
./scripts/convert.sh --tool windsurf
```
