---

copyright:

  years: 2017, 2019

lastupdated: "2019-04-02"

keywords: SoftLayer permissions, classic infrastructure access, classic infrastructure permission, migrated SoftLayer permissions, migrated permission access group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}

# Autorizzazioni dell'infrastruttura classica
{: #infrapermission}

Quando inviti un utente al tuo account, puoi scegliere tra tre serie di autorizzazioni dell'infrastruttura classica che assegnano l'accesso in blocco: Solo visualizzazione, Utente di base e Super utente.
{:shortdesc}

Quando inviti qualcuno all'account, solo tu in qualità di proprietario dell'account o utente con l'autorizzazione di gestione utenti dell'infrastruttura classica, puoi modificare le autorizzazioni per un utente. Se stai assegnando le autorizzazioni e non sei il proprietario dell'account, puoi assegnare solo il livello di autorizzazioni o un sottoinsieme delle autorizzazioni che ti sono già state assegnate. Un proprietario dell'account può aggiornare le autorizzazioni di chiunque nell'account per avere qualsiasi livello di accesso.

Puoi impostare autorizzazioni aggiuntive dopo che l'utente ha accettato l'invito. Ad esempio, la serie di autorizzazioni iniziale assegnata al momento dell'invito non concede l'accesso ai dispositivi. Devi pertanto concedere l'accesso ai dispositivi dopo che l'utente accetta l'invito. Per ulteriori informazioni, vedi [Gestione dell'accesso all'infrastruttura classica](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra).

Il seguente grafico mostra come le autorizzazioni dell'infrastruttura classica vengono assegnate per utente. Puoi concedere ad ogni utente l'accesso a un servizio o dispositivo dell'infrastruttura classica effettuando una selezione dalle opzioni di autorizzazione più dettagliate per personalizzare l'accesso di ogni utente.

![Accesso all'infrastruttura classica](images/ClassicIaaS.svg "Assegnazione dell'accesso all'infrastruttura classica selezionando un utente, un dispositivo o servizio e poi una qualsiasi combinazione di autorizzazioni più dettagliate")



## Autorizzazioni dell'infrastruttura classica migrate
{: #predefined}

Una serie di autorizzazioni dell'infrastruttura classica per visualizzare e gestire le informazioni di fatturazione e lavorare con i casi di supporto vengono ora migrate ai gruppi di accesso. Agli utenti del tuo account a cui sono state precedentemente assegnate queste autorizzazioni viene ora assegnato il rispettivo gruppo di accesso delle autorizzazioni migrate. Di conseguenza, le autorizzazioni dell'infrastruttura classica possono essere gestite direttamente utilizzando le politiche di accesso IAM.

Questi gruppi di accesso speciali includono tutte le politiche IAM appropriate per preservare il comportamento originale delle autorizzazioni dell'infrastruttura classica. Ad esempio, perché un utente continui a vedere tutti gli aggiornamenti di tutti gli utenti su un caso di supporto, i gruppi di accesso delle autorizzazioni migrate per le autorizzazioni di gestione dei ticket dell'infrastruttura classica includono una politica IAM aggiuntiva sul servizio di gestione utenti con il ruolo di visualizzatore assegnato. Per ulteriori informazioni, vedi [Assegnazione dell'accesso utente per lavorare con i casi di supporto](/docs/get-support?topic=get-support-access#access).

Puoi continuare a gestire queste autorizzazioni dell'infrastruttura classica migrate per gli utenti direttamente tramite IAM aggiungendole e rimuovendole dai gruppi di accesso delle autorizzazioni migrate. Le politiche di questi gruppi di accesso sono bloccate per preservare il comportamento di accesso per i loro membri. Per mantenere la facilità d'uso per i nuovi utenti IAM, evita di eliminare questi gruppi di accesso.

Dopo la migrazione delle autorizzazioni della tua infrastruttura classica, devi sospendere l'utilizzo di tali autorizzazioni. Vedi la seguente tabella per tutte le autorizzazioni dell'infrastruttura classica migrate che fanno ora parte dei gruppi di accesso IAM.
{: important}

| Nome gruppo di accesso delle autorizzazioni migrate | Azioni consentite |
|----------|---------|
| Visualizza riepilogo account | Visualizzare la pagina di riepilogo dell'account e le fatture e i pagamenti |
| Ottieni report di conformità | Richiedere i report di conformità |
| Modifica profilo azienda | Modificare le informazioni del profilo azienda |
| Pagamenti una tantum | Effettuare pagamenti una tantum sull'account dell'utente |
| Aggiorna dettagli di pagamento | Aggiornare le informazioni sul pagamento mensile ricorrente |
| Limita restrizione casi UE | Abilitare o disabilitare l'opzione Supportato UE che limita i dati dei casi di supporto all'Unione Europea  |
| Aggiungi casi e visualizza ordini | Creare casi di supporto e visualizzare tutti gli ordini.  |
| Modifica casi | Modificare qualsiasi caso di supporto |
| Cerca casi | Cercare tutti i casi di supporto finché non viene assegnata anche l'autorizzazione per visualizzare i casi |
| Visualizza casi | Visualizzare tutti i casi di supporto |
{: caption="Tabella 1. Gruppi di accesso predefiniti" caption-side="top"}

Puoi continuare a gestire gli utenti per i gruppi di accesso. Tuttavia, potrebbe essere utile creare nuovi gruppi di accesso che includano una combinazione di politiche di accesso per i [servizi di gestione dell'account IAM](/docs/iam?topic=iam-account-services#account-services). La seguente tabella descrive i dettagli di una politica di accesso IAM equivalente ai gruppi di accesso di autorizzazioni migrate, in modo da poter ricreare e combinare queste autorizzazioni con altre in un nuovo gruppo di accesso.


| Nome gruppo di accesso delle autorizzazioni migrate | Descrizione | Servizio {{site.data.keyword.cloud_notm}}  |Ruolo IAM|
|-----------------------------------|-------------|-----------------------------------------|----------|
| Visualizza riepilogo account | Visualizzare la pagina di riepilogo dell'account e le fatture e i pagamenti  |  Fatturazione |  Visualizzatore    |
| Ottieni report di conformità | Richiedere i report di conformità | Fatturazione |    Visualizzatore |
| Modifica profilo azienda | Modificare le informazioni del profilo azienda | Fatturazione  | Operatore |
| Aggiorna dettagli di pagamento | Aggiornare le informazioni sul pagamento mensile ricorrente | Fatturazione   | Operatore |
| Limita restrizione casi UE | Abilitare o disabilitare l'opzione Supportato UE che limita i dati dei casi di supporto all'Unione Europea  |   Fatturazione |   Operatore   |
| Aggiungi casi e visualizza ordini | Creare casi di supporto e visualizzare tutti gli ordini.  | Centro di supporto |   Editor   |
| Modifica casi | Modificare qualsiasi caso di supporto | Centro di supporto |   Editor |
| Cerca casi | Cercare tutti i casi di supporto finché non viene assegnata anche l'autorizzazione per visualizzare i casi | Centro di supporto |  Visualizzatore |
| Visualizza casi | Visualizzare tutti i casi di supporto | Centro di supporto | Visualizzatore |
{: caption="Tabella 2. Accesso dell'autorizzazione dell'infrastruttura migrata associato ai ruoli IAM" caption-side="top"}
