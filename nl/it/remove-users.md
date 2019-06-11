---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

keywords: remove user, delete user, user management

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Rimozione di utenti
{: #remove}

Quando rimuovi un utente dall'account, l'utente non può più accedere alla console, passare al tuo account se appartiene ancora a un altro account o accedere alle risorse dell'account.
{:shortdesc}

Solo i proprietari dell'account o gli utenti con il seguente accesso possono rimuovere gli utenti da un account:

* Una politica IAM per il servizio di gestione account Gestione utenti con il ruolo di amministratore assegnato ed essere il gestore organizzazione Cloud Foundry se l'utente appartiene a un'organizzazione Cloud Foundry.
* Se hai l'infrastruttura classica nel tuo account, un utente deve avere una politica IAM per il servizio di gestione account Gestione utenti con il ruolo di amministratore assegnato, essere il gestore organizzazione Cloud Foundry se l'utente appartiene a un'organizzazione Cloud Foundry ed essere un predecessore dell'utente nella gerarchia di utenti dell'infrastruttura classica con assegnata l'autorizzazione di gestione utenti dell'infrastruttura classica.

Per rimuovere un utente da un account, completa la seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Dalla riga dell'utente che vuoi rimuovere, seleziona **Rimuovi utente** dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg).

Se ricevi un messaggio di errore che indica che un utente dell'infrastruttura classica non può essere rimosso, assicurati che tutti i discendenti nella gerarchia di tale utente siano stati [assegnati a un nuovo elemento principale](/docs/iam?topic=iam-update-parent), [disabilitati nell'account](/docs/iam?topic=iam-status) o eliminati e riprova.
{: tip}
