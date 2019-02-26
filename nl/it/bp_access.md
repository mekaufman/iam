---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Procedure consigliate per l'assegnazione dell'accesso
{: #account_setup}

Per semplificare il processo di assegnazione dell'accesso, puoi approfittare dei gruppi di accesso per assegnare un numero minimo di politiche fornendo lo stesso accesso a tutti gli utenti e ID servizio che appartengono allo stesso gruppo di accesso. Utilizza queste procedure consigliate per imparare come fornire agli utenti l'accesso alle risorse, ai gruppi di risorse e ai servizi di gestione dell'account.
{:shortdesc}

Per assicurati che il tuo account sia correttamente configurato, verifica le [Procedure consigliate per la configurazione del tuo account](/docs/account?topic=account-account_setup#account_setup) e le [Procedure consigliate per l'organizzazione delle risorse nei gruppi di risorse](/docs/resources?topic=resources-bp_resourcegroups#bp_resourcegroups).
{: tip}

## Che cosa è una buona strategia del gruppo di accesso?
{: #rg_strategy}

Un gruppo di accesso è un raggruppamento di ID servizio e utente a cui può essere concesso lo stesso accesso IAM. Puoi assegnare una sola politica al gruppo invece di assegnare lo stesso accesso più volte per ogni utente o ID del servizio individuale.

Assumendo che hai seguito le [procedure consigliate per la configurazione del tuo account](/docs/account?topic=account-account_setup#account_setup), un modo logico per assegnare l'accesso è creando un gruppo di accesso al livello di accesso desiderato. Quindi, puoi associare ogni gruppo di accesso ai gruppi di risorse creati precedentemente. Ad esempio, per controllare l'accesso al progetto `CustApp`, puoi creare i seguenti gruppi di accesso:

* Auditor-Group
* Developer-Group
* Admin-Group

Per Auditor-Group, assegna due politiche di accesso che concedono l'accesso da visualizzatore ai gruppi di risorse `CustApp-Test` e `CustApp-Prod`. Per Developer-Group, assegna due politiche di accesso che concedono l'accesso da editor agli ambienti `CustApp-Dev` e `CustApp-Test`. Per Admin-Group, assegna tre politiche di accesso che concedono l'accesso da amministratore a tutti e tre i gruppi di risorse `CustApp`.

Anche se questi suggerimenti sono progettati per uno scenario ipotetico, puoi configurare l'associazione del gruppo di accesso al gruppo di risorse adattandolo.

## Creazione dei gruppi di accesso
{: #access-group-setup}

Per creare un gruppo di accesso, completa la seguente procedura: 

1. Nella console {{site.data.keyword.Bluemix}}, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Fai clic su **Create**.
3. Immetti il nome e la descrizione per il gruppo.
4. Fai clic su **Create**.

Dopo aver creato un gruppo di accesso, puoi aggiungere gli utenti e gli ID servizio al gruppo.

## Come le politiche di accesso IAM forniscono l'accesso
{: #how_access}

Una politica include un oggetto, una destinazione e un ruolo. L'oggetto in questo caso è il gruppo di accesso. La destinazione è quello a cui desideri l'oggetto abbia accesso, come ad esempio un insieme di risorse, un'istanza del servizio, tutti i servizi nell'account o tutte le istanze di un servizio. Il ruolo definisce il livello di accesso concesso a un utente.

I ruoli più comunemente utilizzati sono visualizzatore, editor e amministratore. Il ruolo di visualizzatore fornisce la quantità minima di accesso per la visualizzazione delle istanze e dei gruppi di risorse in un account. Il ruolo di editor ha maggior accesso per la creazione, la modifica, l'eliminazione e l'associazione delle istanze del servizio. Il ruolo di amministratore include tutto il necessario ad utilizzare un'istanza del servizio e può assegnare l'accesso ad altri. Tuttavia, ci sono due diverse categorie di ruoli che dovresti considerare: piattaforma e servizio. Per ulteriori informazioni sui ruoli che possono essere assegnati, consulta i [Ruoli IAM Cloud](/docs/iam?topic=iam-iamusermanrol#iamusermanrol). 

## Assegnazione dell'accesso ai gruppi di accesso
{: #assigning-access}

Puoi organizzare le risorse in un gruppo di risorse e gli utenti e gli ID servizio in un gruppo di accesso per rendere l'assegnazione dell'accesso il più semplice possibile. Dopo aver configurato tutto, puoi creare le politiche di accesso per i gruppi di accesso per fornire agli utenti nel tuo account l'accesso alle risorse che hai creato.

1. Fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Seleziona il nome del gruppo di accesso a cui vuoi assegnare l'accesso.
3. Seleziona la scheda **Politiche di accesso**, quindi fai clic su **Assegna accesso**. Hai le seguenti opzioni per l'assegnazione dell'accesso:

  * **Assegna l'accesso alle risorse all'interno di un gruppo di risorse**: utilizza questa opzione per fornire la politica a due parti necessaria agli utenti che creano le risorse dal catalogo e le assegnano a un gruppo di risorse. Quando utilizzi questa opzione, puoi concedere l'accesso al gruppo di risorse stesso e a tutte le risorse in un gruppo di risorse particolare o solo a un servizio o a un'istanza nel gruppo di risorse.
  * **Assegna l'accesso alle risorse**: utilizza questa opzione per assegnare l'accesso a tutti i servizi abilitati IAM nell'account o a un solo servizio nell'account, ma non a un livello dell'istanza.
  * **Assegna l'accesso ai servizi di gestione dell'account**: utilizza questa opzione per fornire un accesso utente ai servizi di gestione dell'account come un modo per delegare alcune delle tue funzionalità gestite nell'account. Ad esempio, puoi delegare la capacità di visualizzare la fatturazione e l'utilizzo, di invitare gli utenti remoti, di gestire i gruppi di accesso, i servizi del catalogo o gli ID servizio. Puoi fornire l'accesso a tutti i servizi di gestione dell'account o a solo uno.

Concedi facilmente a più utenti l'accesso da amministratore a tutto nell'account creando un gruppo di accesso e assegnando due politiche a esso. Per creare la prima politica, utilizza l'opzione **Assegna l'accesso alle risorse** e seleziona **Tutti i servizi abilitati di identità e di accesso** con il ruolo di amministratore assegnato. Per creare la seconda politica, utilizza l'opzione **Assegna l'accesso ai servizi di gestione dell'account** e seleziona **Tutti i servizi di gestione dell'account** con il ruolo di amministratore assegnato.
{: tip}


