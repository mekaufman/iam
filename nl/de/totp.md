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
{:note: .note}

# Mehrfaktorauthentifizierung (MFA) mit einmaligem Kenncode für einen Benutzer aktivieren
{: #totp}

Als Administrator mit dem entsprechenden Zugriff können Sie die Option, bei der ein Benutzer bei der Anmeldung zur Eingabe eines zeitbasierten einmaligen Kenncodes (TOTP) aufgefordert wird, in der {{site.data.keyword.Bluemix}}-Konsole auf der Seite 'Benutzerdetails' aktivieren. Dieser Typ von Mehrfaktorauthentifizierung (MFA) ist im Gegensatz zur ID-basierten Mehrfaktorauthentifizierung nur für das Konto erforderlich, für das die Einstellung aktiviert ist. Weitere Informationen finden Sie in [Arten der Mehrfaktorauthentifizierung](/docs/iam?topic=iam-types#types).
{:shortdesc}

Wenn Sie über eines der folgenden Zugriffsrechte verfügen, können Sie diese Einstellung für andere Benutzer in Ihrem Konto aktualisieren:

* Rolle 'Editor' oder höher für den Benutzermanagementservice
* Sie gelten in der Hierarchie der klassischen Infrastruktur als 'Vorfahre' eines Benutzers und Ihnen ist für die klassische Infrastruktur die Berechtigung zum Verwalten von Benutzern zugewiesen

Führen Sie die folgenden Schritte aus, um die Einstellung zur Aufforderung eines Benutzers bei der Anmeldung zur Durchführung der TOTP-MFA zu aktivieren.

Um diese MFA-Option für einen Benutzer zu aktivieren, muss der Benutzer zuerst auf der Seite 'Anmeldeeinstellungen' für das Profil die [TOTP einrichten](/docs/account?topic=account-MFA#MFA).
{: note}

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie einen Benutzer aus der Liste aus.
3. Legen Sie auf der Seite **Benutzerdetails** im Abschnitt **Anmeldung des Benutzers verwalten** für die Option der **Mehrfaktorauthentifizierung mit zeitbasiertem einmaligem Kenncode (TOTP-MFA)** den Wert 'Ein' fest.

Diese Einstellung können Sie für sich selbst verwalten, wenn auf Ihrer Seite für 'Benutzerdetails' die Einstellung für die benutzerverwaltete Anmeldung aktiviert ist.
{: tip}

