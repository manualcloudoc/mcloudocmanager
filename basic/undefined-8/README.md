# 승인권자 관리하기

중앙문서함에서 문서를 반출하는 등 보안상 유의가 필요한 작업에는 승인권자의 승인 절차가 동반됩니다. 승인권자에 대한 설명은 사용자 매뉴얼 – [<mark style="color:$warning;">**승인권자 및 결재 방식 소개**</mark>](https://app.gitbook.com/s/vQ0BiQsGY4PT08D7Nfay/basicmodule/undefined/approve)를 참고합니다.

다음 표는 승인이 요구되는 작업들에 대해 승인권자의 종류별 승인 가능 여부를 정리한 것입니다.

<table data-search="false"><thead><tr><th width="269">승인이 필요한 작업</th><th width="131">팀문서관리자</th><th width="124">폴더관리자</th><th>자가 승인</th></tr></thead><tbody><tr><td><p><strong>자료 반출</strong> </p><ul><li><strong>문서 반출</strong> </li><li><strong>외부 DRM 반출</strong></li></ul></td><td>O</td><td>부서문서함 문서일 경우에만</td><td>O</td></tr><tr><td><p><strong>링크 공유</strong></p><ul><li><strong>문서링크 복사</strong> </li><li><strong>보안 링크메일/웹링크</strong></li><li><strong>대외용 링크메일/웹링크</strong></li></ul></td><td>O</td><td>부서문서함 문서일 경우에만</td><td>O</td></tr><tr><td><strong>보안 해제 (워터마크, 인쇄 제어)</strong></td><td>O</td><td>X</td><td>O</td></tr><tr><td><strong>개인문서함 인계</strong></td><td>O</td><td>X</td><td>X</td></tr><tr><td><strong>문서 보안 등급 변경</strong></td><td>X</td><td>O</td><td>X</td></tr><tr><td><strong>문서 보존 기한 변경</strong></td><td>X</td><td>O</td><td>X</td></tr></tbody></table>

관리자는 자료 반출, 링크 공유, 보안 해제와 같이 자가 승인이 가능한 작업에 대해 자가 승인 허용 여부를 정책으로 설정하여 부서/사용자별로 적용할 수 있습니다.

또한 부서문서함 문서의 반출, 링크 공유와 같이 팀문서관리자와 폴더관리자가 모두 승인 가능한 작업에 대하여, 부서문서함/폴더별로 승인권자의 종류를 지정(팀문서관리자 또는 폴더관리자 중 택일)할 수 있습니다.

### <mark style="color:$primary;">자가 승인 허용 여부 설정</mark>

* 작업별 자가 승인 허용 여부를 정책으로 설정하고, 이를 부서/사용자별로 적용하는 방법은 [**자기승인 정책 관리 및 적용하기**](undefined.md)를 참고합니다.
* 자가승인 정책을 부서/사용자별로 적용한 이력을 조회하는 방법은 [**자가승인 정책 적용 이력 보기**](undefined-1.md)를 참고합니다.
* 자가승인 권한이 설정된 부서/사용자 현황을 확인하는 방법은 [**자가승인권자 현황 보기**](undefined-2.md)를 참고합니다.

### <mark style="color:$primary;">승인권자 종류 지정</mark>

* 문서함/폴더별로 승인권자의 종류를 지정하는 방법은 [**승인권자 종류 지정하기**](undefined-3.md)를 참고합니다.
* 문서함/폴더별로 보안등급문서 승인권자를 선택하고, 등급별 승인 권한을 설정할 수 있습니다. 자세한 내용은[**보안등급문서 승인권자 지정하기**](undefined-4.md)를 참고합니다.
* 문서함/폴더별로 승인권자 종류를 지정한 이력을 확인하는 방법은 [**승인권자 종류 지정 이력보기**](undefined-5.md)**​**를 참고합니다.
* 문서함/폴더에서 보안등급문서 승인권자를 지정한 이력을 확인하는 방법은 [**보안등급문서 승인권자 지정 이력보기**](undefined-6.md)를 참고합니다.
* 승인 권한을 보유한 팀문서관리자, 폴더관리자 현황과 각 승인권자가 보유한 권한 내용을 확인하는 방법은[**승인권자 현황 보기**](undefined-7.md)를 참고합니다.

