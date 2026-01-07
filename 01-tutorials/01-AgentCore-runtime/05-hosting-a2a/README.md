# README

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

Amazon Bedrock AgentCore Runtime is a secure, serverless runtime designed for deploying and scaling AI agents and tools. 
It supports any frameworks, models, and protocols, enabling developers to transform local prototypes into production-ready solutions with minimal code changes.

[Strands Agents](https://strandsagents.com/latest/) is a simple-to-use, code-first framework for building agents.

Recently, AWS announced [A2A support](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/runtime-a2a.html) for AgentCore Runtime.

In this example, we'll build a multi-agent systems using Amazon Bedrock AgentCore and Strands Agents.

This tutorial will navigate through the creation of 3 agents. The first one an AWS Documentation expert, that will consume AWS Docs using MCP. The second one will search on web latest blogs and AWS News and the third one will be an orchestrator, that will invoke the previous ones using MCP.

<img src="images/architecture.png" style="width: 80%;">

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
