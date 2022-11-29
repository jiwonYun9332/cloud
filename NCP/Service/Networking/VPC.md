## VPC(Virtual Network Cloud)

**고객 전용 네트워크를 구현할 수 있는 클라우드 서비스**

**제공 기능**

- 전용 네트워크 사용: 다른 네트워크와 상호 간섭이 발생할 염려 없이 논리적으로 완전히 분리된 네트워크를 사용할 수 있다.
- 다양한 네트워크 토폴리지: VPC 내부에 Public Subnet 또는 Private Subnet 을 생성하여 고객 맞춤형 네트워크 환경을 조성할 수 있다. Subnet 을 생성한 후 서버, 데이터베이스와 같은 리소스를 안에 배치한다.
- 강력한 보안: ACG(Access Control Group) 와 Network ACL(Network Access Control List) 을 통해 네트워크의 접근을 제어한다. ACG 는 서버 단계의 접근을 제어하며, Network ACL 은 Subnet 단계의 접근을 제어한다.
- 외부 네트워크와의 보안 통신: VPC 와 고객 사이트 간 안전한 통신을 위해 Cloud Connect 와 Managed IPSec VPN 을 사용할 수 있다. 
- VPC 간 내부 통신: VPC Peering 을 사용해 다른 VPC 와 통신할 수 있다. 공인 IP 없이 내부 네트워크로 통신하기 때문에 비용의 효율성이 높아진다.

**클라우드 환경 사양**

| 항목 | 지원 사양 |
| ------------ | ------------- |
| 리전(존) | 한국, 싱가포르  |
| Classic | 미지원  |
| VPC | 지원 |
| 언어 | 한국어, 영어, 일본어, 중국어 |

**기본 사양**

| 항목 | 기준 | 제공 사양 |
| ------------ | ------------- | ------------- |
| VPC 개수 | 리전 | 3개 |
| Subnet 개수 | VPC | 200개 |
| IP 개수(IPv4) | VPC | /16-28(65,536개~16개) |
| NAT Gateway 개수 | 존 | 1개 |
| Network ACL 개수 | VPC | 200개 |
| Network ACL 규칙 개수 | Network ACL | 40 개 |
| ACG 개수 | VPC | 500개 |
| ACG 규칙 개수 | ACG | 50개 |
| ACG 적용 개수 | Network Interface | 3개 |
| Route Table 개수 | VPC | 200개 |
| Route Table 규칙 개수 | Route Table | 50개 |
| VPC Peering 개수 | VPC | 20개 |

**NACL, ACG**

![NCP/Service/Networking/images/1_vpc.png](https://github.com/jiwonYun9332/cloud/blob/22e8b34ca67557b2590b0d1563bec470d7edb2d2/NCP/Service/Networking/images/1_vpc.png))

| 구분 | ACG | NACL |
| ------------ | ------------- | ------------- |
| 적용 대상 | 서버의 접근 제어 | 서브넷의 접근 제어
| 지원 규칙 | 허용(Allow) | 허용 및 거부(Allow/Deny)
| 상태 저장 여부 | 상태 저장<br>(규칙에 관계없이 반환 트래픽이 자동으로 허용됨) | 상태 비저장<br>(반환 트래픽이 규칙에 의해 명시적으로 허용되어야 함)
| 적용 방법 | ACG 를 서버의 NIC 에 적용 | 서브넷에 있는 모든 서버에 자동 적용됨 |

> VPC 피어링을 이용한 VPC 간 통신

목적에 따라 VPC 를 여러 개 운영할 경우 VPC 간 통신이 빈번하게 발생할 수 있다. 가장 일반적인 VPC 간 통신은 공인 IP를 기반으로 하는 것이지만 인터넷 기반 통신은 외부 상황에 따라 성능 저하 및 과다한 통신 요금이 발생할 수 있다. VPC 피어링을 이용하면 사설 IP를 기반으로 통신할 수 있어 서비스를 공용 인터넷에 노출하는 일 없이 안전한 통신 수단을 확보할 수 있다.

> Virtual Private Gateway 를 통한 하이브리드 환경 구성

Virtual Private Gateway 를 사용하여 네이버 클라우드 플랫폼과 고객의 온-프레미스 데이터 센터 간 제공되는 회선의 이중화가 가능해 안정적인 하이브리드 환경을 구성할 수 있다. 2개의 IPSec VPN 과 2개의 Cloud Connect 회선, 혹은 1개의 IPSec VPN 과 1개의 Cloud Connect 간에 이중화가 가능하며, Active-Standby 형태로 동작하게 된다.

> 라우팅을 통한 네트워크 흐름 제어

VPC 상에서 복잡한 네트워크 환경을 구성하기 위해 네트워크 라우팅이 필요한 경우 VPC 내에서 동작하는 고유의 라우팅 기능을 통해 외부 연계 네트워크 및 내부 사설 통신 간 흐름을 제어할 수 있습니다.

> VPC Flow Logs 제공

서버의 네트워크 인터페이스에서 송수신되는 네트워크 트래픽에 대해 ACG 를 기반으로 정보를 수집하는 기능을 제공한다. 수집 후 데이터는 오브젝트 스토리지에 저장된다. 단 실시간 로깅이 아닌 15분 가량 지연이 발생할 수 있다.

> 시나리오 1

서브넷에 인터넷 게이트웨이(Internet Gateway)를 연결하여 프론트엔드 전용 서브넷을 구성할 수 있다.




