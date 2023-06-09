# CloudTicket

## 소규모 행사 인원 관리를 위한 스마트 티켓 플랫폼

### [최종 발표 자료](그로쓰_09_L2k_2023-05-26_최종발표.pptx)

### **WHAT**

- 저희 팀은 아마추어인 **개인을 위한** 행사 주최 플랫폼이 없다는 점에 착안하여
- 개인이 누구든 구글 폼을 여는 것처럼 **‘쉽게’** 행사를 관리할 수 있지만, 대상자의 정보 수집이 전부인 구글 폼보다 **‘강력하게’** 행사를 **단 하나의 플랫폼에서 관리할 수 있는 서비스**를 개발했습니다.
- 해당 플랫폼으로 동아리 밴드 공연 등 소규모 행사부터 동아리 회계, 친구들간의 프라이빗 파티 등을 주최하는 것이 가능해질 것입니다.

### **WHY**

- 실제로 티켓 플랫폼이라고 하면 흔히 떠오르는 인터파크, 멜론티켓, 페스타 등의 기존 플랫폼은 **기관, 기업 등이 주최하는 대규모 영리 행사**에 초점을 맞춰 왔습니다.
- 그만큼 티켓 플랫폼은 활성화 되어 있지만
- **아마추어인 개인**이 동아리 공연 등 소규모 행사를 주최할 때 회계 관리, 티켓 발급, 그리고 참여자 관리까지 **간단하게 해낼 수 있는 플랫폼**은 존재하지 않았기 때문에 해당 수요를 타켓팅한 플랫폼을 개발했습니다.


## Architecture Diagram

![architecture diagram final](https://github.com/Capstone-L2K/CloudTicket/assets/84276596/446c838b-7040-4bff-b313-ff5e2e986019)

저희 팀은 AWS Lambda를 이용한 Serverless 아키텍처와 Django를 이용한 Infrastructure 서버 아키텍처로 서버를 구성했습니다. 서버리스 아키텍처에서 구현한 API는 Lambda 함수를 통해 모듈식 개발을 할 수 있으며, 이러한 이점은 소프트웨어 개발을 애자일하게 할 수 있도록 돕고, 추후 해당 서비스의 확장을 용이하게 합니다. 또한 티켓팅 시스템은 특정 시간에 사람이 많이 몰릴 수 있다는 점을 고려하여, SpringBoot로 개발 후 EC2 배포 및 Elastic Load Balancing을 이용해 트래픽 분산을 시도하게 됩니다. 프론트엔드에서는 React 를 사용한 SPA 를 구성해 CSR 방식으로 화면을 렌더링하며, AWS Cloudfront 에 동적 웹사이트를 호스팅하게 됩니다.

## 백엔드

### [백엔드 repository](https://github.com/Capstone-L2K/cloud-ticket-serverless)

AWS의 Lambda 함수, API gateway, S3, RDS 등을 이용하여 백엔드를 개발했습니다. 

github의 repository에는 기록 용도로 일부 Lambda 함수 코드만을 확인할 수 있습니다. 개발환경은 AWS 계정에 존재합니다. 


## 프론트엔드

### [프론트엔드 repository](https://github.com/Capstone-L2K/cloud-ticket-client)

REACT를 사용한 SPA 어플리케이션을 개발했습니다.
