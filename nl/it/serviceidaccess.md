---

copyright:

  years: 2015, 2019
lastupdated: "2019-05-01"

keywords: service ID, service ID access, managing access for service IDs

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gestione delle politiche di accesso degli ID servizio
{: #serviceidpolicy}

Quando crei un ID servizio, puoi assegnare delle politiche di servizio per tale ID servizio per controllare il livello di accesso consentito quando viene utilizzato per eseguire l'autenticazione presso i tuoi servizi. Puoi aggiornare queste politiche di accesso assegnate in qualsiasi momento modificando una politica esistente, eliminando una politica o assegnandone una nuova.
{:shortdesc}

Se elimini o modifichi una politica esistente per un ID servizio attualmente in uso, potrebbe verificarsi un'interruzione del servizio.
{: note}

## Assegnazione del nuovo accesso
{: #access_new}

Per assegnare l'accesso a tutte le risorse in un gruppo di risorse o a un solo servizio all'interno di un gruppo di risorse, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Seleziona l'ID servizio dalla tabella per cui vuoi assegnare una politica di servizio.
3. Fai clic su **Politiche di accesso**.
4. Fai clic su **Assegna accesso**.
5. Seleziona **Assegna per gruppo di risorse**.
6. Seleziona un gruppo di risorse.
7. Scegli un ruolo per il campo **Assegna l'accesso al gruppo di risorse**. Questa opzione consente all'utente di visualizzare il gruppo di risorse nel proprio elenco delle risorse, modificare il nome del gruppo di risorse o gestire l'accesso dell'utente al gruppo. Puoi selezionare **Nessun accesso** se vuoi che l'utente abbia accesso solo alla risorsa da te specificata e non al gruppo a cui è assegnata.
8. Seleziona un servizio nel gruppo di risorse o scegli di fornire l'accesso a tutti i servizi all'interno del gruppo selezionato.
9. Scegli qualsiasi combinazione di ruoli per assegnare l'accesso desiderato per l'utente. Questo accesso si applica solo alle risorse che hai selezionato per la politica. Non dà accesso al contenitore reale che è il gruppo di risorse.
10. Seleziona **Assegna**.

Per assegnare l'accesso a una singola risorsa nell'account, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Seleziona l'ID servizio dalla tabella per cui vuoi assegnare una politica di servizio.
3. 3. Fai clic su **Politiche di accesso**.
4. Fai clic su **Assegna accesso**.
5. Seleziona **Assegna per risorsa**.
6. Seleziona un servizio.
7. Seleziona **Tutte le regioni correnti** su una specifica regione, se ti viene richiesto.
8. Seleziona **Tutte le istanze del servizio correnti** o una specifica istanza del servizio.
9. A seconda del servizio che hai selezionato, potresti visualizzare i seguente campi. Se non immetti valori per questi campi, la politica viene assegnata a livello dell'istanza del servizio anziché a livello del bucket.
    * **Tipo di risorsa**: immetti **bucket**.
    * **ID risorsa**: immetti il nome del tuo bucket.
10. Scegli qualsiasi combinazione di ruoli per assegnare l'accesso desiderato per l'utente.
11. Seleziona **Assegna**.

Per assegnare l'accesso a uno o a tutti i servizi di gestione dell'account, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Seleziona l'ID servizio dalla tabella per cui vuoi assegnare una politica di servizio.
3. Fai clic su **Politiche di accesso**.
4. Fai clic su **Assegna accesso**.
5. Seleziona per assegnare l'accesso ai **servizi di gestione dell'account**
6. Seleziona **Tutti i servizi di gestione account** o seleziona un servizio specifico.
7. Seleziona qualsiasi combinazione di ruoli per assegnare l'accesso desiderato.

Potresti ricevere un messaggio che indica che esiste una politica per i dettagli che hai selezionato. Se stai creando una politica con gli stessi dettagli e ruoli, ti viene richiesto di apportare modifiche alla nuova politica poiché non sono consentite politiche duplicate. Se stai creando una politica con gli stessi dettagli ma con assegnazioni di ruoli differenti rispetto a una politica esistente, ti viene richiesto di controllare e aggiornare la politica esistente con le assegnazioni dei ruoli che vuoi assegnare.
{: tip}

## Modifica dell'accesso esistente
{: #access_edit}

Per modificare una politica esistente:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Seleziona l'ID servizio dalla tabella per cui vuoi modificare una politica del servizio.
3. Fai clic su **Politiche di accesso**.
4. Identifica la riga della politica che vuoi modificare e seleziona **Modifica politica** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg).
5. Apporta le tue modifiche e salva quindi la politica.

Per aggiornare una politica di servizio tramite la CLI, puoi utilizzare il comando [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_service_policy_update).
```
ibmcloud iam service-policy-update ID_SERVIZIO ID_POLITICA [-v, --version VERSIONE] {--file FILE_JSON | [-r, --roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name NOME_SERVIZIO] [--service-instance ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]} [-f, --force]",
```
{: codeblock}

Quando modifichi l'accesso per un ID servizio, potresti ricevere un messaggio che indica che non sono consentite politiche duplicate. Se stai modificando una politica esistente e le modifiche apportate sono in conflitto con l'accesso già assegnato, puoi scegliere di cambiare la politica che stai modificando per fornire un accesso diverso oppure puoi passare alla politica esistente con cui è in conflitto per controllare e apportare modifiche laddove necessario. Potresti voler eliminare la politica che stai modificando, se esiste una politica duplicata che soddisfa le tue esigenze.
{: tip}

## Rimozione dell'accesso
{: #access_remove}

Per rimuovere una politica esistente:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Seleziona l'ID servizio dalla tabella per cui vuoi eliminare una politica del servizio.
3. Fai clic su **Politiche di accesso**.
4. Identifica la riga della politica che vuoi eliminare e seleziona **Rimuovi** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg).
5. Riesamina i dettagli della politica che stai per rimuovere e fai clic su **Rimuovi** per confermare.

Per eliminare una politica di servizio tramite la CLI, puoi utilizzare il comando [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_service_policy_delete).
```
ibmcloud iam service-policy-delete ID_SERVIZIO ID_POLITICA [-f, --force]
```
{: codeblock}
