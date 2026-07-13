# 문서함 내 파일의 경로

스토리지를 마운트하고, 문서함을 수용할 파티션이 준비되었으면, 좀 더 세부적인 폴더 경로에 대해 살펴보겠습니다. 싱글도메인과 멀티도메인 환경에서 개인문서함과 부서문서함 내  파일이 저장되는 경로입니다.

### <mark style="color:$primary;">싱글도메인의 파일 경로</mark>

#### 개인문서함 폴더의 예

개인문서함용 파티션은 관리자 페이지에서 파티션 정보를 등록하기만 해도 일부 폴더(예: **/plusdrive/home/00000/data/**)가 생성됩니다. 사용자를 등록할 때에도 해당 사용자를 위한 폴더(예. **홍길동(gdhong)**)가 자동으로 생성됩니다.

![](<../../.gitbook/assets/img_000 (227).png>)

<img src="../../.gitbook/assets/image (118).png" alt="" data-size="line"> **파티션**: 여기서 **home**은 개인문서함용 파티션입니다. 여러 개의 파티션을 사용하고자 하면 **home2, home3, …** 등과 같이 추가할 수 있습니다. 이 때 폴더 구조는 다음과 같습니다.

<div align="left"><img src="../../.gitbook/assets/img_002 (150).png" alt=""></div>

<img src="../../.gitbook/assets/image (119).png" alt="" data-size="line"> **문서함 아이디**: 개인문서함의 아이디는 **00000**으로 시작되고 파티션 등록시 **00000/data** 폴더가 자동으로 추가됩니다.개인문서함 또는 **전사용 부서문서함**(팀용 부서문서함 아님)이 추가될 때마다최종 문서함 아이디에서 1씩 증가합니다.  만약 최종 문서함 아이디가 00001 이었다면 새로 추가하는 개인문서함은 00002의 아이디를 갖게 됩니다.

<figure><img src="../../.gitbook/assets/img_004 (102).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" icon="lightbulb-exclamation-on" %}
**하나의 개인문서함용 파티션**에는**하나의 개인문서함용 아이디** 폴더를 수용할 수 있습니다.

예)  /plusdrive/home/00000      ->  개인문서함 아이디

&#x20;      /plusdrive/home2/00001    ->  개인문서함 아이디

&#x20;      /plusdrive/home3/00002    ->  개인문서함 아이디
{% endhint %}

<img src="../../.gitbook/assets/image (120).png" alt="" data-size="line"> **사용자 이름(아이디)**:  사용자를 등록하면 **홍길동(gdhong)**&#xACFC; 같이 폴더가 생성됩니다.

#### 부서문서함 폴더의 예

부서문서함의 경우 관리자 페이지에서 파티션 정보만 등록해서는 생성되는 폴더가 없지만, 전사 또는 팀의 부서문서함을 생성하면 관련 폴더(예. **00001/data/**)가 자동으로 파티션에 생성됩니다.

<figure><img src="../../.gitbook/assets/img_007 (63).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (121).png" alt="" data-size="line"> **파티션**:  여기서 **orgcowork**은 부서문서함용 파티션입니다. 여러 개의 파티션을 사용하고자 하면 **orgcowork2, orgcowork3, …** 등과 같이 추가할 수 있습니다. 이 때 폴더 구조는 다음과 같습니다.![](<../../.gitbook/assets/img_009 (48).png>)

<img src="../../.gitbook/assets/image (122).png" alt="" data-size="line">**문서함 아이디**: 문서함 아이디는 **전사용**과 **팀용**의 운영방법이 다릅니다.&#x20;

* **전사용 부서문서함**은 개인용문서함과 중복되지 않도록 00000부터 시작해서 1씩 증가하는 아이디로 관리합니다.

![](<../../.gitbook/assets/img_011 (34).png>)

* **팀용 부서문서함은** 부서코드와 일련번호로 아이디가 구성됩니다. 동일 팀에 여러 부서 문서함이 있는 경우 일련번호는 0 부터 시작해서 1씩 증가합니다. 문서함 아이디는 팀용 **부서코드(기본20자리, 고객사에 따라 변경 가능)+일련번호4자리**로 생성됩니다.

![](<../../.gitbook/assets/img_012 (31).png>)

{% hint style="success" icon="lightbulb-exclamation-on" %}
**하나의 부서문서함용 파티션**에는 **여러개의 부서문서함용 아이디** 폴더를 수용할 수 있습니다.

예)  /plusdrive/orgcowork/00001                            ->  전사용부서문서함 아이디&#x20;

&#x20;     /plusdrive/orgcowork/00002                            ->  전사용부서문서함 아이디

&#x20;     /plusdrive/orgcowork/100000116587377052410000   ->  팀용부서문서함 아이디       &#x20;

&#x20;     /plusdrive/orgcowork/100000116587377052410001   ->  팀용부서문서함 아이디

&#x20;      /plusdrive/orgcowork/100000316587380499430002   ->  팀용부서문서함 아이디
{% endhint %}

<img src="../../.gitbook/assets/image (123).png" alt="" data-size="line"> **부서폴더**: 사용자가 직접 수동으로 만든 폴더의 예입니다. 부서문서함의 윈도우탐색기에서 확인할 수 있습니다.

### <mark style="color:$primary;">멀티도메인의 파일 경로</mark>

싱글도메인에서는 개인문서함과 부서문서함용 파티션을 수동으로 생성하고 등록해야 했습니다. 하지만, 멀티도메인에서는 도메인용 파티션만 수동으로 생성하고 등록하고 나면, 개인문서함과 부서문서함용 폴더가 자동으로 생성됩니다.

#### 개인문서함 폴더의 예

<figure><img src="../../.gitbook/assets/img_015 (19).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (124).png" alt="" data-size="line"> **파티션**: domain은 도메인용 파티션 이름입니다. 동일 서버내에 N개의 파티션을 사용한다면 다음과 같이 이름을 부여할 수 있습니다. 서로 다른 서버인 경우에는 도메인 파티션 이름이 중복되어도 됩니다.

![](<../../.gitbook/assets/img_017 (15).png>)

<img src="../../.gitbook/assets/image (125).png" alt="" data-size="line"> **도메인 아이디**:  회사별로 갖게 되는 아이디로 1부터 시작해서 1씩 증가합니다. 여러 대의 서버를 이용하여 서비스하는 경우라도 시스템 전체적으로 아이디는 유일한 값을 갖습니다.

예) 회사가 N 개 일 때, N개의 도메인 아이디가 생성됩니다

<figure><img src="../../.gitbook/assets/img_019 (13).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (126).png" alt="" data-size="line"> **고정 폴더명**: 시스템 관리에 필요한 고정된 구조로 폴더명은orgcowork입니다.&#x20;

<img src="../../.gitbook/assets/image (127).png" alt="" data-size="line"> **문서함 아이디**: 싱글도메인 문서함 아이디 규칙과 동일합니다. 싱글도메인 개인문서함의 문서함 아이디를 참고하세요.

<img src="../../.gitbook/assets/image (128).png" alt="" data-size="line"> **사용자 이름(아이디)**: 사용자를 등록하면 홍길동(gdhong)과 같이 폴더가 생성됩니다.

#### 부서문서함 폴더의 예

<figure><img src="../../.gitbook/assets/img_023 (10).png" alt=""><figcaption></figcaption></figure>

<img src="../../.gitbook/assets/image (131).png" alt="" data-size="line">\~<img src="../../.gitbook/assets/image (132).png" alt="" data-size="line">의 경우 개인문서함 폴더의 예의 내용과 동일합니다.

<img src="../../.gitbook/assets/image (130).png" alt="" data-size="line"> **문서함 아이디**: 싱글도메인 문서함 아이디 규칙과 동일합니다. 싱글도메인 부서문서함의 문서함 아이디 규칙을 참고하세요.

<img src="../../.gitbook/assets/image (129).png" alt="" data-size="line"> **부서폴더**: 사용자가 직접 수동으로 만든 폴더의 예입니다. 부서문서함의 윈도우탐색기에서 확인할 수 있습니다.



다음 동영상에서 문서함 내 파일의 저장 경로 예시를 확인할 수 있습니다.

{% embed url="https://youtu.be/PGZec5b3Nak?si=I52Iia_0GGIZ6bnF&t=318" %}
