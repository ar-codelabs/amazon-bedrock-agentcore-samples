# Multi-Agent Runtime on Amazon Bedrock AgentCore (Terraform)

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

This pattern demonstrates deploying a multi-agent system with two coordinating agents that communicate via the Agent-to-Agent (A2A) protocol. Agent1 (Orchestrator) can delegate specialized tasks to Agent2 (Specialist), enabling modular and scalable agent architectures.

**Key Features:**
- Two-agent architecture with A2A communication
- Automated Docker image building via CodeBuild
- S3-based source code management with change detection
- IAM-based security with least-privilege access
- Sequential deployment ensuring proper dependencies

This makes it ideal for:
- Building complex multi-agent workflows
- Implementing agent specialization patterns
- Creating scalable agent orchestration systems
- Learning A2A communication protocols

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
