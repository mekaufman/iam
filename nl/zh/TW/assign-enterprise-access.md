---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise policy, enterprise access, assign enterprise access, enterprise service

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# 指派企業存取權
{: #assign-access-enterprise}

若要指派使用者存取權以管理 {{site.data.keyword.Bluemix}} 企業，您必須邀請他們加入企業帳戶，然後指派企業帳戶管理服務的存取權。
{:shortdesc}

管理[企業](/docs/account?topic=account-enterprise)的存取權需要企業帳戶內的存取原則。當您在企業的子帳戶內將「企業」帳戶管理服務原則指派給使用者時，使用者無法管理帳戶所屬的企業。取決於企業帳戶內使用者獲指派的「企業」帳戶管理服務角色，使用者可以執行特定動作：

* 在企業中建立新帳戶
* 建立及命名帳戶群組
* 在帳戶群組之間移動帳戶
* 將現有帳戶匯入至企業
* 更新企業名稱或網域
* 檢視企業的用量報告、特定帳戶群組及其中的帳戶群組或帳戶，或特定帳戶

提供使用者存取企業服務的原則，可以在整個企業上進行指派，或只在特定帳戶群組或單一帳戶上進行指派。
{: tip}

一般而言，企業帳戶本身不包含許多資源。相反地，資源會建立在企業的子帳戶中。它是在使用者可以受邀加入的其中每一個帳戶內，而且還會提供它存取權，以管理及使用資源。使用者在企業帳戶中具有的存取權及成員資格，不適用於企業階層中的帳戶群組及子帳戶。使用者管理及存取管理與每一個帳戶保持隔離，如同您在下圖所述內容看到的一般。

第一個圖表顯示如何將原則指派給企業帳戶中的使用者，以管理整個企業或範圍定為帳戶群組的原則，這提供的存取權只能管理該帳戶群組，以及在其中進行分組的其他帳戶群組或子帳戶。

![企業存取權](images/enterprise-access.svg "此圖顯示企業使用者具有只能管理企業實體的存取權。"){: caption="圖 1. 企業存取權的圖表" caption-side="bottom"}

在決定存取範圍時，原則的目標和角色很重要。企業中的使用者、服務 ID 或存取群組是原則的主體，其可以跨整個企業、可能包含其他帳戶群組和帳戶的帳戶群組，或甚至單一帳戶完成企業管理作業。例如，如果您將「企業」帳戶管理服務上的存取原則指派給企業帳戶中的使用者，而目標範圍設定為特定帳戶群組，則他們可以存取帳戶群組內的完整作業。當目標設為特定帳戶群組或帳戶時，使用者無法完成影響整個企業的動作，例如更新企業名稱或網域。

您可以將適用的企業存取原則指派給子帳戶中的使用者，以僅管理該帳戶或其中包含的資源。例如，如果您將「企業」帳戶管理服務上的角色指派給子帳戶中的使用者，則使用者無法在企業帳戶層級採取動作。您必須將他們新增至企業帳戶，並指派該環境定義中的原則。

![帳戶存取權](images/account-access.svg "此圖顯示子帳戶使用者僅具有其帳戶內的存取權，沒有企業其餘部分的存取權"){: caption="圖 2. 帳戶存取權的圖表" caption-side="bottom"}

## 特定工作的必要原則
{: #sample-enterprise-policies}

取決於需要完成的工作，非企業擁有者的使用者可能需要存取原則的組合。下列範例提供一組存取原則，您必須將這些原則指派給企業中的使用者，才能完成特定作業。

如果您是不屬於企業的帳戶擁有者，但想要帳戶中的另一位使用者能夠將您帳戶轉換成企業，則可以將「計費」帳戶管理服務的「管理者」角色指派給該使用者。
{: note}

### 在企業中檢視用量及管理計費
{: #billing-admin-enterprise}

如需使用者能夠檢視企業中所有帳戶的[用量報告](/docs/billing-usage?topic=billing-usage-enterprise-usage)、進行付款，以及檢視發票，您必須指派下列所有存取原則：

* 企業帳戶中「企業」帳戶管理服務的用量報告檢視者角色
* 企業帳戶中「計費」帳戶管理服務的「管理者」角色

### 將現有帳戶匯入至企業
{: #add-account}

為了讓使用者能夠[將現有 IBM Cloud 帳戶匯入至企業](/docs/account?topic=account-enterprise-add#add-accounts)，您必須指派下列所有存取原則：

* 要匯入之帳戶中「計費」帳戶管理服務的「管理者」角色
* 帳戶群組或企業帳戶（將新增帳戶至其中）之「企業」帳戶管理服務的「管理者」或「編輯者」角色
* 企業帳戶之「計費」帳戶管理服務的「管理者」角色

### 移動帳戶
{: #move-accountgroup}

為了讓使用者能夠[在企業內移動帳戶](/docs/account?topic=account-enterprise-organize#move-accounts)，您必須指派下列存取原則：

* 企業帳戶中「計費」帳戶管理服務的「管理者」角色

然後，使用下列兩個選項之一：

* 整個企業之「企業」帳戶管理服務的「管理者」或「編輯者」角色
* 此帳戶將移至其中之現行及目標帳戶群組的「管理者」或「編輯者」角色

如需使用者可以為每一個角色採取哪些動作的詳細資料，請參閱[帳戶管理服務的動作及角色](/docs/iam?topic=iam-account-services#account-management-actions-roles)。

## 在主控台中指派存取權
{: #enterprise-access-console}

若要將存取原則指派給企業帳戶中的現有使用者，請完成下列步驟：

您可以將原則的目標設為整個企業、特定帳戶群組（可以包含其內所有帳戶的存取權），或甚至是帳戶群組中的特定帳戶。
{: tip}

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表，然後按一下**指派存取權**。
3. 選取以指派**帳戶管理服務**的存取權。
4. 選取**企業**作為服務。
5. 選用項目：將原則範圍設定為企業、帳戶群組或帳戶。
6. 選取任何角色組合，以指派想要的存取權。

|角色|動作|
|:-------|----------|
|檢視者|檢視企業、帳戶群組及帳戶|
|操作員|檢視企業、帳戶群組及帳戶|
|編輯者|藉由編輯名稱及網域來檢視及更新企業、建立帳戶及帳戶群組、檢視用量報告，以及匯入帳戶|
|管理者|藉由編輯名稱及網域來檢視及更新企業、建立帳戶及帳戶群組、在帳戶群組之間移動帳戶、匯入現有帳戶，以及檢視用量報告|
|用量報告檢視者|檢視企業、帳戶及帳戶群組，以及檢視企業中所有帳戶的用量報告|
{: caption="表 1.「企業」帳戶管理服務的角色與範例動作" caption-side="top"}

## 使用 CLI 指派存取權
{: #enterprise-cli-policy}

若要為使用者建立新的存取原則，請執行 **`ibmcloud iam user-policy-create`** 指令。在指令範例中，使用 JSON 檔案來指定原則詳細資料。請檢閱[使用 API 指派存取權](#enterprise-api-policy)一節，以取得 JSON 檔案中所包含內容的範例。

建立使用者原則：
```
$ ibmcloud iam user-policy-create name@example.com -f policy.json
```

如需相關資訊，請參閱 [ibmcloud iam user-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_create)。

## 使用 API 指派存取權
{: #enterprise-api-policy}

下列要求範例會為具有範圍設定為帳戶群組的企業帳戶中「企業」服務的「編輯者」角色的使用者指派一個原則。此類型的原則為階層式，並適用於階層中的所有後代物件，這表示在指定目標帳戶群組內的所有帳戶群組或帳戶。  

```
curl -X POST \
'https://iam.cloud.ibm.com/v1/policies' \
-H 'Authorization: $TOKEN' \
-H 'Content-Type: application/json' \
-d '{
  "type": "access",
  "subjects": [
    {
      "attributes": [
        {
          "name": "iam_id",
          "value": "<IBMid-example>"
        }
      ]
    }
  ],
  "roles":[
    {
      "role_id": "crn:v1:bluemix:public:iam::::role:Editor"
    }
  ],
  "resources":[
    {
      "attributes": [
        {
          "name": "accountId",
          "value": "<account-id-example>"
        },
        {
          "name": "serviceName",
          "value": "enterprise"
        },
        {
          "name": "accountGroupId",
          "value": "<accountGroupId-example>"
        }
      ]
    }
  ]
}'
```
{: codeblock}

如需相關資訊，請參閱[建立原則](https://cloud.ibm.com/apidocs/iam-policy-management#create-a-policy){: external}。
