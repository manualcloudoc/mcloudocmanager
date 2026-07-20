# 관리자 빠른 시작 가이드 - 부서문서함 구성하기

관리자는 다음 단계에 따라 부서문서함을 생성하고 부서문서함 내 폴더를 구성해야 합니다.

1. **부서문서함 생성**: 회사 전체에서 사용할 전사 부서문서함을 생성합니다.
2. **부서별 폴더 생성**: 전사 부서문서함 내에 부서별로 폴더를 생성합니다. 부서별 폴더는 아래 그림과 같이 **조직도와 동일한 다단계 구조로 구성**하거나, **팀 단위 등으로 단순화하여 1뎁스로 구성**할 수 있습니다.            &#x20;

<div align="left"><figure><img src="../../.gitbook/assets/img_000 (163).png" alt="" width="563"><figcaption></figcaption></figure></div>

3. **폴더별 권한 설정**: 부서별 폴더에는 해당 부서 직원만 접근할 수 있도록 권한을 설정해야 합니다. 본 가이드에서는 팀 단위로 1뎁스 폴더를 생성할 경우와 다단계 부서 구조 그대로 폴더를 생성할 경우를 구분하여 권한 설정 방법을 설명합니다.

{% hint style="warning" icon="square-poll-horizontal" %}
전사 부서문서함의 폴더 구성 방식 선택 시 다음을 참고합니다.

* **조직도와 동일한 다단계 구성**: 회사의 조직도와 동일하게 폴더를 계층적으로 구성하는 방식입니다. 이 구조는 조직 체계를 그대로 반영할 수 있으며, 상위/하위 부서별로 문서 접근 권한을 세분화함으로써 보안성을 강화할 수 있습니다.
* **팀 단위 1뎁스 구성**: 조직도의 최하위 레벨인 각 팀을 1뎁스 폴더로 구성하는 방식입니다. 구조가 단순해 구축 및 관리가 용이하며, 소규모 조직에 특히 적합합니다. 또한 조직 개편 등 변화에도 빠르게 대응할 수 있다는 장점이 있습니다.
{% endhint %}

### <mark style="color:$primary;">부서문서함 생성하기</mark>

전사 부서문서함을 생성하는 방법은 다음과 같습니다.

1. 관리자 웹페이지의 **인사 조직 관리 – 조직도 – 조직도 관리** 메뉴를 선택한 후 **조직도 편집기**를 실행합니다.
2. 조직도 편집기 좌측의 부서/그룹 창에서 문서함을 생성할 부서를 선택합니다. 전사 부서문서함을 생성하기 위해서는 사이트명(아래 그림의 예에서는 **MY COMPANY**)을 선택해야 합니다. &#x20;

<figure><img src="../../.gitbook/assets/img_002 (130).png" alt=""><figcaption></figcaption></figure>

3. 상단 툴바에서 **부서문서함 생성**을 클릭합니다.
4. ‘부서문서함 생성’ 창에서 부서문서함의 용량과 이름을 설정한 후 **생성** 버튼을 클릭합니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_003 (113).png" alt="" width="497"><figcaption></figcaption></figure></div>

5. 부서문서함이 생성되면 사용자가 윈도우 탐색기에서 부서문서함 드라이브를 확인할 수 있습니다.&#x20;

<figure><img src="../../.gitbook/assets/img_004 (88).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" icon="square-poll-horizontal" %}
**DOC\_EXPORT**와 **RECYCLER** 폴더는 부서문서함 생성 시에 자동 생성되는 특수 폴더입니다.
{% endhint %}

### <mark style="color:$primary;">부서별 폴더 생성하기</mark>

부서문서함 폴더를 최초로 생성하기 위해서는 반드시 **서비스관리자** 계정으로 웹페이지에 로그인해야 합니다.

1. 웹페이지 우측 상단에서 계정 이름 우측의 ![](<../../.gitbook/assets/img_006 (63).png>) 버튼을 클릭한 후 **Agent 실행**을 선택하여 윈도우 에이전트를 실행합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_007 (53).png" alt=""><figcaption></figcaption></figure>

* PC에 윈도우 에이전트가 설치되어 있지 않은 경우에는 설치 안내 메시지에서 **확인** 버튼을 클릭하여 설치를 진행합니다.
* 설치를 완료한 후에 다시 **Agent 실행** 메뉴를 선택하여 윈도우 에이전트를 실행합니다.



2. 윈도우 탐색기에서 부서문서함 드라이브를 클릭한 후, 탐색기 메뉴에서 **새로 만들기 - 폴더**를 사용하여 폴더를 생성합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_008 (48).png" alt=""><figcaption></figcaption></figure>

3. 문서함의 하위에 생성한 폴더들이 표시됩니다. 다음은 위의 조직도와 동일하게 폴더를 생성한 경우의 예입니다.

<figure><img src="../../.gitbook/assets/img_009 (40).png" alt=""><figcaption></figcaption></figure>

### <mark style="color:$primary;">폴더별 권한 설정하기</mark>

#### 1뎁스 구성에서 폴더 권한 설정하기

다음 그림과 같이 팀 단위 폴더를 생성한 경우, 아래 표의 예시와 같이 폴더 권한을 설정해야 합니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_010 (36).png" alt=""><figcaption></figcaption></figure></div>



<figure><img src="../../.gitbook/assets/img_011 (29).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (101).png" alt="" data-size="line"> 전사문서함의 루트 폴더에 대해서는 기본적으로 전 직원에게 목록보기 권한이 허용됩니다.

<img src="../../.gitbook/assets/image (102).png" alt="" data-size="line"> **1.국내영업팀** 등 모든 부서별 폴더에 대해서는 권한을 새로 설정해야 합니다.

* 폴더를 생성하면 기본적으로 상위 폴더의 권한이 상속됩니다. 따라서, **1.국내영업팀** 폴더를 생성하면 기본적으로 루트 폴더의 권한이 상속 적용되어, 전 직원에게 목록보기 권한이 허용됩니다.
* 하지만, **1.국내영업팀** 폴더에 대해서는 국내영업팀에게만 목록보기, 읽기, 쓰기, 삭제 권한이 허용되어야 하므로, 상위 폴더의 권한을 상속받지 않도록 권한을 새로 설정해야 합니다.

 폴더 권한을 새로 설정하는 방법은 다음과 같습니다.

1.  윈도우 탐색기에서 권한을 설정할 폴더를 선택한 후 마우스 우클릭하여 **폴더 관리 - 권한 설정**을 선택합니다.        

    <figure><img src="../../.gitbook/assets/img_014 (16).png" alt=""><figcaption></figcaption></figure>
2.  &#x20;‘<폴더> 속성’ 창에서 **“이 폴더에 권한을 추가하여 설정**” 항목을 체크한 후, **추가** 버튼을 클릭합니다.\
    &#x20;     &#x20;

    <div align="left"><figure><img src="../../.gitbook/assets/img_015 (15).png" alt="" width="354"><figcaption></figcaption></figure></div>
3.  ‘부서(그룹) 및 사용자 선택’ 창의 좌측 **전체 목록**에서 권한을 부여할 부서를 선택한 후, 추가 버튼을 클릭합니다. 이어서, 우측 **현재 선택된 목록**에서 추가된 부서를 확인한 후, 하단의 **확인** 버튼을 클릭합니다. \
    &#x20;         &#x20;

    <div align="left"><figure><img src="../../.gitbook/assets/img_016 (15).png" alt="" width="563"><figcaption></figcaption></figure></div>

{% hint style="success" icon="lightbulb-exclamation-on" %}
조직도 트리에서 찾기가 어려울 경우, 검색 버튼을 클릭하여 부서/사용자를 검색할 수도 있습니다. 
{% endhint %}

4. ‘<폴더> 속성’ 창에서 **권한 설정 대상 목록**에 추가된 부서를 확인한 후, 하단의 **사용 권한** 영역에서 권한을 선택합니다. 이 예에서는 **허용** 항목의 **모든 권한**을 체크하여 목록보기/읽기/쓰기/삭제 등 모든 권한이 허용되도록 합니다. 또한, 하단의 “**(부모 폴더의) 권한을 계승함**”을 체크 해제하여 상위 폴더의 권한을 상속받지 않도록 합니다. 모든 설정을 완료한 후에 **확인**을 클릭합니다.&#x20;

<div align="left"><figure><img src="../../.gitbook/assets/img_018 (9).png" alt="" width="354"><figcaption></figcaption></figure></div>

5. 하위 부서 적용을 확인하는 창에서 **예**를 클릭하면 폴더 권한 적용이 완료됩니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_019 (10).png" alt="" width="528"><figcaption></figcaption></figure></div>

6. 해당 폴더에서 마우스 우클릭 후 **폴더 관리 – 폴더 권한 설정 현황**을 선택하면, 설정된 폴더 권한을 확인할 수 있습니다. 아래 그림의 예에서는 **1.국내영업팀** 폴더에 대해 읽기, 쓰기, 삭제, 목록 보기, 폴더 생성 등의 권한이 국내영업팀에게 허용된 것을 볼 수 있습니다.       &#x20;

<figure><img src="../../.gitbook/assets/img_020 (7).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" icon="square-poll-horizontal" %}
폴더 권한은 목록보기, 읽기, 쓰기, 삭제 등의 권한을 특정 부서 또는 사용자에게 부여하는 방식으로 설정됩니다. 폴더 권한에 대한 설명은 [**폴더 권한 소개**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/centralfile/undefined-4)를 참고합니다.
{% endhint %}

{% hint style="warning" icon="square-poll-horizontal" %}
생성한 폴더에서 **폴더관리자**를 지정하면, 이후 폴더관리자가 서비스관리자를 대신하여 하위 폴더를 생성하고 권한을 설정하는 등 해당 폴더의 관리 업무를 수행할 수도 있습니다. 자세한 내용은 [**폴더관리자 설정하기**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/undefined-3/undefined-1)를 참고합니다. 
{% endhint %}

#### 다단계 구성에서 폴더 권한 설정하기

조직도와 동일하게 부서별 폴더를 단계별로 생성할 경우에는, 폴더 권한을 더 정밀하게 설계하여 설정할 수 있습니다. 이 목차에서는 다음 그림과 같이 영업본부 폴더 하위에 영업팀별 폴더와 영업팀 공용 폴더를 추가하고, 각 폴더에 추가로 하위 폴더를 생성할 경우를 예로 들어 권한 설정 방법을 설명합니다.&#x20;

<div align="left"><figure><img src="../../.gitbook/assets/img_023 (8).png" alt="" width="238"><figcaption></figcaption></figure></div>



다음 표는 **1.영업본부** 폴더 이하 각 폴더에 대해 필요한 권한의 예를 들고, 권한을 부여하는 방법을 정리한 것입니다.

![](<../../.gitbook/assets/img_024 (9).png>)

1. **1.영업본부** 폴더 등 표에서 <img src="../../.gitbook/assets/image (104).png" alt="" data-size="line"> 표시가 된 폴더에서는 권한을 새로 설정해야 합니다.

* 폴더를 생성하면 기본적으로 상위 폴더의 권한이 상속됩니다. 따라서, **1.영업본부** 폴더를 생성하면 기본적으로 루트 폴더의 권한이 상속 적용되어, 전 직원에게 목록보기 권한이 허용됩니다.
* 하지만, **1.영업본부** 폴더에 대해서는 영업본부에게만 목록보기, 읽기 권한이 허용되어야 하므로, 상위 폴더의 권한을 상속받지 않도록 권한을 새로 설정해야 합니다.
* 폴더에 권한을 설정하는 방법은 [**1뎁스 구성에서 폴더 권한 설정하기**](undefined-2.md#id-1) 목차의 설명을 참고합니다.



2. **1.견적사 자료** 등 표에서 회색 음영으로 표시된 폴더에서는 권한을 별도로 설정할 필요가 없으며, 상위 폴더에서 상속된 권한이 그대로 적용됩니다.

* **1.견적사 자료** 폴더의 경우, 상위 폴더인 **1.국내영업팀** 폴더와 동일하게 국내영업팀 팀원에게 목록 보기, 읽기, 쓰기, 삭제 권한이 허용되어야 합니다. 상위 폴더와 필요한 권한이 동일하므로, 권한을 별도로 설정할 필요가 없습니다.
* 폴더에서 권한을 별도로 설정하지 않은 경우에는, 상위 폴더의 권한을 변경 설정한 경우에도 변경된 권한이 자동으로 상속됩니다. 예를 들어, **1.국내영업팀** 폴더의 권한을 표와 같이 설정한 후, 하위 폴더인 **1.견적서 자료**의 폴더 권한 설정 현황을 확인하면, 다음과 같이 **상속 권한**으로 국내영업팀에게 목록보기, 읽기, 쓰기, 삭제 등의 권한이 허용된 것을 확인할 수 있습니다.

<figure><img src="../../.gitbook/assets/img_028 (3).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" icon="square-poll-horizontal" %}
폴더에서 마우스 우클릭 후 **폴더 관리 – 폴더 권한 설정 현황**을 선택하면 폴더 권한 설정 현황을 확인할 수 있습니다. 상속 권한을 확인하기 위해서는 **권한 구분** 항목에서 상속 권한을 체크해야 합니다.
{% endhint %}
