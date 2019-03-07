---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: application programming interface key, API key, API, classic infrastructure API key, IBM Cloud API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Informationen zu API-Schlüsseln
{: #manapikey}

Bei einem Schlüssel einer Anwendungsprogrammierschnittstelle (API-Schlüssel) handelt es sich um einen eindeutigen Code, der an eine API übergeben wird, um die aufrufende Anwendung oder den aufrufenden Benutzer zu identifizieren. API-Schlüssel werden verwendet, um zu verfolgen und zu steuern, wie die API verwendet wird, um so z. B. Verwendung in böswilliger Absicht oder Missbrauch der API zu verhindern. Der API-Schlüssel dient oft als eindeutige Kennung und zugleich als geheimes Token für die Authentifizierung. Normalerweise ist ihm eine Gruppe von Zugriffsrechten zugeordnet, die speziell für die ihm zugeordnete Identität gelten.
{:shortdesc}

Wenn Sie Ihre API-Schlüssel anzeigen möchten, rufen Sie **Verwalten** > **Zugriff (IAM)** auf und wählen Sie **Benutzer** aus. Wählen Sie dann einen Benutzer aus, um zu dem auf der Seite 'Benutzerdetails' enthaltenen Abschnitt für API-Schlüssel zu navigieren.

## {{site.data.keyword.cloud_notm}}-API-Schlüssel
{: #ibm-cloud-api-keys}

{{site.data.keyword.cloud}}-API-Schlüssel werden in der {{site.data.keyword.cloud_notm}}-Konsole auf der Seite 'Benutzerdetails' für einen Benutzer erstellt und sind der Identität des Benutzers zugeordnet. Nur der Benutzer, dem der API-Schlüssel zugeordnet ist, kann ihn erstellen und löschen. Sie können die {{site.data.keyword.cloud_notm}}-API-Schlüssel in der Befehlszeilenschnittstelle (CLI) oder im Rahmen der Automatisierung für die Anmeldung mit Ihrer Benutzeridentität verwenden. Sie können {{site.data.keyword.cloud_notm}}-API-Schlüssel aber auch verwenden, um auf APIs der klassischen Infrastruktur zuzugreifen. Weitere Informationen zur Verwendung eines API-Schlüssels, der Ihrer Benutzeridentität zugeordnet ist, finden Sie in [API-Schlüssel für Benutzer verwalten](/docs/iam?topic=iam-userapikey#userapikey).

Sie können außerdem API-Schlüssel verwenden, die den von Ihnen erstellten Service-IDs zugeordnet sind. Service-IDs werden verwendet, um eine Verbindung zwischen einer Anwendung innerhalb oder außerhalb von {{site.data.keyword.Bluemix_notm}} und einem {{site.data.keyword.Bluemix_notm}}-Service herzustellen. Weitere Informationen zum Erstellen von API-Schlüsseln, die einer Service-ID zugeordnet sind, finden Sie in [API-Schlüssel für Service-IDs verwalten](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys).

## Andere Typen von API-Schlüsseln
{: #othertypes}

Zusätzlich zu Ihren {{site.data.keyword.cloud_notm}}-API-Schlüsseln stehen einige andere Typen von API-Schlüsseln zur Verfügung, die Sie verwenden können:

* API-Schlüssel der klassischen Infrastruktur
* Servicespezifische API-Schlüssel

API-Schlüssel für die klassische Infrastruktur sind API-Schlüssel, die zum Aufrufen der APIs für Services der klassischen Infrastruktur verwendet werden. Sie können immer nur jeweils einen API-Schlüssel für die klassische Infrastruktur erstellen. Die Erstellung eines API-Schlüssels für die klassische Infrastruktur für einen Benutzer erfolgt über die Seite 'Benutzerdetails'.

{{site.data.keyword.cloud_notm}}-API-Schlüssel können auch für den Zugriff auf APIs der klassischen Infrastruktur verwendet werden.
{: tip}

Einige Services in {{site.data.keyword.Bluemix_notm}} stellen möglicherweise auch einen API-Schlüssel bereit, den Sie beim Arbeiten mit dem Service verwenden können. Wenn Sie beispielsweise über Ihre Ressourcenliste die Angebotsdetails eines Watson-Service anzeigen, können Sie auf der Registerkarte 'Serviceberechtigungsnachweise' einen Berechtigungsnachweis erstellen, der einen API-Schlüssel sowie einen geheimen Schlüssel enthält und für genau diesen Service bestimmt ist.
