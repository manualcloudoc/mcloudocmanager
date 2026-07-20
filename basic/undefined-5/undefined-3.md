# 사용자 개인문서함의 데이터 인계하기

문서중앙화 솔루션은 사용자의 개인 문서함에 있는 모든 문서들을 다른 사용자의 개인 문서함으로 그대로 옮겨주는 ‘데이터 인계’ 기능을 제공합니다. 데이터 인계 기능을 사용하면 승진이나 부서 이동, 퇴직 등으로 인해 후임자에게 업무를 인계해야 하는 경우에 쉽고 간편하게 데이터를 전달할 수 있습니다.

데이터 인계 기능은 관리자와 사용자가 모두 사용할 수 있습니다. 자신의 업무를 인계하고자 하는 ‘사용자’는 인수자를 지정한 후 승인권자의 승인을 받는 과정을 거쳐서 데이터 인계 기능을 사용할 수 있고, ‘관리자’는 인계자와 인수자를 직접 지정하여 바로 데이터 인계 기능을 실행할 수 있습니다.

데이터 인계 기능이 실행되면 먼저 데이터를 인계 받을 인수자의 개인문서함에 새로운 폴더가 생성되고 해당 폴더로 인계자의 개인문서함에 있는 문서가 복사됩니다. 모든 문서의 복사가 끝나면 인계자의 개인문서함에 있던 문서는 모두 삭제됩니다.

인수자의 개인문서함에 생성되는 폴더의 이름은 다음과 같은 형식으로 설정됩니다. 폴더 이름을 통해 인계자의 정보와 인계가 이루어진 시간을 파악할 수 있습니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_000 (45).png" alt=""><figcaption></figcaption></figure></div>

{% hint style="warning" icon="square-poll-horizontal" %}
데이터 인계 기능은 인계자와 인수자가 같은 서버와 같은 파티션에 있는 경우에만 사용할 수 있습니다.
{% endhint %}

{% hint style="warning" icon="square-poll-horizontal" %}
사용자가 데이터 인계 기능을 사용하는 방법은 **사용자 매뉴얼**- [**데이터 인계 기능 소개**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/undefined-2/undefined)의 내용을 참고하세요.&#x20;
{% endhint %}

데이터 인계 기능은 웹 메뉴에서만 제공되고 윈도우 에이전트에서는 제공되지 않습니다. 웹 메뉴에서 특정 사용자의 개인 문서함 데이터를 다른 사용자에게 인계하는 방법은 다음과 같습니다.

1. 웹 페이지에 로그인한 후 화면 왼쪽 메뉴에서 **일반관리 - 인사 조직 관리** – **사용자 - 사용자 관리**를 클릭합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_003 (34).png" alt=""><figcaption></figcaption></figure>

2. 현재 등록된 사용자들의 목록의 보여주는 **사용자 관리** 화면이 나타납니다. 화면에 상단에 있는 다음 두 항목들을 사용하여 데이터를 인계할 사용자(데이터 소유주)를 검색합니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_004 (27).png" alt="" width="562"><figcaption></figcaption></figure></div>

<table><thead><tr><th width="124">항목</th><th>설정 방법</th></tr></thead><tbody><tr><td><strong>계정 상태</strong></td><td><p>검색할 사용자의 계정 상태를 클릭하여 체크합니다.</p><ul><li>전체: 모든 상태의 사용자</li><li>정상: 정상적으로 사용되고 있는 계정</li><li>정지: 잘못된 비밀번호를 입력한 횟수가 정해진 횟수를 초과하여 정지된 계정</li></ul></td></tr><tr><td><strong>검색 조건</strong></td><td>검색할 사용자의 이름이나 ID를 입력합니다. 사용자 이름이나 ID의 일부만 입력할 수도 있습니다. 이 항목을 설정하지 않으면 모든 사용자를 대상으로 검색됩니다.</td></tr></tbody></table>

3. 항목을 설정한 후 **검색** 버튼을 누릅니다.

<div align="left"><img src="../../.gitbook/assets/img_005 (23).png" alt="" width="556"></div>

4. 화면 아래에 설정한 조건의 사용자 목록이 출력됩니다. 사용자 목록에서 데이터를 인계할 사용자의 **데이터 인계** 항목에 있는 **대상선택** 버튼을 클릭합니다.

![](<../../.gitbook/assets/img_006 (20).png>)

5. **데이터 인계** 창이 나타나면 데이터를 인수받을 사용자를 선택합니다. **문서함 이전 받을 사용자** 항목 아래에 있는 입력란에 인수자의 이름이나 ID를 입력하고 **검색**을 클릭합니다. 이름이나 ID의 일부만 입력해도 됩니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_007 (18).png" alt="" width="419"><figcaption></figcaption></figure></div>

6. 창 아래에 있는 **검색 결과** 부분에 검색된 사용자들이 표시됩니다. 목록에서 인수자를 선택한 후 **확인** 버튼을 클릭합니다. 사용자 이름(ID) 뒷부분에 ‘다른 파티션 사용자(인계 불가)’라고 표시된 사용자는 인수자로 선택할 수 없습니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_008 (16).png" alt="" width="416"><figcaption></figcaption></figure></div>

7. 데이터 인계 기능이 진행될 것임을 알려주는 팝업 창이 나타납니다. **확인** 버튼을 클릭하면 데이터 인계 과정이 실행되기 시작합니다.
8. 데이터 인계 작업이 성공적으로 완료되면 이를 알려주는 팝업창이 나타납니다. **확인** 버튼을 클릭합니다.&#x20;

{% hint style="warning" icon="square-poll-horizontal" %}
데이터 인계 작업이 끝나면 데이터를 인수받은 사용자의 개인문서함에 다음과 같은 폴더가 만들어진 것을 확인할 수 있습니다.&#x20;

<img src="../../.gitbook/assets/img_010 (11).png" alt="" data-size="original">
{% endhint %}
