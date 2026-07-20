# 서비스관리자가 윈도우 탐색기로 문서함 관리하는 방법

서비스관리자는 윈도우 탐색기에서 중앙 문서함 전체를 열람하고 부서문서함 폴더의 관리, 문서 보안 등급 설정, 개인문서함의 용량 설정 등의 문서함 관리 업무를 수행할 수 있습니다.

{% hint style="warning" icon="square-poll-horizontal" %}
서버 설정에 따라 서비스관리자에게 개인문서함 내 폴더/파일 목록 열람이 허용되지 않을 수도 있습니다.
{% endhint %}

### <mark style="color:$primary;">윈도우 탐색기 사용하기</mark>

서비스 관리자가 윈도우 탐색기에서 업무를 수행하기 위해서는 먼저 윈도우 에이전트를 실행해야 합니다. 윈도우 에이전트를 설치, 실행하는 방법은 다음과 같습니다.

1. 홈페이지 우측 상단에서 서비스관리자 이름을 클릭하고 **Agent 실행**을 선택합니다.
2. 설치가 되어 있지 않은 경우 안내 메시지에서 **확인** 버튼을 클릭하여 설치를 진행합니다.
3. 설치 완료 후 다시 **Agent 실행** 메뉴를 선택하여 윈도우 에이전트를 실행합니다.

![](<../.gitbook/assets/img_001 (56).png>)

{% hint style="success" icon="lightbulb-exclamation-on" %}
웹페이지에서 에이전트를 실행한 이후, 다음 번부터는 윈도우에서 직접 에이전트 앱을 실행하고 로그인을 진행할 수 있습니다.
{% endhint %}

{% hint style="warning" icon="square-poll-horizontal" %}
정보보호관리자는 윈도우 에이전트를 사용할 수 없습니다.
{% endhint %}

윈도우 에이전트가 실행되면 다음과 같이 윈도우 탐색기에 중앙문서함의 모든 폴더가 표시됩니다. 관리가 필요한 폴더나 파일에서 마우스 우클릭하여**폴더 관리** 또는 **파일 관리**를 선택하면 문서함 관리를 위한  컨텍스트 메뉴를 사용할 수 있습니다.

![](<../.gitbook/assets/img_004 (32).png>)

### <mark style="color:$primary;">부서문서함 폴더 관리하기</mark>

서비스관리자는 윈도우 탐색기에서 부서문서함 내 임의의 폴더에 대한 권한 설정, 용량 제한 설정, 폴더관리자 지정, 폴더 로그 및 현황 보기 등 부서문서함 폴더 관리 업무를 수행할 수 있습니다.&#x20;

#### 폴더관리자 설정하기

서비스관리자는 부서문서함 내 임의의 폴더에 대해 특정 사용자를 폴더관리자로 지정하여 해당 폴더의 관리 권한을 위임할 수 있습니다.  폴더관리자는 서비스관리자를 대신하여 해당 폴더에 대한 권한 및 용량 제한 설정, 폴더 로그 및 현황 보기, 하위 폴더에 대한 폴더관리자 지정 등의 업무를 수행할 수 있습니다.  폴더관리자의 지정 및 해제를 위해서는 **폴더 관리 - 폴더 관리자 설정**을 선택합니다.

폴더관리자를 설정하는 세부적인 방법은 [**폴더관리자 설정하기**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/undefined-3/undefined-1)를 참고하세요.&#x20;

{% hint style="warning" icon="square-poll-horizontal" %}
**폴더관리자**에 대한 자세한 사항은 [**사용자의 종류와 역할**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/concept/user)을 참고하세요.
{% endhint %}

#### 폴더 권한 설정하기

**폴더 관리 - 권한 설정** 메뉴에서 특정 부서/사용자에 대해 해당 폴더에서의 읽기, 쓰기, 목록보기, 삭제, 파일/폴더 생성 등의 권한을 허용 또는 거부할 수 있습니다.&#x20;

폴더 권한을 설정하는 세부적인 방법은 [**폴더 권한 설정하기**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/undefined-3/undefined-1)를 참고하세요.&#x20;

#### 폴더 용량 제한 설정하기

**폴더 관리 - 용량 제한** 메뉴에서 해당 폴더의 용량을 특정 크기로 제한하도록 설정할 수 있습니다.

폴더 용량 제한을 설정하는 방법은 [**폴더 용량 제한 설정하기**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/undefined-3/undefined-3)를 참고하세요.

#### 폴더 로그 보기

**폴더 관리 - 폴더 로그 보기** 메뉴에서 해당 폴더에서의 업로드, 다운로드, 이동, 삭제, 이름 변경, 폴더/파일 생성 등의 작업 이력을 검색할 수 있습니다.

{% hint style="warning" icon="square-poll-horizontal" %}
폴더 로그의 검색 방법 및 표시 내용은 [**폴더 로그 보기**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/undefined-3/undefined-6)를 참고하세요.&#x20;
{% endhint %}

#### 폴더 용량 제한 현황 보기

**폴더 관리 -** **폴더 용량 제한 현황** 메뉴에서 부서문서함 내 폴더의 용량 제한 현황을 확인할 수 있습니다.

폴더 용량 제한 현황을 확인하는 세부적인 방법은 [**폴더 용량 제한 현황 확인하기**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/undefined-3/undefined-4)를 참고하세요.&#x20;

{% hint style="warning" icon="square-poll-horizontal" %}
웹페이지의 **일반 모듈 관리 -** **Basic - 문서함 관리 - 폴더 용량 관리 - 폴더 용량 현황**에서도 동일한 작업이 가능합니다.  자세한 사항은 [**관리자가 웹에서 폴더 용량 제한 현황 확인하는 방법**](undefined-13/undefined-1.md)을 참고하세요.
{% endhint %}

#### 폴더 권한 설정 현황 보기

**폴더 관리 –** **폴더 권한 설정 현황** 메뉴에서 부서문서함 내 폴더의 권한 설정 현황을 확인할 수 있습니다.

폴더 권한 설정 현황을  확인하는 세부적인 방법은 [**폴더 권한 현황 보기**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/centralfile/undefined-5)를 참고하세요.

#### 자산화 폴더 설정하기

**폴더 관리 –** **자산화 설정/해제** 메뉴에서 부서문서함의 특정 폴더를 자산화 폴더로 설정/해제할 수 있습니다. 자산화 폴더는 파일의 편집/수정이 제한되는 폴더로 자산화 폴더로 설정하면 폴더 내 자료를 회사의 자산으로 보존할 수 있습니다.

자산화 폴더  설정/해제를 위한 세부적인 방법은 [**자산화 폴더 설정하기**](undefined-20/undefined.md)를 참고하세요.

### <mark style="color:$primary;">개인문서함 폴더 용량 설정하기</mark>

서비스관리자는 윈도우 탐색기에서 각 사용자의 개인문서함 용량을 설정할 수 있습니다. 사용자별 개인문서함은 개인문서함 드라이브 내 ‘**사용자이름(사용자ID)**’ 폴더로 표시됩니다.

1. 윈도우 탐색기에서 개인문서함 드라이브를 클릭합니다.
2. 용량을 설정할 사용자의 개인문서함 폴더에서 마우스 우클릭 후 **용량 제한**을 선택합니다.

<div align="left"><figure><img src="../.gitbook/assets/img_008 (18).png" alt="" width="563"><figcaption></figcaption></figure></div>

3. ‘**용량 제한**’ 창에서 **용량 변경** 버튼을 클릭합니다.

<div align="left"><figure><img src="../.gitbook/assets/img_009 (15).png" alt=""><figcaption></figcaption></figure></div>

4. ‘**용량 상세보기**’ 창에서 우측 상단의 **추가**를 클릭하여 새로운 용량 정보를 추가하거나, **연필** 아이콘을 클릭하여 기존 용량을 수정할 수 있습니다.

<div align="left"><img src="../.gitbook/assets/img_010 (12).png" alt=""></div>

5. ‘**수정**’ 창에서 정보를 입력한 후 **확인**을 클릭합니다.

> * **용량**: 추가할 용량을 입력합니다. 용량 단위는 MB입니다.
> * **사용 만료일**: 추가 용량의 사용 기한을 입력합니다.

<div align="left"><img src="../.gitbook/assets/img_011 (9).png" alt=""></div>

{% hint style="warning" icon="square-poll-horizontal" %}
웹페이지의 **일반 관리 - 인사 조직 관리 - 사용자 - 사용자 관리**에서도 동일한 작업이 가능합니다. 자세한 사항은 [**웹에서 사용자의 개인문서함 용량 변경하기**](undefined-5/undefined-1.md)를 참고하세요.
{% endhint %}

### <mark style="color:$primary;">문서보안등급 설정하기</mark>

서비스관리자 및 폴더관리자는 윈도우 탐색기에서 파일이나 폴더 단위로 문서보안등급을 설정할 수 있습니다.&#x20;

문서 보안등급을 설정하는 방법은 [**문서 보안등급 설정하기**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/undefined-4/undefined/undefined-2)를 참고하세요.

### <mark style="color:$primary;">문서 보존 기한 설정하기</mark>

서비스관리자 및 폴더관리자는 윈도우 탐색기에서 파일이나 폴더 단위로 문서 보존 기한을 설정할 수 있습니다.&#x20;

문서 보존 기한을 설정하는 방법은 [**문서 보존 기한 설정하기**](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/undefined-4/undefined-1/undefined-2)를 참고하세요.
