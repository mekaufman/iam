---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

keywords: access groups, access group, create group, assign access to group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Configurazione dei gruppi di accesso
{: #groups}

È possibile creare un gruppo di accesso per organizzare un insieme di utenti e ID servizio in un'unica entità che ti faciliti l'assegnazione dell'accesso. Puoi assegnare una sola politica al gruppo invece di assegnare lo stesso accesso più volte per ogni utente o ID del servizio individuale.
{:shortdesc}

Per gestire o creare nuovi gruppi di accesso, devi essere il proprietario dell'account, l'amministratore o l'editor sul servizio Gruppi di accesso IAM nell'account o l'amministratore o l'editor assegnato per tutti i servizi di gestione dell'account. Inoltre, è possibile assegnare l'accesso a un amministratore o un editor per gestire un solo gruppo creando una politica di accesso in cui la risorsa è l'ID del gruppo di accesso. Per ulteriori informazioni sulle politiche di accesso e sui ruoli per il servizio Gruppi di accesso IAM, consulta [Accesso IAM](/docs/iam?topic=iam-userroles#userroles).

Per rendere l'assegnazione e la gestione dell'accesso ancora più semplice, puoi configurare i gruppi di accesso per organizzare una serie di risorse a cui vuoi che un gruppo di utenti abbia accesso. Quando il tuo gruppo di risorse è configurato, puoi assegnare una politica che fornisce l'accesso a tutte le risorse in tale gruppo invece di creare le politiche di accesso per istanze del servizio individuali nel tuo account.
{: tip}

## Creazione di un gruppo di accesso
{: #create_ag}

Per creare un gruppo di accesso, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Fai clic su **Crea**.
3. Immetti un nome e una descrizione facoltativi per il gruppo e fai clic su **Crea**.

Successivamente, continua a configurare il tuo gruppo aggiungendo utenti o ID del servizio:

1. Seleziona il nome del gruppo che vuoi aggiungere.
2. Fai clic su **Aggiungi utenti** nella scheda **Utenti**.
3. Seleziona gli utenti che vuoi aggiungere dall'elenco e fai clic su **Aggiungi al gruppo**.
4. Per aggiungere gli ID del servizio al gruppo, fai clic sulla scheda **ID servizio** e su **Aggiungi ID servizio**.
5. Seleziona gli ID che vuoi aggiungere dall'elenco e fai clic su **Aggiungi al gruppo**.

Puoi eliminare un gruppo selezionando l'opzione **Rimuovi gruppo**. Quando rimuovi un gruppo dall'account, rimuovi tutti gli utenti e gli ID servizio dal gruppo e tutto l'accesso assegnato al gruppo.
{: note}

Per creare un gruppo di accesso utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create).
```
ibmcloud iam access-group-create NOME_GRUPPO [-d, --description DESCRIZIONE]
```
{: codeblock}


## Assegnazione dell'accesso a un gruppo
{: #access_ag}

Dopo aver configurato il tuo gruppo con gli utenti e gli ID del servizio, puoi assegnare una politica di accesso comune al gruppo. Ricorda, qualsiasi politica configuri per il gruppo si applica a tutte le entità all'interno del gruppo.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Seleziona il nome del gruppo a cui vuoi assegnare l'accesso.
3. Fai clic su **Politiche di accesso**.
4. Fai clic su **Assegna accesso**.
5. Scegli di assegnare l'accesso in base alle risorse all'interno di un gruppo di risorse, alle singole risorse disponibili nell'account o ai servizi di gestione dell'account.

Per creare una politica del gruppo di accesso utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create).
```
ibmcloud iam access-group-policy-create NOME_GRUPPO {-f, --file @FILE_JSON | --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name NOME_SERVIZIO] [--service-instance ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]}
```
{: codeblock}
