---

copyright:

  years: 2015, 2019

lastupdated: "2019-08-08"

keywords: invite, invite users, invitation access, vpn-only user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# 邀请用户加入帐户
{: #iamuserinv}

使用 {{site.data.keyword.Bluemix}} Identity and Access Management (IAM)，可以邀请用户，取消邀请，以及向被邀请用户重新发送待处理邀请。此外，您可以一次邀请单个用户或多个用户。
{:shortdesc}

要邀请用户并管理待处理邀请，您必须是帐户所有者、组织管理者或者具有对用户管理服务的编辑者或更高角色的 IAM 访问策略的用户，或者您必须具有添加用户的经典基础架构许可权。

## 设置邀请
{: #invitations}

要邀请用户或管理帐户中的用户邀请，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 单击**邀请用户**。
3. 指定用户的电子邮件地址。如果是使用单个邀请来邀请多个用户，那么将为所有用户分配相同的访问权。
4. 添加所管理的一个或多个访问权选项。必须至少分配一个访问权选项。对于未添加和配置的任何其他访问权选项，都会分配缺省值**无访问权**。根据您有权管理的选项，可能会看到以下一个或全部访问权选项：

  * **服务**
  * **Cloud Foundry 访问权**
  * **经典基础架构访问权**。

  有关更多信息，请参阅[分配用户访问权](/docs/iam?topic=iam-iamuserinv#assignaccess)。

如果确定某个用户不需要访问权，那么可以对“状态”列中显示为“正在处理”或“暂挂”状态的任何用户取消邀请。如果被邀请用户未收到邀请，那么可以向处于“暂挂”状态的任何用户重新发送邀请。

### 使用 CLI 邀请用户
{: #cli-invite}

要使用命令行界面 (CLI) 来邀请用户，请运行以下命令：

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

通过使用 CLI，可以选择分配 Cloud Foundry 访问权，或者暂不分配访问权，以后再分配。有关命令参数的更多信息，请参阅 [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite)。 

### 使用 API 邀请用户
{: #api-invite}

可以使用 [API](https://cloud.ibm.com/apidocs/user-management#invite-users){: external} 批量邀请用户。在单个邀请中包含的所有用户都分配有相同的访问权。使用 API 邀请用户时，可以输入逗号分隔的电子邮件列表，每个条目用引号括起，例如：


```
curl -X POST \
  https://user-management.cloud.ibm.com/v2/accounts/987d4cfd77b04e9b9e1a6asdcc861234/users \
  -H 'Authorization: Bearer <IAM_TOKEN>'
  -H 'Content-Type: application/json' \
    -d '{
      "users": [
      {
        "email": "cloud_api_example_member@ibm.com", "second_user@ibm.com", "third_user@ibm.com",
        "account_role": "Member"
      }],
      "iam_policy": [
      {
        "roles": [
        {
          "id": "crn:v1:bluemix:public:iam::::role:Viewer"
        }],
        "resources": [
        {
          "accountId": "111d4cfd77b04e9b9e1a6asdcc861234",
          "resourceType": "resource-group",
          "resource": "111449dd871049c29ec3a53853ce123e"
        }]
      }]
    }'
```
{: codeblock}

## 通过邀请分配用户访问权
{: #assignaccess}

在邀请用户时，可通过分配 {{site.data.keyword.Bluemix}} IAM 策略、Cloud Foundry 访问权和经典基础架构许可权来为用户分配访问权。根据您有权管理的访问权选项，可以邀请整个帐户、资源组、组织、空间、服务实例和经典基础架构中的用户并为其提供访问权。以下各部分描述了可以分配给受邀用户的三种类型访问权。

### 服务
{: #invite_services}

邀请新用户时，可以通过创建初始 {{site.data.keyword.Bluemix_notm}} IAM 访问策略来分配访问权。在“服务”部分中，可以向用户提供对帐户管理服务的访问权、对资源组中服务的访问权以管理资源组，或对帐户中单个资源的访问权。

用户接受邀请后，可以为其分配更多访问权。有关编辑策略以添加额外角色、分配更多访问权或除去用户策略的详细信息，请参阅[管理对资源的访问权](/docs/iam?topic=iam-iammanidaccser#iammanidaccser)。

根据您在分配策略时选择的服务，可能不会看到以下过程中描述的所有字段。
{: note}

#### 帐户管理服务访问权
{: #invite_acct_mgmt}

要委派您作为帐户所有者的一些职责，您可以向用户提供对帐户管理服务的访问权。例如，您可以委派查看计费和使用情况，邀请和除去用户，管理访问组或管理服务标识的功能。您可以向所有帐户管理服务或仅一个帐户管理服务提供访问权。

1. 在“邀请用户”页面上，展开“服务”部分。
2. 从**将访问权分配给**列表中，选择**帐户管理服务**。 
3. 选择**所有帐户管理服务**，或选择特定的帐户管理服务。
4. 选择任意角色组合来分配所需的访问权。

#### 资源组访问权
{: #invite_rgs}

可以分配对资源组中所有服务的访问权，也可以分配对资源组中单个服务类型的访问权。

1. 在“邀请用户”页面上，展开“服务”部分。
2. 从**将访问权分配给**列表中，选择**资源组**。
3. 选择资源组。
4. 从**分配对资源组的访问权**列表中选择角色，以支持用户在资源列表上查看资源组，编辑资源组名称或管理用户对该组的访问权。如果希望用户仅有权访问您指定的资源，而无权访问资源所组织到的组，那么可以选择**无访问权**。
5. 选择资源组中的服务，或选择提供对所选组中所有服务的访问权。
6. 选择任意角色组合来分配所需的访问权。此访问权仅适用于为策略选择的资源。它并不授予对实际容器（即资源组）的访问权。

#### 资源访问权
{: #invite_resources}

可以分配对帐户中单个资源下至实例的访问权。

1. 在“邀请用户”页面上，展开“服务”部分。
2. 从**将访问权分配给**列表中，选择**资源**。 
3. 选择服务。
4. 选择**所有当前区域**或特定区域（如果系统提示选择）。
5. 选择**所有当前服务实例**或选择特定服务实例。
6. 根据所选择的服务，可能会看到以下字段。如果您未输入这些字段的值，那么会在服务实例级别而非存储区级别来分配策略。
    * **资源类型**：输入`存储区`。
    * **资源标识**：输入存储区的名称。
7. 选择任意角色组合来分配所需的访问权。

有关分配访问权时使用的角色的更多信息，请参阅 [IAM 访问权](/docs/iam?topic=iam-userroles#iamusermanrol)。

### Cloud Foundry 访问权
{: #invite_cf}

当您邀请新用户时，您可以选择将用户添加到帐户中的组织。如果您向组织添加用户，那么可以向该用户分配组织角色。然后，选择通过分配的空间角色为受邀的用户提供所选组织中任何或所有空间的访问权。

1. 在“邀请用户”页面上，展开“Cloud Foundry 访问权”部分。
2. 选择要将用户添加到的组织。
3. 选择组织角色，以定义所选组织的访问级别。
4. 可选：单击**添加组织角色**以指定额外角色。
5. 选择**所有当前区域**或特定区域。
6. 选择**所有当前空间**或特定空间。
7. 选择空间角色，以定义所选空间的访问级别。
8. 可选：单击**添加空间角色**以指定额外角色。

有关分配访问权时使用的角色的更多信息，请参阅 [Cloud Foundry 角色](/docs/iam?topic=iam-cfaccess#cfroles)。

您可以使用 [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite) CLI 命令来添加 Cloud Foundry 角色，但必须使用控制台来分配其他访问权或许可权。
{: tip}

### 经典基础架构访问权
{: #invite_classicinfra}

所分配的许可权会自动限制为您所拥有的许可权的子集。您将成为您邀请的任何用户的父用户。

1. 在“邀请用户”页面上，展开“经典基础架构访问权”部分。
2. 选择用于分配预定义批量许可权的许可权集。

对设备的访问权将在添加用户后单独授予。请转至控制台中用户的**经典基础架构**访问权选项。
{: note}

有关将用户添加到帐户后为用户配置访问权的信息，请参阅[管理经典基础架构访问权](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra)。

## 添加仅使用 VPN 的用户
{: #add-vpn-only}

作为帐户所有者或具有“管理用户”经典基础架构许可权的用户，您可以添加仅使用 VPN 的用户。

1. 在“用户”页面上，单击**添加仅使用 VPN 的用户**。
2. 输入用户的个人详细信息。
3. 单击**保存**。
