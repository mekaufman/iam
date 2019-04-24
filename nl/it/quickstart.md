---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: get started with IAM, IAM tutorial, IAM quick start

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Esercitazione introduttiva
{: #getstarted}

Questa esercitazione ha lo scopo di aiutarti a iniziare rapidamente a lavorare con IBM Cloud Identity and Access Management (IAM) invitando gli utenti al tuo account e assegnando loro l'accesso a Cloud IAM.
{:shortdesc}

Questa esercitazione riguarda le risorse abilitate a IAM. Per i servizi che non supportano la creazione di politiche Cloud IAM per la gestione dell'accesso, puoi utilizzare l'[accesso Cloud Foundry](/docs/iam?topic=iam-cfaccess#cfaccess) o le [autorizzazioni dell'infrastruttura classica](/docs/iam?topic=iam-infrapermission#infrapermission).
{: note}


## Passo 1. Invita gli utenti e assegna l'accesso iniziale
{: #step1}

Puoi invitare uno o più utenti e impostare una politica di accesso iniziale per gli utenti al momento dell'invito. Se inviti più utenti in un unico invito, lo stesso accesso viene assegnato a ciascuno degli utenti. Nella sezione di accesso della pagina Invita utenti, vedi solo le sezioni che puoi assegnare.

In qualità di proprietario dell'account, puoi assegnare i ruoli di Cloud IAM per gli utenti che inviti nella sezione Servizi. Puoi fornire l'accesso a tutte le risorse in un gruppo di risorse, a tutte le risorse per un servizio specifico in un gruppo di risorse, a tutti i servizi abilitati per l'accesso e l'identità nell'account, a una singola risorsa o l'accesso ai servizi di gestione dell'account:

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Fai clic su **Invita utenti**.
3. Specifica l'indirizzo e-mail degli utenti che vuoi invitare.
4. Nella sezione **Accesso**, espandi l'opzione **Servizi**.
5. Scegli di assegnare l'accesso a una **Risorsa**, alle risorse all'interno di un **Gruppo di risorse** o ai **Servizi di gestione dell'account**.
6. A seconda della tua selezione, segui le istruzioni per specificare l'accesso desiderato. Se hai selezionato l'opzione del gruppo di risorse, puoi anche fornire all'utente l'accesso per visualizzare, modificare o gestire l'accesso al gruppo risorse selezionando un ruolo per l'accesso al gruppo di risorse.
7. Se disponi dell'autorizzazione, puoi anche assegnare l'accesso a Cloud Foundry o all'infrastruttura al momento dell'invito.
8. Fai clic su **Invita utenti**.

Per ulteriori informazioni, vedi [Invito di utenti e assegnazione dell'accesso](/docs/iam?topic=iam-iamuserinv#iamuserinv).

## Passo 2. Crea i gruppi di accesso
{: #step2}

Per semplificare il processo di assegnazione dell'accesso agli utenti nel tuo account, puoi creare i gruppi di accesso. I gruppi di accesso sono un modo per organizzare gli utenti e gli ID servizio a cui puoi assegnare facilmente l'accesso definendo una singola politica per l'intero gruppo.

### Configura i tuoi gruppi
{: #group_setup}

Per creare un gruppo di accesso, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Fai clic su **Crea**.
3. Immetti un nome e una descrizione facoltativa per il tuo gruppo
4. Fai clic su **Crea**.

Successivamente, continua a configurare il tuo gruppo aggiungendo utenti o ID del servizio:

1. Seleziona il nome del gruppo che vuoi aggiungere.
2. Fai clic su **Aggiungi utenti**.
3. Seleziona gli utenti che vuoi aggiungere dall'elenco e fai clic su **Aggiungi al gruppo**.
4. Per aggiungere gli ID servizio al gruppo, fai clic su **ID servizio**.
5. Seleziona gli ID che vuoi aggiungere dall'elenco e fai clic su **Aggiungi al gruppo**.

### Assegna l'accesso ai tuoi gruppi
{: #group_access}

Dopo aver creato i tuoi gruppi, puoi assegnare l'accesso a tutte le entità all'interno del gruppo con un'unica politica o più politiche.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Seleziona il nome del gruppo a cui vuoi assegnare l'accesso.
3. Dalla scheda **Politiche di accesso**, fai clic su **Assegna accesso** per configurare una politica di accesso. Ripeti secondo necessità per assegnare ulteriore accesso.

Organizzando le risorse in gruppi di risorse e gli utenti in gruppi di accesso, puoi assegnare a un gruppo di utenti l'accesso a un gruppo di risorse con un'unica politica, il che riduce il numero complessivo di politiche che devi gestire.
{: tip}


## Passo 3. Gestisci l'accesso per gli utenti esistenti
{: #user_access_manage}

Dopo aver invitato gli utenti, assegnato l'accesso iniziale e creato i gruppi di accesso, potresti voler assegnare ulteriore accesso o modificare l'accesso iniziale che hai assegnato per garantire che tutti gli utenti e i gruppi del tuo account abbiano il livello di accesso desiderato.

### Assegnazione del nuovo accesso
{: #new_access}

Per assegnare una nuova politica di accesso, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona il nome dell'utente a cui vuoi assegnare l'accesso.
3. Fai clic su **Politiche di accesso**.
4. Fai clic su **Assegna accesso**.
5. Scegli in che modo assegnare l'accesso:
    * Seleziona **Assegna l'accesso in un gruppo di risorse** per assegnare l'accesso a tutte le risorse in un gruppo o solo alle risorse per un servizio specifico all'interno di un gruppo. Puoi anche fornire all'utente l'accesso per visualizzare, modificare o gestire l'accesso al gruppo risorse selezionando un ruolo per l'accesso al gruppo di risorse. Seleziona **Nessun accesso** se vuoi che l'utente abbia solo accesso alla risorsa specificata e non al gruppo in cui è organizzata.
    * Seleziona **Assegna l'accesso alle risorse** per assegnare l'accesso a tutte le risorse abilitate all'accesso e l'identità nell'account, a tutte le risorse di uno specifico servizio nell'account, a una singola istanza o a una singola risorsa all'interno di una specifica istanza del servizio.
    * Seleziona **Assegna l'accesso ai servizi di gestione account** per assegnare l'accesso a tutti i servizi di gestione dell'account o solo a uno di essi.
5. Seleziona qualsiasi combinazione di ruoli per definire l'ambito di accesso. Per ulteriori informazioni, vedi [Ruoli Cloud IAM](/docs/iam?topic=iam-iamusermanrol#iamusermanrol).
6. Fai clic su **Assegna**.


### Modifica dell'accesso esistente
{: #editing_access}

Puoi aggiornare l'accesso esistente modificando i ruoli assegnati per un utente.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona il nome dell'utente per il quale vuoi modificare l'accesso.
3. Fai clic su **Politiche di accesso**.
4. Fai clic su **Modifica** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) sulla riga della politica che vuoi modificare.
4. Modifica la politica aggiornando i ruoli assegnati.
5. Fai clic su **Save**.

Puoi rimuovere l'accesso da un utente facendo clic sull'opzione **Rimuovi** dal menu **Azioni** ![Icona Elenco di opzioni](../icons/action-menu-icon.svg) per la politica che vuoi rimuovere.

## Passi successivi
{: #next}

Scopri cos'altro puoi fare con Cloud IAM controllando l'elenco delle [Funzioni di Cloud IAM](/docs/iam?topic=iam-features#features).
