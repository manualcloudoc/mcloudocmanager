# 개인정보 검출 관련 통계 알아보기

​

관리자는 웹페이지에서 개인정보 검출 파일에 대한 통계 정보를 확인할 수 있습니다. 또한, 설정에 따라 개인정보 검출 배치(batch) 작업 완료시마다 검출 통계 리포트 메일을 받아 볼 수 있습니다.

#### <mark style="color:$primary;">웹페이지에서 개인정보 검출 통계 확인하기</mark>

정해진 기간 동안의 개인정보 검출 파일의 개수, 항목별 검출 건수 및 파일 생성자별 검출 순위에 대한 통계를 확인할 수 있습니다.

1. **일반 모듈 관리 – 개인정보보호 – 통계**를 클릭합니다.
2. 조회를 원하는기간(검출 날짜 기준)을 선택한 후 **검색** 버튼을 클릭합니다.
3. **검색**버튼 하단 탭에서원하는 정보를 선택합니다.
4. **검출 파일 수**: **검출 날짜**별 개인정보 검출 파일 수를 확인합니다.

<figure><img src="../.gitbook/assets/img_000 (174).png" alt=""><figcaption></figcaption></figure>

* 항목별 검출 건수:  선택한 기간의 검출 항목(주민번호, 휴대폰번호, 외국인주민번호, 법인등록번호, 사업자등록번호, 카드번호 16자리, 여권번호, 구 여권번호, 이메일, 전화번호)별 검출 건수를 확인합니다.

<figure><img src="../.gitbook/assets/img_001 (160).png" alt=""><figcaption></figcaption></figure>

* **파일 생성자 검출 순위**: 선택한 기간 중에 개인정보가 검출된 파일 수가 많은 순서대로 파일 생성자 **순위**를 확인할 수 있습니다. 파일 생성자의 **부서명, 파일 생성자 이름, 파일 생성자 ID, 검출 파일 수, 검출 항목 수**가 함께 표시됩니다.

<figure><img src="../.gitbook/assets/img_002 (138).png" alt=""><figcaption></figcaption></figure>

#### <mark style="color:$primary;">검출 통계 리포트 메일</mark>

개인정보 검출을 위한 주기적인 배치(batch) 작업 완료 시 개인정보 검출 파일에 대한 검출 통계 리포트 메일이 미리 지정된 수신자에게 발송됩니다.

{% hint style="warning" icon="square-poll-horizontal" %}
통합 리포트 메일 수신자는 **설정홈 - 일반 모듈 설정 - 개인정보보호 - 통합 리포트 메일 수신자 설정**에서 변경할 수 있습니다. **사용 안 함** 또는 **관리자 메일 계정**(메일 서버 관리자)을 선택하거나 메일 주소를 직접 입력할 수 있습니다.&#x20;
{% endhint %}

![](<../.gitbook/assets/img_004 (95).png>)

<img src="../.gitbook/assets/image (184).png" alt="" data-size="line"> 개인정보 검출에 대한 통합 알림 메일의 제목입니다.

<img src="../.gitbook/assets/image (186).png" alt="" data-size="line"> 개인정보가 검출된 서버명, 검출일시, 개인정보가 검출된 파일 수, 검출된 개인정보 총 항목 수를 확인할 수 있습니다.

<img src="../.gitbook/assets/image (187).png" alt="" data-size="line"> 관리자가 검출 파일들의 내역을 조회하고 조치할 수 있는 **검출 파일 관리** 메뉴로 바로 이동하는 링크를 제공합니다.

<img src="../.gitbook/assets/image (188).png" alt="" data-size="line"> 금일 개인정보가 검출된 검출 항목별 개수를 문서함별로 확인할 수 있습니다.

<img src="../.gitbook/assets/image (189).png" alt="" data-size="line"> 금일까지 미조치 상태인 개인정보 검출 항목별 누적 개수를 문서함별로 확인할 수 있습니다.
