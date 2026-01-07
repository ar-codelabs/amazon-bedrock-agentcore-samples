# 🔌 Amazon Bedrock AgentCore 통합

Amazon Bedrock AgentCore 샘플 저장소의 통합 섹션에 오신 것을 환영합니다!

이 폴더에는 Amazon Bedrock AgentCore를 인기 있는 에이전트 프레임워크, ID 공급자, 관찰 가능성 도구 및 AWS 서비스와 연결하는 방법을 보여주는 프레임워크 및 프로토콜 통합이 포함되어 있습니다.

## 🤖 에이전트 프레임워크

* **[ADK](./agentic-frameworks/adk/)**: Google Search와 통합된 Agent Development Kit
* **[AutoGen](./agentic-frameworks/autogen/)**: 다중 에이전트 대화 프레임워크
* **[CrewAI](./agentic-frameworks/crewai/)**: 협업 AI 에이전트 오케스트레이션
* **[LangChain](./agentic-frameworks/langchain/)**: 체인 기반 에이전트 워크플로 및 도구 통합
* **[LangGraph](./agentic-frameworks/langgraph/)**: 웹 검색 기능을 갖춘 다중 에이전트 워크플로
* **[LlamaIndex](./agentic-frameworks/llamaindex/)**: 문서 처리 및 검색 증강 생성
* **[OpenAI Agents](./agentic-frameworks/openai-agents/)**: 핸드오프 패턴을 사용한 OpenAI Assistant API 통합
* **[PydanticAI](./agentic-frameworks/pydanticai-agents/)**: Bedrock 모델을 사용한 타입 안전 에이전트 개발
* **[Strands Agents](./agentic-frameworks/strands-agents/)**: 스트리밍, 파일 시스템 및 OpenAI ID를 사용한 네이티브 통합 예제

## ☁️ AWS 서비스

* **[SageMaker AI](./amazon-sagemakerai/)**: AgentCore Runtime과 MLflow 통합
* **[Bedrock Agent](./bedrock-agent/)**: Bedrock Agents와 AgentCore Gateway 간의 통합

## 🔐 ID 공급자

* **[EntraID](./IDP-examples/EntraID/)**: 3LO 아웃바운드 인증을 사용한 Microsoft Entra ID 통합
* **[Okta](./IDP-examples/Okta/)**: 인바운드 인증을 위한 단계별 Okta 통합

## ☁️ Nova

* **[Nova Sonic](./nova/nova-sonic/)**: Amazon Nova 모델 통합 예제

## 📊 관찰 가능성

* **[Dynatrace](./observability/dynatrace/)**: 여행 에이전트 예제를 사용한 애플리케이션 성능 모니터링 통합
* **[Simple Dual Observability](./observability/simple-dual-observability/)**: AgentCore Runtime을 위한 자동 OpenTelemetry 계측을 사용한 Amazon CloudWatch 및 Braintrust 통합

## 🎨 UX 예제

* **[Streamlit Chat](./ux-examples/streamlit-chat/)**: AgentCore 백엔드 통합을 사용한 대화형 채팅 인터페이스

## 🚀 통합 패턴

이러한 통합은 다음을 보여줍니다:

- **프레임워크 적응**: 기존 에이전트 프레임워크를 AgentCore와 함께 작동하도록 적응
- **인증 흐름**: 다양한 ID 공급자 통합 구현
- **모니터링 설정**: 에이전트 성능 추적을 위한 관찰 가능성 도구 연결
- **UI 통합**: AgentCore 서비스에 연결되는 사용자 인터페이스 구축
- **서비스 구성**: 여러 AWS 서비스를 AgentCore와 결합

## 🎯 이 통합의 대상

이 통합은 다음과 같은 분들에게 완벽합니다:

- 기존 에이전트 애플리케이션을 AgentCore로 마이그레이션
- 엔터프라이즈 인증 패턴 구현
- 프로덕션 모니터링 및 관찰 가능성 설정
- 에이전트 상호 작용을 위한 사용자 정의 사용자 인터페이스 구축
- AgentCore를 기존 AWS 인프라와 연결

## 🔗 관련 리소스

- [튜토리얼](../01-tutorials/) - AgentCore 기본 사항 배우기
- [사용 사례](../02-use-cases/) - 엔드투엔드 애플리케이션 예제
- [AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
