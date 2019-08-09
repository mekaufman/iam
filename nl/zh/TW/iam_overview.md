---

copyright:

  years: 2017, 2019

lastupdated: "2019-07-25"

keywords: user identities, service ID, policies, access management, roles, actions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:external: target="_blank" .external}

# IAM 概念
{: #iamconcepts}

當您想要瞭解 {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 時，有兩個主要概念：身分及存取管理。此外，您還可以瞭解存取群組、資源群組、使用者、角色、存取原則，以及其他。
{: shortdesc}

## 身分
{: #identity}

{{site.data.keyword.Bluemix_notm}} IAM 中的身分概念包含使用者身分、服務及應用程式身分、API 金鑰，以及資源。使用者是透過其 IBM ID 或 SoftLayer 帳戶 ID 進行識別。服務 ID 是在帳戶中使用的第二種身分類型。服務 ID 是 Cloud IAM 特性，用來為服務及應用程式提供個別身分。您可以建立可供需要存取 {{site.data.keyword.Bluemix_notm}} 服務之應用程式使用的服務 ID，因此不需要使用個別使用者認證。

若要使用 API 或 CLI 作為使用者或服務 ID 進行鑑別，可以使用 {{site.data.keyword.cloud_notm}} API 金鑰。這些 API 金鑰是透過 Cloud IAM 所提供，因此，通常無法在 IBM Cloud 外部使用 IBM ID 進行鑑別。使用者也可以有可用來存取標準基礎架構 API 的單一標準基礎架構 API 金鑰；不過，您可以使用 {{site.data.keyword.cloud_notm}} API 金鑰來存取相同的 API 時，不需要這樣做。

IAM 身分概念的最終片段是 {{site.data.keyword.Bluemix_notm}} 資源，這些資源是依其雲端資源名稱 (CRN) 進行識別。如需相關資訊，請參閱[雲端資源名稱](/docs/overview?topic=overview-crn#crn)。

## 存取管理
{: #am}

{{site.data.keyword.Bluemix_notm}} 中存取管理的概念包含一些相互關聯的元件，其中包括使用者、資源、原則、角色、動作及 {{site.data.keyword.Bluemix_notm}} IAM 控制系統，容許使用者對帳戶內的資源採取動作。

{{site.data.keyword.Bluemix_notm}} IAM 遵循常用於許多雲端原生服務的[最終一致](https://en.wikipedia.org/wiki/Eventual_consistency){: external}型樣，這可讓 IAM 在多個全球地區中保持高度可用性和效能。對 IAM 存取原則、授權、服務 ID、API 金鑰、存取群組、資源群組、使用者或任何其他存取控制所做的變更，會進行記錄並跨全世界所有 IAM 元件及具有 IAM 功能的服務進行傳播。在傳播處理程序完成之前，存取變更可能不會生效。

### 使用者
{: #iam-users}

帳戶內的所有使用者都是依其 SoftLayer 帳戶 ID 的 IBM ID 進行識別。使用者可以受邀加入帳戶，並取得資源的存取權。存取原則以經常是您帳戶中使用者的主體開始。存取權可以指派給帳戶管理服務、向下直到實例層次的個別資源，或一組在帳戶資源群組中進行分組的資源。


### 存取群組
{: #access-groups-iam}

可以建立使用者及服務 ID 的群組，以使用一個以上的原則，將相同的存取權指派給群組內的所有實體。使用存取群組，您可以簡化存取權指派處理程序，讓您可以管理較少的原則，並減少帳戶中的原則數目，這會增加效能。 在設定群組之後，您可以藉由選取存取群組作為原則的主體，來開始指派原則。如需相關資訊，請參閱[設定存取群組](/docs/iam?topic=iam-groups)。

### 資源
{: #resources-access-management}

帳戶資源是從服務實例內的型錄或更精細資源中選取的已佈建服務供應項目。從型錄建立這些資源時，會將它們新增至資源群組。IAM 存取管理會啟用細部存取，這表示可在更大範圍設定原則，例如存取資源群組內的所有資源，或存取特定實例內的 {{site.data.keyword.cos_full_notm}} 儲存區這類特定資源類型。


### 存取原則
{: #access-policies-concept}

存取原則是指如何將存取帳戶資源的許可權授與帳戶中的使用者、服務 ID 及存取群組。原則包括主體、目標及角色。主體是您要提供存取權的使用者、服務 ID 或存取群組。原則的目標是您要提供存取權的資源。而這些角色是定義原則目標上存取層次或允許動作的方式。您可以利用容許存取帳戶資源的不同類型原則（資源群組原則、資源實例原則及帳戶層面原則），來存取所有已啟用「身分及存取」的服務，以及所有或一個帳戶管理服務上的原則。取決於您的選擇，可能會有自訂配置選項（例如，定義往下至特定地區中資源的存取權，或定義實例內精細層次之服務特定資源的存取權）。

### 角色
{: #iam-roles-concept}

Cloud IAM 存取角色容許使用者完成原則中所定義資源的特定作業。有兩種類型的存取角色：平台管理及服務存取。 

平台管理角色定義可容許的動作來管理平台層次的資源，例如，使用者存取及建立服務實例。平台角色也適用於可以在帳戶管理服務環境定義內採取的動作，例如，邀請及移除使用者、管理存取群組、管理服務 ID，以及專用型錄供應項目。 

服務存取角色會定義在使用服務（例如呼叫服務 API）的環境定義內可容許的動作。這些角色是根據原則內所選取的服務進行自訂。

### 動作
{: #iam-roles-actions}

動作會對映至 Cloud IAM 角色，讓使用者在獲指派不同角色時只執行特定作業。每一個角色的可容許動作會根據所存取的服務而變更，因為每一個服務都會定義該角色如何對映至服務使用。

### 存取管理系統
{: #access-management-system}

根據指派的原則，Cloud IAM 控制系統會容許或拒絕使用者在服務環境定義內的動作。使用者嘗試完成特定動作時，控制系統會使用原則中所定義的屬性，來判定使用者是否有權執行該作業。
