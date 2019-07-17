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

# Richiamo di API del servizio {{site.data.keyword.cloud_notm}}
{: #iamapikeysforservices}

Per richiamare un servizio {{site.data.keyword.Bluemix}} tramite un'API, passa le tue credenziali all'API del servizio per autenticare la tua identità utente e il tuo accesso per eseguire azioni all'interno del contesto del servizio.
{:shortdesc}

Puoi identificare il chiamante in uno dei seguenti modi:

* Chiave API {{site.data.keyword.Bluemix_notm}} o chiave API dell'ID servizio
* Token IAM (Identity and Access Management) {{site.data.keyword.Bluemix_notm}}

[Le chiavi API {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#userapikey), [le chiavi API dell'ID servizio](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys) e i token IAM identificano in modo univoco l'identità del chiamante.  L'identità del chiamante può essere un utente {{site.data.keyword.Bluemix_notm}} o un ID servizio creato in un account {{site.data.keyword.Bluemix_notm}}.

Le chiavi API sono credenziali costituite da una lunga serie di caratteri o numeri casuali. Un'identità {{site.data.keyword.Bluemix_notm}} può avere più chiavi API. Ognuna di queste chiavi API può essere gestita in modo indipendente, nel senso che se questa chiave API viene utilizzata solo dal tuo servizio, puoi eliminare la chiave API senza interrompere altri componenti.

Puoi utilizzare le chiavi API per [accedere all'interfaccia riga di comando {{site.data.keyword.Bluemix_notm}} (CLI)](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login) o per [generare i token IAM](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey). Sebbene non sia consigliato per l'uso di produzione, puoi anche inviare le chiavi API ai servizi {{site.data.keyword.Bluemix_notm}}.

## Passaggio di una chiave API {{site.data.keyword.Bluemix_notm}} per l'autenticazione con un'API del servizio
{: #apikey_auth}

I client API possono passare direttamente una chiave API {{site.data.keyword.Bluemix_notm}} all'API del servizio di destinazione. Per farlo, invia la parola chiave `apikey` come nome utente e la chiave API {{site.data.keyword.Bluemix_notm}} come password utilizzando un'intestazione HTTP dell'autorizzazione di base al servizio di destinazione.

L'API del servizio di destinazione deve esaminare la chiave API {{site.data.keyword.Bluemix_notm}} utilizzando il servizio {{site.data.keyword.Bluemix_notm}} IAM. Il seguente grafico mostra tre interazioni API. La chiave API {{site.data.keyword.Bluemix_notm}} viene passata all'API di ogni servizio di destinazione, pertanto ogni servizio di destinazione deve cercare i dettagli della chiave API {{site.data.keyword.Bluemix_notm}} richiamando {{site.data.keyword.Bluemix_notm}} IAM.

![Autenticazione presso una API del servizio utilizzando una chiave API](images/APIkeyauth.svg "Passaggio di chiavi API ai servizi di destinazione che passano quindi la chiave API a IAM per convalidare le credenziali")

L'utilizzo di una chiave API {{site.data.keyword.Bluemix_notm}} è comodo e semplifica la scoperta di nuove API e la possibilità di provare rapidamente i prototipi. Questo metodo richiede l'invio della chiave API {{site.data.keyword.Bluemix_notm}} all'API del servizio di destinazione in un formato leggibile, che compromette inutilmente la chiave API. Inoltre, poiché l'API del servizio di destinazione deve sempre esaminare la chiave API, questo metodo è meno performante e pertanto non è consigliato per i carichi di lavoro di produzione.

Per l'autenticazione con l'API di un servizio utilizzando una chiave API, completa la seguente procedura:

  1. Per prima cosa, [crea una chiave API {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#create_user_key) se non lo hai già fatto.
  2. Invia la chiave API {{site.data.keyword.Bluemix_notm}} secondo quanto definito in [RFC 7617](https://tools.ietf.org/html/rfc7617){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno") come intestazione HTTP “Authorization”. Utilizza `apikey` come nome utente e il valore della chiave API come password.

A titolo di esempio, nei seguenti passi si presuppone che la tua chiave API sia 0a1A2b3B4c5C6d7D8e9E:

  1.	Concatena il nome utente `apikey` e la chiave API separati da due punti: `apikey:0a1A2b3B4c5C6d7D8e9E`
  2.	Codifica in base64 la stringa: `base64("apikey:0a1A2b3B4c5C6d7D8e9E") => YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`
  3.	Imposta l'intestazione HTTP Authorization con lo schema Basic, ad esempio `Authorization: Basic YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`. Quando usi il comando curl,puoi passarlo con il parametro -u:

    ```
    curl -u "apikey:<IBM Cloud API key value>"
    ```

  Se utilizzi altri strumenti, potresti dover specificare queste credenziali in modo diverso.
  {: tip}

## Passaggio di un token {{site.data.keyword.Bluemix_notm}} per l'autenticazione con l'API di un servizio
{: #token_auth}

Per richiamare un token di accesso IAM, il client API deve prima richiamare un'API {{site.data.keyword.Bluemix_notm}} IAM per autenticare e richiamare tale token. Il modo preferito per i client API del servizio {{site.data.keyword.Bluemix_notm}} è quello di utilizzare una chiave API IAM per ottenere un token di accesso IAM. Il token di accesso IAM può essere utilizzato per più richiami di servizi {{site.data.keyword.Bluemix_notm}} che accettano i token di accesso IAM come metodo di autenticazione. Poiché i token di accesso IAM sono firmati digitalmente con chiavi asimmetriche, i servizi {{site.data.keyword.Bluemix_notm}} possono convalidare un token di accesso IAM senza richiamare alcun servizio esterno. Questo migliora notevolmente le prestazioni del richiamo di un'API.

![Autenticazione presso una API del servizio utilizzando un token di accesso](images/tokenauth.svg "Richiamo di un token da IAM utilizzando una chiave API e passando il token di accesso ai servizi di destinazione per convalidare le credenziali")

Per l'autenticazione con l'API di un servizio utilizzando un token di accesso, completa la seguente procedura:

  1. Per prima cosa, [crea una chiave API {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#create_user_key) se non lo hai già fatto.
  2. Il passo successivo per il client API è il recupero di un token di accesso IAM, come descritto in [Ottenimento di un token IAM da una chiave API](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey).
  3. Dalla risposta, estrai la proprietà `access_token` per ottenere il token di accesso IAM. `expires_in` indica i secondi fino alla scadenza del token di accesso IAM `access_token`. Utilizza questo valore relativo o la data/ora assoluta `expiration` basata sul [tempo UNIX](https://en.wikipedia.org/wiki/Unix_time){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").
  4. Invia il token di accesso IAM come descritto in [RFC 6750, sezione 2.1. Authorization Request Header Field](https://tools.ietf.org/html/rfc6750#page-5){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno"):

Controlla il seguente esempio:

  1.	Utilizza l'intestazione HTTP Authorization
  2.	Applica al token di accesso IAM un prefisso con il valore letterale `Bearer: Bearer eyJhbGciOiJSUzI1Ng...`
  3.	Aggiungi il token di accesso IAM con prefisso all'intestazione HTTP: `Authorization: Bearer eyJhbGciOiJSUzI1Ng...`. Quando usi il comando curl,puoi passarlo con il parametro -H:

    ```
    curl -H "Authorization: Bearer eyJhbGciOiJSUzI1Ng..."
    ```

  Utilizza lo stesso token di accesso IAM per le successive chiamate API del servizio IBM Cloud per ottenere prestazioni e scalabilità migliori.
  {: tip}
