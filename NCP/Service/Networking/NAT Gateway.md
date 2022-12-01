## NAT Gateway

다수의 비공인 IP 주소를 하나의 공인 IP 주소로 변환하는 데 필요한 서비스

### 대표 공인 IP 를 이용한 외부 서버와의 보안 접속

: 여러 대의 비공인 IP 를 가진 서버가 외부 서버와 통신할 수 있도록 연결하며 외부로부터의 직접 접근을 막아 보안을 유지한다.

> 변하지 않는 대표 공인 IP

: NAT Gateway 를 통해 외부로 접속할 때 사용되는 대표 공인 IP 는 해당 NAT Gateway 가 독점적으로 사용하는 IP 로서 변하지 않으며 다른 고객과 공유되지 않는다. 이를 통해 외부 서버에서는 방화벽을 간편하게 설정할 수 있고 내부 서버에서는 보안을 강화할 수 있다.

> 공인 IP 생성 비용 절약 가능

: NAT Gateway 하나로 여러 서버를 연결하기 때문에 외부 접속을 위해 보유하고 있는 서버마다 별도의 Public IP 를 생성하지 않아도 된다.

> Auto Scaling 과 연계된 자동 설정

: NAT Gateway 를 사용하고 있으면서 Auto Scaling 을 적용하여 서버를 증설할 경우 기존에 사용하던 NAT Gateway 설정