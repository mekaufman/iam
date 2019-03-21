---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-30"

keywords: authorizations, service to service access, access between services

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Concessione dell'accesso tra i servizi
{: #serviceauth}

Molte delle funzionalità del sistema {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) sono focalizzati sulla gestione e l'applicazione dell'accesso alle risorse {{site.data.keyword.Bluemix_notm}} da parte degli utenti e delle loro applicazioni. Tuttavia, esistono altri scenari in cui potresti dover fornire un servizio con accesso alla risorsa di un utente in un altro servizio. Tutti gli utenti nel tuo account possono creare un'autorizzazione, ma solo un utente con il ruolo di amministratore può eliminare un'autorizzazione. Puoi configurare e visualizzare le autorizzazioni concesse all'interno del tuo account utilizzando la pagina **Autorizzazioni**.
{:shortdesc}

## Crea un'autorizzazione
{: #create-auth}

Puoi concedere solo il livello di accesso di cui disponi come utente del servizio di destinazione. Ad esempio, se disponi solo dell'accesso di visualizzatore sul servizio a cui si accederà, potrai assegnare solo il ruolo di visualizzatore per l'autorizzazione.

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Autorizzazioni**.
2. Fai clic su **Crea**.
3. Seleziona un servizio di origine e di destinazione per l'autorizzazione. Al servizio di origine viene fornito accesso al servizio di destinazione selezionato.
4. Seleziona un ruolo per assegnare l'accesso al servizio di origine quando si accede al servizio di destinazione.
5. Fai clic su **Autorizza**.

Solo i servizi che consentono di concedere questo tipo di accesso sono disponibili come opzioni.
{: note}

## Rimuovi un'autorizzazione
{: #remove-auth}

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Autorizzazioni**.
2. Identifica la riga per l'autorizzazione che desideri rimuovere dall'account.
3. Dal menu **Azioni** ![Icona Elenco di azioni](../icons/action-menu-icon.svg), seleziona **Rimuovi**.
5. Seleziona **Rimuovi**.
