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

# Getting an {{site.data.keyword.Bluemix_notm}} IAM token by using an API key
{: #iamtoken_from_apikey}

{{site.data.keyword.Bluemix}} APIs can be accessed only by users that are authorized by an assigned IAM role. Therefore, the user that is calling the API must pass credentials for the API to authenticate. You can generate an IAM token by using either your [{{site.data.keyword.Bluemix_notm}} API key](/docs/iam?topic=iam-userapikey#userapikey) or a [service ID's API key](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys). This process is also used if you are developing an application that needs to work with other {{site.data.keyword.Bluemix_notm}} services. You must use a service ID API key to get an access token to be passed to each of the {{site.data.keyword.Bluemix_notm}} services.
{:shortdesc}

1. Use the following `curl` command to generate an IAM token by using an API key.

### POST /identity/token
{: #post_id_token}

### Headers
{: #header}
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### Parameters
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

The following sample is the expected response:

### Response
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
