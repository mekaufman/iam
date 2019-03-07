---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: MFA, multifactor authentication, time-based one-time passcode, TOTP

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Abilitazione della MFA con passcode monouso per un utente
{: #totp}

Come amministratore con l'accesso corretto, puoi abilitare l'opzione per richiedere a un utente di immettere un passcode monouso basato sul tempo (TOTP) al momento dell'accesso dalla pagina Dettagli utente della console {{site.data.keyword.Bluemix}}. Questo tipo di autenticazione multifattore (MFA) è richiesto solo per l'account in cui l'impostazione è abilitata diversamente dalla MFA basata sull'ID. Per ulteriori informazioni, vedi [Tipi di autenticazione multifattore](/docs/iam?topic=iam-types#types).
{:shortdesc}

Se disponi di uno dei seguenti accessi, puoi aggiornare questa impostazione per altri utenti nel tuo account:

* Ruolo Editor o superiore nel servizio di gestione utenti
* Sei un predecessore nella gerarchia dell'infrastruttura classica per l'utente e ti è stata assegnata l'autorizzazione di gestione utenti dell'infrastruttura classica

Per attivare l'impostazione di accesso per richiedere a un utente la MFA TOTP, completa la seguente procedura.

Per attivare questa opzione MFA per un utente, l'utente deve prima [configurare TOTP](/docs/account?topic=account-MFA#MFA) dalla pagina Impostazioni di accesso del profilo.
{: note}

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona un utente dall'elenco.
3. Dalla pagina **Dettagli utente** nella sezione **Gestisci l'accesso dell'utente**, imposta l'opzione **MFA passcode monouso basato sul tempo** su attivo.

Puoi gestire autonomamente questa impostazione se l'impostazione di Accesso gestito dall'utente è abilitata nella tua pagina Dettagli utente.
{: tip}
