---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: IBM Cloud service APIs, IAM token, API key, authenticate with service API

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 呼叫 {{site.data.keyword.cloud_notm}} 服務 API
{: #iamapikeysforservices}

若要透過 API 呼叫 {{site.data.keyword.Bluemix}} 服務，請將您的認證傳遞至服務的 API，以鑑別您的使用者身分以及在服務的環境定義內執行動作的存取權。
{:shortdesc}

您可以使用下列其中一種方式來識別來電者：

* {{site.data.keyword.Bluemix_notm}} API 金鑰或服務 ID API 金鑰
* {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 記號

[{{site.data.keyword.Bluemix_notm}} API 金鑰](/docs/iam?topic=iam-userapikey#userapikey)、[服務 ID API 金鑰](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)及 IAM 記號可以唯一識別來電者的身分。來電者身分是 {{site.data.keyword.Bluemix_notm}} 使用者，或是在 {{site.data.keyword.Bluemix_notm}} 帳戶中建立的服務 ID。

API 金鑰是包含一連串長隨機字元或數字的認證。{{site.data.keyword.Bluemix_notm}} 身分可以有多個 API 金鑰。每一個 API 金鑰都可以獨立管理，也就是說，如果此 API 金鑰僅供您的服務使用，則您可以刪除 API 金鑰，而不中斷某個其他元件。

您可以使用 API 金鑰[登入 {{site.data.keyword.Bluemix_notm}} 指令行介面 (CLI)](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_login#ibmcloud_login) 或[產生 IAM 記號](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey)。雖然不建議用於正式作業，但您也可以將 API 金鑰傳送至 {{site.data.keyword.Bluemix_notm}} 服務。

## 傳遞 {{site.data.keyword.Bluemix_notm}} API 金鑰以向服務 API 進行鑑別
{: #apikey_auth}

API 用戶端可以將 {{site.data.keyword.Bluemix_notm}} API 金鑰直接傳遞至目標服務的 API。若要這樣做，請使用基本授權 HTTP 標頭，將 `apikey` 關鍵字作為使用者名稱並將 {{site.data.keyword.Bluemix_notm}} API 金鑰作為密碼傳送至目標服務。

目標服務 API 必須使用 {{site.data.keyword.Bluemix_notm}} IAM 服務來內部檢查 {{site.data.keyword.Bluemix_notm}} API 金鑰。下圖顯示三個 API 互動。{{site.data.keyword.Bluemix_notm}} API 金鑰會傳遞至每個目標服務的 API，因此每個目標服務都必須呼叫 {{site.data.keyword.Bluemix_notm}} IAM 來查閱 {{site.data.keyword.Bluemix_notm}} API 金鑰詳細資料。

![使用 API 金鑰，以向服務 API 進行鑑別](images/APIkeyauth.svg "將 API 金鑰傳遞至目標服務，然後將 API 金鑰傳遞至 IAM 來驗證認證")

使用 {{site.data.keyword.Bluemix_notm}} API 金鑰很方便，可讓您輕鬆探索新的 API，並快速試用原型。此方法需要您以可讀取的格式將 {{site.data.keyword.Bluemix_notm}} API 金鑰傳送至目標服務的 API，這樣不一定會危及 API 金鑰。此外，因為目標服務的 API 必須一律內部檢查 API 金鑰，所以此方法的效能不佳，因此不建議用於正式作業工作負載。

若要使用 API 金鑰向服務的 API 進行鑑別，請完成下列步驟：

  1. 首先，如果您尚未[建立 {{site.data.keyword.Bluemix_notm}} API 金鑰](/docs/iam?topic=iam-userapikey#create_user_key)，請建立一個 API 金鑰。
  2. 將 [RFC 7617](https://tools.ietf.org/html/rfc7617){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 中定義的 {{site.data.keyword.Bluemix_notm}} API 金鑰傳送為 HTTP 標頭 "Authorization"。使用 `apikey` 作為使用者名稱，並使用 API 金鑰值作為密碼。

例如，下列步驟假設 API 金鑰為 0a1A2b3B4c5C6d7D8e9E：

  1.	連結以冒號區隔的使用者名稱 `apikey` 與 API 金鑰：`apikey:0a1A2b3B4c5C6d7D8e9E`
  2.	Base64 會編碼字串：`base64("apikey:0a1A2b3B4c5C6d7D8e9E") => YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`
  3.	設定綱目為 Basic 的 HTTP 標頭 Authorization，例如 `Authorization: Basic YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`。當您使用 curl 指令時，可以使用參數 -u 來傳遞此項目：

    ```
    curl -u "apikey:<IBM Cloud API key value>"
    ```

  如果您使用其他工具，則可能需要以不同的方式來指定這些認證。
  {: tip}

## 傳遞 {{site.data.keyword.Bluemix_notm}} IAM 記號以向服務 API 進行鑑別
{: #token_auth}

若要擷取 IAM 存取記號，API 用戶端必須先呼叫 {{site.data.keyword.Bluemix_notm}} IAM API 來鑑別及擷取該記號。{{site.data.keyword.Bluemix_notm}} 服務 API 用戶端的偏好方式是使用 IAM API 金鑰來取得 IAM 存取記號。IAM 存取記號可以用於多次呼叫 {{site.data.keyword.Bluemix_notm}} 服務，而這些服務接受 IAM 存取記號作為鑑別方法。因為 IAM 存取記號是使用非對稱金鑰進行數位簽署，所以 {{site.data.keyword.Bluemix_notm}} 服務可以驗證 IAM 存取記號，而不需要呼叫任何外部服務。這會大幅改善呼叫 API 的效能。

![使用存取記號，以向服務 API 進行鑑別](images/tokenauth.svg "使用 API 金鑰從 IAM 擷取記號，以及將存取記號傳遞至目標服務來驗證認證")

若要使用存取記號向服務的 API 進行鑑別，請完成下列步驟：

  1. 首先，如果您尚未[建立 {{site.data.keyword.Bluemix_notm}} API 金鑰](/docs/iam?topic=iam-userapikey#create_user_key)，請建立一個 API 金鑰。
  2. API 用戶端的下一步是擷取 IAM 存取記號，如[從 API 金鑰取得 IAM 記號](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey)中所述。
  3. 從回應中，擷取 `access_token` 內容以取得 IAM 存取記號。`expires_in` 指出 IAM 存取記號 `access_token` 到期之前的秒數。請根據 [UNIX 時間](https://en.wikipedia.org/wiki/Unix_time){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 來使用此相對值或絕對時間戳記 `expiration`。
  4. 傳送 IAM 存取記號，如 [RFC 6750 第 2.1 節，授權要求標頭欄位](https://tools.ietf.org/html/rfc6750#page-5){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 中所述：

請檢閱下列範例：

  1.	使用 HTTP 標頭 Authorization
  2.	在 IAM 存取記號的前面加上 `Bearer: Bearer eyJhbGciOiJSUzI1Ng...` 文字
  3.	將加上字首的 IAM 存取記號新增至 HTTP 標頭：`Authorization: Bearer eyJhbGciOiJSUzI1Ng...`。當您使用 curl 指令時，可以使用參數 -H 來傳遞此項目：

    ```
    curl -H "Authorization: Bearer eyJhbGciOiJSUzI1Ng..."
    ```

  對於後續的 IBM Cloud 服務 API 呼叫使用相同的 IAM 存取記號，以達到最佳效能及可調整性。
  {: tip}
