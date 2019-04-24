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
{:important: .important}

# Anmeldeeinstellungen eines Benutzers verwalten 
{: #loginsettings}

Ein Kontoeigner oder ein Benutzer, der über den entsprechenden Zugriff verfügt, kann die Anmeldeeinstellungen für einen Benutzer verwalten und dadurch zum Beispiel Optionen für die externe Authentifizierung bestellen, einen einmaligen Kenncode zur Verwendung bei der Anmeldung aktivieren, die Verwendung von Sicherheitsfragen bei der Anmeldung aktivieren und einen Zeitraum für die Kennwortgültigkeit festlegen.
{:shortdesc}

Führen Sie die folgenden Schritte aus, um die Anmeldeeinstellungen für einen bestimmten Benutzer zu verwalten:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus. 
2. Wählen Sie in der Liste einen Benutzer aus und klicken Sie auf **Benutzerdetails**. 
3. Im Abschnitt **Anmeldung des Benutzers verwalten** können Sie die folgenden Optionen für den ausgewählten Benutzer aktivieren bzw. inaktivieren: 
    
    * Mehrfaktorauthentifizierung mit zeitbasiertem einmaligem Kenncode (TOTP-MFA): Aktivieren Sie diese Option, um zu ermöglichen, dass der Benutzer bei der Anmeldung zur Eingabe des einmaligen Kenncodes aufgefordert wird. Benutzer müssen ihre TOTP-MFA auf der Seite 'Anmeldeeinstellungen' einrichten. Weitere Informationen hierzu enthält der Abschnitt [Mehrfaktorauthentifizierung (MFA) mit einmaligem Kenncode für einen Benutzer aktivieren](/docs/iam?topic=iam-totp#totp).
    
    * Externe Authentifizierung bestellen: Wählen Sie diese Option aus, um die Symantec-Authentifizierung oder die telefongestützte Authentifizierung für eine monatliche Gebühr zu bestellen. Es kann immer nur jeweils eine Option bestellt und verwendet werden. Weitere Informationen hierzu finden Sie in [Externe Authentifizierung mit Mehrfaktorauthentifizierung (MFA) für einen Benutzer bestellen](/docs/iam?topic=iam-external#external).

        * Telefongestützte Authentifizierung: Der Benutzer kann diese Option verwenden, nachdem der Kontoeigner sie bestellt hat, indem er die Konfiguration verwendet, die auf der Seite 'Benutzerdetails' festgelegt wurde. 
        * Symantec-Authentifizierung: Der Benutzer kann diese Option verwenden, nachdem der Kontoeigner sie bestellt hat. Damit ein Administrator diese Option bestellen kann, muss der Benutzer zuerst seine Berechtigungsnachweis-ID angeben.

    * MFA-Sicherheitsfragen bei Anmeldung: Aktivieren Sie diese Option, um festzulegen, dass ein Benutzer zur Angabe der von ihm auf der Seite 'Anmeldeeinstellungen' festgelegten Sicherheitsfragen mit den zugehörigen Antworten aufgefordert werden muss. Diese Option kann erst aktiviert werden, wenn der Benutzer seine Sicherheitsfragen bereits festgelegt hat. Weitere Informationen hierzu finden Sie in [MFA-Sicherheitsfragen für einen Benutzer aktivieren](/docs/iam?topic=iam-questions#questions).

    * Benutzerverwaltete Anmeldung: Aktivieren Sie diese Option, um dem Benutzer die Festlegung des Ablaufs der Kennwortgültigkeit, die Aktivierung von Sicherheitsfragen für die Anmeldung und die Angabe zulässiger IP-Adressen für die Anmeldung bei {{site.data.keyword.cloud_notm}} und für APIs der klassischen Infrastruktur zu ermöglichen. 

    * Kennwortablauf: Legen Sie den Ablauf der Gültigkeit durch Auswahl einer Option aus der Liste fest. Diese Option ist nur für Benutzer mit einer SoftLayer-ID verfügbar. Wenn der Benutzer die eigenen Anmeldeeinstellungen verwalten kann, so kann er den Ablauf der Gültigkeit auf der Seite für seine Anmeldeeinstellungen festlegen. Nur Benutzer mit den folgenden Berechtigungen können den Ablauf der Kennwortgültigkeit für einen Benutzer festlegen:
        
        * Alle Benutzer, denen über eine IAM-Richtlinie die Rolle des Editors oder höher für den Benutzermanagementservice zugewiesen ist.
        * Alle Benutzer, für die von ihrem Administrator auf der Seite 'Benutzerdetails' die Option der benutzerverwalteten Anmeldung aktiviert wurde.
        * Alle Vorfahren des Benutzers in der Hierarchie der klassischen Infrastruktur mit zugewiesener Berechtigung für die klassische Infrastruktur zum Verwalten von Benutzern.

Es sollte immer nur jeweils eine MFA-Option aktiviert sein. Wenn auch nur für ein Konto, bei dem der Benutzer ein Mitglied ist, die Mehrfaktorauthentifizierung mit IBMid (IBMid MFA) als erforderlich festgelegt ist, so setzt diese alle übrigen aktivierten Mehrfaktorauthentifizierungen außer Kraft und der Benutzer wird zu keinem anderen Typ von MFA aufgefordert.
{: important}



