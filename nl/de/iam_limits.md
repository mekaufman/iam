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

# {{site.data.keyword.Bluemix_notm}} IAM-Grenzwerte
{: #iam_limits}

In der folgenden Tabelle sind die Maximalwerte für {{site.data.keyword.Bluemix_notm}} Identity and Access Management-Ressourcen (IAM) aufgeführt. Diese Grenzwerte gelten für jeden Benutzer, der {{site.data.keyword.Bluemix_notm}} IAM-Ressourcen erstellen kann. Wenn ein Grenzwert überschritten wird, wird eine Ausnahmebedingung ausgegeben und Sie dürfen keine neuen Ressourcen über diesen Grenzwert hinaus erstellen.
{:shortdesc}

| Ressource | Max. |
|----------|---------|
| Zugriffsgruppen pro Konto | 500 |
| Zugriffsgruppen pro Benutzer | 50 |
| Service-IDs pro Konto | 2000 |
| API-Schlüssel pro Identität | 20 |
| Dynamische Regeln pro Zugriffsgruppe | 5 |
{:caption="Tabelle 1. IAM-Kontogrenzwerte" caption-side="top"}

Für eine optimale Leistung Ihres Kontos werden maximal 1.000 Richtlinien und Service-zu-Service-Autorisierungen empfohlen.
{: tip}
