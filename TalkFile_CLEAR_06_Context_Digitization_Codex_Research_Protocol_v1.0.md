---
title: "CLEAR 발표 6장 - Context Digitalization 심층 리서치 Codex 업무 지침"
version: "1.0"
status: "Execution Ready"
project: "AI 국방 해커톤 / CLEAR"
research_scope: "출입 판단에 필요한 기지 맥락의 디지털화·객체화 가능성 검증"
primary_output: "Slide 6 Evidence Pack + FINAL_REPORT"
---

# CLEAR 발표 6장 - Context Digitalization 심층 리서치 Codex 업무 지침

## 0. 문서의 목적

이 문서는 Codex가 추가 설명 없이 읽고 실행할 수 있는 **연구 과제 지시서이자 재현 가능한 리서치 프로토콜**이다.

연구의 최종 목적은 다음 질문에 근거 있게 답하는 것이다.

> **초병이 실제 출입 판단에 사용하는 사람·차량·권한·승인·목적·시간·구역·장비·현장상황 등의 맥락을 기계가 처리 가능한 디지털 객체·관계·속성·상태로 표현할 수 있는가?**

이 연구는 Ontology를 정답으로 전제하지 않는다.  
먼저 무인화/자율화의 선결요건을 조사하고, 그 요건 중 **machine-readable context**가 왜 필요한지 확인한 뒤, 현실 데이터를 어떤 수준까지 디지털화·구조화해야 하는지 검토한다. 이후 민간·산업 표준과 군/DoD 공개 기준을 통해 이를 정렬하고, 마지막으로 공군 출입통제 도메인에서 실제 객체·관계·상태로 매핑 가능한지를 증명한다.

**연구의 순서**

1. 기존 AS-IS 증거 정규화
2. 무인화/자율화 선결요건 조사
3. 현실 데이터의 Digitization-to-Decision 구조 조사
4. 민간·산업 출입통제 및 데이터 표준 Crosswalk
5. 군/DoD/공군 공개 기준 Crosswalk
6. Air Force Access Context Model v0.1 작성
7. 가능성(Feasibility)과 타당성(Validity) 평가
8. 발표 6장 Evidence Pack 작성

---

# 1. 연구가 증명해야 하는 것

## 1.1 핵심 연구 질문

**RQ1.** 자율/무인 시스템이 현실 세계에서 판단하려면 어떤 정보표현이 선결되어야 하는가?  
**RQ2.** 초병의 실제 출입 판단정보 중 무엇이 이미 디지털 데이터로 존재하거나 센서/업무시스템을 통해 구조화 가능한가?  
**RQ3.** 민간·정부·군 표준은 사람, 자격, 차량, 구역, 시간, 정책, 이벤트 등을 어느 수준까지 machine-readable 형태로 정의하는가?  
**RQ4.** 공군 출입통제의 주요 판단 Context를 기존 표준을 활용하여 객체·관계·속성·상태로 모델링할 수 있는가?  
**RQ5.** 데이터가 존재하는 것과 실제 자동판단에 충분한 것은 어떻게 다른가?  
**RQ6.** 어떤 정보는 디지털화 가능하지만, 여전히 인간의 현장판단·예외처리가 필요하다고 보아야 하는가?

## 1.2 검증 명제(Propositions)

아래 명제는 연구 시작 시의 가설이며, 연구 결과에 따라 수정·축소·기각할 수 있다.

### P1. Machine-readable Context 필요성
무인/자율 판단은 운영환경, 대상 객체, 상태, 권한, 정책 및 이벤트를 기계가 처리할 수 있는 형태로 표현하는 것을 선결요건으로 요구한다.

### P2. 출입 판단 핵심정보의 구조화 가능성
초병의 정상 출입 판단에 사용되는 핵심 정보의 상당 부분은 기존 시스템, 센서, 승인 데이터, 신원/자격 데이터, 시간/구역 데이터 등으로부터 디지털화·구조화할 수 있다.

### P3. 표준 재사용 가능성
출입통제 핵심 개념의 상당 부분은 NIST/FICAM, ONVIF, SIA/OSDP, OPC UA, ABAC/XACML, 군 출입통제 문서 등 기존 표준 또는 공개 데이터 모델에 부분적으로 정의되어 있다.

### P4. 공군 도메인 확장 가능성
공군 출입통제의 특수 맥락은 기존 표준을 폐기하지 않고, Core Model + Military Extension + Local Extension 구조로 확장해 표현할 수 있다.

### P5. 완전자동화와 디지털화는 동일하지 않음
Context의 디지털화 가능성이 확인되더라도, 관측 신뢰도·정책 모호성·예외상황·물리대응·보안등급 등의 이유로 일부 판단은 Human-in-the-loop 또는 Human-on-the-loop로 남을 수 있다.

---

# 2. 연구가 증명하면 안 되는 것

다음 주장은 6장의 연구 목적이 아니다.

- "기지 전체를 완전히 디지털 트윈화할 수 있다."
- "모든 초병 판단을 자동화할 수 있다."
- "Ontology가 반드시 유일한 정답이다."
- "모든 기존 시스템이 API를 제공한다."
- "모든 군 출입통제 데이터가 실시간으로 취득 가능하다."
- "현재 단일 인터뷰에서 확인한 절차가 대한민국 공군 전체의 표준 절차다."
- "센서 정확도, 네트워크 가용성, 보안등급 문제가 모두 해결되어 있다."
- "AI가 최종 Allow/Deny 판단을 독립적으로 수행해야 한다."

6장의 결론은 **디지털화·객체화 가능성의 범위와 조건**을 증명하는 데 한정한다.

---

# 3. 연구 범위와 비범위

## 3.1 포함 범위

- 출입 판단에 필요한 정보의 종류
- 사람/차량/권한/승인/목적/시간/구역/이벤트/장비 상태의 데이터화
- 센서 관측값 → 객체/이벤트 변환
- 공통 식별자, 속성, 관계, 상태, 시간 유효성
- 데이터 provenance와 신뢰도
- 출입통제·물리보안 데이터 표준
- 군/DoD 공개 기준의 정보범주
- 공군 도메인에 적용 가능한 객체 모델
- 정상상황 자동판단을 위한 최소 Context Set
- Human exception/escalation을 위한 정보 요구

## 3.2 제외 범위

- 실제 한국 공군 기지의 상세 경계배치
- 비공개 규정·계정·네트워크·시스템 구조
- 실제 경계 우회 또는 취약점 악용 정보
- 무기체계 세부 구조
- 센서별 구체적 공격/회피 방법
- 최종 CLEAR 구현 아키텍처 확정
- Ontology vs 다른 기술의 최종 채택 결정
- 7장의 상용 솔루션 Landscape 전체
- AI 모델 선정 및 성능평가

---

# 4. 기존 AS-IS 입력자료: 반드시 먼저 읽을 파일

연구 시작 전 아래 자료를 `inputs/`에 배치한다. 실제 파일명이 다르면 원본명은 보존하고 아래 Alias를 `inputs/README.md`에 매핑한다.

## 4.1 Primary AS-IS Evidence

| Alias | 문서 제목 / 권장 파일명 | 연구에서의 지위 | Codex가 추출할 핵심 |
|---|---|---|---|
| ASIS-01 | `CLEAR_출입생애주기_AS-IS_1차조사보고서_v1.md` | Local Ground Truth | 업무 흐름, Actor, 승인, 현장확인, 예외, 확인/추정/미확인 |
| ASIS-02 | `CLEAR_Phase2_AS-IS_조사체크리스트.xlsx` | Evidence Register | Q-ID, 조사결과, 사실성, 근거 ID, 추가 확인항목 |
| ASIS-03 | `CLEAR_초병중심_AS-IS_업무구조도_분석보고서_v1.md` | Working Task Model | 초병 업무 단계, Input-Process-Output, 판단/집행 구조 |
| ASIS-04 | `CLEAR_공모과제_기반_AS-IS_조사_Agent_작업지침_v3.md` | Scope / Methodology | 조사 범위, 객체 분류, 사실성 관리 원칙 |

## 4.2 Supporting Prior Research

| Alias | 문서 제목 / 권장 파일명 | 연구에서의 지위 | 사용 목적 |
|---|---|---|---|
| REF-01 | `군_기지_무인자율화_출입게이트_실현범위_CLEAR_핵심가설검증.md` | External Benchmark | 군 무인/자율 게이트의 조건부 자율화 범위 |
| REF-02 | `AS-IS_물리보안_출입통제_통합관제_도식_레퍼런스_심층조사.md` | Industry Supporting Research | PACS/VMS/PSIM 등 기존 객체·이벤트·시스템 구조 |
| META-01 | `CLEAR_온톨로지_Semantic_Layer_채택_및_초병업무_자동화병목_검증_심층연구설계.md` | Research Methodology | 연구 질문, 기존 가설, 후속 연구 정렬 |

## 4.3 입력자료의 증거 지위 규칙

- `ASIS-01`, `ASIS-02`: **현장 Local Evidence**
- `ASIS-03`: **팀의 Working Model**. 외부 사실로 인용 금지.
- `ASIS-04`: **조사 Scope/Method**
- `REF-*`: **기존 외부 리서치**. 원출처 재확인 필요.
- `META-*`: **방법론/가설 자료**. 결론의 근거로 직접 사용 금지.

---

# 5. 전체 연구 파이프라인

```text
AS-IS 원자료
   ↓
Phase -1. Internal Evidence Normalization
   ↓
현장 Context Candidate / Decision Requirement / Unknowns
   ↓
Phase 0. 연구 명제 및 범위 고정
   ↓
Phase 1. Autonomy Prerequisite Research
   ↓
Phase 2. Digitization-to-Decision Research
   ↓
Phase 3. Civil/Industry Standards Crosswalk
   ↓
Phase 4. DoD/Military/Air Force Crosswalk
   ↓
Phase 5. Air Force Access Context Model v0.1
   ↓
Phase 6. Feasibility & Validity Evaluation
   ↓
Phase 7. Slide 6 Evidence Pack
```

**중요:** 외부 검색은 Phase -1이 끝난 뒤 시작한다.

---

# 6. Phase -1. Internal AS-IS Evidence Normalization

## 목적

이미 확보한 현장자료를 연구 가능한 형태로 정규화한다.  
외부 문헌을 먼저 읽고 AS-IS를 그 틀에 억지로 맞추지 않는다.

## Task -1.1. AS-IS Claim Ledger 생성

모든 AS-IS 문서에서 사실·추정·질문을 Claim 단위로 추출한다.

필수 필드:

| 필드 | 설명 |
|---|---|
| Claim ID | `ASIS-C###` |
| Source Alias | ASIS-01~04 |
| Original Evidence ID | 기존 Q-ID/E-ID가 있으면 유지 |
| Claim | 한 문장 사실 진술 |
| Evidence Status | Confirmed / Inferred / Unknown / Contradicted |
| Actor | 초병, 방문자, 내부 담당자 등 |
| Stage | 신청/승인/접근/확인/판단/집행/출영 |
| System/Device | RFID, LPR, 명단, 승인체계 등 |
| Decision Relevance | 이 정보가 어떤 판단에 쓰이는가 |
| Notes | 지역 한정성/추가질문 |

산출: `evidence/as_is_claim_ledger.csv`

## Task -1.2. Context Candidate 추출

AS-IS에서 반복 등장하는 판단정보를 아직 Ontology 객체로 확정하지 않고 `Context Candidate`로 추출한다.

초기 후보:
- Person
- ServiceMember
- Visitor
- Organization / Unit
- Credential
- AccessPermission
- AccessRequest / Visit
- Vehicle
- Driver / Occupant
- Item / Cargo
- Gate / Checkpoint
- Area / Zone
- Purpose
- Mission
- Escort
- TimeWindow
- Device / Sensor
- Observation
- Event
- Restriction / Alert
- Decision
- Action

각 Candidate에는 반드시 근거를 태깅한다.

상태 태그:
- `Confirmed-Local`
- `Derived`
- `Hypothesis`
- `Unknown`

산출: `evidence/context_candidates.csv`

## Task -1.3. Decision Requirement 추출

초병이 실제로 판단하는 질문을 자연어로 추출한다.

예:
- 이 사람은 승인된 사람과 동일한가?
- 현재 이 출입권한은 유효한가?
- 차량과 탑승자 정보는 승인내용과 일치하는가?
- 요구되는 인솔 조건이 충족되었는가?
- 정보가 불일치할 때 누구에게 확인해야 하는가?

산출: `evidence/decision_requirements.csv`

## Task -1.4. Unknown Backlog 정리

ASIS-02의 미확인 질문을 6장 연구에 필요한 질문과 현장 추가조사 질문으로 분리한다.

분류:
- External Research로 해결 가능
- Local Interview 필요
- System Documentation 필요
- 구현 단계로 이관
- 6장 범위 밖

산출: `evidence/unknown_backlog.csv`

### Phase -1 Definition of Done

- 모든 Primary AS-IS 입력자료를 읽음
- 중복 Claim 통합
- Context Candidate마다 최소 하나의 출처가 연결됨
- `Confirmed`와 `Hypothesis`가 혼재되지 않음
- Route, Mission 등 최근 아이디어가 현장 직접근거인지 파생개념인지 구분됨

### Gate -1

AS-IS 원자료가 누락되었거나, 핵심 Claim의 근거상태를 구분할 수 없으면 외부 연구로 넘어가지 말고 `README.md`에 Missing Input을 기록한다.

---

# 7. Phase 0. 연구 명제와 평가기준 고정

## Task 0.1

P1~P5를 Phase -1 결과에 맞게 수정한다.

## Task 0.2

6장이 답해야 할 최소 질문을 아래 4개로 압축한다.

1. 사람이 판단하는 정보는 무엇인가?
2. 그 정보는 어디에서 생성·관측되는가?
3. 기계가 읽을 수 있는 구조로 바꿀 수 있는가?
4. 바꾼 정보는 실제 출입판단에 충분히 유효한가?

## Task 0.3. 반증조건 고정

반드시 아래 반례를 적극 검색한다.

- 주요 판단정보가 대부분 암묵지이고 구조화 불가능
- 실제 군 기준상 핵심정보가 시스템에 존재하지 않음
- 센서 관측만으로 객체/상태를 신뢰성 있게 특정하기 어려움
- 동일 의미를 표현하는 기존 표준이 거의 없음
- 단순 관계형 DB + ABAC로 충분해 별도 semantic model이 과도함
- 군 특화 정책이 너무 지역적이어서 공통모델이 부적절함

산출: `README.md`의 `Research Propositions & Falsifiers`

---

# 8. Phase 1. 무인화/자율화를 위한 선결요건 연구

## 목적

출입통제를 떠나, 현실 세계에서 자율 시스템이 판단·행동하려면 어떤 정보요건이 필요한지 권위자료에서 귀납적으로 도출한다.

## 조사 관점

- Autonomous system reference architecture
- Situational awareness / world model
- Environment representation
- State estimation
- Digital thread / digital engineering
- Digital twin
- Semantic interoperability
- Machine-readable policy / constraints
- Identity / authorization / context-aware access
- Sensor-to-entity abstraction
- Event/time representation
- Human-machine teaming
- Exception / escalation
- Provenance / traceability

## 우선 자료원

1. DoD / DAF / NATO / 정부 공식 문서
2. NIST
3. ISO/IEC/IEEE/OMG/W3C/OASIS
4. 동료심사 논문
5. 공급업체 기술문서

## 검색어 예시

- `"autonomous systems" world model operational context`
- `DoD digital engineering authoritative source of truth model`
- `autonomous system environment representation state estimation`
- `semantic interoperability autonomous systems`
- `machine readable policy autonomous system`
- `digital twin operational context decision making`
- `human machine teaming exception escalation autonomy`

## 추출 필드

| Field | 설명 |
|---|---|
| Requirement | 선결요건 |
| Definition | 문헌 정의 |
| Why Needed | 자율판단과의 관계 |
| Source | 문서명 |
| Exact Section | 페이지/조항 |
| Access-Control Mapping | 출입통제에서의 대응정보 |
| Supports P1? | Yes/Partial/No |
| Evidence Grade | A~D |

## 산출물

`01_autonomy_prerequisites.md`  
`evidence/autonomy_prerequisite_matrix.csv`

### Definition of Done

- 선결요건 최소 5개 이상
- 각 선결요건에 권위 있는 출처 최소 1개
- 최소 3개 요건은 독립된 2개 출처로 교차검증
- "Ontology 필요"가 아니라 "정보요건"으로 서술

### Gate 1

machine-readable context/state/environment representation 필요성을 권위 자료로 지지하기 어렵다면 P1을 축소한다.

---

# 9. Phase 2. Digitization-to-Decision 구조 연구

## 목적

현실 사실이 기계 판단으로 이어지기까지 필요한 계층을 분리하고, 각 기술이 무엇을 해결하는지 정확히 구분한다.

## 분석 계층

1. **Digitization**: 종이·현장사실 → 디지털 값
2. **Connectivity**: API / Driver / Message Bus
3. **Data Integration**: ETL / Mapping
4. **Canonical/Common Data Model**
5. **Entity/Object Model**
6. **Relationship Model**
7. **State/Event/Time Model**
8. **Semantic Model / Ontology**
9. **Policy / Rule Representation**
10. **Reasoning / Context Derivation**
11. **Decision / Action**
12. **Human Escalation / Audit**

## 비교 대상

- API / REST / Message Bus
- Canonical Schema
- Relational Database
- Property Graph
- RDF / OWL
- Knowledge Graph
- Ontology
- Digital Twin
- ABAC / ReBAC
- XACML
- OPA / Policy Engine
- CEP / Complex Event Processing
- Rule Engine

## 핵심 질문

- 각 계층은 무엇을 해결하는가?
- 무엇을 해결하지 못하는가?
- 한 기술이 다른 기술을 대체하는가, 보완하는가?
- 현재 6장의 질문에는 어느 계층까지만 증명하면 충분한가?
- Ontology 없이도 Context Model이 가능한가?

## 산출물

`02_digitization_ladder.md`  
`evidence/technology_fit_matrix.csv`

### Gate 2

Canonical model + ABAC 또는 다른 단순 구조로 충분하다는 근거가 강하면 이를 명시한다. Ontology 필요성은 7~8장 연구로 넘기고 6장에서는 중립을 유지한다.

---

# 10. Phase 3. 민간·산업 출입통제 및 데이터 표준 Crosswalk

## 목적

출입통제 맥락이 이미 어떤 객체·속성·이벤트로 표준화되어 있는지 확인한다.

## 우선 조사 후보

### Identity / Facility Access
- NIST FIPS 201-3
- NIST SP 800-116 Rev.1
- FICAM/PACS 관련 문서
- NIST SP 800-162 ABAC

### Physical Security Interoperability
- ONVIF Profile A
- ONVIF Profile C
- ONVIF Profile M
- SIA OSDP / IEC 60839-11-5
- 기타 SIA integration standards

### Device / State / Information Model
- OPC UA Part 1/3/5/9/16 등
- OPC UA Companion Model 사례

### Policy / Semantic Representation
- OASIS XACML
- W3C RDF 1.1
- W3C OWL 2
- 필요 시 SHACL, PROV-O

### Security Architecture
- IEC 62443의 Zone/Conduit 개념은 직접 출입객체 표준이 아니라 구조화 관점 참고로만 사용

## Standard Coverage Matrix 대상 Concept

- Person / Identity
- Credential
- Organization / Role
- Access Permission
- Door / Gate / Checkpoint
- Area / Zone
- Vehicle
- License Plate
- Purpose
- Visit / Request
- Escort
- Item / Cargo
- Time / Schedule
- Device / Sensor
- Event / Observation
- Alarm / Restriction
- Policy
- Decision / Action
- Provenance / Audit

## 각 표준에서 추출할 필드

| Field | 설명 |
|---|---|
| Standard | 표준명 |
| Authority | 기관 |
| Version / Date | 최신 확인 |
| Concept | 대상 개념 |
| Native Term | 원문 용어 |
| Definition | 의미 |
| Attributes | 속성 |
| Relationships | 관계 |
| Event/State | 동적 표현 |
| Access Relevance | 출입판단 관련성 |
| Exact Clause | 조항/페이지 |
| URL | 공식 링크 |
| Evidence Grade | A~D |

## 산출물

`03_standards_landscape.md`  
`evidence/standards_coverage_matrix.csv`

### Gate 3

핵심 Context의 대부분이 어느 표준에도 매핑되지 않으면 "기존 표준으로 충분히 표현 가능"이라는 표현을 축소하고 "부분 재사용 + 군 특화 확장 필요"로 수정한다.

---

# 11. Phase 4. 군/DoD/공군 공개 기준 Crosswalk

## 목적

민간 표준에서 확보한 개념을 실제 군 출입통제의 판단정보에 맞춰 재정렬한다.

## 우선 조사 대상

- UFC 4-022-01 Entry Control Facilities / Access Control Points
- NTTP 3-26.3 Physical Security (공개 가능한 최신본)
- DoD ePACS / DBIDS 공개 자료
- DoD installation access / physical security / identity credentialing 관련 공개 지침
- FICAM/PIV/PACS 연계
- Army/Navy/USMC automated gate 사례
- DoD IG / GAO의 출입통제·credential 관련 평가
- 공개된 DAFI/AFMAN/AFI 중 installation access, physical security, integrated defense 관련 문서
- 한국 공군 공개자료가 확인되는 경우만 별도 사용

## 군 Context 추출 필드

- 판단 대상
- Identity
- Fitness / Eligibility
- Purpose
- Authorization
- Credential
- Vehicle
- Occupant
- Item / Cargo
- Time
- Area
- Visit / Mission
- Escort
- Alert / Threat Condition
- Equipment State
- Field Observation
- Decision
- Action
- Exception / Manual Verification

## 데이터화 상태 분류

각 항목을 아래 중 하나로 분류한다.

- `A. Existing Digital System`
- `B. Sensor-Digitizable`
- `C. Document/Workflow Structurable`
- `D. Primarily Human/Implicit`
- `E. Unknown from Public Sources`

## Crosswalk 규칙

`AS-IS Local Term → Generic Concept → Civil Standard → DoD/Military Term → Modeling Decision`

예:

```text
"방문 승인"
→ Authorization / Visit
→ ABAC / PACS permission concepts
→ military visitor/sponsor approval concepts
→ AccessRequest + Authorization
```

## 산출물

`04_military_crosswalk.md`  
`evidence/military_access_context_matrix.csv`  
`evidence/military_to_standard_crosswalk.csv`

### Gate 4

공개 공군 자료가 부족하면 DoD/미군 자료를 `Higher-level / Analogue Evidence`로 표시하고 한국 공군 적용은 `Needs Local Validation`으로 남긴다. 비공개 규정을 추정하지 않는다.

---

# 12. Phase 5. Air Force Access Context Model v0.1

## 목적

앞 단계의 근거만 사용해 공군 출입판단에 필요한 최소 Context Model을 만든다.

## 12.1 Concept Status

각 개념은 반드시 아래 중 하나로 태깅한다.

- `Core`: 다수 표준/군 기준에서 공통 확인
- `Military Extension`: 군 임무/운영 특성 때문에 추가
- `Local`: 현장 인터뷰에서만 확인
- `Hypothesis`: 아직 검증되지 않은 설계 후보

## 12.2 최소 객체 후보

- Person
- ServiceMember / Employee / Visitor
- Organization / Unit
- Credential
- AccessPermission
- AccessRequest / Visit
- Vehicle
- Driver / Occupant
- Item / Cargo
- Area / Zone
- Gate / Checkpoint
- Device / Sensor
- Observation / Event
- TimeWindow
- Purpose / Mission
- Escort
- Alert / Restriction
- Decision
- Action

후보를 그대로 채택하지 말고 근거가 확인된 것만 모델에 넣는다.

## 12.3 객체별 필수 필드

| Field | 설명 |
|---|---|
| Concept ID | `CTX-###` |
| Name | 개념명 |
| Status | Core/Military Extension/Local/Hypothesis |
| Definition | 한 문장 정의 |
| Source Standard/Doctrine | 근거 |
| Identifier / Key | 식별 방식 |
| Core Attributes | 주요 속성 |
| Relationships | 관계 |
| Dynamic States | 상태 |
| Source System/Sensor | 생성원 |
| Temporal Validity | 시간 유효성 |
| Update Frequency | 업데이트 특성 |
| Confidence | 신뢰도 |
| Provenance | 데이터 출처 |
| Security/Privacy Concern | 보안/개인정보 |
| Decision Relevance | 어떤 판단에 필요한가 |

## 12.4 관계 모델 규칙

예:
- `Person hasCredential Credential`
- `Person assignedTo Organization`
- `Person drives Vehicle`
- `Vehicle hasOccupant Person`
- `AccessRequest hasPurpose Purpose`
- `AccessPermission authorizes Subject/Vehicle/Area`
- `Escort accompanies Visitor`
- `Observation observedBy Sensor`
- `Event occursAt Area`
- `Decision resultsIn Action`

관계에도 동일하게 근거와 상태태그를 부여한다.

## 산출물

`05_airforce_context_model.md`  
`evidence/object_evidence.csv`  
`evidence/relationship_evidence.csv`  
`diagrams/context_model.mmd`

### Gate 5

핵심 객체/관계의 출처를 추적할 수 없다면 모델에 Core로 포함하지 않는다.

---

# 13. Phase 6. 가능성(Feasibility)과 타당성(Validity) 평가

## 원칙

**데이터가 존재한다 = 자동판단이 가능하다**가 아니다.

평가는 반드시 두 축을 분리한다.

## 13.1 Feasibility

"필요정보를 기계가 읽을 수 있는 형태로 취득·구조화할 수 있는가?"

평가 항목:
- Data Availability
- Observability
- Digitizability
- Identifier Availability
- Interface/Interoperability
- Update/Temporal Availability
- Provenance Availability

## 13.2 Validity

"그 정보가 실제 출입판단에 의미 있고, 군 기준과 일치하며, 정책판단에 충분한가?"

평가 항목:
- Decision Relevance
- Semantic Precision
- Policy Expressiveness
- Context/Temporal Sufficiency
- Reliability / Confidence
- Auditability
- Military/Standard Alignment

## 13.3 구현 제약

별도 항목:
- Security / Classification
- Privacy
- Integration Burden
- Sensor Dependence
- Legacy Constraints
- Human Exception Requirement

## 13.4 점수 Rubric

근거 없는 숫자 사용 금지. 아래 0~3을 먼저 정의한 뒤 적용한다.

### Feasibility 0~3
- 0: 공개 근거상 취득/구조화 경로 없음
- 1: 이론적 가능, 실제 출처/인터페이스 불명확
- 2: 데이터 원천 또는 표준화 방법 존재, 현장 검증 필요
- 3: 실제 시스템/센서/표준에서 직접 확인 가능

### Validity 0~3
- 0: 판단 관련성 근거 없음
- 1: 간접 관련
- 2: 실제 출입/정책 판단에 사용됨이 확인
- 3: 군/정부 기준과 현장근거가 함께 일치

### Evidence Grade
- A: 정부/군/표준기관의 직접 규정·정의
- B: 공식 기술문서 또는 다수 동료심사 근거
- C: 벤더 기술자료/단일 외부 사례
- L: Local Evidence(현장 인터뷰/내부 조사)
- D: 추정/설계 가설

## 산출물

`06_feasibility_validity.md`  
`evidence/feasibility_validity_scorecard.csv`

### Gate 6

핵심 판단정보 상당수가 0~1 수준이면 CLEAR의 자동화 범위를 정상/저위험·정형 상황으로 축소하고 Human-in-the-loop 전제를 강화한다.

---

# 14. Phase 7. Slide 6 Evidence Pack

## 목적

전체 연구를 발표 1장과 40~60초 설명으로 압축한다.

## 14.1 장표가 답해야 할 질문

> **"초병이 보는 기지의 맥락을 정말 기계가 읽을 수 있게 만들 수 있는가?"**

## 14.2 권장 논리

```text
무인 판단의 선결요건
→ 현실 Context의 machine-readable representation
→ 기존 산업/정부/군 표준에 핵심 개념 존재
→ 현장 AS-IS Context와 Crosswalk
→ 공군 Context Model로 구조화 가능
→ 일부 예외/암묵지는 인간 확인 유지
→ 다음 질문: 이 이종 Context를 어떤 공통 의미체계로 연결할 것인가?
```

## 14.3 장표 후보 구조

### 왼쪽 - 사람이 보는 현실
- 사람
- 차량
- 승인
- 자격
- 목적
- 시간
- 구역
- 인솔
- 장비/센서 상태
- 현장 이벤트

### 중앙 - 디지털 근거
- 현장 AS-IS
- NIST/FICAM
- ONVIF/SIA
- OPC UA
- DoD/UFC/군 출입기준

### 오른쪽 - Machine-readable Context
- Person
- Credential
- Vehicle
- Permission
- Visit/Purpose
- Area
- Gate
- Event
- TimeWindow
- Restriction
- Decision

### 하단 결론
연구 결과가 지지하는 범위에서만 아래와 같은 결론을 사용한다.

> **"출입 판단에 필요한 주요 맥락은 기존 시스템·센서·표준으로 상당 부분 디지털 표현이 가능하며, 군 특화 의미와 관계를 추가 정의하면 공통 Context Model로 구조화할 수 있다."**

## 14.4 Evidence Pack 필수 구성

`07_slide6_evidence_pack.md`에는 다음을 포함한다.

1. 한 줄 주장
2. 3~5개 핵심 근거
3. 각 근거의 출처/페이지/조항
4. Context Model 도식 데이터
5. 40~60초 발표 대본
6. 예상 반론 5개
7. 반론별 근거 있는 답변
8. 장표에서 사용하면 안 되는 과장표현
9. 다음 7장으로 연결하는 Transition 문장

---

# 15. Evidence 관리 규칙

## 15.1 Evidence Ledger 필드

`evidence/evidence_ledger.csv`

- Claim ID
- Claim
- Research Phase
- Source Title
- Source Organization
- Source Type
- Authority Level
- Publication Date
- Version
- Exact Quote (최대 25단어)
- Page / Section
- URL
- Interpretation
- Supports / Contradicts
- Scope
- Evidence Grade
- Confidence
- Notes

## 15.2 Source Catalog 필드

`evidence/source_catalog.csv`

- Source ID
- Title
- Organization
- Document Type
- Date
- Version
- Official URL
- Access Date
- Primary/Secondary
- Relevant Phase
- Key Sections
- Reliability Notes

## 15.3 인용 원칙

- 핵심 주장마다 최소 1개 authoritative source
- 가능하면 서로 독립적인 2개 출처
- 마케팅 페이지는 공식 규격/기술문서로 교차검증
- PDF는 정확한 페이지/조항 기록
- 오래된 표준은 최신 상태/후속버전 확인
- 기존 내부 리서치의 2차 인용을 그대로 재사용하지 말고 원출처 확인
- 동일 기관의 여러 문서는 독립 교차검증으로 과대평가하지 않음

---

# 16. 반례 및 대안 탐색 프로토콜

Codex는 CLEAR 가설을 지지하는 자료만 찾지 않는다.

각 Phase마다 최소 1개의 `Contradiction Search`를 실행한다.

필수 반례 질문:

1. 실제 자동화에 semantic model이 필요하지 않은 사례가 있는가?
2. ABAC/PACS만으로 Context 판단을 충분히 수행하는가?
3. 현장 암묵지를 정형화할 수 없는 대표 사례는 무엇인가?
4. 데이터가 디지털이어도 정책 모호성 때문에 자동판단할 수 없는 경우는?
5. 객체화는 가능하지만 실시간성이 없어 사용할 수 없는 경우는?
6. 군 보안/개인정보 규정이 데이터 통합을 제한하는가?
7. 동일 정보를 여러 체계가 서로 다르게 관리할 때 authoritative source를 어떻게 정하는가?

반례는 `Supports/Contradicts` 필드에 반드시 기록한다.

---

# 17. 보안·민감정보 취급 지침

## 금지

- 실제 한국 공군 기지의 취약한 Gate/경로/배치 정보
- 비공개 시스템 명칭·구성·IP·계정·권한구조
- 상세 경계 절차 우회 방법
- 센서 탐지 회피 방법
- 취약점 악용 절차
- 비공개 군 규정의 추정 복원

## 허용

- 공개된 일반화된 출입통제 개념
- 공개 표준/교범
- 익명화된 Local Evidence
- 객체·관계의 추상 모델
- 공개적으로 알려진 일반 센서·PACS 구조

민감 가능성이 있는 Local Evidence는 문서에 원문을 반복하지 말고 `Local Evidence ID`로 참조한다.

---

# 18. 권장 GitHub Repository 구조

```text
/research/06_context_digitization/
├── README.md
├── inputs/
│   ├── README.md
│   ├── as_is/
│   │   ├── ASIS-01_lifecycle_as_is.md
│   │   ├── ASIS-02_phase2_investigation_checklist.xlsx
│   │   ├── ASIS-03_sentinel_task_model.md
│   │   └── ASIS-04_as_is_research_protocol.md
│   └── prior_research/
│       ├── REF-01_military_gate_autonomy.md
│       ├── REF-02_physical_security_landscape.md
│       └── META-01_bottleneck_semantic_research.md
├── evidence/
│   ├── as_is_claim_ledger.csv
│   ├── context_candidates.csv
│   ├── decision_requirements.csv
│   ├── unknown_backlog.csv
│   ├── autonomy_prerequisite_matrix.csv
│   ├── technology_fit_matrix.csv
│   ├── standards_coverage_matrix.csv
│   ├── military_access_context_matrix.csv
│   ├── military_to_standard_crosswalk.csv
│   ├── object_evidence.csv
│   ├── relationship_evidence.csv
│   ├── feasibility_validity_scorecard.csv
│   ├── evidence_ledger.csv
│   └── source_catalog.csv
├── diagrams/
│   └── context_model.mmd
├── 01_autonomy_prerequisites.md
├── 02_digitization_ladder.md
├── 03_standards_landscape.md
├── 04_military_crosswalk.md
├── 05_airforce_context_model.md
├── 06_feasibility_validity.md
├── 07_slide6_evidence_pack.md
└── FINAL_REPORT.md
```

---

# 19. 파일별 Definition of Done

## `README.md`
- 연구 질문/명제
- Scope/Out-of-scope
- 입력자료 manifest
- 현재 Phase
- Stage Gate 결과
- Open Questions
- 완료상태

## `01_autonomy_prerequisites.md`
- 최소 5개 선결요건
- 권위근거
- 출입통제 대응관계
- 반례 포함

## `02_digitization_ladder.md`
- Digitization→Decision 단계
- 각 기술 역할
- 경쟁/보완 관계
- Ontology 중립

## `03_standards_landscape.md`
- 5개 이상 핵심 표준군
- Concept Coverage Matrix
- 정확한 조항/페이지

## `04_military_crosswalk.md`
- 군 출입판단 정보범주
- AS-IS↔군 기준↔민간표준 Crosswalk
- 공개자료 한계 명시

## `05_airforce_context_model.md`
- Core/Extension/Local/Hypothesis 구분
- 객체/관계 근거
- Mermaid 그래프

## `06_feasibility_validity.md`
- Feasibility/Validity 분리
- Rubric 적용
- 미해결 영역
- 결론 confidence

## `07_slide6_evidence_pack.md`
- 1장 장표 논리
- 핵심 근거 3~5개
- 40~60초 대본
- 반론/답변
- Transition

## `FINAL_REPORT.md`
- 전체 연구의 논증
- 반례 포함
- 발표용 결론과 기획서용 상세결론 분리
- 남은 현장 검증 과제

---

# 20. Codex 실행 순서

아래 순서를 변경하지 않는다.

- [ ] 1. `inputs/README.md` 작성 및 파일 Alias 확인
- [ ] 2. ASIS-01~04 전체 읽기
- [ ] 3. `as_is_claim_ledger.csv` 작성
- [ ] 4. `context_candidates.csv` 작성
- [ ] 5. `decision_requirements.csv` 작성
- [ ] 6. `unknown_backlog.csv` 작성
- [ ] 7. Phase -1 Gate 통과 여부 기록
- [ ] 8. P1~P5 재검토
- [ ] 9. Phase 1 선결요건 조사
- [ ] 10. Phase 2 Digitization-to-Decision 조사
- [ ] 11. Phase 3 민간/산업 표준 Crosswalk
- [ ] 12. Phase 4 군/DoD/공군 Crosswalk
- [ ] 13. Phase 5 Context Model v0.1
- [ ] 14. Phase 6 Feasibility/Validity 평가
- [ ] 15. 반례 재검색
- [ ] 16. `FINAL_REPORT.md` 작성
- [ ] 17. `07_slide6_evidence_pack.md` 작성
- [ ] 18. 모든 Claim의 Source ID 추적 가능 여부 검사
- [ ] 19. 과장표현 제거
- [ ] 20. Open Questions와 Local Validation 필요항목 정리

---

# 21. 최종 연구보고서 목차

`FINAL_REPORT.md`

1. Executive Conclusion
2. 연구 질문과 범위
3. 기존 AS-IS Evidence Summary
4. 초병 판단에 필요한 Context
5. 무인화/자율화 선결요건
6. 현실 Context의 디지털화 단계
7. 민간·산업 표준 분석
8. 군/DoD 출입통제 기준 분석
9. AS-IS ↔ 표준 ↔ 군 기준 Crosswalk
10. Air Force Access Context Model v0.1
11. Feasibility Analysis
12. Validity Analysis
13. 자동화 가능한 영역 / 인간 개입이 필요한 영역
14. 강한 반례와 한계
15. 6장 발표 결론
16. 7장으로 넘길 기술 질문
17. 추가 현장조사 Backlog
18. 참고문헌

---

# 22. 6장 발표에서 사용할 수 있는 결론의 강도

연구 결과에 따라 문장을 아래 단계 중 하나로 선택한다.

### Level 1 - 약한 결론
> 주요 출입판단 정보 중 일부는 기존 시스템과 센서를 통해 디지털화할 수 있다.

### Level 2 - 중간 결론
> 정상 출입판단에 필요한 핵심 정보의 상당 부분은 기존 시스템·센서·표준을 통해 구조화할 수 있다.

### Level 3 - 강한 결론
> 핵심 출입판단 Context의 대부분은 기존 데이터와 공개 표준을 기반으로 객체·관계·상태로 표현 가능하며, 군 특화 확장을 통해 공통 Context Model로 구성할 수 있다.

**Level 3는 Coverage 및 Validity 근거가 충분할 때만 사용한다.**

---

# 23. 완료 판정 기준

연구는 아래 조건을 모두 충족해야 완료로 본다.

1. AS-IS Claim 100%에 Source Alias가 존재한다.
2. 핵심 Context Candidate마다 Evidence Status가 존재한다.
3. 최소 5개 권위 있는 표준/정부문서를 직접 검토했다.
4. 핵심 주장 5개 이상이 정확한 조항/페이지로 추적 가능하다.
5. 민간 표준과 군 기준을 Crosswalk했다.
6. Air Force Context Model의 Core 객체는 모두 근거가 있다.
7. Feasibility와 Validity가 분리되어 평가됐다.
8. 반례/한계가 별도 장으로 포함됐다.
9. Local Evidence를 공군 전체의 사실로 일반화하지 않았다.
10. Ontology 필요성을 6장의 결론으로 미리 확정하지 않았다.
11. 발표용 1장과 기획서용 상세보고서가 모두 생성됐다.
12. 남은 질문이 `unknown_backlog.csv`에 남아 있다.

---

# 24. 연구 리스크와 Fallback

## R1. 공군 공개자료 부족
**Fallback:** DoD 상위기준 + Army/Navy 공개사례를 사용하고 `Needs Local Validation`으로 표시.

## R2. 표준이 서로 다른 Concept을 사용
**Fallback:** 직접 동일시하지 말고 `Equivalent / Related / Partial / No Match`로 Crosswalk.

## R3. 특정 데이터의 실제 시스템 존재 여부 확인 불가
**Fallback:** `Structurable in principle`과 `Currently available`을 구분.

## R4. Ontology 없이 충분해 보임
**Fallback:** 결과를 숨기지 않는다. 7~8장 기술선택 단계에서 재검토하도록 명시.

## R5. AS-IS 단일 인터뷰의 일반화 위험
**Fallback:** Local Evidence로 유지하고 외부 군 기준과 비교. 핵심 차이가 있으면 후속 인터뷰 질문 생성.

## R6. Route/Mission 같은 대표사례가 현장 직접근거 부족
**Fallback:** `Hypothesis / Extended Use Case`로 분리하고 기본 6장 증명에는 사용하지 않는다.

---

# 25. 기본 리서치에서 우선 확인할 Authoritative Source 후보

아래는 **연구 시작점 후보**이며, Codex는 최신 버전·적용범위·원문 조항을 다시 확인해야 한다.

## Identity / Physical Access

1. **NIST FIPS 201-3 - Personal Identity Verification (PIV) of Federal Employees and Contractors**  
   https://csrc.nist.gov/pubs/fips/201-3/final  
   - 신원 credential 및 연방시설 접근 인증의 기준선.

2. **NIST SP 800-116 Rev.1 - Guidelines for the Use of PIV Credentials in Facility Access**  
   https://csrc.nist.gov/pubs/sp/800/116/r1/final  
   - PIV와 PACS의 위험기반 시설접근 적용.

3. **NIST SP 800-162 - Guide to Attribute Based Access Control (ABAC)**  
   https://csrc.nist.gov/pubs/sp/800/162/upd2/final  
   - Subject/Object/Environment Attribute와 Policy를 통한 상황별 접근판정 구조.

## Physical Security Interoperability

4. **ONVIF Profile A**  
   https://www.onvif.org/profiles/onvif-profile-a/  
   - Access rule, credential, schedule, access-control event.

5. **ONVIF Profile C**  
   https://www.onvif.org/profiles/onvif-profile-c/  
   - Door control, site information, event/alarm management.

6. **ONVIF Profile M**  
   https://www.onvif.org/profiles/profile-m/  
   - Vehicle, license plate, human, geolocation 등 analytics metadata/event.

7. **SIA Open Supervised Device Protocol (OSDP)**  
   https://www.securityindustry.org/industry-standards/open-supervised-device-protocol/  
   - Access-control controller와 reader/peripheral 간 상호운용, IEC 60839-11-5 연계.

## Information / Object / Event Modeling

8. **OPC UA Part 1 - Overview and Concepts**  
   https://reference.opcfoundation.org/specs/OPC-10000-1/  
   - Object, Node, Reference 기반 정보모델의 개념.

9. **OPC UA Part 5 - Information Model**  
   https://reference.opcfoundation.org/specs/OPC-10000-5/  
   - 표준화된 정보모델 구조.

10. **OPC UA Modelling Best Practices**  
    https://reference.opcfoundation.org/specs/OPC-11030/full  
    - 실제 Information Model 설계·버전관리 관점.

## Semantic / Policy Representation

11. **W3C RDF 1.1 Concepts and Abstract Syntax**  
    https://www.w3.org/TR/rdf-concepts/  
    - Subject-Predicate-Object 형태의 graph representation.

12. **OASIS XACML 3.0**  
    https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html  
    - 속성·정책 기반 접근통제 의사결정 구조.

## DoD / Military

13. **UFC 4-022-01 - Entry Control Facilities / Access Control Points**  
    - WBDG/UFC 공식 저장소에서 최신본 확인.
    - 차량·인원 출입시설 설계 및 자동화/운영 기준 확인.

14. **DoD Data Strategy / 후속 Data, Analytics & AI 정책**  
    - DoD CIO 공식 저장소에서 최신본 확인.
    - 데이터의 표준화·가용성·상호운용성·AI 활용 조건 확인.

15. **NTTP 3-26.3 Physical Security**  
    - 공개 가능한 최신판과 정확한 배포상태 확인.
    - Identity/Fitness/Purpose, ePACS/DBIDS, 수동확인/예외처리 근거 확인.

16. **DAF/AFI/DAFI 공개 Installation Access / Integrated Defense 자료**  
    - Air Force e-Publishing에서 최신 문서 검색.
    - 문서가 직접 출입통제 기준인지 반드시 검증 후 사용.

---

# 26. Codex에게 주는 최종 실행 원칙

1. **현장 → 외부표준 순서로 연구한다.**
2. **결론을 먼저 정하지 않는다.**
3. **Ontology는 6장의 결론이 아니다.**
4. **데이터 존재와 자동판단 가능성을 구분한다.**
5. **민간 표준과 군 기준을 같은 수준의 근거로 취급하지 않는다.**
6. **Local Evidence는 Local로 남긴다.**
7. **근거 없는 숫자와 자동화율을 만들지 않는다.**
8. **반례를 숨기지 않는다.**
9. **모든 핵심 Claim은 Source ID로 역추적 가능해야 한다.**
10. **최종 산출물은 발표 논리와 수정 기획서에 바로 삽입 가능한 형태여야 한다.**

---

# 27. 최종 성공조건

Codex의 최종 연구를 읽은 제3자가 다음 질문에 차례대로 답할 수 있으면 성공이다.

> 1. 초병은 실제로 어떤 정보를 보고 판단하는가?  
> 2. 무인 시스템이 왜 그런 Context를 필요로 하는가?  
> 3. 그 정보는 현실에서 어디에서 생성되는가?  
> 4. 기존 표준은 이를 어떻게 표현하고 있는가?  
> 5. 군 출입통제 기준과 어떻게 대응되는가?  
> 6. 공군 도메인에서 어떤 객체·관계·상태로 모델링할 수 있는가?  
> 7. 어떤 부분은 실제로 디지털화 가능하고, 어떤 부분은 아직 인간에게 남는가?  
> 8. 따라서 발표 6장에서 어디까지 자신 있게 주장할 수 있는가?  
> 9. 그리고 다음 장에서 왜 '이렇게 디지털화된 Context를 어떻게 연결·해석할 것인가'라는 기술 질문으로 넘어가야 하는가?

이 질문에 근거와 출처를 갖춘 상태로 답할 수 있을 때 6장 리서치를 종료한다.
