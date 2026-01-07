# Distributed Multi-agent Solution using Amazon Bedrock AgentCore

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

In this tutorial we will learn how to independently host agents each in their own Bedrock AgentCore Runtime and built with different Agentic Frameworks. We'll then enable communication between them for a distributed multi-agent solution. 

In this example we'll create:
1. A technical agent (tech_agent) that is specialized in answering technical questions about programming and tech troubleshooting.
2. A HR agent (hr_agent) that is specialized in company benefits.
3. An orchestrator agent (orchestrator_agent) that routes questions to the technical or HR agent.

Putting these three agents together you get a multi-agent configuration with a supervisor, which can route user questions to the appropriate subagent. This system is capable of answering a range of questions an employee might have at a company.

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
