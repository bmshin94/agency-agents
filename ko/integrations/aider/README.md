# Aider 연동

Agency의 전체 에이전트 로스터가 하나의 `CONVENTIONS.md` 파일로 통합됩니다.
Aider는 이 파일이 프로젝트 루트에 있으면 자동으로 읽어 들입니다.

## 설치

```bash
# 프로젝트 루트에서 실행하세요
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool aider
```

## 에이전트 활성화

Aider 세션에서 에이전트를 이름으로 지정하면 됩니다.

```
Use the Frontend Developer agent to refactor this component.
```

```
Apply the Reality Checker agent to verify this is production-ready.
```

## 직접 사용하기

conventions 파일을 직접 전달할 수도 있습니다.

```bash
aider --read CONVENTIONS.md
```

## 다시 생성하기

```bash
./scripts/convert.sh --tool aider
```
