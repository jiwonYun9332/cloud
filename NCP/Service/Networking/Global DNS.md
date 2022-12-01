## Global DNS

서비스 운영에 필요한 도메인을 간편하게 설정하고 관리할 수 있는 서비스

- 수월한 DNS 구축 및 관리<br>
: 별도의 DNS 인프라 구축, 솔루션 설치 및 업데이트, 서버 용량 및 성능 관리를 포함한 일체의 운영 관리가 필요하지 않고 웹 기반 콘솔에서 도메인을 추가하는 것만으로 자체 DNS를 구축하고 관리할 수 있다.

- 서비스 연속성 보장<br>
: 여러 대의 DNS 서버를 운영하여 1대의 DNS 서버에 장애가 발생하더라도 다른 DNS 서버에서 응답할 수 있는 구조를 제공하며 도메인 변경 작업을 할 경우에도 각 DNS 서버의 데이터가 빠르게 동기화되어 서비스 중단 없이 안정적으로 제공할 수 있다.

- 손쉬운 도메인 설정<br>
: 도메인은 소유하고 있지만 자체 DNS 서버가 없거나 DNS 구축 경험이 부족하더라도 웹 기반 콘솔에서 어려움 없이 도메인을 등록하고 관리할 수 있다. A, TXT, MX, SPF 등 다양한 리소스 레코드를 설정할 수 있고 대량의 데이터도 손쉽게 업로드할 수 있다.

- 도메인 보안 인증 체계 제공<br>
: Global DNS는 국제표준으로 자리 잡은 DNS Security Extensions(DNSSEC)를 지원하여 응답 데이터의 무결성을 보장한다. 단 한 번의 클릭만으로 손쉽게 DNSSEC 기능을 활성화 또는 비활성화할 수 있다. 전자서명을 위한 키 생성 및 교체는 네이버 클라우드 플랫폼에서 자동으로 수행한다.

**상세 기능**

> 최적의 글로벌 라우팅 방식

: 네이버 클라우드 플랫폼이 보유한 글로벌 Anycast 네트워크를 통해 네트워크 상황에 따라 응답 지연 시간이 가장 짧은 네임서버로 자동 연결한다. 이러한 라우팅 방식은 높은 가용성을 확보하고 최종 사용자에 빠른 응답을 제공하여 서비스 질을 높일 수 있다.

> 별칭(Alias) 레코드

: Global DNS에 구성한 도메인에 별칭 레코드를 매핑할 수 있다. 캐노니컬 네임 레코드(Canonical Name Record, CNAME)와 유사하게 동작하지만 example.com과 같은 루트 도메인에도 별칭(Alias) 레코드를 매핑할 수 있어 CNAME의 제약 사항을 해결할 수 있다.

> 간편한 마이그레이션

: 글로벌 DNS에 존 파일(Zone File)을 가져오는(Import) 것만으로 다른 서비스 또는 자체 DNS에서 운영하던 레코드를 마이그레이션 할 수 있다. 존 파일을 다른 네임서버로 이동할 수 있도록 서비스 중인 모든 레코드를 존 파일로 다운로드할 수 있다.

> 도메인별 질의 통계

: 서비스 중인 도메인별 질의에 대한 통계를 확인할 수 있어 비즈니스 사이트 트래픽의 증감 추이를 확인하고 운영에 참고할 수 있다.

> 리소스 레코드

<table data-v-4f192f4f="" style="width: 100%;"><caption data-v-4f192f4f="">
  </caption><colgroup data-v-4f192f4f=""><col data-v-4f192f4f="" width="20%"><col data-v-4f192f4f="" width="80%"></colgroup><thead data-v-4f192f4f=""><tr data-v-4f192f4f=""><th data-v-4f192f4f="">레코드</th><th data-v-4f192f4f="">설명</th></tr></thead><tbody data-v-4f192f4f=""><tr data-v-4f192f4f=""><th data-v-4f192f4f="">A 레코드</th><td data-v-4f192f4f="">
      가장 기본적인 유형으로 도메인 이름을 IP에 직접 매핑하는 레코드<br data-v-4f192f4f="">소유 도메인 및 그 하위 도메인의 IP 주소(IPv4) 지정 가능
      </td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="">AAAA(IPv6) 레코드</th><td data-v-4f192f4f="">
        A 레코드와 동일한 방식이나 A 레코드는 IPv4 주소 체계에서 사용되고 AAAA 레코드는 IPv6 주소 체계에서 사용<br data-v-4f192f4f=""> 소유 도메인 및 그 하위 도메인의 IPv6 주소 지정 가능
      </td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="">CNAME(도메인 별명) 레코드</th><td data-v-4f192f4f="">도메인 이름에 별명(alias)을 지정하는 레코드로 하나의 도메인 이름을 다른 도메인 이름으로 매핑<br data-v-4f192f4f=""> 단, CNAME 레코드는 다른 레코드와 공존 불가<br data-v-4f192f4f=""> CNAME 레코드는 다른 모든 유형의 레코드와 충돌하므로 CNAME 레코드를 사용하려면 다른 레코드를 삭제 필요</td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="">MX(메일 서버) 레코드</th><td data-v-4f192f4f="">
        사용자가 보유한 도메인과 하위 도메인 중 메일을 수신할 서버를 지정하는 레코드<br data-v-4f192f4f=""> Preference가 작을수록 높은 우선 순위를 가짐</td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="">SPF(스팸 처리 방지) 레코드</th><td data-v-4f192f4f="">
        보안 정책을 지정하여 수신한 메일에 표시된 발송자 정보와 실제 메일 서버에 있는 정보가 일치하는지 확인하는 메일 검증 레코드<br data-v-4f192f4f="">주로 스팸 메일을 방지하기 위해 스팸 메일을 송신한 서버의 IP 주소나 도메인 이름 등의 정보를 명시해 메일 주소 사칭 방지
      </td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="">TXT(도메인 설명) 레코드</th><td data-v-4f192f4f="">도메인에 텍스트 정보를 추가하여 유효한 도메인인지 판단하는 레코드<br data-v-4f192f4f=""> SPF 레코드와 같은 용도로 사용</td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="">SRV 레코드</th><td data-v-4f192f4f="">서비스를 호스팅 하는 서버의 위치(호스트 이름 및 포트 번호)를 저장하기 위해서 사용하는 레코드</td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="">CAA 레코드</th><td data-v-4f192f4f="">특정 도메인에 대한 인증서를 발급한 인증 기관(Certificate Authority, CA)을 확인하는 레코드<br data-v-4f192f4f=""> 잘못된 CA가 도메인에 대한 가짜 인증서를 발급하는 것 방지</td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="">DS 레코드</th><td data-v-4f192f4f="">
        Delegation Signer(DS)는 위임에 대한 서명자(signer)라는 뜻으로 DNSSEC에서 서명이 있는 영역을 식별하는 데 필요한 데이터를 저장하는 레코드
      </td></tr></tbody>
</table>











