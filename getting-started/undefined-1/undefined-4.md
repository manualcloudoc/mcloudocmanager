# 관리자 빠른 시작 가이드 – 문서링크 정책 적용하기

사용자 PC에 로컬저장금지 정책이 적용되면 이메일이나 메신저에 중앙문서함 파일을 첨부할 수 없으므로, 문서를 전달해야 할 경우 문서반출이나 문서링크 복사와 같은 방식을 사용해야 합니다.\
문서링크 복사 기능을 사용하면, 사용자가 중앙문서함 문서의 링크를 생성하여 수신자에게 전달하고, 수신자는 해당 링크에서 문서를 다운로드할 수 있습니다. 문서링크 복사는 주로 사내에서 대용량 파일을 전달할 때 유용하나, 문서중앙화 서버가 공인 IP를 사용하는 경우에는 외부 수신자에게 문서를 전달할 때도 사용할 수 있습니다.\
사용자가 문서링크 복사 기능을 사용하려면, 사전에 문서링크 정책이 적용되어 있어야 합니다. 따라서, 관리자는 문서링크 기본 정책을 확인하고, OTP를 수신할 이메일 도메인을 등록하는 등 정책을 고객사 환경에 맞게 조정한 후, 전사에 적용해야 합니다.

{% hint style="warning" icon="square-poll-horizontal" %}
문서링크 복사의 용도 및 사용 절차에 대한 자세한 설명은 [**문서 공유 및 협업을 위한 기능 소개**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/undefined)를 참고합니다.&#x20;
{% endhint %}

### <mark style="color:$primary;">기본 정책 확인 및 변경하기</mark>

1\.   **일반 모듈 관리 – Basic – 공유·협업 – 문서링크 – 정책 관리** 메뉴를 선택한 후, 좌측 정책 목록에서 정책명(**00000.기본정책**)을 클릭합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_001 (147).png" alt=""><figcaption></figcaption></figure>

2. 페이지 우측 영역에 정책 내용이 표시됩니다. 내부 직원, 계열사 직원을 수신자로 사용할 수 있으며, 각 수신자 유형별로 다음과 같이 정책 항목이 설정되어 있는 것을 확인할 수 있습니다.

<table><thead><tr><th width="176">정책 항목</th><th width="258">내부직원</th><th>계열사직원</th></tr></thead><tbody><tr><td><strong>수신자 인증 방식</strong></td><td><ul><li>에이전트 로그인 (필수)</li><li>이메일 OTP 인증</li><li>패스워드 인증</li></ul></td><td><ul><li>이메일 OTP 인증 (필수) 등록된 도메인으로 사용 제한</li><li>에이전트 로그인</li><li>패스워드 인증</li></ul></td></tr><tr><td><strong>승인 여부 및 결재 방식</strong></td><td>승인 필요 없음</td><td>선결재 승인 필요</td></tr><tr><td><strong>다운로드 유효기한</strong></td><td>제한 없음</td><td>최대 14일</td></tr><tr><td><strong>다운로드 최대 횟수</strong></td><td>제한 없음</td><td>10회</td></tr></tbody></table>

{% hint style="warning" icon="square-poll-horizontal" %}
수신자 인증 방식에 대한 설명은 [**링크 공유 기능에 보안 절차 적용하기**](../../basic/undefined-15/undefined.md) 매뉴얼의 [**수신자 인증**](../../basic/undefined-15/undefined.md#undefined-3) 목차를 참고합니다.
{% endhint %}

3. 위의 기본 정책을 사용할 경우, 계열사 직원 인증 방식으로 이메일 OTP가 필수 적용되며, OTP 수신 이메일 주소는 등록된 도메인으로 제한됩니다. 따라서 관리자는 사전에 수신자 그룹의 이메일 도메인을 정책에 등록해야 합니다. 이렇게 하면 기본 정책이 적용된 사용자가 문서 링크 복사 신청 시, OTP를 수신할 주소로 해당 도메인의 주소만 입력할 수 있습니다.

> 1) **수신자 유형별 공통 설정**의 상단 탭에서 **계열사직원**을 선택합니다.
> 2) **등록된 도메인으로 사용 제한** 아래의 도메인 입력 란에 계열사(수신자 그룹)의 이메일 도메인(예: mcloudoc.com)을 입력한 후 **추가** 버튼을 클릭합니다.&#x20;
> 3) 우측 하단의 **적용** 버튼을 클릭하여 정책 변경 사항을 시스템에 적용합니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_003 (110).png" alt="" width="563"><figcaption></figcaption></figure></div>

{% hint style="warning" icon="square-poll-horizontal" %}
이 외 기본 설정을 변경하거나 다른 정책을 추가로 생성해야 할 경우에는 [**문서링크 정책 관리하기**](../../basic/undefined-15/undefined-2.md)를 참고하여 정책을 설정합니다.
{% endhint %}

### <mark style="color:$primary;">기본 정책 적용하기</mark>

1. **일반 모듈 관리 – Basic – 공유·협업 – 문서링크 – 정책 적용** 메뉴를 선택합니다.
2. 좌측의 조직도에서 정책을 적용할 대상을 선택합니다. 전사에 적용하기 위해서는 사이트명(아래 그림의 예에서는 **MYCOMPANY**)을 선택합니다.&#x20;

<figure><img src="../../.gitbook/assets/img_005 (73).png" alt=""><figcaption></figcaption></figure>

3. 우측의 정책 목록에서 적용할 정책(여기서는 **00000.기본정책**)을 선택한 후, 우측 상단의 **적용** 버튼을 클릭합니다. 선택한 정책이 하위 부서와 사용자에게 모두 상속되어 적용되는 것을 확인할 수 있습니다.

{% hint style="danger" %}
정책 선택 후 화면에 정책이 적용되어 보이더라도, 반드시 **적용** 버튼을 클릭해야 시스템에 정책 설정 내용이 반영됩니다.
{% endhint %}
