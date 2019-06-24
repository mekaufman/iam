---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-30"

keywords: IAM token, token, API key, generate token

subcollection: iam


---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# 使用 API 密钥获取 {{site.data.keyword.Bluemix_notm}} IAM 令牌
{: #iamtoken_from_apikey}

只有获得了 IAM 角色授权的用户才能访问 {{site.data.keyword.Bluemix}} API。每个用户在调用 API 时必须传递 API 的凭证，才能通过认证。
{:shortdesc}

您可以使用 [{{site.data.keyword.Bluemix_notm}} API 密钥](/docs/iam?topic=iam-userapikey#userapikey)或[服务标识的 API 密钥](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)来生成 IAM 令牌。如果要开发的应用程序需要使用其他 {{site.data.keyword.Bluemix_notm}} 服务，也可以使用此过程。要使访问令牌能够传递到每个 {{site.data.keyword.Bluemix_notm}} 服务，必须使用服务标识 API 密钥。



1. 要使用 API 密钥生成 IAM 令牌，请使用以下 `curl` 命令。

### POST /identity/token
{: #post_id_token}

### 头
{: #header}

  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json


### 参数
{: #parameters}

  - grant_type=urn:ibm:params:oauth:grant-type:apikey
  - apikey=*[API key]*

```
curl -k -X POST \
  --header "Content-Type: application/x-www-form-urlencoded" \
  --header "Accept: application/json" \
  --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
  --data-urlencode "apikey=<apikey>" \
  "https://iam.cloud.ibm.com/identity/token"


```
{: codeblock}

以下样本是预期的响应：

### 响应
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
