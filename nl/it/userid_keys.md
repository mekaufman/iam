---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestione delle chiavi API utente
{: #userapikey}

Un utente federato o non federato può creare una chiave API da utilizzare nella CLI o come parte dell'automazione per eseguire l'accesso come tua identità utente. Puoi utilizzare l'IU o la CLI per gestire le tue chiavi API attraverso l'elenco, la creazione, l'aggiornamento o l'eliminazione delle chiavi. Per gestire le chiavi API {{site.data.keyword.Bluemix_notm}} associate alla tua identità utente, vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**. Quindi, fai clic sul tuo nome dall'elenco e seleziona l'opzione **Dettagli utente** per visualizzare un elenco delle tue chiavi API con descrizioni e date. Quindi puoi creare, modificare o eliminare chiavi API. E per un elenco completo dei comandi CLI disponibili, consulta [`ibmcloud iam api-keys`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_keys).

Come [utente federato](/docs/account?topic=account-signup#signup), puoi usare una chiave API per eseguire l'accesso utilizzando la variabile di ambiente `IBMCLOUD_API_KEY`. Per ulteriori informazioni sull'utilizzo di una chiave API per l'accesso, vedi [Accesso con un ID federato](/docs/iam?topic=iam-federated_id#federated_id).
{:shortdesc}

## Creazione di una chiave API
{: #create_user_key}

In qualità di utente {{site.data.keyword.Bluemix_notm}}, potresti voler utilizzare una chiave API quando abiliti un programma o uno script senza distribuire la tua password allo script. Un vantaggio di utilizzare una chiave API può essere che un utente o un'organizzazione può creare più chiavi API per programmi diversi e le chiavi API possono essere eliminate in modo indipendente se compromesse senza interferire con altre chiavi API o con l'utente. Puoi creare fino a 20 chiavi API.

Per creare una chiave API per la tua identità utente nell'IU, completa la seguente procedura:

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**. Quindi, fai clic sul tuo nome dall'elenco e seleziona l'opzione **Dettagli utente**.
2. Fai clic su **Crea una chiave API {{site.data.keyword.Bluemix_notm}}**.
3. Immetti un nome e una descrizione per la tua chiave API.
4. Fai clic su **Create**.
5. Quindi, fai clic su **Mostra** per visualizzare la chiave API per copiarla e salvarla per un secondo momento o fai clic su **Scarica**.

Per motivi di sicurezza, la chiave API è disponibile per essere copiata o scaricata solo durante la fase di creazione. Se la chiave API viene persa, dovrai crearne una nuova.
{: tip}

Per creare una chiave API utilizzando la CLI, utilizza il seguente comando:

1. Immetti `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` nel prompt dei comandi e specifica un nome, una descrizione e un file per salvare la tua chiave. Vedi il seguente esempio:

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
``` 


## Aggiornamento di una chiave API
{: #update_user_key}

Se desideri modificare il nome o la descrizione di una chiave API, completa le seguenti istruzioni nella IU o nella CLI.

Per modificare una chiave API, completa la seguente procedura:

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**. Quindi, fai clic sul tuo nome dall'elenco e seleziona l'opzione **Dettagli utente**.
2. Identifica la riga della chiave API che vuoi aggiornare e seleziona **Modifica** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg).
3. Aggiorna le informazioni per la tua chiave API.
4. Fai clic su **Applica**.

Per modificare una chiave API utilizzando la CLI, utilizza il seguente comando:

1. Immetti `ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` nel tuo prompt dei comandi, specificando il vecchio nome, il nuovo nome e la nuova descrizione della chiave. Ad esempio:

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## Blocco di una chiave API
{: #lock_user_key}

Per le chiavi API della piattaforma che rappresentano la tua identità utente, puoi evitarne l'eliminazione eseguendone il blocco. Una chiave API bloccata è indicata dall'icona ![Icona di bloccato](images/locked.svg "Bloccato"). Puoi bloccare e sbloccare la tua chiave API utilizzando l'IU o la CLI.

### Blocco e sblocco di una chiave API dall'IU
{: #lockui}

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**. Quindi, fai clic sul tuo nome dall'elenco e seleziona l'opzione **Dettagli utente**.
2. Identifica la riga della chiave API che vuoi bloccare e seleziona **Blocca** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg).

Puoi sbloccare la tua chiave API in qualsiasi momento per aggiornarla o rimuoverla dal tuo account. Seleziona dalla tabella la chiave API che vuoi sbloccare e seleziona **Sblocca** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg).
{: tip}

### Blocco e sblocco di una chiave API utilizzando la CLI
{: #lockcli}

Per bloccare una chiave API, utilizza il seguente comando:

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da bloccare, esclusivo con UUID.</dd>
<dt>UUID (obbligatorio)</dt>
<dd>UUID della chiave API da bloccare, esclusivo con NAME.</dd>
<dt>-f, --force</dt>
<dd>Forza il blocco senza conferma.</dd>
</dl>

<strong>Esempio</strong>:

Blocca la chiave API `test-api-key`

```
ibmcloud iam api-key-lock test-api-key
```

Per sbloccare una chiave API, immetti il seguente comando:

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da sbloccare, esclusivo con UUID.</dd>
<dt>UUID (obbligatorio)</dt>
<dd>UUID della chiave API da sbloccare, esclusivo con NAME.</dd>
<dt>-f, --force</dt>
<dd>Forza lo sblocco senza conferma.</dd>
</dl>

<strong>Esempio</strong>:

Sblocca la chiave API `test-api-key`

```
ibmcloud iam api-key-unlock test-api-key
```


## Eliminazione di una chiave API
{: #delete_user_key}

Se stai utilizzando una strategia di rotazione della chiave, potresti voler eliminare una chiave vecchia e sostituirla con una nuova.

Per eliminare una chiave API, completa la seguente procedura: 

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**. Quindi, fai clic sul tuo nome dall'elenco e seleziona l'opzione **Dettagli utente**.
2. Identifica la riga della chiave API che vuoi eliminare e seleziona **Elimina** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg).
3. Infine, conferma l'eliminazione facendo clic su **Elimina**.

Per eliminare una chiave API utilizzando la CLI:
1. Immetti `ibmcloud iam api-key-delete NAME` nel tuo prompt dei comandi, specificando il nome della chiave da eliminare.
