---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gestione dell'utente per le aziende 
{: #enterprise-access}

Le aziende {{site.data.keyword.cloud}} sono importanti per le grandi società o organizzazioni che hanno bisogno di raggruppare una serie di account mentre ancora mantengono gli account separati e isolati per diversi dipartimenti o team. La gestione degli utenti e del loro accesso alle risorse in ogni account rimane completamente separata anche quando gli account vengono aggiunti e organizzati in un'azienda.
{:shortdesc}

Vedi [Cos'è un'azienda?](/docs/account?topic=account-enterprise) per ulteriori informazioni sulle aziende.

L'elenco degli utenti di ciascun account secondario in un'azienda è accessibile solo agli utenti in tale account secondario. Questo significa che gli utenti che vengono invitati nell'azienda e gli utenti che vengono invitati negli account nell'azienda rimangono completamente separati. Questo è vantaggioso perché puoi aggiungere più account a un'azienda e organizzarli se necessario in gruppi di account, ma mantieni gli elenchi utenti interdetti agli altri account.

Nella maggior parte dei casi, vuoi aggiungere solo gli utenti al tuo account aziendale che hanno bisogno della capacità di gestire l'azienda. A seconda del ruolo assegnato all'utente sul [servizio di gestione dell'account aziendale](/docs/iam?topic=iam-assign-access-enterprise), dispone di vari livelli di accesso per la gestione dell'azienda. Ad esempio, un utente a cui è assegnato il ruolo di amministratore sul servizio aziendale può ridenominare l'azienda, aggiornare il dominio, visualizzare l'utilizzo, creare gli account e altro ancora. Tuttavia, un utente con il ruolo di visualizzatore o operatore è limitato alla visualizzazione della gerarchia degli account e dei gruppi di account dell'azienda.

L'invito di utenti nell'account aziendale non fornisce l'accesso per gestire alcuno degli account secondari all'interno dell'azienda o delle rispettive risorse. Se aggiungi un utente a un account aziendale che contiene alcuni account, tali utenti non dispongono automaticamente dell'accesso per gestire questi account per quanto riguarda gestione, fatturazione e altro ancora. Gli utenti dell'account aziendale non hanno inoltre accesso ad alcuna risorsa negli altri account all'interno dell'azienda.

Se desideri che un utente gestisca l'azienda e abbia accesso alle risorse all'interno degli account secondari, devi invitarlo in entrambi gli account. L'assegnazione delle politiche di accesso nell'account aziendale consente all'utente di gestire l'azienda. Inoltre, l'assegnazione delle politiche di accesso all'interno degli account secondari consente all'utente di gestire risorse specifiche o completare attività di gestione dell'account all'interno soltanto di tale account.
{: note}

Per informazioni sull'assegnazione dell'accesso agli utenti in un'azienda, vedi [Assegnazione dell'accesso aziendale](/docs/iam?topic=iam-assign-access-enterprise).
