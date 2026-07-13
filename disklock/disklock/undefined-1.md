# 애플리케이션 카테고리 소개

애플리케이션 카테고리는 사용자 PC에서 사용되는 애플리케이션들을 특성에 따라 분류한 것으로 문서 중앙화 솔루션의 DiskLock, DiskLock Plus와 같은 보안 기능에서 사용됩니다.

**DiskLock**의 **로컬저장금지 정책**은 애플리케이션 카테고리별로 애플리케이션에 허용하고 제한할 권한을 지정합니다. 그리고, **DiskLock Plus**의 **화면 캡쳐 제어 정책**, **클립보드 복사 제어 정책, 인쇄 제어 정책**도 애플리케이션 카테고리별로 허용 여부를 설정합니다. 따라서, 이러한 보안 기능들을 사용하기 위해서는 먼저 애플리케이션들을 적절한 카테고리로 분류하는 과정이 필요합니다.

### <mark style="color:$primary;">기본 애플리케이션 카테고리</mark>

문서 중앙화 솔루션에는 기본적으로 4개의 애플리케이션 카테고리가 생성됩니다. 다음 표는 각 기본 애플리케이션 카테고리로 분류되는 애플리케이션의 종류와 구 버전의 문서 중앙화 솔루션에서 사용하는 카테고리의 이름을 정리한 것입니다.

<table><thead><tr><th width="186.0909423828125">카테고리</th><th width="154.72723388671875">구 버전</th><th>설명</th></tr></thead><tbody><tr><td><strong>Business Applications (업무용 애플리케이션)</strong></td><td>Read Only</td><td>업무 시 산출물을 생성하는 MS Office, 한컴 오피스, AutoCAD 등과 같은 업무용 애플리케이션</td></tr><tr><td><strong>Export Applications (반출용 애플리케이션)</strong></td><td>Application Export</td><td>Outlook, Chrome, 카카오톡, Telegram, FTP와 같이 문서의 첨부와 외부 전송이 가능한 애플리케이션</td></tr><tr><td><strong>FullAccess Applications (전체 접근 애플리케이션)</strong></td><td>Allow Write</td><td>윈도우 탐색기나 개발용 프로그램(예: Visual Studio), 압축 해제 프로그램(예: WinZip)과 같이 정상적인 동작을 위해 로컬과 중앙 서버의 모든 파일에 대한 접근 권한이 필요한 애플리케이션</td></tr><tr><td><strong>없음</strong></td><td>Reject All</td><td>악성 코드나 랜섬웨어와 같이 사용자의 PC와 중앙 서버에 큰 피해를 줄 수 있는 애플리케이션</td></tr><tr><td><strong>미분류</strong></td><td>미분류</td><td>카테고리가 지정되지 않은 애플리케이션</td></tr></tbody></table>

문서 중앙화 솔루션은 기본적으로 사용자 PC에서 자주 사용되는 애플리케이션들을 이러한 기본 애플리케이션 카테고리로 분류되도록 설정되어 있습니다. **애플리케이션** **자동분류** 기능을 사용하면 특정 카테고리로 분류한 애플리케이션과 유사한 새 애플리케이션이 실행될 경우 자동으로 해당 카테고리로 분류되도록 할 수 있습니다. 자동분류 대상이 아닌 새 애플리케이션은 **미분류** 카테고리로 분류되고 사용자가 직접 적절한 카테고리로 이동시켜야 합니다.

### <mark style="color:$primary;">애플리케이션 카테고리 구조</mark>

애플리케이션 카테고리는 **<모든 애플리케이션>**&#xC744; 최상위로, 나머지 기본 애플리케이션 카테고리들이 하위 카테고리로 되어 있는 다음과 같은 계층 구조로 이루어집니다.

<div align="left"><img src="../../.gitbook/assets/img_000 (131).png" alt=""></div>

미분류 카테고리를 제외한 모든 카테고리는 아래에 다음과 같이 새로운 하위 카테고리를 추가할 수 있습니다. 애플리케이션 카테고리에 속한 애플리케이션의 권한은 트리의 모든 레벨에서 설정할 수 있습니다.​

<div align="left"><figure><img src="../../.gitbook/assets/img_001 (123).png" alt=""><figcaption></figcaption></figure></div>



다음은 각 기본 애플리케이션 카테고리에 추가되는 하위 카테고리와 해당 카테고리로 분류되는 대표적인 애플리케이션들의 예입니다.\
​

* **Business Application**

| 카테고리 경로                                                             | 애플리케이션 이름     |
| ------------------------------------------------------------------- | ------------- |
| Business Applications> Productivity> Word Processing> MS Word       | WINWORD.EXE   |
| Business Applications> Productivity> Spreadsheets> MS Excel         | EXCEL.EXE     |
| Business Applications> Productivity> Presentation> MS Powerpoint    | POWERPRNT.EXE |
| Business Applications> Productivity> Word Processing> Other Editors | notepad.exe   |
| Business Applications> Productivity> Graphics> AutoCAD> AutoCAD버전   | acad.exe      |
| Business Applications> Productivity> Graphics> Adobe> PhotoShop     | Photoshop.exe |

* **Export Applications**

| 카테고리 경로                                           | 애플리케이션 이름     |
| ------------------------------------------------- | ------------- |
| Export Applications> Web Browsers> Chrome         | chrome.exe    |
| Export Applications> Web Browsers> MSEdge         | msedge.exe    |
| Export Applications> FTP> Filezilla               | filezilla.exe |
| Export Applications> Instant Messaging> KakaoTalk | KakaoTalk.exe |
| Export Applications> Email> MS Outlook            | OUTLOOK.EXE   |

* **FullAccess Application**

| 카테고리 경로                                                                    | 애플리케이션 이름    |
| -------------------------------------------------------------------------- | ------------ |
| FullAccess Applications> System> Operating Systems>Windows Explorer        | explorer.exe |
| FullAccess Applications> Productivity> Software Development> Visual Studio | XDesProc.exe |
| FullAccess Applications> System> Miscellaneous Utilities> Compress>WinZip  | WINZIP32.EXE |

{% hint style="warning" icon="square-poll-horizontal" %}
애플리케이션 카테고리는DiskLock 콘솔에서 설정할 수 있습니다. DiskLock 콘솔에서 애플리케이션 카테고리를 설정하는 방법은 [**DiskLock 콘솔에서 애플리케이션 카테고리 관리하기**](disklock/mgmtcategory.md)를 참고합니다.
{% endhint %}
