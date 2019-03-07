---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: service ID, service ID API key, lock service ID API key, delete service ID API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# 管理服務 ID API 金鑰
{: #serviceidapikeys}

建立服務 ID，以啟用在 {{site.data.keyword.Bluemix_notm}} 內外部管理的應用程式對您 {{site.data.keyword.Bluemix_notm}} 服務的存取。應用程式會使用 API 金鑰來鑑別為特定服務 ID，並獲指派與該服務 ID 相關聯的存取權。

在您建立服務 ID 之後，即可開始建立 API 金鑰，以及指派服務原則。每一個原則都會指定在使用 API 金鑰向服務進行鑑別時所容許的存取層次。如需建立服務 ID 以及指派原則的相關資訊，請參閱[建立及使用服務 ID](/docs/iam?topic=iam-serviceids#serviceids)。如需用來管理服務 ID API 金鑰之 CLI 指令的詳細資料，請參閱[管理 IAM 存取權、API 金鑰、服務 ID 及存取群組](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_commands_iam)。

每一個與服務 ID 相關聯的 API 金鑰都會繼承已指派給服務 ID 的原則。例如，如果您要某個應用程式只能檢視服務內的資源，則需要使用與服務 ID 相關聯的 API 金鑰，而此 API 金鑰具有以「檢視者」角色指派的原則。而且，如果您要另一個應用程式能夠具有服務內的完整存取權，則需要使用與第二個服務 ID 相關聯的 API 金鑰，而此 API 金鑰具有以「管理者」角色指派的原則。

如需相關資訊，請參閱[如何使用服務 ID 的範例](/docs/iam?topic=iam-serviceids#examples_serviceid)。

## 建立服務 ID 的 API 金鑰
{: #create_service_key}

建立要與服務 ID 相關聯的 API 金鑰。

1. 移至**管理** &gt; **存取 (IAM)**，然後選取**服務 ID**。
2. 如果您尚未建立服務 ID，請建立服務 ID。
3. 從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中，按一下**管理服務 ID**。
4. 按一下 **API 金鑰**。
5. 按一下**建立**。
6. 新增名稱及說明，以輕鬆識別 API 金鑰。
7. 按一下**建立**。
8. 複製 API 金鑰或將其下載至安全位置，以進行儲存。

基於安全理由，只可在建立時複製或下載 API 金鑰。如果 API 金鑰遺失，您必須建立新的 API 金鑰。
{: note}

若要使用 CLI 建立服務 ID 的 API 金鑰，您可以使用 [ibmcloud iam service-api-key-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_create) 指令。
```
ibmcloud iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [--file FILE] [-f, --force]
```
{: codeblock}

## 更新服務 ID 的 API 金鑰
{: #update_service_key}

您可以在使用者介面中編輯用來識別 API 金鑰的名稱或說明，以更新 API 金鑰。

1. 移至**管理** &gt; **存取 (IAM)**，然後選取**服務 ID**。
2. 從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中，按一下**管理服務 ID**。
3. 按一下 **API 金鑰**。
4. 從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中，按一下**編輯名稱及說明**。

若要使用 CLI 更新服務 ID 的 API 金鑰，您可以使用 [ibmcloud iam service-api-key-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_update) 指令。
```
ibmcloud iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```
{: codeblock}

## 鎖定服務 ID 的 API 金鑰
{: #lockkey}

針對代表服務 ID 身分的 API 金鑰，您可以將其鎖定，以防止 API 金鑰被刪除。已鎖定的 API 金鑰在使用者介面中會以 ![「已鎖定」圖示](images/locked.svg "已鎖定") 圖示來表示。

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**服務 ID**。
2. 識別您要為其選取 API 金鑰的服務 ID 列，然後選取服務 ID 的名稱。
3. 按一下 **API 金鑰**。
4. 將滑鼠移至您要鎖定的 API 金鑰列上方，然後按一下**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表，以開啟選項清單。
5. 按一下**鎖定 API 金鑰**。

您可以隨時解除鎖定 API 金鑰，以更新、刪除或新增存取原則，或是移除 API 金鑰。
{: tip}

### 使用 CLI 來鎖定或解除鎖定服務 ID API 金鑰
{: #lock_unlock_cli}

若要鎖定服務 ID API 金鑰，請使用下列指令：

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
<dl>
  <dt>APIKEY_NAME（必要）</dt>
  <dd>API 金鑰的名稱，與 APIKEY_UUID 不能同時使用</dd>
  <dt>APIKEY_UUID（必要）</dt>
  <dd>API 金鑰的 UUID，與 APIKEY_NAME 不能同時使用</dd>
  <dt>SERVICE_ID_NAME（必要）</dt>
  <dd>服務 ID 的名稱，與 SERVICE_ID_UUID 不能同時使用</dd>
  <dt>SERVICE_ID_UUID（必要）</dt>
  <dd>服務 ID 的 UUID，與 SERVICE_ID_NAME 不能同時使用</dd>
  <dt>-f, --force</dt>
  <dd>鎖定而不進行確認</dd>
</dl>

<strong>範例</strong>：

鎖定服務 ID `sample-service` 的服務 API 金鑰 `sample-key`：

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

若要解除鎖定服務 ID API 金鑰，請使用下列指令：

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## 刪除服務 ID 的 API 金鑰
{: #delete_service_key}

您可以刪除與服務 ID 相關聯的 API 金鑰。不過，刪除應用程式目前正在使用的 API 金鑰，該應用程式就無法向服務進行鑑別。

1. 移至**管理** &gt; **存取 (IAM)**，然後選取**服務 ID**。
2. 如果您尚未建立服務 ID，請建立服務 ID。
3. 從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中，按一下**管理服務 ID**。
4. 按一下 **API 金鑰**。
5. 從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中，按一下**刪除**。

若要使用 CLI 刪除服務 ID 的 API 金鑰，您可以使用 [ibmcloud iam service-api-key-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_delete) 指令。
```
ibmcloud iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```
{: codeblock}
