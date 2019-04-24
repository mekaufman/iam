---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: service ID, service ID API key, lock service ID API key, delete service ID API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Gestione delle chiavi API di un ID servizio
{: #serviceidapikeys}

Gli ID servizio vengono creati per abilitare l'accesso ai tuoi servizi {{site.data.keyword.Bluemix_notm}} dalle applicazioni ospitate sia all'interno che all'esterno di {{site.data.keyword.Bluemix_notm}}. Le chiavi API vengono utilizzate da un'applicazione per eseguire l'autenticazione come uno specifico ID servizio e ottenere l'accesso associato a tale ID servizio.

Dopo che hai creato un ID servizio, puoi iniziare a creare le chiavi API e ad assegnare le politiche di servizio. Ciascuna politica specifica il livello di accesso consentito quando la chiave API viene utilizzata per eseguire l'autenticazione presso i tuoi servizi. Per ulteriori informazioni sulla creazione di un ID servizio e sull'assegnazione di politiche, vedi [Creazione e gestione degli ID servizio](/docs/iam?topic=iam-serviceids#serviceids). Per i dettagli sui comandi della CLI utilizzati per gestire le chiavi API di un ID servizio, vedi [Gestione dell'accesso IAM, delle chiavi API, degli ID servizio e dei gruppi di accesso](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_commands_iam).

Ogni chiave API associata a un ID servizio eredita la politica che è stata assegnata all'ID servizio. Ad esempio, se vuoi che un'applicazione sia in grado di visualizzare semplicemente le risorse all'interno di un servizio, devi utilizzare una chiave API associata a un ID servizio che ha una politica assegnata con il ruolo Visualizzatore. Se poi vuoi che un'altra applicazione possa avere un accesso completo in un servizio, devi utilizzare una chiave API associata a un secondo ID servizio che ha una politica assegnata con il ruolo di amministratore.

Per ulteriori informazioni, vedi [Esempi di come utilizzare un ID servizio](/docs/iam?topic=iam-serviceids#examples_serviceid).

## Creazione di una chiave API per un ID servizio
{: #create_service_key}

Crea una chiave API da associare a un ID servizio.

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Se non hai già un ID servizio creato, crea l'ID servizio.
3. Dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg), fai clic su **Gestisci ID servizio**.
4. Fai clic su **Chiavi API**.
5. Fai clic su **Crea**.
6. Aggiungi un nome e una descrizione per identificare facilmente la chiave API.
7. Fai clic su **Crea**.
8. Salva la tua chiave API copiandola o scaricandola in un'ubicazione sicura.

Per motivi di sicurezza, la chiave API è disponibile per essere copiata o scaricata solo durante la fase di creazione. Se la chiave API viene persa, dovrai crearne una nuova.
{: note}

Per creare una chiave API di un ID servizio utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam service-api-key-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_create).
```
ibmcloud iam service-api-key-create NOME ID_SERVIZIO [-d, --description DESCRIZIONE] [--file FILE] [-f, --force]
```
{: codeblock}

## Aggiornamento di una chiave API per un ID servizio
{: #update_service_key}

Puoi aggiornare una chiave API modificando il nome o la descrizione utilizzati per identificare la chiave nell'IU.

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg), fai clic su **Gestisci ID servizio**.
3. Fai clic su **Chiavi API**.
4. Dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg), fai clic su **Modifica nome e descrizione**.

Per aggiornare una chiave API di un ID servizio utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam service-api-key-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_update).
```
ibmcloud iam service-api-key-update NOME ID_SERVIZIO  [-n, --name NUOVO_NOMEs] [-d, --description DESCRIZIONE] [-v, --version VERSIONE] [-f, --force]
```
{: codeblock}

## Blocco di una chiave API dell'ID servizio
{: #lockkey}

Per le chiavi API che rappresentano l'identità dell'ID servizio, puoi evitarne l'eliminazione eseguendone il blocco. Una chiave API bloccata è indicata dall'icona ![Icona di bloccato](images/locked.svg "Bloccato") nell'IU.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Identifica la riga dell'ID servizio per cui vuoi selezionare una chiave API e seleziona il nome dell'ID servizio.
3. Fai clic su **Chiavi API**.
4. Passa con il mouse sulla riga della chiave API che vuoi bloccare e fai clic sul menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) per aprire un elenco di opzioni.
5. Fai clic su **Blocca chiave API**.

Puoi sbloccare la tua chiave API in qualsiasi momento per aggiornare, eliminare o aggiungere una politica di accesso oppure per rimuovere la chiave API.
{: tip}

### Blocco e sblocco di una chiave API dell'ID servizio con la CLI.
{: #lock_unlock_cli}

Per bloccare una chiave API dell'ID servizio, utilizza il seguente comando:

```
ibmcloud iam service-api-key-lock (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Blocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Blocca la chiave API del servizio `sample-key` dell'ID servizio `sample-service`:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

Per sbloccare una chiave API dell'ID servizio, utilizza il seguente comando:

```
ibmcloud iam service-api-key-unlock (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```


## Eliminazione di una chiave API per un ID servizio
{: #delete_service_key}

Puoi eliminare una chiave API associata a un ID servizio. Tuttavia, l'eliminazione di una chiave API attualmente utilizzata da un'applicazione non consentirà più a tale applicazione di eseguire l'autenticazione presso i tuoi servizi.

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Se non hai già un ID servizio creato, crea l'ID servizio.
3. Dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg), fai clic su **Gestisci ID servizio**.
4. Fai clic su **Chiavi API**.
5. Dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg), fai clic su **Elimina**.

Per eliminare una chiave API di un ID servizio utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam service-api-key-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_delete).
```
ibmcloud iam service-api-key-delete NOME ID_SERVIZIO [-f, --force]
```
{: codeblock}
