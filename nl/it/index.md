---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} Identity and Access Management
{: #iamoverview}

## Cos'è Cloud IAM?
{: #what_is_IAM}

{{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) ti consente di autenticare in modo sicuro gli utenti per i servizi di piattaforma e di controllare l'accesso alle risorse in modo coerente su {{site.data.keyword.Bluemix_notm}}. Un insieme di servizi {{site.data.keyword.Bluemix_notm}} è abilitato per utilizzare Cloud IAM per il controllo dell'accesso e questi servizi sono organizzati in [gruppi di risorse](/docs/resources?topic=resources-rgs#rgs) all'interno del tuo account per consentire agli utenti un accesso rapido e semplice a più di una risorsa alla volta. Le politiche di accesso Cloud IAM vengono utilizzate per assegnare agli utenti e agli ID servizio l'accesso alle risorse all'interno del tuo account. Puoi raggruppare utenti e ID servizio in un [gruppo di accesso](/docs/iam?topic=iam-getstarted#getstarted) per fornire facilmente a tutte le entità nel gruppo lo stesso livello di accesso.

Una politica assegna a un oggetto, che è un utente, un [ID servizio](/docs/iam?topic=iam-serviceids#serviceids) o un gruppo di accesso, uno o più ruoli con una combinazione di attributi che definiscono l'ambito di accesso a una destinazione. La politica può fornire l'accesso a un singolo servizio fino al livello di istanza, a una serie di risorse organizzate tra loro in un gruppo di risorse o ai servizi di gestione dell'account. A seconda dei [ruoli IAM](/docs/iam?topic=iam-iamusermanrol#iamusermanrol) che assegni, all'oggetto sono consentiti diversi livelli di accesso per completare le attività di gestione dell'account, utilizzando le istanze del servizio o accedendo a un servizio utilizzando l'IU o completando le chiamate API.


![IAM per il controllo dell'accesso in un account](images/iam-diagram.svg "Come funziona la gestione dell'accesso in un account utilizzando IAM")

Per i servizi che non supportano la creazione di politiche Cloud IAM per la gestione dell'accesso, puoi utilizzare [Accesso Cloud Foundry](/docs/iam?topic=iam-cfaccess#cfaccess) o [Autorizzazioni dell'infrastruttura classica](/docs/iam?topic=iam-infrapermission#infrapermission).


## Quali funzioni sono fornite da Cloud IAM?
{: #features}

<dl>
<dt>Gestione utenti</dt>
<dd>La gestione utenti unificata ti consente di aggiungere ed eliminare gli utenti in un account per i servizi di piattaforma e di infrastruttura classica. Puoi organizzare un gruppo di utenti in un gruppo di accesso per rendere l'assegnazione dell'accesso per più di un utente alla volta un'attività facile e veloce.</dd>
<dt>Controllo dell'accesso dettagliato</dt>
<dd>L'accesso per gli utenti, gli ID servizio e i gruppi di accesso è definito da una politica. All'interno della politica, l'ambito di accesso di un utente, un ID del servizio o di un gruppo di accesso può essere assegnato a un insieme di risorse in un gruppo di risorse, a una singola risorsa o ai servizi di gestione dell'account. Dopo aver impostato l'ambito, puoi definire quali azioni sono consentite dall'oggetto della politica selezionando i ruoli di accesso. I ruoli forniscono un modo per personalizzare il livello di accesso concesso all'oggetto della politica per eseguire azioni sulla destinazione della politica, sia che si tratti di attività di gestione della piattaforma all'interno dell'account o dell'accesso all'IU di un servizio o del completamento delle chiamate API.</dd>
<dt>Chiavi API per l'autenticazione dell'utente</dt>
<dd>È possibile creare più chiavi API per un utente per supportare gli scenari di rotazione della chiave e la stessa chiave può essere utilizzata per accedere a più servizi. Le chiavi API {{site.data.keyword.cloud_notm}} consentono agli utenti che utilizzano l'autenticazione a due fattori o un ID federato di automatizzare l'autenticazione nella console dalla riga di comando. Un utente può anche avere una singola chiave API dell'infrastruttura classica che può essere utilizzata per accedere alle API dell'infrastruttura classica; tuttavia, questa non è necessaria perché puoi utilizzare le chiavi API {{site.data.keyword.cloud_notm}} per accedere alle stesse API.</dd>
<dt>ID servizio</dt>
<dd>Un ID servizio identifica un servizio o un'applicazione analogamente a come un ID utente identifica un utente. Questi sono ID che possono essere utilizzati dalle applicazioni per l'autenticazione con un servizio {{site.data.keyword.Bluemix_notm}}. È possibile assegnare le politiche a ciascun ID servizio per controllare il livello di accesso consentito da un'applicazione che utilizza l'ID servizio ed è possibile creare una chiave API per abilitare l'autenticazione.</dd>
</dl>


## Come posso utilizzare Cloud IAM?
{: #howto}

Puoi accedere e utilizzare Cloud IAM attraverso l'interfaccia utente, la CLI o l'API di Accesso (IAM). 

* Per accedere a Cloud IAM utilizzando l'interfaccia utente, vai a **Gestisci** &gt; **Accesso (IAM)**. 
* Vai a [Gestione dell'accesso IAM, delle chiavi API, degli ID servizio e dei gruppi di accesso](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_commands_iam) per esaminare i comandi della CLI disponibili.
* Vai ai seguenti documenti API per esaminare le API disponibili: 
    * [IAM Identity Services API](https://{DomainName}/apidocs/iam-identity-token-api){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")
    * [IAM Access Groups API](https://{DomainName}/apidocs/iam-access-groups){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")
    * [IAM Policy Management API](https://{DomainName}/apidocs/iam-policy-management){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")
