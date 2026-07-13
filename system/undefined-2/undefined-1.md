# 서버 관제 결과 로그 항목 및 비정상 판단 기준

서버 관제 항목들을 체크한 결과를 취합한 로그에 대한 설명입니다. 비정상인 항목이 있을 경우에는 로그 내용을 메일로 발송하여 서버 이상을 담당자에게 알립니다.

* **로그의 위치 : /plusdrive/log/monitoring\_log/default\_log**

> - **정상일 경우에 로그 파일명** **: Server\_monitoring\_년월일\_시분초.html**
> - **비정상인 경우 로그 파일명 : Alert\_server\_monitoring\_년월일\_시분초.html**

* **로그 양식**

<figure><img src="../../.gitbook/assets/img_000 (228).png" alt=""><figcaption></figcaption></figure>

* **메일 수신자 설정**

> - **설정 파일 : /plusdrive/conf/monitoring.conf**
> - **설정 항목 : recieve\_server\_check\_mail\_list**
>
> &#x20;     ex) recieve\_server\_check\_mail\_list support\_cloudoc@net-id.co.kr
>
> &#x20;           (여러 개의 수신 메일을 설정 시에는 tab으로 구분하여 등록)

### <mark style="color:$primary;">관제 항목 및 비정상 판단 기준</mark>

관제 항목별 기준 값은 설정파일로 저장되어 있습니다. 기준 값을 초과할 경우 비정상으로 판단하여 로그에 붉은색으로 표시합니다. 이 기준 값은 서버 운영 상황에 맞게 변경이 가능합니다.

* **설정 파일: /plusdrive/conf/monitoring.conf**
* **관제 항목 및 기준 값**

<table data-search="false"><thead><tr><th width="109">확인 항목</th><th width="121">확인 내용</th><th width="263">설정 및 기본 기준 값</th><th valign="top">Text비정상 판단 기준</th></tr></thead><tbody><tr><td><strong>Apache</strong></td><td>서비스 정상 여부</td><td><ul><li>설정된 Apache 포트와 통신 확인</li><li>pdrive.conf의 file_http_port에 설정된 Apache 포트로 통신 (기본 80)</li></ul></td><td valign="top">Apache 포트(기본80)로 응답 유무 체크하여 무응답 및 오류가 발생할 경우</td></tr><tr><td></td><td>Thread, CPU, RAM 사용량</td><td><ul><li>Apache 서비스 체크 Thread 기준값check_value_apache_thread 500</li><li>Apache 서비스 체크 CPU 기준값check_value_apache_cpu 100</li><li>Apache 서비스 체크 Memory 기준값check_value_apache_memory 20480</li></ul></td><td valign="top">Thread, CPU, RAM 사용량이 서버 설정 값을 초과할 경우</td></tr><tr><td><strong>Tomcat</strong></td><td>서비스 정상 여부</td><td><ul><li>설정된 Tomcat 포트와 통신 확인</li><li>monitoring.conf의 tomcat_port에 설정된 Tomcat 포트로 통신 (기본 8085)</li></ul></td><td valign="top">Tomcat 포트(기본8085)로 응답 유무 체크하여 무응답 및 오류가 발생할 경우</td></tr><tr><td></td><td>Thread, CPU, RAM 사용량</td><td><ul><li>Tomcat 서비스 체크 Thread 기준값check_value_tomcat_thread 500</li><li>Tomcat 서비스 체크 CPU 기준값check_value_tomcat_cpu 70 </li><li>Tomcat 서비스 체크 Memory 기준값check_value_tomcat_memory 10240</li></ul></td><td valign="top">Thread, CPU, RAM 사용량이 서버 설정 값을 초과할 경우</td></tr><tr><td><strong>Mod_jk</strong></td><td>netstat 상태 확인</td><td><ul><li>mod_jk 체크 Timewait 기준값</li></ul><p>     check_value_modjk_timewait 300</p><ul><li>mod_jk 체크 Closewait 기준값check_value_modjk_closewait 200</li><li>mod_jk 체크 Established 기준값check_value_modjk_established 600</li></ul></td><td valign="top">netstat 에서 8009 포트의 TIME_WAIT, CLOSE_WAIT, ESTABLISHED 항목의 수가 서버 설정 값을 초과할 경우</td></tr><tr><td><strong>Database</strong></td><td>클라우독 DB 확인</td><td><p>pdrive.conf, pdrive_log.conf의 아래 내용에 기입된 정보로 DB연결 확인</p><p></p><p># DB 서버 IP</p><p> database_server </p><p></p><p># DB 접속계정</p><p> database_user </p><p></p><p># DB password </p><p> database_password </p><p></p><p># DB name</p><p> database_dbname </p><p></p><p># DB 종류</p><p> database_type </p><p></p><p># DB Port </p><p> database_port</p></td><td valign="top">클라우독 DB에 연결을 시도하여 연결이 되지 않을 경우</td></tr><tr><td></td><td>인사연동 DB 확인</td><td><p>조직도 연동 진행 시 사용</p><p>group.conf에 기입된 정보로 DB 연결 확인</p><p></p><p> # DB 서버 IP </p><p>orgchart_server</p><p></p><p># DB Port </p><p>orgchart_server_port</p><p></p><p># DB 접속계정 orgchart_server_user</p><p></p><p># DB password orgchart_server_password</p><p></p><p># DB name orgchart_server_dbname</p><p></p><p># DB 종류 orgchart_server_dbtype</p><p></p><p>로그인 연동 진행 시 사용 custom_login.conf에 기입된 정보로 DB 연결 확인 </p><p></p><p># DB 서버 IP </p><p>login_server</p><p></p><p># DB Port </p><p>login_port </p><p></p><p># DB 접속계정 </p><p>login_db_user </p><p></p><p># DB password </p><p>login_db_pass </p><p></p><p># DB name </p><p>login_db_name </p><p></p><p># DB 종류 </p><p>login_db_type</p></td><td valign="top">인사연동 DB에 연결을 시도하여 연결이 되지 않을 경우</td></tr><tr><td><strong>OS</strong></td><td>CPU, Memory, Disk 사용량</td><td><ul><li>디스크 사용률(%) 기준값</li></ul><p>      check_value_hdd 95</p><p></p><ul><li>전체 CPU 사용률(%) 기준값</li></ul><p>       check_value_cpu 100</p><p></p><ul><li>전체 Memory 사용률(%) 기준값</li></ul><p>      check_value_ram 99</p><p></p><ul><li>전체 Swap 사용률(%) 기준값</li></ul><p>      check_value_swap 90</p></td><td valign="top">CPU, Memory, Disk 사용량이 서버 설정 값을 초과할 경우</td></tr><tr><td></td><td>netstat 상태 확인</td><td><ul><li>통신 상태 체크 Closewait 기준값</li></ul><p>      check_value_closewait 1000</p><p></p><ul><li>통신 상태 체크 Timewait 기준값</li></ul><p>       check_value_timewait 5000</p></td><td valign="top">netstat 에서 전체 TIME_WAIT, CLOSE_WAIT 항목의 수가 서버 설정 값을 초과할 경우</td></tr></tbody></table>

### <mark style="color:$primary;">Apache 비정상 예상 원인</mark>

#### 서비스

Apache 서비스가 응답을 하지 않거나 서비스가 종료되어 응답할 수 없는 경우일 수 있습니다.

| <p><strong>응답 없음의 예상되는 원인</strong></p><p></p><ol><li>요청 처리 지연으로 Apache Thread가 Full이되어 더 이상 응답을 받을 수 없을 경우</li><li>Apache의 서버엔진 모듈의 오류로 강제 종료되는 경우</li></ol> |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ |

원인 분석 시 참고: &#x20;

* **기타 서비스 로그 종류 및 오류 내용**의 목차 [**Apache 로그**](undefined-2.md#apache)
* [**서버엔진 로그 예시 및 설명**](undefined-3.md)

#### Thread 수

Apache 요청 처리가 지연되는 경우 또는 요청이 많을 경우, 임계치보다 높아질 수 있습니다.

| <p><strong>요청 처리 지연의 예상되는 원인</strong></p><p></p><ol><li>서버의 CPU, 메모리, 디스크 및 네트워크 대역폭에 영향을 받을 경우 지연됨</li><li>웹 응용 프로그램이 처리하는 작업, 데이터베이스 연결 및 처리, 파일 업로드 등이 지연될 경우</li><li>인터넷 연결의 문제, 대량의 요청, DDoS 공격 등이 지연을 유발함</li></ol> |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

원인 분석 시 참고:&#x20;

* [**Apache 상태 서버 관제 로그 항목 및 비정상 판단 기준**](apache.md)

#### CPU 사용률

Apache CPU 사용률이 임계치보다 증가하는 경우 Apache 서비스 확인이 필요합니다.

| <p><strong>Apache CPU 증가의 원인</strong></p><p></p><ol><li>트래픽 증가로 인해 처리해야 하는 요청이 증가</li><li>무한루프로 인해 불필요한 작업이 계속 실행되는 경우</li><li>서버 메모리 부족하여 서버 성능 저하될 경우</li><li>서버 악성코드 감염</li></ol> |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

원인 분석 시 참고: &#x20;

* [**Apache 상태 서버 관제 로그 항목 및 비정상 판단 기준**](apache.md)
* **기타 서비스 로그 종류 및 오류 내용**의 목차 [**Apache 로그**](undefined-2.md#apache)
* [**서버엔진 로그 예시 및 설명**](undefined-3.md)

#### 메모리

Apache 메모리 사용률이 임계치보다 증가하는 경우 Apache 서비스 확인이 필요합니다.

| <p><strong>Apache 메모리 증가의 원인</strong> </p><p></p><ol><li>트래픽 증가로 인해 처리해야 하는 요청이 증가</li><li>무한루프로 인해 불필요한 작업이 계속 실행되는 경우</li><li>메모리 누수</li></ol> |
| ------------------------------------------------------------------------------------------------------------------------------------------------ |

원인 분석 시 참고: &#x20;

* [**Apache 상태 서버 관제 로그 항목 및 비정상 판단 기준**](apache.md)
* **기타 서비스 로그 종류 및 오류 내용**의목차 [**Apache 로그**](undefined-2.md#apache)
* [**서버엔진 로그 예시 및 설명**](undefined-3.md)

### <mark style="color:$primary;">Tomcat 비정상 예상 원인</mark>

#### 서비스

Tomcat 서비스 이상 또는 네트워크 장애로 인해 통신 안될 경우 응답할 수 없는 경우일 수 있습니다.

| <p><strong>응답 없음의 예상되는 원인</strong> </p><p></p><ol><li>메모리 부족으로 인해 서비스 종료된 경우 </li><li>요청이 많아져서 Thread 부족한 경우 </li><li>방화벽 또는 네트워크 장애로 인해 통신이 안될 경우</li></ol> |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ |

원인 분석 시 참고: &#x20;

* **기타 서비스 로그 종류 및 오류 내용**의목차 [**Tomcat 로그**](undefined-2.md#tomcat)

#### <mark style="color:$primary;">Thread 수</mark>

Tomcat 요청이 많거나 지연되는 경우, 임계치보다 높아질 수 있습니다.

| <p><strong>Thread 증가의 원인</strong> </p><p></p><ol><li>요청 처리량의 증가하여 처리해야 할 요청이 증가됨</li><li>DB와 같은 외부 자원에서 응답 지연되어 Thread가 대기하고 있어 증가됨</li></ol> |
| --------------------------------------------------------------------------------------------------------------------------------------------- |

원인 분석 시 참고:&#x20;

* [**Tomcat Thread 서버 관제 로그 항목 및 비정상 판단 기준**](tomcat-thread.md)

#### CPU 사용률

Tomcat의 CPU 사용률이 임계치보다 증가하는 경우 Tomcat 서비스 확인이 필요합니다.

| <p><strong>Tomcat CPU 증가의 원인</strong></p><p></p><ol><li>Tomcat이 처리하는 요청 증가</li><li>Thread 부족하여 요청 처리가 대기하면서 증가</li><li>메모리 부족으로 인하여 GC 발생으로 인한 증가</li></ol> |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- |

원인 분석 시 참고:  &#x20;

* [**Tomcat Thread 서버 관제 로그 항목 및 비정상 판단 기준**](tomcat-thread.md)
* **기타 서비스 로그 종류 및 오류 내용의** 목차 [**Tomcat 로그**](undefined-2.md#tomcat)

#### 메모리

Tomcat의 메모리 사용률이 임계치보다 증가하는 경우 Tomcat 서비스 확인이 필요합니다.

| <p><strong>Tomcat 메모리 증가의 원인</strong></p><p></p><ol><li>Tomcat이 처리하는 요청 증가</li><li>메모리 누수</li></ol> |
| --------------------------------------------------------------------------------------------------- |

원인 분석 시 참고: &#x20;

* [**Tomcat Thread 서버 관제 로그 항목 및 비정상 판단 기준**](tomcat-thread.md)
* **기타 서비스 로그 종류 및 오류 내용** 의 목차  [**Tomcat 로그**](undefined-2.md#tomcat)

### <mark style="color:$primary;">Modjk 비정상 예상 원인</mark>

mod\_jk는 Apache와 Tomcat 간 연동 모듈이며, Apache에 들어온 요청 중 Tomcat에서 처리할 요청을 8009 포트를 통해 Tomcat으로 전달하고 Tomcat이 처리한 결과를 다시 Apache에게 전달하는 역할을 합니다. 해당 로그 내용은 netstat에서 8009 포트에 관한 내용을 모니터링한 내용으로 각 항목이 임계치보다 높은 경우 확인이 필요합니다.

#### TIME\_WAIT 수

TIME\_WAIT 상태는 TCP 연결이 정상적으로 종료된 후 소켓이 대기(약 60초)하는 동안에는 클라이언트와 서버 간의 연결이 유지되는데, 이를 TIME\_WAIT 상태라고 합니다.

| <p><strong>TIME_WAIT 증가의 원인</strong> </p><p></p><ol><li>요청이 많은 경우 증가할 수 있음</li><li>네트워크 환경이 불안정하여, 패킷 손실이나 지연으로 인해 소켓 연결이 즉시 닫히지 않을 경우 발생</li><li>Tomcat, Apache 서비스의 장애로 인한 영향</li><li>서버의 리소스가 부족으로 인해 발생</li><li>기타 네트워크 구성이나 방화벽으로 인한 문제로 소켓 연결이 종료되지 않는 문제</li></ol> |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

원인 분석 시 참고: &#x20;

* **기타 서비스 로그 종류 및 오류 내용**의 목차 [**Apache 로그**](undefined-2.md#apache)
* \[**Apache 상태 서버 관제 로그 항목 및 비정상 판단 기준**]\(http://서버 모니터링 로그 로그파일 서버관제 서버상황 서버 관제로그)
* [**Tomcat Thread 서버 관제 로그 항목 및 비정상 판단 기준**](tomcat-thread.md)
* **기타 서비스 로그 종류 및 오류 내용**의 목차 [**Tomcat 로그**](undefined-2.md#tomcat)
* [**Netstat 서버 관제 로그 항목 및 비정상 판단 기준**](netstat.md)

#### CLOSE\_WAIT 수

CLOSE\_WAIT 상태는 네트워크 소켓이 닫힐 때까지 대기하는 TCP 상태입니다. 이 상태는 일반적으로 소켓을 닫은 측과 수신 측 간의 연결 종료 프로토콜 과정 중 하나가 완료되지 않은 경우 발생할 수 있습니다.

| <p><strong>CLOSE_WAIT 증가의 원인</strong></p><p></p><ol><li>요청이 많은 경우 증가할 수 있음</li><li>네트워크 오류나 리소스 부족 등으로 인해 소켓이 닫히지 않을 경우 발생</li><li>Apache에서 요청을 처리하지 못할 경우, 연결이 종료되지 않아 발생</li><li>Tomcat에서 오랫동안 활성화되어 있는 연결로 인해 발생</li><li>기타 네트워크 구성이나 방화벽으로 인한 문제로 소켓 연결이 종료되지 않는 문제</li></ol> |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

원인 분석 시 참고: &#x20;

* **기타 서비스 로그 종류 및 오류 내용**의 목차 [**Apache 로그**](undefined-2.md#apache)
* \[**Apache 상태 서버 관제 로그 항목 및 비정상 판단 기준**]\(http://서버 모니터링 로그 로그파일 서버관제 서버상황 서버 관제로그)
* [**Tomcat Thread 서버 관제 로그 항목 및 비정상 판단 기준**](tomcat-thread.md)
* **기타 서비스 로그 종류 및 오류 내용**의 목차 [**Tomcat 로그**](undefined-2.md#tomcat)
* [**Netstat 서버 관제 로그 항목 및 비정상 판단 기준**](netstat.md)

#### ESTABLISHED 수

ESTABLISHED 상태는 연결된 상태로 데이터를 주고받을 수 있습니다. 해당 상태의 수가 증가하는 것은 정상적인 상황이나, 비정상적으로 증가하는 경우 확인이 필요합니다.

| <p><strong>ESTABLISHED 증가의 원인</strong> </p><p></p><ol><li>클라이언트 요청이 많아져 Apache – Tomcat 간 연결 증가</li><li>애플리케이션 서버에서 응답이 지연되는 경우</li><li>네트워크 지연에 따른 증가</li></ol> |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |

원인 분석 시 참고: &#x20;

* **기타 서비스 로그 종류 및 오류 내용**의 목차  [**Apache 로그**](undefined-2.md#apache)
* [**Apache 상태 서버 관제 로그 항목 및 비정상 판단 기준**](apache.md)
* [**Tomcat Thread 서버 관제 로그 항목 및 비정상 판단 기준**](tomcat-thread.md)
* **기타 서비스 로그 종류 및 오류 내용**의 목차 [**Tomcat 로그**](undefined-2.md#tomcat)
* [**Netstat 서버 관제 로그 항목 및 비정상 판단 기준**](netstat.md)

### <mark style="color:$primary;">DB 연결 비정상 예상 원인</mark>

DB 연결이 되지 않거나 DB 서비스 이상이 생겼을 경우로 확인이 필요합니다.

당사는 MySQL만 장애 발생시 지원가능 합니다.

| <p><strong>MySQL 연결 비정상의 원인</strong></p><p></p><ol><li>잘못된 계정 정보</li><li>잘못된 호스트 &#x26; 포트 정보 </li><li>MySQL 서비스가 중지되었을 경우 </li><li>방화벽 또는 네트워크 문제 </li><li>MySQL 사용자 권한 설정 문제 </li><li>동시 접속자 수 초과되었을 경우</li><li>MySQL 구성 파일의 문제인 경우 </li><li>데이터 저장 공간 부족이 문제인 경우</li></ol> |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

원인 분석 시 참고: &#x20;

* **기타 서비스 로그 종류 및 오류 내용**의 목차 [**MySQL 로그**](undefined-2.md#mysql)

### <mark style="color:$primary;">OS 자원 사용량의 비정상 예상 원인</mark>

#### CPU/Memory 높을 시 확인할 사항

서버의 전체의 CPU 사용량과 메모리 사용량이 임계치보다 높은 경우로 서버 시스템과 성능 확인이 필요합니다.

윈도우의 경우 **작업관리자**를 통하여 CPU나 메모리를 가장 많이 사용하는 프로세스를 찾아 점검할 필요가 있습니다.

리눅스의 경우 **top** 명령어를 통하여 확인할 수 있습니다.

서버에 백신 또는 백업이 실행되지는 않는지도 확인이 필요합니다.

#### 디스크 용량 많을 시 확인할 사항

각 디스크 사용량을 모니터링 합니다. 디스크 용량이 꽉 찬 경우 서비스에 영향을 주기 때문에 설정된 임계치보다 높은 경우 해당 디스크의 데이터 정리가 필요합니다.

### <mark style="color:$primary;">Netstat 비정상 예상 원인</mark>

전체 netstat에 대해 모니터링하여 남긴 로그입니다. 각 항목이 임계치보다 높은 경우 서버 확인이 필요합니다.

#### TIME\_WAIT 수

TIME\_WAIT 상태는 TCP 연결이 정상적으로 종료된 후 소켓이 대기(약 60초)하는 동안에는 클라이언트와 서버 간의 연결이 유지되는데, 이를 TIME\_WAIT 상태라고 합니다.

| <p><strong>TIME_WAIT 증가의 원인</strong> </p><p></p><ol><li>연결 요청이 빈번한 경우</li><li>종료 명령을 받지 못하는 등의 원인으로 클라이언트에서 연결 종료가 지연될 경우</li><li>DDoS 공격으로 인해 증가</li></ol> |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- |

원인 분석 시 참고:

* [**Netstat 서버 관제 로그 항목 및 비정상 판단 기준**](netstat.md)

#### CLOSE\_WAIT 수

CLOSE\_WAIT 상태는 네트워크 소켓이 닫힐 때까지 대기하는 TCP 상태입니다. 이 상태는 일반적으로 소켓을 닫은 측과 수신 측 간의 연결 종료 프로토콜 과정 중 하나가 완료되지 않은 경우 발생할 수 있습니다.

| <p><strong>CLOSE_WAIT 증가의 원인</strong> </p><p></p><ol><li>클라이언트에서 소켓을 제대로 닫지 않은 경우</li><li>서버에서 FIN 패킷을 제대로 처리하지 못한 경우</li><li>네트워크 장비나 방화벽 등에 의해 연결이 종료되지 않은 경우</li></ol> |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

원인 분석 시 참고:&#x20;

* ​[**Netstat 서버 관제 로그 항목 및 비정상 판단 기준**](netstat.md)
