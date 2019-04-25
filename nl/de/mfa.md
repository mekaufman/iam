---

copyright:

  years: 2018, 2019
lastupdated: "2019-03-05"

keywords: MFA, multifactor authentication, IBMid MFA, two-factor authentication, account MFA, time-based one-time passcode, TOTP

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# MFA für Benutzer in Ihrem Konto verlangen
{: #enablemfa}

Als Eigner eines {{site.data.keyword.Bluemix}}-Kontos oder Administrator des Abrechnungsservice können Sie festlegen, dass die Mehrfaktorauthentifizierung (MFA) für jeden Benutzer im Konto oder nur für Benutzer ohne föderierte IDs, die kein SSO verwenden, erforderlich ist. Alle Benutzer mit einer IBMid verwenden eine MFA-Methode mit zeitbasiertem einmaligem Konto (Time-Based One-Time Passcode, TOTP). Alle Benutzer mit einem anderen ID-Typ müssen separat für die Verwendung der TOTP-Methode, der Methode mit Sicherheitsfragen oder der externe Authentifizierungsmethode aktiviert werden.  
{:shortdesc}

## Vorbereitende Schritte
{: #considerations}

Berücksichtigen Sie die folgenden Aspekte, bevor Sie die Mehrfaktorauthentifizierung mit einer IBMid (IBMid MFA) für Ihr Konto aktivieren, damit Sie genau wissen, welche Auswirkungen sie auf alle Benutzer in Ihrem Konto hat:

* Wenn Sie MFA für Ihr Konto aktivieren, müssen alle Benutzer bei der nächsten Anmeldung den Prozess der Mehrfaktorauthentifizierung (MFA) durchführen.
* API-Schlüssel für Benutzer und Service-IDs funktionieren weiterhin, nachdem die MFA aktiviert wurde.
* Wenn die Cloud Foundry-Anmeldung über die Befehlszeilenschnittstelle oder die Benutzerschnittstelle erfolgen soll, müssen API-Schlüssel oder Single Sign-on (SSO) verwendet werden, nachdem die MFA für das Konto aktiviert wurde. 
* Die MFA für Ihr Konto bezieht sich auf die Anmeldung eines Benutzers, nicht aber auf API-Aufrufe. Wenn ein Benutzer über die Berechtigung zum Durchführen von API-Aufrufen für Ressourcen in Ihrem Konto verfügt, kann der Benutzer derartige Aufrufe ohne Ausführen der MFA tätigen. Wenn der Benutzer zu anderen Konten gehört, kann er API-Aufrufe für Ressourcen in Ihrem Konto durchführen, indem er den API-Schlüssel eines Kontos verwendet, für das keine MFA erforderlich war.
* Wenn Sie für Ihr Konto MFA als erforderlich angeben und Benutzer in Ihrem Konto vorhanden sind, die nicht über eine IBMid verfügen, müssen Sie für solche Benutzer in der {{site.data.keyword.Bluemix_notm}}-Konsole auf der Seite 'Benutzerdetails' eine der anderen MFA-Optionen aktivieren. Weitere Informationen finden Sie in [Arten der Mehrfaktorauthentifizierung](/docs/iam?topic=iam-types#types).
* Planen Sie eine Kommunikations- und Supportstrategie für Benutzer in Ihrem Konto.
  * Wählen Sie ein Datum und eine Uhrzeit mit möglichst geringer Auswirkung auf Ihr Geschäft für die Aktivierung von MFA aus.
  * Informieren Sie Ihre Kontobenutzer nach der Aktivierung von MFA darüber, [welche Schritte sie ausführen müssen](/docs/iam?topic=iam-enablemfa#setupapp).

Wenn die Kontoeinstellung für die Mehrfaktorauthentifizierung aktiviert ist, werden alle IBMid-Benutzer in Ihrem Konto bei der Anmeldung zur Mehrfaktorauthentifizierung (MFA) mit einer IBMid aufgefordert. Wenn Sie andere MFA-Methoden für IBMid-Benutzer in Ihrem Konto eingerichtet haben, werden diese nicht mehr zu diesen MFA-Methoden aufgefordert.
{: tip}

## Mehrfaktorauthentifizierung (MFA) für alle Benutzer in Ihrem Konto aktivieren
{: #enabling}

Um die MFA zu aktivieren, müssen Sie der Kontoeigner oder ein Administrator für den Abrechnungskontoverwaltungsservice sein. Das Aktivieren der MFA wirkt sich nicht auf Benutzer aus, die bereits angemeldet sind, da die Durchsetzung der Mehrfaktorauthentifizierung nur bei neuen Anmeldungen in Kraft tritt. Informieren Sie die Kontobenutzer unbedingt darüber, dass MFA aktiviert ist, und beschreiben Sie die Auswirkungen dieser Änderung auf ihre nächste Anmeldung.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie anschließend **Einstellungen** aus.
2. Wählen Sie **Aktualisieren** für die Kontoanmeldungseinstellung aus.
3. Wählen Sie **Keine**, **Nur nicht föderierte Benutzer** oder **Alle Benutzer** aus, abhängig davon, welcher Authentifizierungstyp erforderlich sein soll. 
4. Wählen Sie das Kontrollkästchen aus, um zu bestätigen, dass Sie die Auswirkungen der erforderlichen MFA für Benutzer in Ihrem Konto kennen, wenn Sie die Option 'Nur nicht föderierte Benutzer' auswählen.
5. Klicken Sie auf **Speichern**.

## Zeitbasierten einmaligen Kenncode (TOTP) einrichten
{: #setupapp}

Nachdem Sie MFA für Ihr Konto aktiviert haben, müssen Sie bei der nächsten Anmeldung mithilfe einer Authentifikator-App den einmaligen Kenncode festlegen. Alle Benutzer in Ihrem Konto müssen bei ihrer nächsten Anmeldung ebenfalls den einmaligen Kenncode festlegen.

Führen Sie die folgenden Schritte aus, um Ihren einmaligen Kenncode mit einer Authentifikator-App erstmalig festzulegen:

1. Melden Sie sich mit Ihrer IBMid und Ihrem Kennwort an.

  Es kann bis zu fünf Minuten dauern, bis Sie sich mit der MFA erneut anmelden können.
  {: note}

2. Wählen Sie **Verifizieren** im Bildschirm **Verifizierung ist erforderlich** aus, um MFA mit einer Authentifikator-App einzurichten.
3. Wählen Sie **Authentifikator-App konfigurieren** aus, damit ein einmaliger Code an Ihre E-Mail-Adresse gesendet wird, den Sie für die weitere Einrichtung der Authentifikator-App benötigen.
4. Wählen Sie **Verifizieren** aus.
5. Scannen Sie den Barcode mit Ihrer App oder klicken Sie auf **Barcode kann nicht gescannt werden?**, um einen bereitgestellten Schlüssel einzugeben.
6. Klicken Sie auf **Weiter**, um Ihren Code einzugeben.
7. Geben Sie Ihren Code ein und wählen Sie **Verifizieren** aus.

Wenn eine Fehlernachricht mit dem Inhalt angezeigt wird, dass Sie die Authentifizierung bereits eingerichtet haben, Ihr Verifizierungscode jedoch nicht funktioniert oder Sie über keinen Verifizierungscode für die Eingabe verfügen, so müssen Sie sich an den [Help-Desk](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg "Symbol für externen Link") wenden, um Ihre MFA-Registrierung zurückzusetzen.
{: note}
{: #mfahelp}

## Erforderliche Mehrfaktorauthentifizierung (MFA) für alle Benutzer in Ihrem Konto inaktivieren
{: #disablemfa}

Um die MFA zu inaktivieren, müssen Sie der Kontoeigner oder ein Administrator für den Abrechnungskontoverwaltungsservice sein. Das Inaktivieren der MFA wirkt sich nicht auf Benutzer aus, die bereits angemeldet sind. Die Aktion wird bei allen neuen Anmeldungen wirksam.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie anschließend **Einstellungen** aus.
2. Wählen Sie **Bearbeiten** für die Kontoanmeldungseinstellung aus.
3. Wählen Sie **Keine** aus.
4. Klicken Sie auf **Speichern**.

