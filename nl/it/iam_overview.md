---

copyright:

  years: 2017, 2019

lastupdated: "2019-07-25"

keywords: user identities, service ID, policies, access management, roles, actions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:external: target="_blank" .external}

# Concetti di IAM
{: #iamconcepts}

Due concetti maggiori si distinguono quando vuoi ottenere ulteriori informazioni su {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM): gestione di identità e accesso. Inoltre, puoi ottenere informazioni sui gruppi di accesso, i gruppi di risorse, gli utenti, i ruoli, le politiche di accesso e altro ancora.
{: shortdesc}

## Identità
{: #identity}

Il concetto di identità in {{site.data.keyword.Bluemix_notm}} IAM è costituito dalle identità utente, dalle identità servizio e applicazione, dalle chiavi API e dalle risorse. Gli utenti vengono identificati tramite il proprio ID IBM o ID account SoftLayer. Gli ID servizio sono un tipo secondario di identità che viene utilizzato in un account. Gli ID servizio rappresentano la funzione di Cloud IAM utilizzata per fornire un'identità separata per i servizi e le applicazioni. Puoi creare un ID servizio che venga utilizzato da un'applicazione che deve accedere ai tuoi servizi {{site.data.keyword.Bluemix_notm}} in modo che non sia necessario utilizzare le credenziali dei singoli utenti.

Per l'autenticazione tramite l'API o la CLI come utente o ID servizio, possono essere utilizzate le chiavi API {{site.data.keyword.cloud_notm}}. Queste chiavi API vengono fornite tramite Cloud IAM e pertanto non possono essere utilizzate generalmente per l'autenticazione con l'ID IBM all'esterno di IBM Cloud. Un utente può anche avere una singola chiave API dell'infrastruttura classica che può essere utilizzata per accedere alle API dell'infrastruttura classica; tuttavia, questa non è necessaria perché puoi utilizzare le chiavi API {{site.data.keyword.cloud_notm}} per accedere alle stesse API.

L'ultimo tassello mancante del concetto di identità in IAM sono le risorse {{site.data.keyword.Bluemix_notm}}, che vengono identificate dai loro nomi di risorsa cloud (CRN). Per ulteriori informazioni, vedi [Nomi delle risorse cloud](/docs/overview?topic=overview-crn#crn).

## Gestione accesso
{: #am}

Il concetto di gestione dell'accesso in {{site.data.keyword.Bluemix_notm}} è costituito da alcuni componenti correlati, inclusi utenti, risorse, politiche, ruoli, azioni e il sistema di controllo {{site.data.keyword.Bluemix_notm}} IAM, che consentono agli utenti di intraprendere azioni sulle risorse all'interno di un account.

{{site.data.keyword.Bluemix_notm}} IAM segue un modello di eventuale congruenza ([eventually consistent](https://en.wikipedia.org/wiki/Eventual_consistency){: external}) comune per molti servizi nativi cloud, il quale consente a IAM di rimanere altamente disponibile e performante tra più regioni globali. Le modifiche apportate a politiche di accesso, autorizzazioni, ID servizio, chiavi API, gruppi di accesso, gruppi di risorse, utenti o qualsiasi altro controllo dell'accesso IAM; sono registrate e propagate a tutti i componenti IAM e ai servizi abilitati IAM nel mondo. Le modifiche all'accesso non possono essere effettive finché il processo di propagazione non viene completato.

### Utenti
{: #iam-users}

Tutti gli utenti all'interno di un account sono identificati dai loro ID IBM o dai loro ID account SoftLayer. Gli utenti possono essere invitati all'account e avere accesso alle risorse. Le politiche di accesso iniziano con l'oggetto che spesso è un utente nel tuo account. L'accesso può essere assegnato ai servizi di gestione dell'account e a singole risorse, fino al livello di istanza, o a un insieme di risorse che sono organizzate in un gruppo di risorse dell'account.


### Gruppi di accesso
{: #access-groups-iam}

Un gruppo di utenti e di ID del servizio può essere creato in modo che lo stesso accesso possa essere assegnato a tutte le entità all'interno del gruppo con una o più politiche. Mediante l'utilizzo dei gruppi di accesso, puoi semplificare il processo di assegnazione dell'accesso in modo da poter gestire una quantità più piccola di politiche e ridurre il numero di politiche in un account, la qual cosa incrementa le prestazioni. Dopo aver configurato i tuoi gruppi, puoi iniziare ad assegnare le politiche selezionando un gruppo di accesso come l'oggetto della politica. Per ulteriori informazioni, vedi [Configurazione dei gruppi di accesso](/docs/iam?topic=iam-groups).

### Risorse
{: #resources-access-management}

Le risorse dell'account sono le offerte dei servizi con provisioning selezionate dal catalogo o le risorse specifiche all'interno di un'istanza del servizio. Queste risorse vengono aggiunte a un gruppo di risorse quando vengono create dal catalogo. La gestione dell'accesso IAM abilita l'accesso granulare, il che significa che una politica può essere impostata su più ampia scala, ad esempio su tutte le risorse in gruppo di risorse oppure su un tipo di risorsa specifica come un bucket {{site.data.keyword.cos_full_notm}} all'interno di un'istanza specifica.


### Politiche di accesso
{: #access-policies-concept}

Le politiche di accesso sono il modo in cui gli utenti, gli ID servizio e i gruppi di accesso nell'account ricevono l'autorizzazione per accedere alle risorse dell'account. Le politiche includono un oggetto, una destinazione e un ruolo. L'oggetto è l'utente, l'ID servizio o il gruppo di accesso a cui stai fornendo l'accesso. La destinazione della politica è la risorsa per la quale vuoi fornire l'accesso. I ruoli sono il modo per definire il livello di accesso o le azioni consentite sulla destinazione della politica. Ci sono diversi tipi di politiche che consentono l'accesso alle risorse dell'account: una politica del gruppo di risorse, una politica dell'istanza della risorsa, una politica a livello di account per l'accesso a tutti i servizi abilitati per l'accesso e l'identità e una politica su uno o tutti i servizi di gestione dell'account. A seconda delle tue selezioni, potrebbero essere disponibili delle opzioni di configurazione personalizzate come la definizione dell'accesso alle risorse in una regione specifica o la definizione dell'accesso al livello granulare di una risorsa specifica del servizio all'interno di un'istanza.

### Ruoli
{: #iam-roles-concept}

I ruoli di accesso Cloud IAM consentono a un utente di completare attività specifiche sulla risorsa definita nella politica. Esistono due tipi di ruoli di accesso: gestione della piattaforma e accesso al servizio. 

I ruoli di gestione della piattaforma definiscono le azioni consentite per la gestione delle risorse a livello di piattaforma come l'accesso utente e la creazione delle istanze del servizio. I ruoli della piattaforma si applicano anche alle azioni che possono essere eseguite nel contesto dei servizi di gestione dell'account come l'invito e la rimozione degli utenti, la gestione dei gruppi di accesso, la gestione degli ID servizio e le offerte del catalogo privato. 

I ruoli di accesso al servizio definiscono le azioni consentite nel contesto dell'utilizzo del servizio come la chiamata delle API del servizio. Questi ruoli sono personalizzati in base al servizio selezionato nella politica.

### Azioni
{: #iam-roles-actions}

Le azioni vengono associate ai ruoli Cloud IAM per consentire agli utenti di eseguire solo attività specifiche quando vengono assegnati i diversi ruoli. Le azioni consentite per ciascun ruolo potrebbero cambiare in base al servizio a cui si accede poiché ogni servizio definisce il modo in cui quel ruolo viene associato all'utilizzo del servizio.

### Sistema di gestione degli accessi
{: #access-management-system}

Il sistema di controllo di Cloud IAM consente o nega le azioni degli utenti nel contesto di un servizio in base alla politica assegnata. Quando un utente tenta di completare un'azione specifica, il sistema di controllo utilizza gli attributi definiti nella politica per determinare se l'utente dispone dell'autorizzazione per eseguire tale attività.
