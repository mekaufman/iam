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


# 設定存取群組
{: #groups}

您可以建立存取群組，將一組使用者和服務 ID 組織成單一實體，方便您指派存取權。您可以指派單一原則給群組，而不是針對每個個別使用者或服務 ID 指派相同的存取權多次。
{:shortdesc}

若要管理或建立新的存取群組，您必須是帳戶擁有者、帳戶中「IAM 存取群組」服務的管理者或編輯者，或是所有「帳戶管理服務」的受指派管理者或編輯者。此外，管理者或編輯者可以藉由建立存取原則（其中資源是存取群組 ID）而獲指派存取權來管理個別群組。如需 IAM 存取群組服務之存取原則及角色的相關資訊，請參閱 [IAM 存取](/docs/iam?topic=iam-userroles#userroles)。

若要更輕鬆地指派及管理存取權，您可以設定資源群組，來組織您想要一群使用者能存取的一組資源。設定好資源群組之後，您可以指派一個原則，來提供對該群組內所有資源的存取權，而不是為您帳戶內的個別服務實例建立存取原則。
{: tip}

## 建立存取群組
{: #create_ag}

若要建立存取群組，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**存取群組**。
2. 按一下**建立**。
3. 輸入群組的名稱和選用說明，然後按一下**建立**。

接下來，藉由新增使用者或服務 ID 繼續設定群組：

1. 選取您要新增到的群組名稱。
2. 按一下**使用者**標籤上的**新增使用者**。 
3. 從清單選取您要新增的使用者，然後按一下**新增至群組**。
4. 若要將服務 ID 新增至群組，請按一下**服務 ID** 標籤，然後按一下**新增服務 ID**。
5. 從清單選取您要新增的 ID，然後按一下**新增至群組**。

您可以選取**移除群組**選項，來刪除群組。當您從帳戶移除群組時，會從群組移除所有使用者及服務 ID，以及指派給該群組的所有存取權。
{: note}

若要使用 CLI 建立存取群組，您可以使用 [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) 指令。
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}


## 指派群組存取權
{: #access_ag}

在您以使用者和服務 ID 設定群組之後，可以將一般存取原則指派給群組。請記住，為群組設定的任何原則都會適用於群組內的所有實體。

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**存取群組**。
2. 選取您要指派存取權的群組名稱。 
3. 按一下**存取原則**。
4. 按一下**指派存取權**。 
5. 選擇依資源群組內的資源指派存取權、依帳戶內可用的個別資源指派存取權，還是依帳戶管理服務指派存取權。

若要使用 CLI 建立存取群組原則，您可以使用 [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) 指令。
```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}


