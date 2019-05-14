---

copyright:

  years: 2015, 2019
lastupdated: "2019-04-30"

keywords: application programming interface key, API key, API, classic infrastructure API key, IBM Cloud API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Descrizione delle chiavi API
{: #manapikey}

Una chiave API (application programming interface) è un codice univoco che viene passato a un'API per identificare l'applicazione o l'utente chiamante. Le chiavi API vengono utilizzate per tracciare e controllare la modalità di utilizzo della API, ad esempio per prevenire l'uso dannoso o l'abuso della API. La chiave API spesso funge sia da identificativo univoco che da token segreto per l'autenticazione e generalmente ha una serie di accesso specifico per l'identità a cui è associata.
{:shortdesc}

Per visualizzare le tue chiavi API, vai a **Gestisci** > **Accesso (IAM)** > **Chiavi API IBM Cloud**. 

## {{site.data.keyword.cloud_notm}} Chiavi API
{: #ibm-cloud-api-keys}

Le chiavi API {{site.data.keyword.cloud}} sono associate all'identità dell'utente. La chiave API può essere creata ed eliminata solo dall'utente a cui è associata tale chiave API. Puoi utilizzare le chiavi API {{site.data.keyword.cloud_notm}} nella CLI (command-line interface) o come parte dell'automazione per eseguire l'accesso come tua identità utente. Puoi anche utilizzare le chiavi API {{site.data.keyword.cloud_notm}} per accedere alle API dell'infrastruttura classica. Per ulteriori informazioni sull'utilizzo di una chiave API associata alla tua identità utente, consulta [Gestione delle chiavi API utente](/docs/iam?topic=iam-userapikey#userapikey).

Puoi anche utilizzare le chiavi API associate agli ID servizio che crei. Gli ID servizio sono utilizzati per connettere un'applicazione all'interno o all'esterno di {{site.data.keyword.Bluemix_notm}} a un servizio {{site.data.keyword.Bluemix_notm}}. Per ulteriori informazioni sulla creazione di chiavi API associate a un ID servizio, consulta [Gestione delle chiavi API di un ID servizio](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys).

## Altri tipi di chiavi API
{: #othertypes}

Oltre alle tue chiavi API {{site.data.keyword.cloud_notm}}, sono disponibili un paio di altri tipi di chiavi API che puoi utilizzare:

* Chiavi API dell'infrastruttura classica
* Chiavi API specifiche del servizio

Le chiavi API dell'infrastruttura classica vengono utilizzate per chiamare le API relative ai servizi dell'infrastruttura classica. Puoi creare una sola chiave API dell'infrastruttura classica alla volta. Puoi creare una chiave API dell'infrastruttura classica dalla pagina Dettagli utente.

Le chiavi API {{site.data.keyword.cloud_notm}} possono essere utilizzate anche per accedere alle API dell'infrastruttura classica.
{: tip}

Alcuni servizi in {{site.data.keyword.Bluemix_notm}} potrebbero anche fornirti una chiave API da utilizzare quando lavori con il servizio. Ad esempio, se stai visualizzando i dettagli dell'offerta di un servizio Watson dal tuo elenco delle risorse, puoi creare una credenziale, che include una chiave e un segreto API specifici solo per tale servizio, nella pagina Credenziali del servizio.
