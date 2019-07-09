---

copyright:

  years: 2019

lastupdated: "2019-06-24"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}
{:note: .note}


# Gestione delle autorizzazioni dell'account SoftLayer migrate
{: #migrated_permissions}

Puoi utilizzare i gruppi di accesso migrati per gestire una serie di autorizzazioni dell'infrastruttura classica (SoftLayer) per gestire le informazioni sulla fatturazione e utilizzare i casi di supporto. I gruppi di accesso contengono una serie di utenti e ID servizio che hanno lo stesso accesso. Agli utenti del tuo account SoftLayer a cui sono state precedentemente assegnate le autorizzazioni di supporto e account viene ora assegnato il rispettivo gruppo di accesso delle autorizzazioni migrate. Di conseguenza, le autorizzazioni possono essere gestite direttamente utilizzando i gruppi di accesso IAM.
{:shortdesc}

Questi gruppi di accesso speciali includono tutte le politiche IAM appropriate per preservare il comportamento originale delle autorizzazioni dell'account SoftLayer. Ad esempio, per permettere a un utente di continuare a visualizzare tutti gli aggiornamenti da tutti gli utenti su un caso di supporto, i gruppi di accesso dell'autorizzazione migrata per le autorizzazioni dell'account SoftLayer per la creazione di ticket, includono un'ulteriore politica IAM sul servizio di gestione dell'utente con il ruolo di visualizzatore assegnato. Per ulteriori informazioni, vedi [Assegnazione dell'accesso utente per lavorare con i casi di supporto](/docs/get-support?topic=get-support-access#access).

Dopo la migrazione delle autorizzazioni della tua infrastruttura classica, devi sospendere l'utilizzo di tali autorizzazioni e smettere di utilizzare la CLI o l'API SoftLayer per gestirle. Vedi la seguente tabella per le autorizzazioni dell'infrastruttura classica migrate che fanno ora parte dei gruppi di accesso IAM. I gruppi di accesso sono creati solo per le autorizzazioni che sono già state assegnate agli utenti, per cui potresti vedere una sottoserie di gruppi di accesso presenti nel tuo account elencati nella seguente tabella.
{: note}

Puoi continuare a gestire queste autorizzazioni dell'infrastruttura classica migrate per gli utenti direttamente tramite IAM aggiungendo e rimuovendo gli utenti dai gruppi di accesso. Le politiche dei gruppi di accesso sono bloccate per preservare il comportamento di accesso per i loro membri. Tuttavia, potrebbe essere utile creare nuovi gruppi di accesso che includano una combinazione di politiche di accesso per i [servizi di gestione dell'account](/docs/iam?topic=iam-account-services#account-services). La seguente tabella descrive i dettagli di una politica di accesso IAM che include l'autorizzazione dal gruppo di accesso di autorizzazioni migrate, in modo da poter ricreare e combinare queste autorizzazioni con altre in un nuovo gruppo di accesso.

| Nome gruppo di accesso delle autorizzazioni migrate | Descrizione |Servizio di gestione account | Ruolo IAM |
|-----------------------------------|-------------|-----------------------------------------|----------|
| Visualizza riepilogo account | Visualizzare la pagina di riepilogo dell'account e le fatture e i pagamenti.  |  Fatturazione |  Visualizzatore    |
| Ottieni report di conformità | Richiede il report di conformità. | Fatturazione |    Visualizzatore |
| Modifica profilo azienda | Modificare le informazioni del profilo azienda. | Fatturazione  | Operatore |
| Aggiorna dettagli di pagamento | Aggiornare le informazioni sul pagamento mensile ricorrente. | Fatturazione   | Operatore |
| Limita restrizione casi UE |Abilitare o disabilitare l'opzione Supportato UE per limitare i dati dei casi di supporto all'Unione Europea.|   Fatturazione |   Operatore   |
| Aggiungi casi e visualizza ordini | Creare casi di supporto e visualizzare tutti gli ordini.  | Centro di supporto |   Editor   |
| Modifica casi | Modificare qualsiasi caso di supporto. | Centro di supporto |   Editor |
| Cerca casi | Ricercare tutti i casi di supporto se viene assegnata anche l'autorizzazione per visualizzare i casi. | Centro di supporto |  Visualizzatore |
| Visualizza casi | Visualizzare tutti i casi di supporto. | Centro di supporto e gestione utente |Visualizzatore, Visualizzatore|
{: caption="Tabella 1. Autorizzazioni dell'infrastruttura migrate associate ai ruoli IAM" caption-side="top"}

Per visualizzare l'accesso ai casi, crea due politiche separate con il ruolo di visualizzatore per i servizi del centro di supporto e di gestione utente. La politica sul servizio di gestione utente ti assicura che l'utente visualizzi tutti i casi nell'account indipendentemente da chi li ha aperti. Senza la politica sul servizio di gestione utente, se il proprietario dell'account ha limitato la capacità degli utenti di visualizzare gli altri utenti nell'account, la vista dei casi dell'utente potrebbe essere limitata a solo quelli da loro aperti.
{: note}

## Assegnazione di nuove politiche di accesso IAM per le autorizzazioni migrate
{: #migrated-permissions-iam}

Per ricreare le autorizzazioni migrate disponibili in ogni gruppo di accesso, puoi assegnare le politiche a singoli utenti o creare nuovi gruppi di accesso nel tuo account. Il vantaggio di creare un nuovo gruppo di accesso è che puoi scegliere di combinare una serie di autorizzazioni per un gruppo di accesso invece di gestire una serie di gruppi di accesso con un comportamento di accesso granulare impostato per ognuno di essi. Per questo esempio, la procedura illustra come creare un nuovo gruppo di accesso e assegnare una politica di accesso equivalente per la visualizzazione del riepilogo dell'account e di tutti i casi di supporto.

Il ricreare queste autorizzazioni assegnando nuove politiche di accesso IAM per i servizi di gestione dell'account, potrebbe includere delle autorizzazioni in aggiunta all'unica autorizzazione disponibile nel gruppo di accesso di autorizzazioni migrate. Ad esempio, se assegni a un utente il ruolo di visualizzatore sul servizio di fatturazione, tale utente può eseguire ulteriori operazioni rispetto alla visualizzazione del riepilogo dell'account. Per un elenco completo di azioni consentite per ogni ruolo, vedi [Assegnazione dell'accesso ai servizi di gestione dell'account](/docs/iam?topic=iam-account-services#account-services).
{: important}

Per creare un gruppo di accesso, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Fai clic su **Crea**.
3. Immetti un nome e una descrizione facoltativi per il gruppo e fai clic su **Crea**.
4. Fai clic su **Aggiungi utenti** nella scheda **Utenti**.
3. Seleziona gli utenti che vuoi aggiungere dall'elenco e fai clic su **Aggiungi al gruppo**. Puoi completare la stessa azione dalla scheda **ID servizio** se vuoi aggiungere degli ID servizio al gruppo.

Dopo aver configurato il tuo gruppo con gli utenti e gli ID del servizio, assegna l'accesso al gruppo. Ricorda, qualsiasi politica configuri per il gruppo si applica a tutti i membri nel gruppo.

1. Fai clic sulla scheda **Politiche di accesso**.
2. Fai clic su **Assegna accesso**.
3. Seleziona l'opzione **Assegna l'accesso ai servizi di gestione account**.
4. Seleziona il servizio **Fatturazione**.
5. Seleziona il ruolo **Visualizzatore**.
6. Fai clic su **Assegna**.
7. Fai clic su **Assegna accesso** per assegnare una seconda politica di accesso per consentire la visualizzazione dei casi di supporto.
8. Scegli **Assegna l'accesso ai servizi di gestione account**.
9. Seleziona il servizio **Centro di supporto**.
10. Seleziona il ruolo **Visualizzatore**.
11. Fai clic su **Assegna**.
12. Fai clic su **Assegna accesso** per assegnare una terza politica di accesso per consentire la visualizzazione di tutti i casi di supporto indipendentemente da come il proprietario dell'account ha configurato l'impostazione di visibilità utenti dell'account.
13. Seleziona l'opzione **Assegna l'accesso ai servizi di gestione account**.
14. Seleziona il servizio **Gestione utente**.
15. Seleziona il ruolo **Visualizzatore**.
16. Fai clic su **Assegna**.

Sono ora assegnate tre politiche al gruppo:

* Una politica per la visualizzazione del riepilogo dell'account e di tutte le altre azioni associate al ruolo di visualizzatore nel servizio di fatturazione.
* Una politica per la visualizzazione e la ricerca dei casi di supporto nell'account.
* Una politica per la visualizzazione di tutti gli utenti nell'account e di tutte le altre azioni associate al ruolo di visualizzatore sul servizio di gestione utente.

