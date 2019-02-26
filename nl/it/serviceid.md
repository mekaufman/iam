---

copyright:

  years: 2017, 2019
  
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Creazione e gestione degli ID servizio
{: #serviceids}

Un ID servizio identifica un servizio o un'applicazione analogamente a come un ID utente identifica un utente. Un ID servizio da te creato può essere utilizzato per abilitare un'applicazione esterna a {{site.data.keyword.Bluemix_notm}} ad accedere ai tuoi servizi {{site.data.keyword.Bluemix_notm}}. Puoi assegnare delle specifiche politiche di accesso all'ID servizio che limitano le autorizzazioni per l'utilizzo di specifici servizi o anche combinare le autorizzazioni per l'accesso a servizi differenti. Poiché gli ID servizio non sono collegati a uno specifico utente, se capita che un utente lasci un'organizzazione e venga eliminato dall'account, l'ID servizio rimane, garantendo che la tua applicazione o il tuo servizio continuino a essere attivi e in esecuzione.

Quando crei un ID servizio, crei un nome univoco e una descrizione per te facili da identificare e gestire nell'IU. Dopo che hai creato il tuo ID servizio, puoi creare delle chiavi API specifiche per ciascun ID servizio che la tua applicazione può utilizzare per l'autenticazione presso i tuoi servizi {{site.data.keyword.Bluemix_notm}}. Per garantire che la tua applicazione disponga dell'accesso appropriato per eseguire l'autenticazione presso i tuoi servizi {{site.data.keyword.Bluemix_notm}}, utilizzi le politiche di accesso assegnate a ciascun ID servizio che crei. 

Le politiche di accesso associate a un ID servizio abilitano delle specifiche azioni che possono essere eseguite quando tale ID servizio viene utilizzato per accedere a uno specifico servizio. Un singolo ID servizio può avere più politiche assegnate che definiscono il livello di accesso consentito quando si accede a più servizi di identità e abilitati all'accesso e anche a diverse istanze di un singolo servizio. Ad esempio, hai due servizi con due istanze del servizio ciascuno. Potresti assegnare il ruolo Visualizzatore per tutte le istanze disponibili di un servizio e assegnare il ruolo Editor per una sola istanza di un secondo servizio. In questo modo, puoi personalizzare l'accesso a più servizi ma utilizzare una singola chiave API per l'autenticazione per tutti.


## Creazione di un ID servizio
{: #create_serviceid}

Per creare un ID servizio, completa la seguente procedura:

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**. 
2. Fai clic su **Create**.
3. Attieniti alla procedura per creare un nome e una descrizione per il tuo ID servizio. 
4. Fai clic su **Create**. 

Quindi, passa con il mouse sulla riga di un ID servizio per utilizzare il menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) e gestire il tuo ID servizio. Puoi iniziare assegnando una politica e creando le chiavi API. Per ulteriori informazioni sulla gestione delle chiavi API, consulta [Gestione delle chiavi API di un ID servizio](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys). 

## Aggiornamento di un ID servizio
{: #update_serviceid}

Puoi aggiornare un ID servizio modificando il nome e la descrizione in qualsiasi momento. Puoi anche eliminare e creare nuove chiavi API come necessario oppure aggiornare le politiche di accesso assegnate. Passa con il mouse sulla riga di un ID servizio per utilizzare il menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) e gestire il tuo ID servizio.

Qualsiasi modifica apportata a un ID servizio esistente, come la modifica delle politiche assegnate o l'eliminazione di una chiave API attualmente in uso, potrebbe causare interruzioni del servizio per le applicazioni che utilizzano tale ID servizio.

## Blocco di un ID servizio
{: #lock_serviceid}

Per evitare situazioni in cui l'ID servizio viene eliminato causando interruzioni per gli utenti del tuo servizio, hai la possibilità di bloccare il tuo ID servizio utilizzando la IU o la CLI. Il blocco di un ID servizio impedisce inoltre la modifica, l'eliminazione o l'assegnazione di eventuali politiche. Oltre alla possibilità di bloccare un ID servizio, puoi [bloccare singole chiavi API](/docs/iam?topic=iam-lockkey#lockkey) associate a ciascun ID servizio che hai creato nel tuo account. 

Mentre gli ID servizio bloccati non possono essere eliminati dall'account e le politiche di accesso non possono essere aggiornate, gli ID servizio bloccati possono ancora essere rimossi da qualsiasi gruppo di accesso a cui sono stati aggiunti. Questo significa che tutto l'accesso assegnato all'ID dalla sua appartenenza a un gruppo di accesso, viene rimosso quando l'ID servizio viene rimosso dal gruppo di accesso.
{: note}

### Fornisci l'accesso utente per il blocco degli ID servizio
{: #access_lock_serviceid}

Perché un utente disponga dell'accesso per bloccare o sbloccare gli ID servizio e le chiavi API associate agli ID servizio, devono essere assegnati a una politica di accesso specifica. Due tipi di politiche di accesso possono concedere l'accesso appropriato: accesso a tutti gli ID servizio nell'account o accesso a un ID servizio specifico nell'account

Per assegnare l'accesso a tutti gli ID servizio nell'account, imposta una politica di accesso per i servizi di gestione dell'account con i seguenti dettagli:

* Ruolo Editor o Amministratore 
* Servizio di identità IAM

Per assegnare l'accesso a un ID servizio specifico nell'account, imposta una politica di accesso per i servizi di gestione dell'account con i seguenti dettagli:

* Ruolo Editor o Amministratore
* Servizio di identità IAM
* Specifica "serviceid" nel campo Tipo di risorsa 
* Specifica l'identificativo dell'ID servizio nel campo ID risorsa

Per ottenere l'identificativo di uno specifico ID servizio, vai a **Gestisci** > **Accesso (IAM)** e seleziona **ID servizio**. Seleziona l'ID servizio di cui vuoi visualizzare i dettagli e copia il valore dell'ID.
{: tip}

### Blocco di un ID servizio dall'IU
{: #lock_serviceid_ui}

Un ID servizio bloccato è indicato dall'icona ![Icona di bloccato](images/locked.svg "Bloccato").

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **ID servizio**.
2. Identifica la riga dell'ID servizio che vuoi bloccare e seleziona **Blocca ID servizio** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg).

Per sbloccare un ID servizio, seleziona dalla tabella l'ID servizio che vuoi sbloccare e seleziona **Sblocca ID servizio** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg). Devi avere il livello appropriato di accesso per sbloccare un ID servizio.
{: tip}


### Blocco e sblocco di un ID servizio utilizzando la CLI
{: #lock_serviceid_cli}

Per bloccare un ID servizio, utilizza il seguente comando:

```
ibmcloud iam service-id-lock (NOME|UUID) [-f, --force]
```

Opzioni comando:

<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Blocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Blocca ID servizio `sample-test` senza conferma

```
ibmcloud iam service-id-lock sample-test -f
```

Blocca ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

Per sbloccare un ID servizio, utilizza il seguente comando:

 ```
ibmcloud iam service-id-unlock (NOME|UUID) [-f, --force]
```

Opzioni comando:

<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Sblocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Unlock service ID `sample-test` without confirmation

```
ibmcloud iam service-id-unlock sample-test -f
```

Unlock service ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## Esempi di come utilizzare un ID servizio
{: #examples_serviceid}

I seguenti sono esempi di come un ID servizio viene utilizzato con i servizi {{site.data.keyword.objectstorageshort}} e Cloud SQL Query.

- {{site.data.keyword.objectstorageshort}} - [Introduzione](/docs/services/cloud-object-storage?topic=cloud-object-storage-getting-started-cli-#getting-started-cli-).
- Cloud SQL Query - [How to use the SQL Query REST API ![Icona link esterno](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.


