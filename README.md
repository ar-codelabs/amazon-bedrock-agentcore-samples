<div align="center">
  <div>
    <a href="https://aws.amazon.com/bedrock/agentcore/">
      <img width="150" height="150" alt="image" src="https://github.com/user-attachments/assets/b8b9456d-c9e2-45e1-ac5b-760f21f1ac18" />
   </a>
  </div>

  <h1>
      Amazon Bedrock AgentCore 샘플
  </h1>

  <h2>
    모든 프레임워크와 모델을 사용하여 AI 에이전트를 안전하게 대규모로 배포하고 운영하세요
  </h2>

  <div align="center">
    <a href="https://github.com/awslabs/amazon-bedrock-agentcore-samples/graphs/commit-activity"><img alt="GitHub commit activity" src="https://img.shields.io/github/commit-activity/m/awslabs/amazon-bedrock-agentcore-samples"/></a>
    <a href="https://github.com/awslabs/amazon-bedrock-agentcore-samples/issues"><img alt="GitHub open issues" src="https://img.shields.io/github/issues/awslabs/amazon-bedrock-agentcore-samples"/></a>
    <a href="https://github.com/awslabs/amazon-bedrock-agentcore-samples/pulls"><img alt="GitHub open pull requests" src="https://img.shields.io/github/issues-pr/awslabs/amazon-bedrock-agentcore-samples"/></a>
    <a href="https://github.com/awslabs/amazon-bedrock-agentcore-samples/blob/main/LICENSE"><img alt="License" src="https://img.shields.io/github/license/awslabs/amazon-bedrock-agentcore-samples"/></a>
  </div>
  
  <p>
    <a href="https://docs.aws.amazon.com/bedrock-agentcore/">문서</a>
    ◆ <a href="https://github.com/aws/bedrock-agentcore-sdk-python">Python SDK</a>
    ◆ <a href="https://github.com/aws/bedrock-agentcore-starter-toolkit">스타터 툴킷</a>
    ◆ <a href="https://discord.gg/bedrockagentcore-preview">Discord</a>
  </p>
</div>

Amazon Bedrock AgentCore 샘플 저장소에 오신 것을 환영합니다!

Amazon Bedrock AgentCore는 프레임워크와 모델에 구애받지 않아, 고급 AI 에이전트를 안전하고 대규모로 배포하고 운영할 수 있는 유연성을 제공합니다. [Strands Agents](https://strandsagents.com/latest/), [CrewAI](https://www.crewai.com/), [LangGraph](https://www.langchain.com/langgraph), [LlamaIndex](https://www.llamaindex.ai/) 또는 다른 프레임워크로 구축하든, 어떤 대규모 언어 모델(LLM)에서 실행하든 Amazon Bedrock AgentCore는 이를 지원하는 인프라를 제공합니다. 전문화된 에이전트 인프라를 구축하고 관리하는 차별화되지 않은 무거운 작업을 제거함으로써, Amazon Bedrock AgentCore를 사용하면 선호하는 프레임워크와 모델을 가져와 코드를 다시 작성하지 않고도 배포할 수 있습니다.

이 컬렉션은 Amazon Bedrock AgentCore 기능을 이해하고, 구현하고, 애플리케이션에 통합하는 데 도움이 되는 예제와 튜토리얼을 제공합니다.

## 🎥 비디오

Amazon Bedrock AgentCore로 첫 번째 프로덕션 준비 AI 에이전트를 구축하세요. 프로토타이핑을 넘어 Amazon Bedrock AgentCore를 사용하여 첫 번째 에이전트 AI 애플리케이션을 프로덕션화하는 방법을 보여드립니다.

<p align="center">
  <a href="https://www.youtube.com/watch?v=wzIQDPFQx30"><img src="https://markdown-videos-api.jorgenkh.no/youtube/wzIQDPFQx30?width=640&height=360&filetype=jpeg" /></a>
</p>

## 📁 저장소 구조

### 📚 [`01-tutorials/`](./01-tutorials/)
**대화형 학습 및 기초**

이 폴더에는 실습 예제를 통해 Amazon Bedrock AgentCore 기능의 기본 사항을 가르치는 노트북 기반 튜토리얼이 포함되어 있습니다.

구조는 AgentCore 구성 요소별로 나뉩니다:
* **[Runtime](./01-tutorials/01-AgentCore-runtime)**: Amazon Bedrock AgentCore Runtime은 프레임워크, 프로토콜 또는 모델 선택에 관계없이 조직이 AI 에이전트와 도구를 배포하고 확장할 수 있도록 지원하는 안전한 서버리스 런타임 기능으로, 빠른 프로토타이핑, 원활한 확장 및 시장 출시 시간 단축을 가능하게 합니다
* **[Gateway](./01-tutorials/02-AgentCore-gateway)**: AI 에이전트는 데이터베이스 검색부터 메시지 전송까지 실제 작업을 수행하기 위해 도구가 필요합니다. Amazon Bedrock AgentCore Gateway는 API, Lambda 함수 및 기존 서비스를 MCP 호환 도구로 자동 변환하여 개발자가 통합을 관리하지 않고도 이러한 필수 기능을 에이전트에 빠르게 제공할 수 있도록 합니다.
* **[Memory](./01-tutorials/04-AgentCore-memory)**: Amazon Bedrock AgentCore Memory를 사용하면 개발자가 완전 관리형 메모리 인프라와 필요에 맞게 메모리를 사용자 정의할 수 있는 기능을 통해 풍부하고 개인화된 에이전트 경험을 쉽게 구축할 수 있습니다.
* **[Identity](./01-tutorials/03-AgentCore-identity)**: Amazon Bedrock AgentCore Identity는 Okta, Entra 및 Amazon Cognito와 같은 표준 ID 공급자를 지원하면서 AWS 서비스 및 Slack, Zoom과 같은 타사 애플리케이션 전반에 걸쳐 원활한 에이전트 ID 및 액세스 관리를 제공합니다.
* **[Tools](./01-tutorials/05-AgentCore-tools)**: Amazon Bedrock AgentCore는 에이전트 AI 애플리케이션 개발을 단순화하기 위해 두 가지 내장 도구를 제공합니다: Amazon Bedrock AgentCore **Code Interpreter** 도구는 AI 에이전트가 코드를 안전하게 작성하고 실행할 수 있도록 하여 정확성을 향상시키고 복잡한 엔드투엔드 작업을 해결하는 능력을 확장합니다. Amazon Bedrock AgentCore **Browser Tool**은 AI 에이전트가 완전 관리형 보안 샌드박스 환경에서 낮은 지연 시간으로 사람과 같은 정밀도로 웹사이트를 탐색하고, 다단계 양식을 작성하고, 복잡한 웹 기반 작업을 수행할 수 있도록 하는 엔터프라이즈급 기능입니다
* **[Observability](./01-tutorials/06-AgentCore-observability)**: Amazon Bedrock AgentCore Observability는 개발자가 통합 운영 대시보드를 통해 에이전트 성능을 추적, 디버그 및 모니터링할 수 있도록 지원합니다. OpenTelemetry 호환 텔레메트리 지원과 에이전트 워크플로의 각 단계에 대한 상세한 시각화를 통해 Amazon Bedrock AgentCore Observability는 개발자가 에이전트 동작에 대한 가시성을 쉽게 확보하고 대규모로 품질 표준을 유지할 수 있도록 합니다.

* **[AgentCore 엔드투엔드](./01-tutorials/07-AgentCore-E2E)**: 이 튜토리얼에서는 Amazon Bedrock AgentCore 서비스를 사용하여 고객 지원 에이전트를 프로토타입에서 프로덕션으로 이동합니다.


제공된 예제는 초보자와 AI 에이전트 애플리케이션을 구축하기 전에 기본 개념을 이해하려는 사람들에게 완벽합니다.

### 💡 [`02-use-cases/`](./02-use-cases/)
**엔드투엔드 애플리케이션**

Amazon Bedrock AgentCore 기능을 적용하여 실제 비즈니스 문제를 해결하는 방법을 보여주는 실용적인 사용 사례 구현을 살펴보세요.

각 사용 사례에는 상세한 설명과 함께 AgentCore 구성 요소에 중점을 둔 완전한 구현이 포함되어 있습니다.

### 🔌 [`03-integrations/`](./03-integrations/)
**프레임워크 및 프로토콜 통합**

Strands Agents, LangChain 및 CrewAI와 같은 인기 있는 에이전트 프레임워크와 Amazon Bedrock AgentCore 기능을 통합하는 방법을 알아보세요.

A2A를 사용한 에이전트 간 통신 및 다양한 다중 에이전트 협업 패턴을 설정하세요. 에이전트 인터페이스를 통합하고 다양한 진입점에서 Amazon Bedrock AgentCore를 사용하는 방법을 배우세요.

### 🏗️ [`04-infrastructure-as-code/`](./04-infrastructure-as-code/)
**배포 자동화 및 인프라**

코드형 인프라로 Amazon Bedrock AgentCore 리소스를 배포하세요. CloudFormation, AWS CDK 또는 Terraform을 사용한 예제를 제공합니다.

기본 런타임, MCP 서버, 다중 에이전트 시스템 및 도구와 메모리가 포함된 완전한 에이전트 솔루션을 위한 프로덕션 준비 템플릿으로 인프라 프로비저닝을 자동화하세요.

### 🚀 [`05-blueprints/`](./05-blueprints/)
**풀스택 참조 애플리케이션**

Amazon Bedrock AgentCore를 기반으로 구축된 완전하고 배포 준비가 된 에이전트 애플리케이션으로 개발을 빠르게 시작하세요.

각 블루프린트는 사용 사례에 맞게 사용자 정의하고 배포할 수 있는 통합 서비스, 인증 및 비즈니스 로직이 포함된 포괄적인 기반을 제공합니다.

## 노트북 실행하기

1. 가상 환경 생성 및 활성화
```bash
python -m venv .venv
source .venv/bin/activate
```

2. 종속성 설치
```bash
pip install -r requirements.txt
```

3. 노트북 실행에 필요한 AWS 자격 증명 내보내기/활성화

4. Jupyter 노트북에서 사용할 커널로 가상 환경 등록
```bash
python -m ipykernel install --user --name=notebook-venv --display-name="Python (notebook-venv)"
```

다음을 사용하여 커널 목록을 확인할 수 있습니다:
```bash
jupyter kernelspec list
```

5. 노트북을 실행하고 올바른 커널이 선택되었는지 확인
```bash
jupyter notebook path/to/your/notebook.ipynb
```

**중요:** Jupyter에서 노트북을 연 후 `Kernel` → `Change kernel` → "Python (notebook-venv)" 선택으로 이동하여 올바른 커널을 선택하여 가상 환경 패키지를 사용할 수 있도록 하세요.


## 빠른 시작 - [Amazon Bedrock AgentCore Runtime](https://github.com/aws/bedrock-agentcore-starter-toolkit/blob/main/documentation/docs/user-guide/runtime/quickstart.md)

### 1단계: 사전 요구 사항

- 자격 증명이 구성된 [AWS 계정](https://signin.aws.amazon.com/signin?redirect_uri=https%3A%2F%2Fportal.aws.amazon.com%2Fbilling%2Fsignup%2Fresume&client_id=signup) (`aws configure`)
- [Python 3.10](https://www.python.org/downloads/) 이상
- [Docker](https://www.docker.com/) 또는 [Finch](https://runfinch.com/) 설치 및 실행 - 로컬 개발용만
- 모델 액세스: [Amazon Bedrock 콘솔](https://docs.aws.amazon.com/bedrock/latest/userguide/model-access-modify.html)에서 Anthropic Claude 4.0 활성화
- AWS 권한:
    - `BedrockAgentCoreFullAccess` 관리형 정책
    - `AmazonBedrockFullAccess` 관리형 정책
    - `호출자 권한`: 자세한 정책은 [여기](https://github.com/aws/bedrock-agentcore-starter-toolkit/blob/main/documentation/docs/user-guide/runtime/permissions.md#developercaller-permissions) 참조

### 2단계: 설치 및 에이전트 생성

```bash
# 두 패키지 모두 설치
pip install bedrock-agentcore strands-agents bedrock-agentcore-starter-toolkit
```

`my_agent.py` 생성:

```python
from bedrock_agentcore import BedrockAgentCoreApp
from strands import Agent

app = BedrockAgentCoreApp()
agent = Agent()

@app.entrypoint
def invoke(payload):
    """AI 에이전트 함수"""
    user_message = payload.get("prompt", "안녕하세요! 무엇을 도와드릴까요?")
    result = agent(user_message)
    return {"result": result.message}

if __name__ == "__main__":
    app.run()
```
`requirements.txt` 생성:

```bash
cat > requirements.txt << EOF
bedrock-agentcore
strands-agents
EOF
```
### 3단계: 로컬 테스트

```bash
# 에이전트 시작
python my_agent.py

# 테스트 (다른 터미널에서)
curl -X POST http://localhost:8080/invocations \
  -H "Content-Type: application/json" \
  -d '{"prompt": "안녕하세요!"}'
```
성공: {"result": "안녕하세요! 도와드리겠습니다..."}와 같은 응답이 표시되어야 합니다

### 4단계: AWS에 배포

```bash
# 구성 및 배포 (필요한 모든 리소스 자동 생성)
agentcore configure -e my_agent.py
agentcore launch

# 배포된 에이전트 테스트
agentcore invoke '{"prompt": "농담 하나 해줘"}'
```

축하합니다! 이제 에이전트가 Amazon Bedrock AgentCore Runtime에서 실행되고 있습니다!

[Gateway](https://github.com/aws/bedrock-agentcore-starter-toolkit/blob/main/documentation/docs/user-guide/gateway/quickstart.md), [Identity](https://github.com/aws/bedrock-agentcore-starter-toolkit/blob/main/documentation/docs/user-guide/identity/quickstart.md), [Memory](https://github.com/aws/bedrock-agentcore-starter-toolkit/blob/main/documentation/docs/user-guide/memory/quickstart.md), [Observability](https://github.com/aws/bedrock-agentcore-starter-toolkit/blob/main/documentation/docs/user-guide/observability/quickstart.md) 및 [내장 도구](https://github.com/aws/bedrock-agentcore-starter-toolkit/tree/main/documentation/docs/user-guide/builtin-tools)에 대한 빠른 시작 가이드를 따르세요.

## 🔗 관련 링크:

- [Amazon Bedrock AgentCore 시작하기 - 워크샵](https://catalog.us-east-1.prod.workshops.aws/workshops/850fcd5c-fd1f-48d7-932c-ad9babede979/en-US)
- [Bedrock AgentCore 심층 분석 - 워크샵](https://catalog.workshops.aws/agentcore-deep-dive/en-US)
- [Amazon Bedrock AgentCore 가격](https://aws.amazon.com/bedrock/agentcore/pricing/)
- [Amazon Bedrock AgentCore FAQ](https://aws.amazon.com/bedrock/agentcore/faqs/)

## 🤝 기여하기

기여를 환영합니다! 자세한 내용은 [기여 가이드라인](CONTRIBUTING.md)을 참조하세요:

- 새로운 샘플 추가
- 기존 예제 개선
- 문제 보고
- 개선 사항 제안


## 📄 라이선스

이 프로젝트는 Apache License 2.0에 따라 라이선스가 부여됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.


## 기여자

<a href="https://github.com/awslabs/amazon-bedrock-agentcore-samples/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=awslabs/amazon-bedrock-agentcore-samples" />
</a>
