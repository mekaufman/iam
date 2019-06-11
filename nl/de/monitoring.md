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

# IAM-Ereignisse verfolgen
{: #tracking}

Als Sicherheitsbeauftragte, Auditor oder Manager können Sie den {{site.data.keyword.at_full}}-Service verwenden, um die Interaktion von Benutzern und Anwendungen mit {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) zu verfolgen.
{:shortdesc}

Ab 09. Mai 2019 wird der {{site.data.keyword.cloudaccesstraillong}}-Service nicht mehr verwendet. Sie müssen eine Instanz von {{site.data.keyword.at_short}} in Ihrem Konto erstellen, um die Verfolgung von IAM-Ereignissen fortzusetzen. Weitere Informationen finden Sie in [IBM Cloud Activity Tracker-Service wird nicht mehr verwendet](https://www.ibm.com/blogs/bluemix/2019/04/deprecating-ibm-cloud-activity-tracker/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link").
{: deprecated}

Die folgenden Ereignisse können verfolgt werden:

* Verwalten von Zugriffsgruppen durch Erstellen und Löschen von Gruppen bzw. durch Hinzufügen und Entfernen von Benutzern
* Erstellen, Aktualisieren oder Löschen von Service-IDs
* Erstellen, Aktualisieren oder Löschen von API-Schlüsseln
* Erstellen, Aktualisieren oder Löschen von Zugriffsrichtlinien
* Anmelden bei {{site.data.keyword.Bluemix_notm}} mit einem API-Schlüssel, einem Berechtigungscode, einem Kenncode, einem Kennwort oder mit einem einer Service-ID zugeordneten API-Schlüssel

Weitere Informationen zum Einstieg in die Überwachung von Benutzeraktionen finden Sie in [{{site.data.keyword.at_short}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). Weitere Informationen zu den einzelnen Ereignisbereichen, die verfolgt werden können, finden Sie in [IAM-Ereignisse](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam).
