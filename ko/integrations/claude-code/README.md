# Claude Code 연동

Agency는 Claude Code를 위해 만들어졌습니다. 변환 작업이 전혀 필요 없고, 기존 `.md` +
YAML 프론트매터 형식 그대로 네이티브로 동작합니다.

## 설치

```bash
# 모든 에이전트를 Claude Code 에이전트 디렉토리로 복사합니다
./scripts/install.sh --tool claude-code

# 특정 카테고리만 직접 복사해도 됩니다
cp engineering/*.md ~/.claude/agents/
```

## 에이전트 활성화

Claude Code 세션에서 에이전트를 이름으로 지정하면 됩니다.

```
Activate Frontend Developer and help me build a React component.
```

```
Use the Reality Checker agent to verify this feature is production-ready.
```

## 에이전트 디렉토리

에이전트는 디비전(division) 단위로 정리되어 있습니다. 전체 로스터는
[메인 README](../../README.md)에서 확인하세요.
