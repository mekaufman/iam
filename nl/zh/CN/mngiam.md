---

copyright:

  years: 2017, 2019

lastupdated: "2019-04-03"

keywords: resource access, assign access, IAM access policy, access to resource groups, edit access, remove access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 管理对资源的访问权
{: #iammanidaccser}

要使用 IAM 策略来管理用户的访问权或分配新访问权，您必须是帐户所有者、帐户中所有服务的管理员，或者是为特定服务或服务实例分配的管理员。有关访问策略和角色的更多信息，请参阅 [IAM 访问权](/docs/iam?topic=iam-userroles#userroles)。
{:shortdesc}

## 编辑现有访问权
{: #edit_existing}

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 选择要为其分配访问权的用户的名称。
3. 从要编辑的策略所在的行中，选择**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单，然后单击**编辑策略**。
4. 编辑策略。
5. 单击**保存**。

要使用 CLI 更新用户策略，可以使用 [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_update) 命令。
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

编辑用户或组的访问权时，您可能会收到有关不允许重复策略的消息。如果您编辑的是现有策略，而且所执行的更改与已分配的访问权相冲突，那么可以选择更改当前正在编辑的策略以提供不同的访问权，也可以转至现有冲突的策略来进行查看，并视需要进行更改。如果有满足您需求的重复策略存在，那么您可能需要删除正在编辑的策略。
{: note}

## 分配新访问权
{: #assign_new_access}

可以使用以下两种类型的策略来分配对资源的访问权：

* 对资源组中资源（包括仅一个或所有资源的选项）的访问权
* 对帐户中资源（包括仅一种类型或所有类型的选项）的访问权

如果要授予用户完全管理员访问权，以执行[帐户管理](/docs/iam?topic=iam-account-services#account-services)任务（例如，邀请和除去用户，查看计费和使用情况，管理服务标识，管理访问组，管理用户访问权以及所有帐户资源的访问权），那么必须创建两个策略：一个用于具有管理员和管理者角色的**所有启用“身份和访问权”的服务**，另一个用于具有管理员角色的**所有帐户管理服务**。
{: tip}

### 对资源组中资源的访问权
{: #access_to_resources}

要分配对资源组中所有资源的访问权，或分配仅对资源组中一项服务的访问权，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 在要为其分配访问权的用户所在的行中，选择**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单，然后单击**分配访问权**。
3. 选择**分配对资源组的访问权**。
4. 选择资源组。
5. 为**分配对资源组的访问权**字段选择角色，以支持用户在自己的资源列表上查看资源组，编辑资源组名称或管理用户对该组的访问权。如果希望用户仅有权访问您指定的资源，而无权访问资源所组织成的组，那么可以选择**无访问权**。
6. 选择资源组中的服务，或选择提供对所选组中所有服务的访问权。
7. 选择任意角色组合来为用户分配所需的访问权。此访问权仅适用于为策略选择的资源。它并不授予对实际容器（即资源组）的访问权。
8. 单击**分配**。

### 对资源的访问权
{: #resourceaccess}

要分配对帐户中单个资源的访问权或对帐户中所有资源的访问权，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 在要为其分配访问权的用户所在的行中，选择**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单，然后单击**分配访问权**。
3. 选择**分配对资源的访问权**。
4. 选择服务或选择**所有启用“身份和访问权”的服务**。
5. 选择**所有当前区域**或特定区域（如果系统提示选择）。
6. 选择**所有当前服务实例**或选择特定服务实例。
7. 根据所选择的服务，可能会看到以下字段。如果您未输入这些字段的值，那么会在服务实例级别而非存储区级别来分配策略。
    * **资源类型**：输入**存储区**。
    * **资源标识**：输入存储区的名称。
8. 选择任意角色组合来为用户分配所需的访问权。
9. 单击**分配**。

## 除去访问权
{: #removing_access}

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 选择要除去其访问权的用户名。
3. 在**访问策略**选项卡中，选择要除去的策略所在行上的**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单，然后单击**除去**。  
4. 复查即将除去的用户策略的详细信息，然后通过单击**除去**进行确认。

要使用 CLI 除去用户策略，可以使用 [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_delete#ibmcloud_iam_user_policy_delete) 命令。
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## 复查分配的访问权
{: #review_your_access}

如果需要查看您所在帐户中分配给您的访问权，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
3. 选择您的姓名。
4. 在**访问权策略**部分中，复查分配的访问权。

如果需要更多访问权，您必须联系帐户所有者来更新访问权，或者联系服务或服务实例的管理员来更新 Cloud IAM 访问策略。
