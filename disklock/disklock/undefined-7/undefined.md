# 정책 라이브러리를 이용하여 로컬저장금지 정책 설정하기

다음은 정책 라이브러리의 정책 아이템을 활용하여 로컬저장금지 정책을 설정하는 방법입니다. **카카오톡**애플리케이션에 사용할 새 정책 아이템을 정책 라이브러리에서 찾아 로컬저장금지 정책에 추가하는 것을 예로 들어 설명합니다.

1\.  웹에서 **PC 보안 모듈 관리**의 **DiskLock** – **로컬저장금지** – **정책 라이브러리** – **정책 적용** 메뉴를 차례로 클릭합니다.

![](<../../../.gitbook/assets/img_000 (138).png>)

2\.    ‘**정책 적용**’ 화면이 나타납니다. 화면에는 서버의 정책 라이브러리에 등록되어 있는 애플리케이션 카테고리 목록과 정책 아이템 목록이 표시됩니다. \
![](<../../../.gitbook/assets/img_001 (130).png>)&#x20;

애플리케이션 카테고리 목록에는 알파벳 순으로 정렬된 애플리케이션 카테고리가 표시됩니다. 다음과 같은 애플리케이션 카테고리의 정보를 참고하여 원하는 애플리케이션 카테고리(여기서는 KakaoTalk)를 찾습니다.

<table><thead><tr><th width="216">항목</th><th>설명</th></tr></thead><tbody><tr><td><strong>애플리케이션</strong> <strong>카테고리</strong></td><td>애플리케이션 카테고리 이름</td></tr><tr><td><strong>고객사 사용 여부</strong></td><td>애플리케이션 카테고리 생성 여부 및 카테고리로 분류된 애플리케이션의 유무<br><img src="../../../.gitbook/assets/image (211).png" alt=""></td></tr><tr><td><strong>정책아이템 수</strong></td><td>정책 라이브러리에 등록된 해당 애플리케이션 카테고리의 정책 아이템 개수</td></tr></tbody></table>

3\.   목록에 표시된 애플리케이션 카테고리가 많은 경우, 목록 위에 있는 **검색 칸**을 이용해 원하는 카테고리를 쉽게 찾을 수 있습니다. 검색 칸에 애플리케이션 카테고리 이름을 입력한 후 Enter 키를 누르면, 검색이 실행됩니다. 검색은 대소문자를 구분하지 않으며, 이름의 일부만 입력해도 결과가 표시됩니다.\
&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_002 (113).png" alt=""><figcaption></figcaption></figure></div>



4\.  다음 화면은 **kakao**로 검색한 결과입니다. kakao가 포함된 두 개의 애플리케이션 카테고리가 정책 라이브러리에 등록되어 있음을 알 수 있습니다. 각 애플리케이션 카테고리에 적용되는 정책 아이템의 목록을 보려면 해당 카테고리를 클릭합니다.

<div align="left"><img src="../../../.gitbook/assets/img_003 (97).png" alt=""></div>

5\.  선택한 **KakaoTalk** 애플리케이션 카테고리에 적용되는 정책 아이템 목록이 다음과 같이 출력됩니다. 최근에 생성된 정책 아이템일수록 목록 아래쪽에 위치합니다.&#x20;

<div align="left"><img src="../../../.gitbook/assets/img_004 (74).png" alt=""></div>

{% hint style="warning" icon="square-poll-horizontal" %}
**정책 아이템 목록**은 웹 화면의 크기에 따라 애플리케이션 카테고리 목록의 우측이나 하단에 배치될 수 있습니다.&#x20;
{% endhint %}

각 정책 아이템은 다음과 같은 항목을 포함하고 있습니다.&#x20;

<table data-search="false"><thead><tr><th width="206">항목</th><th>설명</th></tr></thead><tbody><tr><td><strong>정책 아이템명</strong></td><td>정책 아이템 이름</td></tr><tr><td><strong>상세내용</strong></td><td>정책 아이템에 대한 상세한 정보를 보여주는 팝업 창을 띄우는 버튼</td></tr><tr><td><strong>아이템 등록일시</strong></td><td>정책 아이템이 생성된 날짜와 시각</td></tr><tr><td><strong>제조회사명</strong></td><td>정책 아이템이 적용되는 애플리케이션의 제조회사</td></tr><tr><td><strong>제품명</strong></td><td>정책 아이템이 적용되는 애플리케이션의 제품 이름</td></tr><tr><td><strong>프로세스</strong></td><td>정책 아이템이 적용되는 애플리케이션의 실행 파일 이름</td></tr></tbody></table>

6\.   더 상세한 정보가 필요한 정책 아이템이 있으면 해당 정책 아이템의 **상세내용** 항목에 있는 **보기**를 클릭합니다. ‘**정책 아이템 상세내용**’ 팝업 창이 나타납니다.&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_006 (54).png" alt=""><figcaption></figcaption></figure></div>

팝업 창에는 다음과 같은 정책 아이템의 설정 정보가 표시됩니다.

<table data-search="false"><thead><tr><th width="187">항목</th><th>설명</th></tr></thead><tbody><tr><td><strong>취합 일시</strong></td><td>정책 아이템이 정책 라이브러리에 등록된 날짜와 시각</td></tr><tr><td><strong>아이템 등록일시</strong></td><td>정책 아이템이 생성된 날짜와 시각</td></tr><tr><td><strong>디스크 종류</strong></td><td>정책 아이템이 적용되는 대상 디스크</td></tr><tr><td><strong>파일 경로</strong></td><td>정책 아이템이 디스크의 특정 경로에만 적용되는 경우, 해당 파일의 경로</td></tr><tr><td><strong>하위 폴더 포함</strong></td><td>정책 아이템이 하위 폴더까지 적용되는지 여부</td></tr><tr><td><strong>파일 종류</strong></td><td>정책 아이템이 적용되는 파일의 종류(지정된 확장자의 파일에만 적용)</td></tr><tr><td><strong>작업 권한</strong></td><td>정책 아이템에 설정된 조건과 일치할 경우 대상 디스크에 대해 허용/차단할 권한</td></tr><tr><td><strong>파일 크기</strong></td><td>정책 아이템이 특정 크기 이상의 파일에만 적용되는지 여부</td></tr><tr><td><strong>종류</strong></td><td>정책 아이템에 설정된 조건과 일치할 경우 작업 권한의 허용/차단 여부</td></tr></tbody></table>

7. 각 정책 아이템의 설정 정보를 확인한 후, 정책 아이템의 좌측에 있는 체크 박스를 클릭하여 적용할 정책 아이템을 선택합니다. 애플리케이션 카테고리 좌측의 체크 박스나 정책 아이템 목록의 상단에 위치한 체크 박스를 클릭하면 모든 정책 아이템을 일괄적으로 선택할 수 있습니다.

* **개별 정책 아이템 선택하기**

<figure><img src="../../../.gitbook/assets/img_007 (46).png" alt=""><figcaption></figcaption></figure>

* **모든 정책 아이템 일괄 선택하기**

<figure><img src="../../../.gitbook/assets/img_008 (43).png" alt=""><figcaption></figcaption></figure>

8. 적용할 정책 아이템을 모두 선택하였으면 목록 우측 상단의 **적용**을 클릭합니다.&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/img_009 (36).png" alt=""><figcaption></figcaption></figure></div>

9. 문서중앙화 서버에 정의된 모든 로컬저장금지 정책들을 보여주는 ‘**삽입 대상 정책**’ 창이 나타납니다. 이전 과정에서 선택한 정책 아이템을 적용할 로컬저장금지 정책을 선택한 후 **확인**을 클릭합니다. 여러 개의 로컬저장금지 정책을 선택하는 것도 가능합니다.

<div align="left"><img src="../../../.gitbook/assets/img_010 (32).png" alt=""></div>

10. 선택한 로컬저장금지 정책에 정책 아이템이 적용되었음을 알려주는 팝업 창이 나타납니다.

<div align="left"><img src="../../../.gitbook/assets/img_011 (25).png" alt="" width="305"></div>

{% hint style="warning" icon="square-poll-horizontal" %}
로컬저장금지 정책에 선택한 정책 아이템이 이미 포함되어 있으면 해당 정책 아이템은 자동으로 제외됩니다. 이러한 중복 정책 아이템이 있는 경우, 다음과 같은 팝업 창이 표시됩니다.&#x20;



<img src="../../../.gitbook/assets/img_013 (16).png" alt="" data-size="original">
{% endhint %}

11. 계속해서 다른 애플리케이션 카테고리의 정책 아이템도 로컬저장금지 정책에 적용하려면 3번 과정부터 반복해서 실행하면 됩니다.
12. **DiskLock 콘솔**에서 선택한 정책 아이템이 로컬저장금지 정책에 적용되었는지 확인할 수 있습니다. \
    **PC 보안 모듈 관리**의 **DiskLock** – **로컬저장금지** – **콘솔 실행** 메뉴를 차례로 클릭한 후 다음과 같은 ‘**콘솔 실행**’ 화면이 나타나면 **DiskLock 콘솔 실행** 버튼을 클릭합니다.

<div align="left"><img src="https://support.mcloudoc.com/galleryDocuments/edbsn0d5c3304276e3597bdeed3520f63b1b052c83bce151c85f1d90938b84ec28c33e75febd0f91b0006b66e7f031774e2ee?inline=true" alt="" height="218" width="378"></div>

13. ‘**디스크락 콘솔**’ 창이 팝업됩니다. 화면의 좌측 메뉴에서 **로컬저장금지 정책 – 정책 관리** 메뉴를 클릭![](<../../../.gitbook/assets/img_015 (12).png>)한 후 현재 정의된 로컬저장금지 정책 목록이 화면 중간에 표시되면, 정책 라이브러리의 정책 아이템을 적용한 정책을 클릭![](<../../../.gitbook/assets/img_016 (12).png>)합니다. 선택한 로컬저장금지 정책에 포함된 정책 아이템의 목록이 화면 우측에 표시됩니다. 정책 아이템 중, **library\_**&#xB85C; 시작하는 이름의 정책 아이템이 정책 라이브러리에서 가져온 정책 아이템![](<../../../.gitbook/assets/img_017 (8).png>)입니다.

<div align="left"><img src="https://support.mcloudoc.com/galleryDocuments/edbsn947a4b2f76114d918d02693caa4280b5e966c45e36a85ede038238f25bdb861ae46d3a001d0bcf2591c5aff5f152dd28?inline=true" alt=""></div>

14. 필요한 경우, 정책 아이템을 더블클릭하여 정책 아이템의 설정을 변경할 수 있습니다.&#x20;

{% hint style="warning" icon="square-poll-horizontal" %}
정책 아이템 설정을 변경하고 서버에 적용하는 방법은 [**DiskLock 콘솔에서 로컬저장금지 정책 아이템 설정하기**](../disklock/disklock-1.md)를 참고합니다.
{% endhint %}
