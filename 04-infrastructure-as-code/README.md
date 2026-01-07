# Amazon Bedrock AgentCore를 위한 코드형 인프라 샘플

CloudFormation 템플릿, AWS CDK 또는 Terraform을 사용하여 Amazon Bedrock AgentCore 리소스를 배포하세요.

## 개요

이러한 코드형 인프라 샘플을 통해 다음을 수행할 수 있습니다:
- 환경 전반에 걸쳐 AgentCore 리소스를 일관되게 배포
- 코드형 인프라로 인프라 프로비저닝 자동화
- 인프라의 버전 관리 유지
- 보안 및 모니터링을 위한 AWS 모범 사례 구현

선호하는 접근 방식을 선택하세요:
- **[CloudFormation](./cloudformation/)** - 선언적 인프라를 위한 YAML/JSON 템플릿
- **[CDK](./cdk/)** - 프로그래밍 방식 인프라를 위한 Python 코드
- **[Terraform](./terraform/)** - 상태 관리를 통한 선언적 인프라를 위한 HCL 코드

## 샘플

### 1. 기본 에이전트 런타임
추가 도구나 메모리 없이 기본 Strands 에이전트로 간단한 AgentCore Runtime을 배포합니다.

**배포 내용:**
- 간단한 에이전트가 포함된 AgentCore Runtime
- ECR 리포지토리 및 자동화된 Docker 빌드
- 최소 권한 정책이 적용된 IAM 역할

**사용 사례:** 복잡성 없이 AgentCore 기본 사항 학습  
**배포 시간:** ~5-15분  
**예상 비용:** 월 ~$50-100

**구현:** [CloudFormation](./cloudformation/basic-runtime/) | [CDK](./cdk/basic-runtime/) | [Terraform](./terraform/basic-runtime/)

### 2. AgentCore Runtime의 MCP 서버
자동화된 Docker 빌드 및 JWT 인증을 갖춘 완전한 MCP(Model Context Protocol) 서버를 배포합니다.

**배포 내용:**
- MCP 서버를 호스팅하는 AgentCore Runtime
- JWT 인증을 위한 Amazon Cognito
- 자동화된 ARM64 Docker 빌드

**샘플 MCP 도구:** `add_numbers`, `multiply_numbers`, `greet_user`  
**배포 시간:** ~10-15분  
**예상 비용:** 월 ~$50-100

**구현:** [CloudFormation](./cloudformation/mcp-server-agentcore-runtime/) | [CDK](./cdk/mcp-server-agentcore-runtime/) | [Terraform](./terraform/mcp-server-agentcore-runtime/)

### 3. 다중 에이전트 런타임
Agent1(오케스트레이터)이 복잡한 작업을 위해 Agent2(전문가)를 호출할 수 있는 다중 에이전트 시스템을 배포합니다.

**배포 내용:**
- 에이전트 간 통신이 가능한 두 개의 AgentCore Runtime
- 에이전트 간 호출 권한이 있는 IAM 역할
- 각 에이전트를 위한 별도의 ECR 리포지토리

**아키텍처:** Agent1이 요청을 라우팅하고 상세 분석을 위해 Agent2에 위임  
**배포 시간:** ~15-20분  
**예상 비용:** 월 ~$100-200

**구현:** [CloudFormation](./cloudformation/multi-agent-runtime/) | [CDK](./cdk/multi-agent-runtime/) | [Terraform](./terraform/multi-agent-runtime/)

### 4. 도구 및 메모리를 갖춘 엔드투엔드 날씨 에이전트
브라우저 자동화, 코드 인터프리터 및 메모리를 갖춘 완전한 날씨 기반 활동 계획 에이전트를 배포합니다.

**배포 내용:**
- Strands 에이전트가 포함된 AgentCore Runtime
- 날씨 데이터 웹 스크래핑을 위한 브라우저 도구
- 날씨 분석을 위한 코드 인터프리터 도구
- 사용자 선호도 저장을 위한 메모리
- 결과 저장을 위한 S3 버킷

**기능:** weather.gov 스크래핑, 조건 분석, 선호도 저장, 권장 사항 생성  
**배포 시간:** ~15-20분  
**예상 비용:** 월 ~$100-150

**구현:** [CloudFormation](./cloudformation/end-to-end-weather-agent/) | [CDK](./cdk/end-to-end-weather-agent/) | [Terraform](./terraform/end-to-end-weather-agent/)

## 사전 요구 사항

샘플을 배포하기 전에 다음을 확인하세요:

1. 적절한 권한이 있는 **AWS 계정**
2. **AWS CLI** 설치 및 구성
3. **Amazon Bedrock AgentCore 액세스** (프리뷰)
4. 다음을 생성할 수 있는 **IAM 권한**:
   - CloudFormation 스택 (CloudFormation 샘플용)
   - IAM 역할 및 정책
   - ECR 리포지토리
   - Lambda 함수
   - AgentCore 리소스
   - S3 버킷 (날씨 에이전트용)

CDK 샘플의 경우 다음도 설치하세요:
- Python 3.8+
- AWS CDK v2.218.0 이상

Terraform 샘플의 경우 다음도 설치하세요:
- Terraform >= 1.6 (버전 관리를 위해 [tfenv](https://github.com/tfutils/tfenv) 권장)
- 참고: `brew install terraform`은 더 이상 사용되지 않는 v1.5.7을 제공합니다

## 저장소 구조

```
04-infrastructure-as-code/
├── README.md                          # 이 파일
├── cloudformation/                    # CloudFormation 샘플
│   ├── README.md                      # CloudFormation 전용 가이드
│   ├── basic-runtime/
│   ├── mcp-server-agentcore-runtime/
│   ├── multi-agent-runtime/
│   └── end-to-end-weather-agent/
├── cdk/                              # CDK 샘플
│   ├── README.md                     # CDK 전용 가이드
│   ├── basic-runtime/
│   ├── mcp-server-agentcore-runtime/
│   ├── multi-agent-runtime/
│   └── end-to-end-weather-agent/
└── terraform/                        # Terraform 샘플
    ├── README.md                     # Terraform 전용 가이드
    ├── basic-runtime/
    ├── mcp-server-agentcore-runtime/
    ├── multi-agent-runtime/
    └── end-to-end-weather-agent/
```

## 추가 리소스

- [Amazon Bedrock AgentCore 문서](https://docs.aws.amazon.com/bedrock/latest/userguide/agentcore.html)
- [AWS CloudFormation 문서](https://docs.aws.amazon.com/cloudformation/)
- [AWS CDK 문서](https://docs.aws.amazon.com/cdk/)
- [Terraform 문서](https://www.terraform.io/docs)
- [원본 튜토리얼](../01-tutorials/)
