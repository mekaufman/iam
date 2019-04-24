---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# 管理服务标识 API 密钥
{: #serviceidapikeys}

创建服务标识是为了支持通过在 {{site.data.keyword.Bluemix_notm}} 内部和外部托管的应用程序访问 {{site.data.keyword.Bluemix_notm}} 服务。应用程序使用 API 密钥作为特定服务标识进行认证，并被授予与该服务标识关联的访问权。

一旦创建了服务标识后，就可以开始创建 API 密钥并分配服务策略。每个策略都会指定在使用 API 密钥向服务进行认证时所允许的访问级别。有关创建服务标识和分配策略的更多信息，请参阅[创建和使用服务标识](/docs/iam?topic=iam-serviceids#serviceids)。有关用于管理服务标识 API 密钥的 CLI 命令的详细信息，请参阅[管理 IAM 访问权、API 密钥、服务标识和访问组](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_commands_iam)。

与服务标识关联的每个 API 密钥都将继承已分配给该服务标识的策略。例如，如果希望一个应用程序只能查看某个服务中的资源，那么就要为某个服务标识分配具有查看者角色的策略，然后使用与该服务标识关联的 API 密钥。如果希望另一个应用程序能够具有对服务的完全访问权，那么就要为另一个服务标识分配具有管理员角色的策略，然后使用与该服务标识关联的 API 密钥。

有关更多信息，请参阅[如何使用服务标识的示例](/docs/iam?topic=iam-serviceids#examples_serviceid)。

## 为服务标识创建 API 密钥
{: #create_service_key}

创建与服务标识关联的 API 密钥。

1. 转至**管理** &gt; **访问权 (IAM)**，然后选择**服务标识**。
2. 如果尚未创建服务标识，请创建服务标识。
3. 在**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单中，单击**管理服务标识**。
4. 单击 **API 密钥**。
5. 单击**创建**。
6. 添加名称和描述以轻松识别 API 密钥。
7. 单击**创建**。
8. 通过将 API 密钥复制或下载到安全位置来保存该密钥。

出于安全原因，API 密钥仅在创建时才可复制或下载。如果 API 密钥丢失，必须创建新的 API 密钥。
{: note}

要使用 CLI 为服务标识创建 API 密钥，可以使用 [ibmcloud iam service-api-key-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_create) 命令。
```
ibmcloud iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [--file FILE] [-f, --force]
```
{: codeblock}

## 更新服务标识的 API 密钥
{: #update_service_key}

可以在 UI 中通过编辑用于标识密钥的名称或描述来更新 API 密钥。

1. 转至**管理** &gt; **访问权 (IAM)**，然后选择**服务标识**。
2. 在**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单中，单击**管理服务标识**。
3. 单击 **API 密钥**。
4. 在**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单中，单击**编辑名称和描述**。

要使用 CLI 更新服务标识的 API 密钥，可以使用 [ibmcloud iam service-api-key-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_update) 命令。
```
ibmcloud iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```
{: codeblock}

## 锁定服务标识的 API 密钥
{: #lockkey}

对于表示服务标识身份的 API 密钥，可以通过锁定 API 密钥来防止将其删除。在 UI 中，锁定的 API 密钥由 ![“已锁定”图标](images/locked.svg "已锁定") 图标指示。

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**服务标识**。
2. 确定要为其选择 API 密钥的服务标识所在的行，然后选择服务标识的名称。
3. 单击 **API 密钥**。
4. 将鼠标悬停在要锁定的 API 密钥所在的行上，然后单击**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单以打开选项列表。
5. 单击**锁定 API 密钥**。

您可以随时解锁 API 密钥以更新、删除或添加访问策略，也可以除去 API 密钥。
{: tip}

### 使用 CLI 锁定或解锁服务标识的 API 密钥
{: #lock_unlock_cli}

要锁定服务标识的 API 密钥，请使用以下命令：

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>先决条件</strong>：端点、登录和目标

<strong>命令选项</strong>：
<dl>
  <dt>APIKEY_NAME（必填）</dt>
  <dd>API 密钥的名称，与 APIKEY_UUID 互斥 </dd>
  <dt>APIKEY_UUID（必填）</dt>
  <dd>API 密钥的 UUID，与 APIKEY_NAME 互斥 </dd>
  <dt>SERVICE_ID_NAME（必需）</dt>
  <dd>服务标识的名称，与 SERVICE_ID_UUID 互斥 </dd>
  <dt>SERVICE_ID_UUID（必填）</dt>
  <dd>服务标识的 UUID，与 SERVICE_ID_NAME 互斥 </dd>
  <dt>-f, --force</dt>
  <dd>锁定而不确认</dd>
</dl>

<strong>示例</strong>：

锁定服务标识 `sample-service` 的服务 API 密钥 `sample-key`：

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

要解锁服务标识的 API 密钥，请使用以下命令：

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## 删除服务标识的 API 密钥
{: #delete_service_key}

可以删除与服务标识关联的 API 密钥。但是，删除应用程序当前正在使用的 API 密钥会让该应用程序不能再向服务进行认证。

1. 转至**管理** &gt; **访问权 (IAM)**，然后选择**服务标识**。
2. 如果尚未创建服务标识，请创建服务标识。
3. 在**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单中，单击**管理服务标识**。
4. 单击 **API 密钥**。
5. 在**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单中，单击**删除**。

要使用 CLI 删除服务标识的 API 密钥，可以使用 [ibmcloud iam service-api-key-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_delete) 命令。
```
ibmcloud iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```
{: codeblock}
