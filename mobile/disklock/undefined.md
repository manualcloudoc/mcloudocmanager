# 중앙문서함으로 다운로드한 문서 바로 열기 오류 해결 방법

#### <mark style="color:$primary;">문제</mark>

웹 브라우저에서 중앙문서함으로 파일 다운로드 완료 후 바로 열기를 이용하여 열람 시도 시 오류가 발생하는 경우입니다.

<figure><img src="https://support.mcloudoc.com/galleryDocuments/edbsn826cec40d6aa1d9428ecd3da85ca5db63de113c2370682bc225dbfcec4d9bd4a84886f6d33d9ea886a56850c6c8305be?inline=true" alt=""><figcaption></figcaption></figure>

&#x20;

<div align="left"><figure><img src="https://support.mcloudoc.com/galleryDocuments/edbsnf8f9e949479d6ea3baebd1efa1358e502987cf3879d55d10740c407b6b47bda944b21fc308ec99396f10b9964e05b825?inline=true" alt="" width="563"><figcaption></figcaption></figure></div>

#### <mark style="color:$primary;">원인</mark> <a href="#id-1" id="id-1"></a>

웹 브라우저에서 바로 열기로 문서를 열람하기 위해서는 웹 브라우저가 해당 문서의 열람 프로그램 파일에 대해 읽기 권한을 보유해야 합니다. 이 권한이 없을 경우, 위와 같은 오류가 발생할 수 있습니다.

#### <mark style="color:$primary;">해결 방법</mark>

사용자에게 적용된 로컬저장금지 정책에 위와 같은 권한을 허용하는 정책 아이템(위 그림의 예에서는 웨일 브라우저에 MS Word 실행 파일에 대한 읽기 권한을 허용하는 정책 아이템)을 추가하여 문제를 해결할 수 있습니다.\
DiskLock 콘솔의 정책 서포트 기능을 사용하면 다음과 같이 문제의 원인을 확인하고, 필요한 정책 아이템을 구성하여 정책에 추가할 수 있습니다.

{% hint style="warning" icon="square-poll-horizontal" %}
정책 서포트 기능의 내용 및 자세한 화면 설명은[ ](https://support.mcloudoc.com/portal/ko/kb/articles/disklock-%EC%BD%98%EC%86%94%EC%97%90%EC%84%9C-%EC%A0%95%EC%B1%85-%EC%84%9C%ED%8F%AC%ED%8A%B8-%EA%B8%B0%EB%8A%A5-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0)[**DiskLock 콘솔에서 정책 서포트 기능 사용하기**](../../disklock/disklock/console/disklock-5.md)를 참고합니다.
{% endhint %}

1. DiskLock 콘솔에서 **로컬저장금지 정책** – **정책 관리**를 클릭합니다.
2. 좌측 정책 목록에서 현재 사용자 PC에서 사용 중인 로컬저장금지 정책을 선택합니다. 사용 중인 정책은 정책명 앞의 ![](https://support.mcloudoc.com/galleryDocuments/edbsn1a92d73b8e8e559a6fc2553c3cf9abebc823300df331e09abb531d246b8302ec9430104dee6633038e0a69946f9ac53a?inline=true) 표시로 식별할 수 있습니다.
3. 우측 상단 정책 아이템 메뉴의 **정책 서포트**를 클릭합니다.
4. 정책 서포트 창에서 **모니터링 시작** 버튼을 클릭하여 파일 입출력 거부 로그 모니터링을 시작합니다.
5. 오류가 발생했던 작업을 다시 수행합니다. 본 예시에서는 웨일 브라우저에서 중앙문서함으로 \~.docx 파일을 다운로드한 후 바로 열기를 시도합니다.
6. 오류가 발생한 후에는 정책 서포트 창에서 모니터링 중지 버튼을 클릭한 후, 파일 입출력 거부 로그를 확인합니다.
7. 수집된 파일 입출력 거부 로그를 검토하여 오류의 원인으로 추정되는 로그를 식별합니다. 본 예시에서는 whale.exe 프로세스에 대해 WINWORD.EXE 파일의 입출력이 차단된 것을 확인할 수 있습니다.&#x20;

{% hint style="success" icon="lightbulb-exclamation-on" %}
​필요 시 컨텍스트 메뉴의 **차단한 정책 아이템** 보기를 클릭하여 특정 로그에 적용된 차단 정책 아이템을 확인할 수 있습니다.
{% endhint %}

<figure><img src="https://support.mcloudoc.com/galleryDocuments/edbsn9578d90651c3c1d79bd61058bf48269c819efbadbc3e171ac47a51bf41119d3832eb1c2f48a00b3cb3e75decc2974941?inline=true" alt=""><figcaption></figcaption></figure>

8. 해결이 필요한 로그(위의 그림에서는 WINWORD.EXE 차단 로그)를 선택한 후, **선택 로그 정책 아이템 추가** 버튼을 클릭합니다.
9. 해당 프로세스가 소속된 애플리케이션 카테고리가 두 개 이상인 경우 다음과 같이 애플리케이션 카테고리 선택 창이 팝업됩니다. 이 경우, 생성할 정책 아이템에 적합한 카테고리를 선택한 후 **확인**을 클릭합니다. 프로세스가 소속된 애플리케이션 카테고리가 한 개인 경우에는 이 단계 없이 곧바로 ‘**정책 아이템 추가**’ 창이 표시됩니다.

<div align="left"><figure><img src="https://support.mcloudoc.com/galleryDocuments/edbsnf8f9e949479d6ea3baebd1efa1358e50ee4d9c2e1badb3a69cbc2e19091d8e65e4dc66b133030368163e3a85bf97b835?inline=true" alt="" width="375"><figcaption></figcaption></figure></div>

10. **‘정책 아이템 추가’** 창에 정책서포트 기능이 제안하는 정책 아이템 내용이 자동으로 생성되어 표시됩니다(아래 왼쪽 그림). 아이템 이름과 허용 권한 등 변경이 필요한 항목을 설정한 후 **확인** 버튼을 클릭합니다. 여기서는 **읽기** 권한이 필요하므로, **쓰기, 삭제** 권한 등은 체크 해제합니다(아래 오른쪽 그림).<br>

    <figure><img src="https://support.mcloudoc.com/galleryDocuments/edbsn08e3096de2a4c563c521373351a37078466b415bb5277f77aa318c5c3fae1b040d410f593087db6d88462a8dbea86c91?inline=true" alt=""><figcaption></figcaption></figure>

{% hint style="warning" icon="square-poll-horizontal" %}
정책 아이템의 항목별 설명 및 설정 방법은 [**DiskLock 콘솔에서 로컬저장금지 정책 아이템 설정하기**](../../disklock/disklock/console/disklock-2.md)를 참고합니다.&#x20;
{% endhint %}

11. 새로 생성된 정책 아이템의 내용이 **추가한 정책 아이템** 영역이 표시됩니다.&#x20;

<figure><img src="https://support.mcloudoc.com/galleryDocuments/edbsn08e3096de2a4c563c521373351a37078e95dc3594e45657c6ccadcd683cbfd993e2479b377d75d8fae99953fadae22c4?inline=true" alt=""><figcaption></figcaption></figure>

12. 위 화면에서 추가한 **정책 아이템**을 확인 후 하단의 **적용** 버튼을 클릭하면 해당 정책 아이템이 현재 사용 중인 로컬저장금지 정책에 추가됩니다. 다음과 같이 로컬저장금지 정책 관리 페이지에서 정책 아이템이 추가된 것을 확인할 수 있습니다.

![](https://support.mcloudoc.com/galleryDocuments/edbsn826cec40d6aa1d9428ecd3da85ca5db64236249c032e7c02526898524575ce92656393ceb1852ec95b6c2c3866288d2c?inline=true)

13. DiskLock 콘솔 좌측 메뉴 하단의 내 PC에 정책 새로고침, 또는 윈도우 에이전트 트레이 메뉴의 정책 새로 고침을 클릭하여 정책 변경 사항을 PC에 곧바로 적용합니다.
14. 오류가 발생했던 작업을 다시 수행하여 오류 해결 여부를 확인합니다. 본 예시에서는 웨일 브라우저에서 중앙문서함에 다운로드한 docx파일을 바로 열기 시도 시 Microsoft Word(WINWORD.EXE)가 성공적으로 실행되는 것을 확인할 수 있습니다.

<figure><img src="https://support.mcloudoc.com/galleryDocuments/edbsncdcde8cd8d7c1a9a3fc3bb7dc864f71e5bae69e1f88638a7f08218a5ce701ade9bf6a37bfde15b86e1f681586812ea9c?inline=true" alt=""><figcaption></figcaption></figure>



<figure><img src="https://support.mcloudoc.com/galleryDocuments/edbsn58ee7d3906ac531f5e1a12ba758d18d7db4e987aea4a615f414b4d87361e1b98be7a87a2b5b2c3fe633073f5373d6a82?inline=true" alt=""><figcaption></figcaption></figure>
