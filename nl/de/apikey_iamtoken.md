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

# {{site.data.keyword.Bluemix_notm}} IAM-Token mithilfe eines API-Schlüssels abrufen
{: #iamtoken_from_apikey}

Auf {{site.data.keyword.Bluemix}}-APIs kann nur von Benutzern zugegriffen werden, die durch eine zugewiesene IAM-Rolle autorisiert sind. Deshalb muss der Benutzer, der die API aufruft, zur Authentifizierung Berechtigungsnachweise für die API übergeben. Sie können ein IAM-Token generieren, indem Sie entweder Ihren [{{site.data.keyword.Bluemix_notm}}-API-Schlüssel](/docs/iam?topic=iam-userapikey#userapikey) oder den [API-Schlüssel einer Service-ID](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys) verwenden. Dieser Prozess wird auch verwendet, wenn Sie eine Anwendung entwickeln, die mit anderen {{site.data.keyword.Bluemix_notm}}-Services zusammenarbeiten muss. Sie müssen den API-Schlüssel einer Service-ID verwenden, um ein Zugriffstoken abzurufen, das an die einzelnen {{site.data.keyword.Bluemix_notm}}-Services übergeben werden soll.
{:shortdesc}

1. Verwenden Sie den folgenden `curl`-Befehl, um ein IAM-Token mithilfe eines API-Schlüssels zu generieren.

### POST /identity/token
{: #post_id_token}

### Header
{: #header}
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### Parameter
{: #parameters}
  - grant_type=urn:ibm:params:oauth:grant-type:apikey
  - apikey=*[api-schlüssel]*

```
curl -k -X POST \
  --header "Content-Type: application/x-www-form-urlencoded" \
  --header "Accept: application/json" \
  --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
  --data-urlencode "apikey=<api-schlüssel>" \
  "https://iam.cloud.ibm.com/identity/token"
```
{: codeblock}

Das folgende Beispiel zeigt, welche Antwort erwartet wird:

### Antwort
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
