# Back-End Deployment - Data Source and Configuration Management Deployment with CDK

> **참고**: 자세한 영문 내용은 [README_eng.md](README_eng.md)를 참조하세요.

## 개요

This tutorial deploys the foundational AWS services required for the video game sales data analyst agent with the following key components:

- **IAM AgentCore Execution Role**: Comprehensive permissions for Amazon Bedrock AgentCore execution, including access to Bedrock models, RDS Data API, DynamoDB, and Secrets Manager
- **VPC with Public and Private Subnets**: Network isolation and security for database resources with NAT Gateway for outbound connectivity
- **Amazon Aurora Serverless v2 PostgreSQL**: Scalable database cluster storing video game sales data with RDS Data API integration and encryption
- **Amazon DynamoDB**: Single table for tracking SQL query results with pay-per-request billing
- **AWS Secrets Manager**: Secure storage for database credentials
- **Amazon S3**: Import bucket for loading data into Aurora PostgreSQL with lifecycle policies
- **VPC Gateway Endpoints**: Cost-effective access to S3 and DynamoDB services
- **SSM Parameter Store**: Configuration management for AgentCore runtime parameters

> [!IMPORTANT]
> Remember to clean up resources after testing to avoid unnecessary costs by following the clean-up steps provided.

자세한 설명, 코드 예제 및 단계별 지침은 영문 README 파일을 참조하세요.

## 시작하기

1. 영문 README 파일([README_eng.md](README_eng.md))의 지침을 따르세요
2. 필요한 사전 요구 사항을 설치하세요
3. 제공된 노트북 또는 스크립트를 실행하세요

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
- [메인 README](../README.md)
