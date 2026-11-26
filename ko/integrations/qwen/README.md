# Qwen Code 연동

Qwen Code는 `.qwen/agents/`에 있는 프로젝트 범위 `.md` SubAgent 파일을 사용합니다.

생성되는 파일은 `scripts/convert.sh --tool qwen`이 만들어 주며, 이 스크립트는 agency
에이전트마다 SubAgent 마크다운 파일 하나씩을 `integrations/qwen/agents/`에 씁니다.

## 생성

리포지토리 루트에서 실행합니다.

```bash
./scripts/convert.sh --tool qwen
```

## 설치

설치하려는 프로젝트 루트에서 설치 스크립트를 실행하세요.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool qwen
```

이 명령은 생성된 SubAgent 파일들을 다음 위치로 복사합니다.

```text
.qwen/agents/
```

## Qwen Code에서 새로고침

설치 후에는 다음 중 하나를 하세요.

- Qwen Code에서 `/agents manage`를 실행해 에이전트 목록을 새로고침하거나
- 현재 Qwen Code 세션을 재시작합니다

## 참고 사항

- Qwen Code는 홈 디렉토리 범위가 아니라 프로젝트 범위입니다
- 생성된 Qwen 파일은 `name`, `description`, 그리고 선택 항목인 `tools`로 구성된
  최소한의 프론트매터만 사용합니다
- 이 리포지토리의 에이전트를 수정했다면, 다시 설치하기 전에 Qwen 출력물을 재생성하세요
