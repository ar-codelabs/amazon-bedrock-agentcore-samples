# Configure Observability for AgentCore Gateway with Amazon CloudWatch and AWS CloudTrail

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

Observability is a fundamental capability for the AgentCore Gateway because it provides comprehensive real-time insights into the functioning and performance of AI agents deployed through the gateway. By capturing and displaying key metrics such as request volumes, success rates, error patterns, latency for tool invocations, and authentication events, the observability features allow developers and operators to monitor the health and efficiency of their agent workflows continuously. This level of monitoring helps quickly identify anomalies or bottlenecks that could affect user experience or system reliability, enabling proactive troubleshooting and performance tuning.

Beyond high-level metrics, AgentCore Gateway observability offers detailed tracing of each agent’s workflow. Every action—from invoking tools to model calls and memory retrieval—is logged as spans and traces compliant with OpenTelemetry standards. This rich telemetry data provides developers with a transparent view into the internal decision-making processes of agents, including how each step was executed and its duration. Such granular traceability is invaluable for debugging complex failures or unexpected behaviors, as it allows engineers to drill down into the exact point of error or inefficiency. Additionally, by integrating with widely used monitoring platforms like Amazon CloudWatch, these observability features enable a unified and accessible operational overview.

Furthermore, observability supports compliance and governance requirements by offering audit trails of agent activity, which is critical for enterprise environments. It also facilitates optimization by revealing usage patterns and helping adjust agent workflows to reduce costs or improve speed. Ultimately, these observability capabilities transform the AgentCore Gateway from a black-box interface into a transparent, manageable system that supports reliable, scalable, and performant AI agent deployment in production environments.

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
