---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: service ID, service ID access, managing access for service IDs

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 管理服務 ID 存取原則
{: #serviceidpolicy}

當您建立服務 ID 時，可以指派該服務 ID 的服務原則，以控制使用它向服務進行鑑別時所容許的存取層次。您可以隨時變更現有原則、刪除原則或指派新原則，來更新這些已指派存取原則。
{:shortdesc}

如果您刪除或編輯目前所使用服務 ID 的現有原則，則可能會導致服務岔斷。
{: note}

## 指派新存取權
{: #access_new}

若要指派資源群組中所有資源的存取權，或只指派資源群組內一項服務的存取權，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**服務 ID**。
2. 從表格中，選取您要指派服務原則的服務 ID。
3. 按一下**存取原則**。
4. 按一下**指派存取權**。
5. 選取以**依資源群組指派**。
6. 選取資源群組。
7. 選擇**指派資源群組存取權**欄位的角色。此選項可讓使用者在其資源清單上檢視資源群組、編輯資源群組名稱，或管理使用者對群組的存取權。如果您要使用者只能存取您指定的資源，而非其指派的群組，則可以選取**不可存取**。
8. 選取資源群組內的服務，或選取以提供所選取群組內所有服務的存取權。
9. 選擇任何角色組合，以指派使用者想要的存取權。此存取權僅適用於您為原則選取的資源。並無法存取本身為資源群組的實際容器。
10. 選取**指派**。

若要指派帳戶中個別資源的存取權，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**服務 ID**。
2. 從表格中，選取您要指派服務原則的服務 ID。
3. 按一下**存取原則**。
4. 按一下**指派存取權**。
5. 選取以**依資源指派**。
6. 選取服務。
7. 當系統提示您時，請選取**所有現行地區**或特定地區。

8. 選取**所有現行服務實例**，或選取特定服務實例。
9. 視您選取的服務而定，可能會看到下列欄位。如果您不輸入這些欄位的值，則會在服務實例層次指派原則，而非儲存區層次。
    * **資源類型**：輸入 **bucket**。
    * **資源 ID**：輸入您的儲存區名稱。
10. 選擇任何角色組合，以指派使用者想要的存取權。
11. 選取**指派**。

若要指派對個別帳戶管理服務或所有帳戶管理服務的存取權，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**服務 ID**。
2. 從表格中，選取您要指派服務原則的服務 ID。
3. 按一下**存取原則**。
4. 按一下**指派存取權**。
5. 選取以指派對**帳戶管理服務**的存取權。
6. 選取**所有帳戶管理服務**，或選取特定的帳戶管理服務。
7. 選取任何角色組合，以指派想要的存取權。

您可能會收到訊息，指出您選取的詳細資料已經有原則存在。如果所要建立的原則具有完全相同的詳細資料和角色，系統會提示您變更新的原則，因為不允許重複的原則。如果您要建立的原則具有與現有原則相同的詳細資料，但角色指派不同，系統會提示您檢閱現有的原則，並更新為您要指派的角色。
{: tip}

## 編輯現有存取權
{: #access_edit}

若要編輯現有原則，請執行下列動作：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**服務 ID**。
2. 從表格中，選取您要編輯服務原則的服務 ID。
3. 按一下**存取原則**。
4. 識別您要編輯的原則列，然後從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中選取**編輯原則**。
5. 進行變更，然後儲存原則。

若要使用 CLI 更新服務原則，您可以使用 [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_update#ibmcloud_iam_service_policy_update) 指令。
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

編輯服務 ID 的存取權時，您可能會收到有關不容許重複原則的訊息。如果您是編輯現有原則，而您所做的變更與已指派的存取權衝突，則可以選擇變更目前所編輯的原則以提供不同的存取權，或者您可以前往發生衝突的現有原則進行檢閱，並依需要進行變更。如果已存在的重複原則符合您的需求，建議您刪除正在編輯的原則。
{: tip}

## 移除存取權
{: #access_remove}

若要移除現有原則，請執行下列動作

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**服務 ID**。
2. 從表格中，選取您要刪除服務原則的服務 ID。
3. 按一下**存取原則**。
4. 識別您要刪除的原則列，然後從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中選取**移除**。
5. 檢閱您即將移除之原則的詳細資料，然後按一下**移除**進行確認。

若要使用 CLI 刪除服務原則，您可以使用 [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_update#ibmcloud_iam_service_policy_delete) 指令。
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
