# DiskLock 콘솔에서 로컬저장금지 정책 로그 보기

로컬저장금지 정책의 로그는 로컬저장금지 정책의 정책 아이템 중에서 로그를 생성하도록 설정된 정책 아이템에 의해 생성됩니다. 서버에 접속한 모든 사용자가 로그를 생성하도록 설정된 정책 아이템이 적용되는 작업을 수행할 때마다 해당 작업의 정보가 담긴 로그가 만들어집니다.

예를 들어, **Business Applications**에 속한 애플리케이션이 **비안전구역에 파일을 저장하는 작업을 차단**하는 정책 아이템이 로그를 생성하도록 설정되어 있으면, 사용자들이 해당 애플리케이션을 사용하면서 비안전구역에 파일을 저장하려고 할 때마다 로그가 생성됩니다. DiskLock 콘솔에서는 이렇게 생성된 로그를 원하는 기간별로 조회할 수 있습니다.

이렇게 정책 아이템에 생성되는 로그 외에도 사용자 PC에서 새로운 애플리케이션이 실행되어 서버에 새로 등록될 때도 로그가 생성됩니다.

### <mark style="color:$primary;">DiskLock 콘솔의 로컬저장금지 정책 로그 보기 화면 살펴보기</mark>

DiskLock 콘솔 화면의 메뉴에서 **로컬저장금지 정책 – 로그 보기** 메뉴를 선택하면 다음과 같은 로그 보기 화면이 나타납니다. 로그 보기 화면은 <img src="../../../.gitbook/assets/image (71).png" alt="" data-size="line">**도구모음**과 <img src="../../../.gitbook/assets/image (72).png" alt="" data-size="line">**로그 목록**, <img src="../../../.gitbook/assets/image (73).png" alt="" data-size="line">**출력 조건**으로 구성되어 있습니다.

<figure><img src="../../../.gitbook/assets/img_003 (75).png" alt=""><figcaption></figcaption></figure>

#### <img src="../../../.gitbook/assets/image (74).png" alt="" data-size="line"> **도구모음**

화면 상단에 있는 도구모음은 로그 출력과 관련된 메뉴들이 아이콘 형태로 제공됩니다. 각 아이콘의 기능은 다음과 같습니다.

<table><thead><tr><th width="144">아이콘</th><th>기능</th></tr></thead><tbody><tr><td><strong>검색기간</strong></td><td>출력하고자 하는 로그가 생성된 기간을 설정합니다.</td></tr><tr><td><strong>조회</strong></td><td><strong>검색기간</strong> 항목에서 지정한 기간동안 생성된 로그를 검색하여 화면에 출력합니다.</td></tr><tr><td><strong>내보내기</strong></td><td>화면에 출력된 로그를 지정한 폴더에 파일로 저장합니다. 로그 파일은 *.csv 형식으로 저장되고 Microsoft EXCEL과 같은 스프레드시트 프로그램에서 사용할 수 있습니다.</td></tr></tbody></table>

#### <img src="../../../.gitbook/assets/image (75).png" alt="" data-size="line">**로그 목록**

로그 생성이 활성화된 로컬저장금지 정책 아이템에 의해 생성된 로그가 출력되는 부분입니다. 가장 최근에 생성된 로그가 가장 위쪽에 출력됩니다. 각 로그가 나타내는 정보는 본 아티클 목차 [**로그 조회하기**](disklock-3.md#undefined-2)에서 설명합니다.&#x20;

#### <img src="../../../.gitbook/assets/image (76).png" alt="" data-size="line">**출력 조건**

화면 하단의 오른쪽에 있는 숫자는 **화면에 출력된 로그 개수/검색된 로그 개수**입니다. 화면에는 기본적으로 500개 단위로 로그를 보여주도록 설정되어 있는 데 드롭다운 목록을 클릭하면 한 번에 출력되는 로그 개수의 단위를 변경할 수 있습니다.

<div align="left"><figure><img src="../../../.gitbook/assets/img_007 (32).png" alt="" width="177"><figcaption></figcaption></figure></div>

현재 화면에 출력된 로그보다 검색된 로그가 더 많을 때에는 **더보기**를 클릭하면 다음 로그를 불러와서 표시해줍니다.

<div align="left"><img src="../../../.gitbook/assets/img_008 (29).png" alt="" width="300"></div>

### <mark style="color:$primary;">로그 조회하기</mark>

특정 기간 동안 만들어진 로그를 조회하는 방법은 다음과 같습니다.

1. 페이지 상단에 있는 도구모음의 **검색 기간** 항목에서 조회할 로그의 생성 기간을 지정할 수 있습니다. 날짜를 직접 입력하거나 날짜 우측의  ![](<../../../.gitbook/assets/img_009 (25).png>) 버튼을 클릭하여 달력에서 원하는 날짜를 선택합니다.
2. 기간을 지정한 후 도구모음에서 **조회**를 클릭합니다. &#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_010 (21).png" alt="" width="375"><figcaption></figcaption></figure></div>

3. 다음과 같이 지정한 기간동안 생성된 로그가 출력됩니다. 화면의 가로 스크롤바를 사용하면 가려진 로그 정보를 볼 수 있습니다. 생성된 로그가 많은 경우에는 화면에 출력되기까지 시간이 걸릴 수 있습니다.

![](<../../../.gitbook/assets/img_011 (14).png>)

각 로그에 표시되는 정보는 다음과 같습니다.

<table><thead><tr><th width="155.81817626953125">로그 항목</th><th>정보</th></tr></thead><tbody><tr><td><strong>일시</strong></td><td>로그가 생성된 날짜와 시간(월/일/년 시:분:초 AM(PM))</td></tr><tr><td><strong>사용자</strong></td><td>로그를 생성시킨 작업을 수행한 사용자의 ID</td></tr><tr><td><strong>프로세스</strong></td><td>로그를 생성시킨 작업을 한 애플리케이션 프로세스</td></tr><tr><td><strong>종류</strong></td><td><p>로그의 종류: </p><p>- <strong>등록</strong>: 사용자 PC에서 최초로 실행된 애플리케이션을 서버에 등록한 경우 </p><p>- <strong>허용</strong>: ‘허용’ 정책 아이템이 적용된 경우 </p><p>- <strong>차단</strong>: ‘차단’ 정책 아이템이 적용된 경우</p></td></tr><tr><td><strong>작업</strong></td><td>정책 아이템에 의해 차단되거나 허용된 작업의 종류: <br>- <img src="https://support.mcloudoc.com/galleryDocuments/edbsndd2d5c0528e60d66ef133d5043d8a32d78d9673a6426d50795ad00300ed5ddb042f98cf74c3505be945edabdc6da8e46?inline=true" alt="">: 읽기, <img src="https://support.mcloudoc.com/galleryDocuments/edbsnfb1de56dbdabd502890bf8749bd45c0093fcc9099de1a512331555347a75b237b5d196c6ef5a90f3f9c062b49954e796?inline=true" alt=""> : 쓰기, <img src="https://support.mcloudoc.com/galleryDocuments/edbsnbf0d1dbeabbc13e0af8c454a980a754b7dccd419f211b890464d2e0b6d4ba49f51de673cb23db2b848cd90a5cc170ee6?inline=true" alt=""> : 목록 보기, <img src="https://support.mcloudoc.com/galleryDocuments/edbsn86e43be0d0450f1b3e9a4552df2ab7eeef40a1529e09fab4810bec2002ed55cd995d023f95627362b101c8e1be99a217?inline=true" alt=""> : 삭제</td></tr><tr><td><strong>디스크 종류</strong></td><td>사용자 PC에서 해당 프로세스가 액세스한 디스크의 종류:<br>- <img src="https://support.mcloudoc.com/galleryDocuments/edbsnad5b33fbc1476398482b89b82439b854dd359d5a5ba2842fd17c84eb1fe214d6a112cda9e2ef989cb56042eeb5e4bcc0?inline=true" alt="">: 고정 디스크, <img src="https://support.mcloudoc.com/galleryDocuments/edbsnfb1de56dbdabd502890bf8749bd45c009ea39f1b33285ee2118f5cca14b0e50406b459c9a7c69ec7333d4d302ac918c6?inline=true" alt="">: CD-ROM,  <img src="https://support.mcloudoc.com/galleryDocuments/edbsn036da58e97bf50844039117d6bcfe1f484efe06de34688d1918f2dfca587c0c8d86c21edb44e6b59d1699b51f78bf886?inline=true" alt="">: 네트워크 디스크, <img src="https://support.mcloudoc.com/galleryDocuments/edbsn176bc8efc124ac2da96d8d5ce8fc058fea155b7593f7d397c57f2075e5dcaf893190fdbc17d267efc58e5ffff1eb38aa?inline=true" alt="">: 이동식 디스크<br>- <img src="https://support.mcloudoc.com/galleryDocuments/edbsnf9d3ce95d250f89794b4a46aa1f52980025d2e2ffea4594d863f31d4706f03e3654c845f92b118373c10fefe3d55dcf7?inline=true" alt="">: 온라인 디스크,  <img src="https://support.mcloudoc.com/galleryDocuments/edbsnfb1de56dbdabd502890bf8749bd45c00b83c38646b3eff8b1e82f4d8052ba21ed25030e63e5051697168f0ef5a669800?inline=true" alt="">: 오프라인 디스크, <img src="https://support.mcloudoc.com/galleryDocuments/edbsndd2d5c0528e60d66ef133d5043d8a32d45a42e9f0e4f13e458cbf9367bae437a2a69a309d1146296a89422f9755ca581?inline=true" alt="">: 반출 디스크, <img src="https://support.mcloudoc.com/galleryDocuments/edbsn72aab517f916eb5ef9afecfd3ee9668b4c8e2ab0bf1dae6b7e24edf2b6067c4da599b2069881f5f607000c27ee930287?inline=true" alt="">: 중앙 문서함</td></tr><tr><td><strong>경로</strong></td><td>프로세스의 실행 파일 경로</td></tr><tr><td><strong>최대 저장 크기</strong></td><td>로그를 생성 시킨 정책 아이템에 설정된 최대 파일 크기</td></tr><tr><td><strong>IP</strong></td><td>로그를 생성 시킨 사용자 PC의 IP 주소. 신규 애플리케이션이 서버에 등록될 때 생성된 로그는 서버의 IP 주소가 표시됩니다.</td></tr></tbody></table>

4. 조회한 로그가 화면에 출력된 로그보다 많을 때에는 화면 하단 우측의 **더보기**를  클릭하면 다음 로그를 불러올 수 있습니다.
5. 더 이상 불러올 로그가 없으면 이를 알려주는 팝업 창이 나타납니다. **확인**을 클릭합니다.

### <mark style="color:$primary;">로그 저장하기</mark>

로그 보기 화면에 출력된 로그는 다음과 같은 방법을 통해 파일로 저장할 수 있습니다.

1. 상단 도구모음에서 **내보내기**를 클릭합니다.

<div align="left"><figure><img src="../../../.gitbook/assets/img_024 (1).png" alt="" width="375"><figcaption></figcaption></figure></div>

2. **다른 이름으로 저장** 창이 나타나면 로그를 저장할 폴더와 파일 이름을 지정한 후 **저장**을 클릭합니다. 로그 파일은 해당 폴더에 \*.csv 파일 형식으로 저장됩니다.
