# 웹서버 캐시 종류 및 갱신 방법

문서중앙화 서버는 데이터베이스 부하를 줄이고 사용자에게 빠른 서비스를 제공하기 위하여 데이터베이스 내용을 파일 캐시로 만들어 이용합니다. 여기서는 웹서버에 저장되는 캐시 종류 및 갱신 방법을 설명합니다. 모든 웹서버는 동일한 내용의 캐시 파일을 관리합니다.

{% hint style="warning" icon="square-poll-horizontal" %}
문서중앙화의 또 다른 캐시인 파일서버 캐시에 대한 설명은 [**파일서버 캐시 종류 및 갱신 방법**](undefined-1.md)을 참고하세요.
{% endhint %}

웹서버 캐시에는 윈도우 보안정책 캐시가 있습니다. 윈도우 PC에서는 2분 주기로 웹서버에 윈도우 보안정책을 요청합니다. 이 때 웹서버는 윈도우 보안정책 캐시를 확인하여 사용자에게 **전체 정책** 또는 **변경된 정책** 정보를 전달합니다

모든 경로는 리눅스 기준으로 명시하였습니다. 윈도 서버인 경우에는 C: 드라이브 하위의 동일 경로입니다.

### <mark style="color:$primary;">윈도우 보안정책 캐시</mark>

#### 캐시 파일

다음은 윈도우 보안정책 캐시별 파일 경로 및 업데이트 주기입니다. 랜덤파일명인 경우 파일이 여러 개면 최근 생성한 파일을 사용합니다.

<table data-search="false"><thead><tr><th width="194">캐시 종류</th><th width="290">파일 경로</th><th>업데이트 주기</th></tr></thead><tbody><tr><td><strong>Application Seed</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /<strong>app_seed</strong>/cache/랜덤파일명</td><td><ul><li>배치 스케줄 시간</li></ul></td></tr><tr><td><strong>Application Category</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /<strong>category</strong>/all_category/cache/랜덤파일명</td><td><ul><li>배치 스케줄 시간</li></ul></td></tr><tr><td></td><td><p>/plusdrive/policy_cache/{도메인아이디}</p><p>/<strong>category</strong>/changed_category/{CategoryID}/랜덤파일명</p></td><td><ul><li>카테고리 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>DiskLock 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/<strong>disklock</strong>/cache/{PolicyID}/랜덤파일명</td><td><ul><li>배치 스케줄 시간 </li><li>정책 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>반출 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/<strong>export</strong>/cache/{사용자ID}/랜덤파일명</td><td><ul><li>배치 스케줄 시간 </li><li>반출 완료 시 실시간 갱신</li></ul></td></tr><tr><td><strong>URL 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/<strong>url</strong>/cache/{PolicyID}/랜덤파일명</td><td><ul><li>배치 스케줄 시간 </li><li>정책 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>탐색기 복사/이동 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/<strong>shell</strong>/cache/{PolicyID}/랜덤파일명</td><td><ul><li>배치 스케줄 시간 </li><li>정책 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>화면 캡쳐 금지 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/<strong>capture</strong>/cache/{PolicyID}/ 랜덤파일명</td><td><ul><li>배치 스케줄 시간 </li><li>정책 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>클립보드 복사 제어 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/<strong>clpbd</strong>/cache/{PolicyID}/랜덤파일명</td><td><ul><li>∙배치 스케줄 시간 </li><li>정책 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>인쇄제어 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/<strong>print</strong>/cache/{PolicyID}/랜덤파일명</td><td><ul><li>배치 스케줄 시간 </li><li>정책 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>임시폴더 보호 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/<strong>temp</strong>/cache/{PolicyID}/랜덤파일명</td><td><ul><li>배치 스케줄 시간 </li><li>정책 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>네트워크락 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/<strong>networklock</strong>/cache/{PolicyID}/랜덤파일명</td><td><ul><li>배치 스케줄 시간 </li><li>정책 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>IP대역 정책</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /policies3/ip/<strong>cache</strong>/{PolicyID}/랜덤파일명</td><td><ul><li>배치 스케줄 시간 </li><li>정책 변경 시 실시간 갱신</li></ul></td></tr><tr><td><strong>사용자 부서 정보</strong></td><td>/plusdrive/policy_cache/{도메인아이디} /group/group_cache/{사용자ID}</td><td><ul><li>사용자가 정보요청 시 캐시 파일이 24시간 경과되었으면 갱신</li></ul></td></tr></tbody></table>

#### 캐시 파일 갱신 방법

윈도우 보안정책 캐시 갱신은 **정기적 갱신**과 **실시간 갱신** 방법이 있습니다.

<mark style="color:$primary;">**정기적 갱신**</mark>

프로그램을 등록하여 정해진 시간마다 프로그램을 실행시켜 캐시를 갱신합니다. 웹서버별로 각 스케줄에 등록되어 있습니다. 전체 윈도우 보안정책 캐시를 최신 상태로 갱신합니다. 필요한 경우 수동으로 실행할 수 있습니다.

캐시 갱신 배치 프로그램 경로 및 기본 배치 실행 시간은 다음과 같습니다.

| 배치 프로그램 경로                                                                  | 기본 배치 실행 시간 |
| --------------------------------------------------------------------------- | ----------- |
| /plusdrive/web/batch/websvr/disklock\_policy\_cache/DiskLockPolicyCache2.sh | 매일 0시 5분    |

<mark style="color:$primary;">**실시간 갱신**</mark>

이벤트가 발생 때 마다 실시간으로 캐시를 갱신합니다. 갱신 절차는 다음과 같습니다.

1. 관리자가 관리자 툴에서 정책을 변경하면 웹서버로 변경 정보를 전달합니다.
2. 변경 정보를 수신한 웹서버는 DB정보를 업데이트하고, 변경된 정책 캐시 파일만 갱신합니다.
3. 이후 웹서버는 다른 웹서버들에게도 캐시 갱신을 요청합니다.
4. 캐시 갱신 요청을 받은 다른 웹서버들도 해당 정책 캐시 파일을 최신 상태로 갱신합니다.

![](<../../.gitbook/assets/img_001 (183).png>)
