---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

keywords: event tracking, IAM events, monitoring

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Traccia degli eventi IAM
{: #tracking}

In qualità di responsabile della sicurezza, revisore o gestore, puoi utilizzare il servizio {{site.data.keyword.at_full}} per tracciare come gli utenti e le applicazioni interagiscono con {{site.data.keyword.Bluemix_notm}} IAM (Identity and Access Management).
{:shortdesc}

A partire dal 9 maggio 2019 il servizio {{site.data.keyword.cloudaccesstraillong}} è obsoleto. Devi creare un'istanza di {{site.data.keyword.at_short}} nel tuo account per continuare a tenere traccia degli eventi IAM. Per ulteriori informazioni, vedi [Deprecation of the IBM Cloud Activity Tracker service](https://www.ibm.com/blogs/bluemix/2019/04/deprecating-ibm-cloud-activity-tracker/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno").
{: deprecated}

Puoi tracciare i seguenti eventi:

* Gestione dei gruppi di accesso mediante la creazione e l'eliminazione di gruppi o l'aggiunta e la rimozione di utenti
* Creazione, aggiornamento o eliminazione di ID servizio
* Creazione, aggiornamento o eliminazione di chiavi API
* Creazione, aggiornamento o eliminazione di politiche di accesso
* Accesso a {{site.data.keyword.Bluemix_notm}} utilizzando una chiave API, un codice di autorizzazione, un passcode, una password oppure una chiave API associata a un ID servizio

Per iniziare a monitorare le azioni del tuo utente, vedi [{{site.data.keyword.at_short}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). Per ulteriori informazioni su ciascuna delle aree di evento che puoi tracciare, vedi [Eventi IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam).
