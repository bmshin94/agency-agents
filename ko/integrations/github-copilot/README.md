# GitHub Copilot 연동

Agency는 GitHub Copilot에서 별도 설정 없이 바로 동작합니다. 변환 작업이 필요 없고,
에이전트는 기존 `.md` + YAML 프론트매터 형식을 그대로 사용합니다.

## 설치

```bash
# 모든 에이전트를 GitHub Copilot 에이전트 디렉토리로 복사합니다
./scripts/install.sh --tool copilot

# 특정 카테고리만 직접 복사해도 됩니다
cp engineering/*.md ~/.github/agents/
cp engineering/*.md ~/.copilot/agents/
```

## 에이전트 활성화

GitHub Copilot 세션에서 에이전트를 이름으로 지정하면 됩니다.

```
Activate Frontend Developer and help me build a React component.
```

```
Use the Reality Checker agent to verify this feature is production-ready.
```

## 에이전트 디렉토리

에이전트는 디비전(division) 단위로 정리되어 있습니다. 현재 전체 로스터는
[메인 README](../../README.md)에서 확인하세요.
