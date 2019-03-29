---

copyright:

  years: 2019

lastupdated: "2019-03-25"

keywords: public access, anonymous access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 啟用對資源的公用存取權
{: #public}

對資源的公用存取權讓所有使用者及服務 ID 能夠存取您帳戶中的特定資源。例如，這表示使用者或服務 ID 不需要向 {{site.data.keyword.Bluemix}} 進行鑑別，即可存取 {{site.data.keyword.cos_full_notm}} 儲存區中的資訊。只有特定服務支援提供對服務之特定資源類型公用存取權的功能。因此，您會受到限制，只能為支援此特性的服務建立原則。
{:shortdesc}

若要啟用資源的公用存取權，您必須使用您帳戶中為您提供的**公用存取**存取群組。這個存取群組依預設會包含所有使用者及服務 ID。您無法刪除群組或變更群組的成員資格，但是可以新增、編輯和刪除群組的存取原則。

## 為公用存取群組建立原則
{: #public_policy}

請完成下列步驟，以指派原則給您的公用存取群組。下列作業使用 Cloud Object Storage 服務作為範例，指派對稱為 `mybucket123` 之儲存區的公用存取。

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**存取群組**。
2. 選取**公用存取**群組。
3. 按一下**指派存取權**。
4. 從服務清單選取 **Cloud Object Storage**。
5. 輸入 `bucket` 作為資源類型。
6. 輸入 `mybucket123` 作為資源 ID。
7. 按一下**指派**。
8. 按一下**是**確認您想要指派公用存取原則給資源，然後按一下**指派**。
