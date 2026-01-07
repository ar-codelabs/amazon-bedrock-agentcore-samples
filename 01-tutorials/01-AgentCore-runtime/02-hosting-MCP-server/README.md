# Hosting MCP server on AgentCore Runtime

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

In this session we will discuss how to host MCP tools on Amazon Bedrock AgentCore Runtime.

We will use the Amazon Bedrock AgentCore Python SDK to wrapper the agents function as an MCP server compatible with Amazon Bedrock AgentCore.
It will handle the MCP server details so you can focus on your agent's core functionality.

The Amazon Bedrock AgentCore Python SDK prepares your agent or tool code to run on AgentCore Runtime. 

It will transform your code into the AgentCore standardized HTTP protocol or MCP protocol contracts to allow for direct REST API endpoint communication for a traditional request/response pattern (HTTP protocol) or Model Context Protocol for tools and agents servers (MCP Protocol).

When you are hosting tools, the Amazon Bedrock AgentCore Python SDK will implement the [Stateless Streamable HTTP] transport protocol with the `MCP-Session-Id` header for [session isolation]https://modelcontextprotocol.io/specification/2025-06-18/basic/transports#session-management, servers must support stateless operation to not reject platform generated Mcp-Session-Id header.
Your MCP server will then be hosted on port `8000` and will provide one invocation path: the `mcp-POST`. This interaction endpoint with receive the MCP RPC messages and process them through your tool's capabilities. It supports both  application/json and text/event-stream as response content-types.

When you set your AgentCore protocol to MCP, AgentCore Runtime will expect the MCP server container to be on path `0.0.0.0:8000/mcp` as that's the default path supported by most of the official MCP server SDKs.

AgentCore Runtime requires you to host stateless streamable-http servers because it provides session-isolation by default and automatically adds a Mcp-Session-Id header for any request without it, so MCP clients can have continuity of connection to same Bedrock AgentCore Runtime session ID. 

Payload of `InvokeAgentRuntime` API is completely pass through, so RPC messages of protocols like MCP can easily be proxied.

In this tutorial you will learn:

* How to create an MCP server with tools
* How to test your server locally
* How to deploy your server to AWS
* How to invoke your deployed server

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
