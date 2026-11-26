# OpenClaw 연동

OpenClaw 에이전트는 `SOUL.md`, `AGENTS.md`, `IDENTITY.md` 파일을 담은 워크스페이스
형태로 설치됩니다. 설치 스크립트는 각 워크스페이스를 `~/.openclaw/agency-agents/`로
복사하고, `openclaw` CLI를 사용할 수 있으면 등록까지 진행합니다.

설치 전에 OpenClaw 워크스페이스를 먼저 생성하세요.

```bash
./scripts/convert.sh --tool openclaw
```

## 설치

```bash
./scripts/install.sh --tool openclaw
```

## 에이전트 활성화

설치가 끝나면 OpenClaw 세션에서 `agentId`로 에이전트를 사용할 수 있습니다.

OpenClaw 게이트웨이가 이미 실행 중이라면 설치 후 재시작하세요.

```bash
openclaw gateway restart
```

## 다시 생성하기

```bash
./scripts/convert.sh --tool openclaw
```
