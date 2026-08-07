# 관리자 빠른 시작 가이드 - PC 보안 정책 이해 및 응용하기

PC 보안을 위한 통합 정책은 DiskLock과 DiskLock Plus모듈의 기능별 정책들로 구성됩니다. 통합 정책의 설정 내용은 관리자 웹페이지의 **PC 보안 모듈 관리 – 모듈 통합정책 적용 – 정책 관리** 메뉴에서 확인할 수 있습니다.

다음 그림은 기본 통합 정책의 설정 내용입니다.

<figure><img src="../../.gitbook/assets/img_000 (160).png" alt=""><figcaption></figcaption></figure>

위의 기능별 정책 중 로컬저장금지 정책과 대부분의 DiskLock Plus정책은 **애플리케이션 카테고리**별로 특정 작업을 허용하거나 차단하는 방식으로 설정됩니다. 따라서, 본 가이드에서는 먼저 기본적으로 제공되는 애플리케이션 카테고리 분류에 대해 알아본 후, 각 기능별로 **기본 정책**의 내용을 소개하고, 필요에 따라 다른 정책을 설정하고 부서 또는 사용자별로 적용하는 응용 방법을 설명합니다.

### <mark style="color:$primary;">애플리케이션 카테고리 분류</mark>

문서중앙화 솔루션에서는 윈도우 PC에서 실행되는 애플리케이션을 카테고리별로 분류하여 관리합니다. 애플리케이션 카테고리 분류는 다음 표의 3가지 기본 카테고리를 바탕으로 하여 아래 그림과 같이 하위 카테고리로 확장되는 트리 구조로 이루어집니다.

<table><thead><tr><th width="211">기본 카테고리</th><th>설명</th></tr></thead><tbody><tr><td><strong>Business Applications (업무용 애플리케이션)</strong></td><td>문서 작성 도구, 스프레드시트, 프레젠테이션 소프트웨어, CAD 설계 프로그램과 같이 업무 시 산출물을 생성하는 애플리케이션</td></tr><tr><td><p><strong>Export Applications</strong> </p><p><strong>(반출용 애플리케이션)</strong></p></td><td>웹 브라우저, 메일 클라이언트, 메신저와 같이 문서의 첨부와 외부 전송이 가능한 애플리케이션</td></tr><tr><td><p><strong>FullAccess Applications</strong> </p><p><strong>(전체 접근 애플리케이션)</strong></p></td><td>윈도우 탐색기나 개발용 프로그램과 같이 정상적인 동작을 위해 로컬디스크와 중앙문서함의 모든 파일에 대한 접근 권한이 필요한 애플리케이션</td></tr></tbody></table>

<figure><img src="../../.gitbook/assets/img_001 (148).png" alt=""><figcaption></figcaption></figure>

&#x20;사용자 PC에서 실행되는 애플리케이션(예: Microsoft Word)은 정해진 기준에 따라 특정 하위 카테고리(위 그림에서 MS Word)로 분류되어 최종적으로는 기본 카테고리 중 하나(위 그림에서 Business Applications)에 포함됩니다. 한편, 분류 기준에 해당하지 않을 경우에는 미분류 상태로 남아있게 됩니다.&#x20;

문서중앙화 솔루션의 기본 설정에는 이미 대표적인 애플리케이션들이 주요 용도에 따라 분류되어 있습니다. 단, 고객사에서 특수한 애플리케이션을 업무용으로 사용하는 경우에는 해당 애플리케이션의 분류 상태를 확인하고, 미분류 상태일 경우 직접 Business Applications 카테고리로 분류해야 합니다.

#### 기본 애플리케이션 분류 소개

기본 설정에서 분류되어 있는 애플리케이션의 예는 다음과 같습니다.

<table><thead><tr><th width="194">기본 카테고리</th><th>소속 애플리케이션</th></tr></thead><tbody><tr><td><strong>Business Applications</strong></td><td>Word, Excel, PowerPoint, Publisher, 한글, Notepad, UltraEdit, Acrobat, SolidWorks, AutoCAD, CATIA, CADian, ZWCAD, Inventor, PhotoShop, Illustrator, InDesign 등</td></tr><tr><td><strong>Export Applications</strong></td><td>Chrome, Edge, Whale, KakaoTalk, LINE, Outlook, FileZilla, Dropbox, Google Drive, MYBOX 등</td></tr><tr><td><strong>FullAccess Applications</strong></td><td>File Explorer, Visual Studio, JDK, Node.js 등</td></tr></tbody></table>

#### 애플리케이션 분류 상태 확인하기

특정 애플리케이션의 분류 현황을 확인하는 방법은 다음과 같습니다.

1. **PC 보안 모듈 관리 – DiskLock – 로컬저장금지 – 콘솔 실행** 메뉴에서 DiskLock 콘솔을 실행합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_002 (128).png" alt=""><figcaption></figcaption></figure>

2. 좌측 메뉴에서 **애플리케이션 관리 - 카테고리 분류**를 선택하고, 우측 상단의 **검색** 도구를 클릭합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_003 (111).png" alt=""><figcaption></figcaption></figure>

3. **애플리케이션 이름** 항목에 프로그램 실행 파일명(프로세스명, 예: WINWORD.EXE)을 입력한 후, **검색** 버튼을 클릭합니다. 대소문자 구별 없이 이름의 일부만 입력하여 검색이 가능합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_004 (87).png" alt=""><figcaption></figcaption></figure>

* 위 그림(Microsoft Word의 예)과 같이 애플리케이션이 이미 분류되어 있는 경우, 애플리케이션 카테고리의 전체 경로를 확인할 수 있습니다. 하단의 **확인** 버튼을 클릭하면 다음 그림과 같이 해당 카테고리의 애플리케이션 목록 화면으로 이동할 수 있습니다.

![](<../../.gitbook/assets/img_005 (74).png>)

* 애플리케이션의 경로가 다음과 같이 **미분류**로 표시되거나 검색 결과가 없는 경우에는 해당 애플리케이션의 분류를 새로 설정해야 합니다.

<figure><img src="../../.gitbook/assets/img_006 (62).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" icon="square-poll-horizontal" %}
애플리케이션의 분류를 설정하는 방법은 [**DiskLock 콘솔에서 애플리케이션 카테고리 관리하기**](../../disklock/disklock/disklock/mgmtcategory.md) 매뉴얼 중 [**애플리케이션 분류하기**](../../disklock/disklock/disklock/mgmtcategory.md#classify) 목차를 참고합니다.
{% endhint %}

### <mark style="color:$primary;">로컬저장금지 정책</mark>

로컬저장금지 정책은 실행되는 애플리케이션에 따라 디스크의 종류별로 파일 입출력을 제한하는 정책입니다. 편의상 중앙문서함과 보안디스크는 **안전구역**, 사용자 PC의 고정 디스크 등 나머지 디스크는 **비안전구역**으로 구분합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_008 (47).png" alt=""><figcaption></figcaption></figure>

로컬저장금지 정책의 종류 및 내용은 DiskLock 콘솔에서 **로컬저장금지 – 정책 관리** 메뉴를 클릭하여 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/img_009 (39).png" alt=""><figcaption></figcaption></figure>

위 화면의 정책 목록 중 전사에 적용해야 하는 기본 정책은 **00003. Central Access Control Policy (DOC\_EXPORT)** 정책이며, 이 외에 관리자가 일시적으로 보안을 해제할 필요가 있을 경우 **00000.Free** 정책을 사용할 수 있습니다. 각 정책의 내용은 다음과 같습니다.

<table><thead><tr><th width="209">정책명</th><th>정책 내용</th></tr></thead><tbody><tr><td><strong>00003. Central Access Control Policy (DOC_EXPORT)</strong></td><td>1. 업무용 애플리케이션(Business Applications 카테고리) 실행 시 중앙문서함을 비롯한 안전구역에만 저장을 허용하고, PC의 고정 디스크 등 비안전구역에는 저장을 금지합니다. 1. 업무용 카테고리 외 다른 애플리케이션의 경우에는 안전구역에서의 파일 입출력을 금지하여 중앙문서함 접근을 통제합니다. 1. 반출용 애플리케이션(Export Applications 카테고리)에 대해서는 모든 디스크에 파일 첨부를 금지하되 예외적으로 반출 전용 폴더(DOC_EXPORT)에서만 첨부를 허용하여, 반출이 허용된 문서만 외부 반출이 가능하도록 합니다.</td></tr><tr><td><strong>00000.Free</strong></td><td>모든 작업이 허용되는 보안 해제 정책입니다.</td></tr></tbody></table>

다음 표는 기본 정책이 적용되었을 때 중앙문서함(안전구역)과 C드라이브(고정 디스크, 비안전구역)에서의 문서 작업이 허용/차단되는 예를 케이스별로 정리한 것입니다.

<table data-search="false"><thead><tr><th width="182">사용 애플리케이션</th><th>작업 종류</th><th>파일 위치</th><th>정책 처리 결과</th></tr></thead><tbody><tr><td><strong>Business Applications : Word, Powerpoint, AutoCAD 등</strong></td><td>문서 열람</td><td>중앙문서함</td><td>허용</td></tr><tr><td></td><td></td><td>C드라이브</td><td>허용</td></tr><tr><td></td><td>문서 저장</td><td>중앙문서함</td><td>허용</td></tr><tr><td></td><td></td><td>C드라이브</td><td>차단</td></tr><tr><td><strong>미분류 카테고리 : 비업무용 애플리케이션 또는 자동 분류되지 않은 신규 애플리케이션</strong></td><td>문서 열람</td><td>중앙문서함</td><td>차단</td></tr><tr><td></td><td></td><td>C드라이브</td><td>허용</td></tr><tr><td></td><td>문서 저장</td><td>중앙문서함</td><td>차단</td></tr><tr><td></td><td></td><td>C드라이브</td><td>허용</td></tr><tr><td><strong>Export Applications : Chrome, Outlook, KakaoTalk 등</strong></td><td>문서 첨부</td><td>중앙문서함</td><td>차단 (DOC_EXPORT폴더는 허용)</td></tr><tr><td></td><td></td><td>C드라이브</td><td>차단</td></tr><tr><td></td><td>문서 다운로드</td><td>중앙문서함</td><td>허용</td></tr><tr><td></td><td></td><td>C드라이브</td><td>차단</td></tr></tbody></table>

{% hint style="warning" icon="square-poll-horizontal" %}
로컬저장금지 정책에 대한 상세한 설명은 [**로컬저장금지 정책 소개**](../../disklock/disklock/undefined-2.md)를 참고합니다.

로컬저장금지 정책을 적용하면 고정 디스크에서의 파일 입출력이 제한되어, 경우에 따라 고객사에서 사용하는 애플리케이션이 정상적으로 실행되지 않을 수도 있습니다.&#x20;

이러한 경우, 로컬저장금지 정책에 새로운 정책 아이템을 추가하여 문제를 해결할 수 있습니다. 정책 라이브러리를 사용하면 특정 애플리케이션에 필요한 정책 아이템을 쉽게 추가할 수 있습니다. [**정책 라이브러리를 이용하여 로컬저장금지 정책 설정하기**](../../disklock/disklock/undefined-7/undefined.md)를 참고하세요.
{% endhint %}

### <mark style="color:$primary;">탐색기 복사/이동 정책</mark>

탐색기 복사/이동 정책은 Windows 파일 탐색기를 통한 디스크 간 복사 및 이동 작업을 제한하는 정책입니다. 이 정책에서 다음 그림과 같이 원본 파일이 저장된 디스크와 대상 디스크의 조합별로 복사/이동 작업의 허용 여부를 설정할 수 있습니다.

탐색기 복사/이동 정책은 DiskLock 콘솔에서 **탐색기 복사/이동 정책 – 정책 관리** 메뉴를 클릭하여 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/img_011 (28).png" alt=""><figcaption></figcaption></figure>

기본 정책의 내용은 다음 표와 같습니다. 표에 표시된 바와 같이, 비안전구역에서 모든 디스크로의 복사/이동은 허용![](<../../.gitbook/assets/img_012 (25).png>) 되며, 안전구역의 파일을 비안전구역으로 복사/이동하는 작업은 모두 차단![](<../../.gitbook/assets/img_013 (18).png>) 됩니다. 예를 들어, 고정 디스크에서 중앙문서함으로는 파일을 복사할 수 있으며 <img src="../../.gitbook/assets/image (105).png" alt="" data-size="line">, 중앙문서함에서 고정 디스크로는 복사할 수 없습니다<img src="../../.gitbook/assets/image (106).png" alt="" data-size="line">.

<figure><img src="../../.gitbook/assets/img_016 (14).png" alt=""><figcaption></figcaption></figure>

### <mark style="color:$primary;">웹 반출 예외 정책</mark>

크롬(Chrome), 엣지(Edge) 등 웹 브라우저 사용 시, 로컬저장금지 정책과 클립보드 복사 제어 정책에 따라 파일 첨부, ActiveX 설치, 클립보드 붙여넣기가 차단될 수 있습니다. 단, 웹 반출 예외 정책에 예외 웹사이트를 등록하면 해당 웹사이트에 대해서는 예외적으로 파일 첨부, ActiveX 설치, 또는 클립보드 붙여넣기를 허용할 수 있습니다.&#x20;

다음은 기본 설정에서 제공되는 정책(**00000.전사정책**) 내용의 일부입니다. 주요 금융 기관, 정부 기관, 헬프데스크 등이 예외 웹사이트로 등록되고, 고정 디스크 파일의 첨부와 ActiveX 설치가 허용되어 있습니다.

<figure><img src="../../.gitbook/assets/img_017 (10).png" alt=""><figcaption></figcaption></figure>

\
전체 예외 사이트를 확인하기 위해서는 **PC 보안 모듈 관리 - DiskLock - 웹 반출 예외 정책 - 정책 관리** 메뉴를 선택합니다. 좌측 정책 목록에서 정책명\*\*(00000.전사정책\*\*)을 클릭하면 우측 영역에서 정책 내용을 확인할 수 있습니다.

{% hint style="warning" icon="square-poll-horizontal" %}
고객사에서 추가로 예외 처리가 필요한 사이트가 있거나, 이미 등록되어 있는 사이트를 삭제할 필요가 있는 경우, 정책 아이템을 추가 또는 변경해야 합니다. 또한, 특정 사용자에게만 다른 정책을 적용해야 할 경우에는 새로운 정책을 추가해야 합니다. 자세한 방법은 [**웹 반출 예외 정책 관리하기**](../../disklock/disklock/undefined-9.md)를 참고합니다.
{% endhint %}

### <mark style="color:$primary;">문서반출 정책</mark>

로컬저장금지 정책을 적용하면 중앙문서함의 문서를 이메일·메신저에 첨부하거나 로컬 디스크에 저장하는 것이 차단될 수 있습니다. 이러한 경우에 문서 반출 기능을 사용하면, 중앙문서함 문서를 로컬 디스크로 반출하거나 이메일 등에 첨부할 수 있습니다. 문서 반출을 위해서는 승인권자의 승인이 필요하며, 문서반출 정책에 따라 사용자가 문서반출 신청 시 적용될 결재 방식과 반출 가능 용량, 반출 기한, 반출 가능한 디스크 등이 결정됩니다.

#### 기본 정책 소개

기본 설정에서 제공되는 정책은 다음과 같이 확인할 수 있습니다.

1. **PC 보안 모듈 관리 – DiskLock – 문서반출 – 정책 관리** 메뉴를 선택한 후, 좌측 정책 목록에서 정책명(**00000.기본정책**)을 클릭합니다.     &#x20;

<figure><img src="../../.gitbook/assets/img_019 (9).png" alt=""><figcaption></figcaption></figure>

2. 우측 영역에서 다음과 같은 정책 내용을 확인할 수 있습니다.

| 정책 항목                  | 설정값       | 내용                                                                                                                       |
| ---------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------ |
| **결재 방식**              | 선결재       | 문서반출 신청을 승인권자가 승인한 후에 해당 문서가 반출 폴더에 복사됩니다. 반출 폴더에 복사된 문서는 이메일, 메신저 등에 첨부할 수 있습니다.                                        |
| **용량 제한**              | 100MB로 제한 | 파일 용량을 합산하여 한 번에 최대 100MB까지 반출 신청할 수 있습니다.                                                                               |
| **반출 기한**              | 최대 7일     | 문서반출 신청 시 반출 기한을 최대 7일까지 지정할 수 있습니다. 반출 기한 만료 후에는 반출 폴더를 사용할 수 없습니다.                                                     |
| **공개 반출 시 반출 가능한 디스크** | 반출 디스크    | 공개 반출 신청 시에도 반출 폴더에 저장된 문서를 반출 보안디스크로만 반출할 수 있으며, 고정 디스크나 이동식 디스크로는 반출이 불가능합니다. 보안 반출 신청 시에는 기본적으로 반출 보안디스크로만 반출이 제한됩니다. |
| **폴더 반출 가능 여부**        | 허용        | 폴더 단위로 반출 신청이 가능합니다.                                                                                                     |

#### 정책 추가 생성하기

특정 부서 또는 사용자에게 기본 정책과 다른 설정을 적용하여 좀 더 유연한 반출을 허용할 수도 있습니다. 이를 위해서는, 새로운 문서반출 정책을 만들어야 합니다. 다음과 같은 내용을 포함한 정책을 예로 들어, 정책을 생성하는 방법을 설명합니다.

* **결재 방식**: 후결재 (승인 전에 우선 반출이 가능하며, 승인권자가 사후에 확인함)
* **용량 제한**: 제한 없음
* **공개 반출 시 반출 가능한 디스크**: 반출 디스크를 비롯해 고정/이동식/네트워크 디스크로도 반출 허용

1. **PC 보안 모듈 관리 – DiskLock – 문서반출 – 정책 관리** 메뉴를 선택합니다.
2. 좌측 **정책 목록** 우측의   ![](<../../.gitbook/assets/img_020 (6).png>)를 클릭하여 정책명(필수)과 정책 내용을 입력한 후, **확인**을 클릭하면 새 정책이 생성됩니다.&#x20;

<figure><img src="../../.gitbook/assets/img_021 (6).png" alt=""><figcaption></figcaption></figure>

<div align="left"><figure><img src="../../.gitbook/assets/img_022 (6).png" alt=""><figcaption></figcaption></figure></div>

3. 정책 목록 중 생성된 정책이 선택된 상태에서, 우측 정책 내용을 다음과 같이 변경한 후, **적용** 버튼을 클릭합니다.

<figure><img src="../../.gitbook/assets/img_023 (7).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" icon="lightbulb-exclamation-on" %}
기존 정책을 변형한 정책을 생성하고자 할 경우, 변형할 정책 우측의  <img src="../../.gitbook/assets/img_025 (4).png" alt="" data-size="line"> 를 클릭한 후, **사본 생성**을 선택합니다. 이후, 생성된 사본의 이름을 변경한 후, 변경이 필요한 정책 항목을 설정하여 적용하는 방법으로 더욱 손쉽게 새 정책을 만들 수 있습니다.&#x20;

![](<../../.gitbook/assets/img_026 (3).png>)
{% endhint %}

{% hint style="warning" icon="square-poll-horizontal" %}
생성한 정책을 부서 또는 사용자에게 적용하기 위해서는 별도로 통합 정책을 생성하여 적용해야 합니다. 자세한 내용은 아래 [**모듈 통합 정책 생성 및 적용하기**](pc-1.md#undefined-15) 목차를 참고합니다.
{% endhint %}

### <mark style="color:$primary;">화면 캡처 금지 정책</mark>

화면 캡처 금지 기능은 사용자가 지정된 애플리케이션 실행 중 화면 캡처를 시도할 경우, 내용이 저장되지 않도록 차단하는 기능입니다. 화면 캡처 금지 정책이 적용되면, 정책에 등록된 애플리케이션에 대해 캡처 시도 시, 오류 메시지가 표시되거나 캡처 화면에서 해당 애플리케이션 영역이 제외됩니다.

화면 캡처 금지 정책은 **PC 보안 모듈 관리 – DiskLock Plus – 화면 캡처 금지 – 정책 관리** 메뉴에서 확인할 수 있습니다. 아래 그림과 같이 좌측 정책 목록에서 정책을 선택하면 우측 영역에 정책에 등록된 애플리케이션 카테고리가 표시됩니다. &#x20;

<figure><img src="../../.gitbook/assets/img_028 (2).png" alt=""><figcaption></figcaption></figure>

기본으로 제공되는 정책은 다음과 같습니다.

<table><thead><tr><th width="150">정책명</th><th>등록된 애플리케이션 카테고리</th><th>정책 내용</th></tr></thead><tbody><tr><td><strong>00001.기본정책</strong></td><td><p>Business Applications</p><p>Windows Remote Desktop</p></td><td>업무용 애플리케이션과 원격 데스크탑의 화면 캡처가 금지됨</td></tr><tr><td><strong>00000.모두허용</strong></td><td>없음</td><td>모든 애플리케이션 실행 시 화면 캡처가 허용됨</td></tr></tbody></table>

{% hint style="warning" icon="square-poll-horizontal" %}
새 정책을 생성하거나 정책을 변경하는 방법은 [**화면 캡처 금지 정책 관리하기**](../../disklock-plus/disklock-plus/undefined.md)를 참고합니다.
{% endhint %}

### <mark style="color:$primary;">클립보드 복사 제어 정책</mark>

클립보드 복사 제어 기능은 사용자가 지정된 애플리케이션의 컨텐츠를 복사하여 다른 애플리케이션에 붙여 넣지 못하도록 제한하는 기능입니다. 클립보드 복사 제어 정책이 적용되면, 정책에 등록된 애플리케이션에서 등록되지 않은 애플리케이션으로 문서 내용을 복사할 수 없습니다.

클립보드 복사 제어 정책은 **PC 보안 모듈 관리 – DiskLock Plus – 클립보드 복사 제어 – 정책 관리** 메뉴에서 확인할 수 있습니다. 아래 그림과 같이 좌측 정책 목록에서 정책을 선택하면 우측 영역에 정책에 등록된 애플리케이션 카테고리가 표시됩니다.&#x20;

<figure><img src="../../.gitbook/assets/img_030 (2).png" alt=""><figcaption></figcaption></figure>

기본으로 제공되는 정책은 다음과 같습니다.

<table><thead><tr><th width="145">정책명</th><th width="214">등록된 애플리케이션 카테고리</th><th>정책 내용</th></tr></thead><tbody><tr><td><strong>00001.기본정책</strong></td><td>Business Applications</td><td>업무용 애플리케이션으로 열람 중인 문서 내용을 업무용 카테고리에 등록되지 않은 다른 애플리케이션으로 복사할 수 없음</td></tr><tr><td><strong>00000.모두허용</strong></td><td>없음</td><td>모든 애플리케이션 간의 클립보드 복사가 허용됨</td></tr></tbody></table>

{% hint style="warning" icon="square-poll-horizontal" %}
새 정책을 생성하거나 정책을 변경하는 방법은 [**클립보드 복사 제어 정책 관리하기**](../../disklock-plus/disklock-plus/undefined-1.md)를 참고합니다. 
{% endhint %}

### <mark style="color:$primary;">프린트 워터마크 정책</mark>

프린트 워터마크 정책에서는 워터마크로 사용할 이미지·텍스트와 사용자 정보, 워터마크를 출력에서 제외할 예외 프로세스 등 각종 인쇄 옵션을 설정할 수 있습니다. 또한 통합 모듈 정책에서는 워터마크 사용 여부를 다음 중 하나로 선택할 수 있습니다.&#x20;

> • 이미지로 사용
>
> • 텍스트로 사용
>
> • 사용 안 함

프린트 워터마크 정책 내용은 **PC 보안 모듈 관리 – DiskLock Plus – 프린트 워터마크 – 정책 관리** 메뉴에서 설정할 수 있습니다.&#x20;

아래 그림은 정책의 기본 설정 내용입니다. 고객사의 워터마크 이미지와 텍스트를 등록하면 워터마크 사용 시 우측의 미리보기와 같은 모양으로 출력됩니다. 사용자 정보로는 기본적으로 컴퓨터 이름, 윈도우 계정명, 사용자 부서 정보, 사용자 IP, 인쇄일시, 사용자 이름, 사용자 ID가 출력됩니다.

이미지, 텍스트 등 워터마크 백그라운드와 사용자 정보 출력 내용, 출력 위치 등의 옵션을 설정하는 방법은 [**프린트 워터마크 정책 관리하기**](../../disklock-plus/disklock-plus/undefined-2.md)를 참고합니다.

<figure><img src="../../.gitbook/assets/img_032 (2).png" alt=""><figcaption></figcaption></figure>



<figure><img src="../../.gitbook/assets/img_033 (2).png" alt=""><figcaption></figcaption></figure>

### <mark style="color:$primary;">인쇄 제어 정책</mark>

인쇄 제어 정책이 적용되면, 정책의 내용에 따라 특정 프린터 또는 특정 애플리케이션에서만 인쇄가 허용되거나 차단됩니다.&#x20;

#### 프린터 등록하기

인쇄 제어 정책을 사용하기 위해서는 먼저 고객사의 프린터 정보를 등록해야 합니다. 프린터 정보는 **PC 보안 모듈 관리 – DiskLock Plus – 인쇄 제어 – 프린터 등록/제거** 메뉴에서 등록할 수 있습니다. 자세한 방법은 **인쇄 제어 정책 관리하기** 매뉴얼 중 [**프린터 등록/제거하기**](../../disklock-plus/disklock-plus/undefined-3.md#undefined-1)를 참고합니다.

기본적으로 등록되어 있는 프린터는 다음과 같습니다.

<figure><img src="../../.gitbook/assets/img_034 (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" icon="square-poll-horizontal" %}
위의 등록 프린터 중 Microsoft XPS Document Writer는 시스템 내부적으로 사용되므로 반드시 포함되어 있어야 합니다. 또한 VMWare를 사용하는 경우, 위의 내용과 같이 TP Output Gateway가 프린터 드라이버로 등록되어 있어야 합니다.
{% endhint %}

#### 기본 정책 소개

인쇄 제어 정책은 **PC 보안 모듈 관리 – DiskLock Plus – 인쇄 제어 – 정책 관리** 메뉴에서 확인할 수 있습니다. 기본 정책(**00000.기본정책**)의 내용은 다음 그림과 같습니다. 기본 정책이 적용되면 등록된 모든 프린터에서 업무용 애플리케이션에서만 인쇄가 가능하며, 그 외의 프린터나 애플리케이션 사용 시에는 인쇄가 불가능하게 됩니다.&#x20;

<figure><img src="../../.gitbook/assets/img_036 (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" icon="square-poll-horizontal" %}
Print Services 카테고리에는 시스템 내부적으로 인쇄를 위해 사용되는 프로세스가 포함됩니다.
{% endhint %}

{% hint style="warning" icon="square-poll-horizontal" %}
인쇄 제어 정책에 대한 자세한 설명과 정책을 생성, 변경하는 방법은 [**인쇄 제어 정책 관리하기**](../../disklock-plus/disklock-plus/undefined-3.md)를 참고합니다.
{% endhint %}

### <mark style="color:$primary;">모듈 통합 정책 생성 및 적용하기</mark>

부서나 사용자의 특성에 따라 기본 정책 외에 다른 정책을 생성하여 적용할 경우, 먼저 필요한 기능별 정책을 생성한 후 통합 정책을 설정하여 적용해야 합니다. 여기서는 위의 [**문서반출 정책**](pc-1.md) 목차에서 부서별 정책의 예로 소개한 **00001.영업팀정책**을 사용하여 통합 정책을 생성하고, 영업 부서에 적용하는 방법을 예를 들어 설명합니다.

#### 통합 정책 생성하기

모듈 통합 정책을 생성하는 방법은 다음과 같습니다. 여기서는 기본 정책을 변형한 정책을 생성하기 위해 기본 정책의 사본을 생성하여 변경하는 방법을 설명합니다.

1. **PC 보안 모듈 관리 – 모듈 통합정책 적용 – 정책 관리** 메뉴를 선택합니다.
2. 좌측 정책 목록에서 **00001.기본정책** 우측의 <img src="../../.gitbook/assets/img_039 (3).png" alt="" data-size="line"> 를 클릭하고, 펼쳐진 메뉴 목록에서 **사본 생성**을 클릭합니다. 확인 창이 팝업되면 **확인**을 클릭합니다. &#x20;

<figure><img src="../../.gitbook/assets/img_040 (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" icon="lightbulb-exclamation-on" %}
정책 항목을 모두 새로 설정하려면 좌측 **정책 목록** 우측의  ![](<../../.gitbook/assets/img_042 (2).png>) 를 클릭하여 새 정책을 생성하는 편이 좋습니다.
{% endhint %}

3\.   생성된 사본 우측의  <img src="../../.gitbook/assets/img_043 (2).png" alt="" data-size="line">를 클릭하고 **이름 변경**을 클릭한 후, ‘이름 변경’ 창에서정책명을 입력하고 **확인**을 클릭합니다.  &#x20;

<div align="left"><figure><img src="../../.gitbook/assets/img_044 (2).png" alt=""><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../../.gitbook/assets/img_045 (2).png" alt=""><figcaption></figcaption></figure></div>

4. 정책 목록에서 설정할 통합 정책이 선택된 상태에서, 우측 영역의 기능별 정책 중 변경할 정책 우측의 아래 화살표를 클릭하고, 적용할 정책을 선택합니다. 아래 그림의 예에서는 문서 반출 정책으로 **00001.영업팀 정책**을 선택합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_046 (1).png" alt=""><figcaption></figcaption></figure>

5. 하단의 **적용** 버튼을 클릭하여 변경 사항을 시스템에 적용합니다.

{% hint style="warning" icon="square-poll-horizontal" %}
**정책 적용 구간 설정** 항목에서는 사용자 PC에서 보안 정책이 적용(**ON**) 또는 해제(**OFF**)되는 구간을 설정할 수 있습니다. 기본적으로는 PC 부팅 시부터 종료 시까지 정책에 적용되도록 설정됩니다.
{% endhint %}

#### 통합 정책 적용하기

생성한 모듈 통합 정책을 특정 부서 또는 사용자에게 적용하는 방법은 다음과 같습니다.

1. **PC 보안 모듈 관리 – 모듈 통합정책 적용 – 정책 적용** 메뉴를 선택합니다.
2. 좌측의 조직도에서 정책을 적용할 대상을 선택합니다. 조직도 트리를 펼쳐서 부서 또는 사용자를 찾거나, 상단의 검색 아이콘   ![](<../../.gitbook/assets/img_048 (1).png>)을 클릭하여 부서명 또는 사용자 이름으로 검색할 수도 있습니다.&#x20;

![](<../../.gitbook/assets/img_049 (1).png>)

* 검색 아이콘을 클릭한 경우에는 ‘검색’ 창에서 이름을 입력하고 **검색**을 클릭합니다. 이름의 일부만 입력해도 검색할 수 있습니다. 표시되는 결과를 선택하고 **확인**을 클릭하면 조직도에서 해당 부서 또는 사용자가 선택됩니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_050 (1).png" alt="" width="325"><figcaption></figcaption></figure></div>

3. 우측의 기본 정책 목록에서 정책을 선택합니다. 아래 그림과 같이 조직도에서 영업본부를 선택한 경우, 선택한 정책이 하위 부서와 사용자에게 모두 상속되어 적용되는 것을 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/img_051 (1).png" alt=""><figcaption></figcaption></figure>

4. 우측 상단의 **적용** 버튼을 클릭하여 화면의 변경 사항을 시스템에 적용합니다.

{% hint style="danger" %}
정책 선택 후 화면에 정책이 적용되어 보이더라도, 반드시 **적용** 버튼을 클릭해야 시스템에 정책 설정 내용이 반영됩니다.
{% endhint %}

{% hint style="warning" icon="square-poll-horizontal" %}
기본 정책 외에 일정 기간 동안에만 한시적으로 적용되는 임시 정책을 설정할 수도 있습니다. 임시 정책을 설정하는 방법은 [**모듈 통합정책 생성 및 적용하기**](../../disklock/undefined/undefined.md) 매뉴얼 중 [**모듈 통합정책 적용하기**](../../disklock/undefined/undefined.md#undefined-1) 목차를 참고합니다.
{% endhint %}
