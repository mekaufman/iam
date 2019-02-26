---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-30"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Limiti di IAM {{site.data.keyword.Bluemix_notm}}
{: #iam_limits}

La seguente tabella elenca i limiti massimi per le risorse {{site.data.keyword.Bluemix_notm}} IAM (Identity and Access Management). Questi limiti si applicano a qualsiasi utente che può creare risorse IAM {{site.data.keyword.Bluemix_notm}}; se un limite viene superato, riceverai un'eccezione e non ti sarà consentito creare nuove risorse oltre tale limite.

| Risorsa | Massimo |
|----------|---------|
| Gruppi di accesso per account | 500 |
| Gruppi di accesso per utente | 50 | 
| ID servizio per account | 2000 | 
| Chiavi API per identità | 20 |
{:caption="Tabella 1. Limiti dell'account IAM" caption-side="top"}

Per garantire delle prestazioni ottimali nel tuo account, consigliamo un massimo di 1.000 politiche e autorizzazioni da-servizio-a-servizio all'interno di un singolo account. 
{: tip}
