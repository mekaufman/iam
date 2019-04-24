---

copyright:

  years: 2015, 2019

lastupdated: "2019-01-29"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:new_window: target="_blank"}

# Accesso IAM
{: #userroles}

Tutti i servizi che sono organizzati in un gruppo di risorse nel tuo account vengono gestiti utilizzando {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM). Ai proprietari dell'account viene assegnato automaticamente il ruolo di amministratore di account per Cloud IAM. Come amministratore dell'account puoi assegnare e gestire l'accesso per gli utenti, creare gruppi di risorse, creare gruppi di accesso, visualizzare i dettagli di fatturazione e tracciare l'utilizzo e creare le istanze del servizio. Fornisci l'accesso per gli utenti, gli ID servizio e i gruppi di accesso creando delle politiche che impostano una destinazione per un oggetto della politica per accedere e un ruolo che definisce quale tipo di accesso è consentito.
{: shortdesc}

## Cosa sono le politiche Cloud IAM e chi può assegnarle?
{: #iamusermanpol}

Una politica concede a un oggetto uno o più ruoli per un insieme di risorse per effettuare azioni specifiche all'interno del contesto delle risorse di destinazione specificate. Puoi assegnare e gestire le politiche se hai il ruolo appropriato. La seguente tabella mostra le attività di gestione delle politiche e il ruolo richiesto per ciascuna.

| Azione | Ruolo richiesto |
|----------|---------|
| Creare una politica in un account per tutti i servizi e le istanze | Proprietario o amministratore dell'account su tutti i servizi di gestione dell'account e tutti i servizi abilitati per l'accesso e l'identità | 
| Creare una politica su un servizio in un account | Proprietario dell'account, amministratore su tutti i servizi abilitati per l'accesso e l'identità o amministratore sul servizio nell'account |
| Creare una politica su un'istanza del servizio | Proprietario dell'account, amministratore su tutti i servizi abilitati per l'accesso e l'identità, amministratore sul servizio nell'account, amministratore su tutti i servizi nel gruppo di risorse relativo o amministratore sull'istanza del servizio |
{: caption="Tabella 1. Utenti autorizzati a creare politiche di accesso" caption-side="top"} 

Quando assegni una politica, inizi con l'oggetto. Dopo aver selezionato l'oggetto della politica, puoi scegliere di impostare la politica per un gruppo di risorse, una risorsa individuale o un servizio di gestione dell'account. 

Quindi, a seconda della tua selezione iniziale, puoi selezionare dalle opzioni:
  
  * Un servizio all'interno di un gruppo di risorse
  * Tutte le risorse in un gruppo di risorse
  * Tutte le istanze o una sola istanza per la risorsa selezionata
  * Tutti i servizi abilitati IAM nell'account
  * Un servizio di gestione dell'account 

Potrebbero essere disponibili altre opzioni di configurazione, a seconda del servizio che selezioni. Infine, seleziona i ruoli da assegnare. 

## Tipi di politica di accesso comuni
{: #policytypes}

Puoi fornire l'accesso dettagliato per gli utenti, gli ID servizio o i gruppi di accesso assegnando i seguenti tipi di politiche di accesso:

* Tutti i servizi di gestione dell'account
* Servizio di gestione dell'account specifico
* Tutte le risorse nell'account
* Tutte le risorse all'interno di tutti i servizi che appartengono a un singolo gruppo di risorse con la possibilità di gestire il gruppo di risorse
* Tutte le risorse all'interno di un singolo servizio in un gruppo di risorse con la possibilità di gestire il gruppo di risorse
* Tutte le risorse all'interno di un singolo servizio nell'account, indipendentemente dal gruppo di risorse a cui sono assegnate
* Le risorse in una singola istanza
* Un singolo tipo di risorsa all'interno di un'istanza, ad esempio un bucket in un'istanza {{site.data.keyword.objectstorageshort}}

Per concedere a un altro utente l'accesso completo all'account ai fini della gestione dell'accesso degli utenti e della gestione di tutte le risorse dell'account, devi assegnare due politiche. Una politica che consenta all'utente di accedere a tutte le risorse dell'account selezionando **Tutti i sevizi abilitati per l'accesso e l'identità** con il ruolo **Amministratore** assegnato. E una politica che fornisce l'accesso utente a tutti i servizi di gestione dell'account nell'account selezionando **Tutti i servizi di gestione account** con il ruolo assegnato **Amministratore**.
{: tip}

## Ruoli Cloud IAM
{: #iamusermanrol}

Con Cloud IAM, puoi gestire e definire l'accesso per gli utenti e le risorse nel tuo account. Possono essere assegnati due tipi di ruoli: i ruoli di gestione della piattaforma e i ruoli di accesso al servizio.

<dl>
<dt>Ruoli di gestione della piattaforma</dt> 
<dd>I ruoli di gestione della piattaforma coprono una gamma di azioni, inclusa la capacità di creare ed eliminare le istanze, gestire gli alias, i bind e le credenziali e gestire l'accesso. I ruoli della piattaforma sono amministratore, editor, operatore, visualizzatore. I ruoli di gestione della piattaforma si applicano anche ai servizi di gestione dell'account che consentono agli utenti di invitare utenti, gestire ID di servizio, politiche di accesso, voci di catalogo e tenere traccia della fatturazione e dell'utilizzo in base al proprio ruolo assegnato in un servizio di gestione dell'account.</dd>
<dt>Ruoli di accesso al servizio</dt>
<dd>I ruoli di accesso al servizio definiscono la capacità di un utente o un servizio di eseguire azioni su un'istanza del servizio, come l'accesso alla console o l'esecuzione di chiamate API. I ruoli di accesso al servizio sono gestore, scrittore e lettore. </dd>
</dl> 

Potresti non vedere tutti i ruoli qui elencati come opzioni quando assegni le politiche nell'interfaccia utente perché vengono visualizzati solo i ruoli disponibili per il servizio che hai scelto. Per ulteriori informazioni su quali ruoli sono abilitati e quali azioni sono consentite da ciascun ruolo di accesso per ciascun servizio, consulta la documentazione relativa a tale servizio.
{: note}

### Ruoli di gestione della piattaforma
{: #platformroles}

Con i ruoli di gestione della piattaforma è possibile assegnare agli utenti diversi livelli di autorizzazione per l'esecuzione di azioni della piattaforma all'interno dell'account o su un servizio. Ad esempio, i ruoli di gestione della piattaforma assegnati alle risorse di catalogo, consentono agli utenti di completare azioni come la creazione, l'eliminazione, la modifica e la visualizzazione delle istanze del servizio. Mentre i ruoli di gestione della piattaforma assegnati ai servizi di gestione dell'account consentono agli utenti di completare azioni come l'invito e la rimozione degli utenti, l'utilizzo dei gruppi di risorse e la visualizzazione delle informazioni di fatturazione. Per ulteriori informazioni sui servizi di gestione dell'account, consulta [Tabella 3. Ruoli e azioni di gestione di esempio per i servizi di gestione dell'account](#platformrolestable2).

Le seguenti tabelle forniscono esempi di alcune delle azioni di gestione della piattaforma che gli utenti possono effettuare nel contesto delle risorse del catalogo, dei gruppi di risorse e dei servizi di gestione dell'account. Consulta la documentazione di ogni offerta del catalogo per comprendere in che modo i ruoli vengano applicati agli utenti nel contesto del servizio utilizzato.

La prima riga della tabella descrive le distinte opzioni da cui puoi scegliere quando crei una politica e la prima colonna descrive i ruoli selezionati per la politica. Le restanti celle associano il ruolo selezionato dalla prima colonna al tipo di politica selezionato dalle opzioni nella prima riga.

| Dettagli della politica di accesso | Azioni sui servizi nell'account | Azioni sulle risorse nei gruppi di risorse | Azioni per l'accesso ai gruppi di risorse |
|:--------------|:------------|:-------------|:-------------|
|  | Uno o tutti i servizi abilitati a IAM | Servizio selezionato in un gruppo di risorse | Gruppo di risorse selezionato |
| Ruolo visualizzatore | Visualizzare istanze, alias, bind e credenziali | Visualizzare solo le istanze specificate nel gruppo di risorse | Visualizzare il gruppo di risorse |
| Ruolo operatore |  Visualizzare istanze e gestire alias, bind e credenziali |  Non applicabile | Non applicabile |
| Ruolo editor |  Creare, eliminare, modificare e visualizzare istanze. Gestire alias, bind e credenziali | Creare, eliminare, modificare, sospendere, riprendere, visualizzare e associare solo le istanze specificate nel gruppo di risorse | Visualizzare e modificare il nome del gruppo di risorse |
| Ruolo amministratore |  Tutte le azioni di gestione per i servizi | Tutte le azioni di gestione per le istanze specificate nel gruppo di risorse | Visualizzare, modificare e gestire l'accesso per il gruppo di risorse |
{: caption="Tabella 2. Ruoli e azioni di esempio per la gestione dei servizi in un account" caption-side="top"}
{: #platformrolestable1}

La seguente tabella descrive le azioni comuni che puoi eseguire in base al ruolo che ti viene assegnato per ogni servizio di gestione dell'account. Scorri orizzontalmente per visualizzare tutte le voci nella tabella.
{: #acctmgmt}

Se assegni una politica di accesso a **Tutti i servizi di gestione account**, a seconda del ruolo che selezioni, l'utente può completare le seguenti azioni per ogni servizio di tale ruolo. Inoltre, questo tipo di politica fornisce l'accesso utente alle informazioni di fatturazione e la capacità di tenere traccia dell'utilizzo in base al proprio ruolo assegnato. Per dettagli, consulta la seguente tabella.
{: note}

La prima riga della tabella descrive gli specifici servizi da cui puoi scegliere quando crei una politica e la prima colonna descrive il tipo di ruolo selezionato per la politica. Le restanti celle associano il ruolo selezionato dalle opzioni nella prima colonna al tipo di politica selezionato dalle opzioni nella prima riga.

| Dettagli della politica di accesso |  Azioni per gli ID di servizio  | Azioni per la gestione dei gruppi di accesso | Azioni per la gestione dell'accesso al catalogo | Azioni per l'accesso alla gestione degli utenti | Azioni per il supporto | Azioni per la fatturazione | Azioni per tutti i servizi di gestione account | 
|:--------------|:-------------|:--------------|:--------------|:-----------|:--------------|:--------------|:--------------|
|  |  Servizio di identità IAM |  Gruppi di accesso IAM |  Catalogo risorse globali |  Gestione utenti  | Centro di supporto | Fatturazione e utilizzo | Tutti i servizi di gestione dell'account |
| Ruolo visualizzatore |  <ul><li>Visualizza ID</li></ul> |  <ul><li>Visualizza i gruppi di accesso e i membri</li></ul> | <ul><li>Visualizza i servizi privati</li></ul>  |  <ul><li>Visualizza gli utenti nell'account</li><li>Visualizza le impostazioni del profilo utente</li></ul> | <ul><li>Visualizza casi</li><li>Cerca casi</li></ul> | <ul><li>Visualizza le impostazioni della funzione dell'account</li><li>Visualizza le sottoscrizioni nell'account</li><li>Visualizza il nome dell'account</li><li>Visualizza i gruppi di risorse</li></ul> | Tutte le azioni del ruolo visualizzatore per i servizi di gestione dell'account |
| Ruolo operatore | <ul><li>Crea ed elimina ID e chiavi API</li></ul> |  <ul><li>Non applicabile</li></ul> | <ul><li>Non applicabile</li></ul> |  <ul><li>Visualizza gli utenti nell'account</li><li>Visualizza le impostazioni del profilo utente</li></ul> | <ul><li>Non applicabile</li></ul> | <ul><li>Visualizza le impostazioni della funzione dell'account</li><li>Visualizza le sottoscrizioni nell'account</li><li>Visualizza e modifica il nome dell'account</li><li>Visualizza e aggiorna i gruppi di risorse</li></ul> | Tutte le azioni del ruolo operatore per i servizi di gestione dell'account |
| Ruolo editor |  <ul><li>Crea, aggiorna ed elimina ID e chiavi API</li></ul> |  <ul><li>Visualizza, crea, modifica ed elimina i gruppi</li><li>Aggiungi o rimuovi gli utenti dai gruppi</li></ul> | <ul><li>Può modificare i metadati dell'oggetto ma non può modificare la visibilità per i servizi privati</li></ul>  | <ul><li>Visualizza, invita, rimuove e aggiorna utenti dall'account</li><li>Visualizza e aggiorna le impostazioni del profilo utente</li></ul> |  <ul><li>Visualizza casi</li><li>Cerca casi</li><li>Aggiorna casi</li><li>Crea casi</li></ul> | <ul><li>Visualizza e aggiorna le impostazioni della funzione dell'account</li><li>Visualizza le sottoscrizioni nell'account</li><li>Visualizza le offerte nell'account</li><li>Visualizza e applica i codici funzione</li><li>Visualizza e modifica il nome dell'account</li><li>Visualizza e aggiorna i limiti di spesa</li><li>Visualizza, crea e aggiorna i gruppi di risorse</li></ul> | Tutte le azioni del ruolo editor per i servizi di gestione dell'account |
| Ruolo amministratore |   <ul><li>Crea, aggiorna ed elimina ID e chiavi API</li><li>Assegna l'accesso alle politiche e agli ID</li></ul> |  <ul><li>Visualizza, crea, modifica ed elimina i gruppi</li><li>Aggiungi o rimuovi gli utenti</li><li>Assegna l'accesso al gruppo</li><li>Gestisci l'accesso per l'utilizzo dei gruppi di accesso</li></ul> | <ul><li>Può modificare i metadati dell'oggetto o la visibilità per i servizi privati e limitare la visibilità di un servizio pubblico.</li></ul> | <ul><li>Visualizza, invita, rimuove e aggiorna utenti dall'account</li><li>Visualizza e aggiorna le impostazioni del profilo utente</li></ul> |  <ul><li>Visualizza casi</li><li>Cerca casi</li><li>Aggiorna casi</li><li>Crea casi</li></ul> |  <ul><li>Visualizza e aggiorna le impostazioni della funzione dell'account</li><li>Visualizza le sottoscrizioni nell'account</li><li>Visualizza le offerte nell'account</li><li>Visualizza e applica i codici funzione</li><li>Visualizza e modifica il nome dell'account</li><li>Visualizza e aggiorna i limiti di spesa</li><li>Visualizza i bilanci della sottoscrizione e traccia l'utilizzo</li><li>Visualizza, crea, aggiorna e assegna l'accesso per gestire i gruppi di risorse</li></ul> | Tutte le azioni del ruolo amministratore per i servizi di gestione dell'account|
{: caption="Tabella 3. Ruoli e azioni di esempio per la gestione della piattaforma per i servizi di gestione dell'account" caption-side="top"}
{: #platformrolestable2}

Per il servizio di identità IAM, queste azioni si applicano agli ID servizio all'interno dell'account che l'utente non ha creato. Tutti gli utenti possono creare gli ID servizio. Questi sono gli amministratori di tali ID e possono creare la chiave API associata e le politiche di accesso, ma questo servizio di gestione dell'account si applica alla possibilità di visualizzare, eliminare ed assegnare l'accesso agli ID servizio nell'account creato da altri utenti.
{: note}

Alcuni servizi potrebbero associare specifiche azioni ai ruoli di gestione della piattaforma correlati alla gestione del servizio piuttosto che all'accesso del servizio. Come esempio, consulta la seguente tabella che descrive le azioni del servizio {{site.data.keyword.containershort_notm}} associate a questi ruoli.

| Ruolo di gestione della piattaforma | Azioni | Azioni di esempio per {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Visualizzatore | Può visualizzare le istanze del servizio ma non può modificarle  | <ul><li>Elencare i cluster</li><li>Visualizzare i dettagli per un cluster</li></ul>|
| Editor | Eseguire tutte le azioni di piattaforma eccetto la gestione dell'account e l'assegnazione delle politiche di accesso |<ul><li>Eseguire il bind di un servizio a un cluster</li><li>Crea un webhook</li></ul> |
| Operatore | Eseguire le azioni di piattaforma necessarie per configurare e gestire le istanze del servizio, come ad esempio visualizzare il dashboard di un servizio | <ul><li>Aggiungere o rimuovere i nodi di lavoro</li><li>Riavviare o ricaricare i nodi di lavoro</li><li>Eseguire il bind di un servizio a un cluster</li></ul> |
| Amministratore | Eseguire tutte le azioni di piattaforma in base alla risorsa assegnata a questo ruolo, inclusa l'assegnazione di politiche di accesso ad altri utenti |<ul><li>Rimuovere un cluster</li><li>Creare un cluster</li><li>Aggiorna le politiche di accesso utente</li><li>Tutte le azioni che possono essere eseguite da un visualizzatore, un operatore e un editor</li></ul>|
{: caption="Tabella 4. Ruoli e azioni di esempio per la gestione della piattaforma per il servizio {{site.data.keyword.containershort_notm}}" caption-side="top"}

### Ruoli di accesso al servizio

I ruoli di accesso al servizio consentono di assegnare agli utenti diversi livelli di autorizzazione per richiamare l'API del servizio e accedere all'interfaccia utente del servizio. La seguente tabella fornisce le azioni di esempio che è possibile eseguire a seconda dei ruoli assegnati in base all'utilizzo del servizio {{site.data.keyword.objectstorageshort}}.

Le azioni che possono essere eseguite in base a ciascun ruolo assegnato variano in base al servizio che hai selezionato per la politica. Non tutti i servizi utilizzano questi tipi di ruoli. Consulta la documentazione del servizio per maggiori dettagli.
{: note}

| Ruolo di accesso al servizio | Azioni | Azioni di esempio per il servizio {{site.data.keyword.objectstorageshort}} |
|:-----------------|:-----------------|:-----------------|
|  Lettore | Eseguire azioni di sola lettura all'interno di un servizio, ad esempio visualizzare le risorse specifiche del servizio | Elencare e scaricare oggetti |
| Scrittore | Autorizzazioni al di sopra del ruolo di lettore, incluse la creazione e la modifica di risorse specifiche del servizio | Creare ed eliminare bucket e oggetti |
| Gestore | Autorizzazioni al di sopra del ruolo di scrittore per completare le azioni privilegiate definite dal servizio, più le risorse specifiche del servizio di creazione e modifica | Gestire tutti gli aspetti dell'archiviazione dati, creare ed eliminare bucket e oggetti |
{: caption="Tabella 5. Ruoli utente e azioni di esempio per l'accesso al servizio" caption-side="top"}



