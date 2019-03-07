---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: what is IAM, IBM Cloud IAM, IAM features, IAM API

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} Identity and Access Management
{: #iamoverview}

## Was ist Cloud IAM?
{: #what_is_IAM}

{{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) ermöglicht Ihnen die sichere Authentifizierung von Benutzern für beide Plattformservices und die einheitliche Steuerung des Zugriffs auf Ressourcen innerhalb von {{site.data.keyword.Bluemix_notm}}. Ein Set von {{site.data.keyword.Bluemix_notm}}-Services sind für die Nutzung von Cloud IAM zur Zugriffssteuerung aktiviert und in [Ressourcengruppen](/docs/resources?topic=resources-rgs#rgs) innerhalb Ihres Kontos organisiert. Auf diese Weise erhalten Benutzer den schnellen und einfachen Zugriff auf mehrere Ressourcen gleichzeitig. Die Cloud IAM-Zugriffsrichtlinien werden verwendet, um Benutzern und Service-IDs die Zugriffsberechtigungen für die Ressourcen innerhalb Ihres Kontos zuzuweisen. Sie können Benutzer und Service-IDs in einer [Zugriffsgruppe](/docs/iam?topic=iam-getstarted#getstarted) zusammenfassen, um allen Entitäten in der Gruppe ohne großen Aufwand dieselbe Zugriffsebene zu erteilen.

Eine Richtlinie weist ein Subjekt (das ein Benutzer, eine [Service-ID](/docs/iam?topic=iam-serviceids#serviceids) oder Zugriffsgruppe sein kann) einer oder mehreren Rollen zu, zusammen mit einer Kombination von Attributen, die den Geltungsbereich für die Zugriffsberechtigung auf ein Ziel definieren. Die Richtlinie kann Zugriff auf einen einzelnen Service bis hinunter zur Instanzebene erteilen, auf ein Set von Ressourcen, die in einer Ressourcengruppe organisiert sind, oder auf Kontoverwaltungsservices. Abhängig von den [IAM-Rollen](/docs/iam?topic=iam-iamusermanrol#iamusermanrol), die Sie zuweisen, werden dem Subjekt unterschiedliche Zugriffsebenen für die Durchführung von Kontoverwaltungstasks, die Arbeit mit Serviceinstanzen, den Zugriff auf einen Service über die Benutzerschnittstelle oder die Ausführung von API-Aufrufen erteilt.


![IAM zur Zugriffssteuerung in einem Konto](images/iam-diagram.svg "Informationen zum Zugriffsmanagement in einem Konto mit IAM")

Für Services, die die Erstellung von Cloud IAM-Richtlinien zur Verwaltung des Zugriffs nicht unterstützen, können Sie [Cloud Foundry-Zugriff](/docs/iam?topic=iam-cfaccess#cfaccess) oder [Berechtigungen für die klassische Infrastruktur](/docs/iam?topic=iam-infrapermission#infrapermission) verwenden.


## Welche Funktionen bietet Cloud IAM?
{: #features}

<dl>
<dt>Benutzermanagement</dt>
<dd>Das einheitliche Benutzermanagement ermöglicht Ihnen das Hinzufügen und Löschen von Benutzern in einem Konto sowohl für Plattformservices als auch für Services der klassischen Infrastruktur. Sie können eine Gruppe von Benutzern in einer so genannten Zugriffsgruppe zusammenfassen, um so die Zuweisung von Zugriff für mehrere Benutzer gleichzeitig zu beschleunigen und zu vereinfachen.</dd>
<dt>Differenzierte Zugriffssteuerung</dt>
<dd>Der Zugriff für Benutzer, Service-IDs und Zugriffsgruppen wird durch eine Richtlinie definiert. Innerhalb der Richtlinie kann der Geltungsbereich des Zugriffs für einen Benutzer, eine Service-ID oder eine Zugriffsgruppe einem Set von Ressourcen in einer Ressourcengruppe, einer einzelnen Ressource oder Kontoverwaltungsservices zugewiesen werden. Nachdem der Geltungsbereich festgelegt wurde, können Sie definieren, welche Aktionen für das Subjekt der Richtlinie zulässig sind, indem Sie die Zugriffsrollen auswählen. Rollen bieten eine Möglichkeit zur Anpassung der für das Richtliniensubjekt erteilten Zugriffsebene, um Aktionen für das Ziel der Richtlinie auszuführen, seien es Plattformmanagement-Tasks innerhalb des Kontos, der Zugriff auf die Benutzerschnittstelle eines Service oder die Ausführung von API-Aufrufen.</dd>
<dt>API-Schlüssel für Benutzerauthentifizierung</dt>
<dd>Es können mehrere API-Schlüssel für einen Benutzer erstellt werden, um Schlüsselrotationsszenarios zu unterstützen, und der gleiche Schlüssel kann für den Zugriff auf mehrere Services verwendet werden. Die {{site.data.keyword.cloud_notm}}-API-Schlüssel bieten Benutzern, die eine Zwei-Faktor-Authentifizierung oder eine föderierte ID verwenden, die Möglichkeit, die Authentifizierung bei der Konsole über die Befehlszeile zu automatisieren. Ein Benutzer kann auch über einen einzigen API-Schlüssel für die klassische Infrastruktur verfügen, der für den Zugriff auf APIs der klassischen Infrastruktur verwendet werden kann. Dies ist jedoch nicht erforderlich, da Sie mit den {{site.data.keyword.cloud_notm}}-API-Schlüsseln auf dieselben APIs zugreifen können.</dd>
<dt>Service-IDs</dt>
<dd>Eine Service-ID dient (ähnlich wie eine Benutzer-ID, die einen Benutzer identifiziert) zur Identifikation eines Service oder einer Anwendung. Es existieren IDs, die von Anwendungen zur Authentifizierung bei einem {{site.data.keyword.Bluemix_notm}}-Service verwendet werden können. Jeder Service-ID können Richtlinien zugewiesen werden, um die Zugriffsebene zu steuern, die eine Anwendung, die diese Service-ID verwendet, zulässt. Zur Aktivierung der Authentifizierung kann ein API-Schlüssel erstellt werden.</dd>
</dl>


## Wie nutze ich Cloud IAM?
{: #howto}

Der Zugriff auf und die Verwendung von Cloud IAM ist über die Benutzerschnittstelle (UI), die Befehlszeilenschnittstelle (CLI) oder die Anwendungsprogrammierschnittstelle (API) für Identity and Access Management (IAM) möglich.

* Wenn Sie über die Benutzerschnittstelle (UI) auf Cloud IAM zugreifen wollen, rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf.
* Lesen Sie den Abschnitt [IAM-Zugriff, API-Schlüssel, Service-IDs und Zugriffsgruppen verwalten](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_commands_iam), um mehr zu den verfügbaren CLI-Befehlen zu erfahren.
* Konsultieren Sie die folgenden API-Dokumente, um mehr zu den verfügbaren APIs zu erfahren:
    * [API für IAM-Identitätsservices](https://{DomainName}/apidocs/iam-identity-token-api){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")
    * [API für IAM-Zugriffsgruppen](https://{DomainName}/apidocs/iam-access-groups){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")
    * [API für IAM-Richtlinienmanagement](https://{DomainName}/apidocs/iam-policy-management){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link")
