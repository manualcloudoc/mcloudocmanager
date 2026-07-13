# NetworkLock 관리자 정책 소개

NetworkLock은 기존의 PC 업무 환경에 문서중앙화 소프트웨어를 설치하는 것만으로 **논리적으로 망을 분리**하여 악성코드 감염 및 정보 유출을 방지할 수 있는 기능입니다.

관리자는 NetworkLock정책을 설정하여, 내부망과 외부망 모드에서 각각 접속이 허용/차단되는 IP 주소를 지정할 수 있습니다. NetworkLock 정책이 적용되면 사용자는 하나의 PC에서 내부망 또는 외부망 모드를 선택하여 간편하게 망 전환을 할 수 있습니다. 각각의 망모드에서 시스템은 다음과 같이 동작합니다.

|            |                                                                                                                                    |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| **망모드**    | **설명**                                                                                                                             |
| **내부망 모드** | 1. 기본적으로 모든 IP 및 도메인 주소로의 통신 차단 2. NetworkLock정책에서 허용된 IP/도메인 주소에만 접속 가능 3. **문서중앙화 드라이브 및 보안디스크가 마운트 됨**                          |
| **외부망 모드** | 1. 기본적으로 모든 IP 및 도메인 주소로의 통신 허용 2. NetworkLock정책에서 차단된 IP/도메인 주소에는 접속 불가 3. **문서중앙화 드라이브 마운트 해제** 4. **반출 보안 디스크에는 접근(읽기/쓰기)이 가능** |

![Notes](<../.gitbook/assets/img_000 (168).png>)**내부망/외부망** **모드**에 대한 소개는 **사용자 매뉴얼**의 [**NetworkLock\*\*\*\*소개**](https://github.com/manualcloudoc/mcloudoc-user-manual/blob/main/zoho-export/markdown/%EC%82%AC%EC%9A%A9%EC%9E%90-%EB%A7%A4%EB%89%B4%EC%96%BC/networklock/networklock-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EB%9D%BD-%EC%86%8C%EA%B0%9C.md)를 참고하세요.\
NetworkLock 정책은 다음과 같이 **내부망 모드에서 허용할 IP 대역**과 **외부망 모드에서 차단할 IP 대역**으로 구성됩니다.

![](<../.gitbook/assets/img_001 (155).png>)

## **내부망 모드 허용 IP 대역**

관리자는 NetworkLock 정책 설정 시 내부망 모드에서 접속을 허용할 업무용 IP대역(또는 도메인 주소)을 등록해야 합니다.  이때 사내망 IP대역뿐 아니라 게이트웨이, DNS 서버 등 네트워크 서비스의 IP주소를 필수적으로 등록해야 합니다.  또한, 고객사의 업무 환경 및 인프라에 따라 그룹웨어, ERP 서버, 보안 관련 서버 등 고객사에서 운용하는 서버 및 업무상 접속이 필수적인 인터넷 사이트 등의 주소를 추가해야 합니다.

### 필수 허용 IP 대역

|             |                           |                                                              |                 |
| ----------- | ------------------------- | ------------------------------------------------------------ | --------------- |
| **항목**      | **예시 (정책 아이템 이름, IP대역)**  |                                                              | **비고**          |
| **내부망 대역**  | Intranet                  | 192.168.1.1 \~ 192.168.1.255                                 |                 |
| **게이트웨이**   | Gateway                   | 192.168.1.10 \~ 192.168.1.10                                 | 2개 이상일 경우 각각 지정 |
| **DNS 서버**  | DNS serverDNS server(sub) | 203.248.252.2 \~ 203.248.252.2164.124.101.2 \~ 164.124.101.2 | 2개 이상일 경우 각각 지정 |
| **DHCP 서버** | DHCP server               | 192.168.1.40 \~ 192.168.1.40                                 | 존재할 경우에 한해 등록   |

![Notes](<../.gitbook/assets/img_002 (134).png>)게이트웨이나 DHCP 서버 등의 IP가 이미 허용 등록된 내부망 대역에 포함된 경우에는 별도로 등록할 필요가 없습니다.\
![Idea](<../.gitbook/assets/img_003 (117).png>)게이트웨이,  DNS 서버, DHCP 서버의 IP 주소는 다음의 방법으로 확인할 수 있습니다.

1\.   \[시작 버튼]-\[windows 시스템]-\[명령 프롬프트]를 실행하거나, 실행창에서 "cmd"를 입력합니다. (실행창: 키보드의 WIN+R, 윈도우 작업표시줄의 Microsoft Search창 등)\
2\.  명령 프롬프트에서 "ipconfig /all”을 입력합니다.\
3\.  화면의 목록 중 사용하는 네트워크 연결(예: Wi-Fi, 이더넷)의 설정 정보를 참고합니다.

![](<../.gitbook/assets/img_004 (91).png>)\
![Notes](<../.gitbook/assets/img_005 (78).png>)이 외 필수적으로 접속이 허용되어야 하는 문서중앙화 웹 서버 주소 및 255.255.255.255 (DHCP에서 사용되는 broadcast 주소)는 정책과 상관없이 시스템에서 자동적으로 허용됩니다.

### 고객사 환경에 따라 선택이 필요한 IP 대역

|                                              |                                          |                             |                                       |
| -------------------------------------------- | ---------------------------------------- | --------------------------- | ------------------------------------- |
| **구분**                                       | **항목**                                   | **예시(정책 아이템 이름, IP대역/도메인)** |                                       |
| 회사 운용 서버                                     | 업무용 서버 (그룹웨어, 메일, ERP 서버 등               | Groupware                   | 192.168.1.100                         |
| 보안 관련 서버 (DLP, DRM, 키보드 보안, 백신, 보안 USB 서버 등) | DLP Server                               | 192.168.1.20                |                                       |
| 사용자 인증 서버 (Active Directory 서버 등)            | Active Directory                         | 192.168.1.30                |                                       |
| 업무용 사이트                                      | 관공서, 은행 사이트 등 업무상 접속이 필요한 외부 사이트         | 정부24                        | \*.gov.kr                             |
| Windows 사이트                                  | Windows 업데이트 및SmartScreen 지원을 위해 허용할 사이트 | WindowsUpdate1SmartScreen1  | \*.windowsupdate.comurs.microsoft.com |
| 원격지원 사이트                                     | 문서중앙화 서비스 원격 지원을 위한 사이트 등                | 이지헬프                        | 939.co.krwww.ezhelp.co.krwww.ezh.kr   |

![Notes](<../.gitbook/assets/img_006 (66).png>)위 예시의 항목 및 IP/도메인 주소는 단순한 예시로서, 실제로 등록할 항목 및 주소는 고객사의 업무 환경 및 인프라 구성을 참고하여 설정합니다.![Notes](<../.gitbook/assets/img_007 (56).png>)SmartScreen(Microsoft Defender SmartScreen)은 윈도우 환경에서 피싱 또는 악성 프로그램 웹사이트에 접근하거나, 악의적인 파일을 다운로드할 경우 경고 메시지를 표시하여 PC를 보호하는 기능입니다. 자세한 설명은 다음의 링크를 참고하세요.[https://learn.microsoft.com/ko-kr/windows/security/operating-system-security/virus-and-threat-protection/microsoft-defender-smartscreen/](https://learn.microsoft.com/ko-kr/windows/security/operating-system-security/virus-and-threat-protection/microsoft-defender-smartscreen/)

SmartScreen을 지원하기 위해 접속이 허용되어야 하는 도메인은 다음과 같은 종류가 있습니다.\
\-     urs.microsoft.com-    \*.urs.microsoft.com\
\-    \*.smartscreen.microsoft.com\
\-    \*.smartscreen-prod.microsoft.com

\[참고 링크]-    [https://learn.microsoft.com/ko-kr/troubleshoot/developer/browsers/stability-performance/hangs-when-access-to-smartscreen-blocked](https://learn.microsoft.com/ko-kr/troubleshoot/developer/browsers/stability-performance/hangs-when-access-to-smartscreen-blocked)-    [https://learn.microsoft.com/ko-kr/deployedge/microsoft-edge-security-endpoints](https://learn.microsoft.com/ko-kr/deployedge/microsoft-edge-security-endpoints) Windows 업데이트를 위해서는 다음과 같은 도메인으로의 접속이 허용되어야 합니다.

\-     windowsupdate.microsoft.com-     \*.windowsupdate.microsoft.com-     \*.update.microsoft.com-     \*.windowsupdate.com-     download.windowsupdate.com-     \*.download.windowsupdate.com-     download.microsoft.com-     wustat.windows.com-     ntservicepack.microsoft.com

\[참고 링크]\
[https://learn.microsoft.com/ko-kr/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-configure-your-firewall-to-allow-your-first-wsus-server-to-connect-to-microsoft-domains-on-the-internet](https://learn.microsoft.com/ko-kr/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-configure-your-firewall-to-allow-your-first-wsus-server-to-connect-to-microsoft-domains-on-the-internet)![Warning](<../.gitbook/assets/img_008 (51).png>)업무용 서버 및 웹사이트에서 외부 서버와 연동이 필요하거나 다른 웹사이트로의 링크(외부 URL 참조)가 존재할 경우, 외부 서버 또는 웹사이트의 IP/도메인 주소도 추가되어야 합니다.\
예를 들어, 그룹웨어에서 네이버 지도 연동이 필요한 경우 \*.map.naver.com 등이 추가로 허용되어야 하며, 정부24 사이트에서 가족관계등록시스템으로의 링크 사용 시\
efamily.scourt.go.kr 이 추가되어야 합니다.

필요한 모든 주소가 추가되지 않을 경우, 서버/웹사이트의 기능이 정상적으로 동작하지 않거나, 이미지/동영상 등이 표시되지 않을 수 있습니다.

서버/웹사이트가 정상적으로 동작하지 않을 경우, 추가적으로 허용해야 할 IP/도메인 주소를 찾아내는 방법은 [**NetworkLock 사용 시 인터넷 사이트 접속 관련 오류 해결 방법**](https://github.com/manualcloudoc/mcloudoc-user-manual/blob/main/zoho-export/markdown/%EA%B4%80%EB%A6%AC%EC%9E%90-faq-new-ver/networklock/networklock-%EC%82%AC%EC%9A%A9-%EC%8B%9C-%EC%9D%B8%ED%84%B0%EB%84%B7-%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%A0%91%EC%86%8D-%EA%B4%80%EB%A0%A8-%EC%98%A4%EB%A5%98-%ED%95%B4%EA%B2%B0-%EB%B0%A9%EB%B2%95.md)을 참고하세요.

### 내부망 모드 제한 사항

1. **외부 서버와 연동 또는 외부 URL 참조 문제**

내부망 모드에서 접속 가능한 업무용 서버 및 웹사이트 내에서 연동 또는 링크된 모든 외부사이트에 대한접속이 NetworkLock 정책에서 추가로 허용되지 않은 경우, 서버/웹사이트의 기능이 정상적으로 동작하지 않거나, 이미지/동영상 등이 표시되지 않을 수 있습니다. (위의 중요 참고사항 참조)또한, 인터넷 웹사이트 중 쇼핑몰과 같이 외부 URL 참조가 많을 경우, 해당 도메인 주소를 모두 허용하더라도 접속이 과도하게 느려져 사용이 어려울 수 있습니다.

1. **상용 메신저 및 인터넷 서비스 사용 문제**

상용 메신저(카카오톡, MSN 메신저 등), 인터넷 서비스(구글 드라이브, 네이버 드라이브 등)와 같은 프로그램의 경우 유동적인 IP 대역과 많은 도메인 주소가 존재하여 내부망 모드에서 허용 시 완벽한 정책 설정이 어려우므로, 외부망 모드에서 사용하는 것을 권장합니다.

&#x20;

## 외부망 모드 차단 IP 대역

관리자는 외부망 모드에서 업무용 IP 대역에 대한 접속이 차단되도록 정책을 설정해야 합니다. 단, 필수 서버에 대한 접속은 허용되어야 하므로, 차단할 IP 대역에 네트워크 서비스, 보안 관련 서버, 사용자 인증 서버 등의 IP가 포함된 경우, 해당 IP주소는 차단에서 제외되도록 주의하여 설정해야 합니다.

### 차단할 IP 대역

|                               |                          |                                |                                                    |
| ----------------------------- | ------------------------ | ------------------------------ | -------------------------------------------------- |
| **항목**                        | **예시 (정책 아이템 이름, IP대역)** |                                | **비고**                                             |
| 내부망 대역                        | Intranet                 | 192.168.1.1 \~ 192.168.1.255   | 내부망 대역 차단 시 차단에서 제외되어야 할 IP주소에 유의하여 구간을 세분하여 등록 필요 |
| 회사 운용 서버 (그룹웨어, 메일, ERP 서버 등) | 메일 서버                    | 192.168.2.100 \~ 192.168.2.100 | 차단할 서버의 IP가 내부망 대역에 포함되지 않을 경우 추가로 등록 필요           |

### 차단에서 제외할 IP대역

|           |                                                                                |
| --------- | ------------------------------------------------------------------------------ |
| **구분**    | **항목**                                                                         |
| 네트워크 서비스  | -      게이트웨이 -      DNS 서버 -      DHCP 서버 등                                    |
| 보안 관련 서버  | -      DLP 서버 -      DRM 서버 -       키보드 보안 서버 -      백신 서버 -       보안 USB 서버 등 |
| 사용자 인증 서버 | -      Active Directory 서버 등                                                   |

위와 같은 필수 서버의 IP주소가 차단 등록된 IP대역에 포함되어 있을 경우, 해당 IP 주소는 차단에서 제외되도록 차단할 IP대역을 세분하여 재등록해야 합니다.\
앞에서 소개한 NetworkLock 정책 예시에서 사내망 IP 대역 192.168.1.1\~192.168.1.255에 대한 차단 등록 시, 다음과 같이 IP대역을 구간별로 구분, 등록하여 게이트웨이(192.168.1.10), DLP 서버(192.168.1.20) 등을 차단에서 제외할 수 있습니다.

![](<../.gitbook/assets/img_009 (43).png>)
