## Global Route Manager

DNS을 기반으로 네트워크 트래픽을 다수의 서버로 분산(로드밸런싱) 해주는 서비스

> 특징

**세분화된 트래픽 분산을 통한 서비스 제공 품질 향상**

리소스 별로 처리하는 트래픽 양을 조정하거나 응답 비율을 다르게 설정하여 응답 시간을 단축하고 서비스 연속성을 강화할 수 있다.

- 리소스 가용성 및 연속성 확보<br>
: 리소스 상태 확인(Resource Health Check) 기능으로 문제가 생긴 리소스를 도메인 응답에서 제외할 수 있고 Active, Standby 리소스를 지정하여 Active 리소스에 장애가 발생하면
Standby 리소스가 응답하도록 설정할 수 있다.

- 콘솔 기반 설정 및 관리<br>
: 네이버 클라우드 플랫폼 콘솔에서 도메인을 입력하고 원하는 로드밸런싱 타입을 선택한 뒤 타입에 맞는 리소스를 추가할 수 있다.
Resource Health Check 기능도 쉽게 설정할 수 있으며 Global Route Manager 도메인에 속한 리소스의 상태(Status) 확인도 할 수 있다.

- 서비스 간 연계 가능<br>
: 네이버 클라우드 플랫폼의 Server, Load Balancer 서비스를 사용하는 고객은 Global Route Manager를 구성할 때 기존에 보유하고 있는 리소스를 추가하여 사용할 수 있다.
이 밖에 기존 보유하고 있는 도메인도 리소스로 추가할 수 있어 서비스 간 연계를 통해 시너지를 창출할 수 있다.

- 사용량에 따른 요금 부과<br>
: 구성된 도메인 개수, 추가한 Resource Health Check 리소스 개수, 쿼리 수에 따라 요금이 결정된다. 사용량에 따라 요금이 부과되므로 계획적으로 서비스를 이용할 수 있다.

> 상세 기능

<div data-v-4f192f4f="" data-table="true" class="on-top"><div data-v-4f192f4f="" class="scroll-body"><s data-v-4f192f4f="" class="top-arrow"></s><table data-v-4f192f4f="" style="width: 1200px;"><colgroup data-v-4f192f4f=""><col data-v-4f192f4f="" span="4" width="2"><col data-v-4f192f4f="" width="5"></colgroup><thead data-v-4f192f4f=""><tr data-v-4f192f4f=""><th data-v-4f192f4f="">로드 밸런싱 타입</th><th data-v-4f192f4f="" colspan="2">리소스 타입</th><th data-v-4f192f4f="">Health Check</th><th data-v-4f192f4f="">설명</th></tr></thead><tbody data-v-4f192f4f=""><tr data-v-4f192f4f=""><th data-v-4f192f4f="">
        Round Robin <br data-v-4f192f4f=""><a data-v-4f192f4f="" class="btn-arrow-right cp" style="text-decoration: none;">활용 사례 보기</a></th><td data-v-4f192f4f="" colspan="2">IP (Server 서비스 연계 가능)</td><td data-v-4f192f4f="">설정 가능</td><td data-v-4f192f4f="">최대 16개까지 리소스 추가 가능<br data-v-4f192f4f="">요청에 대해 공평하게 순차적으로 리소스가 응답</td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="" rowspan="2">
        Weighted <br data-v-4f192f4f=""><a data-v-4f192f4f="" class="btn-arrow-right cp" style="text-decoration: none;">활용 사례 보기</a></th><td data-v-4f192f4f="" colspan="2">IP (Server 서비스 연계 가능)</td><td data-v-4f192f4f="">설정 가능</td><td data-v-4f192f4f="" rowspan="2">
        최대 16개까지 리소스 추가 가능<br data-v-4f192f4f=""> 각 리소스별로 처리하는 트래픽 양에 대한 가중치를 주어 요청에 따른
        트래픽 분배 가능
      </td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="" colspan="2">Domain (Load Balancer 서비스 연계, 직접 도메인 입력 가능)</td><td data-v-4f192f4f="">설정 불가능</td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="">
        GeoLocation <br data-v-4f192f4f=""><a data-v-4f192f4f="" class="btn-arrow-right cp" style="text-decoration: none;">활용 사례 보기</a></th><td data-v-4f192f4f="" colspan="2">Domain (Load Balancer 서비스 연계, 직접 도메인 입력 가능)</td><td data-v-4f192f4f="">설정 불가능</td><td data-v-4f192f4f="">
        글로벌 서비스에 최적화된 로드밸런싱 타입<br data-v-4f192f4f="">사용자의 위치를 기준으로 대륙 혹은 국가 단위 분기 가능<br data-v-4f192f4f=""> IP
        대역을 기준으로 한 분기 설정 가능<br data-v-4f192f4f=""> Geo Map 메뉴를 통해 고객에게 꼭 맞는 Map을 손쉽게 구성 가능<br data-v-4f192f4f="">
        IP 대역 기준으로 CIDR Map을 구성 가능
      </td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="" rowspan="3">
        Fail Over<br data-v-4f192f4f=""><a data-v-4f192f4f="" class="btn-arrow-right cp" style="text-decoration: none;">활용 사례 보기</a></th><td data-v-4f192f4f="">Active</td><td data-v-4f192f4f="">IP (Server 서비스 연계 가능)</td><td data-v-4f192f4f="">설정 가능</td><td data-v-4f192f4f="" rowspan="3">
        Active, Standby 리소스를 지정하여 Active 리소스 장애 시 Standby 리소스가 응답<br data-v-4f192f4f="">
        Standby 리소스에는 IP Type과 Domain Type 혼용 불가<br data-v-4f192f4f="">
        Active, Standby에 각각 최대 16개까지 리소스 추가 가능
      </td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="" rowspan="2">Standby</td><td data-v-4f192f4f="">IP (Server 서비스 연계 가능)</td><td data-v-4f192f4f="">설정 가능</td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="">Domain (Load Balancer서비스 연계, 직접 도메인 입력 가능)</td><td data-v-4f192f4f="">설정 불가능</td></tr></tbody></table><!----></div></div>

> Resource Health Check 기능 지원

Resource Health Check 기능은 리소스 상태를 확인하는 기능으로 IP 타입으로 추가된 리소스에만 설정할 수 있다. 확인 주기는 60초, 180초, 300초 단위로 제공하며 Port는 제공되는 Port 외에
사용자가 직접 설정할 수도 있다. 프로토콜은 TCP, HTTP, HTTPS를 지원하며 HTTP, HTTPS일 경우에는 Forward Host와 Path를 직접 설정할 수 있다.

<table data-v-4f192f4f="" width="100%"><tbody data-v-4f192f4f=""><tr data-v-4f192f4f=""><th data-v-4f192f4f="" class="bt">주기</th><td data-v-4f192f4f="" colspan="2">30초, 60초, 180초, 300초</td></tr><tr data-v-4f192f4f=""><th data-v-4f192f4f="" rowspan="3">프로토콜</th><td data-v-4f192f4f="">TCP</td><td data-v-4f192f4f="">Port : 80, 8080, 443</td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="">HTTP</td><td data-v-4f192f4f="">Port : 80</td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="">HTTPS</td><td data-v-4f192f4f="">Port : 443</td></tr></tbody></table>

> Geo Map, CIDR Map 설정

Geo Map과 CIDR Map을 원하는 대로 구성하고 관리하여 대륙, 국가 단위별 분기 및 IP 대역 분기에 필요한 GeoLocation Type을 구성할 수 있다. GeoLocation Type을 신규로 생성할 때 미리 설정해둔
Map을 도메인 별로 불러와 활용할 수 있다. Geo Map은 Default Map을 제공한다.

**기본 제공되는 Geo Map**

<div data-v-4f192f4f="" data-table="true" class="mt-0"><div data-v-4f192f4f="" class="scroll-body"><s data-v-4f192f4f="" class="top-arrow"></s><table data-v-4f192f4f="" width="100%"><colgroup data-v-4f192f4f=""><col data-v-4f192f4f="" width="2"><col data-v-4f192f4f="" width="2"><col data-v-4f192f4f="" width="4"></colgroup><thead data-v-4f192f4f=""><tr data-v-4f192f4f=""><th data-v-4f192f4f="">Map 이름</th><th data-v-4f192f4f="">Zone</th><th data-v-4f192f4f="">포함된 대륙/국가</th></tr></thead><tbody data-v-4f192f4f=""><tr data-v-4f192f4f=""><th data-v-4f192f4f="" rowspan="7">DEFAULT_MAP</th><td data-v-4f192f4f="">NCP_KR</td><td data-v-4f192f4f="">South Korea</td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="">NCP_JP</td><td data-v-4f192f4f="">Japan, Taiwan</td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="">NCP_HK</td><td data-v-4f192f4f="">Hong Kong, Macau, Philippines, Viet nam</td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="">NCP_SG</td><td data-v-4f192f4f="">Asia, Oceania</td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="">NCP_DE</td><td data-v-4f192f4f="">Europe, Middle East(Iran, Iraq, Sauid), Africa</td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="">NCP_USW</td><td data-v-4f192f4f="">Alaska, Arizona, California, Colorado, Hawaii, Idaho, Montana, Nevada, New Mexico, Oregon, Utah, Washington, Wyoming</td></tr><tr data-v-4f192f4f=""><td data-v-4f192f4f="">NCP_USE</td><td data-v-4f192f4f="">North America, South America</td></tr></tbody></table><!----></div></div>

> Resource Health Check 로그 제공 (예정)

Global Route Manager 도메인과 도메인에 속한 리소스의 Resource Health Check 로그와 결과를 확인할 수 있다.
구성된 Global Route Manager는 기간을 선택해 도메인 단위로 조회하거나 원하는 리소스에 대한 결과만 검색해 로그를 확인할 수 있다.
