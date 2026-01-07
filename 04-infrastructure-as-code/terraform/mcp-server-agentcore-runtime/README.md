# MCP Server on AgentCore Runtime - Terraform

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

This Terraform configuration creates an MCP server deployment that includes:

- **MCP Server**: Hosts three custom tools (add_numbers, multiply_numbers, greet_user)
- **JWT Authentication**: Cognito User Pool for secure access
- **AgentCore Runtime**: Serverless hosting with MCP protocol support
- **ECR Repository**: Stores the Docker container image
- **CodeBuild Project**: Automatically builds the ARM64 Docker image

The stack uses the Amazon Bedrock AgentCore Python SDK to wrap agent functions as an MCP server compatible with Amazon Bedrock AgentCore. When hosting tools, the SDK implements the [Stateless Streamable HTTP](https://modelcontextprotocol.io/specification/2025-06-18/basic/transports) transport protocol with the `MCP-Session-Id` header for session isolation.

This makes it ideal for:
- Learning MCP protocol with AgentCore Runtime
- Building secure MCP servers with JWT authentication
- Understanding MCP tool development patterns
- Creating custom tools for AI agents

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
