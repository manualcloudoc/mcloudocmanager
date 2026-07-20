# 로그 설정

{% hint style="info" %}
메뉴 경로: 시스템 설정 - 설정 홈 연결 - 일반 모듈 설정 - Basic - 로그
{% endhint %}

### <mark style="color:$primary;">파일 작업 로그와 서버 성능 모니터링 설정</mark>

파일 작업 로그와 서버 성능 모니터링에 관한 설정입니다.

* 파일 작업 로그:  로그인 인증, 파일 작업 등에서 로그를 기록할 대상 및 기록할 최소 로그의 크기를 설정합니다.
* 서버 성능 모니터링:  서버 관제 사용 시 Apache, Tomcat, Netstat 서비스 및 Disk, CPU, Memory의 모니터링  관련 기준값을 설정합니다. 로그 파일 보관 기간, 관제 메일 발송 등을 설정합니다.

#### 파일 작업 로그

<table data-search="false"><thead><tr><th width="193">로그 옵션</th><th width="253">내용</th><th>기본값</th></tr></thead><tbody><tr><td>인증 로그 기록 대상</td><td><p>사용자의 로그인에 대한 기록 중 로그로 남길 대상을 설정합니다.</p><ul><li><strong>로그인</strong></li><li><strong>로그아웃</strong></li><li><strong>인증 실패</strong></li></ul></td><td>로그인, 로그아웃, 인증 실패</td></tr><tr><td>로그 기록 대</td><td><p>로그로 기록할 사용자의 파일작업에 대한 기록 대상을 설정합니다.</p><ul><li><strong>업로드</strong> </li><li><strong>다운로드</strong> </li><li><strong>삭제</strong> </li><li><strong>복사</strong> </li><li><strong>이동</strong> </li><li><strong>이름변경</strong></li></ul></td><td>업로드, 다운로드, 삭제, 복사, 이동, 이름변경</td></tr><tr><td>공유 로그 기록 대상</td><td><p>공유 폴더의 파일작업에 대한 로그 기록 대상을 설정합니다.</p><ul><li><strong>업로드</strong> </li><li><strong>다운로드</strong> </li><li><strong>삭제</strong> </li><li><strong>복사</strong> </li><li><strong>이동</strong> </li><li><strong>이름변경</strong></li></ul></td><td>업로드, 다운로드, 삭제, 복사, 이동, 이름변경</td></tr><tr><td>게스트 로그 기록 대상</td><td><p>게스트가 작업한 파일작업에 대한 로그 기록대상을 설정합니다. </p><ul><li><strong>업로드</strong> </li><li><strong>다운로드</strong> </li><li><strong>삭제</strong></li></ul></td><td>업로드, 다운로드, 삭제</td></tr><tr><td>로그 기록 최소 파일 크기</td><td><p>일정 크기 이상의 파일만 로그를 기록하도록 설정할 수 있습니다 </p><ul><li><strong>로그를 기록할 최소 파일 크기</strong>: 설정한 크기(단위:MB) 이상의 파일만 로그를 기록합니다. </li><li><strong>모든 파일</strong>: 파일 크기에 관계없이 로그를 기록합니다.</li></ul></td><td>모든 파일</td></tr></tbody></table>

#### **서버 성능 모니터링**

<table data-search="false"><thead><tr><th>로그 옵션</th><th width="325">내용</th><th>기본값</th></tr></thead><tbody><tr><td>서버 관제 사용 여부</td><td>서버에서 문서중앙화 관련 서비스 및 운영체제가 정상적으로 운영되고 있는지 모니터링할 수 있습니다. 서버 모니터링 사용 여부를 설정합니다.</td><td>사용함</td></tr><tr><td>Apache 서비스 자동 재시작 사용 여부</td><td>서비스가 정상 작동하는지 확인하여 비정상이면 재시작 하도록 설정할 수 있습니다. Apache 포트(기본80)로 응답 유무를 체크하여 무응답 및 오류가 발생할 경우 비정상으로 판단합니다.</td><td>사용 안 함</td></tr><tr><td>Apache 서비스 자동 재시작용 설정 (윈도우만 사용)</td><td><p>윈도우 서버의 경우 자동으로 재시작하는 서비스 실행 타입을 서비스 형태 또는 배치 형 태 중 선택합니다. </p><ul><li><strong>서비스(service)</strong> </li><li><strong>배치(batch)</strong></li></ul></td><td>서비스(service)</td></tr><tr><td>Apache 비트 여부 (윈도우만 사용)</td><td><ul><li><strong>64bit</strong> </li><li><strong>32bit</strong></li></ul></td><td>64bit</td></tr><tr><td>Apache 서비스 경로 (윈도우 서버이고 실행 타입이 service일 경우 해당)</td><td>Apache 서비스 경로를 설정합니다.</td><td>C:\www\Apache24_x64\bin\httpd.exe</td></tr><tr><td>Tomcat Port</td><td>8085</td><td></td></tr><tr><td>Java 경로 (윈도우 서버일 경우만 해당)</td><td>Java 경로를 설정합니다.</td><td>C:\java\bin</td></tr><tr><td>Tomcat 서비스 자동 재시작 사용 여부</td><td>서비스가 정상 작동하는지 확인하여 비정상이면 재시작 하도록 설정할 수 있습니다.  Tomcat 포트(기본8085)로 응답 유무 체크하여 무응답 및 오류가 발생할 경우 비정상으로 판단합니다.</td><td>사용 안 함</td></tr><tr><td>Tomcat 서비스 자동 재시작용 설정 (윈도우만 사용)</td><td><p>윈도우 서버의 경우 자동으로 재시작하는 서비스 실행 타입을 서비스 형태 또는 배치 형태에서 선택할 수 있습니다. </p><ul><li><strong>서비스(service)</strong> </li><li><strong>배치(batch)</strong></li></ul></td><td>서비스(service)</td></tr><tr><td>Tomcat 비트 여부 (윈도우만 사용)</td><td><ul><li><strong>64bit</strong> </li><li><strong>32bit</strong></li></ul></td><td>64bit</td></tr><tr><td>Tomcat 서비스 이름 (윈도우 서버이고 실행 타입이 service일 경우 해당)</td><td>Tomcat 서비스 이름을 설정합니다. 윈도우 서버이고 서비스 실행 타입일 경우에 설정합니다. 기본값 Tomcat7.</td><td>Tomcat7</td></tr><tr><td>Apache 서비스 체크 Thread 기준값</td><td>설정한 Thread 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>500</td></tr><tr><td>Apache 서비스 체크 CPU 기준값</td><td>설정한 CPU 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>100</td></tr><tr><td>Apache 서비스 체크 Memory 기준값</td><td>설정한 Memory기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>10240</td></tr><tr><td>Tomcat 서비스 체크 Thread 기준값</td><td>설정한 Thread 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>500</td></tr><tr><td>Tomcat 서비스 체크 CPU 기준값</td><td>설정한 CPU 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>70</td></tr><tr><td>Tomcat 서비스 체크 Memory 기준값</td><td>설정한 Memory기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>10240</td></tr><tr><td>mod_jk 체크 Timewait 기준값</td><td>설정한 Timewait 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>300</td></tr><tr><td>mod_jk 체크 Closewait 기준값</td><td>설정한 Closewait 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>200</td></tr><tr><td>mod_jk 체크 Established 기준값</td><td>설정한 Established 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>600</td></tr><tr><td>통신 상태 체크 Closewait 기준값</td><td>설정한 Timewait 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>1000</td></tr><tr><td>통신 상태 체크 Timewait 기준값</td><td>설정한 Closewait 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>5000</td></tr><tr><td>디스크 사용률(%) 기준값</td><td>설정한 디스크 사용률(%) 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>95%</td></tr><tr><td>전체 CPU 사용률(%) 기준값</td><td>설정한 전체 CPU 사용률(%) 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>100%</td></tr><tr><td>전체 Memory 사용률(%) 기준값</td><td>설정한 전체 Memory 사용률(%) 기준값을 초과하는 경우 비정상으로 판단합니다.</td><td>99%</td></tr><tr><td>전체 SWAP 사용률(%) 기준값</td><td>설정한 전체 SWAP 사용률(%) 기준값을 초과하는 경우 비정상으로 판단합니다</td><td>90%</td></tr><tr><td>Monitoring 로그 기록 사용 여부</td><td><ul><li><strong>사용함</strong> </li><li><strong>사용 안 함</strong></li></ul></td><td>사용함</td></tr><tr><td>Apache Status 로그 기록 사용 여부</td><td><p></p><ul><li><strong>사용함</strong> </li><li><strong>사용 안 함</strong></li></ul></td><td>사용함</td></tr><tr><td>Tomcat Thread Dump 로그 기록 사용 여부</td><td><p></p><ul><li><strong>사용함</strong> </li><li><strong>사용 안 함</strong></li></ul></td><td>사용함</td></tr><tr><td>Netstat 로그 기록 사용 여부</td><td><p></p><ul><li><strong>사용함</strong> </li><li><strong>사용 안 함</strong></li></ul></td><td>사용함</td></tr><tr><td>재시작 로그 기록 사용 여부</td><td><p></p><ul><li><strong>사용함</strong> </li><li><strong>사용 안 함</strong></li></ul></td><td>사용함</td></tr><tr><td>Monitoring 로그 파일 보관기간</td><td>설정된 일 수만큼 보관합니다.</td><td>7일</td></tr><tr><td>Apache Status 로그 파일 보관기간</td><td>설정된 일 수만큼 보관합니다.</td><td>7일</td></tr><tr><td>Tomcat Thread Dump 로그 파일 보관기간</td><td>설정된 일 수만큼 보관합니다.</td><td>7일</td></tr><tr><td>Netstat 로그 파일 보관기간</td><td>설정된 일 수만큼 보관합니다.</td><td>7일</td></tr><tr><td>재시작 로그 파일 보관기간</td><td>설정된 일 수만큼 보관합니다.</td><td>7일</td></tr><tr><td>메일 전송 설정(넷아이디 메일서버 사용여부)</td><td><p>넷아이디 메일서버 사용 여부를 설정할 수 있습니다. </p><ul><li><strong>사용함</strong> </li><li><strong>사용 안함:</strong> websvc.conf 에 설정된 메일 서버를 사용합니다.</li></ul></td><td>사용함</td></tr><tr><td>수신인 목록</td><td>관제 메일을 수신하고 있는 수신인을 ‘<strong>수신인 목록’</strong> 창에서 조회할 수 있고, 이메일 주소를 추가할 수 있습니다.</td><td></td></tr><tr><td>관제 메일 발송 설정</td><td><p>관제 메일을 항상 또는 장애시에만 발송하도록 설정할 수 있습니다. </p><ul><li><strong>항상 발송:</strong> 정상 상태일 때에도 메일 발송</li><li><strong>장애시 발송</strong>: 장애 발생시에만 메일 발송</li></ul></td><td>장애 시 발송</td></tr><tr><td>메일 언어 설정</td><td><p>발송할 메일의 언어를 설정할 수 있습니다. </p><ul><li><strong>한국어</strong> </li><li><strong>영어</strong> </li><li><strong>일본어</strong> </li><li><strong>중국어</strong></li></ul></td><td></td></tr></tbody></table>

### <mark style="color:$primary;">모니터링 결과, 서비스 상태, 서비스 재시작 수행에 대한 로그 종류</mark>

로그 종류별 로그 파일 위치는 아래와 같습니다. 로그파일은 서버 설정 값에 등록된 일 수만큼 보관합니다.

<table data-search="false"><thead><tr><th width="125">로그 종류</th><th width="149">세부 유형</th><th>로그 내용</th><th>로그 파일 위치</th></tr></thead><tbody><tr><td><strong>기본 로그</strong></td><td>Apache</td><td>서비스 정상 여부</td><td>/plusdrive/log/monitoring_log/default_log/ default_log_날짜_시간.html</td></tr><tr><td></td><td></td><td>Thread, CPU, RAM 사용량</td><td>위와 같음</td></tr><tr><td></td><td>Tomcat</td><td>서비스 정상 여부</td><td>위와 같음</td></tr><tr><td></td><td></td><td>Thread, CPU, RAM 사용량</td><td>위와 같음</td></tr><tr><td></td><td></td><td>Netstat 상태 (Port 8009)</td><td>위와 같음</td></tr><tr><td></td><td>Database</td><td>클라우독 DB 연결 정상 여부</td><td>위와 같음</td></tr><tr><td></td><td></td><td>인사연동 DB 연결 정상 여부</td><td>위와 같음</td></tr><tr><td></td><td>OS</td><td>CPU, Memory, Disk 사용량</td><td>위와 같음</td></tr><tr><td></td><td></td><td>Netstat 상태</td><td>위와 같음</td></tr><tr><td><strong>Apache</strong> <strong>관련 로그</strong></td><td></td><td>Apache Status 로그</td><td>/plusdrive/log/monitoring_log/apache_status /apache_status_날짜_시간.html</td></tr><tr><td><strong>Tomcat</strong> <strong>관련 로그</strong></td><td></td><td>Tomcat Thread Dump 결과</td><td>/plusdrive/log/monitoring_log/tomcat_status /tomcat_thread_dump_날짜_시간.txt</td></tr><tr><td></td><td></td><td>Tomcat 메모리 덤프 결과</td><td>/plusdrive/log/monitoring_log/tomcat_status /heap_memory_dump_날짜_시간.hprof</td></tr><tr><td><strong>Netstat 로그</strong></td><td></td><td>전체 netstat 상태</td><td>/plusdrive/log/monitoring_log/netstat_log /netstat_날짜_시간.txt</td></tr><tr><td><strong>재시작 로그</strong></td><td>Apache</td><td>서비스 재시작 로그</td><td>/plusdrive/log/monitoring_log/restart_log /apache_restart_log_날짜_시간.html</td></tr><tr><td></td><td>Tomcat</td><td>서비스 재시작 로그</td><td>/plusdrive/log/monitoring_log/restart_log /tomcat_restart_log_날짜_시간.html</td></tr></tbody></table>

### <mark style="color:$primary;">메일 알림</mark>

모니터링 결과 및 서비스 재시작 결과를 메일로 알려줍니다.

* 모니터링 결과 알림: 모니터링 항목 중 한가지라도 이상인 사항이 있으면 기본 로그의 전체 내용을 메일로 발송합니다.정상 상태일 때에도 메일을 발송합니다.

&#x20;     다음은 정상 상태인 경우 발송된 메일의 예입니다.

<div align="left"><img src="../../.gitbook/assets/img_001 (170).png" alt=""></div>

* 서비스 재시작 알림: 서비스가 비정상으로 판단되어 서비스 재시작을 하게 되는 경우, 메일로 재시작 완료 여부를 알려줍니다.&#x20;

&#x20;     다음은 재시작 알림 메일의 예입니다.

<div align="left"><img src="../../.gitbook/assets/img_002 (145).png" alt=""></div>

### <mark style="color:$primary;">서비스 재시작</mark>

Apache 및 Tomcat 모니터링 결과가 이상이라고 판단되면, 해당 서비스를 자동으로 재 시작하여 정상 동작하도록 할 수 있습니다.

Tomcat의 경우, 재시작 전에 현재 메모리 덤프를 취득한 후 재시작 합니다.

### <mark style="color:$primary;">서버 모니터링 설정 방법</mark>

서버 모니터링 설정 방법입니다.&#x20;

1. 설정 전에 아래 배치프로그램을 확인합니다.예약 작업 배치로 등록해야 하는 파일이 아래 경로에 위치하는지 확인합니다.

* &#x20;Windows 서버:c:\plusdrive\web\batch\filesvr\server\_status\_check\ServerStatusCheck.bat
* Linux 서버:\
  &#x20;/plusdrive/web/batch/filesvr/server\_status\_check/ServerStatusCheck.sh&#x20;

2. 해당 배치가 예약 작업(반복주기: 기본 10분)으로 등록되어 있는지 확인합니다.

* Windows 서버: **제어판 – 관리도구 – 작업 스케줄러** 메뉴를 실행하여, 아래 이름으로 모니터링 예약 작업이 등록되어 있는지 확인합니다

![](<../../.gitbook/assets/img_003 (125).png>)

* Linux 서버: 명령 실행창에서 crontab -u netid –l 을 입력하여 아래와 같은 항목이 있는지 확인합니다.

&#x20;    <mark style="background-color:$primary;">\*/10 \* \* \* \* /plusdrive/web/batch/filesvr/server\_status\_check/ServerStatusCheck.sh</mark>

![](<../../.gitbook/assets/img_004 (98).png>)
