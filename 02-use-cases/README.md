# 💡 Amazon Bedrock AgentCore 사용 사례

Amazon Bedrock AgentCore 샘플 저장소의 사용 사례 섹션에 오신 것을 환영합니다!

이 폴더에는 Amazon Bedrock AgentCore 기능을 적용하여 실제 비즈니스 문제를 해결하는 방법을 보여주는 엔드투엔드 애플리케이션이 포함되어 있습니다. 각 사용 사례는 상세한 설명 및 배포 지침과 함께 완전한 구현을 제공합니다.

## 🎯 주요 사용 사례

* **[AWS Operations Agent](./AWS-operations-agent/)**: Okta 인증 및 포괄적인 모니터링 기능을 갖춘 지능형 AWS 운영 어시스턴트
* **[Customer Support Assistant](./customer-support-assistant/)**: 메모리, 지식 베이스 통합 및 Google OAuth를 갖춘 프로덕션 준비 고객 서비스 에이전트
* **[DB Performance Analyzer](./DB-performance-analyzer/)**: PostgreSQL 통합을 통한 데이터베이스 성능 모니터링 및 분석 에이전트
* **[Device Management Agent](./device-management-agent/)**: Cognito 인증 및 실시간 모니터링을 갖춘 IoT 디바이스 관리 시스템
* **[Enterprise Web Intelligence Agent](./enterprise-web-intelligence-agent/)**: 경쟁 인텔리전스를 위한 브라우저 도구를 사용한 웹 연구 및 분석 에이전트
* **[Farm Management Advisor](./farm-management-advisor/)**: 식물 감지, 날씨 예보 및 관리 권장 사항을 제공하는 농업 자문 시스템
* **[Finance Personal Assistant](./finance-personal-assistant/)**: 다중 에이전트 워크플로 및 가드레일을 갖춘 개인 예산 관리
* **[Healthcare Appointment Agent](./healthcare-appointment-agent/)**: 환자 데이터 통합을 통한 FHIR 호환 의료 예약 스케줄링
* **[Local Prototype to AgentCore](./local-prototype-to-agentcore/)**: 로컬 개발에서 프로덕션 AgentCore 배포로의 마이그레이션 가이드
* **[Market Trends Agent](./market-trends-agent/)**: 브라우저 도구 및 메모리 통합을 통한 금융 시장 분석
* **[SRE Agent](./SRE-agent/)**: 다중 에이전트 LangGraph 워크플로를 갖춘 사이트 안정성 엔지니어링 어시스턴트
* **[Text to Python IDE](./text-to-python-ide/)**: AgentCore Code Interpreter를 사용한 코드 생성 및 실행 환경
* **[Video Games Sales Assistant](./video-games-sales-assistant/)**: Amplify 프론트엔드 및 CDK 배포를 갖춘 데이터 분석 어시스턴트

## 🏗️ 아키텍처 패턴

이러한 사용 사례는 다양한 아키텍처 패턴을 보여줍니다:

- **단일 에이전트**: 특정 작업을 위한 집중 솔루션
- **다중 에이전트**: 다양한 프레임워크를 사용한 협업 에이전트 워크플로
- **풀스택**: 프론트엔드, 백엔드 및 배포가 포함된 완전한 애플리케이션
- **통합**: 외부 시스템 및 API와의 연결
- **인증**: 다양한 ID 공급자(Cognito, Okta, Google, EntraID)

## 🚀 시작하기

각 사용 사례에는 다음이 포함됩니다:
- 완전한 소스 코드 및 구성
- 단계별 배포 지침
- 아키텍처 다이어그램 및 설명
- 테스트 및 검증 스크립트
- 정리 절차

요구 사항에 맞는 사용 사례를 선택하고 개별 README의 설정 지침을 따르세요.

## 🔗 관련 리소스

- [튜토리얼](../01-tutorials/) - AgentCore 기본 사항 배우기
- [통합](../03-integrations/) - 프레임워크 및 프로토콜 통합
- [AgentCore 문서](https://docs.aws.amazon.com/bedrock-agentcore/)
