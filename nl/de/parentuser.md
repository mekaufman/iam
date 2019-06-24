---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: parent user, change parent user, classic infrastructure hierarchy

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Übergeordneten Benutzer eines Benutzers aktualisieren
{: #update-parent}

Wenn Sie über den entsprechenden Zugriff verfügen, können Sie den übergeordneten Benutzer eines Benutzers aktualisieren. Die Aktualisierung des übergeordneten Benutzers wirkt sich darauf aus, wie die Anzeige anderer Benutzer in dem Konto erfolgt, wenn für die Sichtbarkeit der Benutzerliste die Einstellung 'Eingeschränkte Ansicht' festgelegt ist. Benutzer können nur solche Benutzer sehen, denen sie selbst übergeordnet sind, sowie alle weiteren Benutzer, die von den Nachkommen des übergeordneten Benutzers eingeladen wurden.
{:shortdesc}

Weitere Informatione zu dieser Einstellung finden Sie in [Anzeigezugriffsberechtigung für Benutzer festlegen](/docs/iam?topic=iam-userlistview#userlistview).

Wenn Sie über die folgenden Zugriffsrechte verfügen, können Sie den übergeordneten Benutzer für einen anderen Benutzer aktualisieren:

* Ihnen ist über eine IAM-Richtlinie die Rolle des Editors oder höher für den Benutzermanagementservice zugewiesen
* Sie gelten in der Hierarchie der klassischen Infrastruktur als 'Vorfahre' eines Benutzers und Ihnen ist für die klassische Infrastruktur die Berechtigung zum Verwalten von Benutzern zugewiesen


Führen Sie die folgenden Schritte aus, um den übergeordneten Benutzer eines Benutzers zu aktualisieren:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.  
2. Wählen Sie einen Benutzername aus der Liste aus.
3. Wählen Sie auf der Seite 'Benutzerdetails' im Menü **Übergeordnet** einen neuen übergeordneten Benutzer aus.
4. Klicken Sie auf **Anwenden**.
