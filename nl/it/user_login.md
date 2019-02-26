---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:important: .important}

# Gestione delle impostazioni di accesso di un utente 
{: #loginsettings}

Un proprietario dell'account o un utente che ha l'accesso corretto può gestire le impostazioni di accesso di un utente, ad esempio, ordinare opzioni di autenticazione esterne, abilitare un passcode monouso da utilizzare durante l'accesso, abilitare l'uso di domande di sicurezza all'accesso e impostare un tempo di scadenza della password.
{:shortdesc}

Completa la seguente procedura per gestire le impostazioni di accesso per uno specifico utente:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**. 
2. Seleziona un utente dall'elenco e fai clic su **Dettagli utente**. 
3. Dalla sezione **Gestisci l'accesso dell'utente**, puoi attivare o disattivare le seguenti opzioni per l'utente selezionato: 
    
    * MFA passcode monouso basato sul tempo: attiva questa opzione per fare in modo che all'utente venga richiesto il passcode monouso all'accesso. L'utente deve configurare la propria MFA TOTP dalla pagina Impostazioni di accesso. Per ulteriori informazioni, vedi [Abilitazione della MFA con passcode monouso per un utente](/docs/iam?topic=iam-totp#totp).
    
    * Ordina autenticazione esterna: seleziona questa opzione per acquistare l'autenticazione Symantec o basata sul telefono a una tariffa mensile. È possibile ordinare e utilizzare una sola opzione alla volta. Per ulteriori informazioni, vedi [Ordinazione dell'autenticazione esterna MFA per un utente](/docs/iam?topic=iam-external#external).

        * Autenticazione basata sul telefono: l'utente può utilizzare questa opzione utilizzando la configurazione che ha impostato dalla pagina Dettagli utente dopo che il proprietario dell'account la ha ordinata. 
        * Autenticazione Symantec: l'utente può utilizzare l'opzione dopo che il proprietario dell'account la ha ordinata. Affinché un amministratore ordini questa opzione, l'utente deve prima fornire l'ID credenziale.

    * Domande di sicurezza MFA all'accesso: attiva questa opzione per richiedere a un utente di immettere le domande e le risposte di sicurezza che ha impostato dalla pagina Impostazioni di accesso. Puoi attivare questa opzione solo se l'utente ha già impostato le proprie domande di sicurezza. Per ulteriori informazioni, vedi [Abilitazione delle domande di sicurezza MFA per un utente](/docs/iam?topic=iam-questions#questions).

    * Accesso gestito dall'utente: attiva questa opzione per consentire all'utente di impostare la scadenza della password, di attivare le domande di sicurezza per l'accesso e di specificare gli indirizzi IP consentiti per l'accesso a {{site.data.keyword.cloud_notm}} e per le API dell'infrastruttura classica. 

    * Scadenza password: imposta una scadenza selezionando un'opzione dall'elenco. Questa opzione è disponibile solo per gli utenti con ID SoftLayer. Se l'utente può gestire le proprie impostazioni di accesso, può impostare questa scadenza dalla pagina Impostazioni di accesso. Solo gli utenti con le seguenti autorizzazioni possono impostare una scadenza password per un utente:
        
        * Qualsiasi utente a cui è assegnata una politica IAM con il ruolo Editor o superiore nel servizio di gestione utenti.
        * Qualsiasi utente per cui l'amministratore ha abilitato l'accesso gestito dall'utente nella pagina Dettagli utente.
        * Qualsiasi predecessore nella gerarchia dell'infrastruttura classica per l'utente a cui è stata assegnata l'autorizzazione di gestione utenti dell'infrastruttura classica.

È necessario abilitare solo un'opzione MFA alla volta. Se la MFA dell'ID IBM è richiesta per qualsiasi account di cui l'utente è membro, sovrascrive eventuali altre MFA abilitate e all'utente non vengono richiesti altri tipi di MFA.
{: important}



