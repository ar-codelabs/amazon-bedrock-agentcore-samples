# Amazon Bedrock AgentCore 런타임에서 Amazon Bedrock 모델을 사용한 Strands 에이전트 호스팅

## 개요

이 튜토리얼에서는 **Amazon Bedrock AgentCore 런타임**을 사용하여 기존 에이전트를 호스팅하는 방법을 배웁니다. 

이때 **Strands 에이전트와 Amazon Bedrock 모델**을 사용한 예제를 중심으로 설명합니다.  
Amazon Bedrock 모델을 사용한 **LangGraph** 예제는 [여기](../02-langgraph-with-bedrock-model)를 참고하고,  
**OpenAI 모델을 사용한 Strands 에이전트** 예제는 [여기](../03-strands-with-openai-model)를 참고하세요.

---

### 튜토리얼 세부 정보

| 정보               | 세부 정보                                                                 |
|:-------------------|:-------------------------------------------------------------------------|
| 튜토리얼 유형      | 대화형                                                                   |
| 에이전트 유형      | 단일                                                                   |
| 에이전트 프레임워크 | Strands 에이전트                                                         |
| LLM 모델            | Anthropic Claude Haiku 4.5                                              |
| 튜토리얼 구성 요소 | AgentCore 런타임에서 에이전트 호스팅. Strands 에이전트 및 Amazon Bedrock 모델 사용 |
| 튜토리얼 분야      | 다분야                                                                   |
| 예제 복잡도         | 초보자 수준                                                               |
| 사용된 SDK          | Amazon BedrockAgentCore Python SDK 및 boto3                               |

---

### 튜토리얼 아키텍처

이 튜토리얼에서는 **기존 에이전트를 AgentCore 런타임에 배포하는 방법**을 설명합니다. 

시연을 위해 **Amazon Bedrock 모델을 사용한 Strands 에이전트**를 사용합니다.  
예제에서는 **`get_weather`** 및 **`get_time`** 두 도구를 사용하는 매우 간단한 에이전트를 사용합니다. 

<div style="text-align:left">
    <img src="images/architecture_runtime.png" width="100%"/>
</div>

---

### 튜토리얼 주요 기능

* **Amazon Bedrock AgentCore 런타임에서 에이전트 호스팅**
* **Amazon Bedrock 모델 사용**
* **Strands 에이전트 사용**
