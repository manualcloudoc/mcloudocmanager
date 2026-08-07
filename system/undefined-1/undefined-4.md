# 문서함에 저장된 파일의 이름과 구조

문서중앙화 서버에서 변환되는 파일의 이름과 구조 및 내부적으로 관리하는 특수 파일에 대해 설명합니다.&#x20;

#### <mark style="color:$primary;">문서 파일</mark>

문서 파일은 서버에 저장될 때 암호화나 헤더 추가 등으로 파일의 이름이 변환됩니다. 여기서는 변환되는 문서 파일의 이름과 구조에 대해 설명합니다.

서버에 저장되는 문서는 기본적으로 PC문서와 동일한 이름으로 저장되지만, 특수 파일명에 사용되는 ‘%’를 파일명에 포함하고 있는 경우 다음과 같이 해당 문자를 인코딩하여 파일명을 변경합니다.&#x20;

<table><thead><tr><th width="202">변환 전 파일명 문자</th><th>변환 후 파일명 문자</th></tr></thead><tbody><tr><td><strong>%</strong></td><td><strong>%251</strong></td></tr></tbody></table>

​예) report%1.docx 은 report%251.docx 로 이름을 변경하여 저장합니다. 파일이 암호화되어 저장된 경우는 변환된 파일명 뒤에 \*\*.secure+\*\*확장자가 붙어 저장됩니다. 또한, 추가적인 정보나 기능을 제공하기 위해 파일이 헤더를 갖도록 설정할 수 있습니다. 이 경우 역시 파일명 뒤에 .cld+ 를 붙여서 저장합니다.

<table data-search="false"><thead><tr><th width="209">헤더 항목</th><th>내용</th></tr></thead><tbody><tr><td><strong>Version</strong></td><td>버전​</td></tr><tr><td><strong>hsize</strong></td><td>파일 사이즈</td></tr><tr><td><strong>crtdby</strong></td><td>파일 생성자</td></tr><tr><td><strong>mdfdby</strong></td><td>파일의 마지막 수정자</td></tr><tr><td><strong>docid</strong></td><td>문서 고유 아이디</td></tr><tr><td><strong>seclvl</strong></td><td>문서보안등급 코드(기능 사용시에만 설정되는 항목)</td></tr><tr><td><strong>exprdate</strong></td><td>문서 만료일(기능 사용시에만 설정되는 항목)</td></tr><tr><td><strong>acdate</strong></td><td>파일의 마지막 접근일(기능 사용시에만 설정되는 항목)</td></tr><tr><td><strong>pcy</strong></td><td>개인정보 파일 여부 (Y or N)(기능 사용시에만 설정되는 항목)​</td></tr></tbody></table>

내용검색, 문서태그, 문서보안등급, 문서 만료일 등의 기능을 제공하기 위해서는 반드시 문서 헤더를 이용해야 합니다.

파일명이 report%1.docx 인 경우 헤더와 암호화 사용 여부에 따라 파일명은 아래 테이블과 같이 변경하여 저장합니다.

<table><thead><tr><th width="152">파일 헤더 여부</th><th width="200">파일 암호화 여부</th><th>저장 파일명</th></tr></thead><tbody><tr><td><strong>사용 안함</strong></td><td>평문</td><td>report%251.docx</td></tr><tr><td></td><td>암호화</td><td>report%251.docx.secure+</td></tr><tr><td><strong>사용함</strong></td><td>평문</td><td>report%251.docx.cld+</td></tr><tr><td></td><td>암호화</td><td>report%251.docx.secure+.cld+8</td></tr></tbody></table>

#### <mark style="color:$primary;">특수 파일</mark>

내부적으로 파일시스템을 관리하기 위해 사용하는 특수 파일들이 다음과 같습니다.

<table><thead><tr><th width="201">파일명</th><th>폴더 위치</th><th>용도</th></tr></thead><tbody><tr><td>%%props</td><td>문서함 내 모든 폴더마다 존재</td><td><p>해당 폴더의 속성 정보 확인 </p><ul><li>폴더를 생성한 사용자</li><li>보안 반출 폴더 여부</li><li>문서보안등급 폴더인 경우 관련 정보</li></ul></td></tr><tr><td>%%quota</td><td><p>문서함 root 레벨 또는 부서문서함의 quota 설정 폴더</p><p></p><p>예) /plusdrive/home/00000/data/%%quota /plusdrive/orgcowork/00001/data/marketing/%%quota</p></td><td>문서함 또는 폴더에 할당한 전체 용량 확인</td></tr><tr><td>%%used/value</td><td><p>문서함 root 레벨 또는 부서문서함의 quota 설정 폴더 </p><p></p><p>예) /plusdrive/home/00000/%%used/value /plusdrive/orgcowork/00001/data/marketing/%%used/value</p></td><td>현재 사용중인 용량 확인</td></tr><tr><td>%%used/{년월일시분초}/delta</td><td><p>문서함 root 레벨 </p><p>(부서문서함의 quota 설정 폴더에는 사용하지 않음)</p><p></p><p>예) /plusdrive/home/00000/%%used/20200831125530/delta</p></td><td>실시간 용량 변화량 기록하여 1분마다 %%used/value 파일에 반영.</td></tr><tr><td>%%share/{사용중인 파일명}/{세션아이디_사용자아이디}</td><td><p>사용중인 파일이 존재하는 경로 </p><p></p><p>예) /plusdrive/orgcowork/00003/data/marketing/%%share /<strong>REPORT.DOCX</strong>/d26a0f9318f2b7ab569f25157512d04d_gdhong</p></td><td><ul><li>현재 파일을 사용중인 사용자 목록을 관리하여 읽기와 쓰기 등을 통제하는데 이용. </li><li>파일명에 영문자가 들어가면 대문자로 변경되어 폴더명이 생성됨.</li></ul><p> 예) data 경로 하위marketing 폴더 내의 report.docx 파일을 연 경우 왼쪽 예와 같이 대문자로 <strong>REPORT.DOCX</strong>  폴더명이 생성됨.</p></td></tr><tr><td>%%dslexcept</td><td><p>문서함 경로 내 폴더에 엔지니어가 수동 생성</p><p></p><p>ex) /plusdrive/orgcowork/00003/data/marketing</p></td><td>해당 파일이 존재하는 경우 하위 파일의 문서보안등급 확인 제외 (윈도우 탐색기에서 폴더 목록보기 속도 이슈로 추가)​</td></tr></tbody></table>

&#x20;

​\
​
