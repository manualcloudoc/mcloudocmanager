# 로컬저장금지 정책 소개

로컬저장금지 기능은 사용자의 로컬 디스크에 문서 저장을 금지하고 외부로 문서 첨부 및 전송을 차단하는 DiskLock의 핵심 기능으로, 사내의 모든 문서를 중앙 문서함에만 저장하여 안전하게 통합 관리하기 위해 사용됩니다. 이를 위해 로컬저장금지 기능은 **애플리케이션 카테고리**를 사용하여 애플리케이션을 종류별로 구분하고, 애플리케이션 카테고리마다 각각의 디스크에서 수행할 수 있는 파일 작업에 대한 권한(허용/차단)을 설정하는 **로컬저장금지 정책**을 사용합니다.&#x20;

### 애플리케이션 카테고리와 디스크

DiskLock의 로컬저장금지 정책을 비롯하여 DiskLock Plus의 일부 보안 기능을 위해, 사용자 PC에서 사용되는 애플리케이션들은 그 특성에 따라 다음과 같은 애플리케이션 카테고리로 분류됩니다. 이 카테고리에 속하지 않는 애플리케이션은 ‘**미분류**’ 카테고리에 속하게 됩니다.

<table><thead><tr><th width="189">카테고리</th><th>설명</th><th>대표적인 애플리케이션</th></tr></thead><tbody><tr><td><strong>Business Applications</strong></td><td>업무 시 산출물을 생성하는 업무용 애플리케이션</td><td>MS Office, 한컴 오피스, AutoCAD</td></tr><tr><td><strong>Export Applications</strong></td><td>문서의 첨부와 외부 전송이 가능한 반출용 애플리케이션</td><td>Outlook, Chrome, 카카오톡, Telegram, FTP</td></tr><tr><td><strong>FullAccess Applications</strong></td><td>정상적인 동작을 위해 로컬과 중앙 서버의 모든 파일에 대한 접근 권한이 필요한 애플리케이션</td><td>윈도우 탐색기, Visual Studio, Winzip</td></tr></tbody></table>

파일을 저장하는 데 사용되는 각종 디스크들은 DiskLock에 의해 보호되는지 여부에 따라 **안전구역**과 **비안전구역**으로 나누어집니다. 기본적으로 사용자 PC의 로컬 디스크는 비안전구역, 중앙 문서함은 안전구역에 해당됩니다. 필요한 경우 사용자 PC에도 보안디스크를 생성하여 안전구역으로 사용할 수 있습니다.

다음은 사용자 PC에 보안디스크(온라인, 오프라인, 반출)를 생성한 경우, 안전구역과 비안전구역에 어떤 디스크가 포함되는지 보여주는 그림입니다.​

![](<../../.gitbook/assets/img_000 (124).png>)

{% hint style="warning" icon="square-poll-horizontal" %}
애플리케이션 카테고리와 보안디스크에 대한 상세한 설명은 각각 [**애플리케이션 카테고리 소개**](undefined-1.md)와 [**보안디스크 소개**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/disklock/undefined-2/undefined)를 참고합니다.
{% endhint %}

### <mark style="color:$primary;">로컬저장금지 정책 유형</mark>

로컬저장금지 기능은 기본적으로 다음과 같은 두 가지 수준의 정책으로 구현할 수 있습니다.

* **중앙 저장 유도 정책(Central Storage Induction Policy)**

중요 문서를 중앙문서함에만 저장하고 관리하기 위한 정책으로, 업무 문서를 생산하는 **Business Applications 카테고리**의 애플리케이션을 **안전구역에만 저장**이 가능하도록 권한을 제한(비안전구역의 쓰기 권한은 차단)하고, 나머지 카테고리의 애플리케이션은 전체 디스크에 대한 모든 권한을 허용합니다.

* **중앙 접근 통제 정책 (Central Access Control Policy)**

Business Applications 카테고리의 권한만 제한한 중앙 저장 유도 정책을 사용할 경우, 권한을 제한하지 않은 다른 카테고리의 애플리케이션을 통한 문서 유출의 가능성이 있습니다. 이를 방지하기 위해 반드시 안전구역의 접근이 필요한 **일부 FullAccess Applications** 카테고리 애플리케이션 외에는 안전구역의 중요 문서에 접근하지 못하도록 **안전구역의 읽기/쓰기 권한**을 모두 **차단**합니다. 이 정책을 사용하면 Business Applications에 대해 안전구역에만 저장이 가능하도록 하여 문서중앙화를 유도할 뿐 아니라, 업무에 필요한 프로그램(Business Applications와 일부 FullAccess Applications)외에는 안전구역에 접근할 수 없도록 하여 내부 사용자에 의한 정보 유출 가능성을 차단할 수 있습니다.

다음은 두 정책의 안전 구역과 비안전구역에서 Business Applications 카테고리와 다른 애플리케이션 카테고리의 읽기/쓰기 권한을 보여주는 그림입니다.

![](<../../.gitbook/assets/img_002 (100).png>)

중앙 저장 유도 정책과 중앙 접근 통제 정책 모두 외부로 문서를 전송할 수 있는 **Export Applications** 카테고리에 대해 **안전구역으로만 파일을 다운로드(쓰기)**&#xD560; 수 있고 **반출 승인된 문서만 첨부(읽기**)가 가능하도록 동일하게 설정합니다. 사내 주요 문서가 로컬 디스크(비안전구역)에 남아있을 수 있으므로 안전구역 뿐 아니라 **비안전구역**까지도 **첨부를 금지**하고, 반출이 승인된 문서가 저장되는 안전구역 내 **반출 폴더** 대해서만 **모든 권한을 허용**하여 **Export Applications** 카테고리의 애플리케이션은 반출 승인된 문서만 첨부하고 외부로 전송할 수 있습니다.

![](<../../.gitbook/assets/img_003 (85).png>)

다음은 두 정책에서 각 애플리케이션 카테고리별로 안전구역과 비안전구역에 대해 설정하는 권한을 정리한 표입니다.

* 윈도우 탐색기: 모든 디스크에 대한 모든 권한 허용
* 특별한 권한이 필요한 애플리케이션에 대해 개별적인 권한 설정

<table><thead><tr><th width="125.45452880859375">카테고리</th><th>중앙 저장 유도 정책</th><th>중앙 접근 통제 정책</th></tr></thead><tbody><tr><td><strong>Business Applications</strong></td><td><ul><li>안전구역: 모든 권한 허용 </li><li>비안전구역: 쓰기 차단</li></ul></td><td>왼쪽과 동일</td></tr><tr><td><strong>Export Applications</strong></td><td><ul><li>반출 폴더(안전구역): 읽기(첨부) 허용</li><li>반출 폴더 외 안전구역: 읽기(첨부) 차단, 쓰기(다운로드) 허용</li><li>비안전구역: 읽기(첨부) 차단, 쓰기(다운로드) 차단</li></ul></td><td>왼쪽과 동일</td></tr><tr><td><strong>FullAccess Applications</strong></td><td><ul><li>안전구역: 모든 권한 허용</li><li>비안전구역: 모든 권한 허용</li></ul></td><td><ul><li>윈도우 탐색기: 모든 디스크에 대한 모든 권한 허용</li><li>특별한 권한이 필요한 애플리케이션에 대해 개별적인 권한 설정</li></ul></td></tr><tr><td><strong>미분류</strong></td><td><ul><li>안전구역: 모든 권한 허용</li><li>비안전구역: 모든 권한 허용</li></ul></td><td><ul><li>안전구역: 모든 권한 차단</li><li>비안전구역: 모든 권한 허용</li></ul></td></tr></tbody></table>

{% hint style="warning" icon="square-poll-horizontal" %}
중앙 저장 유도 정책과 중앙 접근 통제 정책 모두 Business Applications 카테고리의 비안전구역에 대한 권한을 모두 차단하기 때문에 비안전구역의 파일 입출력이 필요한 업무용 프로그램은 정상적으로 동작하지 않을 수 있습니다. 이를 방지하기 위해서는 해당 업무용 프로그램에 대한 예외 정책을 추가해주어야 합니다.
{% endhint %}

### <mark style="color:$primary;">로컬저장금지 정책 구성</mark>

로컬저장금지 정책은 아래 그림과 같이 여러 **정책 아이템**의 계층 구조로 이루어집니다.

![](<../../.gitbook/assets/img_005 (56).png>)

로컬저장금지 정책을 설정하는 것은 정책에 맞게 정책 아이템들을 생성하고 정책 아이템을 적절한 순서로 배치하는 것입니다. 최하단의 기본 정책 아이템을 기초(정책 아이템1)로, 하위 정책 아이템에 대한 예외 규정이 되는 정책 아이템이 상단에 순차적으로 덧붙여지는 방식으로 정책이 구성되며, 정책 아이템이 상단에 위치할수록 높은 우선 순위를 가집니다.

로컬저장금지 정책을 구성하는 정책 아이템은 우선순위가 높을수록 정책의 상단에 위치하게 되고 우선적으로 적용됩니다. 사용자가 애플리케이션을 실행하면 문서중앙화 솔루션은 사용자에게 적용된 로컬저장금지 정책에서 가장 우선순위가 높은 정책 아이템부터 적용합니다. 애플리케이션이 그 정책 아이템에 해당되지 않으면 그 다음 우선순위의 정책 아이템으로 넘어갑니다. 이런 방식으로 계속해서 해당 애플리케이션에 적용될 수 있는 정책 아이템을 찾습니다. 해당 애플리케이션에 맞는 정책 아이템을 찾으면 정책 아이템에 설정된 권한에 따라 애플리케이션의 동작을 허용 또는 차단하게 됩니다.

로컬저장금지 정책의 가장 하단에는 모든 애플리케이션에 적용될 수 있는 정책 아이템이 위치하도록 하여 어떤 애플리케이션이든 최소한 하나의 정책 아이템에 의해 처리될 수 있도록 합니다.

#### 정책 아이템

각 정책 아이템은 특정 애플리케이션 카테고리에 대해 특정 디스크의 접근 권한을 정의한 것으로 주요 설정 항목은 다음과 같습니다.

<table><thead><tr><th width="182.727294921875">항목</th><th>설명</th></tr></thead><tbody><tr><td><strong>애플리케이션 카테고리</strong></td><td>정책 아이템이 적용될 애플리케이션 카테고리</td></tr><tr><td><strong>권한</strong></td><td>애플리케이션 카테고리에 속하는 애플리케이션에 허용하거나 차단할 권한(읽기, 쓰기, 삭제, 목록 보기)</td></tr><tr><td><strong>디스크</strong></td><td>권한이 적용될 대상 디스크</td></tr></tbody></table>

앞 그림의 정책 아이템 예시(정책 아이템 5)는 아래 표와 같은 정책 아이템을 DiskLock 콘솔에서 설정하는 화면을 표시한 것입니다.



**Allow ClouDoc : Windows Explorer 정책 아이템**

<table><thead><tr><th width="176.3636474609375">항목</th><th>Text값</th></tr></thead><tbody><tr><td><strong>애플리케이션 카테고리</strong></td><td>FullAccess Applications>>System>>Operating Systems>>Windows Explorer (윈도우 탐색기 프로그램이 분류되는 카테고리)</td></tr><tr><td><strong>권한</strong></td><td>모든 권한</td></tr><tr><td><strong>디스크</strong></td><td>온라인 보안디스크, 오프라인 보안디스크, 중앙 문서함</td></tr></tbody></table>

이 정책 아이템은 **윈도우 탐색기 프로그램**에 **온라인 보안디스크**와 **오프라인 보안디스크**, 그리고 **중앙 문서함**에 대해 **모든 권한**을 **허용**합니다.

{% hint style="warning" icon="square-poll-horizontal" %}
로컬저장금지 정책과 정책 아이템은 문서중앙화 솔루션의 **DiskLock 콘솔**에서 설정할 수 있습니다. DiskLock 콘솔에서 로컬저장금지 정책과 정책 아이템을 설정하는 방법은 [**로컬저장금지 정책 생성 및 편집하기**](disklock/disklock.md) 와 [**로컬저장금지 정책 아이템 설정하기**](disklock/disklock-1.md)를 참고합니다.&#x20;
{% endhint %}

### <mark style="color:$primary;">중앙 저장 유도 정책의 정책 아이템 구성</mark>

중앙 저장 유도 정책을 구현하기 위해서는 정책에 다음과 같은 정책 아이템들이 포함되어야 합니다.

<figure><img src="../../.gitbook/assets/img_006 (48).png" alt=""><figcaption></figcaption></figure>

로컬저장금지 정책이 적용될 때에는 가장 상위에 있는 정책 아이템부터 적용되므로 이 순서대로 각 정책 아이템에 대해 살펴봅니다.

**⑥ 고정 디스크 접근이 제한된 애플리케이션 구동을 위한 예외 정책 아이템들**

중앙 저장 유도 정책은 고정 디스크(비안전구역)에 대해 Business Applications카테고리 애플리케이션의 쓰기가 금지되고(<img src="../../.gitbook/assets/image (4).png" alt="" data-size="line">번 정책 아이템), Export Applications의 읽기/쓰기가 금지됩니다(<img src="../../.gitbook/assets/image (5).png" alt="" data-size="line">번 정책 아이템). Business Applications와 Export Applications 카테고리 애플리케이션 중 고정 디스크의 특정 영역에 파일 입출력이 필수적인 경우, 이 애플리케이션들의 구동을 위한 예외 규정이 정의된 정책 아이템들이 필요합니다. 이 영역에는 이러한 예외 정책 아이템들이 위치합니다.

\
**⑤ Export Applications 애플리케이션 카테고리에 반출 폴더의 첨부를 허용하는 정책**

중앙 저장 유도 정책에서는 Export Applications 카테고리애플리케이션은 안전구역에 있는 반출 폴더의 첨부가 허용되므로 이를 위해 반출 폴더의 읽기 권한을 허용하는 정책 아이템을 설정합니다.

**④ Export Applications 카테고리에 안전구역의 다운로드를 허용하는 정책 아이템**

중앙 저장 유도 정책에서는 Export Applications 카테고리 애플리케이션을 통해 외부에서 수신한 문서를 안전구역으로 다운로드할 수 있습니다. 이를 위해 안전구역의 쓰기 권한을 허용하는 정책 아이템을 설정합니다.

**③ Export Applications카테고리에 전체 디스크의 첨부/다운로드를 금지하는 정책 아이템**

중앙 저장 유도 정책에서 Export Applications 카테고리 어플리케이션은 외부에서 수신한 문서를 비안전구역으로 다운로드하거나 반출 폴더를 제외한 나머지 디스크(안전구역과 비안전구역 모두)의 문서를 첨부해서 전송할 수 없습니다. 이를 위해 모든 디스크에 대해 첨부(읽기 권한), 다운로드(쓰기 권한)를 차단하는 정책 아이템을 설정합니다.

**② Business Applications 카테고리에 비안전구역의 쓰기를 금지하는 정책 아이템**

중앙 저장 유도 정책에서는 Business Applications카테고리는 안전구역에만 문서를 저장할 수 있으므로 비안전구역에 대한 쓰기 권한을 차단하는 정책 아이템을 설정합니다.

**① 모든 애플리케이션에 대해 전체 권한을 허용하는 정책 아이템**

이 정책 아이템은 모든 애플리케이션에 대해 전체 디스크에 대한 모든 권한을 허용합니다. 상위 정책 아이템에서 별도로 권한이 설정되지 않는 애플리케이션에게 전체 접근 권한이 허용될 수 있도록 모든 로컬저장금지 정책에 반드시 포함되어야 하는 기본 정책 아이템입니다. 중앙 저장 유도 정책에서는 Business Applications 와 Export Applications 카테고리에 속하지 않는 모든 애플리케이션이 이 정책 아이템에 따라 모든 디스크에 모든 권한이 허용됩니다.

## 중앙 접근 통제 정책의 정책 아이템 구성

중앙 접근 통제 정책을 구현하기 위해서는 정책에 다음과 같은 정책 아이템들이 포함되어야 합니다.

![](<../../.gitbook/assets/img_007 (41).png>)

중앙 접근 통제 정책의 정책 아이템 중 <img src="../../.gitbook/assets/image (6).png" alt="" data-size="line">, <img src="../../.gitbook/assets/image (7).png" alt="" data-size="line">, <img src="../../.gitbook/assets/image (8).png" alt="" data-size="line">\~<img src="../../.gitbook/assets/image (9).png" alt="" data-size="line">번 정책 아이템은 중앙 저장 유도 정책에서 사용하는 정책 아이템과 동일합니다. 중앙 접근 통제 정책에서는 Business Applications 카테고리 외의 기타 프로그램(FullAccess Applications 카테고리와 미분류 카테고리)에도 권한이 제한되기 때문에, 이를 위해 위 그림의 노란색 상자에 있는 <img src="../../.gitbook/assets/image (10).png" alt="" data-size="line">\~<img src="../../.gitbook/assets/image (11).png" alt="" data-size="line">번 정책 아이템을 추가로 설정해야 합니다.

**⑤ 윈도우 탐색기의 안전구역 읽기/쓰기를 허용하는 정책 아이템**

FullAccess Applications 카테고리에 속하는 윈도우 탐색기의 경우, 안전구역에서도 정상적으로 동작할 수 있어야 하므로 윈도우 탐색기에 대해 안전구역에서의 모든 권한을 허용하는 정책을 설정합니다.&#x20;

**④ Business Applications 카테고리에 안전구역의 읽기/쓰기를 허용하는 정책 아이템**

중앙 접근 통제 정책은 Business Applications 카테고리에 안전구역의 모든 권한을 허용하므로 <img src="../../.gitbook/assets/image (13).png" alt="" data-size="line">번 아이템의 예외 규정으로 이를 위한 정책 아이템을 설정해야 합니다.&#x20;

**③ 모든 애플리케이션에 대해 안전구역의 읽기/쓰기를 금지하는 정책 아이템**중앙 접근 통제 정책은 안전구역에 대한 별도의 권한이 필요하지 않은 FullAccess Applications 카테고리와 미분류 카테고리의 애플리케이션( <img src="../../.gitbook/assets/image (14).png" alt="" data-size="line">번이나 <img src="../../.gitbook/assets/image (15).png" alt="" data-size="line">번 정책 아이템에 해당되지 않는 애플리케이션)에 대해 안전구역의 모든 권한을 차단합니다. 이를 위한 정책 아이템을 설정합니다.&#x20;

{% hint style="danger" %}
중앙 접근 통제 정책에서는 미분류 카테고리의 애플리케이션은 안전구역으로의 접근이 차단됩니다. 그러므로, 안전구역으로 파일 입출력이 필요한 업무용 애플리케이션이 미분류 카테고리에 있는 경우에는 애플리케이션이 정상적으로 동작할 수 있도록 Business Applications 카테고리로 분류하도록 합니다.
{% endhint %}

#### 로컬저장금지 정책 동작 예

여기서는 다음과 같은 정책 아이템으로 구성된 중앙 접근 통제 정책을 로컬저장금지 정책으로 사용하는 경우, 몇 가지 예를 통해 실제 사용자가 수행하는 작업이 로컬저장금지 정책에 의해 어떻게 처리되는지를 살펴봅니다.

| <img src="../../.gitbook/assets/image (20).png" alt="" data-size="line"> \~ 고정 디스크 접근이 제한된 애플리케이션 구동을 위한 예외 정책 아이템들                |
| ---------------------------------------------------------------------------------------------------------------------------------- |
| <img src="../../.gitbook/assets/image (21).png" alt="" data-size="line"> Export Applications 카테고리에 DOC\_EXPORT 폴더의 첨부를 허용하는 정책 아이템 |
| <img src="../../.gitbook/assets/image (22).png" alt="" data-size="line"> Export Applications 카테고리에 안전구역의 다운로드를 허용하는 정책 아이템         |
| <img src="../../.gitbook/assets/image (23).png" alt="" data-size="line"> Export Applications 카테고리에 전체 디스크에서 첨부/다운로드를 금지하는 정책 아이템   |
| <img src="../../.gitbook/assets/image (25).png" alt="" data-size="line"> 윈도우 탐색기에 안전구역 읽기/쓰기를 허용하는 정책 아이템                          |
| <img src="../../.gitbook/assets/image (26).png" alt="" data-size="line"> Business Applications 카테고리에 안전구역의 읽기/쓰기를 허용하는 정책 아이템      |
| <img src="../../.gitbook/assets/image (27).png" alt="" data-size="line"> <모든 애플리케이션> 카테고리에 안전구역의 읽기/쓰기를 금지하는 정책 아이템                |
| <img src="../../.gitbook/assets/image (28).png" alt="" data-size="line"> Business Applications 카테고리에 비안전구역의 쓰기를 금지하는 정책 아이템        |
| <img src="../../.gitbook/assets/image (29).png" alt="" data-size="line"> <모든 애플리케이션> 카테고리에 모든 권한을 허용하는 정책 아이템                      |



* **예1) 이동식 디스크의 파일을 삭제하는 작업:** <img src="../../.gitbook/assets/image (30).png" alt="" data-size="line">**번 정책 아이템 적용** ![](<../../.gitbook/assets/img_009 (32).png>) **삭제 허용**

> 이 작업은 비안전구역인 사용자 PC의 이동식 디스크에서 윈도우 탐색기가 파일을 삭제하는 작업입니다. 비안전구역에 대한 정책 아이템은 <img src="../../.gitbook/assets/image (31).png" alt="" data-size="line">번 밖에 없지만 이 정책 아이템의 조건(Business Applications 카테고리)과 맞지 않으므로 <img src="../../.gitbook/assets/image (32).png" alt="" data-size="line">번 정책 아이템의 의해 이동식 디스크에서 파일이 삭제됩니다.

{% hint style="warning" icon="circle-1" %}
&#x20;<모든 애플리케이션> 카테고리에 모든 권한을 허용하는 정책 아이템
{% endhint %}

* **예2) 바탕화면에 엑셀 파일을 저장하는 작업:** <img src="../../.gitbook/assets/image (33).png" alt="" data-size="line">**번 정책 아이템 적용** ![](<../../.gitbook/assets/img_010 (28).png>) **저장 차단**

> 이 작업은 비안전구역인 사용자 PC의 바탕화면에 Business Applications 카테고리인 MS Excel 프로그램이 파일을 저장하는(쓰기) 작업입니다. 이 작업에 해당하는 <img src="../../.gitbook/assets/image (36).png" alt="" data-size="line">번 정책 아이템에 의해 파일 저장이 차단됩니다.&#x20;

{% hint style="warning" icon="circle-2" %}
Business Applications 카테고리에 비안전구역의 쓰기를 금지하는 정책 아이템
{% endhint %}

* **예 3) 중앙 문서함에서 설치(exe, msi) 파일을 실행하는 작업:** <img src="../../.gitbook/assets/image (35).png" alt="" data-size="line">**번 정책 아이템 적용** ![](<../../.gitbook/assets/img_011 (21).png>) **실행 차단**

> 이 작업은 **안전구역**인 중앙 문서함에서 **미분류** 카테고리로 분류되는 설치 파일을 실행하는 작업입니다. 이 작업에 해당하는 <img src="../../.gitbook/assets/image (37).png" alt="" data-size="line">번 정책 아이템에 의해 안전구역의 파일 입출력이 금지되므로 설치 파일을 실행했을 때 오류가 발생합니다.

{% hint style="warning" icon="circle-3" %}
**<모든 애플리케이션> 카테고리에 안전구역의 읽기/쓰기를 금지하는 정책 아이템**
{% endhint %}

* **예 4) 중앙 문서함에서 AutoCAD 도면 저장하는 작업:** <img src="../../.gitbook/assets/image (38).png" alt="" data-size="line">**번 정책 아이템 적용** ![](<../../.gitbook/assets/img_012 (19).png>) **저장 허용**

> 이 작업은 **안전구역**인 중앙 문서함에 **Business Applications** 카테고리에 속하는 AutoCAD 프로그램이 파일을 저장하는 작업입니다. 이 작업은 <img src="../../.gitbook/assets/image (40).png" alt="" data-size="line">번 정책 아이템에 의해 중앙 문서함에 AutoCAD 파일이 성공적으로 저장됩니다.

{% hint style="warning" icon="circle-4" %}
**Business Applications 카테고리에 안전구역의 읽기/쓰기를 허용하는 정책 아이템**
{% endhint %}

* **예5) D드라이브의 문서를 Outlook을 통해 첨부하는 작업:** <img src="../../.gitbook/assets/image (41).png" alt="" data-size="line">**번 정책 아이템 적용** ![](<../../.gitbook/assets/img_013 (12).png>)  **첨부 차단**

> 이 작업은 **Export Applications** 카테고리에 속하는 Outlook 프로그램이 **비안전구역**인 사용자 PC의 D 드라이브(고정 디스크)에 저장된 문서를 첨부하는 작업입니다. 이 작업은 <img src="../../.gitbook/assets/image (42).png" alt="" data-size="line">번 정책 아이템에 해당되므로 전체 디스크에 첨부/다운로드를 금지하는 이 정책 아이템에 정상적으로 실행되지 않습니다.&#x20;

{% hint style="warning" icon="circle-6" %}
**Export Applications 카테고리에 전체 디스크에서 첨부/다운로드를 금지하는 정책 아이템**
{% endhint %}

### <mark style="color:$primary;">기본 로컬저장금지 정책</mark>

문서 중앙화 솔루션은 다음과 같은 로컬저장금지 정책을 기본으로 제공합니다.



* **00000.Free :**  모든 작업이 허용되는 보안 해제 정책
* **00001.Central Storage Induction Policy :** **로컬저장금지 정책의 유형**에서 설명된 중앙 저장 유도 정책
* **00002.Central Access Control Policy :** **로컬저장금지 정책의 유형**에서 설명된 중앙 접근 통제 정책에서 반출 관련 정책 아이템이 제외된 정책
* **00003.Central Access Control Policy(DOC\_EXPORT) : 로컬저장금지 정책의 유형**에서 설명된 중앙 접근 통제 정책(반출 관련 정책 지원)
* **00004.ExtDRM :** 외부 DRM 문서를 열람하는 협력사 PC에 적용될 외부 DRM 로컬저장금지 정책

사용자는 이러한 정책을 기본으로 하여 사용자의 업무 환경에 맞게 필요한 정책 아이템을 추가하거나 삭제, 변경할 수 있고 기본 정책 외에도 새로운 로컬저장금지 정책을 만들어 사용할 수도 있습니다.

### <mark style="color:$primary;">로컬저장금지 정책 적용</mark>

로컬저장금지 정책은 하나의 정책을 전사적으로 적용하거나 부서나 사용자별로 별도의 정책을 적용할 수 있습니다. 부서별로 정책을 적용하는 경우에는 상위 부서에 적용된 정책을 하위 부서 혹은 부서의 구성원(사용자)에게 그대로 적용시키거나 하위 부서나 각 구성원에게는 다른 정책이 적용되도록 별도의 정책을 지정할 수도 있습니다.

이와 같이 부서나 사용자별로 다른 정책을 적용할 수 있으므로 회사의 중요한 정보를 다루는 부서나 사용자는 보다 보안이 강화된 정책을 적용하고 외부와의 업무가 많은 부서는 반출 작업을 쉽게 할 수 있는 정책을 적용하는 등 회사의 상황에 맞추어 유연하게 정책을 적용할 수 있습니다.

로컬저장금지 정책을 적용하는 방법은 문서중앙화 솔루션의 모든 보안 기능들(DiskLock, DiskLock Plus, 외부 DRM 반출 정책 등)을 통합된 정책을 통해 관리하는 **모듈 통합정책**의 사용 여부에 따라 달라집니다.

모듈 통합정책을 사용하는 경우에는 각 모듈 통합정책에서 사용할 로컬저장금지 정책을 지정한 후 부서나 사용자에게 적용할 모듈 통합정책을 지정합니다. 모듈 통합정책에 사용될 로컬저장금지 정책은 다음과 같이 문서중앙화 솔루션의 웹 화면에서 **PC 보안 모듈 관리** – **모듈 통합정책 적용** - **정책 관리** 메뉴에서 지정할 수 있습니다.

![](<../../.gitbook/assets/img_014 (11).png>)

그리고, 다음과 같이 웹 화면의 **PC 보안 모듈 관리** – **모듈 통합정책 적용** - **정책 적용** 메뉴를 사용하여 특정 부서나 사용자에게 적용할 모듈 통합정책을 지정할 수 있습니다.&#x20;

![](<../../.gitbook/assets/img_015 (10).png>)

모듈 통합정책을 사용하지 않는 경우에는 **DiskLock 콘솔**을 사용하여 다른 보안 기능과 별도로 사용자나 부서에 적용할 로컬저장금지 정책만 지정할 수 있습니다. 다음은 **DiskLock 콘솔**의 **로컬저장금지 정책**- **정책 적용** 메뉴를 사용하여 **특정 부서의 로컬저장금지 정책을 설정**하는 화면입니다.&#x20;

<figure><img src="../../.gitbook/assets/img_016 (10).png" alt=""><figcaption></figcaption></figure>

다음 동영상에서 로컬저장금지 정책에 대한 자세한 설명을 확인할 수 있습니다.

{% embed url="https://www.youtube.com/watch?feature=youtu.be&si=4DrgfWzZ0_P8D0zS&t=121&v=nMBQ9y9QJu4" %}
