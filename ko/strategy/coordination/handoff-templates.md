# 📋 NEXUS 핸드오프 템플릿

> NEXUS 파이프라인에서 일어나는 모든 종류의 에이전트 간 핸드오프를 위한 표준 템플릿입니다. 일관된 핸드오프는 컨텍스트 유실을 막아줍니다 — 멀티 에이전트 조율 실패의 1순위 원인이 바로 컨텍스트 유실입니다.

---

## 1. 표준 핸드오프 템플릿

에이전트 간 모든 작업 인계에 사용합니다.

```markdown
# NEXUS 핸드오프 문서

## 메타데이터
| 항목 | 값 |
|-------|-------|
| **From** | [Agent Name] ([Division]) |
| **To** | [Agent Name] ([Division]) |
| **단계** | Phase [N] — [Phase Name] |
| **과업 참조** | [Task ID from Sprint Prioritizer backlog] |
| **우선순위** | [Critical / High / Medium / Low] |
| **타임스탬프** | [YYYY-MM-DDTHH:MM:SSZ] |

## 컨텍스트
**프로젝트**: [Project name]
**현재 상태**: [What has been completed so far — be specific]
**관련 파일**:
- [file/path/1] — [what it contains]
- [file/path/2] — [what it contains]
**의존 관계**: [What this work depends on being complete]
**제약 조건**: [Technical, timeline, or resource constraints]

## 산출물 요청
**필요한 것**: [Specific, measurable deliverable description]
**완료 기준**:
- [ ] [Criterion 1 — measurable]
- [ ] [Criterion 2 — measurable]
- [ ] [Criterion 3 — measurable]
**참고 자료**: [Links to specs, designs, previous work]

## 품질 기대치
**반드시 통과해야 할 것**: [Specific quality criteria for this deliverable]
**필요한 증거**: [What proof of completion looks like]
**다음 핸드오프 대상**: [Who receives the output and what format they need]
```

---

## 2. QA 피드백 루프 — PASS

Evidence Collector나 다른 QA 에이전트가 과업을 승인할 때 사용합니다.

```markdown
# NEXUS QA 판정: PASS ✅

## 과업
| 항목 | 값 |
|-------|-------|
| **과업 ID** | [ID] |
| **과업 설명** | [Description] |
| **개발 에이전트** | [Agent Name] |
| **QA 에이전트** | [Agent Name] |
| **시도** | 3회 중 [N]회차 |
| **타임스탬프** | [YYYY-MM-DDTHH:MM:SSZ] |

## 판정: PASS

## 증거
**스크린샷**:
- 데스크톱 (1920x1080): [filename/path]
- 태블릿 (768x1024): [filename/path]
- 모바일 (375x667): [filename/path]

**기능 검증**:
- [x] [Acceptance criterion 1] — 확인 완료
- [x] [Acceptance criterion 2] — 확인 완료
- [x] [Acceptance criterion 3] — 확인 완료

**브랜드 일관성**: 확인 완료 — 색상, 타이포그래피, 간격이 디자인 시스템과 일치
**접근성**: 확인 완료 — 키보드 내비게이션, 명암비, 시맨틱 HTML
**성능**: [Load time measured] — 허용 범위 내

## 비고
[관찰한 내용, 향후 개선을 위한 사소한 제안, 또는 칭찬할 지점]

## 다음 액션
→ Agents Orchestrator: 과업을 완료 처리하고 백로그의 다음 과업으로 진행
```

---

## 3. QA 피드백 루프 — FAIL

Evidence Collector나 다른 QA 에이전트가 과업을 반려할 때 사용합니다.

```markdown
# NEXUS QA 판정: FAIL ❌

## 과업
| 항목 | 값 |
|-------|-------|
| **과업 ID** | [ID] |
| **과업 설명** | [Description] |
| **개발 에이전트** | [Agent Name] |
| **QA 에이전트** | [Agent Name] |
| **시도** | 3회 중 [N]회차 |
| **타임스탬프** | [YYYY-MM-DDTHH:MM:SSZ] |

## 판정: FAIL

## 발견된 문제

### 문제 1: [Category] — [심각도: Critical/High/Medium/Low]
**설명**: [Exact description of the problem]
**기대 동작**: [What should happen according to acceptance criteria]
**실제 동작**: [What actually happens]
**증거**: [Screenshot filename or test output]
**수정 지침**: [Specific, actionable instruction to resolve]
**수정할 파일**: [Exact file paths]

### 문제 2: [Category] — [심각도]
**설명**: [...]
**기대 동작**: [...]
**실제 동작**: [...]
**증거**: [...]
**수정 지침**: [...]
**수정할 파일**: [...]

[발견된 모든 문제에 대해 반복]

## 완료 기준 현황
- [x] [Criterion 1] — 통과
- [ ] [Criterion 2] — 실패 (문제 1 참조)
- [ ] [Criterion 3] — 실패 (문제 2 참조)

## 재시도 지침
**개발 에이전트에게**:
1. 위에 나열된 문제만 수정하세요
2. 새로운 기능이나 변경을 추가하지 마세요
3. 모든 문제를 해결한 뒤 QA에 다시 제출하세요
4. 이번은 최대 3회 중 [N]회차 시도입니다

**3회차도 실패하면**: 과업이 Agents Orchestrator로 에스컬레이션됩니다
```

---

## 4. 에스컬레이션 리포트

과업이 재시도 3회를 초과했을 때 사용합니다.

```markdown
# NEXUS 에스컬레이션 리포트 🚨

## 과업
| 항목 | 값 |
|-------|-------|
| **과업 ID** | [ID] |
| **과업 설명** | [Description] |
| **개발 에이전트** | [Agent Name] |
| **QA 에이전트** | [Agent Name] |
| **소진된 시도** | 3/3 |
| **에스컬레이션 대상** | [Agents Orchestrator / Studio Producer] |
| **타임스탬프** | [YYYY-MM-DDTHH:MM:SSZ] |

## 실패 이력

### 1회차
- **발견된 문제**: [Summary]
- **적용한 수정**: [What the developer changed]
- **결과**: FAIL — [Why it still failed]

### 2회차
- **발견된 문제**: [Summary]
- **적용한 수정**: [What the developer changed]
- **결과**: FAIL — [Why it still failed]

### 3회차
- **발견된 문제**: [Summary]
- **적용한 수정**: [What the developer changed]
- **결과**: FAIL — [Why it still failed]

## 근본 원인 분석
**과업이 계속 실패하는 이유**: [Analysis of the underlying problem]
**구조적 문제 여부**: [일회성인가, 반복되는 패턴인가?]
**복잡도 평가**: [과업 범위가 적절하게 잡혔는가?]

## 권장 해결 방안
- [ ] **재배정** — 다른 개발 에이전트에게 ([recommended agent])
- [ ] **과업 분해** — 더 작은 하위 과업으로 ([proposed breakdown])
- [ ] **접근 방식 변경** — 아키텍처/설계 변경 필요
- [ ] **현 상태 수용** — 한계를 문서화한 상태로 수용
- [ ] **연기** — 향후 스프린트로 이월

## 영향 평가
**블로킹**: [What other tasks are blocked by this]
**일정 영향**: [How this affects the overall schedule]
**품질 영향**: [현 상태를 수용할 경우 감수해야 할 품질 타협]

## 필요한 의사결정
**의사결정자**: [Agents Orchestrator / Studio Producer]
**기한**: [추가 지연을 막기 위해 결정이 필요한 시점]
```

---

## 5. 단계 게이트 핸드오프

NEXUS 단계 간 전환 시 사용합니다.

```markdown
# NEXUS 단계 게이트 핸드오프

## 전환
| 항목 | 값 |
|-------|-------|
| **이전 단계** | Phase [N] — [Name] |
| **다음 단계** | Phase [N+1] — [Name] |
| **게이트 키퍼** | [Agent Name(s)] |
| **게이트 결과** | [PASSED / FAILED] |
| **타임스탬프** | [YYYY-MM-DDTHH:MM:SSZ] |

## 게이트 기준 결과
| # | 기준 | 임계값 | 결과 | 증거 |
|---|-----------|-----------|--------|----------|
| 1 | [Criterion] | [Threshold] | ✅ PASS / ❌ FAIL | [Evidence reference] |
| 2 | [Criterion] | [Threshold] | ✅ PASS / ❌ FAIL | [Evidence reference] |
| 3 | [Criterion] | [Threshold] | ✅ PASS / ❌ FAIL | [Evidence reference] |

## 다음 단계로 넘기는 문서
1. [Document name] — [Purpose for next phase]
2. [Document name] — [Purpose for next phase]
3. [Document name] — [Purpose for next phase]

## 다음 단계의 핵심 제약 조건
- [Constraint 1 from this phase's findings]
- [Constraint 2 from this phase's findings]

## 다음 단계 에이전트 활성화
| 에이전트 | 역할 | 우선순위 |
|-------|------|----------|
| [Agent 1] | [Role in next phase] | [Immediate / Day 2 / As needed] |
| [Agent 2] | [Role in next phase] | [Immediate / Day 2 / As needed] |

## 이월되는 리스크
| 리스크 | 심각도 | 완화 방안 | 담당 |
|------|----------|------------|-------|
| [Risk] | [P0-P3] | [Mitigation plan] | [Agent] |
```

---

## 6. 스프린트 핸드오프

스프린트 경계에서 사용합니다.

```markdown
# NEXUS 스프린트 핸드오프

## 스프린트 요약
| 항목 | 값 |
|-------|-------|
| **스프린트** | [Number] |
| **기간** | [Start date] → [End date] |
| **스프린트 목표** | [Goal statement] |
| **벨로시티** | [Planned] / [Actual] 스토리 포인트 |

## 완료 현황
| 과업 ID | 설명 | 상태 | QA 시도 | 비고 |
|---------|-------------|--------|-------------|-------|
| [ID] | [Description] | ✅ 완료 | [N] | [Notes] |
| [ID] | [Description] | ✅ 완료 | [N] | [Notes] |
| [ID] | [Description] | ⚠️ 이월 | [N] | [Reason] |

## 품질 지표
- **1차 QA 통과율**: [X]%
- **평균 재시도 횟수**: [N]
- **완료 과업**: [X/Y]
- **전달한 스토리 포인트**: [N]

## 다음 스프린트로 이월
| 과업 ID | 설명 | 사유 | 우선순위 |
|---------|-------------|--------|----------|
| [ID] | [Description] | [Why not completed] | [RICE score] |

## 회고 인사이트
**잘된 점**: [Key successes]
**개선할 점**: [Key improvements]
**액션 아이템**: [Specific changes for next sprint]

## 다음 스프린트 미리보기
**스프린트 목표**: [Proposed goal]
**핵심 과업**: [Top priority items]
**의존 관계**: [Cross-team dependencies]
```

---

## 7. 인시던트 핸드오프

인시던트 대응 중에 사용합니다.

```markdown
# NEXUS 인시던트 핸드오프

## 인시던트
| 항목 | 값 |
|-------|-------|
| **심각도** | [P0 / P1 / P2 / P3] |
| **발견 주체** | [Agent or system] |
| **발견 시각** | [Timestamp] |
| **담당** | [Agent Name] |
| **상태** | [Investigating / Mitigating / Resolved / Post-mortem] |

## 설명
**무슨 일이 일어났는가**: [Clear description of the incident]
**영향**: [누가/무엇이 얼마나 심각하게 영향을 받는가]
**타임라인**:
- [HH:MM] — [Event]
- [HH:MM] — [Event]
- [HH:MM] — [Event]

## 현재 상태
**영향받은 시스템**: [List]
**우회 방법 존재 여부**: [Yes/No — 있다면 설명]
**예상 해결 시점**: [Time estimate]

## 취한 조치
1. [Action taken and result]
2. [Action taken and result]

## 핸드오프 컨텍스트
**다음 대응자에게**:
- [시도해본 것]
- [아직 시도하지 않은 것]
- [추정 근본 원인]
- [확인할 로그/지표]

## 이해관계자 커뮤니케이션
**마지막 업데이트 발송**: [Timestamp]
**다음 업데이트 예정**: [Timestamp]
**커뮤니케이션 채널**: [업데이트를 게시하는 곳]
```

---

## 사용 가이드

| 상황 | 사용할 템플릿 |
|-----------|----------------|
| 다른 에이전트에 작업 배정 | 표준 핸드오프 (#1) |
| QA가 과업 승인 | QA PASS (#2) |
| QA가 과업 반려 | QA FAIL (#3) |
| 과업이 재시도 3회 초과 | 에스컬레이션 리포트 (#4) |
| 단계 간 전환 | 단계 게이트 핸드오프 (#5) |
| 스프린트 종료 | 스프린트 핸드오프 (#6) |
| 시스템 인시던트 | 인시던트 핸드오프 (#7) |
