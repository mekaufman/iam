---

copyright:

  years: 2019

lastupdated: "2019-05-13"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}


# Gestione delle autorizzazioni dell'account SoftLayer migrate 
{: #migrated_permissions}

I gruppi di accesso includono ora una serie di autorizzazioni dell'account SoftLayer migrate per visualizzare e gestire le informazioni di fatturazione e lavorare con i casi di supporto. Agli utenti del tuo account a cui sono state precedentemente assegnate queste autorizzazioni viene ora assegnato il rispettivo gruppo di accesso delle autorizzazioni migrate. Di conseguenza, le autorizzazioni possono essere gestite direttamente utilizzando i gruppi di accesso IAM.
{:shortdesc}

Questi gruppi di accesso speciali includono tutte le politiche IAM appropriate per preservare il comportamento originale delle autorizzazioni dell'account SoftLayer. Ad esempio, per permettere a un utente di continuare a visualizzare tutti gli aggiornamenti da tutti gli utenti su un caso di supporto, i gruppi di accesso dell'autorizzazione migrata per le autorizzazioni dell'account SoftLayer per la creazione di ticket, includono un'ulteriore politica IAM sul servizio di gestione dell'utente con il ruolo di visualizzatore assegnato. Per ulteriori informazioni, vedi [Assegnazione dell'accesso utente per lavorare con i casi di supporto](/docs/get-support?topic=get-support-access#access).

Puoi continuare a gestire queste autorizzazioni dell'infrastruttura classica migrate per gli utenti direttamente tramite IAM aggiungendole e rimuovendole dai gruppi di accesso delle autorizzazioni migrate. Le politiche di questi gruppi di accesso sono bloccate per preservare il comportamento di accesso per i loro membri. Per mantenere la facilità d'uso per i nuovi utenti IAM, evita di eliminare questi gruppi di accesso.

Dopo la migrazione delle autorizzazioni della tua infrastruttura classica, devi sospendere l'utilizzo di tali autorizzazioni. Vedi la seguente tabella per tutte le autorizzazioni dell'infrastruttura classica migrate che fanno ora parte dei gruppi di accesso IAM.
{: important}

| Nome gruppo di accesso delle autorizzazioni migrate | Azioni consentite |
|----------|---------|
| Visualizza riepilogo account |Visualizzare la pagina di riepilogo dell'account e le fatture e i pagamenti.|
| Ottieni report di conformità |Richiede il report di conformità.|
| Modifica profilo azienda |Modificare le informazioni del profilo azienda.|
| Pagamenti una tantum |Effettuare pagamenti una tantum nell'account dell'utente. |
| Aggiorna dettagli di pagamento |Aggiornare le informazioni sul pagamento mensile ricorrente.|
| Limita restrizione casi UE |Abilitare o disabilitare l'opzione Supportato UE che limita i dati dei casi di supporto all'Unione Europea.|
| Aggiungi casi e visualizza ordini | Creare casi di supporto e visualizzare tutti gli ordini.  |
| Modifica casi |Modificare qualsiasi caso di supporto.|
| Cerca casi |Ricercare tutti i casi di supporto se viene assegnata anche l'autorizzazione per visualizzare i casi. |
| Visualizza casi |Visualizzare tutti i casi di supporto.|
{: caption="Tabella 1. Gruppi di accesso predefiniti" caption-side="top"}

