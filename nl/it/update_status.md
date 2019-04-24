---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-28"

keywords: user state, user status, change user status, update user status

subcollection: iam

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}

# Aggiornamento dello stato di un utente
{: #status}

Lo stato assegnato di un utente dipende da se l'utente ha accettato l'invito a unirsi all'account, se è un utente solo VPN o se l'amministratore utente imposta l'utente come utente dell'infrastruttura classica disabilitata.
{:shortdesc}

Se disponi del seguente accesso, puoi aggiornare lo stato di un altro utente:

  * Una politica IAM con ruolo Editor o superiore nel servizio di gestione utenti.
  * Sei un predecessore nella gerarchia dell'infrastruttura classica per l'utente e ti è stata assegnata l'autorizzazione di gestione utenti dell'infrastruttura classica

Per ulteriori informazioni sui tipi di stato utente, vedi [Stati utente](/docs/iam?topic=iam-user_status#user_status).

## Opzioni per modificare lo stato di un utente
{: #status_options}

Per aggiornare lo stato di un utente, puoi scegliere tra le seguenti opzioni:

<dl>
<dt>Attivo</dt>
<dd>L'utente ha accesso completo alla console {{site.data.keyword.cloud_notm}} in base alle politiche di accesso e alle autorizzazioni dell'infrastruttura classica assegnate.</dd>
<dt>Infrastruttura classica disabilitata</dt>
<dd>L'utente non può accedere più alle risorse dell'infrastruttura classica, ma può continuare ad accedere alla console e alle risorse della piattaforma.</dd>
<dt>Solo VPN</dt>
<dd>L'utente non può accedere alla console, ma ha accesso a qualsiasi dispositivo e sottorete VPN che assegni per l'infrastruttura classica accedendo direttamente all'applicazione.</dd>
</dl>

Quando aggiorni un utente dallo stato Solo VPN allo stato Attivo, l'utente deve conoscere la password per accedere alla console. Nella maggior parte dei casi, questa è la password dell'ID SoftLayer, che potresti dover reimpostare per poterla utilizzare. In rari casi in cui l'utente abbia già un ID IBM, deve accedere con ID IBM e password.
{: note}

## Aggiornamento dello stato di un utente
{: #update_user_status}

Per modificare lo stato di un utente, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona un utente dall'elenco.
3. Dalla pagina Dettagli utente, seleziona un'opzione dal menu **Stato utente**.  
4. Fai clic su **Applica**.
