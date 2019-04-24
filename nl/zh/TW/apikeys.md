---

copyright:

  years: 2015, 2019
lastupdated: "2019-03-05"

keywords: application programming interface key, API key, API, classic infrastructure API key, IBM Cloud API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 瞭解 API 金鑰
{: #manapikey}

應用程式設計介面金鑰（API 金鑰）是傳入 API 的唯一代碼，可識別呼叫端應用程式或使用者。API 金鑰用來追蹤及控制 API 的使用方式，例如，防止惡意使用或濫用 API。API 金鑰通常作為進行鑑別的唯一 ID 及密碼記號，而且一般具有其相關聯身分特有的一組存取權。
{:shortdesc}

若要檢視 API 金鑰，請移至**管理** > **存取 (IAM)** > **IBM Cloud API 金鑰**。

## {{site.data.keyword.cloud_notm}} API 金鑰
{: #ibm-cloud-api-keys}

{{site.data.keyword.cloud}} API 金鑰與使用者的身分相關聯。只有與 API 金鑰相關聯的使用者，才能建立及刪除它。您可以在指令行介面 (CLI) 或自動化作業中使用 {{site.data.keyword.cloud_notm}} API 金鑰，以您的使用者身分登入。您也可以使用 {{site.data.keyword.cloud_notm}} API 金鑰來存取標準基礎架構 API。如需使用與您使用者身分相關聯的 API 金鑰的相關資訊，請參閱[管理使用者 API 金鑰](/docs/iam?topic=iam-userapikey#userapikey)。

您也可以使用與所建立服務 ID 相關聯的 API 金鑰。服務 ID 是用來將 {{site.data.keyword.Bluemix_notm}} 內部或外部的應用程式連接至 {{site.data.keyword.Bluemix_notm}} 服務。如需建立與服務 ID 相關聯的 API 金鑰的相關資訊，請參閱[管理服務 ID API 金鑰](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)。

## 其他類型的 API 金鑰
{: #othertypes}

除了 {{site.data.keyword.cloud_notm}} API 金鑰之外，還有一些您可能使用的其他 API 金鑰類型：

* 標準基礎架構 API 金鑰
* 服務特有的 API 金鑰

標準基礎架構 API 金鑰可用來呼叫標準基礎架構服務的 API。您一次只能建立一個標準基礎架構 API 金鑰。您可以從「使用者詳細資料」頁面中建立使用者的標準基礎架構 API 金鑰。

{{site.data.keyword.cloud_notm}} API 金鑰也可以用來存取標準基礎架構 API。
{: tip}

{{site.data.keyword.Bluemix_notm}} 中的某些服務可能也會提供 API 金鑰，供您在使用服務時使用。例如，如果您從資源清單中檢視 Watson 服務的供應項目詳細資料，則您可以在「服務認證」頁面上建立包括 API 金鑰及密碼的認證，而此認證僅專屬於該服務。
