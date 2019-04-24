---



copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:faq: data-hd-content-type='faq'}
{:note: .note}

# Häufig gestellte Fragen (FAQs)
{: #iamfaq}

## Was ist das Identitäts- und Zugriffsmanagement von {{site.data.keyword.cloud_notm}}?
{: #whatisiam}
{: faq}

IAM (Identity and Access Management, Identitäts- und Zugriffsmanagement) ermöglicht Ihnen, Benutzer sicher für Plattformservices zu authentifizieren und den Zugriff auf Ressourcen innerhalb der {{site.data.keyword.cloud_notm}}-Plattform zu steuern. Eine Reihe von IBM Cloud-Services kann Cloud IAM für die Zugriffssteuerung verwenden. Diese Services sind in Ressourcengruppen innerhalb Ihres Kontos organisiert, um Benutzern einen schnellen und bequemen Zugriff auf mehrere Ressourcen gleichzeitig zu ermöglichen. Die Cloud IAM-Zugriffsrichtlinien werden verwendet, um Benutzern und Service-IDs die Zugriffsberechtigungen für die Ressourcen innerhalb Ihres Kontos zuzuweisen. Weitere Informationen finden Sie in [{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam?topic=iam-iamoverview#iamoverview).

## Was ist ein IAM-fähiger Service?
{: #iam-enabled}
{: faq}

Ein IAM-fähiger Service muss in einer Ressourcengruppe enthalten sein und der Zugriff auf den Service erfolgt über die Verwendung von IAM-Zugriffsrichtlinien. Wenn Sie einen IAM-fähigen Service aus dem Katalog erstellen, müssen Sie ihn einer Ressourcengruppe zuordnen. Weitere Informationen finden Sie in [Was ist eine Ressource?](/docs/resources?topic=resources-resource#resource)

{{site.data.keyword.containerlong_notm}} ist die einzige Ausnahme. Der Zugriff wird über IAM gesteuert, doch der Service ist stets der Standardressourcengruppe zugewiesen. Daher können Sie bei der Erstellung aus dem Katalog keine Ressourcengruppe auswählen, denn es werden keine entsprechenden Auswahloptionen angezeigt. Darüber hinaus ist die Zuordnung des Service zu einer beliebigen anderen Ressourcengruppe nicht möglich.


## Sind IAM und Cloud Foundry verwandt?
{: #iam-cloudfoundry}
{: faq}

Sie sind nicht verwandt. Cloud Foundry ist eine Open-Source-Plattform, die Organisationen, Bereiche und Cloud-Foundry-Rollen für den Zugriff auf die Verwaltung verwendet. IAM ist die sichere Methode, Benutzer für Plattformservices zu authentifizieren und den Zugriff auf Ressourcen über die {{site.data.keyword.cloud_notm}}-Plattform zu steuern, indem Ressourcengruppen und IAM-Zugriffsrollen verwendet werden.

Die Systeme für das Zugriffsmanagement sind völlig unterschiedlich. IAM-Ressourcen gehören zu einer Ressourcengruppe, und Cloud Foundry-Ressourcen gehören zu einer Organisation und einem Bereich. IAM-Zugriffsrichtlinien werden verwendet, um Zugriff auf Ressourcen in einer Ressourcengruppe bereitzustellen. Darüber hinaus, werden Cloud Foundry-Organisations- und Bereichsrollen verwendet, um in einem Bereich Benutzerzugriff auf Cloud Foundry-Ressourcen zu bieten. IAM bietet keinen Zugriff auf Elemente in Cloud Foundry-Bereichen und Cloud Foundry-Rollen können keinen Zugriff auf Ressourcen in einer Ressourcengruppe gewähren.

## Wie stelle ich fest, worauf ich Zugriff haben?
{: #iam-access}
{: faq}

Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie auf der Seite 'Benutzer' Ihren Namen aus. Öffnen Sie dann abhängig von dem Zugriff, nach dem Sie suchen, die verschiedenen Registerkarten.

* Wenn Sie anhand der Ihnen zugewiesenen Zugriffsgruppen ermitteln wollen, welchen Zugriff Sie haben, wählen Sie **Zugriffsgruppen** aus.
* Wenn die Ihnen zugewiesenen IAM-Zugriffsrichtlinien angezeigt werden sollen, wählen Sie **Zugriffsrichtlinien** aus.
* Wenn Ihr Cloud Foundry-Zugriff für alle Organisationen und Bereiche angezeigt werden soll, wählen Sie **Cloud Foundry-Zugriff** aus.


## Wie fordere ich Zugriff auf eine Ressource an?
{: #request-access}
{: faq}

Der Kontoeigner kann Ihren Zugriff auf eine beliebige Ressource im Konto aktualisieren oder Sie können einen beliebigen Benutzer kontaktieren, der die Administratorrolle für den Service oder die Serviceinstanz innehat.

## Warum sollte ich Ressourcengruppen und Zugriffsgruppen verwenden?
{: #resource-groups}
{: faq}

Eine Ressourcengruppe ist ein logischer Container für Ressourcen. Wenn eine Ressource erstellt wird, wird sie einer Ressourcengruppe zugeordnet und kann nicht verschoben werden, nachdem sie hinzugefügt wurde.

Eine Zugriffsgruppe wird verwendet, um eine Gruppe von Benutzern und Service-IDs ohne großen Aufwand in einer einzigen Entität zu organisieren, um so Zuordnungen zu vereinfachen. Sie können einer Zugriffsgruppe eine einzige Richtlinie zuordnen, um allen Mitgliedern diese Berechtigungen zu erteilen. Wenn Sie mehr als einen Benutzer oder mehr als eine Service-ID haben, die denselben Zugriff benötigen, erstellen Sie eine Zugriffsgruppe, anstatt denselben Zugriff mehrmals für den einzelnen Benutzer oder die einzelne Service-ID zuzuweisen.

Durch die Verwendung sowohl von Ressourcengruppen als auch von Zugriffsgruppen können Sie die Zugriffszuordnungsrichtlinie optimieren, indem Sie eine begrenzte Anzahl von Richtlinien zuordnen. Sie können alle Ressourcen, auf die eine bestimmte Gruppe von Benutzern und Service-IDs Zugriff benötigt, in einer einzigen Ressourcengruppe organisieren, alle Benutzer oder Service-IDs in einer Zugriffsgruppe gruppieren und dann eine einzige Richtlinie zuordnen, die Zugriff auf alle Ressourcen in der Ressourcengruppe gewährt.

Weitere Informationen enthält [Bewährte Verfahren für die Zuweisung von Zugriff](/docs/iam?topic=iam-account_setup#account_setup).

## Wie stelle ich sicher, dass meine Benutzer Ressourcen in einer Ressourcengruppe erstellen können?
{: #resources}
{: faq}

Um eine Ressource in einer Ressourcengruppe zu erstellen, muss der Benutzer über zwei Zugriffsrichtlinien verfügen: Eine Richtlinie, die der Ressourcengruppe selbst zugeordnet ist, und eine Richtlinie, die den Ressourcen in der Gruppe zugeordnet ist. Der Zugriff auf die Ressourcengruppe selbst ist einfach ein Zugriff auf den Container,  der die Ressourcen verwaltet. Diese Art von Richtlinie erlaubt einem Benutzer, den Zugriff auf die Gruppe anzuzeigen, zu bearbeiten oder zu verwalten. Sie erlaubt jedoch  keinen Zugriff auf die Ressourcen innerhalb der Gruppe. Der Zugriff auf Services innerhalb der Ressourcengruppe ermöglicht einem Benutzer die Arbeit mit den Serviceinstanzen. Das heißt, der Benutzer kann eine Serviceinstanz erstellen.

Der Benutzer muss also mindestens über folgende Zugriffsrechte verfügen:

* Rolle des Anzeigeberechtigten ('Viewer') oder höher für die Ressourcengruppe selbst
* Rolle des Bearbeiters ('Editor') oder höher für den Service oder für alle Services in der Ressourcengruppe


## Welchen Zugriff brauche ich, um anderen Zugriff zu ermöglichen?
{: #user-access}
{: faq}

Für IAM-fähige Services müssen Sie die Rolle des Administrators für den Service oder die Ressource innehaben, zu dem bzw. zu der Sie Benutzern Zugriff gewähren möchten. Wenn Sie Zugriff auf alle Services oder Ressourcen im Konto zuweisen möchten, benötigen Sie für alle IAM-fähigen Services eine Richtlinie mit der Administratorrolle. Um Benutzern Zugriff auf Kontoverwaltungsservices zuweisen zu können, muss Ihnen außerdem die Administratorrolle für den speziellen Service oder für alle Kontoverwaltungsservices zugewiesen sein.

Für Cloud Foundry-Services müssen Sie über die Cloud Foundry-Rollen des Organisationsmanagers und des Bereichsmanagers verfügen, um Zugriff auf Cloud Foundry-Ressourcen erteilen zu können.

Für die klassische Infrastruktur müssen Sie über die Berechtigung der klassischen Infrastruktur zum Verwalten von Benutzern verfügen und für diejenigen Service- und Gerätekategorien Berechtigungen für die Ressourcen besitzen, für die Sie dem Benutzer Zugriff erteilen möchten.

## Was ist der Unterschied zwischen der Bereitstellung eines Zugriffs zur Verwaltung einer Ressourcengruppe und dem Zugriff auf Ressourcen innerhalb einer Ressourcengruppe?
{: #providing-access}
{: faq}

Wenn Sie über Zugriff zur Verwaltung einer Ressourcengruppe verfügen, können Sie den Namen anzeigen und bearbeiten und den Zugriff auf die Ressourcengruppe selbst abhängig von der zugeordneten Rolle verwalten. Der Zugriff auf die Ressourcengruppe selbst bedeutet nicht, dass der Benutzer Zugriff auf die Ressourcen innerhalb der Ressourcengruppe hat.

Wenn Sie über Zugriff auf die Ressourcen innerhalb einer Ressourcengruppe haben, können Sie Instanzen bearbeiten, löschen und erstellen oder abhängig von der zugeordneten Rolle über alle Verwaltungsaktionen für die angegebenen Services innerhalb der Ressourcengruppe verfügen.

Informationen zu Plattformmanagementrollen und Aktionen für die Kontoverwaltungsservices finden Sie zum Beispiel in den Tabellen der Plattformrollen unter [Platform roles table](/docs/iam?topic=iam-userroles#platformrolestable2).

## Wer kann Benutzer entfernen?
{: #remove-users}
{: faq}

Der Kontoeigner kann beliebige Benutzer aus dem Konto entfernen. Ferner können auch alle Benutzer, die über die folgenden Zugriffsrechte verfügen, Benutzer aus einem Konto entfernen:

* Ihnen ist über eine IAM-Richtlinie für den Benutzerverwaltungs- und Kontoverwaltungsservice die Administratorrolle zugewiesen und sie haben die Funktion des Cloud Foundry-Organisationsmanagers, wenn der Benutzer einer Cloud Foundry-Organisation angehört.
* Wenn Ihr Konto die klassische Infrastruktur beinhaltet, muss den Benutzern über eine IAM-Richtlinie für den Benutzerverwaltungs- und Kontoverwaltungsservice die Administratorrolle zugewiesen sein, sie müssen die Funktion des Cloud Foundry-Organisationsmanagers haben, wenn der Benutzer einer Cloud Foundry-Organisation angehört, und sie müssen in der Benutzerhierarchie der klassischen Infrastruktur als Vorfahre gelten, dem für die klassische Infrastruktur die Berechtigung zum Verwalten von Benutzern zugewiesen ist.

## Wie mache ich die Mehrfaktorauthentifizierung mit einer IBMid (IBMid MFA) für mein Konto erforderlich?
{: #multi-factor}
{: faq}

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie **Einstellungen** aus.
2. Wählen Sie **Mehrfaktorauthentifizierung** aus und klicken Sie dann auf **Ja, ich bin sicher**. Weitere Informationen hierzu finden Sie in [MFA für Benutzer in Ihrem Konto verlangen](/docs/iam?topic=iam-enablemfa#enablemfa).

## Was ist der Unterschied zwischen Service- und Plattformrollen?
{: #service-platform-roles}
{: faq}

Service- und Plattformrollen sind zwei verschiedene Typen von Rollen:

* Plattformrollen sind die Art und Weise, wie Sie mit einem Service in einem Konto arbeiten, z. B. Instanzen erstellen, Instanzen binden und den Benutzerzugriff auf den Service verwalten. Für Plattformservices ermöglichen diese Rollen den Benutzern beispielsweise, Ressourcengruppen zu erstellen und Service-IDs zu verwalten. Plattformrollen sind: Administrator, Bearbeiter, Bediener und Anzeigeberechtigter.

* Servicerollen definieren die Möglichkeit, Aktionen für einen Service auszuführen und sind für jeden Service spezifisch. Zu den Aktionen zählen das Ausführen von API-Aufrufen oder das Zugreifen auf die Benutzerschnittstelle. Servicerollen sind: Manager, Schreibberechtigter und Leseberechtigter. Weitere Informationen darüber, wie diese Rollen angewendet werden, finden Sie in der Dokumentation des jeweiligen Service.

## Was ist der Unterschied zwischen einer Ressourcengruppe und Cloud Foundry-Organisationen und -Bereichen?
{: #groups-organizations}
{: faq}

Am Anfang von {{site.data.keyword.Bluemix_notm}} war der Open-Source-Plattform-Service für die Zugriffssteuerung und die Organisation von Ressourcen Cloud Foundry die einzige Methode für die Organisierung und Steuerung des Zugriffs auf Ressourcen. Mit der Erweiterung von {{site.data.keyword.Bluemix_notm}} wurde eine neue Methode erforderlich, die von allen Service- und Ressourcentypen verwendet werden kann. Ressourcengruppen werden jetzt verwendet, um viele Typen von Ressourcen zu gruppieren und zu organisieren. IAM wird verwendet, um den Zugriff auf Services und Ressourcen konsistent zu steuern. Eine Reihe von Services ist bereits zur Verwendung von Ressourcengruppen und IAM übergegangen. Weitere Services werden im Laufe der Zeit diese neue Methode der Ressourcenorganisation und Zugriffsverwaltung verwenden.

Die Zugriffssteuerung und die Ressourcenorganisation des Kontos sind die wesentlichen Unterschiede zwischen Ressourcengruppen und Cloud Foundry-Organisationen und -Bereichen. Ressourcengruppen organisieren IAM-fähige Services in einem Konto, dessen Zugriffssteuerung über IAM-Richtlinien erfolgt. Die Zugriffssteuerung für Organisationen und Bereiche erfolgt über Cloud Foundry-Rollen und Cloud Foundry-Ressourcen werden Bereichen zugeordnet. Organisationen und Bereiche können verwendet werden, um Ressourcen innerhalb eines Cloud Foundry-Bereichs zu organisieren und den Zugriff auf sie zu steuern, während Ressourcengruppen und IAM für mehrere Ressourcentypen in {{site.data.keyword.Bluemix_notm}} verwendet werden können.

## Wie kann ich Funktionen des Kontoadministrators delegieren?  
{: #account-administrator}
{: faq}

Um die Funktionen des Kontoadministrators zu delegieren, müssen Sie folgenden Zugriff zuordnen:

* Eine IAM-Richtlinie, über die die Rolle des Administrators für alle Services mit aktiviertem Identity and Access Management zugewiesen ist, wodurch der Benutzer die Möglichkeit erhält, Serviceinstanzen zu erstellen und Benutzern Zugriff auf alle Ressourcen im Konto zu erteilen.
* Eine IAM-Richtlinie, über die die Rolle des Administrators für alle Kontoverwaltungsservices zugewiesen ist, wodurch der Benutzer die Möglichkeit erhält, Tasks wie das Einladen und Entfernen von Benutzern, Verwalten von Zugriffsgruppen, Service-IDs und privaten Katalogangeboten auszuführen sowie die Abrechnungs- und Nutzungsverfolgung zu verwenden.
* Das Berechtigungsset des Superusers für die klassische Infrastruktur.
* Die Rolle des Cloud Foundry-Managers für alle Organisationen.

Ein Kontoadministrator kann jedoch selbst mit dem zuvor beschriebenen Zugriff die MFA-Einstellung für das Konto nicht ändern. Diese Einstellung kann nur vom Kontoeigner geändert werden.
{: note}

## Was ist der Unterschied zwischen einem Kontoadministrator und einem Kontoeigner?
{: #owner-administrator}
{: faq}

Kontoeigner werden automatisch als Kontoadministrator für {{site.data.keyword.Bluemix_notm}} IAM zugewiesen. Als Kontoadministrator können Sie Benutzer einladen, den Zugriff für Benutzer zuweisen und verwalten, Ressourcengruppen erstellen, die Mehrfaktorauthentifizierung (MFA) für alle Benutzer im Konto verlangen und Serviceinstanzen erstellen. Wenn Sie anderen Benutzern in Ihrem Konto die Funktion des Kontoadministrators ermöglichen wollen, müssen Sie ihnen den folgenden Zugriff zuweisen:

* Eine IAM-Richtlinie, über die die Rolle des Administrators für alle Services mit aktiviertem Identity and Access Management zugewiesen ist, wodurch der Benutzer die Möglichkeit erhält, Serviceinstanzen zu erstellen und Benutzern Zugriff auf alle Ressourcen im Konto zu erteilen.
* Eine IAM-Richtlinie, über die die Rolle des Administrators für alle Kontoverwaltungsservices zugewiesen ist, wodurch der Benutzer die Möglichkeit erhält, Tasks wie das Einladen von Benutzern, Verwalten von Zugriffsgruppen, Service-IDs und privaten Katalogangeboten auszuführen sowie die Abrechnungs- und Nutzungsverfolgung zu verwenden.
* Das Berechtigungsset des Superusers für die klassische Infrastruktur.
* Die Rolle des Cloud Foundry-Managers für alle Organisationen.

Ein Kontoadministrator kann jedoch selbst mit dem zuvor beschriebenen Zugriff die MFA-Einstellung für das Konto nicht ändern. Diese Einstellung kann nur vom Kontoeigner geändert werden.
{: note}

## Wie kann ich Zugriff auf die Infrastruktur und auf Geräte zuweisen?
{: #infrastructure-devices}
{: faq}

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie dann **Benutzer** aus.
2. Wählen Sie den Namen eines Benutzers aus.
3. Klicken Sie auf **Klassische Infrastruktur**.
4. Verwenden Sie zum Zuweisen von Berechtigungen den Abschnitt **Berechtigungen**, zum Zuweisen von Zugriff auf Geräte den Abschnitt **Geräte** und zum Zuweisen von Zugriff auf VPN-Teilnetze für die Geräte, für die dem Benutzer Zugriff zugewiesen ist, den Abschnitt **VPN-Zugriff**.

## Kann jeder Benutzer in meinem Konto alle anderen Benutzer sehen?
{: #users}
{: faq}

Ein Kontoeigner kann all anderen Benutzer im Konto anzeigen und auf der Seite 'Benutzer' auswählen, wie Benutzern andere Benutzer im Konto angezeigt werden. Auf der Seite 'Einstellungen' kann ein Kontoeigner die Einstellung für die [Sichtbarkeit der Benutzerliste](/docs/iam?topic=iam-userlistview#userlistview) durch die Auswahl einer der folgenden Optionen anpassen:

* **Ansicht ohne Einschränkung**: Alle Benutzer in Ihrem Konto können alle anderen Benutzer im Konto anzeigen.
* **Eingeschränkte Ansicht**: Beschränkt die Sichtbarkeit von Benutzern auf der Seite 'Benutzer' auf diejenigen Benutzer, denen explizit Zugriff gewährt wurde, sowie auf solche Benutzer, für die andere Benutzer über eine gemeinsam genutzte Cloud Foundry-Organisation oder eine Beziehung in der Benutzerhierarchie der klassischen Infrastruktur sichtbar sind.


## Muss ich einem Benutzer Zugriff erteilen, wenn ich ihn zum Konto einlade?
{: #account-invite}
{: faq}

Ja. Sie müssen einem Benutzer im Rahmen der folgenden drei Systeme für das Zugriffsmanagement Zugriff erteilen:

* IAM-Zugriffsrichtlinie für eine Ressource, eine Ressourcengruppe oder für Kontoverwaltungsservices
* Cloud Foundry-Rolle für eine Organisation und einen Bereich
* Berechtigungsset für die klassische Infrastruktur


## Wie kann ich Authentifizierung in meine Webanwendungen und mobilen Apps einbinden?
{: #appid}
{: faq}

IAM wird für die Verwaltung des Zugriffs auf Ihre {{site.data.keyword.cloud_notm}}-Services und -Ressourcen verwendet. Mit {{site.data.keyword.appid_full_notm}} können Sie die Cloudsicherheit noch weiter steigern, indem Sie Authentifizierungsmechanismen in Ihre Webanwendungen und mobilen Apps einbinden. Mit nur wenigen Zeilen Code können Sie Ihre cloud-nativen Apps und Services, deren Ausführung auf {{site.data.keyword.cloud_notm}} erfolgt, ohne großen Aufwand schützen. Sind Sie bereit, loszulegen? [Informieren Sie sich anhand der Dokumentation](/docs/services/appid?topic=appid-gettingstarted#gettingstarted).
