# BackupDoc(백업독) 소개

​\
BackupDoc은 외부의 공격이나 부주의로 인한 데이터 손실을 막기 위해 원본 서버의 중요 데이터를 백업 서버에 스냅샷 형태로 보관하는 백업 솔루션으로 별도 구매가 필요한 제품입니다. BackupDoc을 사용하면 증분 백업을 통해 저장 공간을 효율적으로 활용할 수 있으며, 다양한 관리 기능을 활용한 간편하고 안정적인 백업이 가능합니다.

### <mark style="color:$primary;">BackupDoc 특징</mark>

#### **증분 백업 방식**

최초 백업(풀 백업) 이후에는 변경된 부분만 백업(증분 백업)하는 방식으로, 원하는 횟수만큼 해당 시점의 스토리지 스냅샷을 생성하여 보관합니다. 전체 데이터를 복제하지 않기 때문에 스냅샷 생성 및 데이터 복원에 소요되는 시간이 단축되며 용량 역시 증분 백업만큼만 증가하므로, 시스템 자원을 효율적으로 사용할 수 있습니다.

![](<../../.gitbook/assets/img_000 (11).png>)

#### **맞춤 백업 스케줄 설정**

고객사의 환경에 맞는 백업 스케줄을 간편하게 설정하고 관리할 수 있습니다. 백업할 원본 서버가 여러 대인 경우, 서버별로 적합한 백업 일정을 설정할 수 있으며, 하나의 원본 서버 내에서도 백업할 경로에 따라 백업 일정을 개별적으로 설정할 수 있습니다.

![](<../../.gitbook/assets/img_001 (3).png>)

#### **백업 탐색기**

백업 탐색기에서 서버별, 백업 스케줄별로 백업된 파일/폴더의 목록을 일목요연하게 확인하고, 복구가 필요한 파일/폴더를 간편하게 다운로드할 수 있습니다. 또한, 백업 내용을 스냅샷 단위로 삭제할 수 있습니다.

![](<../../.gitbook/assets/img_002 (3).png>)

#### 백업 로그 및 모니터링

백업 로그, 전송량, 백업 장비 상태 등을 직관적으로 한눈에 확인할 수 있어 즉각적인 조치가 가능합니다.\
![](<../../.gitbook/assets/img_003 (1).png>)

### <mark style="color:$primary;">BackupDoc 도입 유형</mark>

고객사의 필요에 따라 BackupDoc을 **사내 구축형** 또는 **클라우드형**으로 도입할 수 있으며, 문서중앙화 서비스를 사용하지 않을 경우에도 BackupDoc만 별도로(stand-alone) 사용이 가능합니다.

* **BackupDoc**: 고객사에 백업 서버를 직접 설치하여 백업하는 **구축형** 백업 솔루션
* **BackupDoc.biz**: 백업 서버를 구축하지 않은 고객사에서도 원격 데이터센터로 백업이 가능한 **클라우드형** 백업 솔루션

원본 서버를 백업하기 위해서는 백업독 에이전트가 필요합니다. 원본 서버가 문서중앙화 서버일 경우에는 에이전트가 내장되어 있으며, 그 외 일반 서버(윈도우, 리눅스, NAS 파일 서버 등)일 경우에는 별도로 에이전트 설치가 필요합니다.

다음 그림은 각각 구축형, 클라우드형으로 도입할 경우의 시스템 구성 사례입니다.

<div data-with-frame="true"><figure><img src="../../.gitbook/assets/img_004 (3).png" alt=""><figcaption></figcaption></figure></div>

<div data-with-frame="true"><figure><img src="../../.gitbook/assets/img_005 (3).png" alt=""><figcaption></figcaption></figure></div>

구축형으로 도입 시, 고객사의 환경에 따라 다음과 같은 다양한 시스템 구성이 가능합니다. 다중 스토리지 또는 다중 백업 서버로 구성할 경우, 원본 서버별(계열사별)로 백업관리자 계정을 별도로 두어 독립적으로 백업을 관리하도록 할 수 있습니다. 백업관리자의 역할은 [**BackupDoc 관리자의 종류와 역할**](backupdoc-1.md)​​를 참고합니다.&#x20;

#### 단일 원본 서버, 단일 백업 서버

<div data-with-frame="true"><figure><img src="../../.gitbook/assets/img_006 (3).png" alt=""><figcaption></figcaption></figure></div>

#### &#x20;다중 원본 서버, 단일 백업 서버(스토리지 한 개)

이 경우, 복수의 원본 서버를 하나의 백업관리자 계정으로 관리합니다.

<div data-with-frame="true"><figure><img src="../../.gitbook/assets/img_007 (2).png" alt=""><figcaption></figcaption></figure></div>

#### &#x20;**다중 원본 서버**, **단일 백업 서버(스토리지 두 개 이상)** ​

<div data-with-frame="true"><figure><img src="../../.gitbook/assets/img_008 (1).png" alt=""><figcaption></figcaption></figure></div>

#### 다중 원본 서버, 다중 백업 서버

<div data-with-frame="true"><figure><img src="../../.gitbook/assets/img_009 (1).png" alt=""><figcaption></figcaption></figure></div>
