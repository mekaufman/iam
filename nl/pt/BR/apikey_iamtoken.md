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

# Obtendo um token do {{site.data.keyword.Bluemix_notm}} IAM usando uma chave API
{: #iamtoken_from_apikey}

As APIs do {{site.data.keyword.Bluemix}} podem ser acessadas somente pelos usuários que estão autorizados por uma função de IAM designada. Portanto, o usuário que está chamando a API deve passar credenciais para a API autenticar. É possível gerar um token do IAM usando sua [chave de API do {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#userapikey) ou uma [chave de API do ID de serviço](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys). Este processo também será usado se você estiver desenvolvendo um aplicativo que precisa trabalhar com outros serviços do {{site.data.keyword.Bluemix_notm}}. Deve-se usar uma chave API do ID de serviço para obter um token de acesso para ser passado para cada um dos serviços do {{site.data.keyword.Bluemix_notm}}.
{:shortdesc}

1. Use o comando `curl` a seguir para gerar um token do IAM usando uma chave API.

### POST /identity/token
{: #post_id_token}

### Cabeçalhos
{: #header}
  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json

### Parâmetros
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

A amostra a seguir é a resposta esperada:

### Resposta
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
