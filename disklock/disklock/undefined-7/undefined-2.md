# 수동으로 표준 정책 라이브러리를 고객사 라이브러리에 반영하기

정책 관리 서버와 고객사의 문서중앙화 서버가 연결되어 있으면, 정책 관리 서버의 표준 정책 라이브러리에 새로 추가된 정책 아이템은 고객사의 정책 라이브러리에 자동으로 반영됩니다. \
하지만, 정책 관리 서버와의 통신 장애로 인해 고객사의 정책 라이브러리가 자동으로 업데이트되지 않는 경우, 관리자는 엠클라우독 담당자로부터 정책 관리 서버의 표준 정책 라이브러리 파일을 ZIP 형식의 압축 파일로 전달받아 직접 업데이트를 수행할 수 있습니다.

또한, 관리자는 자동 업데이트가 수행되기 전에 고객사의 정책 라이브러리를 최신 표준 정책 라이브러리로 즉시 업데이트할 수도 있습니다. 이 기능은 주로 타사에서 설정한 새로운 정책 아이템이 표준 정책 라이브러리에 수동 반영된 직후, 이를 고객사의 정책 라이브러리에도 즉시 적용해야 할 때 유용하게 사용될 수 있습니다.&#x20;

#### <mark style="color:$primary;">고객사 정책 라이브러리 수동 업데이트하기</mark>

엠클라우독 담당자로부터 전달 받은 정책 관리 서버의 표준 정책 라이브러리 파일(ZIP 형식)을 사용하여, 다음과 같은 방법으로 정책 라이브러리를 직접 업데이트할 수 있습니다.

1. 웹에서 **PC 보안 모듈 관리**의 **DiskLock** – **로컬저장금지** – **정책 라이브러리** – **정책 라이브러리 업데이트** 메뉴를 차례로 클릭합니다.&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_000 (130).png" alt=""><figcaption></figcaption></figure></div>

2. ‘**정책 라이브러리 업데이트**’ 화면이 나타납니다. 다음 두 방법 중 하나를 사용하여 업데이트할 정책 라이브러리 파일을 선택합니다.

* <img src="../../../.gitbook/assets/image (207).png" alt="" data-size="line"> **파일 선택**을 클릭한 후 ‘**열기**’ 창이 나타나면  <img src="../../../.gitbook/assets/image (208).png" alt="" data-size="line">전달받은 정책 라이브러리 파일을 선택하고 <img src="../../../.gitbook/assets/image (210).png" alt="" data-size="line">**열기**를 클릭합니다.

<figure><img src="../../../.gitbook/assets/img_001 (122).png" alt=""><figcaption></figcaption></figure>

* 윈도우 탐색기에서 전달받은 정책 라이브러리 파일을 선택한 후 ‘**정책 라이브러리 업데이트**’ 창으로 끌어와 놓습니다.

<figure><img src="../../../.gitbook/assets/img_002 (105).png" alt=""><figcaption></figcaption></figure>

3. 선택한 정책 라이브러리 파일이 **‘정책 라이브러리 업데이트 창**’에 표시됩니다. 화면 하단의 **정책 라이브러리 업데이트**를 클릭합니다. &#x20;

<figure><img src="../../../.gitbook/assets/img_003 (90).png" alt=""><figcaption></figcaption></figure>

4. 정책 라이브러리 파일에 저장되어 있는 정책 아이템들을 가져와 고객사의 정책 라이브러리를 업데이트하는 작업이 수행됩니다. 화면 하단의 창을 통해 업데이트 진행 상황을 확인할 수 있습니다.

<div align="left"><figure><img src="../../../.gitbook/assets/img_004 (70).png" alt=""><figcaption></figcaption></figure></div>

5. 업데이트가 완료되면 이를 알려주는 다음과 같은 팝업 창이 화면 상단에 나타납니다. 지금 바로 업데이트한 정책 라이브러리를 사용하여 로컬저장금지 정책을 설정하려면 **확인**을 클릭하고, 설정 작업을 수행하지 않으려면 **취소**를 클릭합니다.

<div align="left"><figure><img src="../../../.gitbook/assets/img_005 (59).png" alt=""><figcaption></figcaption></figure></div>

{% hint style="warning" icon="square-poll-horizontal" %}
정책 라이브러리 파일에 문제가 있으면 다음과 같은 팝업 창이 나타납니다. 이 경우, 담당자를 통해 심사가 완료된 정책 라이브러리 파일을 다시 전달받은 후 업데이트를 진행하도록 합니다.

![](<../../../.gitbook/assets/img_007 (44).png>)
{% endhint %}

{% hint style="warning" icon="square-poll-horizontal" %}
이미 고객사 정책 라이브러리에 있는 정책 아이템은 추가되지 않습니다. 중복된 정책 아이템이 있는 경우에는 다음과 같은 팝업 창이 나타납니다.

![](<../../../.gitbook/assets/img_009 (35).png>)
{% endhint %}

6. 이전 과정에서 **확인**을 클릭한 경우,다음과 같이‘**정책 적용**’화면으로 이동합니다. [**정책 라이브러리 적용하기**](undefined.md)의 내용을 참고하여 업데이트한 정책 라이브러리를 사용해 로컬저장금지 정책을 설정합니다. &#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_010 (31).png" alt=""><figcaption></figcaption></figure></div>

#### <mark style="color:$primary;">최신 정책 라이브러리로 즉시 업데이트하기</mark>

정책 관리 서버에서 최신 정책 아이템 정보를 가져와 고객사의 정책 라이브러리를 즉시 업데이트하는 방법은 다음과 같습니다.

1. 웹에서 **윈도우 보안 모듈 관리** – **DiskLock** – **로컬저장금지** – **정책 라이브러리** – **정책 아이템 업데이트** 메뉴를 차례로 클릭합니다.&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_011 (24).png" alt=""><figcaption></figcaption></figure></div>

2. ‘**정책 아이템 업데이트**’ 화면이 나타나면 **정책 아이템 업데이트**를 클릭합니다.

<figure><img src="../../../.gitbook/assets/img_012 (22).png" alt=""><figcaption></figcaption></figure>

3. 정책 관리 서버로부터 최신 정책 아이템에 대한 정보를 가져와 정책 라이브러리를 업데이트하는 작업이 진행됩니다. 업데이트가 성공적으로 완료되고 나면 다음과 같은 팝업 창을 볼 수 있습니다.

<div align="left"><figure><img src="../../../.gitbook/assets/img_013 (15).png" alt=""><figcaption></figcaption></figure></div>
