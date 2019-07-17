---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: MFA, multifactor authentication, external authentication, order authentication, Symantec, phone-based authentication, cancel authentication order

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Ordinazione dell'autenticazione esterna MFA per un utente
{: #external}

Come amministratore con l'accesso corretto, puoi ordinare l'autenticazione esterna e abilitare l'opzione MFA (multifactor authentication) per l'accesso di un utente. Per le opzioni di autenticazione esterne ti viene addebitata una tariffa mensile. Questo tipo di autenticazione multifattore (MFA) è richiesto solo per l'account in cui l'impostazione è abilitata diversamente dalla MFA basata sull'ID. Per ulteriori informazioni, vedi [Tipi di autenticazione multifattore](/docs/iam?topic=iam-types#types).
{:shortdesc}

## Ordinazione dell'autenticazione esterna
{: #ordering}

Se disponi di uno dei seguenti accessi, puoi ordinare l'autenticazione esterna per un utente:

* Ruolo Editor o superiore nel servizio di gestione utenti
* Sei un predecessore nella gerarchia dell'infrastruttura classica per l'utente e ti è stata assegnata l'autorizzazione di gestione utenti dell'infrastruttura classica

Per ordinare l'autenticazione esterna, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona un utente dall'elenco.
3. Dalla pagina **Dettagli utente**, seleziona **Ordina autenticazione esterna** nella sezione Gestisci l'accesso dell'utente.
4. Seleziona **Protezione identità Symantec** o **Protezione identità basata sul telefono**.
    * Per l'autenticazione Symantec, l'utente deve scaricare l'applicazione [Symantec VIP](https://vip.symantec.com/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg) e ottenere un ID credenziale per continuare con il processo di ordinazione.
    * Per l'autenticazione basata sul telefono, puoi procedere con l'ordine, ma il tuo utente deve [impostare la propria configurazione](/docs/account?topic=account-login-settings#setting-up-phone-based-authentication) prima che tu possa abilitare l'opzione.
5. In base alla tua selezione, segui le istruzioni per rivedere il prezzo e i termini prima di effettuare l'ordine.
6. Fai clic su **Ordina** per finalizzare la tua selezione.

Dopo aver ordinato l'autenticazione Symantec, puoi attivare l'opzione per l'utente dalla pagina Dettagli utente. Allo stesso modo, dopo che l'autenticazione basata sul telefono è stata ordinata e quindi configurata dall'utente, puoi attivare l'opzione per l'utente dalla pagina Dettagli utente.

## Disabilitazione delle opzioni di autenticazione esterne
{: #disable}

Puoi disabilitare la MFA Symantec o basata sul telefono per un utente in qualsiasi momento.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona un utente dall'elenco.
3. Dalla pagina **Dettagli utente**, imposta l'opzione **Autenticazione Symantec** o quella **Autenticazione basata sul telefono** su Disattivo.

## Annullamento delle opzioni di autenticazione esterne
{: #cancel}

Se disponi dell'accesso corretto, puoi annullare l'ordine per l'autenticazione esterna in qualsiasi momento. Puoi scegliere di annullarlo immediatamente senza alcun rimborso oppure scegliere di annullarlo entro un periodo di un anno da quando hai effettuato l'ordine.

Per annullare un ordine per l'autenticazione esterna, devi essere un proprietario dell'account o disporre di tutti i seguenti accessi:

* Autorizzazione di gestione utenti dell'infrastruttura classica
* Autorizzazione di annullamento servizi dell'infrastruttura classica
* Amministratore per il servizio di gestione account Centro di supporto o autorizzazioni dell'infrastruttura classica migrate per la visualizzazione, modifica e aggiunta di ticket che non sono disponibili nei [gruppi di accesso delle autorizzazioni migrate](/docs/iam?topic=iam-migrated_permissions).

Per annullare l'ordine dell'autenticazione esterna, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona Utenti.
2. Seleziona un utente dall'elenco.
3. Dalla pagina **Dettagli utente**, fai clic su **Elimina** ![Icona Elimina](../icons/icon_trash.svg) per la riga **Autenticazione Symantec** o **Autenticazione basata sul telefono**, a seconda di quale hai ordinato.
4. Seleziona quando rimuoverla.
5. Fai clic su **Rimuovi**.
