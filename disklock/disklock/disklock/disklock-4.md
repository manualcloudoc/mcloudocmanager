# DiskLock 콘솔에서 정책 서포트 기능 사용하기

사용자에게 적용된 로컬저장금지 정책으로 인해, 사용자 PC에서 구동되는 애플리케이션에 따라 특정 디스크에서의 파일 입출력이 제한될 수 있습니다. 대부분의 애플리케이션은 고정디스크의 특정 영역에 대해 파일 입출력이 가능해야 프로그램이 정상적으로 구동될 수 있으므로, 문서중앙화 솔루션에서 제공되는 로컬저장금지 정책에는 필수적인 애플리케이션에 대해 고정디스크의 특정 경로에 대한 입출력 권한을 허용하는 **예외 정책 아이템**들이 포함되어 있습니다.

그럼에도, 사용자가 사용하게 될 애플리케이션 및 시스템 환경을 모두 예측할 수 없으므로 사용자에게 꼭 필요한 작업이 제한되는 경우가 발생할 수 있습니다. 이 경우, 관리자는 사용자에게 적용된 로컬저장금지 정책에 예외 정책 아이템을 추가하여 문제를 해결할 수 있습니다.

**정책 서포트** 기능은 사용자의 윈도우 PC에서 파일 입출력 거부로 인해 애플리케이션을 정상적으로 수행할 수 없는 경우, 파일 입출력 거부 로그를 통해 차단된 작업을 식별할 수 있도록 하고, 문제 해결을 위해 추가되어야 할 예외 정책 아이템을 제안하여 간편하게 정책에 추가할 수 있도록 지원하는 기능입니다.

{% hint style="info" %}
로컬저장금지 정책과 정책 아이템에 대한 설명은 [**로컬저장금지 정책 소개**](../undefined-2.md)를 참고합니다.
{% endhint %}

#### <mark style="color:$primary;">정책 서포트 기능 시작하기</mark>

정책 서포트 기능은 다음과 같이 구동할 수 있습니다.

1. DiskLock 콘솔의 **로컬저장금지 정책 – 정책 관리**를 클릭합니다.
2. 좌측 정책 목록에서 현재 사용자 PC에서 사용 중인 로컬저장금지 정책을 선택합니다. 사용 중인 정책은 정책명 앞의 ![](<../../../.gitbook/assets/img_001 (112).png>)표시로 식별할 수 있습니다.&#x20;

<figure><img src="../../../.gitbook/assets/img_002 (96).png" alt=""><figcaption></figcaption></figure>

3. 우측 상단 정책 아이템 메뉴의 **정책 서포트**를 클릭합니다. 현재 사용 중인 정책을 선택한 경우에만 정책 서포트 메뉴가 활성화됩니다.&#x20;

<figure><img src="../../../.gitbook/assets/img_003 (81).png" alt=""><figcaption></figcaption></figure>

4. ‘**정책 서포트**’ 창이 팝업됩니다. 이제 정책 서포트를 위한 모니터링을 시작할 수 있습니다.

<div align="left"><figure><img src="../../../.gitbook/assets/img_004 (62).png" alt=""><figcaption></figcaption></figure></div>

#### <mark style="color:$primary;">정책 서포트 화면 소개</mark>

‘**정책 서포트**’ 창은 다음과 같은 영역으로 구성됩니다.&#x20;

![](<../../../.gitbook/assets/img_005 (52).png>)

<img src="../../../.gitbook/assets/image (52).png" alt="" data-size="line"> **메뉴 버튼**

정책 서포트 기능의 사용 단계에 따라 사용할 수 있는 메뉴는 다음과 같습니다.

<table><thead><tr><th width="149.6363525390625">메뉴명</th><th>기능 설명</th></tr></thead><tbody><tr><td><strong>모니터링 시작/중지</strong></td><td>파일 입출력 거부 로그 모니터링을 시작 또는 중지할 수 있습니다. <strong>모니터링 중지</strong> 상태에서는 <strong>모니터링 시작</strong> 버튼이 표시되며, 모니터링 시작 후에는 <strong>모니터링 중지</strong> 버튼으로 변경됩니다.</td></tr><tr><td><strong>모든 로그 지우기</strong></td><td>현재까지 화면에 표시된 로그를 지울 수 있습니다. 모니터링을 새로 시작할 경우에는 화면에 표시된 로그가 자동으로 삭제됩니다.</td></tr><tr><td><strong>새로고침</strong></td><td>로그를 수동으로 <strong>새로고침</strong>하여 발생된 로그를 즉시 확인할 수 있습니다.</td></tr><tr><td><strong>선택 로그 정책 아이템 추가</strong></td><td>파일 입출력 거부 로그 목록에서 특정 로그를 선택할 경우 활성화되는 버튼으로, 클릭 시 ‘<strong>정책 아이템 추가</strong>’ 창이 팝업됩니다. 이때, 정책 아이템의 각 항목은 정책 서포트 기능에서 제안하는 <strong>예외 정책 아이템</strong>(선택된 로그에 적용된 <strong>차단 정책 아이템</strong>에 대한 예외)의 내용으로 자동 설정됩니다.</td></tr><tr><td><strong>적용</strong></td><td><strong>추가할 정책 아이템</strong> 영역에 정책 아이템이 추가된 경우에 활성화되는 버튼입니다. 클릭 시 해당 정책 아이템이 현재 사용중인 로컬저장금지 정책에 자동으로 추가됩니다.</td></tr><tr><td><strong>닫기</strong></td><td>‘<strong>정책 서포트</strong>’ 창을 닫습니다.</td></tr></tbody></table>

<img src="../../../.gitbook/assets/image (53).png" alt="" data-size="line"> **모니터링 상태**

이 영역에는 로그의 모니터링 상태가 표시됩니다. 표시되는 상태값은 다음과 같습니다.

<table><thead><tr><th width="205.0909423828125">상태값</th><th>내용</th></tr></thead><tbody><tr><td><strong>모니터링 중지</strong></td><td>모니터링 시작 전의 초기 상태, 또는 모니터링 중지 버튼을 클릭하여 모니터링을 중지한 상태입니다.</td></tr><tr><td><strong>처음 로그 생성 확인 중</strong></td><td>모니터링 시작 버튼을 클릭한 후 파일 입출력 거부 로그가 생성되기 이전 상태입니다.</td></tr><tr><td><p><strong>로그 모니터링 동작 중</strong> </p><p><strong>(n초 후 새로고침)</strong></p></td><td>차단된 작업이 발생하여 파일 입출력 거부 로그가 모니터링 되는 상태입니다. 생성되는 로그가 주기적으로 화면에 추가되며 다음 번 자동 새로고침까지 남은 시간이 표시됩니다.</td></tr></tbody></table>

<img src="../../../.gitbook/assets/image (54).png" alt="" data-size="line"> **프로세스 목록**

파일 입출력 작업이 차단된 프로세스가 표시되는 영역으로, 프로세스명과 PID(프로세스 ID)가 표시됩니다. 프로세스명 앞의 체크박스 체크 시 해당 프로세스에서 생성된 파일 입출력 거부 로그를 확인할 수 있습니다. 기본 상태는 모두 체크된 상태입니다.

애플리케이션 카테고리가 미분류 상태인 프로세스일 경우에는 다음과 같이 미분류 표시가 추가됩니다.

<div align="left"><img src="../../../.gitbook/assets/img_006 (44).png" alt="" width="215"></div>

<img src="../../../.gitbook/assets/image (55).png" alt="" data-size="line"> **수집된 파일 입출력 거부 로그**

파일 입출력 거부 로그가 표시되는 영역입니다. 모니터링 시작 후 생성된 파일 입출력 작업 거부 로그가 주기적으로 화면에 추가됩니다. 각각의 로그에 표시되는 항목은 다음과 같습니다.

<table><thead><tr><th width="142.3636474609375">항목</th><th>내용</th></tr></thead><tbody><tr><td><strong>프로세스</strong></td><td>파일 입출력 작업을 수행한 프로세스명이 표시됩니다.</td></tr><tr><td><strong>경로</strong></td><td>작업 대상 파일의 전체 경로가 표시됩니다.</td></tr><tr><td><strong>파일</strong></td><td>작업 대상 파일의 파일명이 표시됩니다.</td></tr><tr><td><strong>차단된 작업</strong></td><td>차단(거부)된 작업의 종류가 <strong>r</strong>(읽기), <strong>w</strong>(쓰기), <strong>d</strong>(삭제), <strong>l</strong>(목록보기)로 표시됩니다.</td></tr></tbody></table>

표시된 로그 중에서 특정 로그를 선택하여 마우스 우클릭하면 다음과 같은 컨텍스트 메뉴를 사용할 수 있습니다. 단, 로그의 선택은 **모니터링 중지** 상태에서만 가능합니다.

![](<../../../.gitbook/assets/img_007 (37).png>)

•    **차단된 정책 아이템 보기**\
로그 컨텍스트 메뉴에서 **차단된 정책 아이템 보기** 선택 시 다음과 같이 파일 입출력 거부의 원인이 되는 로컬저장금지 정책 아이템을 확인할 수 있습니다.

<div align="left"><figure><img src="../../../.gitbook/assets/img_008 (34).png" alt="" width="427"><figcaption></figcaption></figure></div>

•    **프로세스 관련 정책 아이템 보기**\
로그 컨텍스트 메뉴에서 **프로세스 관련 정책 아이템 보기** 선택 시 다음과 같이 해당 프로세스에 적용 가능한 모든 정책 아이템을 확인할 수 있습니다.

<figure><img src="../../../.gitbook/assets/img_009 (30).png" alt=""><figcaption></figcaption></figure>

하단의 **부모 카테고리 정책 아이템 표시**를 체크하면, 해당 프로세스가 속한 애플리케이션 카테고리(예: whale) 뿐만 아니라 부모 카테고리(예: Export Applications, <모든 애플리케이션>)에 적용되는 정책 아이템도 함께 표시됩니다. 이때 부모 카테고리에 대한 정책 아이템일 경우 배경색이 노란색으로 구분됩니다.&#x20;



<img src="../../../.gitbook/assets/image (56).png" alt="" data-size="line"> **추가할 정책 아이템**

**선택 로그 정책 아이템 추가** 버튼을 클릭하여 정책 아이템을 추가하면, 새로 생성된 정책 아이템의 내용이 이 영역이 표시됩니다. 하단의 **적용** 버튼 클릭 시, 해당 정책 아이템이 현재 사용 중인 로컬저장금지 정책에 추가되고, 이 영역에서는 사라집니다.

<img src="../../../.gitbook/assets/image (57).png" alt="" data-size="line"> **선택 로그 관련 카테고리 경로**

**수집된 파일 입출력 거부 로그** 목록에서 특정 로그 선택 시, 해당 로그와 관련된 프로세스의 애플리케이션 카테고리 경로가 표시됩니다.

#### <mark style="color:$primary;">정책 서포트 기능의 단계별 사용 방법</mark>

정책 서포트 기능을 사용하는 절차는 다음과 같습니다.

<img src="../../../.gitbook/assets/image (58).png" alt="" data-size="line">모니터링 시작

<img src="../../../.gitbook/assets/image (59).png" alt="" data-size="line">파일 입출력 거부 로그 생성 (오류가 발생하는 작업을 수행)

<img src="../../../.gitbook/assets/image (60).png" alt="" data-size="line">오류의 원인이 되는 로그 식별

<img src="../../../.gitbook/assets/image (61).png" alt="" data-size="line">문제 해결을 위한 예외 정책 아이템 생성

<img src="../../../.gitbook/assets/image (62).png" alt="" data-size="line">생성된 정책 아이템을 로컬저장금지 정책에 추가

<img src="../../../.gitbook/assets/image (63).png" alt="" data-size="line">오류 해결 확인

각 단계별 사용 방법은 웨일 브라우저에서 중앙문서함으로 파일 다운로드 시 발생하는 오류를 해결하는 예를 들어 설명합니다.

***

**①  모니터링 시작**

1\.   ‘**정책 서포트**’ 창에서 **모니터링 시작** 버튼을 클릭합니다.&#x20;

<figure><img src="../../../.gitbook/assets/img_010 (26).png" alt=""><figcaption></figcaption></figure>

&#x20;2\.   모니터링이 시작되면 모니터링 중지 버튼이 활성화되고, 모니터링 상태가 ‘처음 로그 생성 확인 중’으로 변경됩니다.&#x20;

<figure><img src="../../../.gitbook/assets/img_011 (19).png" alt=""><figcaption></figcaption></figure>



**②   파일 입출력 거부 로그 생성**

1\.   파일 입출력 거부 로그 생성을 위해 오류가 발생했던 작업을 다시 수행합니다. 아래 예시 화면은 웨일 브라우저에서 메일의 첨부 파일을 중앙문서함으로 다운로드 시 실패하는 사례를 재현한 것입니다.

<figure><img src="../../../.gitbook/assets/img_012 (17).png" alt=""><figcaption></figcaption></figure>

2\.   ‘**정책 서포트**’ 창에서 **수집된 파일 입출력 거부 로그** 영역에 로그가 표시되는 것을 확인한 후, 다음 단계 수행을 위해 **모니터링 중지** 버튼을 클릭하여 모니터링을 중지합니다.<br>

<figure><img src="../../../.gitbook/assets/img_013 (10).png" alt=""><figcaption></figcaption></figure>



**③  오류의 원인이 되는 로그 식별**

수집된 파일 입출력 거부 로그를 검토하여 오류의 원인으로 추정되는 로그를 식별합니다. 필요 시 컨텍스트 메뉴의 **차단/적용된 정책 아이템 보기**를통해 관련 정책 아이템을 확인합니다.

<figure><img src="../../../.gitbook/assets/img_014 (9).png" alt=""><figcaption></figcaption></figure>



**④   문제 해결을 위한 예외 정책 아이템 생성**

1. 해결이 필요한 로그(본 예시에서는 Windows Defender dll 파일의 입출력 차단)를 선택한 후, 하단의 **선택 로그 정책 아이템 추가** 버튼을 클릭합니다.

<figure><img src="../../../.gitbook/assets/img_015 (8).png" alt=""><figcaption></figcaption></figure>

2\. 해당 프로세스가 소속된 애플리케이션 카테고리가 두 개 이상인 경우 다음과 같이 애플리케이션 카테고리 선택 창이 팝업됩니다. 이 경우, 생성할 예외 정책 아이템에 적합한 카테고리를 선택한 후 **확인**을 클릭합니다. 프로세스가 소속된 애플리케이션 카테고리가 한 개인 경우에는 이 단계 없이 곧바로 ‘**정책 아이템 추가**’ 창이 표시됩니다.&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_016 (8).png" alt="" width="285"><figcaption></figcaption></figure></div>

3. ‘**정책 아이템 추가**’ 창에 정책서포트 기능이 제안하는 정책 아이템 내용이 자동으로 생성되어 표시됩니다.&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_017 (5).png" alt="" width="357"><figcaption></figcaption></figure></div>

4. 수정이 필요한 항목을 적절히 수정한 후, **확인**을 클릭합니다.

<div align="left"><figure><img src="../../../.gitbook/assets/img_018 (5).png" alt="" width="358"><figcaption></figcaption></figure></div>

{% hint style="warning" icon="square-poll-horizontal" %}
정책 아이템의 항목별 설명 및 설정 방법은 [**DiskLock 콘솔에서 로컬저장금지 정책 아이템 설정하기**](disklock-1.md) 를 참고합니다.
{% endhint %}

5. 새로 생성된 정책 아이템의 내용이 **추가한 정책 아이템** 영역이 표시됩니다.

<figure><img src="../../../.gitbook/assets/img_020 (3).png" alt=""><figcaption></figcaption></figure>



**⑤ 생성된 정책 아이템을 로컬저장금지 정책에 추가**

1. 위 화면에서 **추가한 정책 아이템**을 확인 후 하단의 **적용** 버튼을 클릭하면 해당 정책 아이템이 현재 사용 중인 로컬저장금지 정책에 추가됩니다. 다음과 같이 로컬저장금지 정책 관리 페이지에서 정책 아이템이 추가된 것을 확인할 수 있습니다.

<figure><img src="../../../.gitbook/assets/img_021 (3).png" alt=""><figcaption></figcaption></figure>

&#x20;2\.   좌측 메뉴 하단의 **내 PC에 정책 새로고침**을 클릭하여 정책 변경 사항을 PC에 곧바로 적용합니다.&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_022 (3).png" alt="" width="138"><figcaption></figcaption></figure></div>

{% hint style="warning" icon="square-poll-horizontal" %}
**내 PC에 정책 새로고침**을 사용하지 않을 경우, 일정 시간 후에 자동으로 PC 정책이 업데이트됩니다.
{% endhint %}



**⑥ 오류 해결 확인**

오류가 발생했던 작업을 다시 수행하여 오류 해결 여부를 확인합니다. 본 예시에서는 웨일 브라우저에서 메일 첨부 파일 다운로드 시 파일이 성공적으로 다운로드되는 것을 확인할 수 있습니다. <br>

<figure><img src="../../../.gitbook/assets/img_024 (5).png" alt=""><figcaption></figcaption></figure>
