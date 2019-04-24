---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: parent user, change parent user, classic infrastructure hierarchy

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Aggiornamento dell'utente principale di un utente
{: #update-parent}

Se disponi dell'accesso corretto, puoi aggiornare l'utente principale per un utente. L'aggiornamento dell'utente principale influisce sul modo in cui un utente vede gli altri utenti nell'account quando l'impostazione di visibilità dell'elenco utenti è impostata su limitato. Gli utenti vedono solo gli altri utenti per i quali sono un utente principale e tutti gli altri utenti invitati da quei discendenti dell'utente principale.
{:shortdesc}

Per ulteriori dettagli sull'impostazione, vedi [Impostazione di visibilità dell'elenco utenti](/docs/iam?topic=iam-userlistview#userlistview).

Se disponi del seguente accesso, puoi aggiornare l'utente principale per un altro utente:

* Una politica IAM con ruolo Editor o superiore nel servizio di gestione utenti.
* Sei un predecessore nella gerarchia dell'infrastruttura classica per l'utente e ti è stata assegnata l'autorizzazione di gestione di utenti dell'infrastruttura classica


Per aggiornare l'utente principale di un utente, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.  
2. Seleziona un nome utente dall'elenco.
3. Dalla pagina Dettagli utente, seleziona un nuovo utente principale dal menu **Elemento principale**.
4. Fai clic su **Applica**.
