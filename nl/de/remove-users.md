---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: remove user, delete user, user management

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Benutzer entfernen
{: #remove}

Wenn Sie einen Benutzer aus dem Konto entfernen, kann dieser Benutzer sich nicht mehr an der Konsole anmelden, zu Ihrem Konto wechseln, sofern er noch einem anderen Konto angehört, oder auf Kontoressourcen zugreifen.
{:shortdesc}

Benutzer können nur von solchen Kontoeignern oder Benutzern entfernt werden, die über folgende Zugriffsrechte verfügen:

* Ihnen ist über eine IAM-Richtlinie für den Benutzerverwaltungs- und Kontoverwaltungsservice die Administratorrolle zugewiesen und sie haben die Funktion des Cloud Foundry-Organisationsmanagers, wenn der Benutzer einer Cloud Foundry-Organisation angehört.
* Wenn Ihr Konto die klassische Infrastruktur beinhaltet, muss den Benutzern über eine IAM-Richtlinie für den Benutzerverwaltungs- und Kontoverwaltungsservice die Administratorrolle zugewiesen sein, sie müssen die Funktion des Cloud Foundry-Organisationsmanagers haben, wenn der Benutzer einer Cloud Foundry-Organisation angehört, und sie müssen in der Benutzerhierarchie der klassischen Infrastruktur als Vorfahre gelten, dem für die klassische Infrastruktur die Berechtigung zum Verwalten von Benutzern zugewiesen ist.

Führen Sie die folgenden Schritte aus, um einen Benutzer aus einem Konto zu entfernen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, der entfernt werden soll, im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Benutzer entfernen** aus.
