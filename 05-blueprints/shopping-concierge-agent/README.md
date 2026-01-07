# 쇼핑 에이전트 개요

AWS Bedrock AgentCore, Amplify 및 React로 구축된 쇼핑 지원 기능을 갖춘 AI 기반 컨시어지 에이전트입니다.

쇼핑 어시스턴트는 리뷰 조사, 기능 정보 및 사용자 프로필을 기반으로 한 개인화된 추천을 포함한 모든 쇼핑 관련 쿼리를 전문으로 합니다. 항목을 비교하고 가격을 제공하며 리뷰를 표시하고 모든 항목이 사용자 선호도 및 제약 조건과 일치하는지 확인합니다.

## 사용 사례 세부 정보
| 정보                | 세부 사항                                                    |
|---------------------|--------------------------------------------------------------|
| 사용 사례 유형      | 에이전트 결제                                                |
| 에이전트 유형       | 다중 에이전트                                                |
| 사용 사례 구성 요소 | 도구(MCP 기반), 관찰 가능성(로그, 메트릭)                    |
| 사용 사례 분야      | FSI                                                          |
| 예제 복잡도         | 고급                                                         |
| 사용된 SDK          | Strands, MCP                                                 |

## 기능

- **쇼핑 어시스턴트** - 제품 검색 및 추천(SERP API 통합 필요)
- **장바구니 및 결제** - Visa 토큰화 지원을 통한 장바구니 관리(기능 플래그 활성화)
- **대화 메모리** - 세션 간 지속적인 채팅 기록
- **실시간 스트리밍** - 도구 사용 표시기가 있는 실시간 에이전트 응답
- **안전한 인증** - JWT 기반 인증을 사용한 AWS Cognito

## 시작하기

전체 배포 지침, 사전 요구 사항, 문제 해결 및 구성은 **[배포 가이드](DEPLOYMENT.md)**를 참조하세요.

### 빠른 배포
[개발 가이드 섹션으로 이동](./DEPLOYMENT.md#Quick_Start)

## 프로젝트 구조

```
sample-concierge-agent/
├── amplify/                    # AWS Amplify 백엔드(Cognito, DynamoDB, GraphQL)
├── concierge_agent/           # 에이전트 코드 및 Docker 컨테이너
│   ├── Dockerfile
│   └── code/                  # Python 에이전트 구현
├── infrastructure/            # 에이전트 배포를 위한 CDK 인프라
├── documents/                 # 지식 베이스 문서
├── web-ui/                    # React 프론트엔드 애플리케이션
└── scripts/                   # 배포 및 설정 스크립트
```

## 문서

- **[배포 가이드](DEPLOYMENT.md)** - 전체 배포 지침, 사전 요구 사항 및 문제 해결
- **[Visa 로컬 설정](docs/VISA_LOCAL_SETUP.md)** - 실제 Visa API 테스트를 위한 설정
- **[인프라 README](infrastructure/README.md)** - CDK 인프라 세부 정보
- **[프론트엔드 모의 모드](FRONTEND_MOCK_MODE.md)** - 백엔드 없이 UI 테스트
- **[Visa 문서](visa-documentation/README.md)** - Visa API 문서

## 데이터 흐름
![쇼핑 데이터 흐름](docs/shopping_data_flow.png)

## 아키텍처
![쇼핑 아키텍처](docs/Shopping_Agent_VISA.png)

## 데모
![쇼핑 에이전트 데모](docs/demo.gif)

## 구성

다음을 포함한 자세한 구성:
- API 키(SERP API, Visa API)
- Visa 결제 통합(모의 vs 실제)
- 로컬 개발 설정
- 환경 변수
- 정리 지침

**[배포 가이드](DEPLOYMENT.md)**를 참조하세요.

> [!NOTE]
> 이 프로젝트는 교육 목적을 위한 샘플 구현으로 제공되며 프로덕션 준비가 되어 있지 않습니다.
> 조직의 정책 및 AWS 서비스 약관을 준수하는지 확인하세요.
