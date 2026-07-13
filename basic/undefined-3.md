# 서버 관리 웹메뉴 사용 방법

관리자웹 **서버 관리** 메뉴에서는 각 회사별 서버 구성에 맞게 파티션을 추가하여 관리합니다. 서버 관리에 앞서 [**스토리지 마운트(Storage Mount) 방법**](../system/sw/storage-mount.md), [**시스템 구성별 파티션 정보 등록 방법**](../system/sw/undefined-2.md)을 확인하여 주시기 바랍니다. 해당 아티클에서 파티션 개념 및 시스템 구성을 참고하실 수 있습니다.

### <mark style="color:$primary;">파티션 추가, 삭제하기</mark>

#### 파티션 추가하기

파티션을 추가하기에 앞서 /plusdrive/home이나 d:\plusdrive\orgcowork 등과 같은 파티션의 경로를 미리 생성할 것을 권장합니다. 만일 해당 폴더가 존재하지 않는 경우 솔루션이 자동으로 폴더를 생성합니다.

1. **일반관리 - 서버 관리**를 클릭합니다.

![](<../.gitbook/assets/img_000 (53).png>)

2. **추가**를 클릭합니다.
3. **‘파티션 추가’** 창에 등록할 파티션 정보를 입력합니다.​

<div align="left"><figure><img src="../.gitbook/assets/img_001 (50).png" alt=""><figcaption></figcaption></figure></div>

<table data-search="false"><thead><tr><th width="143">항목명</th><th width="114">소항목명</th><th>내용</th></tr></thead><tbody><tr><td><strong>용도</strong></td><td></td><td></td></tr><tr><td></td><td><strong>개인문서함</strong></td><td>파티션 내에 여러 사용자 폴더가 생성됩니다.</td></tr><tr><td></td><td><strong>부서문서함</strong></td><td><p>파티션 내에 여러 부서문서함이 생성됩니다. </p><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p>캐시 업데이트 목적의 부서문서함 파티션인 경우, <strong>문서함 수용여부</strong>를 <strong>수용 안 함</strong>으로 등록하기 때문에 /plusdrive/file/과 하위의 부서문서함은 생성되지 않습니다.</p></div></td></tr><tr><td></td><td><strong>도메인</strong></td><td>시스템을 멀티도메인으로 구성한 경우만 이용합니다. 파티션 내에 여러 추가 도메인이 생성됩니다. 각 추가 도메인은 하나의 기업 혹은 기관을 의미합니다.</td></tr><tr><td></td><td><strong>웹서버</strong></td><td>웹서버가 2개 이상으로 구성된 경우 캐시 업데이트 목적으로만 등록하며, 파티션 이름은 모두 가능하지만 관리 편의상 ‘web’으로 입력을 권장합니다.</td></tr><tr><td><strong>관리자용 개인문서함 드라이브명</strong></td><td></td><td><p>파티션의 용도가 개인문서함인 경우에만 활성화되는 항목입니다. 서비스관리자가 윈도우 에이전트를 실행하면, 윈도우 탐색기에 개인문서함의 드라이브명으로 조회할 수 있습니다.  </p><p><br><img src="https://support.mcloudoc.com/galleryDocuments/edbsn68b86cb3b88334fda49bb3ab79f2678fe565e6bb6d2571d4f7b44a9f3209431f2351a3647f4939f56fedb3bdce0a1531?inline=true" alt=""></p><p></p><p>개인문서함 파티션 내에 여러 사용자 폴더가 생성됩니다. </p><p>예) ‘개인문서함_본사’이라고 이름을 입력하면 ‘개인문서함_본사(G:)’등과 같이 조회할 수 있습니다. </p><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p>일반 사용자는 관리자가 <strong>시스템 설정 - 설정 홈 연결 - 일반 모듈 설정 - Basic - 문서함 관리 - 문서함 드라이브 문자 관리</strong>에서 지정한 이름으로 개인문서함용 윈도우 탐색기 드라이브명이 설정됩니다.</p></div></td></tr><tr><td><strong>파티션명</strong></td><td></td><td><p>파티션의 이름은 다국어가 가능하지만, 영문 입력을 권장합니다. 파티션이 생성 완료되면 이름을 변경할 수 없고, 한 서버에 중복된 이름은 허용하지 않습니다. 파티션 용도에 따라 다음과 같은 이름을 추천합니다. </p><p></p><ul><li>개인문서함용 파티션명:  home, home2, home3, … </li><li>부서문서함용 파티션명:  orgcowork, orgcowork2, orgcowork3, … </li><li>도메인용 파티션명:  domain, domain2, domain3, … </li><li>(캐시 업데이트 목적) 웹서버 파티션명:  web </li><li>(캐시 업데이트 목적) 부서문서함 파티션명: file </li></ul><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p>파티션 등록이 캐시 업데이트 목적인 경우: 한 서버 주소에 대해 파티션은 한 개만 입력하면 되기 때문에 <strong>web</strong> 또는 <strong>file</strong> 한 개만 이용해도 충분합니다. 파티션명은 어떤 것을 이용해도 상관없지만, 관리의 용이성을 위해 <strong>web</strong> 또는 <strong>file</strong>로 입력할 것을 권장합니다. </p></div><p></p><p>서버 OS별 파티션명 입력방법은 다음과 같습니다.</p><p></p><p><img src="../.gitbook/assets/image (136).png" alt="" data-size="original"></p></td></tr><tr><td><strong>서버 주소</strong></td><td></td><td>파티션을 등록할 서버의 실제 IP주소 또는 DNS명을 직접 입력합니다. 기존에 등록된 서버인 경우에는 목록에서 선택할 수 있습니다.</td></tr><tr><td><strong>서버 위치</strong></td><td></td><td>파티션을 등록할 서버의 지역(Region)을 입력합니다. 기존에 등록된 위치가 있으면 목록에서 선택할 수 있고, 없는 경우에는 직접 입력합니다.</td></tr><tr><td><strong>중요도</strong></td><td></td><td>높음 또는 보통 등으로 지정 가능하며, 중요도에 따른 관리 정책(예: 백업 실행 횟수, 디스크 품질)을 세워 관리할 수 있습니다.</td></tr><tr><td><strong>전체용량</strong></td><td></td><td>파티션이 사용 가능한 전체 용량을 입력합니다. 0 ~ 1,048,576(GB)까지 입력 가능 합니다.</td></tr><tr><td><strong>문서함 수용여부</strong></td><td></td><td>파티션 종류별로 추가 생성 수용여부를 결정합니다.</td></tr><tr><td></td><td><strong>수용함</strong></td><td><ul><li><strong>개인문서함용 파티션</strong>: 사용자 추가 생성 허용 시 선택 </li><li><strong>부서문서함용 파티션</strong>: 부서문서함 추가 생성 허용 시 선택 </li><li><strong>도메인용 파티션</strong>: 추가도메인 추가 생성 허용 시 선택</li></ul></td></tr><tr><td></td><td><strong>수용 안 함</strong></td><td><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p><strong>개인문서함용 파티션</strong>: 다른 개인문서함용 파티션에 사용자를 생성하고 싶은 경우 선택</p></div><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p><strong>부서문서함용 파티션</strong>: 다른 부서문서함용 파티션에 부서문서함을 생성하고 싶은 경우 선택  ,  캐시 업데이트 목적의 부서문서함 파티션 등록인 경우 선택</p></div><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p><strong>도메인용 파티션</strong>: 다른 도메인용 파티션에 추가도메인을 생성하고 싶은 경우 선택</p></div></td></tr></tbody></table>

#### 파티션 삭제하기

1. **일반관리 - 서버 관리**를 클릭합니다.
2. 삭제하고자 하는 서버의 **휴지통**을 클릭합니다.

### <mark style="color:$primary;">파티션 정보 변경하기</mark>

1. **일반관리 - 서버 관리**를 클릭합니다.
2. 전체 목록에서 변경할 서버의 **연필** 아이콘을 클릭합니다.
3. **‘파티션 수정’** 창에서 정보를 변경합니다.

* **용도**\*\*,\*\* **서버 주소**\*\*,\*\* **파티션명**은 변경할 수 없습니다.
* 용도가 개인문서함인 경우 **관리자용 개인문서함 드라이브명**은 변경할 수 있습니다.
* **서버위치**\*\*,\*\* **중요도**\*\*,\*\* **전체 용량**\*\*,\*\* **문서함 수용여부**는 변경할 수 있습니다.

4. **확인**을 클릭합니다.

{% hint style="danger" %}
서버 설정의 변경이나 삭제로 인해서 사용자 문서함이 사라질 수 있으므로 주의해야 합니다.
{% endhint %}
