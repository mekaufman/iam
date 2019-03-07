---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-30"

keywords: user state, user status, type of user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# 사용자 상태
{: #user_status}

사용자가 계정으로 초대된 경우 사용자 유형과 초대를 수락하는 상태에 따라 특정 사용자의 **사용자 세부사항** 페이지에 표시되는 상태가 지정됩니다.
{:shortdesc}

| 사용자 상태 |설명 |
|:-----------|:------------|
|활성 | 사용자가 초대를 수락했고 계정 내에서 작동하도록 지정된 액세스를 갖습니다. |
| 사용 불가능한 클래식 인프라 | 계정 소유자 또는 충분한 권한을 가진 사용자는 사용자가 더 이상 클래식 인프라 리소스에 액세스할 수 없도록 다른 사용자를 사용 안함으로 설정할 수 있습니다. 사용자는 계속해서 콘솔에 로그인하고 플랫폼 리소스에 액세스할 수 있습니다. |
| VPN 전용 | 계정에 작성되었지만 디바이스에 대한 VPN 액세스로만 제한되는 사용자입니다. 이 유형의 사용자에게 콘솔에 로그인하기 위한 액세스가 없습니다.|
|처리 중 | 사용자가 초대에 추가되었지만 초대가 전송되지 않았고 시스템이 사용자의 첫 번째 인스턴스를 작성한 보기 드문 상태입니다. |
|보류 중 | 사용자가 초대되었지만 초대를 수락하지 않았거나 {{site.data.keyword.Bluemix_notm}} 계정을 작성하여 계정에 참여한 상태입니다. |
{: caption="표 1. 사용자 상태" caption-side="top"}

사용자 상태 변경에 대한 정보는 [사용자 상태 업데이트](/docs/iam?topic=iam-status#status)를 참조하십시오.
