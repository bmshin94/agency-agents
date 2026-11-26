# 🇰🇷 ko/ 한국어 번역 작업 인계 문서

이 문서는 `ko/` 한국어 미러 트리의 **번역 규칙과 진행 상황**을 담은 인계 문서입니다.
새 세션에서 번역을 이어갈 때 이 파일을 먼저 읽으면 동일한 기준으로 작업할 수 있습니다.

- 원본 리포지토리: https://github.com/msitarzewski/agency-agents
- 이 포크: https://github.com/bmshin94/agency-agents
- 작업 브랜치: `claude/magical-noether-ygw4xj`

---

## 1. 구조 — `ko/` 미러 트리

원본 경로 앞에 `ko/`만 붙인 **동일 구조 미러**입니다.

```
engineering/engineering-frontend-developer.md
  → ko/engineering/engineering-frontend-developer.md
strategy/playbooks/phase-0-discovery.md
  → ko/strategy/playbooks/phase-0-discovery.md
README.md
  → ko/README.md
```

**원본 파일은 수정하지 않습니다.** `ko/` 밖의 파일도 생성·수정하지 않습니다.

### 미러 구조를 택한 이유
상대 링크가 그대로 맞아떨어져 링크 재작성이 필요 없습니다.
`ko/README.md`의 `engineering/x.md`는 `ko/engineering/x.md`로 해석됩니다.

### CI 주의사항 ⚠️
`scripts/check-divisions.sh`는 루트의 새 디렉토리를 전부 "미등록 부서"로 간주합니다.
그래서 `NON_DIVISION_DIRS`에 `ko`를 추가해 두었습니다.

```bash
NON_DIVISION_DIRS=(examples scripts integrations strategy ko)
```

`convert.sh`와 `lint-agents.sh`는 `ko/`를 스캔하지 않으므로,
**영문 원본이 계속 유일한 설치 소스**로 남습니다.

---

## 2. 번역 규칙

### 2.1 YAML 프론트매터
- 키 이름은 그대로 (`name`, `description`, `tools`, `color`, `emoji`, `vibe`)
- **`name`은 영문 그대로 유지** — 에이전트 호출 핸들이자 런북·앱이 참조하는 슬러그입니다.
  번역하면 에이전트가 호출되지 않습니다.
- `description`, `vibe`는 자연스러운 한국어로 번역
- `tools`, `color`, `emoji`는 그대로
- 원본에 없는 키를 추가하지 않습니다

### 2.2 마크다운 구조
- 헤딩 레벨, 목록 기호, 표 구조, 이모지, 수평선, 인용블록, 들여쓰기를 **1:1로** 유지
- 표 헤더는 번역: `Agent`→`에이전트`, `Specialty`→`전문 분야`, `When to Use`→`사용 시점`
- 내용을 추가·삭제·요약하지 않습니다. 번역자 주석을 달지 않습니다
- 배지 이미지, `<div align="center">`, `<details>/<summary>` 같은 HTML은 원문 유지
- 설치 스크립트의 아스키 아트 TUI 박스는 실제 터미널 출력이므로 원문 유지

### 2.3 링크
- **상대 경로 링크는 바이트 단위로 그대로 둡니다** (미러 구조라 그대로 맞음)
- 단, **미러에 없는 대상**만 `../`를 붙입니다:
  `LICENSE`, `divisions.json`, `tools.json`, `scripts/*.sh`, `.github/*`,
  `CONTRIBUTING_zh-CN.md`, `AGENCY-AGENTS-ANALYSIS-KO.md`, `strategy/runbooks.json`
- 외부 URL은 그대로
- 앵커 링크는 번역된 헤딩에 맞게 수정. 원본에서 이미 깨진 앵커는 원본 그대로 유지

### 2.4 코드 블록
**코드·명령어·식별자는 원문 그대로.** 번역 금지 대상:
파일 경로, 슬러그, CLI 플래그, 환경변수명, JSON/YAML 키, 함수·클래스·변수명,
패키지명, SQL, 셸 명령, 네트워크 장비 설정 명령, 엔진 API, 프론트매터 키

**코드 블록 안의 주석과 사용자 노출 문자열만** 한국어로 번역합니다.
언어 태그(` ```bash `, ` ```tsx `)는 그대로.

### 2.5 문체와 어휘
- **문서·가이드**: 정중한 설명체 (`~합니다`, `~하세요`)
- **에이전트 페르소나 본문**: 원본이 2인칭 지시문이므로 `당신은 ~입니다`, `~해야 합니다`
- **억지 번역 금지.** 한국 개발자가 실제로 영어로 쓰는 용어는 영어 그대로:
  React, Vue, TypeScript, Core Web Vitals, WCAG, SLO, SLI, RAG, MCP, CI/CD, API, LLM,
  ETL, OAuth, SAML, CRDT, Kubernetes, Docker, 리팩터링, 마이그레이션, 캐싱
- 처음 등장하는 낯선 약어는 `지연 시간(latency)` 처럼 괄호 병기 1회
- 번역투 금지. `~되어집니다`, `~에 대하여`, `~를 수행합니다` 같은 어색한 표현 대신
  자연스러운 한국어로. 수동태는 능동태로 풀어 씁니다
- 어미를 문서 전체에서 일관되게 유지합니다

### 2.6 도메인별 주의사항

| 영역 | 규칙 |
|---|---|
| **규제·제도명** | 미국/EU/중국 제도 고유명사는 **원문 유지 + 괄호 설명 1회**. 한국 제도명으로 치환하면 오역입니다 — `HIPAA`, `GDPR`, `CCPA`, `IOLTA`, `TRID`, `FedRAMP`, `NIST 800-53`, `SOC 2`, `ICD-10`, `CPT`, `HCPCS`, `Eurocode`, `ACI`, `AISC`, `portage salarial` |
| **이미지 생성 프롬프트** | Midjourney/DALL-E에 실제 입력하는 영문 프롬프트는 **영문 그대로**. 번역하면 도구에서 작동하지 않습니다 |
| **판정 라벨** | `NEEDS-WORK`, `PASS`, `FAIL` 등은 파이프라인에서 문자열로 쓰이므로 영문 유지 |
| **영업·마케팅 카피** | 콜드 이메일, 전화 스크립트, 광고 카피, 고객 응대 문장은 직역하지 말고 **한국어로 자연스럽게 재작성**. 단 원본의 설득 구조와 기법은 유지 |
| **중국 플랫폼** | 통용 표기 + 원문 1회 병기: 샤오홍슈(小红书), 더우인(抖音), 빌리빌리(B站), 위챗(WeChat), 콰이쇼우(快手), 웨이보(微博), 즈후(知乎), 타오바오(淘宝) |
| **게임 엔진 API** | 한국 게임 개발자도 영문으로 쓰므로 원문 유지: `ScriptableObject`, `MonoBehaviour`, DOTS/ECS, Blueprint, GAS, Nanite, Niagara, GDScript, `MultiplayerAPI`, Luau, `DataStore` |
| **영업 방법론** | 영문 유지: SPIN, Gap Selling, Sandler, MEDDPICC, BANT, Challenger, QBR |
| **보안 탐지 룰** | 정규식·SIEM 룰·쿼리는 그대로 동작해야 하므로 코드 변경 금지 |
| **수치** | 숫자, 단위, 지표, 임계값은 원본 그대로 |

### 2.7 품질 확인
작업 후 원본과 구조를 대조합니다.

```bash
f=engineering/engineering-frontend-developer.md
printf "줄수   %s / %s\n"   "$(wc -l < $f)"            "$(wc -l < ko/$f)"
printf "헤딩   %s / %s\n"   "$(grep -c '^#\+ ' $f)"    "$(grep -c '^#\+ ' ko/$f)"
printf "표행   %s / %s\n"   "$(grep -c '^|' $f)"       "$(grep -c '^|' ko/$f)"
printf "코드   %s / %s\n"   "$(grep -c '^```' $f)"     "$(grep -c '^```' ko/$f)"
```

줄 수가 정확히 같을 필요는 없지만(한국어 문장 길이 차이), **원본의 60% 미만이면 내용 누락**이므로
다시 작업합니다.

---

## 3. 번역 제외 파일

| 파일 | 이유 |
|---|---|
| `AGENCY-AGENTS-ANALYSIS-KO.md` | 이미 한국어 |
| `CONTRIBUTING_zh-CN.md` | 중국어 번역판 |
| `.github/PULL_REQUEST_TEMPLATE.md` | GitHub 인프라 — `ko/`에 두면 GitHub이 쓰지 않음 |

**번역 대상 총 324개 파일 / 84,354줄**

---

## 4. 이어서 작업하는 방법

### 남은 파일 목록 뽑기
```bash
cd /home/user/agency-agents
for f in $(git ls-files '*.md' \
    | grep -vE '^(ko/|\.github/|AGENCY-AGENTS-ANALYSIS-KO|CONTRIBUTING_zh-CN)'); do
  [ -s "ko/$f" ] || echo "$f"
done
```

### 전체 검증
```bash
# 커버리지 + 분량 + 프론트매터 + 한글 포함 여부
for f in $(git ls-files '*.md' \
    | grep -vE '^(ko/|\.github/|AGENCY-AGENTS-ANALYSIS-KO|CONTRIBUTING_zh-CN)'); do
  [ -s "ko/$f" ] || { echo "[누락] $f"; continue; }
  o=$(wc -l < "$f"); k=$(wc -l < "ko/$f")
  [ "$o" -gt 20 ] && [ $((k*100/o)) -lt 60 ] && echo "[짧음] $f  $o→$k"
  on=$(awk '/^---$/{c++;next} c==1 && /^name:/{print;exit}' "$f")
  kn=$(awk '/^---$/{c++;next} c==1 && /^name:/{print;exit}' "ko/$f")
  [ "$on" != "$kn" ] && echo "[name불일치] $f"
done

# CI 4종
./scripts/check-divisions.sh && ./scripts/check-tools.sh \
  && ./scripts/check-runbooks.sh && ./scripts/lint-agents.sh

# 원본 무수정 확인 (ko/ 외부에 변경이 없어야 함)
git status --porcelain | grep -v 'ko/'
```

---


## 5. 진행 상황

마지막 갱신: 2026-11-26 11:47 UTC

**진행률: 324 / 324 파일 (100%) — 전체 완료 ✅**

| 부서 | 완료 / 전체 | 상태 |
|---|---|---|
| 루트 문서 | 4 / 4 | ✅ 완료 |
| `integrations/` | 18 / 18 | ✅ 완료 |
| `design/` | 10 / 10 | ✅ 완료 |
| `testing/` | 9 / 9 | ✅ 완료 |
| `paid-media/` | 7 / 7 | ✅ 완료 |
| `academic/` | 6 / 6 | ✅ 완료 |
| `product/` | 5 / 5 | ✅ 완료 |
| `research/` | 1 / 1 | ✅ 완료 |
| `support/` | 6 / 6 | ✅ 완료 |
| `scripts/` | 1 / 1 | ✅ 완료 |
| `project-management/` | 7 / 7 | ✅ 완료 |
| `strategy/` | 16 / 16 | ✅ 완료 |
| `gis/` | 13 / 13 | ✅ 완료 |
| `spatial-computing/` | 6 / 6 | ✅ 완료 |
| `engineering/` | 64 / 64 | ✅ 완료 |
| `specialized/` | 59 / 59 | ✅ 완료 |
| `security/` | 12 / 12 | ✅ 완료 |
| `game-development/` | 21 / 21 | ✅ 완료 |
| `marketing/` | 36 / 36 | ✅ 완료 |
| `sales/` | 9 / 9 | ✅ 완료 |
| `examples/` | 6 / 6 | ✅ 완료 |
| `finance/` | 5 / 5 | ✅ 완료 |
| `healthcare/` | 3 / 3 | ✅ 완료 |

### 검증 결과 (전수)

| 항목 | 결과 |
|---|---|
| 커버리지 | 324 / 324 ✅ |
| 분량 (원본 85% 미만 탐지) | 의심 0건 ✅ |
| 프론트매터 `name` 일치 | 불일치 0건 ✅ |
| 한글 포함 (미번역 탐지) | 미포함 0건 ✅ |
| 깨진 문자 / PUA | 0건 ✅ |
| UTF-8 유효성 | 전부 통과 ✅ |
| `ko/` 밖 파일 변경 | 0건 ✅ |
| 비마크다운 파일 | 0건 ✅ |
| `check-divisions.sh` | PASSED ✅ |
| `check-tools.sh` | PASSED ✅ |
| `check-runbooks.sh` | PASSED ✅ |
| `lint-agents.sh` | PASSED (0 errors) ✅ |
