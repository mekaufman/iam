---

copyright:

  years: 2017, 2019

lastupdated: "2019-07-25"

keywords: user identities, service ID, policies, access management, roles, actions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:external: target="_blank" .external}

# IAM-Konzepte
{: #iamconcepts}

Bei {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) geht es im Wesentlichen um zwei Konzepte: 'Identität' und 'Zugriffsmanagement'. Darüber hinaus können Sie sich über Zugriffsgruppen, Ressourcengruppen, Benutzer, Rollen, Zugriffsrichtlinien und mehr informieren.
{: shortdesc}

## Identität
{: #identity}

Das Konzept der Identität in {{site.data.keyword.Bluemix_notm}} IAM basiert auf Benutzeridentitäten, Service- und App-Identitäten sowie API-Schlüsseln und Ressourcen. Benutzer werden durch ihre IBMid oder SoftLayer-Konto-ID identifiziert. Service-IDs sind ein zweiter Identitätstyp, der bei einem Konto verwendet wird. Bei den Service-IDs handelt es sich um die Funktion von Cloud IAM, die zur Bereitstellung einer separaten Identität für Services und Anwendungen benutzt wird. Sie können eine Service-ID erstellen, die von einer Anwendung benutzt wird, die Zugriff auf Ihre {{site.data.keyword.Bluemix_notm}}-Services benötigt, damit die individuellen Benutzerberechtigungsnachweise nicht verwendet werden müssen.

Für die Authentifizierung mit einer API oder CLI als Benutzer- oder Service-ID können {{site.data.keyword.cloud_notm}}-API-Schlüssel verwendet werden. Diese API-Schlüssel werden über Cloud IAM bereitgestellt und können aus diesem Grund nicht allgemein für die Authentifizierung mit einer IBMid außerhalb von IBM Cloud eingesetzt werden. Ein Benutzer kann auch über einen einzigen API-Schlüssel für die klassische Infrastruktur verfügen, der für den Zugriff auf APIs der klassischen Infrastruktur verwendet werden kann. Dies ist jedoch nicht erforderlich, da Sie mit den {{site.data.keyword.cloud_notm}}-API-Schlüsseln auf dieselben APIs zugreifen können.

Schließlich gehören zum Identitätskonzept in IAM noch die {{site.data.keyword.Bluemix_notm}}-Ressourcen, die durch ihre Cloud-Ressourcennamen (CRN) identifiziert werden. Weitere Informationen hierzu finden Sie in [Cloudressourcennamen](/docs/overview?topic=overview-crn#crn).

## Zugriffsmanagement
{: #am}

Das Konzept des Zugriffsmanagements in {{site.data.keyword.Bluemix_notm}} basiert auf einer Reihe von Komponenten, die zueinander in Beziehung stehen. Dazu gehören Benutzer, Ressourcen, Richtlinien, Rollen, Aktionen und das {{site.data.keyword.Bluemix_notm}} IAM-Steuersystem, die es Benutzern erlauben, Aktionen für die Ressourcen innerhalb eines Kontos auszuführen.

{{site.data.keyword.Bluemix_notm}} IAM folgt einem [sukzessive erreichten](https://en.wikipedia.org/wiki/Eventual_consistency){: external} Muster, das vielen Cloud-nativen Services gemeinsam ist, wodurch die hohe Verfügbarkeit und Leistung von IAM über mehrere globale Regionen hinweg erhalten bleiben. Änderungen, die an IAM-Zugriffsrichtlinien, Berechtigungen, Service-IDs, API-Schlüsseln, Zugriffsgruppen, Ressourcengruppen, Benutzern oder anderen Zugriffssteuerungen vorgenommen werden, werden erfasst und über alle IAM-Komponenten und IAM-fähigen Services weltweit weitergegeben. Änderungen an den Zugriffsrechten werden möglicherweise erst wirksam, wenn der Weitergabeprozess abgeschlossen ist.

### Benutzer
{: #iam-users}

Alle Benutzer innerhalb eines Kontos werden mithilfe ihrer IBMids der SoftLayer-Konto-IDs identifiziert. Benutzer können zu dem Konto eingeladen werden und es kann ihnen Zugriff auf Ressourcen erteilt werden. Zugriffsrichtlinien beginnen mit dem Subjekt; häufig ist dies ein Benutzer in Ihrem Konto. Der Zugriff kann Kontoverwaltungsservices, einzelnen Ressourcen (bis zur Instanzebene) oder aber einem Set von Ressourcen zugewiesen werden, die in einer Kontoressourcengruppe organisiert sind.


### Zugriffsgruppen
{: #access-groups-iam}

Es kann eine Gruppe von Benutzern und Service-IDs erstellt werden, sodass allen Entitäten in der Gruppe derselbe Zugriff mit einer oder mehreren Richtlinien zugewiesen werden kann. Durch die Verwendung von Zugriffsgruppen können Sie den Zugriffszuordnungsprozess optimieren, da Sie nur eine geringere Anzahl von Richtlinien verwalten brauchen und die Anzahl der Richtlinien in einem Konto verringern können, wodurch sich die Leistung verbessert. Nachdem Sie Ihre Gruppen eingerichtet haben, können Sie mit der Zuordnung von Richtlinien beginnen, indem Sie eine Zugriffsgruppe als Gegenstand der Richtlinie auswählen. Weitere Informationen finden Sie in [Zugriffsgruppen einrichten](/docs/iam?topic=iam-groups).

### Ressourcen
{: #resources-access-management}

Kontoressourcen stellen die bereitgestellten Serviceangebote dar, die aus dem Katalog oder den differenzierteren Ressourcen innerhalb einer Serviceinstanz ausgewählt werden. Diese Ressourcen werden zu einer Ressourcengruppe hinzugefügt, wenn sie aus dem Katalog erstellt werden. Das IAM-Zugriffsmanagement ermöglicht einen differenzierten Zugriff, was bedeutet, dass eine Richtlinie entweder mit einem größeren Umfang (z. B. für alle Ressourcen in einer Ressourcengruppe) oder für einen bestimmten Ressourcentyp (wie z. B. ein {{site.data.keyword.cos_full_notm}}-Bucket in einer bestimmten Instanz) festgelegt werden kann.


### Zugriffsrichtlinien
{: #access-policies-concept}

Zugriffsrichtlinien legen fest, auf welche Weise Benutzern, Service-IDs und Zugriffsgruppen im Konto die Berechtigung zum Zugriff auf Kontoressourcen erteilt wird. Richtlinien umfassen ein Subjekt, ein Ziel und eine Rolle. Das Subjekt ist die Benutzer- oder Service-ID oder die Benutzergruppe, der Sie die Zugriffsberechtigungen erteilen. Das Ziel der Richtlinie ist die Ressource, auf die Zugriff bereitgestellt werden soll. Die Rollen legen die Zugriffsebene oder die zulässigen Aktionen für das Ziel der Richtlinie fest. Es stehen verschiedene Typen von Richtlinien zur Verfügung, die den Zugriff auf die Kontoressourcen zulassen: eine Ressourcengruppenrichtlinie, eine Ressourceninstanzrichtlinie, eine kontoweite Richtlinie für den Zugriff auf alle Services mit aktiviertem Identity and Access Management sowie eine Richtlinie für einen oder alle Kontoverwaltungsservices. Abhängig von den von Ihnen ausgewählten Optionen können angepasste Konfigurationsoptionen verfügbar sein, z. B. zum Definieren des Zugriffs bis zur Ressourcenebene in einer bestimmten Region oder zum Definieren des Zugriffs auf die differenzierte Ebene einer servicespezifischen Ressource innerhalb einer Instanz.

### Rollen
{: #iam-roles-concept}

Die Cloud IAM-Zugriffsrollen ermöglichen einem Benutzer die Ausführung bestimmter Tasks für die Ressource, die in der Richtlinie definiert ist. Es stehen zwei Typen von Zugriffsrollen zur Verfügung: Zugriffsrollen für das Plattformmanagement und den Servicezugriff. 

Plattformverwaltungsrollen definieren zulässige Aktionen für die Verwaltung von Ressourcen auf Plattformebene, z. B. den Benutzerzugriff und die Erstellung von Serviceinstanzen. Plattformrollen gelten auch für Aktionen, die im Kontext von Kontoverwaltungsservices ausgeführt werden können, wie z. B. das Einladen und Entfernen von Benutzern, das Verwalten von Zugriffsgruppen und Service-IDs sowie private Katalogangebote. 

Die Servicezugriffsrollen definieren die zulässigen Aktionen im Kontext der Servicenutzung, z. B. den Aufruf von Service-APIs. Diese Rollen werden basierend auf dem Service angepasst, der in der Richtlinie ausgewählt wird.

### Aktionen
{: #iam-roles-actions}

Aktionen werden bestimmten Cloud IAM-Rollen zugeordnet. Auf diese Weise erhalten Benutzer nur dann die Möglichkeit, spezielle Tasks auszuführen, wenn ihnen die entsprechenden Rollen zugewiesen wurden. Die zulässigen Aktionen der einzelnen Rollen können sich abhängig vom Service, auf den zugegriffen wird, ändern. Dies ist darauf zurückzuführen, dass jeder Service festlegt, wie eine bestimmte Rolle der Verwendung des Service zugeordnet wird.

### System für das Zugriffsmanagement
{: #access-management-system}

Das Cloud IAM-Steuersystem ermöglicht oder verweigert die Ausführung von Aktionen durch Benutzer innerhalb des Kontextes eines Service auf Basis der zugewiesenen Richtlinie. Wenn ein Benutzer versucht, eine bestimmte Aktion auszuführen, dann verwendet das Steuersystem die Attribute, die in der Richtlinie definiert sind, um festzustellen, ob der Benutzer über die Berechtigung zur Ausführung dieser Task verfügt.
