# 🎭 agency-agents 전수조사 분석 리포트 (한국어)

> 이 문서는 `agency-agents` 저장소를 전수조사하고, 설치·사용법·수익화까지 정리한 한국어 분석 리포트입니다.
> 작성: Claude Code 세션 (카리나 페르소나 / `CLAUDE.md` 기준)
> 작성일: 2026-10-03

---

## 🔗 관련 깃허브 주소

| 구분 | 주소 |
|---|---|
| **원본 저장소 (upstream)** | https://github.com/msitarzewski/agency-agents |
| **내 포크 (origin)** | https://github.com/bmshin94/agency-agents |
| 데스크톱 앱 저장소 | https://github.com/msitarzewski/agency-agents-app |
| 앱 최신 릴리즈 | https://github.com/msitarzewski/agency-agents-app/releases/latest |
| 앱 공식 사이트 | https://agencyagents.app |
| 이슈 / 토론 | https://github.com/msitarzewski/agency-agents/issues · https://github.com/msitarzewski/agency-agents/discussions |
| 한국어 커뮤니티 번역본 | https://github.com/jnMetaCode/agency-agents-ko |
| 일본어판 (최대 규모 참고) | https://github.com/sscodeai/agency-agents-ja |
| 중국어판 | https://github.com/jnMetaCode/agency-agents-zh |
| OpenClaw 파생 컬렉션 | https://github.com/mergisi/awesome-openclaw-agents |
| MCP 생태계 | https://modelcontextprotocol.io |

**라이선스**: MIT (Copyright (c) 2025 AgentLand Contributors) — 상업적 이용·수정·재배포 자유. 재배포 시 라이선스·저작권 고지 포함 필요.

---

## 1. 이게 뭐하는 저장소인가

한 줄 요약: **"AI 전문가 264명짜리 인력사무소(Agency)를 마크다운 파일로 패키징한 오픈소스 프로젝트"**

- Reddit 스레드에서 시작 → 전 세계 컨트리뷰터 참여 규모로 성장
- 각 에이전트는 단순 프롬프트 템플릿이 아니라 **역할·규칙·산출물·성공지표까지 명세된 완성형 페르소나**
- 핵심 가치는 ① 에이전트 코퍼스 264개 ② 16개 AI 툴로의 자동 변환/설치 파이프라인 ③ NEXUS 멀티 에이전트 오케스트레이션 체계

### 전체 구조 (파일 363개)

```
agency-agents/
├── README.md (1,138줄)      ← 전체 로스터 카탈로그
├── CLAUDE.md                ← 프로젝트 페르소나 지침 (카리나)
├── divisions.json           ← 18개 부서 정의 (단일 진실 공급원 / SSOT)
├── tools.json               ← 지원 도구 16종 정의
├── SECURITY.md / LICENSE / CONTRIBUTING_zh-CN.md
│
├── [18개 부서 폴더] ────── 에이전트 .md 264개
│   ├── engineering/        64개
│   ├── specialized/        59개
│   ├── marketing/          36개
│   ├── game-development/   21개
│   ├── gis/                13개
│   ├── security/           12개
│   ├── design/             10개
│   ├── testing/ sales/      9개씩
│   ├── project-management/ paid-media/  7개씩
│   ├── support/ spatial-computing/ academic/  6개씩
│   ├── product/ finance/    5개씩
│   ├── healthcare/          3개
│   └── research/            1개
│
├── strategy/ (16개 문서)    ← NEXUS 오케스트레이션 교리 (※ 부서 아님)
│   ├── nexus-strategy.md · EXECUTIVE-BRIEF.md · QUICKSTART.md
│   ├── playbooks/  phase-0 ~ phase-6 (7단계)
│   ├── runbooks/   시나리오 4종 + runbooks.json
│   └── coordination/ agent-activation-prompts.md · handoff-templates.md
│
├── scripts/ (총 5,194줄)    ← 핵심 엔진
│   ├── install.sh  (1,508줄)
│   ├── convert.sh  (801줄)
│   ├── lib.sh · lint-agents.sh · check-divisions.sh · check-tools.sh
│   ├── check-runbooks.sh · check-agent-originality.sh
│   ├── test-install.sh · test-convert-outputs.sh · convert-outputs.sha256
│   ├── build-hermes-plugin.py (599줄) · check-hermes-*.py
│   └── i18n/ (중국어 로컬라이즈 도구)
│
├── integrations/            ← convert.sh의 출력 트리 + 툴별 README 18개
│   └── mcp-memory/          ← MCP 영속 기억 연동 가이드 + setup.sh
├── examples/                ← 멀티 에이전트 협업 실전 예제 6개
└── .github/workflows/       ← CI 검증 6종
```

### 에이전트 파일 구조

```markdown
---
name: Frontend Developer
description: Expert frontend developer specializing in React/Vue/Angular...
tools: WebFetch, WebSearch, Read, Write, Edit   # 264개 중 17개만 선언
color: cyan
emoji: 🖥️
vibe: Builds responsive, accessible web apps with pixel-perfect precision.
---

# Frontend Developer Agent Personality
## 🧠 Your Identity & Memory      ← 정체성 / 기억
## 🎯 Your Core Mission            ← 핵심 미션
## 🚨 Critical Rules You Must Follow  ← 금지 규칙
## 📋 Your Technical Deliverables  ← 산출물 명세 (실제 코드 예제 포함)
## 📊 Success Metrics              ← 성공 지표
## 💬 Communication Style          ← 말투
```

---

## 2. 변환 + 설치 파이프라인 (저장소의 알짜)

```
264개 소스 .md
      │
      ▼
scripts/convert.sh  ← 16개 툴 포맷으로 자동 변환
      │
      ├─ claude-code  → <division>-<slug>.md        (원본 그대로)
      ├─ copilot      → <division>-<slug>.md
      ├─ gemini-cli / opencode / qwen / zcode / kimi → <slug>.md
      ├─ cursor       → .cursor/rules/*.mdc          (룰)
      ├─ codex        → *.toml                       (TOML)
      ├─ vibe         → *.toml + prompts/*.md
      ├─ antigravity  → agency-<slug>/SKILL.md       (스킬 포맷)
      ├─ osaurus      → agency-<slug>/SKILL.md       (스킬 포맷)
      ├─ hermes       → lazy-router 플러그인 1개 + 인덱스 (플러그인)
      ├─ openclaw     → <agent>/SOUL.md
      ├─ aider        → CONVENTIONS.md (단일 파일)
      └─ windsurf     → .windsurfrules  (단일 파일)
      │
      ▼
scripts/install.sh  ← 설치된 툴 자동 감지 후 올바른 경로에 배치
```

**지원 툴 16종**: `claude-code, codex, gemini-cli, copilot, qwen, cursor, opencode, osaurus, aider, antigravity, kimi, openclaw, windsurf, hermes, vibe, zcode`

### 설치 경로 (기본값 / 환경변수 오버라이드)

| 툴 | 경로 | 환경변수 |
|---|---|---|
| claude-code | `~/.claude/agents/` | `CLAUDE_CONFIG_DIR` |
| copilot | `~/.github/agents/`, `~/.copilot/agents/` | `COPILOT_AGENT_DIR` |
| antigravity | `~/.gemini/config/skills/` | — |
| gemini-cli | `~/.gemini/agents/` | `GEMINI_AGENTS_DIR` |
| opencode | `.opencode/agents/` (프로젝트) | `OPENCODE_AGENTS_DIR` |
| cursor | `.cursor/rules/` (프로젝트) | `CURSOR_RULES_DIR` |
| aider | `CONVENTIONS.md` (현재 디렉토리) | — |
| windsurf | `.windsurfrules` (현재 디렉토리) | — |
| openclaw | `~/.openclaw/agency-agents/` | `OPENCLAW_DIR` |
| qwen | `~/.qwen/agents/` 또는 `.qwen/agents/` | `QWEN_AGENTS_DIR` |
| zcode | `~/.zcode/agents/` 또는 `.zcode/agents/` | `ZCODE_AGENTS_DIR` |
| codex | `~/.codex/agents/` (TOML) | `CODEX_AGENTS_DIR` |
| osaurus | `~/.osaurus/skills/` | `OSAURUS_SKILLS_DIR` |
| hermes | `~/.hermes/plugins/` (+ 설정 자동 활성화) | `HERMES_HOME`, `HERMES_PLUGIN_DIR` |
| vibe | `~/.vibe/agents/`, `~/.vibe/prompts/` | `VIBE_HOME` |

---

## 3. NEXUS — 멀티 에이전트 오케스트레이션 체계

**NEXUS = Network of EXperts, Unified in Strategy**

문제의식: 에이전트 개별 성능은 좋아도 **핸드오프 경계에서 품질이 붕괴**한다.

### 구성 요소

| 구성 | 내용 |
|---|---|
| Master Strategy | 800줄+ 운영 교리, 전 에이전트 × 7단계 |
| Phase Playbooks (7) | phase-0 발견 → phase-6 운영, 단계별 활성화 순서·프롬프트·품질 게이트 |
| Activation Prompts | 파이프라인 역할별 즉시 사용 프롬프트 템플릿 |
| Handoff Templates (7) | QA 통과/실패, 에스컬레이션, 단계 게이트, 스프린트, 인시던트 |
| Scenario Runbooks (4) | Startup MVP / Enterprise Feature / Marketing Campaign / Incident Response |
| Quick-Start Guide | 5분 활성화 가이드 |
| `runbooks.json` | 앱의 "원클릭 팀 배포"용 기계 판독 명단 (슬러그 기반 → 이름 변경에 안전) |

### 3가지 배포 모드

| 모드 | 에이전트 수 | 기간 | 용도 |
|---|---|---|---|
| NEXUS-Full | 전원 | 12~24주 | 제품 전체 생애주기 |
| NEXUS-Sprint | 15~25명 | 2~6주 | 기능 / MVP 빌드 |
| NEXUS-Micro | 소수 | 단기 | 핀포인트 작업 |

### 핵심 설계 원칙 (그대로 차용할 가치가 큼)

- **Reality Checker**: 기본 판정이 `NEEDS-WORK`. 증거(스크린샷·테스트 결과·로그) 없으면 통과 불가 → "AI가 자기 결과물에 A+ 주는 환상적 승인" 방지
- **Dev↔QA 루프**: 최대 3회 재시도 제한 → 무한 루프 토큰 낭비 방지
- **4트랙 병렬 워크스트림**: Core Product / Growth / Quality / Brand
- **Phase 게이트**: 단계 전환마다 증거 기반 검문

---

## 4. 품질 관리 (CI 6종 + 로컬 스크립트)

| 워크플로 | 검증 내용 |
|---|---|
| `lint-agents.yml` | 프론트매터·구조 검증 |
| `check-divisions.yml` | `divisions.json` ↔ 실제 디렉토리 ↔ convert.sh/lint-agents.sh ↔ CI 필터 일치 |
| `check-tools.yml` | `tools.json` ↔ 설치/변환 스크립트 일치 |
| `check-runbooks.yml` | 런북 슬러그가 실제 에이전트 파일을 가리키는지 |
| `check-hermes-config-rewrite.yml` | Hermes 설정 재작성 회귀 테스트 (들여쓰기·멱등성) |
| `test-install.yml` | Linux / macOS 설치 테스트 |

추가로 `check-agent-originality.sh`(중복·표절 검사), `convert-outputs.sha256`(생성물 해시 고정 회귀 테스트)까지 운영 중.

> ⚠️ **주의**: 루트에 새 디렉토리를 만들고 추적 파일을 넣으면 `check-divisions.sh`가 "미등록 부서"로 판단해 CI가 실패합니다. 비(非)부서 디렉토리는 `examples, scripts, integrations, strategy` 4개만 허용됩니다. (이 문서를 루트에 둔 이유)

---

## 5. 설치 및 사용법

### 방법 A: 데스크톱 앱 (가장 쉬움)

- 다운로드: https://github.com/msitarzewski/agency-agents-app/releases/latest
- macOS: `brew install --cask msitarzewski/agency-agents/agency-agents`
- macOS / Linux / Windows 지원, 자동 업데이트

### 방법 B: Claude Code + 스크립트 (권장)

```bash
git clone https://github.com/bmshin94/agency-agents.git
cd agency-agents

# 전체 설치
./scripts/install.sh --tool claude-code

# 실행 전 계획만 확인
./scripts/install.sh --tool claude-code --dry-run

# 필요한 부서만 (권장: 토큰 절약)
./scripts/install.sh --tool claude-code --division engineering,security,marketing

# 특정 에이전트만
./scripts/install.sh --tool claude-code --agent frontend-developer,ui-designer

# 파일 목록으로
./scripts/install.sh --agents-file scripts/agents-to-install.example

# 심볼릭 링크 (git pull 시 업데이트 자동 반영)
./scripts/install.sh --tool claude-code --link

# 목록 조회
./scripts/install.sh --list tools
./scripts/install.sh --list teams
./scripts/install.sh --list agents

# 병렬 설치
./scripts/install.sh --parallel --jobs 8
```

가장 단순한 방법: `cp engineering/*.md ~/.claude/agents/`

### 방법 C: 그 외 툴

```bash
./scripts/convert.sh                 # 전체 변환 → integrations/
./scripts/convert.sh --tool cursor   # 특정 툴만
./scripts/install.sh                 # 대화형 위자드 (TTY 자동 감지)
./scripts/install.sh --tool codex
```

### 호출 방법

```
Frontend Developer 활성화해서 React 가상 스크롤 컴포넌트 만들어줘
```

```
Activate Backend Architect.
주문/결제 API 설계해줘. PostgreSQL, 하루 10만 요청 기준.
```

멀티 에이전트 릴레이:
```
1) Sprint Prioritizer    → 4주 스프린트 분할
2) UX Researcher         → 경쟁사 분석 1페이지
3) Backend Architect     → [위 결과 붙여넣기] 기반 API 설계
4) Frontend Developer    → 구현
5) Reality Checker       → 증거 기반 검수
```

NEXUS 런북 통째로:
```
strategy/runbooks/scenario-startup-mvp.md 읽고 NEXUS-Sprint 모드로 시작해줘.
프로젝트: 리모트팀 회고 도구, 4주, 솔로 개발, React + Node.
```

### 주의사항

- **OpenCode 버그**: 런타임이 약 119개만 등록하고 나머지를 조용히 버림 → `--division`으로 분할 설치 (설치기가 경고 출력)
- 264개 전부 설치 시 에이전트 선택 단계에서 컨텍스트 소비가 늘어남 → 필요한 부서만 권장
- 환경변수로 설치 경로 오버라이드 가능 (위 표 참조)

---

## 6. 플러그인? 스킬? MCP?

**본질은 "서브에이전트/페르소나 프롬프트 팩"이며, 변환 타겟에 따라 스킬 또는 플러그인 포맷이 된다. MCP는 아니다.**

| 분류 | 해당 | 설명 |
|---|:---:|---|
| 서브에이전트 프롬프트 팩 | ✅ 본질 | YAML 프론트매터 + 마크다운 시스템 프롬프트. Claude Code는 `~/.claude/agents/`에 서브에이전트로 등록 |
| 스킬(Skill) | ⭕ 변환 시 | `antigravity`, `osaurus` → `agency-<slug>/SKILL.md` |
| 플러그인(Plugin) | ⭕ 변환 시 | `hermes` → lazy-router 플러그인 1개 (`build-hermes-plugin.py`, 599줄) |
| 룰(Rules) | ⭕ 변환 시 | `cursor` → `.mdc`, `windsurf` → `.windsurfrules`, `aider` → `CONVENTIONS.md` |
| MCP 서버 | ❌ | MCP 서버 코드 없음. 실행 프로세스가 아니라 텍스트 파일 모음 |

### MCP와의 관계

1. `integrations/mcp-memory/` — 세션 간 영속 기억 연동 **가이드**. `remember`, `recall`, `rollback`, `search` 툴을 노출하는 MCP 서버를 별도 준비해야 함
   ```json
   { "mcpServers": { "memory": { "command": "your-mcp-memory-server", "args": [] } } }
   ```
2. `specialized/specialized-mcp-builder.md` — **MCP 서버를 설계·구현·테스트해주는 에이전트**
3. `tools:` 프론트매터 — 264개 중 17개만 툴 접근 권한 선언, 나머지는 호스트 툴 기본 권한

---

## 7. API 토큰이 필요한가

**저장소 자체는 토큰 불필요. 하드코딩된 키/토큰 없음(검증 완료).**
API 키 언급은 전부 교육용 예제 / 보안 가이드 문맥(`security-senior-secops`, `security-ai-generated-code-auditor`, `engineering-technical-writer`, `engineering-voice-ai-integration-engineer`, `marketing-carousel-growth-engine`, `examples/nexus-spatial-discovery`).

| 상황 | 토큰 필요 | 설명 |
|---|:---:|---|
| 클론 + 설치 | ❌ | 파일 복사. 네트워크 미사용 |
| `convert.sh` / `install.sh` | ❌ | 순수 bash / python 로컬 처리 |
| Claude Code로 에이전트 사용 | ⭕ | **Claude Code 자체의** 구독 또는 Anthropic API 키 |
| Cursor / Copilot 등에서 사용 | ⭕ | 해당 툴의 구독·키 (에이전트 파일과 무관) |
| `tools: WebSearch` 보유 17개 | ⭕ | 호스트 툴의 검색 기능 → 호스트 요금에 포함 |
| MCP 메모리 연동 | ⭕(별개) | MCP 서버 별도 구동 (대부분 로컬 무료) |
| 에이전트가 안내하는 외부 서비스 | ⭕(별개) | 예: SEO 툴 구독은 사용자 계정 |

**결론: 저장소는 무료. 이미 Claude Code를 쓰고 있다면 추가 비용 0원.**

---

## 8. AI 에이전트 구축에 도움이 되는가 → 매우 큰 도움

### ① 프롬프트 설계 교과서 264권
검증된 구조를 그대로 차용 가능:
`정체성 → 미션 → 금지 규칙 → 산출물 명세(코드 예제) → 성공 지표 → 말투`

### ② 에이전트 제작 지원 에이전트들

| 에이전트 | 역할 |
|---|---|
| `engineering-prompt-engineer` | 애매한 지시 → 안정적 AI 동작 변환 |
| `engineering-multi-agent-systems-architect` | 멀티 에이전트 토폴로지·컨텍스트·신뢰·실패복구 설계 |
| `specialized-mcp-builder` | MCP 서버 설계·구현·테스트 |
| `engineering-rag-pipeline-engineer` | 프로덕션 RAG (청킹·하이브리드 검색·리랭킹·eval) |
| `engineering-knowledge-graph-engineer` | Neo4j + LangGraph 그래프 RAG |
| `engineering-llm-post-training-engineer` | SFT / DPO / GRPO / RLVR |
| `engineering-autonomous-optimization-architect` | LLM 라우팅 + 비용 최적화 + 섀도 테스팅 |
| `engineering-ai-engineer` | ML 모델 배포·통합 |
| `specialized-workflow-architect` / `specialized-model-qa` / `agents-orchestrator` | 워크플로·QA·파이프라인 지휘 |

### ③ NEXUS = 멀티 에이전트 설계 패턴 모음
- 핸드오프 컨텍스트 유실 → 핸드오프 템플릿 7종
- 자기 결과 과대평가 → Reality Checker "증거 없으면 불합격"
- 무한 재시도 → 3회 제한 Dev↔QA 루프
- 단계 전환 혼란 → Phase 게이트 0~6
- 병렬 실행 충돌 → 4트랙 워크스트림

### ④ 아키텍처 레퍼런스
- `divisions.json` / `tools.json` / `runbooks.json` → **SSOT + CI 교차 검증** 패턴
- 슬러그 기반 참조 → 표시명 변경에 안전한 레지스트리 설계
- `convert.sh` → 1 소스 N 포맷 빌드 패턴
- `convert-outputs.sha256` → 생성물 해시 고정 회귀 테스트
- `check-agent-originality.sh` → 중복 방지

### 한계 (직접 보완해야 하는 것)

| 없는 것 | 보완 |
|---|---|
| 실행 런타임 / 코드 | LangGraph, CrewAI, Claude Agent SDK 등 |
| 영속 메모리 | MCP 메모리 서버 (가이드만 존재) |
| 자동 에이전트 선택 라우터 | Hermes 플러그인 참고 또는 직접 구현 |
| 평가(eval) 프레임워크 | 자체 구현 |
| 툴 호출 스키마 | 17개만 `tools:` 선언 |

---

## 9. React / PHP로 재구현 가능한가 → 가능

구조화된 텍스트 + bash이므로 어떤 언어로든 재구현 가능.

### React / Next.js

1. **에이전트 카탈로그 웹앱** (가장 현실적)
   - 데이터: `divisions.json` + 264개 프론트매터 (`gray-matter` 파싱 → JSON 빌드)
   - 기능: 18개 부서 필터(label/icon/color 그대로 활용), 실시간 검색, 상세 뷰, "내 팀 구성" → ZIP/설치 명령어 생성, 프롬프트 복사, 다국어
   - 스택: Next.js + Tailwind + shadcn/ui + Fuse.js + gray-matter → Vercel 정적 배포(서버비 0)
2. **에이전트 에디터/빌더** — 폼 입력 → `.md` 생성, `lint-agents.sh` 규칙을 JS로 포팅해 실시간 검증
3. **NEXUS 대시보드** — 7단계 칸반, 활성화 프롬프트 원클릭, 핸드오프 템플릿 자동 채우기
4. **실제 동작 채팅** — 에이전트 본문을 `system`에 주입

```js
import Anthropic from '@anthropic-ai/sdk';
const client = new Anthropic({ apiKey: process.env.ANTHROPIC_API_KEY });
const msg = await client.messages.create({
  model: 'claude-sonnet-5-5',
  max_tokens: 4096,
  system: agentMarkdownBody,
  messages: [{ role: 'user', content: userInput }],
});
```
> API 키는 반드시 서버사이드(Route Handler)에서만 사용. 브라우저 노출 금지.

### PHP

1. **WordPress 플러그인** (저장소에 WP/Drupal 전문 에이전트 6개 존재 → 시너지)
   - 에이전트 `.md` → 커스텀 포스트 타입 임포트
   - 프론트매터 파서(`preg_match` + `yaml_parse` / `symfony/yaml`)
   - 관리자 화면 채팅, 숏코드 프론트엔드 노출
   - `wp_remote_post`로 `https://api.anthropic.com/v1/messages` 호출 (헤더: `x-api-key`, `anthropic-version: 2023-06-01`)
2. **Laravel SaaS** — Filament 어드민, Livewire 실시간 채팅, Cashier + 토스페이먼츠 과금, Horizon 큐로 멀티 에이전트 비동기 파이프라인
3. **PHP CLI 변환기** — `php agency.php convert --tool=cursor` 등, Windows 호환성 이점

### 추천 조합

```
Next.js (카탈로그·검색·팀빌더)
      │ REST / JSON
Laravel API (인증·구독·크레딧·큐·Claude API 프록시 — 키 보관)
      │
agency-agents (264 .md + divisions/tools/runbooks JSON)
```

MVP 4주: 1주 파서+JSON 빌드+번역 / 2주 카탈로그 / 3주 API 프록시+채팅+크레딧 / 4주 결제+배포+랜딩

---

## 10. 유튜브 강의 제작 가능한가 → 가능

- **MIT 라이선스**이므로 상업적 강의 제작 자유. 설명란에 원본 저장소 링크 표기 권장
- 한국어 AI 에이전트 실무 콘텐츠가 희소하고 검색 수요는 급증 중, 264개 = 에피소드 무한

### 커리큘럼

**입문 (각 8~12분)**
1. AI 직원 264명을 5분 만에 고용했습니다 (개요 + 설치 데모)
2. Claude Code에 에이전트 설치 완전정복 (`install.sh` 전 옵션)
3. Cursor·Codex·Gemini에도 똑같이 깔기 (`convert.sh`)
4. 에이전트 `.md` 파일 완전 분해 (프론트매터 + 6개 섹션)
5. 나만의 에이전트 직접 만들기

**실전 (각 15~25분)**
6. 에이전트 5명으로 랜딩페이지 하루에 만들기
7. NEXUS 지휘법: AI 팀이 안 싸우게 하는 7단계
8. Reality Checker: AI가 자기 결과에 A+ 주는 걸 막는 법
9. 워드프레스 쇼핑몰, AI 에이전트 3명으로 구축
10. 핸드오프 템플릿으로 컨텍스트 유실 막기

**심화 (각 20~30분)**
11. MCP 메모리로 에이전트에 기억 심기
12. React로 에이전트 카탈로그 웹앱 만들기
13. Laravel로 에이전트 SaaS 만들기
14. 264개 전부 깔면 안 되는 이유 (토큰 경제학)
15. 에이전트 수익화 실전

**숏츠 (30~60초)** — 마케팅 에이전트 36개 순회 / Before·After 비교 / Reality Checker / TOP 5

### 제작 팁
화면녹음 + 실제 터미널 실행 · Before/After 비교 · 1분 내 결과물 선공개 · 터미널 폰트 18pt+ · 설명란에 GitHub 링크·타임스탬프·명령어 전문 · 챕터 마커 · 재생목록 시리즈화

### 주의
API 키 노출 금지 · AI 생성물 명시 · 촬영 시점 커밋 해시 기재(저장소가 계속 업데이트됨)

### 수익 구조
애드센스 + 채널 멤버십 + 인프런/클래스101 강의 + 제휴 링크 + 컨설팅 유입 + 템플릿 판매

---

## 11. 수익화 아이디어 상세

> MIT 라이선스 기반으로 모두 합법. 재배포 상품에는 원본 MIT 라이선스·저작권 고지를 포함할 것.

### 요약표

| # | 아이디어 | 난이도 | 수익 모델 | 예상 월수익 |
|---|---|:---:|---|---|
| 1 | 한국어 완전 현지화 번들 | 중 | 1회 판매 + 구독 | ₩4,430,000 |
| 2 | 웹 SaaS "에이전트 허브" | 중상 | Freemium 구독 | 순익 ₩5,400,000 |
| 3 | 업종별 에이전트 팩 | 중 | 팩 판매 | ₩2,000,000 → ₩9,000,000 |
| 4 | 유튜브 + 온라인 강의 | 하 | 광고 + 강의 + 부트캠프 | ₩7,000,000~10,000,000 |
| 5 | AI 에이전시 대행 | 중 | 프로젝트 수임료 | ₩5,400,000 |
| 6 | WordPress 플러그인 | 중상 | 연간 라이선스 | ₩16,000,000/년 → ₩40,000,000/년 |
| 7 | 기업 컨설팅·사내 구축 | 상 | 고액 프로젝트 + 리테이너 | 건당 ₩15,000,000~50,000,000 |
| 8 | 노션/옵시디언 템플릿 | 하 | 템플릿 판매 | ₩2,900,000 |
| 9 | 에이전트 마켓플레이스 | 상 | 수수료 30% | 투자 유치형 |
| 10 | 뉴스레터 + 멤버십 | 하 | 유료 구독 | ₩4,950,000 |

### 1. 한국어 완전 현지화 번들 「AI 에이전시 코리아」

**근거**: 중국어·포르투갈어·러시아어·인도네시아어·아랍어·일본어·베트남어 번역본이 존재. 한국어판은 184개에서 정체 + 한국 시장 오리지널 없음. 일본어판은 "281 현지화 + 97 일본 오리지널 + 27 워크플로"로 압도적 → 한국 시장은 공백.

**구성**
- 264개 전체 한국어 번역 (직역이 아닌 한국 실무 맥락 재작성)
- 한국 시장 오리지널 30~50개 신규 제작:
  네이버 SEO 전략가 / 카카오톡 채널 마케터 / 쿠팡·스마트스토어 셀러 전략가 / 당근마켓 로컬 마케터 / 한국 세무사 어시스턴트(부가세·종소세·연말정산) / 4대보험·근로기준법 HR / 전자금융감독규정 컴플라이언스 / 개인정보보호법(PIPA) 담당자 / 나라장터 제안서 전문가 / 토스페이먼츠·포트원 결제 엔지니어 / 한국 부동산 중개 / 블라인드·잡플래닛 평판 관리
- 한국어 NEXUS 플레이북 + 런북, 설치 가이드 영상, 노션 매뉴얼

**가격**: 무료 20개 샘플(리드 수집) / 스탠다드 ₩49,000 / 프로 ₩129,000 / 구독 ₩9,900/월 / 팀 ₩290,000/년
**시나리오**: 월 50건 × ₩49,000 = ₩2,450,000 + 구독 200명 × ₩9,900 = ₩1,980,000 → **월 ₩4,430,000**
**회수기간**: 2~3개월

### 2. 웹 SaaS 「에이전트 허브」 (React + Laravel)

**차별화**: 공식 데스크톱 앱 대비 **한국어 + 웹 + 즉시 실행 + 파이프라인**

| 티어 | 가격 | 기능 |
|---|---|---|
| 무료 | ₩0 | 264개 카탈로그·한국어 검색, 프롬프트 복사, 월 20회 체험 채팅, 설치 명령어 생성기 |
| 프로 | ₩19,900/월 | 무제한 채팅, 멀티 에이전트 파이프라인, NEXUS 7단계 보드, 히스토리·산출물 아카이브, 커스텀 에이전트 제작기, ZIP/스크립트 내보내기 |
| 팀 | ₩99,000/월 | 5~20석, 팀 공유, 사내 컨벤션 주입, 사용량 리포트, SSO |

**스택**: Next.js 15 + Tailwind + shadcn/ui + Fuse.js / Laravel 11 + Filament + Horizon / Anthropic SDK (`claude-sonnet-5-5`, `claude-opus-5-5`) / PostgreSQL + Redis / 토스페이먼츠·포트원(해외 Stripe) / Vercel + Forge

**시나리오**: 프로 300명 ₩5,970,000 + 팀 20팀 ₩1,980,000 = 매출 ₩7,950,000 − API 원가 약 ₩2,200,000 − 인프라 ₩300,000 → **순익 약 ₩5,400,000/월**

**리스크 대응**: 크레딧 상한 + 프롬프트 캐싱 + 모델 티어링(Haiku→Sonnet), 서버사이드 프록시 only + 레이트 리밋

**MVP**: 4~6주 / 회수기간 4~6개월

### 3. 업종별 「AI 에이전트 팩」 (가장 빠른 현금화)

**근거**: 264개 중 내 업종에 필요한 건 10개뿐 → 큐레이션 + 현지화가 곧 가치

| 팩 | 가격 | 기반 에이전트 | 추가 오리지널 |
|---|---|---|---|
| 🏥 병원·의원 | ₩89,000 | healthcare-* 3개, healthcare-customer-service, healthcare-marketing-compliance, medical-billing-coding-specialist | 의료광고 심의(의료법 56조), 건강보험 청구, 네이버 플레이스 병원 마케터, 환자 리뷰 응대, 비급여 진료비 안내 |
| ⚖️ 법무법인 | ₩149,000 | legal-document-review, legal-client-intake, legal-billing-time-tracking, support-legal-compliance-checker | 한국 판례 리서치, 계약서 검토(민법), 내용증명, 등기 서류 체크리스트 |
| 🛒 이커머스 셀러 | ₩69,000 | wordpress/drupal-shopping-cart, payments-billing-engineer, retail-customer-returns, marketing-seo-specialist, paid-media-ppc-strategist | 쿠팡 로켓그로스, 스마트스토어 상위노출, 상세페이지 카피, 리뷰 관리, CS 템플릿 |
| 🏗️ 건설·시공 | ₩99,000 | specialized-civil-engineer, project-manager-senior, finance-fpa-analyst | 건설안전보건관리, 하도급법, 공공입찰 제안서 |
| 💻 1인 개발자 생존 | ₩59,000 | engineering 핵심 15개, finance-tax-strategist, resume-tailor, sales-proposal-strategist | 프리랜서 견적서·계약서 |

**시나리오**: 팩 5종 × 월 20건 × 평균 ₩90,000 = ₩9,000,000/월 (현실적으로 초기 1~2백만 → 6개월 후 5백만+)
**채널**: 크몽 / 탈잉 / 자체몰 / Gumroad / 노션 판매
**제작기간**: 팩당 1~2주

### 4. 유튜브 + 온라인 강의 (리스크 최저)

```
Phase 1 (1~3개월) 유튜브 무료 — 입문 5편 + 숏츠 20편, 구독 1,000명·4,000시간 달성,
                                 전 영상 → 무료 PDF 리드마그넷 → 이메일 수집
Phase 2 (3~6개월) 유료 강의 — 인프런 ₩99,000, 클래스101/자체 동시, 구독자 할인 쿠폰
Phase 3 (6~12개월) 고단가 — 라이브 부트캠프 4주 ₩490,000 × 20명,
                              1:1 컨설팅 시간당 ₩150,000, 기업 사내교육 1일 ₩2,000,000~
```
**시나리오**: 애드센스 ₩500,000~1,500,000 + 인프런 월 50명 × ₩99,000 × 0.7 = ₩3,465,000 + 부트캠프 분기 ₩9,800,000 + 기업교육 ₩2,000,000 + 제휴·템플릿 → **월 평균 ₩7,000,000~10,000,000**
**초기비용 거의 0, 복리 효과 최고**

### 5. AI 에이전시 대행 서비스 (즉시 현금흐름)

264명 + NEXUS = 1인이 에이전시급 산출물 생산.

| 상품 | 가격 | 투입 에이전트 | 납기 |
|---|---|---|---|
| 랜딩페이지 풀패키지 | ₩1,500,000 | UX Researcher → UI Designer → Frontend Developer → SEO Specialist → Reality Checker | 1주 |
| MVP 구축 | ₩8,000,000 | NEXUS-Sprint (15~25명) | 4~6주 |
| 사이트 성능 진단서 | ₩800,000 | WP/Drupal Performance + Database Optimizer | 3일 |
| SEO 종합 감사 | ₩1,200,000 | SEO Specialist + AEO Foundations + Technical Writer | 1주 |
| 보안 감사 리포트 | ₩2,000,000 | security 12개 + AI Generated Code Auditor | 2주 |
| 브랜드 전략 패키지 | ₩2,500,000 | Brand Guardian + Visual Storyteller + Image Prompt Engineer | 2주 |
| 사업계획서/IR덱 | ₩1,800,000 | business-strategist + chief-financial-officer + Universal Document Compiler | 1주 |
| 정부지원사업 신청서 | ₩1,500,000 | grant-writer + government-digital-presales-consultant | 1주 |

**시나리오**: 월 3건 × 평균 ₩1,800,000 = ₩5,400,000/월. 건당 API 원가 ₩50,000~150,000 → 마진률 90%+
**채널**: 크몽 / 위시켓 / 프리랜서코리아 / 링크드인 콘텐츠 마케팅 / 유튜브 유입

### 6. WordPress 플러그인 상품화

**근거**: WordPress는 전 세계 웹사이트 40%+, 저장소에 WP/Drupal 전문 에이전트 6개, PHP 역량이 진입장벽 겸 방어막

| 판 | 가격 | 기능 |
|---|---|---|
| 무료 (WP.org) | $0 | 에이전트 20개, 관리자 채팅(사용자 키 입력), 프롬프트 라이브러리 |
| 프로 | $79/년 (1사이트) | 264개 전체 + 월 업데이트, 숏코드 프론트엔드, 포스트 자동 초안, WooCommerce 상품 설명 생성, Elementor/Gutenberg 블록 |
| 멀티사이트 | $199/년 | 멀티사이트 지원 |
| 에이전시 | $399/년 | 무제한 사이트 |

**시나리오**: 무료 설치 5,000건 × 전환율 3% = 150건 × $79 ≈ **₩16,000,000/년**, 2년차 갱신+신규 → ₩40,000,000/년 목표
**채널**: 자체몰 + CodeCanyon + WP.org 무료판 유입 / **제작 6~8주**

### 7. 기업 컨설팅 + 사내 AI 에이전트 구축 (최고 단가)
현황 진단 → 사내 맞춤 에이전트 제작 → NEXUS 도입 → 교육.
**₩15,000,000~50,000,000/프로젝트 + 리테이너 ₩2,000,000/월**
타겟: 중견기업 IT팀, 디지털 전환 조직. 근거자료로 `automation-governance-architect`, `change-management-consultant` 활용.

### 8. 노션/옵시디언 템플릿 번들 (초간단)
264개 DB화 + 부서 필터 + 복사 버튼, NEXUS 7단계 템플릿, 핸드오프 템플릿 7종.
**₩29,000 × 월 100건 = ₩2,900,000/월**. 제작 2~3일, 패시브 인컴.

### 9. 에이전트 마켓플레이스 (스케일 승부)
창작자 업로드 → 판매, 수수료 30%. 264개를 무료 시드 콘텐츠로(MIT 합법). 품질 검증은 `lint-agents.sh` + `check-agent-originality.sh` 포팅.
양면시장 치킨에그 문제 → 투자 유치형.

### 10. 뉴스레터 + 유료 멤버십 (신뢰 자산)
무료: 주 1개 에이전트 심층 분석 + 업계 뉴스 / 유료 ₩9,900/월: 신규 에이전트 + 실전 템플릿 + 디스코드 + 월간 라이브 Q&A.
**500명 × ₩9,900 = ₩4,950,000/월**. 성장은 느리지만 가장 단단한 자산.

---

## 12. 추천 로드맵

```
0~1개월   ⚡ 업종별 팩 「1인 개발자 생존 팩」 제작·판매 (1~2주, 투자 0원, 시장 검증)
          📹 동시에 유튜브 입문 5편 촬영
1~3개월   💸 대행 서비스 시작 (랜딩페이지 패키지 ₩1,500,000) — 포트폴리오 = 유튜브 소재
          🇰🇷 한국어 번역 작업 병행
3~6개월   🚀 SaaS 또는 WP 플러그인 개발 (앞 단계 수익으로 개발기간 버티기)
          🎓 인프런 강의 론칭 (유튜브 구독자 = 초기 유저)
6~12개월  👑 기업 컨설팅 (고단가) + 💌 멤버십으로 안정화
```

---

## 13. 공통 주의사항

1. **MIT 라이선스 고지** — 재배포 상품에 원본 MIT 라이선스 + 저작권 고지 포함 (필수 조건)
2. **"공식" 표현 금지** — 원본 프로젝트와 무관한 독립 상품임을 명시
3. **API 키 관리** — 반드시 서버사이드, 사용량 상한 필수
4. **AI 생성물 고지** — 의료·법률·세무 팩은 "전문가 검토 필수" 면책 문구 필수
5. **원가 관리** — 프롬프트 캐싱 + 모델 티어링으로 API 비용 50%+ 절감 가능
6. **업스트림 추적** — `git remote add upstream https://github.com/msitarzewski/agency-agents.git` 후 주기적 동기화
7. **CI 제약** — 루트에 새 디렉토리 + 추적 파일 추가 시 `check-divisions.sh` 실패. 비부서 디렉토리는 `examples, scripts, integrations, strategy`만 허용

---

## 14. 핵심 수치 요약

| 항목 | 값 |
|---|---|
| 전체 파일 | 363개 |
| 에이전트 (프론트매터 보유) | 264개 |
| 부서 (divisions.json) | 18개 |
| 지원 AI 툴 (tools.json) | 16종 |
| `tools:` 선언 에이전트 | 17개 |
| scripts 총 코드량 | 5,194줄 |
| `install.sh` / `convert.sh` | 1,508줄 / 801줄 |
| NEXUS 문서 | 16개 (플레이북 7 + 런북 4 + 교리 3 + 코디네이션 2) |
| CI 워크플로 | 6종 |
| 라이선스 | MIT |
| 커뮤니티 번역본 | 9개 (중국어 2, 일본어, 한국어, 포르투갈어, 러시아어, 인도네시아어, 아랍어, 베트남어) |

---

*이 리포트는 저장소를 직접 전수조사하여 작성되었습니다. 수익 예상치는 가정에 기반한 시나리오이며 보장된 수치가 아닙니다.*
