---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Richiesta di MFA per gli utenti nel tuo account
{: #enablemfa}

In qualità di proprietario dell'account {{site.data.keyword.Bluemix}}, puoi scegliere di richiedere l'autenticazione multifattore (MFA) per ogni utente nel tuo account. Tutti gli utenti con un ID IBM utilizzano un metodo MFA con passcode monouso basato sul tempo (TOTP) e gli utenti con un diverso tipo di ID devono essere abilitati ad utilizzare il TOTP, le domande di sicurezza o il metodo di autenticazione esterno separato.  
{:shortdesc}

## Prima di iniziare
{: #considerations}

Esamina le seguenti considerazioni prima di abilitare la MFA dell'ID IBM per il tuo account per assicurarti di sapere come influisce su tutti gli utenti nel tuo account:

* Quando abiliti la MFA per il tuo account, tutti gli utenti aggiunti al tuo account devono completare il processo MFA al successivo accesso.
* Le chiavi API per gli utenti e gli ID servizio continuano a funzionare dopo l'abilitazione di MFA.
* Se devi utilizzare l'accesso IU o CLI CF nativa in Cloud Foundry, devi utilizzare le chiavi API oppure SSO (single sign-on) dopo l'abilitazione della MFA per l'account.
* La MFA per il tuo account si applica all'accesso di un utente, ma non si applica alle chiamate API. Se un utente dispone dell'autorizzazione per effettuare chiamate API alle risorse nel tuo account, l'utente può farlo senza completare la MFA. Se l'utente appartiene ad altri account, l'utente può effettuare chiamate API alle risorse nel tuo account utilizzando una chiave API da un account che non ha richiesto la MFA.
* Se sei un utente federato, la MFA non è supportata. 
* Se richiedi la MFA per il tuo account e nel tuo account ci sono utenti che non hanno un ID IBM, devi abilitare una delle altre opzioni MFA per tali utenti dalla pagina Dettagli utente nella console {{site.data.keyword.Bluemix_notm}}. Per ulteriori informazioni, vedi [Tipi di autenticazione multifattore](/docs/iam?topic=iam-types#types).
* Pianifica una strategia di comunicazione e supporto per gli utenti nel tuo account:
  * Scegli una data e ora in cui intendi abilitare la MFA che produca il minimo impatto sulla tua attività aziendale.
  * Dopo che hai abilitato la MFA, notifica agli utenti del tuo account le informazioni su come [procedere alla configurazione](/docs/iam?topic=iam-enablemfa#setupapp).

Quando l'impostazione dell'account di autenticazione multifattore è abilitata, a tutti gli utenti ID IBM nel tuo account viene richiesta l'autenticazione MFA dell'ID IBM all'accesso. Se hai configurato altri metodi MFA per qualsiasi utente ID IBM nel tuo account, all'utente non vengono più richiesti questi metodi MFA.
{: tip}

## Abilitazione della MFA per tutti gli utenti nel tuo account
{: #enabling}

Per abilitare la MFA, devi essere il proprietario dell'account. L'abilitazione della MFA non influisce sugli utenti che hanno già effettuato l'accesso, poiché l'applicazione della MFA sull'account ha effetto solo sui nuovi accessi. Assicurati di notificare agli utenti del tuo account che la MFA è abilitata e descrivi l'impatto sugli utenti al loro prossimo accesso. 

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona quindi **Impostazioni**.
2. Seleziona **Autenticazione multifattore**.
3. Nella finestra di conferma, fai clic su **Sì, sono sicuro**.

## Configurazione del tuo TOTP
{: #setupapp}

Dopo aver abilitato la MFA per il tuo account, devi configurare il passcode monouso con un'applicazione autenticatore al prossimo accesso. Anche tutti gli utenti nel tuo account devono configurare il passcode monouso al loro prossimo accesso. 

Completa la seguente procedura per configurare il tuo passcode monouso con l'applicazione autenticatore per la prima volta.

1. Accedi con i tuoi ID IBM e password. 

  Potrebbero essere necessari fino a 5 minuti per poter accedere nuovamente con la MFA.
  {: note}

2. Seleziona **Verify** nella schermata **Verification is required** per configurare la MFA con un'applicazione autenticatore.
3. Seleziona **Setup your authenticator app** per ottenere un codice monouso inviato alla tua email per continuare la configurazione dell'applicazione autenticatore.
4. Seleziona **Verify**.
5. Esegui la scansione del codice a barre con la tua applicazione oppure fai clic su **Can't scan the bar code?** per immettere una chiave fornita. 
6. Fai clic su **Continue** per immettere il tuo codice.
7. Immetti il tuo codice e seleziona **Verify**. 

Se rilevi un messaggio di errore che indica che hai già configurato l'autenticazione, ma il tuo codice di verifica non funziona o non hai il codice di verifica da immettere, devi contattare l'[Help desk](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno") per reimpostare la tua registrazione della MFA.
{: note}
{: #mfahelp}

## Disabilitazione della MFA richiesta per tutti gli utenti nel tuo account
{: #disablemfa}

Per disabilitare la MFA, devi essere il proprietario dell'account. La disabilitazione della MFA non influisce sugli utenti che hanno già effettuato l'accesso e l'azione ha effetto su tutti i nuovi accessi.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona quindi **Impostazioni**.
2. Seleziona **Standard**.
3. Nella finestra di conferma, fai clic su **Sì, sono sicuro**.
