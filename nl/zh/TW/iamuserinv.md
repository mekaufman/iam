---

copyright:

  years: 2015, 2019

lastupdated: "2019-06-25"

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

# 邀請使用者
{: #iamuserinv}

使用 {{site.data.keyword.Bluemix}} Identity and Access Management (IAM) 可以邀請使用者、取消邀請，以及將擱置邀請重新傳送給受邀使用者。此外，您還可以一次邀請單一使用者或多位使用者。
{:shortdesc}

若要邀請使用者並管理未完成的邀請，您必須是帳戶擁有者、組織管理員、含使用者管理服務上具有「編輯者」或更高角色之 IAM 存取原則的使用者，或者必須具有用來新增使用者的標準基礎架構許可權。

## 設定邀請
{: #invitations}

若要在您帳戶中邀請使用者，或管理使用者邀請，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**使用者**。
2. 按一下**邀請使用者**。
3. 指定使用者的電子郵件位址。如果您使用單一邀請來邀請多位使用者，則他們都會獲指派相同的存取權。
4. 新增您管理的一個以上存取選項。您必須至少指派一個存取選項。對於您未新增及配置的任何其他存取選項，會指派預設值：**不可存取**。視您獲授權管理的選項而定，您可能會看到下列其中一個或所有存取選項：

  * **服務**
  * **Cloud Foundry 存取權**
  * **標準基礎架構存取**。

  如需相關資訊，請參閱[指派使用者存取權](/docs/iam?topic=iam-iamuserinv#assignaccess)。

如果判定使用者不需要存取權，您可以針對「狀態」直欄中的「處理中」或「擱置中」狀態所顯示的任何使用者，取消邀請。如果受邀使用者沒有收到邀請，您可以將邀請重新傳送給處於「擱置中」狀態的任何使用者。

### 使用 CLI 來邀請使用者
{: #cli-invite}

若要使用指令行介面 (CLI) 來邀請使用者，請執行下列指令：

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

使用 CLI，即可選擇指派 Cloud Foundry 存取權或未指派任何存取權，並稍後處理存取權的指派。如需指令參數的相關資訊，請參閱 [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite)。 

### 使用 API 來邀請使用者
{: #api-invite}

您可以使用 [API](https://cloud.ibm.com/apidocs/user-management#invite-users){: external} 大量邀請使用者。單一邀請中所含的所有使用者都會獲指派相同的存取權。當您使用 API 邀請使用者時，會使用每個以引號括住的項目的逗點區隔清單來輸入電子郵件，例如：


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

## 從邀請指派使用者存取權
{: #assignaccess}

您可以藉由指派 {{site.data.keyword.Bluemix}} IAM 原則、Cloud Foundry 存取及標準基礎架構許可權，以在邀請使用者時為其指派存取權。視您獲授權管理的存取選項而定，您可以邀請帳戶、資源群組、組織、空間、服務實例及標準基礎架構的使用者，並為其提供存取權。下列各節說明可指派給受邀使用者的三種存取權類型。

### 服務
{: #invite_services}

當您邀請新的使用者時，可以藉由建立起始 {{site.data.keyword.Bluemix_notm}} IAM 存取原則來指派存取權。在「服務」區段中，您可以將下列項目的存取權提供給使用者：帳戶管理服務、資源群組中具有管理資源群組存取權的服務，或帳戶中的個別資源。

使用者接受邀請之後，您可以指派其他存取權。如需編輯原則來新增額外角色、指派其他存取權或移除使用者原則的詳細資料，請參閱[管理對資源的存取權](/docs/iam?topic=iam-iammanidaccser#iammanidaccser)。

視您在指派原則時選取的服務而定，您可能看不到下列程序中所述的所有欄位。
{: note}

#### 帳戶管理服務存取權
{: #invite_acct_mgmt}

若要將部分責任委派給帳戶擁有者，您可以提供使用者對帳戶管理服務的存取權。例如，您可以委派檢視計費及用量、邀請及移除使用者、管理存取群組或管理服務 ID 的能力。您可以提供對所有帳戶管理服務或只有一個帳戶管理服務的存取權。

1. 在「邀請使用者」頁面上，展開「服務」區段。
2. 從**指派對右列項目的存取權**清單，選取**帳戶管理服務**。 
3. 選取**所有帳戶管理服務**，或選取特定的帳戶管理服務。
4. 選取任何角色組合，以指派想要的存取權。

#### 資源群組存取權
{: #invite_rgs}

您可以指派資源群組內所有服務的存取權，或資源群組中單一服務類型的存取權。

1. 在「邀請使用者」頁面上，展開「服務」區段。
2. 從**指派對右列項目的存取權**清單，選取**資源群組**。
3. 選取資源群組。
4. 從**指派對資源群組的存取權**清單選取角色，讓使用者在資源清單上檢視資源群組、編輯資源群組名稱，或管理使用者對群組的存取權。如果您要使用者只能存取您指定的資源，而非其所屬組織內的群組，則可以選取**不可存取**。
5. 選取資源群組內的服務，或選取以提供所選取群組內所有服務的存取權。
6. 選取任何角色組合，以指派想要的存取權。此存取權僅適用於您為原則選取的資源。它未提供對本身為資源群組之實際容器的存取權。

#### 資源存取權
{: #invite_resources}

您可以將帳戶內單一資源的存取權指派給實例。

1. 在「邀請使用者」頁面上，展開「服務」區段。
2. 從**指派對右列項目的存取權**清單，選取**資源**。 
3. 選取服務。
4. 當系統提示您時，選取**所有現行地區**或特定地區。
5. 選取**所有現行服務實例**，或選取特定服務實例。
6. 視您選取的服務而定，可能會看到下列欄位。如果您不輸入這些欄位的值，原則會在服務實例層次指派，而非儲存區層次。
    * **資源類型**：輸入 `bucket`。
    * **資源 ID**：輸入您的儲存區名稱。
7. 選取任何角色組合，以指派想要的存取權。

如需指派存取權時所使用角色的相關資訊，請參閱 [IAM 存取](/docs/iam?topic=iam-userroles#iamusermanrol)。

### Cloud Foundry 存取權
{: #invite_cf}

當您邀請新的使用者時，可以選擇將使用者新增至帳戶中的組織。如果您將使用者新增至組織，則可以為他或她指派一個組織角色。然後，請選擇授權受邀使用者，以受指派的空間角色存取所選取組織中的任何或所有空間。

1. 在「邀請使用者」頁面上，展開「Cloud Foundry 存取權」區段。
2. 選取要新增使用者的組織。
3. 選取組織角色，以定義所選取組織的存取層次。
4. 選用項目：按一下**新增組織角色**，以指定額外角色。
5. 選取**所有現行地區**或特定地區。
6. 選取**所有現行空間**或特定空間。
7. 選取空間角色，以定義所選取空間的存取層次。
8. 選用項目：按一下**新增空間角色**，以指定額外角色。

如需指派存取權時所使用角色的相關資訊，請參閱 [Cloud Foundry 角色](/docs/iam?topic=iam-cfaccess#cfroles)。

您可以使用 [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite) CLI 指令來新增 Cloud Foundry 角色，但必須使用主控台來指派其他存取權或許可權。
{: tip}

### 標準基礎架構存取權
{: #invite_classicinfra}

指派的許可權自動受限於您所擁有的許可權子集。您會成為所邀請的任何使用者的母項使用者。

1. 在「邀請使用者」頁面上，展開「標準基礎架構存取權」區段。
2. 選取許可權集，以指派預先定義的大量許可權。

新增使用者之後，會個別授與裝置存取權。在主控台中，移至使用者的**標準基礎架構**存取選項。
{: note}

如需在將使用者新增至您的帳戶之後為其配置存取權的相關資訊，請參閱[管理標準基礎架構存取](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra)。

## 新增僅限 VPN 使用者
{: #add-vpn-only}

身為帳戶擁有者或具有「管理使用者」標準基礎架構許可權的使用者，您可以新增僅限 VPN 使用者。

1. 在「使用者」頁面上，按一下**新增僅限 VPN 使用者**。
2. 輸入使用者的個人資訊詳細資料。
3. 按一下**儲存**。
