---

copyright:

  years: 2019

lastupdated: "2019-02-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Assegnazione dell'accesso ai servizi di gestione dell'account
{: #account-services}

In quanto proprietario dell'account o amministratore di un servizio di gestione dell'account, puoi utilizzare i servizi di gestione dell'account per concedere agli utenti nell'account l'accesso per invitare utenti all'account, tracciare fatturazione e utilizzo e gestire i casi di supporto. Gli utenti con l'accesso possono anche gestire gli ID servizio, le politiche di accesso, le voci di catalogo e i gruppi di accesso.

## Creazione di politiche per l'accesso al servizio di gestione dell'account
{: #account-management-access}

Per assegnare l'accesso a uno o a tutti i servizi di gestione dell'account, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Dalla riga per l'utente a cui desideri assegnare l'accesso, seleziona il menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) e fai clic su **Assegna accesso**.
3. Seleziona per assegnare l'accesso a **Servizi di gestione account**.
4. Seleziona **Tutti i servizi di gestione account** o seleziona un servizio specifico.
5. Seleziona qualsiasi combinazione di ruoli per assegnare l'accesso desiderato.

Per concedere a un altro utente l'accesso completo all'account ai fini della gestione dell'accesso degli utenti e di tutte le risorse dell'account, devi assegnare due politiche. Una politica che consenta all'utente di accedere a tutte le risorse dell'account selezionando **Tutti i sevizi abilitati per l'accesso e l'identità** con il ruolo **Amministratore** assegnato. E una politica che fornisce l'accesso utente a tutti i servizi di gestione dell'account nell'account selezionando **Tutti i servizi di gestione account** con il ruolo assegnato **Amministratore**.
{: tip}

## Associazioni di azioni e ruoli per i servizi di gestione dell'account
{: #account-management-actions-roles}

Le seguenti tabelle descrivono le azioni che gli utenti possono eseguire quando viene loro assegnato uno specifico ruolo per ogni servizio di gestione dell'account. Riesamina le informazioni per assicurarti che stai assegnando il livello di accesso corretto ai tuoi utenti.

| Ruoli | Azioni |
|:-------|----------|
| Visualizzatore |   Visualizza i gruppi di accesso e i membri     |
| Operatore | Non applicabile    |
| Editor |  Visualizza, crea, modifica ed elimina i gruppi <br><br> Aggiungi o rimuovi gli utenti dai gruppi     |
| Amministratore |  Visualizza, crea, modifica ed elimina i gruppi <br><br> Aggiungi o rimuovi gli utenti <br><br> Assegna l'accesso al gruppo <br><br> Gestisci l'accesso per l'utilizzo dei gruppi di accesso   |
{: caption="Tabella 1. Ruoli e azioni di esempio per il servizio Gruppi di accesso" caption-side="top"}

| Ruoli | Azioni |
|:-------|----------|
| Visualizzatore |  Visualizza gli utenti nell'account <br><br> Visualizza le impostazioni del profilo utente     |
| Operatore | Visualizza gli utenti nell'account <br><br> Visualizza le impostazioni del profilo utente  |
| Editor |  Visualizza, invita, rimuove e aggiorna utenti dall'account <br><br> Visualizza e aggiorna le impostazioni del profilo utente    |
| Amministratore | Visualizza, invita, rimuove e aggiorna utenti dall'account <br><br> Visualizza e aggiorna le impostazioni del profilo utente    |
{: caption="Tabella 2. Ruoli e azioni di esempio per il servizio Gestione utenti" caption-side="top"}

| Ruoli | Azioni |
|:-------|----------|
| Visualizzatore |  Visualizza casi <br><br> Cerca casi      |
| Operatore |  Non applicabile    |
| Editor |  Visualizza casi <br><br> Cerca casi <br><br> Aggiorna casi <br><br> Crea casi     |
| Amministratore |  Visualizza casi <br><br> Cerca casi <br><br> Aggiorna casi <br><br> Crea casi    |
{: caption="Tabella 3. Ruoli ed azioni di esempio per il servizio Centro di supporto" caption-side="top"}

| Ruoli | Azioni |
|:-------|----------|
| Visualizzatore | Visualizza le impostazioni della funzione dell'account <br><br> Visualizza le sottoscrizioni nell'account <br><br> Visualizza il nome dell'account <br><br> Visualizza i gruppi di risorse   |
| Operatore | Visualizza le impostazioni della funzione dell'account <br><br> Visualizza le sottoscrizioni nell'account <br><br> Visualizza e modifica il nome dell'account <br><br> Visualizza e aggiorna i gruppi di risorse    |
| Editor |  Visualizza e aggiorna le impostazioni della funzione dell'account <br><br> Visualizza le sottoscrizioni nell'account <br><br> Visualizza le offerte nell'account <br><br> Visualizza e applica i codici funzione <br><br> Visualizza e modifica il nome dell'account <br><br> Visualizza e aggiorna i limiti di spesa <br><br> Visualizza, crea e aggiorna i gruppi di risorse    |
| Amministratore |  Visualizza e aggiorna le impostazioni della funzione dell'account <br><br> Visualizza le sottoscrizioni nell'account <br><br> Visualizza le offerte nell'account <br><br> Visualizza e applica i codici funzione <br><br> Visualizza e modifica il nome dell'account <br><br> Visualizza e aggiorna i limiti di spesa <br><br> Visualizza i bilanci della sottoscrizione e traccia l'utilizzo <br><br> Visualizza, crea, aggiorna e assegna l'accesso per gestire i gruppi di risorse  |
{: caption="Tabella 4. Ruoli ed azioni di esempio per il servizio Fatturazione" caption-side="top"}

| Ruoli | Azioni |
|:-------|----------|
| Visualizzatore |   Visualizza ID     |
| Operatore | Creare ed eliminare ID e chiavi API   |
| Editor |  Crea, aggiorna ed elimina ID e chiavi API  |
| Amministratore |  Crea, aggiorna ed elimina ID e chiavi API <br><br> Assegna l'accesso alle politiche e agli ID  |
{: caption="Tabella 5. Ruoli ed azioni di esempio per il servizio Identità IAM" caption-side="top"}

Per il servizio di identità IAM, queste azioni si applicano agli ID servizio all'interno dell'account che l'utente non ha creato. Tutti gli utenti possono creare gli ID servizio. Questi sono gli amministratori di tali ID e possono creare la chiave API associata e le politiche di accesso. Tuttavia, questo servizio di gestione dell'account si applica alla capacità di visualizzare, eliminare ed assegnare l'accesso agli ID servizio nell'account creato da altri utenti.
{: note}

| Ruoli | Azioni |
|:-------|----------|
| Visualizzatore |   Visualizza i servizi privati    |
| Operatore | Non applicabile    |
| Editor | Modifica i metadati dell'oggetto ma non può modificare la visibilità per i servizi privati   |
| Amministratore |   Modifica i metadati dell'oggetto o la visibilità per i servizi privati e limita la visibilità di un servizio pubblico.   |
{: caption="Tabella 6. Ruoli e azioni di esempio per il servizio Catalogo globale" caption-side="top"}

| Ruoli | Azioni |
|:-------|----------|
| Visualizzatore |  Tutte le azioni del ruolo visualizzatore per i servizi di gestione dell'account     |
| Operatore |  Tutte le azioni del ruolo operatore per i servizi di gestione dell'account     |
| Editor |  Tutte le azioni del ruolo editor per i servizi di gestione dell'account     |
| Amministratore |  Tutte le azioni del ruolo amministratore per i servizi di gestione dell'account   |
{: caption="Tabella 7. Ruoli e azioni di esempio per una politica su tutti i servizi di identità e di accesso" caption-side="top"}
