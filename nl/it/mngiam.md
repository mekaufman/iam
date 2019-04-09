---

copyright:

  years: 2017, 2019

lastupdated: "2019-04-03"

keywords: resource access, assign access, IAM access policy, access to resource groups, edit access, remove access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gestione dell'accesso alle risorse
{: #iammanidaccser}

Per gestire l'accesso o assegnare un nuovo accesso per gli utenti utilizzando le politiche IAM, devi essere il proprietario dell'account, l'amministratore su tutti i servizi nell'account o l'amministratore assegnato per il servizio o l'istanza del servizio particolare. Per ulteriori informazioni sulle politiche di accesso e sui ruoli, vedi [Accesso IAM](/docs/iam?topic=iam-userroles#userroles).
{:shortdesc}

## Modifica dell'accesso esistente
{: #edit_existing}

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona il nome dell'utente a cui vuoi assegnare l'accesso.
3. Dalla riga per la politica che vuoi modificare, seleziona il menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) e fai clic su **Modifica politica**.
4. Modifica la politica.
5. Fai clic su **Save**.

Per aggiornare una politica utente utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_update).
```
ibmcloud iam user-policy-update NOME_UTENTE ID_POLITICA [-v, --version VERSIONE] {-f, --file FILE_JSON | [--roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name NOME_SERVIZIO] [--service-instance ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]}
```
{: codeblock}

Quando modifichi l'accesso per un utente o gruppo, potresti ricevere un messaggio che indica che non sono consentite politiche duplicate. Se stai modificando una politica esistente e le modifiche apportate sono in conflitto con l'accesso già assegnato, puoi scegliere di cambiare la politica che stai modificando per fornire un accesso diverso oppure puoi passare alla politica esistente con cui è in conflitto per controllare e apportare modifiche laddove necessario. Potresti voler eliminare la politica che stai modificando, se esiste già una politica duplicata che soddisfa le tue esigenze.
{: note}

## Assegnazione del nuovo accesso
{: #assign_new_access}

Puoi assegnare l'accesso alla risorsa utilizzando due tipi di politiche:

* Accesso alle risorse all'interno di un gruppo di risorse inclusa l'opzione per una sola o per tutte
* Accesso alle risorse nell'account inclusa l'opzione per un solo tipo o per tutti i tipi

Se vuoi abilitare un accesso da amministratore completo per tutte le attività di [gestione dell'account](/docs/iam?topic=iam-account-services#account-services) come l'invito e la rimozione degli utenti, la visualizzazione della fatturazione e dell'utilizzo, la gestione degli ID servizio, la gestione dei gruppi di accesso, la gestione dell'accesso utente e l'accesso a tutte le risorse dell'account, devi creare due politiche: una su **Tutti i servizi abilitati per l'accesso e l'identità** con il ruolo di amministratore e di gestore e una su **Tutti i servizi di gestione account** con il ruolo di amministratore.
{: tip}

### Accesso alle risorse all'interno di un gruppo di risorse
{: #access_to_resources}

Per assegnare l'accesso a tutte le risorse in un gruppo di risorse o a un solo servizio all'interno di un gruppo di risorse, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Dalla riga per l'utente a cui desideri assegnare l'accesso, seleziona il menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) e fai clic su **Assegna accesso**.
3. Seleziona **Assegna l'accesso in un gruppo di risorse**.
4. Seleziona un gruppo di risorse.
5. Scegli un ruolo per il campo **Assegna accesso a un gruppo di risorse** per consentire all'utente di visualizzare il gruppo di risorse nel proprio elenco delle risorse, modificare il nome del gruppo di risorse o gestire l'accesso dell'utente al gruppo. Puoi selezionare **Nessun accesso** se vuoi che l'utente abbia accesso solo alla risorsa da te specificata e non al gruppo in cui è organizzata.
6. Seleziona un servizio nel gruppo di risorse o scegli di fornire l'accesso a tutti i servizi all'interno del gruppo selezionato.
7. Scegli qualsiasi combinazione di ruoli per assegnare l'accesso desiderato per l'utente. Questo accesso si applica solo alle risorse che hai selezionato per la politica. Non dà accesso al contenitore reale che è il gruppo di risorse.
8. Fai clic su **Assegna**.

### Accesso alle risorse
{: #resourceaccess}

Per assegnare l'accesso a una singola risorsa o a tutte le risorse nell'account, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Dalla riga per l'utente a cui desideri assegnare l'accesso, seleziona il menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) e fai clic su **Assegna accesso**.
3. Seleziona **Assegna l'accesso alle risorse**.
4. Seleziona un servizio o seleziona **Tutti i servizi abilitati per l'accesso e l'identità**.
5. Seleziona **Tutte le regioni correnti** su una specifica regione, se ti viene richiesto.
6. Seleziona **Tutte le istanze del servizio correnti** o una specifica istanza del servizio.
7. A seconda del servizio che hai selezionato, potresti visualizzare i seguente campi. Se non immetti valori per questi campi, la politica viene assegnata a livello dell'istanza del servizio anziché a livello del bucket.
    * **Tipo di risorsa**: immetti **bucket**.
    * **ID risorsa**: immetti il nome del tuo bucket.
8. Scegli qualsiasi combinazione di ruoli per assegnare l'accesso desiderato per l'utente.
9. Fai clic su **Assegna**.

## Rimozione dell'accesso
{: #removing_access}

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona il nome dell'utente per il quale vuoi rimuovere l'accesso.
3. Dalla scheda **politiche di accesso**, seleziona il menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) sulla riga della politica che vuoi rimuovere e fai clic su **Rimuovi**.  
4. Riesamina i dettagli della politica utente che stai per rimuovere e quindi conferma facendo clic su **Rimuovi**.

Per rimuovere una politica utente utilizzando la CLI, puoi utilizzare il comando [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_delete#ibmcloud_iam_user_policy_delete).
```
ibmcloud iam user-policy-delete ID_UTENTE ID_POLITICA [-f, --force]
```
{: codeblock}

## Controllo del tuo accesso assegnato
{: #review_your_access}

Se devi controllare il tuo accesso assegnato in un account a cui sei stato aggiunto, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
3. Seleziona il tuo nome.
4. Controlla il tuo accesso assegnato nella sezione **Politiche di accesso**.

Se hai bisogno di ulteriore accesso, devi contattare il proprietario dell'account per aggiornare il tuo accesso o contattare l'amministratore del servizio o dell'istanza del servizio per aggiornare la politica di accesso Cloud IAM.
