---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: resource access, assign access, IAM access policy, access to resource groups, edit access, remove access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 리소스에 대한 액세스 관리
{: #iammanidaccser}

IAM 정책을 사용하여 액세스를 관리하거나 사용자에 대해 새 액세스를 지정하려면 계정 소유자, 계정의 모든 서비스에 대한 관리자 또는 특정 서비스나 서비스 인스턴스에 대한 지정된 관리자여야 합니다. 정책 및 역할 액세스에 대한 자세한 정보는 [IAM 액세스](/docs/iam?topic=iam-userroles#userroles)를 참조하십시오.
{:shortdesc}

## 기존 액세스 권한 편집
{: #edit_existing}

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **사용자**를 선택하십시오.
2. 액세스를 지정할 사용자의 이름을 선택하십시오.
3. 편집할 정책에 대한 행에서 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴를 선택한 다음 **정책 편집**을 클릭하십시오.
4. 정책을 편집하십시오.
5. **저장**을 클릭하십시오.

CLI를 사용하여 사용자 정책을 업데이트하기 위해 [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_update) 명령을 사용할 수 있습니다.
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

사용자나 그룹에 대한 액세스를 편집할 때 중복 정책을 허용하지 않는 데 관한 메시지가 나타날 수 있습니다. 기존 정책을 편집하고 변경사항이 이미 지정된 액세스와 충돌하는 경우 다른 액세스를 제공하기 위해 현재 편집 중인 정책을 변경하도록 선택하거나 충돌하는 기존 정책으로 돌아가 검토한 후 필요한 경우 변경할 수 있습니다. 요구사항을 충족하는 중복 정책이 이미 있으면 편집 중인 정책을 삭제할 수 있습니다.
{: note}

## 새 액세스 지정
{: #assign_new_access}

두 가지 유형의 정책을 사용하여 리소스에 대한 액세스 권한을 지정할 수 있습니다.

* 하나 또는 모두에 대한 옵션을 포함하여 리소스 그룹 내 리소스에 액세스
* 하나의 유형만 또는 모든 유형에 대한 옵션을 포함하여 계정의 리소스에 액세스

사용자 초대 및 제거, 청구 및 사용량 보기, 서비스 ID 관리, 액세스 그룹 관리, 사용자 액세스 권한 관리, 모든 계정 서비스에 대한 액세스와 같은 [계정 관리](/docs/iam?topic=iam-account-services#account-services) 태스크를 완료할 수 있도록 사용자에게 전체 관리자 액세스를 허용하려면 두 개의 정책(관리자 역할을 통한 **모든 ID 및 액세스 사용 서비스**에 대한 정책과 관리자 역할을 통한 **모든 계정 관리 서비스**에 대한 정책)을 작성해야 합니다.
{: tip}

### 리소스 그룹 내의 리소스에 액세스
{: #access_to_resources}

리소스 그룹의 모든 리소스에 대해 또는 리소스 그룹 내의 하나의 서비스에 대해서만 액세스를 지정하려면 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **사용자**를 선택하십시오.
2. 액세스를 지정할 사용자에 대한 행에서 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴를 선택한 다음 **액세스 지정**을 클릭하십시오.
3. **리소스 그룹 내의 액세스 지정**을 선택하십시오.
4. 리소스 그룹을 선택하십시오.
5. 사용자가 리소스 목록에서 리소스 그룹을 보거나 리소스 그룹 이름을 편집하거나 그룹에 대한 사용자 액세스를 관리할 수 있도록 **리소스 그룹에 대한 액세스 지정** 필드에 대한 역할을 선택하십시오. 사용자가 지정된 리소스에만 액세스하고 리소스가 속한 그룹에는 액세스하지 못하도록 하려는 경우 **액세스 없음**을 선택할 수 있습니다.
6. 리소스 그룹 내의 서비스를 선택하거나, 선택된 그룹 내의 모든 서비스에 대한 액세스 제공을 선택하십시오.
7. 사용자에 대해 원하는 액세스를 지정하기 위한 역할의 임의의 조합을 선택하십시오. 이 액세스는 정책에 대해 선택된 리소스에만 적용됩니다. 이는 리소스 그룹인 실제 컨테이너에 대한 액세스는 제공하지 않습니다.
8. **지정**을 클릭하십시오.

### 리소스에 액세스
{: #resourceaccess}

계정의 개별 리소스에 대한 액세스 또는 계정의 모든 리소스에 대한 액세스를 지정하려면 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **사용자**를 선택하십시오.
2. 액세스를 지정할 사용자에 대한 행에서 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴를 선택한 다음 **액세스 지정**을 클릭하십시오.
3. **리소스에 대한 액세스 지정**을 선택하십시오.
4. 서비스를 선택하거나 **모든 ID 및 액세스 사용 서비스**를 선택하십시오.
5. 프롬프트되는 경우 **모든 현재 지역** 또는 특정 지역을 선택하십시오.
6. **모든 현재 서비스 인스턴스**를 선택하거나 특정 서비스 인스턴스를 선택하십시오.
7. 선택한 서비스에 따라 다음 필드를 볼 수 있습니다. 이러한 필드에 값을 입력하지 않으면 버킷 레벨 대신 서비스 인스턴스 레벨에서 정책이 지정됩니다.
    * **리소스 유형**: **버킷**을 입력하십시오.
    * **리소스 ID**: 버킷의 이름을 입력하십시오.
8. 사용자에 대해 원하는 액세스를 지정하기 위한 역할의 임의의 조합을 선택하십시오.
9. **지정**을 클릭하십시오.

## 액세스 제거
{: #removing_access}

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **사용자**를 선택하십시오.
2. 해당 액세스를 제거할 사용자 이름을 선택하십시오.
3. **액세스 정책** 탭을 통해, 제거할 정책에 대한 행에서 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴를 선택하고 **제거**를 클릭하십시오.  
4. 제거할 사용자 정책 세부사항을 검토한 후에 **제거**를 클릭하여 확인하십시오.

CLI를 사용하여 사용자 정책을 제거하기 위해 [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_delete#ibmcloud_iam_user_policy_delete) 명령을 사용할 수 있습니다.
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## 지정된 액세스 검토
{: #review_your_access}

추가된 계정에서 지정된 액세스 권한을 검토해야 하는 경우에는 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **사용자**를 선택하십시오.
3. 이름을 선택하십시오.
4. **액세스 정책** 섹션에서 지정된 액세스를 검토하십시오.

추가 액세스가 필요한 경우에는 계정 소유자에게 문의하여 액세스를 업데이트하거나 서비스 또는 서비스 인스턴스의 관리자에게 문의하여 Cloud IAM 액세스 정책을 업데이트해야 합니다.
