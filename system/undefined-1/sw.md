# 문서중앙화 서버 SW 아키텍처

### <mark style="color:$primary;">문서중앙화 서버 구성 프로그램</mark>

문서중앙화 서버의 기본 프로그램 구성 및 역할은 다음과 같습니다.

* **Apache**: 문서중앙화 엔진 모듈을 탑재하고 있으며, 모든 요청을 수신하여 URL에 따라 엔진 모듈 또는 Tomcat으로 전달하는 역할을 담당합니다.
* **Tomcat**: jsp웹 서비스를 제공합니다.
* **Java**: Tomcat 서비스 구동 및 배치 프로그램을 동작하기 위한 프로그램입니다.
* **MySQL**: 기본 데이터베이스입니다. MSSQL, ORACLE등의 다른 DB로 변경하여 사용 가능합니다.

운영체제별 설치 경로는 다음과 같습니다.&#x20;

<table data-search="false"><thead><tr><th width="132">프로그램</th><th width="141">운영체제</th><th>설치 경로</th></tr></thead><tbody><tr><td>Apache</td><td>리눅스</td><td>/usr/local/apache</td></tr><tr><td></td><td>윈도우</td><td>c:\www\Apache24_x64</td></tr><tr><td>Tomcat</td><td>리눅스</td><td>/usr/local/tomcat</td></tr><tr><td></td><td>윈도우</td><td>c:\www\Tomcat7_x64</td></tr><tr><td>Java</td><td>리눅스</td><td>/usr/local/java</td></tr><tr><td></td><td>윈도우</td><td>c:\java</td></tr><tr><td>MySQL</td><td>리눅스</td><td>/usr/local/mysql</td></tr><tr><td></td><td>윈도우</td><td>c:\mysql</td></tr></tbody></table>

{% hint style="info" %}
서비스용 웹 소스코드는 리눅스인 경우 /plusdrive/web, 윈도우인 경우 c:\plusdrive\web에 저장됩니다.&#x20;
{% endhint %}

### <mark style="color:$primary;">문서중앙화 서버 종류</mark>

문서중앙화 서버는 웹서버와 파일서버로 구성됩니다. 서버가 1대인 경우, 웹서버와 파일서버 기능을 병행합니다.

* **웹서버**: 웹페이지와 클라이언트 프로토콜을 처리하는 서버입니다. DB와 연결되는 서버로 관리자/사용자 웹페이지, 로그인, 정책수신, 클라이언트 연동 등을 처리합니다.
* **파일서버**: 클라이언트의 데이터 입출력 요청을 처리하는 서버입니다. 스토리지와 연결되는 서버로 목록보기, 열람, 편집 저장 등의 작업을 처리합니다.

웹서버와 파일서버가 각각 1개로 구성된 경우의 서비스 아키텍처는 다음과 같습니다.

![](<../../.gitbook/assets/img_001 (177).png>)

### <mark style="color:$primary;">문서중앙화 서버 처리 흐름도</mark>

문서중앙화의 웹서버와 파일서버는 요청오는 URL에 따라서 처리 흐름이 달라집니다.

#### 웹서버

Apache는 URL이 \*.jsp 으로 오는 요청은 모두 Tomcat에게 전달하며 이때 mod\_jk.so 모듈을 이용합니다. 기본 포트번호는 다음과 같습니다. 포트 번호는 변경 가능합니다.

* **웹서버 기본 접속 Port**: 80, 443
* **Tomat 기본 연결 Port**: 8009

문서중앙화 웹서버 처리 흐름도는 다음과 같습니다.&#x20;

![](<../../.gitbook/assets/img_002 (148).png>)

#### 파일서버

Apache는 URL이  \*/PlusDrive/\*으로 오는 요청은 모두 엔진 모듈에게 전달합니다. 기본 포트번호는 다음과 같습니다. 포트 번호는 변경 가능합니다.

* **파일서버 기본 접속 Port**: 80, 443

문서중앙화 파일서버 처리 흐름도는 다음과 같습니다.&#x20;

![](<../../.gitbook/assets/img_003 (127).png>)
