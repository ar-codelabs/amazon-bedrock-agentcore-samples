# Amazon Bedrock Agent Integration with Bedrock AgentCore Gateway

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

This use case demonstrates a complete end-to-end integration between **Amazon Bedrock Agents** and **Amazon Bedrock AgentCore Gateway** using the **Model Context Protocol (MCP)** to connect with a practical fruit stand backend API built on AWS Lambda and DynamoDB. This showcase illustrates how MCP enables seamless communication between AI agents and existing backend systems, allowing agents to access real-world tools and data without requiring complex integration work.

**Key Integration Focus: Model Context Protocol (MCP)**
MCP is an open standard that enables AI agents to securely connect to external data sources and tools. In this use case:
- **Bedrock Agent** communicates with the Gateway using standard action group calls
- **AgentCore Gateway** translates these calls into MCP-compatible format
- **Backend Lambda functions** are automatically exposed as MCP tools
- **Real-time data access** is achieved through MCP's standardized protocol

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
