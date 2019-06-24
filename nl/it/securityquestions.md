---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: security questions, MFA, multifactor authentication, login security

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Abilitazione delle domande di sicurezza MFA per un utente
{: #questions}

Come amministratore con l'accesso corretto, puoi abilitare l'opzione per richiedere a un utente di immettere domande e risposte di sicurezza al momento dell'accesso. Questo tipo di autenticazione multifattore (MFA) è richiesto solo per l'account in cui l'impostazione è abilitata. Questo tipo di autenticazione multifattore (MFA) è richiesto solo per l'account in cui l'impostazione è abilitata diversamente dalla MFA basata sull'ID. Per ulteriori informazioni, vedi [Tipi di autenticazione multifattore](/docs/iam?topic=iam-types#types).
{:shortdesc}

Se hai uno dei seguenti tipi di accesso, puoi aggiornare questa impostazione per gli altri utenti nel tuo account:

* Ruolo Editor o superiore nel servizio di gestione utenti
* Sei un predecessore nella gerarchia dell'infrastruttura classica per l'utente e ti è stata assegnata l'autorizzazione di gestione utenti dell'infrastruttura classica


Per attivare questa opzione MFA per un utente, l'utente deve configurare le [domande di sicurezza](/docs/account?topic=account-login-settings#security-questions) e le risposte dalla pagina Impostazioni di accesso del profilo.
{: note}

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona un utente dall'elenco.
3. Dalla pagina **Dettagli utente** nella sezione **Gestisci l'accesso dell'utente**, imposta l'opzione **Richiedi domande di sicurezza MFA all'accesso** su attivo.

Puoi gestire autonomamente questa impostazione se l'impostazione di Accesso gestito dall'utente è abilitata nella tua pagina Dettagli utente.
{: tip}
