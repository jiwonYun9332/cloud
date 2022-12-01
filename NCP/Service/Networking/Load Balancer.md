## Load Balancer

서버 성능과 부하량을 고려하여 네트워크 트래픽을 다수의 서버로 분산해 주는 서비스

**365일 중단 없는 안정적인 서비스 제공**

특정 서버에 발생한 부하를 분산해 서버 가용성, 응답 시간을 최적화함으로써 무정지 서비스를 제공할 수 있다.

- 높은 가용성 보장<br>
로드 밸런서에 연결된 일부 서버에 장애가 발생할 경우 자동으로 해당 서버의 부하를 다른 서버로 분산하여 서비스가 중단되지 않도록 처리합니다. 이미 로드 밸런서에 반영된 서버라도 다른 로드 밸런서에 다중으로 추가 설정할 수 있습니다.

- 관리 콘솔 및 개발용 API 제공
웹네이버 클라우드 플랫폼 콘솔에서 어려움 없이 로드 밸런서를 생성하고 설정을 관리할 수 있고, 개발용 RESTful API도 제공하여 편리하게 설정할 수 있습니다. 또한 모니터링 기능을 통해 로드 밸런서별 현황을 확인할 수 있습니다.

- 암호화 처리를 통한 보안 강화
TLS v1.0, TLS v1.1, TLS v1.2 등 암호화 통신을 지원하여 네트워크 과정에서 발생할 수 있는 보안 문제에 대응할 수 있습니다. 또한 SSL Offloading 기능으로 서버 대신 암복호화를 처리하여 서버의 부하를 최소화할 수 있습니다. HTTPS/SSL Listener를 사용할 경우 SSL 인증서를 로드 밸런서에 설정하면 연결된 개별 서버에 SSL 인증서를 설정하지 않아도 됩니다. Listener 당 최대 25개의 SSL 추가인증서 설정이 가능합니다.

- 상황별 로드 밸런싱 알고리즘 지원
서버 부하 분산 방식으로 순환 순서 방식(Round Robin), 최소 연결 방식(Least Connection), IP 해시 방식(Source IP Hash) 3가지를 제공하여 상황에 맞는 방식을 선택해 사용할 수 있도록 지원합니다.

## Classic

Classic LB

**지원 기능**

- SSL 인증 및 암호화 설정<br>
공인 CA에서 발급받은 SSL 인증서를 Certificate Manager에 등록하여 간단하게 로드 밸런서에 적용할 수 있습니다. 인증서의 유효기간을 확인하여 인증서가 만료되기 전에 콘솔에 등록된 고객의 연락처로 자동 통보합니다.

- Load Balancer 포트 설정<br>
여러 개의 로드 밸런서 규칙을 동시에 설정할 수 있다. 주의할 점은 서버 포트의 경우 다른 로드 밸런서 규칙의 서버 포트와 동일하게 설정할 수 있으나 로드밸런서 규칙을 설정할 때는 다른 로드 밸런서 규칙의 포트와 다르게 설정해야 한다.

- Load Balancer 모니터링<br>
서버 모니터링과 마찬가지로 로드 밸런서에 대한 기본 모니터링 정보를 제공받을 수 있다. 모니터링 정보 수집 주기는 1분, 5분, 2시간, 1일 단위로 선택할 수 있다. 네트워크 로드 밸런서 모니터링은 Concurrent Connection, 초당 Connection, Traffic In, (Un)Available hosts 등
5가지 항목의 정보를 제공한다. 애플리케이션 로드 밸런서는 Traffic Out 을 포함하여 6가지 항목을 제공합니다.

- Load Balancer 관리<br>
로드 밸런서 생성 후 Connection Idle Timeout 또는 Keep-Ailve 설정을 변경할 수 있다. Connection Idle Timeout 은 로드 밸런서와 연결을 유지하는 시간으로 일반적으로 해당 시간이 지나면 연결이 강제로 해제된다. Long transaction 을 지원하는 애플리케이션이 필요하다면
Connection Idle Timeout 의 옵션을 조절해 연결 시간을 설정한다. 연결을 일정 시간 동안 유지하면서 다시 연결을 요청할 때, HTTP Keep-Alive 옵션을 사용하면 기존 연결을 재사용할 수 있다.

## VPC

Network LB (TCP, DSR 지원)

Network Proxy LB (TCP, DSR 지원안함)

Application LB (HTTP/HTTPS)

**지원기능**

- TCP 고성능 분산 처리 ( 네트워크 로드밸런서 )<br>
네트워크 로드 밸런서는 초당 연결 수 기준 최소 100,000 개에서 최대 400,000 개까지 성능을 보장하는 단계별 상품을 제공하여 고객 서비스 규모에 최적화된 분산 처리 성능을 제공한다.
또한 고객 서버에서 직접 응답하는 기능(Direct Server Return, DSR)을 구현하여 트래픽 분배만을 수행함으로써 보다 빠르고 효율적인 서비스를 이용할 수 있다.

- TCP 세션 관리 ( 네트워크 프록시 로드밸런서 )<br>
: 네트워크 프록시 로드 밸런서는 프록시 방식의 통신을 제공하여 세션 유지가 필요한 TCP 기반 애플리케이션에 이용할 수 있고, 애플리케이션 로드 밸런서와 동일한 부하 분산 알고리즘을 적용할 수 있다.

- SSL 인증 및 암호화 설정 ( 애플리케이션 로드밸런서, 네트워크 프록시 로드밸런서 )<br>
: 웹 기반의 콘솔에서 SSL 인증서를 추가하고 Certificate Manager와 연동하여 편리하게 관리할 수 있습니다. TLSv1, TLSv1.1, TLSv1.2 등 SSL 프로토콜 및 SSL 암호화 스위트(Cipher suite)를 설정하여 암호화할 수 있습니다. Listener 당 최대 25개의 SSL 추가인증서 설정이 가능합니다.

- 다양한 서버 부하 분산 방식 ( 애플리케이션 로드밸런서, 네트워크 프록시 로드밸런서 )<br>
  - Round Robin
  - Least Connection
  - Source IP Hash

- L7(Application Layer) 기능 제공( 애플리케이션 로드밸런서 )<br>
HTTP/HTTPS 트래픽의 패킷 헤더를 기반으로 애플리케이션 계층에서 로드를 분산한다. 로드 밸런서의 리스너에 Host Header 기반 분기 처리, URL Path Patten 기반 분기 처리, 가중치 기반 분기 처리, Redirection 응답 처리와 같은 규칙이 지원되어 클라이언트의 요청을 보다 세분화하여 서버에 전달할 수 있고 이를 바탕으로 고급 서비스를 구성할 수 있다.

- Load Balancer 모니터링<br>
서버 모니터링과 마찬가지로 로드 밸런서에 대한 기본 모니터링 정보를 제공받을 수 있다. 모니터링 정보 수집 주기는 1분, 5분, 2시간, 1일 단위로 선택할 수 있다. 네트워크 로드밸런서 모니터링은 Concurrent Connection, Traffic In, (Un)Available hosts 등 5가지 항목의 정보를 제공한다. 애플리케이션 로드 밸런서는 Traffic Out 을 포함하여 6가지 항목을 제공한다.

- Load Balancer 포트 설정<br>
여러 개의 포트밸런서 규칙을 동시에 설정할 수 있다.

**Load Balancer 타입별 기능 비교**

| 기능 | Network Load Balancer | Network Proxy Load Balancer | Application Load Balancer |
|  --- | --- | --- | --- |
| 프로토콜 | TCP | TCP, TLS | HTTP, HTTPS |
| 상태 확인 | O | O | O |
| 로깅 | X | O | O |
| Direct Server Return(DSR) | O | X | X |
| 같은 인스턴스의 여러 포트로 로드 밸런싱 | X | X | O |
| HTTP 2.0 지원 | N/A | N/A | O |
| 경로 기반 라우팅 | N/A | N/A | O |
| SSL 오프로드 | X | O | O |
| 고정 세션 | O | X | O |



















