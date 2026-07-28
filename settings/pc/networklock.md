# NetworkLock 설정

{% hint style="info" %}
메뉴 경로: 시스템 설정 - 설정 홈 연결 - PC 보안 모듈 설정 - NetworkLock
{% endhint %}

개인 PC의 망을 내부망(업무망)과 외부망(인터넷망)으로 분리하여 사용하도록 설정하는 방법입니다.

<table><thead><tr><th width="222">NetworkLock 옵션</th><th width="358">내용</th><th>기본값</th></tr></thead><tbody><tr><td><strong>NetWorkLock 사용 여부</strong></td><td>개인 PC의 망을 내부망(업무망)과 외부망(인터넷망)으로 분리하여 사용하도록 설정합니다.</td><td>사용 안 함</td></tr><tr><td><strong>예외 IP목록</strong></td><td>망모드에 관계없이 기본적으로 통신을 허용할 IP를 등록할 수 있습니다.</td><td></td></tr><tr><td><strong>망 전환 위젯 표시</strong></td><td><p>망 전환을 위한 위젯을 표시하는 영역을 설정합니다.</p><p></p><ul><li><strong>활성</strong>: 위젯을 사용자 PC 화면 오른쪽 중간 부분에 표시합니다.</li><li><strong>비활성</strong>: 작업줄에 표시합니다. 단, 윈도우11부터는 작업줄에 표시를 지원하지 않아 표시할 수 없습니다.</li></ul></td><td>활성</td></tr><tr><td><strong>로그인 시 자동 내부망 전환 여부</strong></td><td><p>로그인 시 내부망으로 자동 전환되도록 설정할 수 있습니다.</p><p></p><ul><li><strong>내부망 전환</strong></li><li><strong>외부망 유지</strong></li></ul></td><td>외부망 유지</td></tr><tr><td><strong>외부망 모드 전환 시 반드시 종료해야 할 프로세스 목록</strong></td><td><p>사용자가 내부망에서 외부망으로 네트워크를 전환할 때,  등록된 프로세스들이 모두 종료된 후에만 외부망 전환이 가능합니다.</p><p></p><p>예) notepad.exe, winword.exe, wordpad.exe</p></td><td></td></tr><tr><td><strong>문서중앙화 접근 프로세스 종료 여부</strong></td><td>외부망 모드 전환 시 파일에 대해 액세스가 일어난 모든 프로그램을 종료합니다.</td><td>사용함</td></tr></tbody></table>

사용자가 내부망에서 외부망으로 네트워크를 전환할 때, 등록된 프로세스들이 모두 종료된 후에만 외부망 전환이 가능합니다
