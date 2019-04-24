---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-30"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# API 키를 사용하여 {{site.data.keyword.Bluemix_notm}} IAM 토큰 가져오기
{: #iamtoken_from_apikey}

{{site.data.keyword.Bluemix}} API는 지정된 IAM 역할에 의해 권한이 부여된 사용자만 액세스할 수 있습니다. 따라서 API를 호출 중인 사용자는 인증하기 위해 API에 대한 인증 정보를 전달해야 합니다. [{{site.data.keyword.Bluemix_notm}} API 키](/docs/iam?topic=iam-userapikey#userapikey) 또는 [서비스 ID의 API 키](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)를 사용하여 IAM 토큰을 생성할 수 있습니다. 또한 이 프로세스는 다른 {{site.data.keyword.Bluemix_notm}} 서비스와 작업해야 하는 애플리케이션을 개발 중인 경우에도 사용됩니다. {{site.data.keyword.Bluemix_notm}}의 각 서비스에 전달될 액세스 토큰을 가져오려면 서비스 ID API 키를 사용해야 합니다.
{:shortdesc}

1. API 키를 사용하여 IAM 토큰을 생성하려면 다음 `curl` 명령을 사용하십시오.

### POST/ID/토큰
{: #post_id_token}

### 헤더
{: #header}
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### 매개변수
{: #parameters}
  - grant_type=urn:ibm:params:oauth:grant-type:apikey
  - apikey=*[Api key]*

```
curl -k -X POST \
  --header "Content-Type: application/x-www-form-urlencoded" \
  --header "Accept: application/json" \
  --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
  --data-urlencode "apikey=<apikey>" \
  "https://iam.cloud.ibm.com/identity/token"
```
{: codeblock}

다음 샘플은 예상 응답입니다.

### 응답
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
