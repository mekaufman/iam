---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 사용자에 대한 특정 IP 주소 허용
{: #ips}

기본적으로 모든 IP 주소를 사용하여 {{site.data.keyword.cloud}} 콘솔에 로그인하고 클래식 인프라 API에 액세스할 수 있습니다. 액세스가 있는 IP 주소를 지정할 수 있고, 지정된 주소만 허용되어 사용될 수 있으며 다른 모든 주소는 제한됩니다.
{:shortdesc}

제한된 IP 주소를 보유하고 있는 경우에는 [https://cloud.ibm.com](https://cloud.ibm.com){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")의 클래식 인프라 페이지에 액세스할 수 없습니다. [https://control.softlayer.com](https://control.softlayer.com){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")으로 이동해야 합니다.
{: important}

다음 지정된 액세스가 있는 경우 다른 사용자의 제한된 IP 주소를 업데이트할 수 있습니다.

  * 사용자 관리 서비스에 대한 편집자 이상의 역할을 가진 IAM 정책.
  * 사용자에 대한 클래식 인프라 계층에서 조상이며 사용자 클래식 인프라 관리 권한이 지정됨
  
사용자 세부사항 페이지에서 사용자 관리 로그인 설정을 사용하는 경우 스스로 이 설정을 관리할 수 있습니다.
{: tip}

사용자를 특정 IP 주소 사용으로만 제한하려면 다음 단계를 완료하십시오. 

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **사용자**를 선택하십시오. 
2. 목록에서 사용자를 선택하십시오.
3. 사용자 세부사항 페이지에서 **IP 비밀번호 제한** 섹션으로 이동하십시오. 
4. **클라우드 플랫폼**에 대해 IP 주소를 입력하십시오. 나열된 IP 주소는 이 사용자가 {{site.data.keyword.Bluemix}}에 로그인하는 데 사용할 수 있는 IP 주소입니다.
5. **클래식 인프라**에 대해 IP 주소를 입력하십시오. 나열된 IP 주소는 사용자가 클래식 인프라 API를 호출하는 데 사용할 수 있는 IP 주소입니다. 
  
  클래식 인프라 IP 주소를 입력하려면 사용자가 클래식 인프라 API 키를 이미 작성했어야 합니다.
  {: note}
 


