# 웹 브라우저에서 다운로드 오류 해결 방법 - 바이러스 검사 실패 case

#### 문제

\
웹 브라우저를 통해 중앙문서함으로 파일 다운로드 시 바이러스 검사 실패로 인해 다운로드가 안되는 경우입니다. <br>

![](https://support.mcloudoc.com/galleryDocuments/edbsn223b335716c1a197d3854bd5fd8e75a7fe6d2ee75d37bb5945a9ab01681aa3b01c65a8f4eabb7badacd11ce8960be6b7?inline=true)\
\
![Notes](https://static.zohocdn.com/zoho-desk-editor/static/images/file.png/)위 그림의 예는 엣지(Microsoft Edge) 브라우저에서 파일 다운로드 시 Microsoft Defender를 사용한 바이러스 검사가 실패한 경우입니다.  사용하는 브라우저와 백신 프로그램에 따라 ‘바이러스 검사 실패’ 안내가 표시되지 않을 수도 있습니다.

#### 원인  <a href="#id-1" id="id-1"></a>

웹 브라우저에서 파일 다운로드 시 바이러스 검사를 하기 위해서는 백신 프로그램을 구동할 권한이 있어야 합니다. 사용하는 브라우저 애플리케이션이 백신 프로그램 구동을 위해 필요한 파일들에 대한 입출력 권한(주로 dll 파일에 대한 읽기 권한)을 충분히 보유하지 않은 경우 위와 같은 문제가 발생할 수 있습니다.<br>

#### 해결 방법  <a href="#id" id="id"></a>

사용자에게 적용된 로컬저장금지 정책에 위와 같은 권한을 허용하는 정책 아이템(위 그림의 예에서는 엣지 브라우저에 Microsoft Defender dll 파일에 대한 읽기 권한을 허용하는 정책 아이템)을 추가하여 문제를 해결할 수 있습니다.

DiskLock 콘솔의 정책 서포트 기능을 사용하면 다음과 같이 문제의 원인을 확인하고, 필요한 정책 아이템을 구성하여 정책에 추가할 수 있습니다.

![Notes](https://static.zohocdn.com/zoho-desk-editor/static/images/file.png/)정책 서포트 기능의 내용 및 자세한 화면 설명은 [DiskLock 콘솔에서 정책 서포트 기능 사용하기](https://support.mcloudoc.com/portal/ko/kb/articles/disklock-%EC%BD%98%EC%86%94%EC%97%90%EC%84%9C-%EC%A0%95%EC%B1%85-%EC%84%9C%ED%8F%AC%ED%8A%B8-%EA%B8%B0%EB%8A%A5-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0)를 참고합니다. \
1\.   DiskLock 콘솔에서 로컬저장금지 정책 – 정책 관리를 클릭합니다.\
\
2\.   좌측 정책 목록에서 현재 사용자 PC에서 사용 중인 로컬저장금지 정책을 선택합니다. 사용 중인 정책은 정책명 앞의 ![](https://support.mcloudoc.com/galleryDocuments/edbsn5dd9e607b8850536a82b215b51ffc1d0191782258f248a7abfd8ae36f8166b4e41bed264801a5d7149b15bd411300fc0?inline=true)표시로 식별할 수 있습니다.\
\
3\.   우측 상단 정책 아이템 메뉴의 정책 서포트를 클릭합니다.\
4\.   정책 서포트 창에서 모니터링 시작 버튼을 클릭하여 파일 입출력 거부 로그 모니터링을 시작합니다.\
5\.   오류가 발생했던 작업을 다시 수행합니다. 본 예시에서는 엣지 브라우저를 사용하여 웹사이트에서 중앙문서함으로 파일 다운로드를 시도합니다.\
6\.   오류가 발생한 후에는 정책 서포트 창에서 모니터링 중지 버튼을 클릭한 후, 파일 입출력 거부 로그를 확인합니다.\
7\.   수집된 파일 입출력 거부 로그를 검토하여 오류의 원인으로 추정되는 로그를 식별합니다. 주로 사용하는 백신 프로그램 폴더 내 dll 파일(예: “C:\Program Files\AhnLab\Safe Transaction\RunTmp \nzbrcom.dll”)에 대한 읽기 차단이 원인이 됩니다.  \
본 예시에서는 msedge.exe 프로세스에 대해 Microsoft Defender 프로그램 경로 내 MpOav.dll 파일의 입출력이 차단된 것을 확인할 수 있습니다. \
\
![Idea](https://static.zohocdn.com/zoho-desk-editor/static/images/lights.png/)필요 시 컨텍스트 메뉴의 차단한 정책 아이템 보기를 클릭하여 특정 로그에 적용된 차단 정책 아이템을 확인할 수 있습니다\
![](https://support.mcloudoc.com/galleryDocuments/edbsn4229ea234bf7389442a65d02d14bab197e3d9660adec210bd78ad9cd34f586ea652ed12556e2ba866e16daf2fe6ef1a8?inline=true)\
\
8\.   해결이 필요한 로그(위의 그림에서는 MpOav.dll 차단 로그)를 선택한 후, 선택 로그 정책 아이템 추가 버튼을 클릭합니다.

9\.   해당 프로세스가 소속된 애플리케이션 카테고리가 두 개 이상인 경우 다음과 같이 애플리케이션 카테고리 선택 창이 팝업됩니다. 이 경우, 생성할 정책 아이템에 적합한 카테고리를 선택한 후 확인을 클릭합니다. 프로세스가 소속된 애플리케이션 카테고리가 한 개인 경우에는 이 단계 없이 곧바로 ‘정책 아이템 추가’ 창이 표시됩니다.

![](https://support.mcloudoc.com/galleryDocuments/edbsnf8e7ff7034d4e079182605ef75d600f9333e4f873ee739409beaa48116559502c1add66f31ff9a81e3ee74ea1cd0c389?inline=true)

\
&#x20;10\.  ‘정책 아이템 추가’ 창에 정책 서포트 기능이 제안하는 정책 아이템 내용이 자동으로 생성되어 표시됩니다(아래 왼쪽 그림). 아이템 이름과 허용 권한 등 변경이 필요한 항목을 설정한 후 확인 버튼을 클릭합니다. 여기서는 읽기 권한이 필요하므로, 쓰기, 삭제 권한 등은 체크 해제합니다(아래 오른쪽 그림).\
\
![](https://support.mcloudoc.com/galleryDocuments/edbsncdcde8cd8d7c1a9a3fc3bb7dc864f71efbcd53bce61db4e535200399496c792e4531c9fea700028b2837eb5c9804fd0b?inline=true)\
\
![Notes](https://static.zohocdn.com/zoho-desk-editor/static/images/file.png/)정책 아이템의 항목별 설명 및 설정 방법은​ [DiskLock 콘솔에서 로컬저장금지 정책 아이템 설정하기](https://support.mcloudoc.com/portal/ko/kb/articles/disklock-%EC%BD%98%EC%86%94%EC%97%90%EC%84%9C-%EB%A1%9C%EC%BB%AC%EC%A0%80%EC%9E%A5%EA%B8%88%EC%A7%80-%EC%A0%95%EC%B1%85-%EC%95%84%EC%9D%B4%ED%85%9C-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0-26-9-2024)를 참고합니다. \
11\.  새로 생성된 정책 아이템의 내용이 추가한 정책 아이템 영역이 표시됩니다.![](https://support.mcloudoc.com/galleryDocuments/edbsn670906b7c501bc8fa3f8f57a9bd60ecfc6c35465e615050cb3d63aaa6f64ed0598bb609fa6d200be8db563df0e81a0cf?inline=true)\
\
12\.  위 화면에서 추가한 정책 아이템을 확인 후 하단의 적용 버튼을 클릭하면 해당 정책 아이템이 현재 사용 중인 로컬저장금지 정책에 추가됩니다. 다음과 같이 로컬저장금지 정책 관리 페이지에서 정책 아이템이 추가된 것을 확인할 수 있습니다.\
\
![](https://support.mcloudoc.com/galleryDocuments/edbsnaf6735d480021b279fa0971d3343cd08f7fee617c0af8a13b8b3e19b0c9aed5ae85555e0bd1fe8e1b82673ca42ec520e?inline=true)\
\
13\.  DiskLock 콘솔 좌측 메뉴 하단의 내 PC에 정책 새로고침, 또는 윈도우 에이전트 트레이 메뉴의 정책 새 고침을 클릭하여 정책 변경 사항을 PC에 곧바로 적용합니다.

14\.  오류가 발생했던 작업을 다시 수행하여 오류 해결 여부를 확인합니다.

<br>
