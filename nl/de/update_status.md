---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-28"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}

# Status eines Benutzers aktualisieren
{: #status}

Der einem Benutzer zugewiesene Status richtet sich danach, ob der Benutzer die Einladung zum Beitritt zu dem Konto angenommen hat, er ein Benutzer mit dem Status 'Nur VPN' ist oder der Benutzeradministrator den Benutzer als inaktivierten Benutzer der klassischen Infrastruktur festgelegt hat.
{:shortdesc}

Wenn Sie über die folgenden Zugriffsrechte verfügen, können Sie den Status anderer Benutzer aktualisieren:

  * Ihnen ist über eine IAM-Richtlinie die Rolle des Editors oder höher für den Benutzermanagementservice zugewiesen
  * Sie gelten in der Hierarchie der klassischen Infrastruktur als 'Vorfahre' eines Benutzers und Ihnen ist für die klassische Infrastruktur die Berechtigung zum Verwalten von Benutzern zugewiesen

Weitere Informationen zu den Typen von Benutzerstatus enthält der Abschnitt [Benutzerstatus](/docs/iam?topic=iam-user_status#user_status).

## Optionen zum Ändern des Status eines Benutzers
{: #status_options}

Zum Aktualisieren des Status eines Benutzers stehen die folgenden Optionen zur Auswahl:

<dl>
<dt>Aktiv</dt>
<dd>Der Benutzer besitzt auf der Grundlage der ihm zugewiesenen Zugriffsrichtlinien und Berechtigungen für die klassische Infrastruktur uneingeschränkten Zugriff auf die {{site.data.keyword.cloud_notm}}-Konsole.</dd>
<dt>Inaktivierte klassische Infrastruktur</dt>
<dd>Der Benutzer kann nicht mehr auf Ressourcen der klassischen Infrastruktur zugreifen, er kann sich jedoch weiterhin an der Konsole anmelden und auf Ressourcen der Plattform zugreifen.</dd>
<dt>Nur VPN</dt>
<dd>Der Benutzer kann sich nicht an der Konsole anmelden, er hat jedoch Zugriff auf alle Geräte und VPN-Teilnetze, die Sie für die klassische Infrastruktur zuweisen, indem er sich direkt bei der Appliance anmeldet.</dd>
</dl>

Wenn Sie einen Benutzer mit dem Status 'Nur VPN' zum Status 'Aktiv' aktualisieren, muss dem Benutzer das entsprechende Kennwort bekannt sein, um sich an der Konsole anmelden zu können. In den meisten Fällen handelt es sich hierbei um das SoftLayer-ID-Kennwort, das möglicherweise zurückgesetzt werden muss, um verwendet werden zu können. In seltenen Fällen, in denen der Benutzer bereits über eine IBMid verfügt, muss sich der Benutzer mit der IBMid und dem Kennwort anmelden.
{: note}

## Status eines Benutzers aktualisieren
{: #update_user_status}

Führen Sie die folgenden Schritte aus, um den Status eines Benutzers zu ändern:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus. 
2. Wählen Sie einen Benutzer aus der Liste aus.
3. Wählen Sie auf der Seite 'Benutzerdetails' im Menü **Benutzerstatus** eine Option aus.  
4. Klicken Sie auf **Anwenden**.


