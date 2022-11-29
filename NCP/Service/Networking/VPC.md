## VPC(Virtual Network Cloud)

**고객 전용 네트워크를 구현할 수 있는 클라우드 서비스**

**기능**

- 전용 네트워크 사용: 다른 네트워크와 상호 간섭이 발생할 염려 없이 논리적으로 완전히 분리된 네트워크를 사용할 수 있다.
- 다양한 네트워크 토폴리지: VPC 내부에 Public Subnet 또는 Private Subnet 을 생성하여 고객 맞춤형 네트워크 환경을 조성할 수 있다. Subnet 을 생성한 후 서버, 데이터베이스와 같은 리소스를 안에 배치한다.
- 강력한 보안: ACG(Access Control Group) 와 Network ACL(Network Access Control List) 을 통해 네트워크의 접근을 제어한다. ACG 는 서버 단계의 접근을 제어하며, Network ACL 은 Subnet 단계의 접근을 제어한다.
- 외부 네트워크와의 보안 통신: VPC 와 고객 사이트 간 안전한 통신을 위해 Cloud Connect 와 Managed IPSec VPN 을 사용할 수 있다. 
- VPC 간 내부 통신: VPC Peering 을 사용해 다른 VPC 와 통신할 수 있다. 공인 IP 없이 내부 네트워크로 통신하기 때문에 비용의 효율성이 높아진다.


