---

copyright:
  years: 2018, 2019
lastupdated: "2019-08-08"

keywords: IAM token, token, API key, generate token, access token

subcollection: iam


---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}

# API キーを使用した {{site.data.keyword.Bluemix_notm}} IAM トークンの生成
{: #iamtoken_from_apikey}

IAM API キーまたはサービス ID の API キーを使用して、{{site.data.keyword.Bluemix}} ID およびアクセス管理 (IAM) トークンを生成します。{{site.data.keyword.Bluemix_notm}} API には、割り当てられた IAM 役割によって許可されたユーザーのみがアクセスできます。API を呼び出す各ユーザーは、API が認証するための資格情報を渡す必要があります。
{:shortdesc}

IAM トークンは、[{{site.data.keyword.Bluemix_notm}} API キー](/docs/iam?topic=iam-userapikey#userapikey)または[サービス ID の API キー](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)のいずれかを使用して生成できます。 このプロセスは、他の {{site.data.keyword.Bluemix_notm}} サービスと協力する必要があるアプリケーションを開発している場合にも使用されます。 サービス ID API キーを使用して、各 {{site.data.keyword.Bluemix_notm}} サービスに渡されるアクセス・トークンを取得する必要があります。


次の `curl` コマンドを使用して、API キーを使用して IAM トークンを生成します。

### POST /identity/token
{: #post_id_token}

### ヘッダー
{: #header}

  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json


### パラメーター
{: #parameters}

  - grant_type=urn:ibm:params:oauth:grant-type:apikey
  - apikey=*[API キー]*

```
curl -k -X POST \
  --header "Content-Type: application/x-www-form-urlencoded" \
  --header "Accept: application/json" \
  --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
  --data-urlencode "apikey=<apikey>" \
  "https://iam.cloud.ibm.com/identity/token"
```
{: codeblock}

以下の例は、予期される応答です。

### 応答
{: #response}

```
{
  "access_token": "eyJhbGciOiJIUz......sgrKIi8hdFs",
  "refresh_token": "SPrXw5tBE3......KBQ+luWQVY=",
  "token_type": "Bearer",
  "expires_in": 3600,
  "expiration": 1473188353
}
```
{: codeblock}

IAM トークンは 60 分間有効であり、変更されることがあります。トークンが有効期限切れとなった場合、新しいトークンを生成する必要があります。
{: note}
