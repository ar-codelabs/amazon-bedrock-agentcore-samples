# Samsung Electronics × AWS — AgentCore 전환 프로젝트 딜리버리 로그

> 삼성전자 TV Apps Service의 LangGraph 기반 자연어 질의 에이전트를 Amazon Bedrock AgentCore 기반 프로덕션 환경으로 전환하는 프로젝트의 고객 전달 자산(deliverables)을 정리한 문서입니다.
>
> 본 repo에는 AgentCore tutorial 및 참고 코드가 함께 포함되어 있으니 참고 바랍니다.

---

## 목차

1. [프로젝트 개요](#1-프로젝트-개요)
2. [Sprint 일정](#2-sprint-일정)
3. [Text2SQL 고도화 전략](#3-text2sql-고도화-전략)
4. [AgentCore Runtime & Gateway 가이드](#4-agentcore-runtime--gateway-가이드)
5. [구축 현황](#5-구축-현황)
6. [발표 구성 및 인사이트](#6-발표-구성-및-인사이트)
7. [데모 시나리오](#7-데모-시나리오)
8. [AgentCore Policy 활용 방안](#8-agentcore-policy-활용-방안)
9. [AgentCore Observability 이슈 및 해결](#9-agentcore-observability-이슈-및-해결)
10. [참고 자료 링크 모음](#10-참고-자료-링크-모음)

---

## 1. 프로젝트 개요

| 항목 | 내용 |
|------|------|
| 목표 | 운영 중인 LangGraph 멀티 에이전트를 Amazon Bedrock AgentCore 기반 프로덕션 환경으로 전환 |
| 대상 사용자 | PM / Developer / Operator 약 300명 |
| 데이터소스 | Oracle (STG/PRD), MySQL DB(API), BigQuery(KPI), Athena(KPI) |
| 에이전트 구조 | Supervisor 패턴 + Sub-Agent (KPI · 앱 지원 · 앱 검색) |

> Amazon Bedrock AgentCore를 활용하여 LangGraph 멀티 에이전트를 프로덕션 환경에 배포한 실전 사례를 공유합니다. AgentCore Runtime에서 Supervisor 패턴의 멀티 에이전트를 실행하고, MCP(Model Context Protocol)를 통해 내부 API 등 외부 도구를 표준화된 방식으로 연결합니다. Gateway로 MCP 서버를 중앙 관리하고 에이전트 트래픽을 제어하며, Policy & Identity로 자연어 기반 접근 제어와 Okta IdP 연동을 구현한 과정을 다룹니다. 또한 OpenTelemetry 기반 Observability로 Sub-Agent별 계층적 트레이싱을 구성하고, Evaluation을 CI 파이프라인에 통합하여 에이전트 품질을 자동으로 검증하는 방법을 소개합니다.

---

## 2. Sprint 일정

| Sprint | 일정 | 주제 |
|--------|------|------|
| 1주 | 3/27 (금) | AgentCore — Runtime, Gateway |
| 2주 | 4/2 (목) | AgentCore — Memory, Observability, Evaluation |
| 3주 | 4/10 (금) | AgentCore — Identity, Policy |
| 4주 | 4/17 (금) | 최종 검증 |

---

## 3. Text2SQL 고도화 전략

### 3.1 High Accuracy Text2SQL System (AIML Specialist 문곤수)

AIML Specialist가 작성한 Text2SQL 고도화 전략 방안 요약입니다.
(문서: `260303_text2sql_rag_ontology_architecture_v2.0_moongonsoo.pdf`)

- **3-Tier 온톨로지 RAG**: 스키마 메타(BM25 중심) / 비즈니스 규칙(Vector 중심) / 검증 쿼리(균형)를 Tier별 가중치 하이브리드 검색으로 LLM에 맥락 주입
- **Domain-First 라우팅**: 경량 LLM으로 도메인 분류 → 검색 범위 축소 → Schema Linking 기반 Direct / Clarify / Decompose 3-경로 분기
- **Clarify Loop**: 모호한 질의 감지 시 어휘적/범위/참조 유형별 선택지를 사용자에게 제시하여 능동적 해소
- **4-Level 검증**: AST 구문 → 스키마 일치 → DB 실행 → 역번역(SQL→자연어 의도 비교) 순차 검증, 실패 시 자동 재생성
- **Thumbs Up Template 캐싱**: SQL을 파라미터 템플릿으로 추상화 → 사용자 승인 쿼리만 캐시 → 이중 검증(의미 유사도 + 템플릿 구조) 후 값 바인딩 반환
- **Flywheel 선순환**: 사용 증가 → 캐시 축적 + Clarify 패턴의 규칙 승격 → 정확도 향상 → 사용 증가

### 3.2 AWS 고객 사례 — IGAWorks AI 에이전트 '클레어'

2025 AWS Industry Week 발표 "Text2SQL로 완성한 데이터 분석 에이전트" 관련 블로그입니다. IGAWorks가 Amazon Bedrock 기반으로 개발한 '클레어'는 SQL 지식이 없는 마케터도 자연어로 복잡한 데이터 분석을 수행할 수 있게 합니다.

- 1부 (기획 배경 · 전반 아키텍처): https://aws.amazon.com/ko/blogs/tech/iganetworks-text2sql-agent-with-bedrock-1/
- 2부 (멀티 에이전트 구조 · RAG 상세 설계 · LLM 프롬프트 · 성능 관리): https://aws.amazon.com/ko/blogs/tech/iganetworks-text2sql-agent-with-bedrock-2/

> 자연어 질문의 모호함 분석, 스키마 및 샘플 쿼리 기반 쿼리 생성 가이드, 데이터 격리 방안, 데이터 시각화 등 실무 방법론 참고.

### 3.3 Text2SQL Optimization 문서 (SA 이혜원)

Text2SQL 최적화 관련 SA 이혜원 작성 문서 별도 전달 완료.

---

## 4. AgentCore Runtime & Gateway 가이드

### 4.1 가이드 문서

- AgentCore Runtime / Gateway 가이드 PDF 전달 완료.

### 4.2 AgentCore 코드 참고

- Runtime 코드: https://github.com/kyopark2014/mcp-runtime
- 대한항공 Agentic AI PoC 코드: https://github.com/aws-samples/sample-agentic-ai-platform-with-agentcore

---

## 5. 구축 현황

| 구성요소 | 현황 |
|---------|------|
| **Runtime** | Cognito 인증 기반 구성 완료 |
| **Gateway** | MCP target 3개 구성, user 질문 내용 기반 동적 라우팅 |
| **접근 제어** | 검증계/운영계 user 레벨 접근 제어는 현재 요건 없음으로 확인 |
| **Memory** | Short-Term Memory 사용 |
| **멀티 데이터소스** | Oracle STG(서울), Oracle PRD(버지니아), BigQuery(KPI) |
| **향후 계획** | Superset DB → S3 이관 후 Glue + Athena 쿼리 예정 |

---

## 6. 발표 구성 및 인사이트

### 6.1 경험 소개
- 운영 중인 LangGraph → AgentCore 전환 완료 (마이그레이션 순서, 기간, 코드 변경량, 레슨런 공유)
- LangGraph + AgentCore Gateway + MCP + BigQuery(GCP) + AWS DB — 멀티클라우드 + 멀티DB를 Gateway 하나로 추상화한 사례

### 6.2 Gateway
- Gateway 단일 endpoint 구조
- 새 데이터소스 추가 시 Agent 코드 변경 없이 target 등록만으로 즉시 반영
- Text2SQL AS-IS vs TO-BE 비교
- Gateway 시맨틱 검색 활성화

### 6.3 Observability + Evaluation CI
- AS-IS vs TO-BE Observability 비교: LangGraph(블랙박스) vs AgentCore(모든 trace 가시화), Tool 호출 병목 찾는 과정 시연
- Evaluation CI 실패 → 배포 차단: Text2SQL 정확도 낮으면 CI가 자동 Evaluation 후 배포 차단

### 6.4 추가 아이디어
- **Runtime**: 스케일링/컨테이너/가용성 관리형 전환
- **Memory**: 멀티턴 vs 싱글턴 비교
- **Identity + Policy**: Cognito 인증, Cedar 기반 세밀한 접근 제어

---

## 7. 데모 시나리오

1. **Query 고도화** — Text2SQL AS-IS vs TO-BE
2. **멀티 데이터소스 크로스 쿼리**

> 구체적 시나리오는 추가 정리하여 공유 예정. 추가 데모 아이디어 수렴 중.

---

## 8. AgentCore Policy 활용 방안

> 미팅에서 논의한 대로, 고객 use-case에 필요 없는 기능이면 제외해도 무방합니다.

**참고 튜토리얼** (AIML Specialist 문곤수): https://github.com/gonsoomoon-ml/amazon-bedrock-agentcore-policy-tutorials

### 활용 방안

- **MCP Tool read-only 강제** — "`get_*`으로 시작하는 Tool만 허용, insert/update/delete 관련 Tool 차단". 나중에 누군가 실수로 write Tool을 추가해도 Policy가 차단.
- **특정 테이블/데이터 접근 제한** — "`app_master` 테이블은 허용, 개인정보가 있는 `user_info` 테이블은 차단"
- **호출 빈도 제한** — "동일 사용자가 1분에 10회 이상 Tool 호출 시 차단" (운영 챗봇의 비정상 호출 방지)
- **향후 user 구분 확장 대비** — Cedar로 작성해두면, 나중에 Cognito user 속성(role, department)을 조건으로 추가할 때 코드 변경 없이 정책 파일만 수정하면 됨

### 인증 → 인가 → 실행 흐름

1. **인증** — Amazon Cognito로 사용자 확인 및 JWT 토큰 발급
2. **인가** — Cedar 정책 언어로 "이 사용자가 이 작업을 할 수 있는가?" 판단
3. **실행** — 권한이 있을 때만 실제 도구(Lambda 또는 MCP 서버) 실행

---

## 9. AgentCore Observability 이슈 및 해결

### 9.1 Evaluation 관련 파싱 에러

- AWS supported frameworks에는 `opentelemetry-` / `openinference-` 두 가지 instrumentation 방식이 있습니다.
- `opentelemetry-instrumentation-langchain`은 버전에 따라 lc 포맷을 **attributes**에 넣는 버전과 **events body**에 넣는 버전이 있습니다. (참고: [Download span logs 문서](https://docs.aws.amazon.com/ko_kr/bedrock-agentcore/latest/devguide/getting-started-on-demand.html#download-span-logs))
- **해결**: `opentelemetry-instrumentation-langchain` 최신 버전으로 설치하거나, `openinference-instrumentation-langchain`으로 변경.
- **검증 완료**: `openinference-instrumentation-langchain`으로 변경하여 테스트한 결과 파싱이 정상 동작함을 확인.

### 9.2 Span duration 지표

- 콘솔에 표시되는 duration은 **OpenTelemetry 표준 Span duration 지표**이며, **마이크로초(μs) 단위**로 표시됩니다.

---

## 10. 참고 자료 링크 모음

### AgentCore 튜토리얼 시리즈 (영상 + 블로그)
- AgentCore Runtime
- Code Interpreter & Browser
- Identity
- Memory
- Gateway
- Observability

### 코드 저장소
- AgentCore Runtime 코드: https://github.com/kyopark2014/mcp-runtime
- 대한항공 Agentic AI PoC: https://github.com/aws-samples/sample-agentic-ai-platform-with-agentcore
- AgentCore Policy 튜토리얼: https://github.com/gonsoomoon-ml/amazon-bedrock-agentcore-policy-tutorials

### AWS 공식 문서
- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [On-demand Evaluation / Span 로그 다운로드](https://docs.aws.amazon.com/ko_kr/bedrock-agentcore/latest/devguide/getting-started-on-demand.html#download-span-logs)
- [Gateway 지원 target](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/gateway-supported-targets.html)
