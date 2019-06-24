---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-08"

keywords: maximum limits, IBM Cloud IAM, limits, maximum policies

subcollection: iam

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Limiti di IAM {{site.data.keyword.Bluemix_notm}}
{: #iam_limits}

La seguente tabella elenca i limiti massimi per le risorse {{site.data.keyword.Bluemix_notm}} IAM (Identity and Access Management). Questi limiti si applicano a tutti gli utenti che possono creare risorse {{site.data.keyword.Bluemix_notm}} IAM. Se viene superato un limite, riceverai un'eccezione e non ti sarà consentito creare nuove risorse oltre tale limite.
{:shortdesc}

| Risorsa | Massimo |
|----------|---------|
| Gruppi di accesso per account | 500 |
| Gruppi di accesso per utente | 50 |
| ID servizio per account | 2000 |
| Chiavi API per identità | 20 |
| Regole dinamiche per ogni gruppo di accesso | 5 |
{:caption="Tabella 1. Limiti dell'account IAM" caption-side="top"}

Per garantire delle prestazioni ottimali nel tuo account, consigliamo un massimo di 1.000 politiche e autorizzazioni da-servizio-a-servizio all'interno di un singolo account.
{: tip}
