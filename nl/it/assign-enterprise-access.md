---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise policy, enterprise access, assign enterprise access, enterprise service

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Assegnazione dell'accesso aziendale 
{: #assign-access-enterprise}

Per assegnare a un utente l'accesso per gestire un'azienda {{site.data.keyword.Bluemix}}, devi invitarlo nell'account aziendale e assegnargli un accesso al servizio di gestione dell'account aziendale.
{:shortdesc}

L'accesso per gestire l'[azienda](/docs/account?topic=account-enterprise) richiede una politica di accesso all'interno dell'account aziendale. Quando assegni a un utente una politica del servizio di gestione dell'account aziendale all'interno di un account secondario in un'azienda, l'utente non può gestire l'azienda a cui appartiene l'account. A seconda del ruolo assegnato dell'utente per il servizio di gestione dell'account aziendale nell'account aziendale, l'utente può eseguire delle specifiche azioni:

* Creare nuovi account nell'azienda
* Creare e fornire il nome ai gruppi di account
* Spostare gli account tra i gruppi di account
* Importare gli account esistenti nell'azienda
* Aggiornare il nome e il dominio dell'azienda
* Visualizzare i report di utilizzo per l'azienda, uno specifico gruppo di account e i gruppi di account o gli account al suo interno, o un account specifico.

Una politica che fornisce a un utente l'accesso al servizio aziendale può essere assegnata sull'intera azienda oppure solo su un gruppo di account specifico o su un singolo account.
{: tip}

Normalmente, l'account aziendale stesso non contiene molte risorse. Invece, le risorse vengono create negli account secondari dell'azienda. È all'interno di ognuno di questi account che gli utenti possono essere invitati e gli viene fornito l'accesso per gestire ed utilizzare le risorse. L'accesso e l'appartenenza a disposizione di un utente nell'account aziendale non si applicano ai gruppi di account o agli account secondari nella gerarchia aziendale. La gestione dell'utente e la gestione dell'accesso rimangono isolate per ogni account come puoi vedere nei seguenti diagrammi.

Il primo diagramma mostra come puoi assegnare una politica a un utente nell'account aziendale per gestire l'intera azienda oppure una politica destinata a un gruppo di account, che fornisce l'accesso per gestire solo tale gruppo di account e gli altri gruppi di account o account secondari che sono organizzati al suo interno.

![Accesso aziendale](images/enterprise-access.svg "Diagramma che mostra che gli utenti aziendali hanno accesso per gestire solo le entità aziendali")

La destinazione e il ruolo della politica sono importanti nel determinare l'ambito dell'accesso. Un utente, un ID servizio o un gruppo di accesso in un'azienda, che è l'oggetto della politica, può completare le attività di gestione aziendale nell'intera azienda, in un gruppo di account che può contenere altri gruppi di account e account o anche in un solo account. Ad esempio, se assegni a un utente nell'account aziendale una politica di accesso sul servizio di gestione dell'account aziendale con una destinazione pensata per uno specifico gruppo di account, dispone dell'accesso per completare le attività all'interno del gruppo di account. L'utente non completare le azioni che riguardano l'intera azienda, come l'aggiornamento del nome o del dominio aziendali, quando la destinazione è impostata su uno specifico gruppo di account o account.

Puoi assegnare gli utenti in un account secondario nelle politiche di accesso aziendali che si applicano alla gestione soltanto di tale account o delle risorse che contiene. Se ad esempio assegni a un utente in un account secondario un ruolo sul servizio di gestione dell'account aziendale, l'utente non può eseguire azioni al livello dell'account aziendale. Devi aggiungerlo all'account aziendale e assegnargli la politica in tale contesto.

![Accesso account](images/account-access.svg "Diagramma che mostra che gli utenti dell'account secondario dispongono dell'accesso all'interno dei propri account soltanto e non al resto dell'azienda")

## Politiche necessarie per lavori specifici
{: #sample-enterprise-policies}

A seconda del lavoro che deve essere fatto, potrebbe essere necessaria una combinazione di politiche per un utente che non è il proprietario dell'azienda. I seguenti esempi forniscono la serie di politiche di accesso che devi assegnare a un utente nell'azienda in modo che possa completare delle particolari azioni.

Se sei il proprietario di un account che non fa parte di un'azienda, ma vuoi che un altro utente nel tuo account possa convertire il tuo account in un'azienda, puoi assegnare a tale utente il ruolo di amministratore sul servizio di gestione dell'account di fatturazione.
{: note}

### Visualizzazione dell'utilizzo e gestione della fatturazione nell'azienda
{: #billing-admin-enterprise}

Per consentire a un utente di [visualizzare i report di utilizzo](/docs/billing-usage?topic=billing-usage-enterprise-usage) per tutti gli account nell'azienda, di effettuare i pagamenti e di visualizzare le fatture, devi assegnare tutte le seguenti politiche di accesso:

* Il ruolo di visualizzatore dei report di utilizzo per il servizio di gestione dell'account aziendale nell'account aziendale
* Il ruolo di amministratore per il servizio di gestione dell'account aziendale nell'account aziendale

### Importazione di un account esistente nell'azienda
{: #add-account}

Per consentire a un utente di [importare un account IBM Cloud esistente nell'azienda](/docs/account?topic=account-enterprise-add#add-accounts), devi assegnare tutte le seguenti politiche di accesso:

* Il ruolo di amministratore sul servizio di gestione dell'account di fatturazione nell'account che deve essere importato
* Il ruolo di amministratore o editor sul servizio di gestione dell'account aziendale per il gruppo di account o l'account aziendale a cui sarà aggiunto l'account
* Il ruolo di amministratore sul servizio di gestione dell'account aziendale per l'account aziendale

### Spostamento di un account
{: #move-accountgroup}

Per consentire a un utente di [spostare un account all'interno di un'azienda](/docs/account?topic=account-enterprise-organize#move-accounts), devi assegnare tutte le seguenti politiche di accesso:

* Il ruolo di amministratore per il servizio di gestione dell'account aziendale nell'account aziendale

Successivamente, una delle seguenti due opzioni:

* Ruolo di amministratore o editor per il servizio di gestione dell'account aziendale per l'intera azienda.
* Ruolo di amministratore o editor sul gruppo di account corrente e di destinazione a cui sarà spostato questo account

Per i dettagli su quali azioni possono essere effettuate per ogni ruolo, vedi [Azioni e ruoli per i servizi di gestione dell'account](/docs/iam?topic=iam-account-services#account-management-actions-roles).

## Assegnazione dell'accesso nella console
{: #enterprise-access-console}

Per assegnare una politica di accesso a un utente esistente nell'account aziendale, completa la seguente procedura:

Puoi impostare la destinazione della politica in modo che sia l'intera azienda, uno specifico gruppo di account, che può includere l'accesso a tutti gli account al suo interno o anche a uno specifico account in un gruppo di account.
{: tip}

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Dalla riga per l'utente a cui desideri assegnare l'accesso, seleziona il menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg) e fai clic su **Assegna accesso**.
3. Seleziona per assegnare l'accesso a **Servizi di gestione account**.
4. Seleziona **Azienda** per il servizio.
5. Facoltativo: destina la politica all'azienda, al gruppo di account o all'account.
6. Seleziona qualsiasi combinazione di ruoli per assegnare l'accesso desiderato.

| Ruoli | Azioni |
|:-------|----------|
| Visualizzatore |  Visualizzare l'azienda, i gruppi di account e gli account    |
| Operatore |  Visualizzare l'azienda, i gruppi di account e gli account    |
| Editor |  Visualizzare e aggiornare l'azienda modificando il nome e il dominio, creare gli account e i gruppi di account, visualizzare i report di utilizzo e importare gli account |
| Amministratore |  Visualizzare e aggiornare l'azienda modificando il nome e il dominio, creare gli account e i gruppi di account, spostare gli account tra i gruppi di account, importare account esistenti e visualizzare i report di utilizzo   |
| Visualizzatore del report di utilizzo | Visualizzare l'azienda, gli account e i gruppi di account e visualizzare i report di utilizzo di tutti gli account nell'azienda |
{: caption="Tabella 1. Ruoli ed azioni di esempio per il servizio di gestione dell'account aziendale" caption-side="top"}

## Assegnazione dell'accesso utilizzando la CLI
{: #enterprise-cli-policy}

Per creare una nuova politica di accesso per un utente, esegui il comando **`ibmcloud iam user-policy-create`**. Nell'esempio di comando, viene utilizzato un file JSON per specificare i dettagli della politica. Controlla l'esempio nella sezione [Assegnazione dell'accesso utilizzando l'API](#enterprise-api-policy) per un esempio di cosa è incluso nel file JSON.

Crea una politica utente:
```
$ ibmcloud iam user-policy-create name@example.com -f policy.json
```

Per ulteriori informazioni, vedi [ibmcloud iam user-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_create).

## Assegnazione dell'accesso utilizzando l'API
{: #enterprise-api-policy}

Il seguente esempio di richiesta assegna una politica per un utente con il ruolo di editor sul servizio aziendale in un account aziendale destinato a un gruppo di account. Questo tipo di politica è gerarchica e si applica a tutti gli oggetti discendenti nella gerarchia, il che significa tutti i gruppi di account o gli account all'interno del gruppo di account di destinazione specificato.  

```
curl -X POST \
'https://iam.cloud.ibm.com/v1/policies' \
-H 'Authorization: $TOKEN' \
-H 'Content-Type: application/json' \
-d '{
  "type": "access",
  "subjects": [
    {
      "attributes": [
        {
          "name": "iam_id",
          "value": "<IBMid-example>"
        }
      ]
    }
  ],
  "roles":[
    {
      "role_id": "crn:v1:bluemix:public:iam::::role:Editor"
    }
  ],
  "resources":[
    {
      "attributes": [
        {
          "name": "accountId",
          "value": "<account-id-example>"
        },
        {
          "name": "serviceName",
          "value": "enterprise"
        },
        {
          "name": "accountGroupId",
          "value": "<accountGroupId-example>"
        }
      ]
    }
  ]
}'
```
{: codeblock}

Per ulteriori informazioni, vedi [Crea una politica](https://cloud.ibm.com/apidocs/iam-policy-management#create-a-policy){: external}.
