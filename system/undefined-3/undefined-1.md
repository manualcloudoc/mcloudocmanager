# 덤프 취득 및 분석 방법

​\
응용 프로그램이 비정상적으로 동작하거나 시스템 오류(예: 블루스크린)가 발생한 경우 이에 대한 원인 분석을 위한 덤프 취득 및 분석 방법을 설명합니다.

## **커널 영역과 사용자 영역**

윈도우 운영체제는 운영체제 보호 목적으로 메모리를 커널 영역과 사용자 영역으로 구분하여 관리합니다.

<div align="left"><img src="../../.gitbook/assets/img_000 (226).png" alt="" width="397"></div>

<table><thead><tr><th width="171">구분</th><th>설명</th></tr></thead><tbody><tr><td>사용자 영역</td><td><p>일반 응용 프로그램이 실행되는 영역. </p><p>  예) PlusDrive.exe, Excel.exe, Powerppt.exe 등 동작 </p><p>일반 응용 프로그램(사용자 모듈)은 <strong>사용자 모드</strong>에서 동작. </p><p>커널 영역 메모리에 접근할 수 없음. </p><p>따라서, 커널 작업이 필요할 때 시스템 콜 사용해야 함.</p></td></tr><tr><td>커널 영역</td><td><p>파일 시스템, 하드웨어 제어 디바이스 드라이버 등과 같이 운영체제가 실행되는 영역예) PlusFsd.sys, Plusfsfd.sys, usbstor.sys 등 동작 </p><p>커널 모듈은 커널 영역에 위치하며 <strong>커널 모드</strong>로 동작. </p><p>커널 모듈은 커널 영역과 사용자 영역 메모리 모두 접근 가능.</p></td></tr></tbody></table>

사용자 영역에서 동작하는 응용 프로그램들은 운영체제에 의해 엄격히 구분되어 보호됩니다. 따라서, 특정 응용 프로그램에 문제 발생 시 다른 응용 프로그램에 영향을 거의 주지 않습니다.

그러나, 커널 영역에서 동작하는 실행 모듈들은 상호 참조가 가능하여 특정 모듈에서 문제 발생 시 전체 시스템 크래시(블루스크린)로 이어집니다.

### <mark style="color:$primary;">**덤프 종류**</mark>

덤프는 크게 **사용자모드 덤프**와 **커널모드 덤프**로 나눌 수 있습니다.

사용자모드 덤프는 응용 프로그램 실행 정보를 기록하고 있으며, 응용 프로그램이 예기치 않게 종료되거나 멈출(hang) 때 취득합니다. 반면, 커널모드 덤프는 윈도우 시스템(OS) 실행 정보를 기록하고 있으며, 일반적으로 블루스크린이 발생하거나 시스템이 멈출 때 취득합니다.

아래는 모드별 덤프 종류에 대한 설명입니다.

<table><thead><tr><th width="98">분류</th><th width="204">덤프 종류</th><th>설명</th></tr></thead><tbody><tr><td>사용자모드</td><td>전체 덤프</td><td>해당 프로세스 전체 메모리, 실행 파일 이미지, 핸들 테이블 등 덤프 생성 시 메모리 상황을 파악하는 데 필요한 덤프. 제공되는 정보가 고정되어 있음.</td></tr><tr><td></td><td>미니 덤프</td><td>기본적으로 증상 해결에 필요한 최소한의 정보를 제공하나, 옵션에 따라 정보를 추가할 수 있음. 추가한 옵션에 따라 전체 덤프보다 더 많은 정보를 저장</td></tr><tr><td>커널모드</td><td>작은 메모리 덤프</td><td>필요한 크래시 덤프 정보만 기록한 덤프</td></tr><tr><td></td><td>커널 메모리 덤프 (권장)</td><td>커널 메모리 정보를 기록한 덤프</td></tr><tr><td></td><td>전체 메모리 덤프</td><td>실행 중인 프로세스 정보 포함하여 시스템 메모리의 모든 내용을 기록한 덤프</td></tr><tr><td></td><td>자동 메모리 덤프</td><td>커널 메모리 덤프와 동일하나, 커널 메모리 정보를 기록하기 위한 페이지 파일(pagefile.sys)의 크기를 자동으로 최적화한다.</td></tr><tr><td></td><td>활성화된 메모리 덤프</td><td>전체 메모리 덤프와 비슷하지만, 분석에 불필요한 정보를 필터링하여 기록하여 전체 메모리 덤프보다 덤프 파일 크기가 작음</td></tr></tbody></table>

### <mark style="color:$primary;">**덤프 생성 방법**</mark>

커널모드와 사용자모드 덤프 파일 생성을 위한 여러 방법이 있습니다.

#### 1)   응용 프로그램 덤프 자동 생성

응용 프로그램 실행 중 오류가 발생하면 덤프 파일을 자동 생성하도록 레지스트리에 미리 설정해야 합니다.

1. 레지스트리 편집기(regedit.exe)를 실행합니다.
2. 아래 키 위치에 덤프 생성 정보를 설정합니다.

> 키:  HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Windows\Windows Error Reporting\LocalDumps

| 이름             | 종류              | 설명                                    | 기본 값                      |
| -------------- | --------------- | ------------------------------------- | ------------------------- |
| **DumpFolder** | REG\_EXPAND\_SZ | 덤프 파일이 생성되는 경로                        | %LOCALAPPDATA%\CrashDumps |
| **DumpCount**  | REG\_DWORD      | 덤프 파일 생성 최대 개수                        | 10                        |
| **DumpType**   | REG\_DWORD      | 생성할 덤프 타입 0: 커스텀 덤프 1: 미니 덤프 2: 전체 덤프 | 1                         |

3. 응용 프로그램 비정상 종료 시 덤프 파일이 자동 생성됩니다.

#### 2)   실행 중인 응용 프로그램 덤프 수동 생성

응용 프로그램 실행 중 멈춤 현상이 발생할 때 해당 프로그램 덤프 파일을 생성하는 일반적인 방법입니다.

1. 작업 관리자(taskmgr.exe) 실행합니다.
2. **세부 정보** 탭으로 이동 후 덤프 생성할 프로세스를 선택합니다.
3. 마우스 우클릭하여 표시된 컨텍스트 메뉴에서 **덤프 파일 만들기** 항목을 선택합니다.

<div align="left"><img src="../../.gitbook/assets/img_001 (179).png" alt="" width="440"></div>

#### 3)   Windbg를 통한 덤프 수동 생성

응용 프로그램 실행 초기 오류 발생하여 강제 종료되는 경우 작업관리자를 통한 덤프 취득이 안됩니다. 이 경우 Windbg 프로그램을 통해 덤프 취득이 가능합니다.

1. Windbg를 실행 후 **File** 메뉴의 **Open Executable…** 메뉴를 선택합니다.
2. 덤프를 취득할 실행 프로그램을 선택합니다. 실행 옵션이 필요한 경우 **Arguments**를 입력합니다.

![](<../../.gitbook/assets/img_002 (149).png>)

3. 응용 프로그램 실행과 동시에 Windbg가 제어권을 가지며 실행이 중단됩니다.

![](<../../.gitbook/assets/img_003 (129).png>)

4. Windbg의 **Debug** 메뉴의 **Go** 메뉴를 선택합니다. 중단된 응용 프로그램이 계속 실행됩니다.
5. 실행 중 예외(Exception)가 발생하면 Windbg가 제어권을 가집니다. 알려진 예외이면 계속 진행하고, 그렇지 않으면 아래 명령어를 입력하여 덤프 파일 생성합니다.

> .dump  /ma  <파일경로>     (dump 앞에 점(.)이 있음에 주의)

![](<../../.gitbook/assets/img_004 (101).png>)

#### 4)   커널모드 덤프 설정 후 자동 생성

먼저 덤프 관련 설정 후 블루스크린 발생 시 덤프 파일이 자동으로 생성됩니다.

* 커널 덤프 설정 방법

> - **시작메뉴**, **설정**, **고급 시스템 설정**을 누릅니다.
> - **시작 및 복구** 의 **설정** 버튼을 누릅니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_005 (86).png" alt="" width="375"><figcaption></figcaption></figure></div>

> * **시스템 오류**에서 설정한 후 **확인**을 누릅니다. 덤프 파일 종류는 **커널 메모리 덤프**를 권장합니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_006 (74).png" alt="" width="372"><figcaption></figcaption></figure></div>

> 사용 중 시스템 크래시 발생 시 설정된 위치에 덤프 파일이 자동 생성됩니다. 단, 덤프 생성 완료되기 전에 컴퓨터를 강제 종료하면 덤프가 생성되지 않을 수 있습니다.  덤프 파일 크기가 큰 관계로 압축 후 당사에 보내주시면 됩니다.

<div align="left"><figure><img src="../../.gitbook/assets/img_007 (62).png" alt="" width="375"><figcaption></figcaption></figure></div>

#### 5)   강제 블루스크린 발생하여 커널모드 덤프 생성

커널 작업 수행 중 멈춤 현상이 발생한 경우 덤프 파일 생성이 안 될 수 있습니다. 이런 상황에서 강제 블루스크린을 발생하여 덤프 취득할 수 있습니다.

**프로그램 실행할 수 있는 상태인 경우**

1. NotMyFault.exe 툴 실행합니다.

> 다운로드 경로 : [https://docs.microsoft.com/en-us/sysinternals/downloads/notmyfault](https://docs.microsoft.com/en-us/sysinternals/downloads/notmyfault)

2. **Crash** 버튼을 클릭하면 블루스크린이 발생합니다.

<div align="left"><img src="../../.gitbook/assets/img_008 (56).png" alt="" width="466"></div>

**프로그램 실행할 수 없는 상태인 경우**

키보드를 통한 강제 블루스크린 방법을 사용합니다.

1. 레지스트리 편집기(regedit.exe)를 실행합니다.
2. 키보드 연결 타입에 따라 아래 레지스트리 값을 설정합니다.

<table data-search="false"><thead><tr><th width="134">키보드 종류</th><th width="94"></th><th width="113"></th><th>레지스트리 정보</th></tr></thead><tbody><tr><td><strong>PS/2 키보드</strong></td><td>키</td><td></td><td>HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services \i8042prt\Parameters</td></tr><tr><td></td><td>값</td><td>이름</td><td>CrashOnCtrlScroll</td></tr><tr><td></td><td></td><td>종류</td><td>REG_DWORD</td></tr><tr><td></td><td></td><td>데이터</td><td>1</td></tr><tr><td><strong>USB 키보드</strong></td><td>키</td><td></td><td>HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services \kbdhid\Parameters</td></tr><tr><td></td><td>값</td><td>이름</td><td>CrashOnCtrlScroll</td></tr><tr><td></td><td></td><td>종류</td><td>REG_DWORD</td></tr><tr><td></td><td></td><td>데이터</td><td>1</td></tr><tr><td><strong>Hyper-V 키보드</strong></td><td>키</td><td></td><td>HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services \hyperkbd\Parameters</td></tr><tr><td></td><td>값</td><td>이름</td><td>CrashOnCtrlScroll</td></tr><tr><td></td><td></td><td>종류</td><td>REG_DWORD</td></tr><tr><td></td><td></td><td>데이터</td><td>1</td></tr></tbody></table>

3. 시스템을 재시작하여 설정을 적용합니다.
4. 강제 블루스크린이 필요한 상황에서 우측 Ctrl 키 누른 상태에서 Scroll Lock 키 두 번 누르면 블루스크린이 발생합니다.

### <mark style="color:$primary;">**WinDbg를 통한 덤프 분석**</mark>

생성된 덤프 파일을 분석하기 위한 도구로 WinDbg를 주로 사용합니다. 커널모드 덤프나 사용자모드 덤프나 분석 방법은 거의 유사합니다.

덤프 분석 시 자주 사용하는 WinDbg 명령어는 아래와 같습니다.

<table><thead><tr><th width="165">명령어</th><th>설명</th></tr></thead><tbody><tr><td><strong>!analyze -v</strong></td><td>덤프 생성 당시 예외(Exception) 또는 BugCheck에 대한 자세한 정보 출력.</td></tr><tr><td><strong>!analyze -hang</strong></td><td>덤프 생성 당시 멈춤(hang) 관련 정보를 분석하여 출력.</td></tr><tr><td><strong>k</strong></td><td>현재 활성화된 스레드의 스택 프레임(콜스택) 정보를 출력.</td></tr><tr><td><strong>lmvm [패턴]</strong></td><td>주어진 패턴과 일치하는 모든 모듈의 상세 정보를 출력. 예) lmvm plus* (plus로 시작하는 모든 모듈 정보 표시)</td></tr><tr><td><strong>lm</strong></td><td>활성화된 모든 모듈 정보를 출력한다.</td></tr></tbody></table>

분석 절차는 아래와 같습니다.

1. &#x20;WinDbg를 실행한 후 **File** 메뉴의 **Open Crash Dump…** 메뉴를 통해 덤프 파일을 읽는다.
2. Command 창에 명령어 !analyze –v 입력하여 분석 시작합니다.

<figure><img src="../../.gitbook/assets/img_009 (47).png" alt=""><figcaption></figcaption></figure>

3. 일반적으로 예외 발생 모듈 이름이 표시됩니다.

![](<../../.gitbook/assets/img_010 (41).png>)

4. k 명령어를 통해 스택 프레임(콜스택) 정보를 확인하여 검증합니다. 목록 상단이 최근 호출 정보입니다. 목록 상단부터 예외를 발생하는 모듈을 찾습니다. 이때, ntdll, KERNELBASE, kernel32 등 과 같은 MS에서 배포한 운영체제 모듈은 예외로 합니다.

![](<../../.gitbook/assets/img_011 (33).png>)

5. lmvm \*<\*_모듈명>_  명령어로 입력하여 모듈과 연관된 제품 및 회사 정보를 찾습니다

![](<../../.gitbook/assets/img_012 (30).png>)

6. 예외 발생 모듈이 당사에서 배포한 모듈인 경우 덤프 파일을 보내주시기 바랍니다.

사용자모드 모듈: $Program Files\NetID\PlusDrive 경로를 가지는 모든 모듈

커널모드 모듈:  모듈 이름이 아래 목록에 포함된 모듈

* PlusFsd.sys
* PlusFsfd.sys
* npSecureDisk.sys
* npNwlock.sys
* npMtpFlt.sys
* npRepFlt.sys

### <mark style="color:$primary;">**Verifier**</mark>

WinDbg로 커널모드 덤프 분석 시 예외 발생 모듈 이름이 “memory corruption”으로 표시될 수 있습니다. 이는 메모리 손상이 누적된 상황에서 예외가 발생한 것으로 모듈 이름을 특정하기 어렵습니다.

![](<../../.gitbook/assets/img_013 (23).png>)

커널 메모리 손상은 커널 영역에서 동작하는 모든 모듈 동작에 악영향을 줍니다. 이때 시스템 메모리를 손상시키는 모듈을 먼저 찾아야 합니다. verifier.exe를 사용하면 커널 모듈 동작을 검사하고 모니터링하여 이러한 모듈을 찾을 수 있습니다. 해당 프로그램은 운영 체제 설치 시 자동 배포됩니다.

모니터링 절차는 아래와 같습니다.

1. 윈도우 시작메뉴 명령 창에서 verifier.exe를 실행합니다.
2. **표준 설정 만들기** 또는 **사용자 지정 설정 만들기**를 선택합니다.

<div align="left"><img src="../../.gitbook/assets/img_014 (19).png" alt="" width="563"></div>

3. 메모리 손상 모듈을 찾기 위해 **특수 풀**과 **풀 추적**을 필수 체크합니다. 테스트 유형을 많이 체크할수록 시스템 성능이 저하됩니다. 앞에서 **표준 설정 만들기**를 선택한 경우 **플래그 유형**이 **표준**인 항목들이 자동 체크됩니다.

<div align="left"><img src="../../.gitbook/assets/img_015 (18).png" alt="" width="563"></div>

4. **드라이버 이름을 목록에서 선택**을 선택합니다

<div align="left"><img src="../../.gitbook/assets/img_016 (18).png" alt="" width="563"></div>

5. 최근에 설치되었거나 의심되는 모듈을 선택합니다. 모듈을 많이 선택할수록 시스템 성능이 느려집니다.

<img src="../../.gitbook/assets/img_017 (14).png" alt="" width="563">

6. 설정을 저장하기 위해 **마침**을 누르고 시스템을 재시작합니다.
7. 시스템 재시작 후 선택한 모듈 작업 진행 시 선택한 테스트 항목이 자동 검사됩니다. 검사 과정에서 실패되면 블루스크린이 발생하고 설정한 덤프 파일이 생성됩니다.
8. 위 검사 및 모니터링은 사용자가 설정 삭제할 때까지 계속 유지됩니다. 문제가 해결되면 시스템 성능을 위해 verifier.exe를 실행 후 설정을 삭제합니다.

<div align="left"><img src="../../.gitbook/assets/img_018 (11).png" alt="" width="563"></div>

### <mark style="color:$primary;">**분석 요청 시 필요 정보**</mark>

덤프 분석 요청 시 덤프 파일과 함께 보내주시면 좋은 정보들입니다.

* 덤프 파일 (용량이 크면 압축 필요)
* 운영체제 버전과 플랫폼 정보 (예: Windows 10, 64비트)
* 설치된 에이전트 버전과 커널 모듈 정보 (트레이 메뉴 **프로그램 정보** 화면 캡처)

![](<../../.gitbook/assets/img_019 (12).png>)

* 증상 발생 시 수행한 상세 작업 내용
* 최근 시스템에 반영된 변경 사항(업데이트 내용)
