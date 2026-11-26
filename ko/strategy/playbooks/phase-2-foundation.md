# ⚙️ Phase 2 플레이북 — 기반 구축 및 스캐폴딩

> **기간**: 3~5일 | **에이전트**: 6 | **게이트 키퍼**: DevOps Automator + Evidence Collector

---

## 목표

이후 모든 작업이 의존하는 기술적·운영적 토대를 만듭니다. 근육을 붙이기 전에 골격을 세웁니다. 이 단계가 끝나면 모든 개발자가 동작하는 환경, 배포 가능한 파이프라인, 그리고 함께 쓸 디자인 시스템을 갖게 됩니다.

## 사전 조건

- [ ] Phase 1 품질 게이트 통과 (아키텍처 패키지 승인)
- [ ] Phase 1 핸드오프 패키지 수령
- [ ] 모든 아키텍처 문서 확정

## 에이전트 활성화 순서

### 워크스트림 A: 인프라 (1~3일차, 병렬)

#### 🚀 DevOps Automator — CI/CD 파이프라인 + 인프라
```
[PROJECT]의 인프라 구축을 위해 DevOps Automator를 활성화합니다.

입력: Backend Architect 시스템 아키텍처 + 배포 요구사항
필요한 산출물:
1. CI/CD 파이프라인 (GitHub Actions / GitLab CI)
   - 보안 스캐닝 단계
   - 자동 테스트 단계
   - 빌드 및 컨테이너화 단계
   - 배포 단계 (블루-그린 또는 카나리)
   - 자동 롤백 기능
2. Infrastructure as Code
   - 환경 프로비저닝 (dev, staging, production)
   - 컨테이너 오케스트레이션 세팅
   - 네트워크 및 보안 설정
3. 환경 설정
   - 시크릿 관리
   - 환경 변수 관리
   - 다중 환경 간 동등성

생성할 파일:
- .github/workflows/ci-cd.yml (또는 동등한 파일)
- infrastructure/ (Terraform/CDK 템플릿)
- docker-compose.yml
- Dockerfile(s)

포맷: IaC 템플릿이 포함된 동작하는 CI/CD 파이프라인
기간: 3일
```

#### 🏗️ Infrastructure Maintainer — 클라우드 인프라 + 모니터링
```
[PROJECT]의 모니터링 구축을 위해 Infrastructure Maintainer를 활성화합니다.

입력: DevOps Automator 인프라 + Backend Architect 아키텍처
필요한 산출물:
1. 클라우드 자원 프로비저닝
   - 컴퓨트, 스토리지, 네트워킹 자원
   - 오토스케일링 설정
   - 로드 밸런서 세팅
2. 모니터링 스택
   - 애플리케이션 지표 (Prometheus/DataDog)
   - 인프라 지표
   - 커스텀 대시보드 (Grafana)
3. 로깅 및 알림
   - 중앙 집중식 로그 집계
   - 핵심 임계값에 대한 알림 규칙
   - 온콜 알림 설정
4. 보안 하드닝
   - 방화벽 규칙
   - SSL/TLS 설정
   - 접근 제어 정책

포맷: 대시보드 접근 정보가 포함된 인프라 준비 리포트
기간: 3일
```

#### ⚙️ Studio Operations — 프로세스 세팅
```
[PROJECT]의 프로세스 세팅을 위해 Studio Operations를 활성화합니다.

입력: Sprint Prioritizer 계획 + Project Shepherd 조율 요구사항
필요한 산출물:
1. Git 워크플로
   - 브랜치 전략 (GitFlow / 트렁크 기반)
   - PR 리뷰 프로세스
   - 머지 정책
2. 커뮤니케이션 채널
   - 팀 채널 세팅
   - 알림 라우팅
   - 상태 업데이트 주기
3. 문서 템플릿
   - PR 템플릿
   - 이슈 템플릿
   - 의사결정 로그 템플릿
4. 협업 도구
   - 프로젝트 보드 세팅
   - 스프린트 추적 설정

포맷: 운영 플레이북
기간: 2일
```

### 워크스트림 B: 애플리케이션 기반 (1~4일차, 병렬)

#### 🎨 Frontend Developer — 프로젝트 스캐폴딩 + 컴포넌트 라이브러리
```
[PROJECT]의 프로젝트 스캐폴딩을 위해 Frontend Developer를 활성화합니다.

입력: UX Architect CSS 디자인 시스템 + Brand Guardian 아이덴티티
필요한 산출물:
1. 프로젝트 스캐폴딩
   - 프레임워크 세팅 (아키텍처에 따라 React/Vue/Angular)
   - TypeScript 설정
   - 빌드 툴링 (Vite/Webpack/Next.js)
   - 테스트 프레임워크 (Jest/Vitest + Testing Library)
2. 디자인 시스템 구현
   - UX Architect의 CSS 디자인 토큰
   - 기본 컴포넌트 라이브러리 (Button, Input, Card, Layout)
   - 테마 시스템 (라이트/다크/시스템 전환)
   - 반응형 유틸리티
3. 애플리케이션 셸
   - 라우팅 세팅
   - 레이아웃 컴포넌트 (Header, Footer, Sidebar)
   - 에러 바운더리 구현
   - 로딩 상태

생성할 파일:
- src/ (애플리케이션 소스)
- src/components/ (컴포넌트 라이브러리)
- src/styles/ (디자인 토큰)
- src/layouts/ (레이아웃 컴포넌트)

포맷: 컴포넌트 라이브러리를 갖춘 동작하는 애플리케이션 골격
기간: 3일
```

#### 🏗️ Backend Architect — 데이터베이스 + API 기반
```
[PROJECT]의 API 기반 구축을 위해 Backend Architect를 활성화합니다.

입력: 시스템 아키텍처 명세 + 데이터베이스 스키마 설계
필요한 산출물:
1. 데이터베이스 세팅
   - 스키마 배포 (마이그레이션)
   - 인덱스 생성
   - 개발용 시드 데이터
   - 커넥션 풀링 설정
2. API 스캐폴드
   - 프레임워크 세팅 (Express/FastAPI 등)
   - 아키텍처에 맞는 라우트 구조
   - 미들웨어 스택 (인증, 검증, 에러 처리, CORS)
   - 헬스체크 엔드포인트
3. 인증 시스템
   - 인증 제공자 연동
   - JWT/세션 관리
   - 역할 기반 접근 제어 스캐폴드
4. 서비스 통신
   - API 버저닝 세팅
   - 요청/응답 직렬화
   - 에러 응답 표준화

생성할 파일:
- api/ 또는 server/ (백엔드 소스)
- migrations/ (데이터베이스 마이그레이션)
- docs/api-spec.yaml (OpenAPI 명세)

포맷: 데이터베이스와 인증을 갖춘 동작하는 API 스캐폴드
기간: 4일
```

#### 🏛️ UX Architect — CSS 시스템 구현
```
[PROJECT]의 CSS 시스템 구현을 위해 UX Architect를 활성화합니다.

입력: Brand Guardian 아이덴티티 + 본인이 Phase 1에서 만든 CSS 디자인 시스템 명세
필요한 산출물:
1. 디자인 토큰 구현
   - CSS 커스텀 프로퍼티 (색상, 타이포그래피, 간격)
   - 시맨틱 네이밍이 적용된 브랜드 색상 팔레트
   - 반응형 조정이 포함된 타이포그래피 스케일
2. 레이아웃 시스템
   - 컨테이너 시스템 (반응형 브레이크포인트)
   - 그리드 패턴 (2열, 3열, 사이드바)
   - Flexbox 유틸리티
3. 테마 시스템
   - 라이트 테마 변수
   - 다크 테마 변수
   - 시스템 설정 감지
   - 테마 전환 컴포넌트
   - 테마 간 부드러운 전환

생성/수정할 파일:
- css/design-system.css (또는 프레임워크 내 동등한 파일)
- css/layout.css
- css/components.css
- js/theme-manager.js

포맷: 테마 전환이 적용된 CSS 디자인 시스템 구현물
기간: 2일
```

## 검증 체크포인트 (4~5일차)

### Evidence Collector 검증
```
Phase 2 기반 검증을 위해 Evidence Collector를 활성화합니다.

다음 항목을 스크린샷 증거와 함께 확인하세요:
1. CI/CD 파이프라인이 정상 실행됨 (파이프라인 로그 제시)
2. 애플리케이션 골격이 브라우저에서 로드됨 (데스크톱 스크린샷)
3. 애플리케이션 골격이 모바일에서 로드됨 (모바일 스크린샷)
4. 테마 전환이 동작함 (라이트 + 다크 스크린샷)
5. API 헬스체크가 응답함 (curl 출력)
6. 데이터베이스에 접근 가능함 (마이그레이션 상태)
7. 모니터링 대시보드가 활성화됨 (대시보드 스크린샷)
8. 컴포넌트 라이브러리가 렌더링됨 (컴포넌트 데모 페이지)

포맷: 스크린샷이 포함된 증거 패키지
판정: 구체적인 문제와 함께 PASS / FAIL
```

## 품질 게이트 체크리스트

| # | 기준 | 증거 출처 | 상태 |
|---|-----------|----------------|--------|
| 1 | CI/CD 파이프라인이 빌드, 테스트, 배포를 수행 | 파이프라인 실행 로그 | ☐ |
| 2 | 모든 테이블/인덱스와 함께 데이터베이스 스키마 배포 | 마이그레이션 성공 출력 | ☐ |
| 3 | API 스캐폴드가 헬스체크에 응답 | curl 응답 증거 | ☐ |
| 4 | 프런트엔드 골격이 브라우저에서 렌더링 | Evidence Collector 스크린샷 | ☐ |
| 5 | 모니터링 대시보드에 지표 표시 | 대시보드 스크린샷 | ☐ |
| 6 | 디자인 시스템 토큰 구현 완료 | 컴포넌트 라이브러리 데모 | ☐ |
| 7 | 테마 전환 동작 (라이트/다크/시스템) | 전후 스크린샷 | ☐ |
| 8 | Git 워크플로와 프로세스 문서화 | Studio Operations 플레이북 | ☐ |

## 게이트 판정

**양측 승인 필요**: DevOps Automator (인프라) + Evidence Collector (시각)

- **PASS**: DevOps 파이프라인이 완비된 동작하는 골격 → Phase 3 활성화
- **FAIL**: 구체적인 인프라 또는 애플리케이션 문제 → 수정 후 재검증

## Phase 3로의 핸드오프

```markdown
## Phase 2 → Phase 3 핸드오프 패키지

### 모든 개발 에이전트에게:
- 동작하는 CI/CD 파이프라인 (머지 시 자동 배포)
- 디자인 시스템 토큰과 컴포넌트 라이브러리
- 인증과 헬스체크를 갖춘 API 스캐폴드
- 스키마와 시드 데이터가 있는 데이터베이스
- Git 워크플로와 PR 프로세스

### Evidence Collector에게 (상시 QA):
- 애플리케이션 URL (dev, staging)
- 스크린샷 캡처 방법론
- 컴포넌트 라이브러리 참조
- 시각 검증용 브랜드 가이드라인

### Agents Orchestrator에게 (Dev↔QA 루프 관리):
- Sprint Prioritizer 백로그 (Phase 1에서)
- 완료 기준이 포함된 과업 목록 (Phase 1에서)
- 에이전트 배정 매트릭스 (NEXUS 전략에서)
- 과업 유형별 품질 임계값

### 환경 접근 정보:
- Dev 환경: [URL]
- Staging 환경: [URL]
- 모니터링 대시보드: [URL]
- CI/CD 파이프라인: [URL]
- API 문서: [URL]
```

---

*Phase 2는 골격 애플리케이션이 구동되고, CI/CD 파이프라인이 가동되며, Evidence Collector가 모든 기반 요소를 스크린샷으로 검증했을 때 완료됩니다.*
