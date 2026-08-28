# 시작하기 전에

본 매뉴얼은 관리자가 문서중앙화 솔루션을 원활하게 운용, 관리하는 데 필요한 전반적인 설정 방법과 솔루션에서 제공되는 다양한 관리 기능의 구체적인 사용법에 대한 가이드입니다.

문서중앙화 솔루션을 처음 도입하신 경우에는 [**관리자 빠른 시작 가이드**](undefined-1/)를 먼저 참고하시기 바랍니다. 빠른 시작 가이드에서 문서중앙화 서비스를 시작하기 위해 관리자가 먼저 수행해야 하는 필수 절차를 간략히 확인할 수 있습니다.



### <mark style="color:$primary;">매뉴얼 표기 규칙 및 유의 사항</mark>

​본 매뉴얼은 윈도우 에이전트 3.164 버전 및 상위 버전을 기준으로 작성되었습니다. 사용하는 버전에 따라 실제 UI가 매뉴얼의 내용과 상이할 수 있습니다.

​매뉴얼 내용의 표기는 다음과 같은 규칙을 따릅니다.​

<table data-search="false"><thead><tr><th width="200.36358642578125">표기 규칙</th><th>설 명</th></tr></thead><tbody><tr><td><strong>굵은체</strong></td><td>중요 개념 또는 클릭 작업과 연관된 사용자 인터페이스 요소(버튼, 메뉴 등)</td></tr><tr><td><strong>-</strong></td><td>메뉴의 경로</td></tr><tr><td><strong>‘ ’ (작은 따옴표)</strong></td><td><p>레이어 팝업창의 명칭</p><p>예시: ‘로그인’ 창에서 로그인해주세요.</p></td></tr><tr><td><img src=".gitbook/assets/image (255).png" alt=""></td><td>관련 메뉴 이동 안내, 관리자에게 요청해야 하는 경우, 부가 설명 등 참고 사항</td></tr><tr><td><img src=".gitbook/assets/image (246).png" alt="" data-size="original"></td><td>잠재적 실수를 유발시킬 사항, 즉 위험이나 경고 또는 주의가 필요한 정보</td></tr><tr><td><img src=".gitbook/assets/image (247).png" alt="" data-size="original"></td><td>작업 수행에 유용한 정보를 제공하는 사용팁</td></tr><tr><td><img src=".gitbook/assets/image (248).png" alt="" data-size="original"></td><td>주의해서 알아야 할 정보</td></tr></tbody></table>

&#x20;​​

문서중앙화 웹페이지에서 공통적으로 사용되는 기호는 다음과 같습니다.​

<table><thead><tr><th width="200.36358642578125">아이콘</th><th>설 명</th></tr></thead><tbody><tr><td><img src=".gitbook/assets/image (249).png" alt="" data-size="original"></td><td>해당 정보를 엑셀 파일로 다운로드</td></tr><tr><td><img src=".gitbook/assets/image (250).png" alt="" data-size="line"></td><td>더보기 버튼. 정책의 이름을 변경하거나 생성한 정책을 복사, 삭제할 수 있습니다.</td></tr><tr><td><img src=".gitbook/assets/image (251).png" alt="" data-size="line"></td><td>검색 버튼</td></tr><tr><td><img src=".gitbook/assets/image (252).png" alt="" data-size="line"></td><td>수정 버튼</td></tr><tr><td><img src=".gitbook/assets/image (253).png" alt="" data-size="line"></td><td>삭제 버튼</td></tr></tbody></table>

&#x20;&#x20;

### <mark style="color:$primary;">솔루션 기능 모듈 소개</mark>

본 매뉴얼에서는 문서중앙화 솔루션의 관리 방법을 다음과 같은 기능 모듈별로 구분하여 설명합니다. 이 외에 [**서비스/시스템 설정  항목**](settings/)과 [**시스템 아키텍처 및 주요 동작 원리**](system/)를 별도 카테고리로 구성하여 안내합니다.

<table data-header-hidden="false" data-header-sticky data-search="false"><thead><tr><th width="200.36358642578125">기능 모듈</th><th>대표 기능</th></tr></thead><tbody><tr><td><a href="basic/"><strong>Basic</strong></a></td><td><ul><li>윈도우/Mac/모바일/웹 문서 탐색기</li><li>개인/부서 문서함 및 조직도 관리</li><li>폴더 권한 및 용량 관리</li><li>문서 버전 관리</li><li>사용 중 파일 자동 잠금</li><li>폴더 공유 및 문서링크 공유</li><li>외부 사용자 협업을 위한 게스트 아이디</li></ul></td></tr><tr><td><a href="disklock/"><strong>DiskLock</strong></a></td><td><ul><li>애플리케이션 카테고리별 읽기/쓰기 권한 설정</li><li>보안 수준별 정책 관리</li><li>로컬디스크로 파일 복사/이동 금지</li><li>파일 첨부 금지</li><li>문서 반출 프로세스 제공</li><li>파일 수집 및 중앙 문서함 이관</li><li>로컬디스크 내 보안디스크 운용</li></ul></td></tr><tr><td><a href="disklock-plus/"><strong>DiskLock Plus</strong></a></td><td><ul><li>클립보드 복사, 화면 캡쳐, 인쇄 금지</li><li>인쇄 로그 및 워터마크 제공</li></ul></td></tr><tr><td><strong>모바일</strong></td><td><ul><li>안드로이드 및 iOS 디바이스 지원</li><li>문서 열람, 메모, 폴더 공유, 문서링크 공유, 문서 반출 지원</li><li>사진 및 동영상 업로드</li><li>문서 반출, 결제 승인 등의 PUSH 알림 서비스</li></ul></td></tr><tr><td><strong>Mac</strong></td><td><ul><li>macOS 지원</li><li>문서 열람, 폴더 공유, 문서링크 공유, 문서 반출 지원</li></ul></td></tr><tr><td><a href="networklock/"><strong>NetworkLock</strong></a></td><td><ul><li>논리적 망 분리 (내부망/외부망) 및 모드 전환</li><li>망 간 자료 교환</li></ul></td></tr><tr><td><a href="pclog/"><strong>PC로그</strong></a></td><td><ul><li>로컬디스크 입출력 로그 수집 및 정책 관리</li><li>로그 검색, 열람 및 통계 차트 표시</li></ul></td></tr><tr><td><a href="undefined-2/"><strong>보안 뷰어</strong></a></td><td><ul><li>다운로드 없이 스트리밍으로 문서 열람</li><li>오피스 문서 변환</li></ul></td></tr><tr><td><a href="external-drm/"><strong>외부DRM</strong></a></td><td><ul><li>외부(협력사)에 암호화된 파일/폴더 링크 반출</li><li>수신 문서 열람을 위한 인증</li><li>반출된 문서 관리</li></ul></td></tr><tr><td><a href="document-security-classification/"><strong>문서보안</strong></a><a href="document-security-classification/"><strong>등급</strong></a></td><td><ul><li>문서 보안 등급 및 취급 권한 정의</li><li>보안 등급에 따른 정보 유출 통제</li><li>문서 보존 기한 설정</li></ul></td></tr><tr><td><a href="personal-information-security/"><strong>개인정보보호</strong></a></td><td><ul><li>개인정보 검출 및 검출 패턴 관리</li><li>검출 문서 통제 및 관리</li></ul></td></tr><tr><td><a href="project-version-management/"><strong>프로젝트 버전 관리</strong></a></td><td><ul><li>프로젝트 폴더별 버전 관리</li><li>프로젝트 백업 및 복원</li></ul></td></tr><tr><td><a href="external-document-exchange/"><strong>대외문서교환 서비스</strong></a></td><td><ul><li>DMZ 구간(대외문서교환 서버)에서 외부(협력사)와 문서 교환</li><li>대외용 문서 링크 공유 및 다운로드</li><li>외부에서 게스트 아이디로 파일 업로드</li></ul></td></tr><tr><td><strong>전문 검색 서비스</strong></td><td><ul><li>문서 카테고리 및 상세 검색</li><li>검색어 자동 완성</li></ul></td></tr><tr><td><a href="undefined-3/undefined.md"><strong>빅데이터 통계</strong></a></td><td><ul><li>문서 현황 및 문서 반출, 파일 작업 현황 제공</li><li>각 차트에 대한 리포팅</li></ul></td></tr><tr><td><a href="pc-backup/"><strong>PC 백업</strong></a></td><td><ul><li>PC 중요 파일을 중앙문서함에 백업/복원</li><li>즉시/예약, 증분 백업 지원</li></ul></td></tr><tr><td><a href="backupdoc/"><strong>BackupDoc</strong></a></td><td><ul><li>원본 서버의 중요 데이터 스냅샷을 백업 서버에 보관</li><li>증분 백업 및 맞춤형 백업 스케줄링 지원</li><li>백업 탐색기를 통한 편리한 다운로드/삭제</li></ul></td></tr></tbody></table>

{% hint style="warning" icon="file-lines" %}
고객사의 도입 범위와 관리자의 설정에 따라 각 기능의 제공 여부와 사용 방식이 달라질 수 있습니다.
{% endhint %}

&#x20;
