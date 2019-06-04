---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: classic infrastructure access, VPN subnet access, classic infrastructure permissions, device access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Gestione dell'accesso all'infrastruttura classica
{: #mngclassicinfra}

Puoi aggiornare le autorizzazioni per i servizi dell'infrastruttura classica o puoi aggiungere l'accesso al dispositivo o alla sottorete VPN per un utente in qualsiasi momento. Per accedere alle autorizzazioni dell'infrastruttura classica, vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**. Quindi, seleziona il nome dell'utente per il quale vuoi aggiornare l'accesso e fai clic su **Infrastruttura classica**.
{:shortdesc}

Devi avere l'autorizzazione di gestione utenti dell'infrastruttura classica ed essere un predecessore dell'utente all'interno della gerarchia di utenti dell'infrastruttura classica. I proprietari dell'account hanno accesso completo all'account, quindi non visualizzano le autorizzazioni sulla pagina. I singoli utenti non possono modificare le proprie autorizzazioni e inoltre non visualizzano le autorizzazioni sulla pagina.
{: note}

  1. Seleziona **Autorizzazioni** per aggiornare le autorizzazioni dell'utente. Puoi selezionare tra quattro tipi di autorizzazioni: account, dispositivi, rete e servizi. Seleziona singolarmente le autorizzazioni da ogni categoria o utilizza l'opzione di una serie di autorizzazioni per assegnare le autorizzazioni in blocco.

    Le autorizzazioni di gestione e supporto dell'account che avevi precedentemente assegnato agli utenti nel tuo account vengono ora migrate dalle autorizzazioni dell'infrastruttura classica ai gruppi di accesso IAM migrati. Per ulteriori informazioni, vedi [Autorizzazioni dell'infrastruttura classica migrate](/docs/iam?topic=iam-migrated_permissions).
    {: tip}

  2. Per concedere a un utente l'accesso al dispositivo, seleziona **Dispositivi** e assegna l'accesso a dispositivi e tipi di dispositivi specifici secondo necessità.

    L'accesso ai dispositivi viene assegnato dopo che l'utente è stato invitato all'account. Le autorizzazioni del dispositivo si applicano ai dispositivi specifici assegnati per l'utente. Puoi selezionare specifici dispositivi dall'elenco o assegnare l'accesso in base al tipo di dispositivo. Se assegni l'accesso per tipo di dispositivo, potresti voler utilizzare le opzioni **Abilita accesso futuro** per garantire che ogni volta che vengono aggiunti nuovi dispositivi di un tipo specifico, all'utente venga assegnato automaticamente l'accesso a tali dispositivi.

  3. Per aggiornare l'accesso di un utente alle sottoreti VPN, seleziona **Sottoreti VPN**.

    Utilizza l'opzione **Assegnazione automatica** per impostare il modo in cui l'utente ottiene l'accesso alle sottoreti VPN in base al suo accesso al dispositivo. Se questa opzione è attivata, all'utente viene automaticamente assegnato l'accesso a tutte le sottoreti per i dispositivi a cui ha già accesso. Puoi disattivare questa opzione per selezionare manualmente le sottoreti dall'elenco.
    {: tip}

    Per fornire l'accesso alle sottoreti VPN, all'utente deve essere già stato assegnato l'accesso a uno o più dispositivi. Se l'utente non accede ad alcun dispositivo, non sono disponibili sottoreti per la selezione. Puoi definire il tipo di sottorete VPN a cui l'utente ha accesso utilizzando l'opzione **Tipo VPN**. Se selezioni **Nessuno**, non è possibile assegnare alcun accesso VPN.

    L'opzione PPTP è obsoleta, quindi se hai questa opzione e la cancelli, non è più disponibile.
    {: deprecated}
