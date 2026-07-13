# NetworkLock 사용 시 인터넷 사이트 접속 관련 오류 해결 방법

NetworkLock 사용 시 내부망 모드에서 내부망 모드 허용 IP 대역으로 등록되지 않은 서버 또는 웹사이트 접속할 경우, 또는 등록된 사이트에 접속하더라도 해당 사이트 내에서 내부망 모드 허용 IP대역에 등록되지 않은 외부 URL을 참조할 경우, 애플리케이션 또는 웹페이지가 정상적으로 동작하거나 표시되지 않을 수 있습니다.\
\
이러한 경우, 다음 절차에 따라 접속이 허용되지 않은 IP 또는 도메인을 찾아내어 내부망 모드 허용 IP대역에 추가하는 방법으로 문제를 해결할 수 있습니다. \
<br>

#### 1.   NetworkLock 디버깅을 위한 Windows 레지스트리 등록  <a href="#id-1_networklock__windows" id="id-1_networklock__windows"></a>

NetworkLock.reg 파일을 더블 클릭하여 실행한 후, PC를 재부팅합니다. \
![](https://support.mcloudoc.com/galleryDocuments/edbsn9512cbe84c033dc6d84b73935ff2e35149b76b2de58d2d07dca3ae1f9a31ca80dafc32c1284b3be8ba23332b3d9a059a?inline=true)\
<br>

![Notes](https://static.zohocdn.com/zoho-desk-editor/static/images/file.png)

NetworkLock.reg 및 npSupportUtil.exe파일은 기술지원팀에서 제공받을 수 있습니다.<br>

#### 2.    문서중앙화 에이전트 로그 설정  <a href="#id-2" id="id-2"></a>

npSupportUtil.exe 파일을 실행하여 로그를 기록할 모듈을 선택합니다.<br>

1. PlusFsfd\_DiskLock (DiskLock 커널 로그)와 PlusFsfd\_DeniedIO (파일I/O 거부 커널 로그)를 선택한 후 적용 버튼을 클릭한다.

> ![](https://support.mcloudoc.com/galleryDocuments/edbsn7481034f72976761355f9fd99da445f94b9f668e1bd455215c87d66352b4e4ac6b2747d41b9cee177bb3359a4c13cf39?inline=true)<br>

![](https://support.mcloudoc.com/galleryDocuments/edbsn936a947ea44bc16a8b94cfbc5f5c313179da0b327d2ea7f776a6369e7617480e9e2c4b2ad5bfdd4568149c2ad733166a?inline=true)

<br>

#### 3.    DebugView에서 접속이 차단되는 IP 또는 도메인 확인  <a href="#id-3__debugview___ip" id="id-3__debugview___ip"></a>

①   Dbgview.exe 파일을 우클릭하여 관리자 모드로 실행합니다.\
<br>

![](https://support.mcloudoc.com/galleryDocuments/edbsncab56cd002f5dcfe16afdc620df421d5062a94b4fa5520efcc07371c595913de0f809632f85e439c10a012dfaadfe501?inline=true)

![Notes](https://static.zohocdn.com/zoho-desk-editor/static/images/file.png)

DebugView에 대한 설명 및 다운로드는 다음 링크를 참고하세요.[https://learn.microsoft.com/ko-kr/sysinternals/downloads/debugview](https://learn.microsoft.com/ko-kr/sysinternals/downloads/debugview)

②   상단 Edit 탭에서 Filter/Highlight를 선택하여 DebugView 필터를 설정합니다.<br>

1. Include 항목에 Block을 입력하거나 DNS와 pName을 입력한 후 OK 버튼을 클릭합니다. 입력 시 빈칸이나 문장 부호 없이 입력하며 두 개 이상의 문자열을 입력할 경우 세미콜론( ; )으로 구분합니다.

> 1) Block으로 설정할 경우, 차단되는 IP를 확인할 수 있습니다.
> 2) DNS;pName으로 설정할 경우, 접속을 시도하는 도메인 주소 및 해당 도메인으로의 접속 허용 여부를 확인할 수 있습니다.<br>

![Notes](https://static.zohocdn.com/zoho-desk-editor/static/images/file.png)필터 설정 시 Block, DNS, pName을 한꺼번에 Include 할 수 있으나, 여기서는 편의상 별도로 설명합니다.\
\
![](https://support.mcloudoc.com/galleryDocuments/edbsncab56cd002f5dcfe16afdc620df421d5d38397fdae5239446f0d6677b38960f5391c1f0807db8a82cec024a3fe8a2ab9?inline=true)\
\
③   상단 Capture탭에서 화면과 같이 항목을 체크하여 활성화합니다.<br>

![](https://support.mcloudoc.com/galleryDocuments/edbsn5bb06c73f301cacece06bccbc18983e60ad3ff248f6b7e6722be02f8bddd02c1e373535c173969f9a92a50eea2eee490?inline=true)<br>

④   다음 화면과 같이 ②에서 설정한 필터에 따라 디버그 출력이 표시됩니다. 문제가 발생하는 인터넷 사이트에 접속하여, 출력되는 로그를 확인합니다.\
\
![](https://support.mcloudoc.com/galleryDocuments/edbsnf59519eb97e0bbad48f80960e1563008fab23e257bd4ec9836aba47a541a0b331948338663046de92d2ec735a48c215b?inline=true)\
![Idea](https://static.zohocdn.com/zoho-desk-editor/static/images/lights.png)Options 탭의 Clock Time을 선택하면 통상적인 시간 포맷으로 로그가 출력됩니다. \
\
⑤   다음과 같은 방법으로 NetworkLock 정책에서 추가로 허용할 도메인 또는 IP 주소를 확인합니다.<br>

1. 필터를 DNS;pName으로 설정한 경우<br>

> 다음은 웹 브라우저에서 youtube.com에 접속 시 로그 일부를 간추린 것입니다. YouTube 접속을 허용하기 위해 \*.youtube.com을 NetworkLock 정책의 내부망 모드 허용 IP대역으로 등록하였으나, 페이지의 이미지나 폰트가 정상적으로 표시되지 않는 경우의 예입니다.\
> <br>
>
> <img src="https://support.mcloudoc.com/galleryDocuments/edbsnc44a20839e49024a65d9c49235d0bbf6c275af8053e607f9efb034011f88207408dd83a4bb73c7f3f1a77d4f4657aabb?inline=true" alt="" data-size="original">

&#x20;         ![](https://support.mcloudoc.com/galleryDocuments/edbsne73cc55f317bf703e10735d4d6492d024238692bbc830d6edc7be5eaf19cbe72bdacb186ab3d855be8bc903f6e79fcbf?inline=true)    youtube.com 에 연결을 시도합니다.\
&#x20;         ![](https://support.mcloudoc.com/galleryDocuments/edbsnc58629015a2084aeeaab4d835e896a9bd714c1e2ede066e4dbcbd7e3bcb83d2359fa0c6441976e68d4215fdb93b345f0?inline=true)    NetworkLock 정책에 등록된 허용 도메인에서 youtube.com과 매칭되는 아이템을 찾습니다.       \
&#x20;         ![](https://support.mcloudoc.com/galleryDocuments/edbsnc58629015a2084aeeaab4d835e896a9bef47d0edb3f8d2861cc8dbcf254bcbfc98f154b4f35ddf39161ecf69f154b5bf?inline=true)    매칭되는 아이템이 있으므로 이 사이트의 IP주소를 허용 리스트에 등록합니다.\
&#x20;                          ⇨ 이 경우, youtube.com에는 접속이 가능합니다.<br>

> \
> ![](https://support.mcloudoc.com/galleryDocuments/edbsncd5f400350e7d0ef88b6c8e9f3b6ea534e47e01fa1758a9ba1e6be9d0571c82a23162b3e74babe7bf9f644c78d6d06c9?inline=true)<br>

&#x20;          ![](https://support.mcloudoc.com/galleryDocuments/edbsn936a947ea44bc16a8b94cfbc5f5c3131ba169bbaad9917982a9d340c28b478743f36a74b1159b7460e5a58c562ef92dc?inline=true)    youtube.com 에 연결된 후, 연이어 i.ytimg.com 및 fonts.googleapis.com 에 접속을 시도합니다.\
\
&#x20;         ![](https://support.mcloudoc.com/galleryDocuments/edbsneefca89014543522f066c637680a48a4916b5ddd264435e3fde6af298fe5fc15ddf01670f98408d6a02f67b52823d618?inline=true)    NetworkLock 정책에 등록된 허용 도메인에서 매칭되는 아이템을 찾지 못합니다.

⇨   해당 사이트에 접속이 차단되어, YouTube 페이지에서 이미지나 폰트가 정상적으로 표시되지 않은 것을 알 수 있습니다.<br>

⇨    NetworkLock 정책의 내부망 모드 허용 IP대역에 i.ytimg.com 및 fonts.googleapis.com을 추가로 등록하여 문제를 해결할 수 있습니다.<br>

<br>

1. 필터를 Block으로 설정한 경우 <br>

> 아래와 같이 접속 시도가 차단된 IP를 확인할 수 있습니다. 회사 운용 서버 등 접속이 필요한 IP주소가 차단되어 있을 경우, 해당 IP를 내부망 모드 허용 IP대역에 추가하여 문제를 해결할 수 있습니다.<br>

![](https://support.mcloudoc.com/galleryDocuments/edbsn5bb06c73f301cacece06bccbc18983e6d59e9d429a0df4a0ab47d2b4562503937f8213cb8f194cd98c3a6573eecf6b2d?inline=true)\
\
![Notes](https://static.zohocdn.com/zoho-desk-editor/static/images/file.png)외부망 모드의 경우에도 같은 방법으로 차단된 필수 IP를 확인하고, 외부망 차단 IP대역에서 제거하여 문제를 해결할 수 있습니다.\
⑥   관리자 웹페이지에서 윈도우 보안 모듈 관리 - NetworkLock- 정책 관리를 선택하여 현재 사용 중인 NetworkLock 정책을 변경합니다. <br>

1. ⑤에서 찾아낸 도메인 또는 IP주소를 내부망 모드 허용 IP대역에 추가합니다.
2. 자세한 방법은 [NetworkLock 정책 관리하기](https://support.mcloudoc.com/portal/ko/kb/articles/networklock-%EC%A0%95%EC%B1%85-%EA%B4%80%EB%A6%AC%ED%95%98%EA%B8%B0)를 참고하세요.

<br>
