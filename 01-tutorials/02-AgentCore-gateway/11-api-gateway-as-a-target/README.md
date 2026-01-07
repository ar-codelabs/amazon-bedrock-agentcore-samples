# Integrate your API Gateway as an AgentCore Gateway Target

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

As organizations explore the possibilities of agentic applications, they continue to navigate challenges of using enterprise data as context in invocation requests to large language models (LLMs) in a manner that is secure and aligned with enterprise policies. To help standardize and secure those interactions, many organizations are using the Model Context Protocol (MCP) specification, which defines how agentic applications can securely connect to data sources and tools.

While MCP has been advantageous for net new use cases, organizations also navigate challenges with bringing their existing API estate into the agentic era. MCP can certainly wrap existing APIs, but it requires additional work, translating requests from MCP to RESTful APIs, making sure security is maintained through the entire request flow, and applying the standard observability required for production deployments.

[Amazon Bedrock AgentCore Gateway](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/gateway.html) now supports [Amazon API Gateway](https://aws.amazon.com/api-gateway/) as a target, translating MCP requests to AgentCore Gateway (ACGW) into RESTful requests to API Gateway (APIGW). You can now expose both new and existing API endpoints from APIGW to agentic applications via MCP, with built-in security and observability. This notebook covers this new capability and shows how to implement them.

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
