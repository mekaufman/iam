---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Bestimmte IP-Adressen für einen Benutzer zulassen
{: #ips}

Standardmäßig können alle IP-Adressen zum Anmelden an der {{site.data.keyword.cloud}}-Konsole und zum Zugreifen auf APIs der klassischen Infrastruktur verwendet werden. Sie können jedoch angeben, welche IP-Adressen Zugriff erhalten sollen, sodass nur die als zulässig angegebenen Adressen verwendet werden können und die Verwendung aller übrigen eingeschränkt ist.
{:shortdesc}

Wenn Sie eingeschränkte IP-Adressen verwenden, ist der Zugriff auf die klassische Infrastruktur über [https://cloud.ibm.com](https://cloud.ibm.com){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") nicht möglich. Stattdessen müssen Sie die URL-Adresse [https://control.softlayer.com](https://control.softlayer.com){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") verwenden.
{: important}

Wenn Sie über die folgenden Zugriffsrechte verfügen, können Sie die eingeschränkten IP-Adressen für einen Benutzer aktualisieren:

  * Ihnen ist über eine IAM-Richtlinie die Rolle des Editors oder höher für den Benutzermanagementservice zugewiesen
  * Sie gelten in der Hierarchie der klassischen Infrastruktur als 'Vorfahre' eines Benutzers und Ihnen ist für die klassische Infrastruktur die Berechtigung zum Verwalten von Benutzern zugewiesen
  
Diese Einstellung können Sie für sich selbst verwalten, wenn auf Ihrer Seite für 'Benutzerdetails' die Einstellung für die benutzerverwaltete Anmeldung aktiviert ist.
{: tip}

Führen Sie die folgenden Schritte aus, um einen Benutzer auf die Verwendung bestimmter IP-Adressen zu beschränken: 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus. 
2. Wählen Sie einen Benutzer aus der Liste aus. 
3. Gehen Sie auf der Seite 'Benutzerdetails' zum Abschnitt **IP-Adresseinschränkungen**. 
4. Geben Sie für **Cloudplattform** die IP-Adressen ein. Die aufgelisteten IP-Adressen sind die einzigen, von denen aus sich dieser Benutzer bei {{site.data.keyword.Bluemix}} anmelden kann.
5. Geben Sie für **Klassische Infrastruktur** die IP-Adressen ein. Die aufgelisteten IP-Adressen sind die einzigen, von denen aus der Benutzer eine API der klassischen Infrastruktur aufrufen kann. 
  
  Um eine IP-Adresse für die klassische Infrastruktur eingeben zu können, muss der Benutzer bereits einen API-Schlüssel für die klassische Infrastruktur erstellt haben.
  {: note}
 


