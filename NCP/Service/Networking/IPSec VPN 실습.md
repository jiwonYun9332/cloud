## IPSEC VPN 실습


**Cloud <-> Cloud 간 IPSec Tunnling 연결**


> 클라우드 환경설정

## **A 계정 환경설정**

### 1. VPC 생성

VPC Name: ipsec-vpc-a

IP 주소 범위: 192.168.65.0/24

### 2. Subnet 생성

Subnet Name: ipsec-subnet-a

Internet Gateway 전용 여부: Y (Public)

### 3. Server 생성

Server Name: ipsec-server-a

OS: CentOS 7.8-64

### 4. ACG Accept 규칙 설정

TCP,UDP 0.0.0.0/0 1-65535

ICMP 0.0.0.0/0 

### 5. Virtual Private Gateway 설정

Virtual Private Gateway Name: ipsec-vpg-a

Virtual Private Gateway Group Name: ipsec-vpgg-a

### 6. IPSec VPN 생성

IPSec VPN Name: ipsec-vpn-a

IPSec VPN Tunnel Name: ipsec-vpn-tunnel-a

Peer IP: b계정 ipsec-vpn

Local Network: 192.168.65.0/24

Remote Network: 192.168.75.0/24

IKE Version: IKEv2

IKE Negotiation Mode: main

IKE Pre-sharedkey: ***

IPSec Proposal: aes-128

DH-Group: 5

Hash: sha256

Lifetime: 3600

DPD Retry Interval: 10/Second

DPD Retry Count: 2

## **B 계정 환경설정**

### 1. VPC

VPC Name: ipsec-vpc-b

IP 주소 범위: 192.168.75.0/24

### 2. Subnet

Subnet Name: ipsec-subnet-b

Internet Gateway 전용 여부: Y (Public)

### 3. Server 

Server Name: ipsec-server-b

OS: CentOS 7.8-64


### 4. ACG Accept 규칙 설정

TCP,UDP 0.0.0.0/0 1-65535

ICMP 0.0.0.0/0 

### 5. Virtual Private Gateway 설정

Virtual Private Gateway Name: ipsec-vpg-b

Virtual Private Gateway Group Name: ipsec-vpgg-b

### 6. IPSec VPN 생성

IPSec VPN Name: ipsec-vpn-b

IPSec VPN Tunnel Name: ipsec-vpn-tunnel-b

Peer IP: a계정 ipsec-vpn

Local Network: 192.168.75.0/24

Remote Network: 192.168.65.0/24

IKE Version: IKEv2

IKE Negotiation Mode: main

IKE Pre-sharedkey: ***

IPSec Proposal: aes-128

DH-Group: 5

Hash: sha256

Lifetime: 3600

DPD Retry Interval: 10/Second

DPD Retry Count: 2
