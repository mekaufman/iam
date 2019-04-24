---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

keywords: access groups, access group, create group, assign access to group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# 设置访问组
{: #groups}

可以创建一个访问组，用于将一组用户和服务标识组织成单个实体，供您轻松分配访问权。您可以将单个策略分配给该组，而不用对每个用户或服务标识多次指定相同的访问权。
{:shortdesc}

要管理访问组或创建新的访问组，您必须是帐户所有者，帐户中 IAM 访问组服务的管理员或编辑者，或者是为所有帐户管理服务分配的管理员或编辑者。此外，可以通过创建访问策略（其中的资源是访问组标识），向管理员或编辑者分配管理单个组的访问权。有关 IAM 访问组服务的访问策略和角色的更多信息，请参阅 [IAM 访问权](/docs/iam?topic=iam-userroles#userroles)。

要更轻松地分配和管理访问权，可以设置资源组来组织希望用户组有权访问的一组资源。设置资源组后，可以为其分配策略，用于授予对该组内所有资源的访问权，而不用为帐户内的各个服务实例分别创建访问策略。
{: tip}

## 创建访问组
{: #create_ag}

要创建访问组，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**访问组**。
2. 单击**创建**。
3. 输入组的名称和可选描述，然后单击**创建**。

接下来，继续通过添加用户或服务标识来设置组：

1. 选择要添加到的目标组的名称。
2. 单击**用户**选项卡上的**添加用户**。
3. 从列表中选择要添加的用户，然后单击**添加到组**。
4. 要将服务标识添加到组，请单击**服务标识**选项卡，然后单击**添加服务标识**。
5. 从列表中选择要添加的标识，然后单击**添加到组**。

可以通过选择**除去组**选项来删除组。从帐户中除去组时，将除去该组中的所有用户和服务标识以及分配给该组的所有访问权。
{: note}

要使用 CLI 创建访问组，可以使用 [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) 命令。
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}


## 为组分配访问权
{: #access_ag}

使用用户和服务标识设置组后，可以为该组分配公共访问策略。请记住，您为该组设置的任何策略都将应用于该组内的所有实体。

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**访问组**。
2. 选择要为其分配访问权的组的名称。
3. 单击**访问策略**。
4. 单击**分配访问权**。
5. 选择是按资源组中的资源、按帐户中可用的单个资源还是按帐户管理服务分配访问权。

要使用 CLI 创建访问组策略，可以使用 [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) 命令。
```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}
