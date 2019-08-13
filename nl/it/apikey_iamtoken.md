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

# Generazione di un token IAM {{site.data.keyword.Bluemix_notm}} utilizzando una chiave API
{: #iamtoken_from_apikey}

Genera un token {{site.data.keyword.Bluemix}} Identity and Access Management (IAM) utilizzando la tua chiave API IAM o la chiave API dell'ID servizio. Alle API {{site.data.keyword.Bluemix_notm}} possono accedere solo gli utenti autorizzati da un ruolo IAM assegnato. Ogni utente che richiama l'API deve passare le credenziali dell'API per l'autenticazione.
{:shortdesc}

Puoi generare un token IAM utilizzando la tua [chiave API {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#userapikey) oppure una [chiave API dell'ID servizio](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys). Questo processo è utilizzato anche se stai sviluppando un'applicazione che deve lavorare con altri servizi {{site.data.keyword.Bluemix_notm}}. Devi utilizzare una chiave API dell'ID servizio per ottenere un token di accesso da passare a ciascuno dei servizi {{site.data.keyword.Bluemix_notm}}.


Utilizza il seguente comando `curl` per generare un token IAM utilizzando una chiave API.

### POST /identity/token
{: #post_id_token}

### Intestazioni
{: #header}

  - Content-Type: application/x-www-form-urlencoded
  - Accept: application/json


### Parametri
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

Il seguente esempio è la risposta prevista:

### Risposta
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

Un token IAM è valido per 60 minuti ed è soggetto a modifiche. Quando un token scade, devi generarne un altro.
{: note}
