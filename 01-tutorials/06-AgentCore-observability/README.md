# AgentCore Observability

이 저장소는 Amazon CloudWatch 및 기타 공급자를 사용하여 에이전트에 대한 AgentCore 관찰 가능성을 구현하는 방법을 보여줍니다. Amazon Bedrock AgentCore Runtime에 호스팅된 에이전트와 인기 있는 오픈 소스 에이전트 프레임워크를 사용하여 런타임에 호스팅되지 않은 에이전트 모두에 대한 예제를 제공합니다.

AgentCore Observability에 대한 자세한 내용은 [이 블로그 게시물](https://aws.amazon.com/blogs/machine-learning/build-trustworthy-ai-agents-with-amazon-bedrock-agentcore-observability/)을 참조하세요.

## 프로젝트 구조

```
06-AgentCore-observability/
├── 01-Agentcore-runtime-hosted/
│   ├── CrewAI/
│   │   ├── images/
│   │   ├── requirements.txt
│   │   └── runtime-with-crewai-and-bedrock-models.ipynb
│   ├── LlamaIndex/
│   │   ├── images/
│   │   ├── requirements.txt
│   │   ├── runtime_with_llamaindex_and_bedrock_models.ipynb
│   │   └── README.md
│   ├── Strands Agents/
│   │   ├── images/
│   │   ├── requirements.txt
│   │   └── runtime_with_strands_and_bedrock_models.ipynb
│   └── README.md
├── 02-Agent-not-hosted-on-runtime/
│   ├── CrewAI/
│   │   ├── .env.example
│   │   ├── CrewAI_Observability.ipynb
│   │   └── requirements.txt
│   ├── Langgraph/
│   │   ├── .env.example
│   │   ├── Langgraph_Observability.ipynb
│   │   └── requirements.txt
│   ├── LlamaIndex/
│   │   ├── images/
│   │   ├── .env.example
│   │   ├── LlamaIndex_Observability.ipynb
│   │   ├── README.md
│   │   └── requirements.txt
│   ├── Strands/
│   │   ├── images/
│   │   ├── .env.example
│   │   ├── requirements.txt
│   │   └── Strands_Observability.ipynb
│   └── README.md
├── 03-advanced-concepts/
│   ├── 01-custom-span-creation/
│   │   ├── .env.example
│   │   ├── Custom_Span_Creation.ipynb
│   │   └── requirements.txt
│   └── README.md
├── 04-Agentcore-runtime-partner-observability/
│   ├── Arize/
│   │   ├── requirements.txt
│   │   └── runtime_with_strands_and_arize.ipynb
│   ├── Braintrust/
│   │   ├── requirements.txt
│   │   └── runtime_with_strands_and_braintrust.ipynb
│   ├── Instana/
│   │   ├── requirements.txt
│   │   └── runtime_with_strands_and_instana.ipynb
│   ├── Langfuse/
│   │   ├── requirements.txt
│   │   └── runtime_with_strands_and_langfuse.ipynb
│   ├── images/
│   └── README.md
├── 05-Lambda-AgentCore-invocation/
│   ├── .gitignore
│   ├── agentcore_observability_lambda.ipynb
│   ├── lambda_agentcore_invoker.py
│   ├── mcp_agent_multi_server.py
│   ├── README.md
│   └── requirements.txt
└── README.md
```

## 개요

이 저장소는 개발자가 GenAI 애플리케이션에 대한 관찰 가능성을 구현하는 데 도움이 되는 예제 및 도구를 제공합니다. AgentCore Observability는 개발자가 통합 운영 대시보드를 통해 프로덕션에서 에이전트 성능을 추적, 디버그 및 모니터링할 수 있도록 지원합니다. OpenTelemetry 호환 텔레메트리 지원과 에이전트 워크플로의 각 단계에 대한 상세한 시각화를 통해 Amazon CloudWatch GenAI Observability는 개발자가 에이전트 동작에 대한 가시성을 쉽게 확보하고 대규모로 표준을 유지할 수 있도록 합니다.

## 내용

인기 있는 에이전트 개발 프레임워크를 사용한 예제를 보여줍니다:

- **Strands Agents**: 모델 기반 에이전트 개발을 사용하여 복잡한 워크플로로 LLM 애플리케이션 구축
- **CrewAI**: 작업을 수행하기 위해 역할에서 함께 작동하는 자율 AI 에이전트 생성
- **LangGraph**: 복잡한 추론 시스템을 위한 상태 저장 다중 행위자 애플리케이션으로 LangChain 확장
- **LlamaIndex**: 워크플로를 사용한 데이터에 대한 LLM 기반 에이전트

### 1. Bedrock AgentCore Runtime 호스팅 (01-Agentcore-runtime-hosted)

Amazon OpenTelemetry Python Instrumentation 및 Amazon CloudWatch를 사용하여 Amazon Bedrock AgentCore Runtime에 호스팅된 에이전트에 대한 관찰 가능성을 보여주는 예제입니다.

### 2. 런타임에 호스팅되지 않은 에이전트 (02-Agent-not-hosted-on-runtime)

Amazon Bedrock AgentCore Runtime에 호스팅되지 않은 인기 있는 오픈 소스 에이전트 프레임워크에 대한 관찰 가능성을 보여주는 예제입니다.

### 3. 고급 개념 (03-advanced-concepts)

고급 관찰 가능성 패턴 및 기술:

- **사용자 정의 스팬 생성**: 에이전트 워크플로 내의 특정 작업에 대한 상세한 추적 및 모니터링을 위해 사용자 정의 스팬을 생성하는 방법 알아보기

### 4. 파트너 관찰 가능성 (04-Agentcore-runtime-partner-observability)

타사 관찰 가능성 도구와 함께 Amazon Bedrock AgentCore Runtime에 호스팅된 에이전트를 사용하는 예제:

- **Arize**: AI 및 에이전트 엔지니어링 플랫폼
- **Braintrust**: AI 평가 및 모니터링 플랫폼
- **Instana**: 실시간 APM 및 관찰 가능성 플랫폼
- **Langfuse**: LLM 관찰 가능성 및 분석

### 5. Lambda AgentCore 호출 (05-Lambda-AgentCore-invocation)

완전한 CloudWatch 관찰 가능성을 통해 AWS Lambda 함수에서 AgentCore Runtime 에이전트를 호출하는 방법 알아보기:

- **Lambda 통합**: 호스팅된 에이전트를 호출하는 서버리스 함수 배포
- **MCP 다중 서버**: 단일 에이전트에서 여러 MCP 서버(AWS Docs + CDK) 사용
- **CloudWatch GenAI Observability**: 프로덕션에서 에이전트 동작 및 성능 모니터링

## 시작하기

1. 탐색하려는 프레임워크의 디렉토리로 이동
2. 요구 사항을 설치합니다.
3. AWS 자격 증명을 구성합니다
4. `.env.example` 파일을 `.env`로 복사하고 변수를 업데이트합니다
5. Jupyter 노트북을 열고 실행합니다

## 사전 요구 사항

- 적절한 권한이 있는 AWS 계정
- Python 3.10+
- Jupyter 노트북 환경
- 자격 증명으로 구성된 AWS CLI
- Transaction Search 활성화

## 정리

예제를 완료한 후 불필요한 요금을 피하기 위해 Amazon CloudWatch에서 생성된 로그 그룹 및 관련 리소스를 삭제하세요.

## 라이선스

이 프로젝트는 저장소에 지정된 조건에 따라 라이선스가 부여됩니다.
