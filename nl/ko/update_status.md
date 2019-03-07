---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-28"

keywords: user state, user status, change user status, update user status

subcollection: iam

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}

# 사용자 상태 업데이트
{: #status}

사용자의 지정된 상태는 사용자가 계정 참여 초대를 수락했는지, 사용자가 VPN 전용 사용자인지, 또는 관리자가 사용자를 사용 불가능한 클래식 인프라 사용자로 설정했는지에 따라 다릅니다.
{:shortdesc}

다음 액세스가 있는 경우 다른 사용자의 상태를 업데이트할 수 있습니다.

  * 사용자 관리 서비스에 대한 편집자 이상의 역할을 가진 IAM 정책.
  * 사용자에 대한 클래식 인프라 계층에서 조상이며 사용자 클래식 인프라 관리 권한이 지정됨

사용자 상태 유형에 대한 자세한 정보는 [사용자 상태](/docs/iam?topic=iam-user_status#user_status)를 참조하십시오.

## 사용자 상태 변경에 대한 옵션
{: #status_options}

사용자 상태를 업데이트하기 위해 다음 옵션에서 선택할 수 있습니다.

<dl>
<dt>활성</dt>
<dd>사용자에게 지정된 액세스 정책 및 클래식 인프라 권한을 기반으로 한 {{site.data.keyword.cloud_notm}} 콘솔에 대한 전체 액세스가 있습니다.</dd>
<dt>사용 불가능한 클래식 인프라</dt>
<dd>사용자는 더 이상 클래식 인프라 리소스에 액세스할 수 없지만 계속해서 콘솔에 로그인하고 플랫폼 리소스에 액세스할 수 있습니다.</dd>
<dt>VPN 전용</dt>
<dd>사용자는 콘솔에 로그인할 수 없지만 어플라이언스에 직접 로그인하여 클래식 인프라에 지정한 디바이스와 VPN 서브넷이 무엇이든 액세스할 수 있습니다.</dd>
</dl>

사용자를 VPN 전용 상태에서 활성 상태로 업데이트하는 경우 사용자가 콘솔에 로그인하려면 비밀번호를 알아야 합니다. 대부분의 경우 이는 SoftLayer ID 비밀번호이며, 사용하려면 이를 재설정해야 합니다. 드물게 사용자에게 이미 IBM ID가 있는 경우 IBM ID 및 비밀번호로 로그인해야 합니다.
{: note}

## 사용자 상태 업데이트
{: #update_user_status}

사용자 상태를 변경하려면 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **사용자**를 선택하십시오.
2. 목록에서 사용자를 선택하십시오.
3. 사용자 세부사항 페이지의 **사용자 상태** 메뉴에서 옵션을 선택하십시오.  
4. **적용**을 클릭하십시오.
