---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: classic infrastructure access, VPN subnet access, classic infrastructure permissions, device access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Zugriff auf die klassische Infrastruktur verwalten
{: #mngclassicinfra}

Sie können jederzeit die Berechtigungen für Services der klassischen Infrastruktur aktualisieren oder Geräte- und VPN-Teilnetzzugriff für einen Benutzer hinzufügen. Wenn Sie auf die Berechtigungen für die klassische Infrastruktur zugreifen möchten, rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie **Benutzer** aus. Wählen Sie dann den Namen des Benutzers aus, dessen Zugriffsberechtigungen aktualisiert werden sollen, und klicken Sie auf **Klassische Infrastruktur**.
{:shortdesc}

Ihnen muss die Berechtigung der klassischen Infrastruktur zum Verwalten von Benutzern zugewiesen sein und Sie müssen in der Benutzerhierarchie der klassischen Infrastruktur als 'Vorfahre' des Benutzers gelten. Da Kontoeigner uneingeschränkten Zugriff auf das Konto haben, werden ihnen die Berechtigungen auf der Seite nicht angezeigt. Einzelpersonen können ihre eigenen Berechtigungen nicht bearbeiten. Daher werden ihnen auf der Seite ebenfalls keine Berechtigungen angezeigt.
{: note}

  1. Wählen Sie zum Aktualisieren der Berechtigungen für den Benutzer die Option **Berechtigungen** aus. Es stehen die folgenden vier Typen von Berechtigungen zur Auswahl: 'Konto', 'Geräte', 'Netz' und 'Services'. Wählen Sie einzeln aus jeder Kategorie Berechtigungen aus oder verwenden Sie eine Berechtigungssetoption, um eine Massenzuweisung des Zugriffs durchzuführen.

    Die Berechtigungen für die Kontoverwaltung und den Support, die Sie Benutzern zuvor in Ihrem Konto zugewiesen haben, werden nun von Berechtigungen der klassischen Infrastruktur zu migrierten IAM-Zugriffsgruppen migriert. Weitere Informationen hierzu enthält der Abschnitt [Migrierte Berechtigungen der klassischen Infrastruktur](/docs/iam?topic=iam-migrated_permissions).
    {: tip}

  2. Wenn Sie einem Benutzer Gerätezugriff erteilen wollen, wählen Sie **Geräte** aus und weisen Sie nach Bedarf den Zugriff für bestimmte Geräte und Gerätetypen zu.

    Die Zuweisung von Zugriff für Geräte erfolgt, nachdem der Benutzer zu dem Konto eingeladen wurde. Die Geräteberechtigungen gelten für die jeweiligen Geräte, die dem Benutzer zugewiesen sind. Sie können bestimmte Geräte aus der Liste auswählen oder Sie können Zugriff nach Gerätetyp zuweisen. Wenn Sie Zugriff nach Gerätetyp zuweisen, ist es sinnvoll, die Option **Späteren Zugriff aktivieren** zu verwenden. Damit ist sichergestellt, dass dem Benutzer jedes Mal, wenn neue Geräte eines bestimmten Typs hinzugefügt werden, automatisch Zugriff auf diese Geräte zugewiesen wird.

  3. Wenn Sie den Zugriff eines Benutzers auf VPN-Teilnetze aktualisieren wollen, wählen Sie **VPN-Teilnetze** aus.

    Verwenden Sie die Option **Automatische Zuweisung**, um festzulegen, wie der Benutzer auf der Grundlage seines Gerätezugriffs Zugriff auf VPN-Teilnetze erhält. Wenn diese Option mit 'Ein' aktiviert ist, wird dem Benutzer für die Geräte, auf die er bereits Zugriff hat, automatisch Zugriff auf alle Teilnetze zugewiesen. Wenn Sie Teilnetze lieber manuell aus der Liste auswählen wollen, können Sie diese Option mit 'Aus' inaktivieren.
    {: tip}

    Damit der Zugriff auf VPN-Teilnetze bereitgestellt werden kann, muss dem Benutzer bereits Zugriff auf ein oder mehrere Geräte zugewiesen sein. Wenn der Benutzer über keinerlei Zugriff auf Geräte verfügt, stehen keine Teilnetze für die Auswahl zur Verfügung. Mithilfe der Option **VPN-Typ** können definieren, auf welchen Typ von VPN-Teilnetzen der Benutzer Zugriff erhalten soll. Wenn Sie **Ohne** auswählen, kann kein VPN-Zugriff zugewiesen werden.

    Die Option 'PPTP' ist veraltet. Wenn bei Ihnen diese Option festgelegt ist und Sie sie abwählen, ist sie daher nicht mehr verfügbar.
    {: deprecated}
