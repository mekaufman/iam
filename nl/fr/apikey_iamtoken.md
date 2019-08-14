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

# Génération d'un jeton IAM {{site.data.keyword.Bluemix_notm}} à l'aide d'une clé d'API
{: #iamtoken_from_apikey}

Vous pouvez générer un jeton IAM (Identity and Access Management) {{site.data.keyword.Bluemix}} à l'aide de votre clé API IAM ou d'une clé d'API d'ID de service. Les API {{site.data.keyword.Bluemix_notm}} ne sont accessibles que par des utilisateurs auxquels un rôle IAM est affecté. 
Chaque utilisateur qui appelle l'API doit transmettre des données d'identification pour l'API afin de s'authentifier. {:shortdesc}

Vous pouvez générer un jeton IAM en utilisant votre clé d'API [{{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#userapikey) ou une [clé d'API d'ID de service](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys). Ce processus est également utilisé si vous développez une application qui doit fonctionner avec d'autres services {{site.data.keyword.Bluemix_notm}}. Vous devez utiliser une clé d'API d'ID de service pour obtenir un jeton d'accès à transmettre à chacun des services {{site.data.keyword.Bluemix_notm}}.


Exécutez la commande `curl` suivante pour générer un jeton IAM en utilisant une clé d'API :

### POST /identity/token
{: #post_id_token}

### En-têtes
{: #header}

  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json


### Paramètres
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

L'exemple ci-dessous constitue la réponse attendue :

### Réponse
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

Un jeton IAM est valable pendant 60 minutes et est susceptible d'être modifié. Lorsqu'un jeton expire, vous devez en générer un nouveau.
{: note}
