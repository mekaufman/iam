---

copyright:

  years: 2019

lastupdated: "2019-03-25"

keywords: public access, anonymous access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Abilitazione dell'accesso pubblico alle risorse
{: #public}

L'accesso pubblico alle le risorse consente a tutti gli utenti e ID del servizio di poter accedere a una risorsa specifica nel tuo account. Questo significa che un utente o un ID del servizio non deve eseguire l'autenticazione con {{site.data.keyword.Bluemix}} ad esempio per accedere alle informazioni in un bucket {{site.data.keyword.cos_full_notm}}. Solo alcuni servizi supportano la possibilità di fornire l'accesso pubblico a tipi di risorse specifici per il servizio. Pertanto, sei limitato alla creazione di politiche solo per i servizi che supportano questa funzione.
{:shortdesc}

Per abilitare l'accesso pubblico per le risorse, devi utilizzare il gruppo di accesso **Public Access** che ti viene fornito nel tuo account. Per impostazione predefinita, questo gruppo di accesso include tutti gli utenti e gli ID del servizio. Non puoi eliminare il gruppo o modificarne l'appartenenza, ma puoi aggiungere, modificare ed eliminare le politiche di accesso per il gruppo.

## Creazione di una politica per il gruppo di accesso pubblico.
{: #public_policy}

Completa la seguente procedura per assegnare una politica al tuo gruppo di accesso pubblico. La seguente attività utilizza il servizio Cloud Object Storage come esempio di assegnazione dell'accesso pubblico a un bucket denominato `mybucket123`.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Seleziona il gruppo **Public Access**.
3. Fai clic su **Assegna accesso**.
4. Seleziona **Cloud Object Storage** dall'elenco dei servizi.
5. Immetti `bucket` per il tipo di risorsa.
6. Immetti `mybucket123` per l'ID della risorsa.
7. Fai clic su **Assegna**.
8. Fai clic su **Sì** per confermare che vuoi assegnare la politica di accesso pubblico alla risorsa e poi fai clic su **Assegna**.
