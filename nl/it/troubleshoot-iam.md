---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-01"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Risoluzione dei problemi relativi a IAM
{: #troubleshoot_iam}

I problemi generali con l'utilizzo di IAM potrebbero includere la necessità di accedere a una risorsa o un account per eseguire un'attività o l'identificazione del tipo corretto di accesso da assegnare agli utenti nel tuo account per eseguire attività specifiche. In molti casi, puoi risolvere questi problemi seguendo pochi semplici passi.
{:shortdesc}

## Come faccio a sapere quale tipo di accesso mi è stato assegnato?
{: #troubleshoot-myaccess}
{: troubleshoot}

Se non disponi dell'accesso per completare una particolare attività, come ad esempio la creazione di un'istanza del servizio, la sua aggiunta a un gruppo di risorse o l'invito di altri utenti nell'account, potresti dover controllare quale tipo di accesso ti è stato assegnato.

Non sono sicuro di quale livello di accesso mi è stato assegnato per completare delle azioni in un account di cui sono un membro.
{: tsSymptoms}
   
È possibile che non ti sia stato assegnato l'accesso corretto.
{: tsCauses}

Per controllare a cosa hai accesso e il livello di accesso, completa la seguente procedura. Se devi richiedere l'accesso, contatta il proprietario dell'account.

Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona il tuo nome nella pagina **Utenti**. Quindi, a seconda dell'accesso che stai cercando, seleziona le diverse schede:
{: tsResolve}

* Per determinare l'accesso di cui disponi attraverso i gruppi di accesso che ti sono stati assegnati, seleziona **Gruppi di accesso**.
* Per vedere le politiche di accesso IAM che ti sono state assegnate, seleziona **Politiche di accesso**.
* Per vedere il tuo accesso a Cloud Foundry per tutte le organizzazioni e gli spazi, seleziona **Accesso Cloud Foundry**.


## Come posso ottenere il livello di accesso per invitare degli utenti nell'account? 
{: #troubleshoot-invite}
{: troubleshoot}

Se non sei il proprietario dell'account e non ti è stato assegnato l'accesso corretto, non puoi invitare degli utenti in un account. 

Non posso invitare degli utenti nell'account.
{: tsSymptoms}
   
È possibile che non ti sia stato assegnato l'accesso corretto.
{: tsCauses}

Per invitare gli utenti e gestire gli inviti in sospeso, devi essere un proprietario dell'account, un gestore dell'organizzazione, un utente con una politica di accesso IAM con il ruolo Editor o superiore nel servizio di gestione dell'account utente o devi avere le autorizzazioni dell'infrastruttura classica per aggiungere gli utenti.
{: tsResolve}


## Come posso visualizzare le autorizzazioni dell'infrastruttura classica per altri utenti?
{: #troubleshoot-classicinfra}
{: troubleshoot}

I proprietari dell'account hanno accesso completo all'account, quindi non visualizzano le autorizzazioni per loro stessi. I singoli utenti non possono modificare le proprie autorizzazioni, per cui visualizzano le autorizzazioni sulla loro pagina dell'infrastruttura classica, ma non possono modificarle. Devi disporre dell'accesso specifico per visualizzare e modificare le autorizzazioni di un altro utente nell'account.

Vedi un messaggio che indica che non puoi visualizzare le autorizzazioni dell'infrastruttura classica di un altro utente.
{: tsSymptoms}
   
È possibile che non ti sia stato assegnato l'accesso corretto.
{: tsCauses}

Devi chiedere al proprietario dell'account che ti venga assegnata l'autorizzazione dell'infrastruttura classica **Gestisci utenti**, ma devi anche essere un predecessore dell'utente all'interno della gerarchia utenti dell'infrastruttura classica per visualizzare e gestire le autorizzazioni di un altro utente.
{: tsResolve}
