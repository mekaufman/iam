---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# 액세스 그룹 설정
{: #groups}

액세스 그룹을 작성하여 사용자 및 서비스 ID 세트를 액세스를 쉽게 지정할 수 있게 하는 단일 엔티티로 구성할 수 있습니다. 개별 사용자 또는 서비스 ID마다 동일한 액세스를 여러 번 지정하는 대신 그룹에 단일 정책을 지정할 수 있습니다.
{:shortdesc}

새 액세스 그룹을 관리하거나 작성하려면 계정 소유자, 계정의 IAM 액세스 그룹 서비스의 관리자 또는 편집자, 모든 계정 관리 서비스에 대해 지정된 관리자 또는 편집자여야 합니다. 또한 리소스가 액세스 그룹 ID인 액세스 정책을 작성하여 개별 그룹을 관리하기 위해 관리자 또는 편집자를 지정할 수 있습니다. IAM 액세스 그룹 서비스에 대한 액세스 정책 및 역할에 대한 자세한 정보는 [IAM 액세스](/docs/iam?topic=iam-userroles#userroles)를 참조하십시오.

액세스를 훨씬 더 쉽게 지정하고 관리하기 위해 리소스 그룹을 설정하여 사용자 그룹이 액세스하게 할 리소스 세트를 구성할 수 있습니다. 리소스 그룹이 설정되면 계정 내 개별 서비스 인스턴스에 대한 액세스 정책을 작성하는 대신 이 그룹 내 모든 리소스에 액세스를 제공하는 정책을 지정할 수 있습니다. 
{: tip}

## 액세스 그룹 작성
{: #create_ag}

액세스 그룹을 작성하려면 다음 단계를 완료하십시오.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **액세스 그룹**을 선택하십시오.
2. **작성**을 클릭하십시오.
3. 그룹에 대한 선택적 설명 및 이름을 입력하고 **작성**을 클릭하십시오.

그런 다음, 계속 서비스 ID 또는 사용자를 추가하여 그룹을 설정하십시오.

1. 추가할 그룹의 이름을 선택하십시오.
2. **사용자** 탭에서 **사용자 추가**를 클릭하십시오. 
3. 목록에서 추가할 사용자를 선택하고 **그룹에 추가**를 클릭하십시오.
4. 그룹에 서비스 ID를 추가하려면 **서비스 ID** 탭을 클릭하고 **서비스 ID 추가**를 클릭하십시오.
5. 목록에서 추가할 ID를 선택하고 **그룹에 추가**를 클릭하십시오.

**그룹 제거** 옵션을 선택하여 그룹을 삭제할 수 있습니다. 계정에서 그룹을 제거하면 그룹 및 그룹에 지정된 모든 액세스에서 사용자와 서비스 ID가 모두 제거됩니다.
{: note}

CLI를 사용하여 액세스 그룹을 작성하기 위해 [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) 명령을 사용할 수 있습니다.
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}


## 그룹에 액세스 지정
{: #access_ag}

사용자 및 서비스 ID로 그룹을 설정한 후 그룹에 공통 액세스 정책을 지정할 수 있습니다. 그룹에 설정한 정책은 그룹 내 모든 엔티티에 적용됩니다.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **액세스 그룹**을 선택하십시오.
2. 액세스를 지정할 그룹의 이름을 선택하십시오. 
3. **액세스 정책**을 클릭하십시오.
4. **액세스 지정**을 클릭하십시오. 
5. 리소스 그룹 내 리소스, 계정 내에서 사용 가능한 개별 리소스 또는 계정 관리 서비스로 액세스를 지정하도록 선택하십시오.

CLI를 사용하여 액세스 그룹 정책을 작성하기 위해 [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) 명령을 사용할 수 있습니다.
```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}


