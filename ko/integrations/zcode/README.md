# ZCode 연동

[ZCode](https://z.ai)는 Z.ai의 GLM 기반 코딩 에이전트 하네스입니다. 각 agency
에이전트는 `name`과 `description` 프론트매터를 가진 독립 마크다운 에이전트 파일로
변환되며, ZCode가 자신의 에이전트 디렉토리에서 이를 찾아냅니다.

생성되는 파일은 `scripts/convert.sh --tool zcode`가 만들어 주며, 이 스크립트는 agency
에이전트마다 마크다운 파일 하나씩을 `integrations/zcode/agents/`에 씁니다. 생성된
파일은 커밋되지 않으므로(`.gitignore` 참고) 로컬에서 직접 재생성하세요.

## 생성

리포지토리 루트에서 실행합니다.

```bash
./scripts/convert.sh --tool zcode
```

## 설치

설치하려는 디렉토리에서 설치 스크립트를 실행하세요.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool zcode
```

에이전트는 ZCode가 서브에이전트를 읽어 들이는 디렉토리인
`~/.zcode/agents/<slug>.md`(사용자 범위)에 설치됩니다. 일부만 설치하려면
`--division` / `--agent`를 사용하고, 설치 위치를 바꾸려면 `ZCODE_AGENTS_DIR`을 설정하세요.
