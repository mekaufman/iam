---

copyright:

  years: 2018, 2019

lastupdated: "2019-08-09"

keywords: remove user, delete user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Benutzer aus einem Konto entfernen
{: #remove}

Wenn Sie einen Benutzer aus einem Konto entfernen, kann dieser Benutzer sich nicht mehr an der Konsole anmelden, zu Ihrem Konto wechseln, falls er noch zu einem anderen Konto gehört, oder auf Kontoressourcen zugreifen. Wenn ein Benutzer aus einem Konto entfernt wird, bedeutet das nicht, dass die IBMid für diesen Benutzer gelöscht wird.
{:shortdesc}

Benutzer können nur von solchen Kontoeignern oder Benutzern entfernt werden, die über folgende Zugriffsrechte verfügen:

* Ihnen ist über eine IAM-Richtlinie für den Benutzerverwaltungs- und Kontoverwaltungsservice die Administratorrolle zugewiesen und sie haben die Funktion des Cloud Foundry-Organisationsmanagers, wenn der Benutzer einer Cloud Foundry-Organisation angehört.
* Wenn Ihr Konto die klassische Infrastruktur beinhaltet, muss den Benutzern über eine IAM-Richtlinie für den Benutzerverwaltungs- und Kontoverwaltungsservice die Administratorrolle zugewiesen sein, sie müssen die Funktion des Cloud Foundry-Organisationsmanagers haben, wenn der Benutzer einer Cloud Foundry-Organisation angehört, und sie müssen in der Benutzerhierarchie der klassischen Infrastruktur als Vorfahre gelten, dem für die klassische Infrastruktur die Berechtigung zum Verwalten von Benutzern zugewiesen ist.

Führen Sie die folgenden Schritte aus, um einen Benutzer aus einem Konto zu entfernen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, der entfernt werden soll, im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Benutzer entfernen** aus.

Alle von diesem Benutzer erstellten Ressourcen verbleiben im Konto. Der Benutzer verfügt jedoch nicht mehr über Zugriff zur Bearbeitung dieser Ressourcen. D. h., der Kontoeigner oder ein Administrator dieses Service bzw. dieser Serviceinstanz kann andere Benutzer zur Bearbeitung der Ressourcen zuweisen oder sie aus dem Konto löschen.

Wenn Sie eine Fehlernachricht erhalten, die angibt, dass ein Benutzer der klassischen Infrastruktur nicht entfernt werden kann, stellen Sie sicher, dass allen Nachkommen dieses Benutzers in der Benutzerhierarchie [ein neues übergeordnetes Element zugewiesen ist](/docs/iam?topic=iam-update-parent), dass sie [im Konto inaktiviert sind](/docs/iam?topic=iam-status) oder dass sie gelöscht sind. Wiederholen Sie anschließend den Vorgang.
{: tip}
