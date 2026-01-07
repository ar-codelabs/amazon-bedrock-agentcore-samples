# Simple Dual Platform Observability Tutorial

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

This tutorial demonstrates two observability approaches for Amazon Bedrock AgentCore agents:

1. **CloudWatch Observability (Default & Always Active)**: AgentCore Runtime automatically provides vended traces to CloudWatch Logs with zero configuration
2. **Braintrust Observability (Optional)**: Add AI-focused observability by exporting OpenTelemetry traces from the agent to Braintrust platform

The tutorial shows how AgentCore Runtime provides automatic observability via CloudWatch, with the optional ability to add AI-focused monitoring through Braintrust by exporting OpenTelemetry traces from your Strands agent. Note: CloudWatch traces are provided by AgentCore Runtime infrastructure, while Braintrust receives OTEL traces directly from your agent code.

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
