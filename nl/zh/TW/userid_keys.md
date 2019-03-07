---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: API key, user API keys, IBM Cloud API keys, manage user keys, create API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 管理使用者 API 金鑰
{: #userapikey}

聯合或非聯合使用者可以建立 API 金鑰以在 CLI 上使用，或是在自動化作業之中使用，以您的使用者身分登入。您可以使用使用者介面或 CLI 來管理 API 金鑰，方法是列出金鑰、建立金鑰、更新金鑰，或刪除金鑰。若要管理與您使用者身分相關聯的 {{site.data.keyword.Bluemix_notm}} API 金鑰，請移至**管理** &gt; **存取 (IAM)**，然後選取**使用者**。接著，從清單中按一下您的名稱，然後選取**使用者詳細資料**選項，以查看您的 API 金鑰清單，以及說明和日期。然後，您可以建立、編輯或刪除 API 金鑰。再者，如需可用 CLI 指令的完整清單，請參閱 [`ibmcloud iam api-keys`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_keys)。

身為[聯合使用者](/docs/account?topic=account-signup#signup)，您可以使用 `IBMCLOUD_API_KEY` 環境變數來使用 API 金鑰進行登入。如需使用 API 金鑰進行登入的相關資訊，請參閱[使用聯合 ID 進行登入](/docs/iam?topic=iam-federated_id#federated_id)。
{:shortdesc}

## 建立 API 金鑰
{: #create_user_key}

身為 {{site.data.keyword.Bluemix_notm}} 使用者，當您啟用程式或 Script 而不將密碼配送至 Script 時，建議您使用 API 金鑰。使用 API 金鑰的好處在於使用者或組織可以為不同的程式建立數個 API 金鑰，而且可以在洩密的情況下獨立刪除，而不會干擾其他 API 金鑰甚至使用者。您可以建立最多 20 個 API 金鑰。

若要在使用者介面中建立使用者身分的 API 金鑰，請完成下列步驟：

1. 移至**管理** &gt; **存取 (IAM)**，然後選取**使用者**。接著，從清單中按一下您的名稱，然後選取**使用者詳細資料**選項。
2. 按一下**建立 {{site.data.keyword.Bluemix_notm}} API 金鑰**。
3. 輸入 API 金鑰的名稱及說明。
4. 按一下**建立**。
5. 然後，按一下**顯示**以顯示要複製的 API 金鑰，並儲存它以供之後使用，或按一下**下載**。

基於安全理由，只可在建立時複製或下載 API 金鑰。如果 API 金鑰遺失，您必須建立新的 API 金鑰。
{: tip}

若要使用 CLI 來建立 API 金鑰，請使用下列指令：

1. 在命令提示字元中輸入 `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]`，並指定名稱、說明和儲存金鑰用的檔案。請參閱下列範例：

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```


## 更新 API 金鑰
{: #update_user_key}

如果您想要變更 API 金鑰的名稱或說明，請在使用者介面或 CLI 中完成下列步驟。

若要編輯 API 金鑰，請完成下列步驟：

1. 移至**管理** &gt; **存取 (IAM)**，然後選取**使用者**。接著，從清單中按一下您的名稱，然後選取**使用者詳細資料**選項。
2. 識別您要更新的 API 金鑰列，然後從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中選取**編輯**。
3. 更新 API 金鑰的資訊。
4. 按一下**套用**。

若要使用 CLI 來編輯 API 金鑰，請輸入下列指令：

1. 在命令提示字元中輸入 `ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]`，並指定金鑰的舊名稱、新名稱和新說明。例如：

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## 鎖定 API 金鑰
{: #lock_user_key}

針對代表使用者身分的平台 API 金鑰，您可以將其鎖定，以防止 API 金鑰遭到刪除。已鎖定的 API 金鑰會以 ![「已鎖定」圖示](images/locked.svg "已鎖定") 圖示來表示。您可以利用使用者介面或 CLI 來鎖定及解除鎖定 API 金鑰。

### 從使用者介面鎖定及解除鎖定 API 金鑰
{: #lockui}

1. 移至**管理** &gt; **存取 (IAM)**，然後選取**使用者**。接著，從清單中按一下您的名稱，然後選取**使用者詳細資料**選項。
2. 識別您要鎖定的 API 金鑰列，然後從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中選取**鎖定**。

您可以隨時解除鎖定 API 金鑰，以從帳戶中更新或移除 API 金鑰。從表格中選取您要解除鎖定的 API 金鑰，然後從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中選取**解除鎖定**。
{: tip}

### 使用 CLI 來鎖定及解除鎖定 API 金鑰
{: #lockcli}

若要鎖定 API 金鑰，請使用下列指令：

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要鎖定之 API 金鑰的名稱，與 UUID 不能同時使用。</dd>
<dt>UUID（必要）</dt>
<dd>要鎖定之 API 金鑰的 UUID，與 NAME 不能同時使用。</dd>
<dt>-f, --force</dt>
<dd>強制鎖定，而不進行確認。</dd>
</dl>

<strong>範例</strong>：

鎖定 API 金鑰 `test-api-key`

```
ibmcloud iam api-key-lock test-api-key
```

若要解除鎖定 API 金鑰，請執行下列指令：

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>NAME（必要）</dt>
<dd>要解除鎖定之 API 金鑰的名稱，與 UUID 不能同時使用。</dd>
<dt>UUID（必要）</dt>
<dd>要解除鎖定之 API 金鑰的 UUID，與 NAME 不能同時使用。</dd>
<dt>-f, --force</dt>
<dd>強制解除鎖定，而不進行確認。</dd>
</dl>

<strong>範例</strong>：

解除鎖定 API 金鑰 `test-api-key`

```
ibmcloud iam api-key-unlock test-api-key
```


## 刪除 API 金鑰
{: #delete_user_key}

如果您使用金鑰旋轉策略，則可能會想要刪除舊的金鑰，並取代為新的金鑰。

若要刪除 API 金鑰，請完成下列步驟：

1. 移至**管理** &gt; **存取 (IAM)**，然後選取**使用者**。接著，從清單中按一下您的名稱，然後選取**使用者詳細資料**選項。
2. 識別您要刪除的 API 金鑰列，然後從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中選取**刪除**。
3. 然後，按一下**刪除**來確認刪除。

若要使用 CLI 刪除 API 金鑰，請執行下列動作：
1. 在命令提示字元中輸入 `ibmcloud iam api-key-delete NAME`，並指定所要刪除的金鑰名稱。
