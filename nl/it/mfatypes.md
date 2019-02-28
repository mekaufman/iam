---

copyright:

  years: 2018,2019
lastupdated: "2019-01-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Tipi di autenticazione multifattore
{: #types}

L'autenticazione multifattore (MFA, multifactor authentication) aggiunge un ulteriore livello di sicurezza al tuo account richiedendo a tutti gli utenti di autenticarsi utilizzando un metodo di autenticazione aggiuntivo oltre a ID e password. Questa è anche comunemente nota come autenticazione a due fattori (2FA, two-factor authentication).
{:shortdesc}

Per il tuo account potrebbero essere abilitati i seguenti due tipi di opzioni MFA:

<dl>
<dt>MFA basata sull'ID</dt>
<dd>Un'opzione abilitata da un proprietario di account in uno degli account di cui sei membro. Questo tipo di MFA è associato al tuo ID IBM e ti autentica in tutti gli account di cui sei membro, quindi devi autenticarti solo una volta.</dd>
<dt>Opzioni basate sull'account</dt>
<dd>Opzioni come le domande di sicurezza, l'utilizzo di un passcode monouso basato sul tempo e le opzioni di autenticazione esterne come l'autenticazione Symantec e basata sul telefono. Questi tipi di MFA sono specifici per ciascun account, il che significa che se hai configurato un tipo diverso per ogni account a cui appartieni, devi autenticarti in un modo diverso ogni volta che cambi account. Queste opzioni MFA legacy sono disponibili solo con i precedenti account dell'infrastruttura classica.</dd>
</dl>

La MFA dell'ID IBM soddisfa i requisiti di autenticazione, pertanto non ti vengono richiesti altri tipi di MFA anche se sono abilitati. Quindi, se un proprietario di un account di cui sei membro attiva questa opzione, questo è l'unico tipo di MFA che ti viene richiesto al momento dell'accesso. Se sei un nuovo utente, usa l'opzione MFA dell'ID IBM basata sull'ID per assicurarti che il tuo accesso sia facile e sicuro.
{: tip}

## Opzione MFA basata sull'ID
{: #id-based}

La MFA dell'ID IBM per un account richiede un passcode monouso basato sul tempo oltre a un ID IBM e password standard durante l'accesso. Questo tipo di MFA viene abilitato a livello di account dal proprietario dell'account. Quando questa funzione è abilitata, a te e a tutti gli utenti aggiunti al tuo account viene richiesto di utilizzare lo standard di sicurezza aggiuntivo durante l'accesso. Questo tipo di MFA si applica a tutte le risorse dell'account. Puoi attivare o disattivare questa opzione dalla pagina **Gestisci** > **Accesso (IAM)** > **Impostazioni** nella console {{site.data.keyword.Bluemix}} solo se sei il proprietario dell'account.

Uno dei vantaggi della MFA dell'ID IBM è che è gratuita e legata al tuo ID invece del solo account specifico in cui ti trovi. Se appartieni a molti account, devi autenticarti solo una volta quando accedi alla console. Per ulteriori informazioni sulla MFA dell'ID IBM, le considerazioni che devono essere esaminate prima di richiedere MFA dell'ID IBM per il tuo account e come configurare MFA dell'ID IBM per conto proprio, vedi [Richiesta di MFA per gli utenti nel tuo account](/docs/iam/mfa.html#setting-up-ibmid-mfa).

## Opzioni MFA basata sull'account
{: #account-based}

Un amministratore account deve abilitare una delle seguenti opzioni MFA per essere configurate e utilizzate da un utente nell'account. Questo tipo di MFA è legato all'account corrente di un utente. Se un amministratore abilita un'opzione MFA diversa per ciascun account di cui è membro un utente, all'utente viene richiesto di autenticarsi in modo diverso ogni volta che cambia account. 

Se il proprietario dell'account richiede la MFA dell'ID IBM per tutti gli utenti nell'account, il metodo MFA dell'ID IBM sovrascrive qualsiasi altra opzione MFA abilitata e configurata nell'account di un utente. Pertanto, anche se un utente ha altre opzioni MFA, come ad esempio la seguente configurazione, non vengono richieste all'utente durante l'accesso.

Le seguenti opzioni MFA legacy sono disponibili solo con i precedenti account dell'infrastruttura classica.

<dl>
<dt>Autenticazione passcode monouso basato sul tempo (TOTP)</dt>
<dd>TOTP può essere configurato utilizzando un'applicazione di autenticazione. Un proprietario o amministratore dell'account può abilitare questa impostazione per un utente nella pagina Dettagli utente solo se l'utente ha configurato l'autenticazione nella pagina Impostazioni di accesso del profilo. Se questa impostazione è abilitata per un utente, a tale utente viene richiesto il passcode durante l'accesso. Gli utenti con accesso per gestire le proprie impostazioni di accesso, in quanto hanno l'impostazione di Accesso gestito dall'utente abilitata dalla loro pagina Dettagli utente, possono attivare e disattivare questa opzione.</dd>
<dt>Domande di sicurezza</dt>
<dd>Gli utenti possono configurare le risposte alle domande di sicurezza disponibili nella pagina Impostazioni di accesso del profilo. L'utente deve configurare le domande e le risposte di sicurezza prima che un proprietario o amministratore dell'account possa abilitare questa impostazione nella pagina Dettagli utente. Gli utenti con accesso per gestire le proprie impostazioni di accesso, in quanto hanno l'impostazione di Accesso gestito dall'utente abilitata dalla loro pagina Dettagli utente, possono attivare e disattivare questa opzione. </dd>
<dt>Autenticazione esterna</dt>
<dd>Esistono due opzioni di autenticazione esterne di terze parti che possono essere ordinate a un costo mensile: autenticazione Symantec e basata sul telefono. Un proprietario o amministratore dell'account deve ordinare queste opzioni per un utente e abilitarne l'utilizzo dalla pagina Dettagli utente per l'utente. Per Symantec, l'amministratore deve collaborare con l'utente per ottenere l'ID credenziale dell'utente per completare l'ordine. Per configurare l'autenticazione basata sul telefono, l'amministratore deve ordinarla e quindi l'utente deve configurarla nella pagina Dettagli utente affinché l'amministratore possa abilitarla per l'uso. Gli utenti con accesso per gestire le proprie impostazioni di accesso, in quanto hanno l'impostazione di Accesso gestito dall'utente abilitata dalla loro pagina Dettagli utente, possono attivare e disattivare questa opzione.</dd>
</dl>

Per ulteriori informazioni sulla configurazione delle opzioni MFA, vedi [Impostazione della protezione dell'accesso](/docs/account/login_settings.html#login-settings). E, se sei proprietario o amministratore di un account che gestisce le impostazioni di accesso di altri utenti o hai la possibilità di gestire le tue proprie impostazioni di accesso, vedi [Gestione delle impostazioni di accesso di un utente](/docs/iam/user_login.html#loginsettings).

