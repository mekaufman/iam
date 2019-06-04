---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-23"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Fehlerbehebung für IAM
{: #troubleshoot_iam}

Zu den allgemeinen Problemen bei der Verwendung von IAM gehören gegebenenfalls der Zugriff auf eine Ressource oder auf ein Konto, um eine Aufgabe auszuführen oder den richtigen Zugriffstyp zu ermitteln, damit Benutzer zum Ausführen bestimmter Aufgaben Ihrem Konto zugewiesen werden. In vielen Fällen können Sie diese Probleme durch Ausführen weniger einfacher Schritte beheben.
{:shortdesc}

## Woher weiß ich, welchen Zugriff ich habe?
{: #troubleshoot-myaccess}
{: troubleshoot}

Wenn Sie keine Zugriffsrechte haben, um eine bestimmte Aufgabe auszuführen (z. B. eine Serviceinstanz erstellen und sie einer Ressourcengruppe hinzufügen oder andere Benutzer zum Konto einladen), müssen Sie möglicherweise prüfen, welche Zugriffsrechte Ihnen zugewiesen wurden.

Ich bin mir nicht sicher, auf welcher Zugriffsebene ich Aktionen für ein Konto, dessen Mitglied ich bin, ausführen kann. 
{: tsSymptoms}
   
Möglicherweise wurden Ihnen nicht die korrekten Zugriffsrechte zugewiesen. 
{: tsCauses}

Führen Sie die folgenden Schritte aus, um zu überprüfen, worauf Sie Zugriff haben und auf welcher Zugriffsebene. Wenn Sie einen Zugriff anfordern möchten, wenden Sie sich an den Kontoeigner.

Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie auf der Seite **Benutzer** Ihren Namen aus. Wählen Sie dann abhängig von dem Zugriff, nach dem Sie suchen, die verschiedenen Registerkarten aus:
{: tsResolve}

* Wenn Sie anhand der Ihnen zugewiesenen Zugriffsgruppen ermitteln wollen, welchen Zugriff Sie haben, wählen Sie **Zugriffsgruppen** aus.
* Wenn die Ihnen zugewiesenen IAM-Zugriffsrichtlinien angezeigt werden sollen, wählen Sie **Zugriffsrichtlinien** aus.
* Wenn Ihr Cloud Foundry-Zugriff für alle Organisationen und Bereiche angezeigt werden soll, wählen Sie **Cloud Foundry-Zugriff** aus.


## Wie kann ich Zugriff erhalten, um Benutzer zum Konto einzuladen? 
{: #troubleshoot-invite}
{: troubleshoot}

Wenn Sie nicht der Kontoeigner sind und nicht über den richtigen Zugriff verfügen, können Sie keine Benutzer zu einem Konto einladen. 

Ich kann keine Benutzer zum Konto einladen.
{: tsSymptoms}
   
Möglicherweise wurden Ihnen nicht die korrekten Zugriffsrechte zugewiesen. 
{: tsCauses}

Zum Einladen von Benutzern und Verwalten ausstehender Einladungen müssen Sie entweder ein Kontoeigner, ein Organisationsmanager oder ein Benutzer mit einer IAM-Zugriffsrichtlinie mit der Rolle 'Editor' oder oder höher für den Benutzermanagementservice sein oder Sie müssen über Berechtigungen für die klassische Infrastruktur zum Hinzufügen von Benutzern verfügen.
{: tsResolve}


## Wie kann ich Berechtigungen für die klassische Infrastruktur für andere Benutzer anzeigen?
{: #troubleshoot-classicinfra}
{: troubleshoot}

Da Kontoeigner uneingeschränkten Zugriff auf das Konto haben, werden ihnen die Berechtigungen nicht angezeigt. Einzelpersonen können ihre eigenen Berechtigungen nicht bearbeiten. Daher sehen sie die Berechtigungen auf der Seite der klassischen Infrastruktur, können sie jedoch nicht bearbeiten. Sie müssen über bestimmte Zugriffsrechte verfügen, um Berechtigungen für einen anderen Benutzer im Konto anzuzeigen und zu bearbeiten.

Sie erhalten eine Nachricht, die angibt, dass Sie die Berechtigungen für die klassische Infrastruktur eines anderen Benutzers nicht anzeigen können.
{: tsSymptoms}
   
Möglicherweise wurden Ihnen nicht die korrekten Zugriffsrechte zugewiesen.
{: tsCauses}

Sie müssen den Kontoeigner bitten, Ihnen die Berechtigung für die klassische Infrastruktur **Benutzer verwalten** zu erteilen. Sie müssen jedoch auch ein "Vorfahre" des Benutzers in der Benutzerhierarchie der klassischen Infrastruktur sein, um die Berechtigungen eines anderen Benutzers anzeigen und verwalten zu können.
{: tsResolve}

## Wie kann ich migrierte Berechtigungen für Abrechnungen und Supportfälle in IBM Cloud verwalten?
{: #troubleshoot-migrated-permissions}
{: troubleshoot}

Bei der ursprünglichen Migration von Benutzern und Berechtigungen für die Verwaltung von Abrechnungen und Supportfällen von Ihrem SoftLayer-Konto zu Ihrem verknüpften {{site.data.keyword.Bluemix_notm}}-Konto wurden möglicherweise für einige Benutzer diese Berechtigungen nicht berücksichtigt. Nun sind jedoch allen Zugriffsgruppen mit migrierten Berechtigungen die korrekten IAM-Zugriffsrichtlinien zugewiesen, wodurch sichergestellt wird, dass allen Benutzern die korrekten Zugriffsberechtigungen zugewiesen sind, über die sie auch zuvor verfügten. 

Benutzer verfügen nicht über dieselben Berechtigungen für die Verwaltung von Abrechnungen und Supportfällen in der {{site.data.keyword.Bluemix_notm}}-Konsole, die ihnen zuvor im SoftLayer-Konto zugewiesen waren.
{: tsSymptoms}
   
Bei der ursprünglichen Migration der Benutzer wurden den Zugriffsgruppen mit migrierten Berechtigungen möglicherweise nicht die korrekten Zugriffsrichtlinien zugewiesen.
{: tsCauses}

Ab 20. Mai 2019 sind allen [Zugriffsgruppen mit migrierten Berechtigungen](/docs/iam?topic=iam-migrated_permissions) die korrekten Richtlinien für die Verwaltung von Abrechnungen und Supportfällen zugewiesen. Wenn Sie vor diesem Datum versucht haben, diese Gruppen zu verwenden, haben die Zugriffsgruppen, denen die entsprechenden IAM-Zugriffsrichtlinien nicht zugewiesen waren, möglicherweise zu einer Abweichung beim zugewiesenen Zugriff zwischen den SoftLayer-Berechtigungen und den IAM-Zugriffsberechtigungen geführt. Dieses Problem wurde behoben. Sie können **Verwalten** > **Zugriff (IAM)** aufrufen und dann **Zugriffsgruppen** auswählen, um die Benutzer und Richtlinien zu überprüfen, die den jeweiligen Zugriffsgruppen zugewiesen sind.
{: tsResolve}

