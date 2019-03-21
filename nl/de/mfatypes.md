---

copyright:

  years: 2018,2019
lastupdated: "2019-03-05"

keywords: MFA, multifactor authentication, two-factor authentication

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Typen der Mehrfaktorauthentifizierung
{: #types}

Durch die Mehrfaktorauthentifizierung (MFA) wird eine zusätzliche Sicherheitsebene zu Ihrem Konto hinzugefügt, denn alle Benutzer müssen sich neben der Angabe einer ID mit Kennwort mit einer zusätzlichen Authentifizierungsmethode authentifizieren. Dieser Mechanismus wird gängigerweise auch als Zwei-Faktor-Authentifizierung (2FA) bezeichnet.
{:shortdesc}

Für Ihr Konto können die folgenden zwei Typen von MFA-Optionen aktiviert werden:

<dl>
<dt>ID-basierte MFA</dt>
<dd>Eine Option, die von einem Kontoeigner oder einem Administrator für das Abrechnungssystem in einem der Konten aktiviert wird, denen Sie als Mitglied angehören. Dieser Typ von Mehrfaktorauthentifizierung ist Ihrer IBMid zugeordnet und sorgt für Ihre Authentifizierung bei allen Konten, denen Sie als Mitglied angehören, sodass Sie sich nur einmal authentifizieren müssen.</dd>
<dt>Kontobasierte Optionen</dt>
<dd>Optionen wie Sicherheitsfragen, die Verwendung eines zeitbasierten einmaligen Kenncodes und Optionen der externen Authentifizierung wie Symantec-Authentifizierung und telefongestützte Authentifizierung. Diese Typen von MFA sind für jedes Konto spezifisch. Wenn für jedes Konto, dem Sie angehören, ein anderer MFA-Typ eingerichtet ist, bedeutet das, dass Sie sich bei jedem Wechsel des Kontos auf eine andere Art authentifizieren müssen. Diese traditionellen MFA-Optionen sind nur in Verbindung mit früheren Konten der klassischen Infrastruktur verfügbar.</dd>
</dl>

IBMid MFA erfüllt die Authentifizierungsanforderung. Daher werden Sie nicht zu anderen Typen der MFA aufgefordert, selbst wenn diese aktiviert sind. Wenn also für ein Konto, dem Sie als Mitglied angehören, diese Option aktiviert wird, ist dies der einzige MFA-Typ, für den Sie bei der Anmeldung zur Eingabe aufgefordert werden. Wenn Sie ein neuer Benutzer sind, sollten Sie die Option der ID-basierten Mehrfaktorauthentifizierung (MFA) mit IBMid verwenden, um sicherzustellen, dass Ihre Anmeldung einfach und sicher ist.
{: tip}

## Option der ID-basierten MFA
{: #id-based}

Die Mehrfaktorauthentifizierung mit IBMid (IBMid MFA) für ein Konto macht bei der Anmeldung zusätzlich zur standardmäßigen IBMid mit dem zugehörigen Kennwort die Eingabe eines zeitbasierten einmaligen Kenncodes erforderlich. Dieser MFA-Typ wird vom Kontoeigner oder einem Administrator für den Abrechnungsservice auf Kontoebene aktiviert. Wenn dieses Feature aktiviert ist, müssen Sie den zusätzlichen Sicherheitsstandard bei der Anmeldung verwenden. Alle Benutzer, die zu Ihrem Konto hinzugefügt werden, sind ebenfalls zu seiner Verwendung verpflichtet. Dieser MFA-Typ gilt für alle Kontoressourcen. Sie können diesen Typ auf der Seite **Verwalten** > **Zugriff (IAM)** > **Einstellungen** in der {{site.data.keyword.Bluemix}}-Konsole nur aktivieren oder inaktivieren, wenn Sie der Kontoeigner oder ein Administrator für den Abrechnungsservice sind. 

Einer der Vorteile der Mehrfaktorauthentifizierung mit IBMid (IBMid MFA) besteht darin, dass sie kostenlos ist und an Ihre ID und nicht einfach nur an das jeweilige Konto gebunden ist, dem Sie angehören. Wenn Sie zahlreichen Konten als Mitglied angehören, müssen Sie sich nur einmal authentifizieren, wenn Sie sich an der Konsole anmelden. Weitere Informationen zur Mehrfaktorauthentifizierung mit IBMid (IBMid MFA), zu den Aspekten, die Sie überprüfen müssen, bevor Sie IBMid MFA für Ihr Konto als erforderlich festlegen, und zur Vorgehensweise zum Einrichten der IBMid MFA für sich selbst finden Sie im Abschnitt [MFA für Benutzer in Ihrem Konto verlangen](/docs/iam?topic=iam-enablemfa#enablemfa).

## Optionen der kontobasierten MFA
{: #account-based}

Ein Kontoadministrator muss beliebige der folgenden MFA-Optionen so aktivieren, dass diese von einem Benutzer des Kontos konfiguriert und verwendet werden können. Dieser Typ von Mehrfaktorauthentifizierung (MFA) ist an das aktuelle Konto eines Benutzers gebunden. Wenn ein Administrator für jedes Konto, dem ein Benutzer als Mitglied angehört, eine andere dieser MFA-Optionen aktiviert, wird der Benutzer daher bei jedem Wechsel des Kontos dazu aufgefordert, sich auf eine andere Art zu authentifizieren.

Wenn für ein Konto die Mehrfaktorauthentifizierung (MFA) mit IBMid für alle Benutzer in dem Konto erforderlich ist, dann setzt diese MFA-Methode mit IBMid alle anderen MFA-Optionen außer Kraft, die im Konto eines Endbenutzers aktiviert und eingerichtet sind. Selbst wenn für einen Benutzer andere MFA-Optionen festgelegt sind, wie etwa in der nachfolgenden Konfiguration, wird der Benutzer bei der Anmeldung nicht zu ihrer Durchführung aufgefordert.

Die folgenden traditionellen MFA-Optionen sind nur in Verbindung mit früheren Konten der klassischen Infrastruktur verfügbar.

<dl>
<dt>Zeitbasierte einmalige Authentifizierung mit Kenncode (TOTP)</dt>
<dd>Die zeitbasierte einmalige Authentifizierung mit Kenncode (TOTP) kann mithilfe einer Authentifizierungsapp eingerichtet werden. Ein Kontoeigner oder -administrator kann diese Einstellung nur dann für einen Benutzer auf der Seite 'Benutzerdetails' aktivieren, wenn der Benutzer die Authentifizierung auf der Seite 'Anmeldeeinstellungen' für das Profil konfiguriert hat. Wenn diese Einstellung für einen Benutzer aktiviert ist, wird er bei der Anmeldung zur Eingabe des Kenncodes aufgefordert. Benutzer, für die die Einstellung 'Benutzerverwaltete Anmeldung' aktiviert ist und die daher Zugriff auf die Verwaltung ihrer eigenen Anmeldeeinstellungen haben, können diese Art der Authentifizierung aktivieren bzw. inaktivieren.</dd>
<dt>Sicherheitsfragen</dt>
<dd>Benutzer können Antworten auf die Sicherheitsfragen konfigurieren, die auf der Seite 'Anmeldeeinstellungen' für das Profil zur Verfügung stehen. Der Benutzer muss die Sicherheitsfragen mit den zugehörigen Antworten einrichten, bevor ein Kontoeigner oder -administrator diese Einstellung auf der Seite 'Benutzerdetails' aktivieren kann. Benutzer, für die die Einstellung 'Benutzerverwaltete Anmeldung' aktiviert ist und die daher Zugriff auf die Verwaltung ihrer eigenen Anmeldeeinstellungen haben, können diese Art der Authentifizierung aktivieren bzw. inaktivieren. </dd>
<dt>Externe Authentifizierung</dt>
<dd>Es gibt zwei externe Authentifizierungsoptionen von Drittanbietern, die für eine monatliche Gebühr bestellt werden können: die Symantec-Authentifizierung und die telefongestützte Authentifizierung. Diese Optionen muss ein Kontoeigner oder -administrator für den Benutzer bestellen und auf der Seite 'Benutzerdetails' für den Benutzer zur Verwendung aktivieren. Für Symantec muss sich der Administrator an den Benutzer wenden, um die Berechtigungsnachweis-ID dieses Benutzers zu erhalten und die Bestellung abschließen zu können. Zur Einrichtung der telefongestützten Authentifizierung muss zuerst der Administrator die entsprechende Bestellung aufgeben. Danach muss der Benutzer diese Art der Authentifizierung auf seiner Seite 'Benutzerdetails' einrichten, bevor der Administrator sie schließlich für die Verwendung aktivieren kann. Benutzer, für die die Einstellung 'Benutzerverwaltete Anmeldung' aktiviert ist und die daher Zugriff auf die Verwaltung ihrer eigenen Anmeldeeinstellungen haben, können diese Art der Authentifizierung aktivieren bzw. inaktivieren.</dd>
</dl>

Weitere Informationen zum Einrichten von MFA-Optionen enthält der Abschnitt [Anmeldesicherheit einrichten](/docs/account?topic=account-login-settings#login-settings). Wenn Sie ein Kontoeigner oder ein Administrator sind, der die Anmeldeeinstellungen für andere Benutzer verwaltet oder wenn Sie befähigt sind, Ihre eigenen Anmeldeeinstellungen zu verwalten, lesen Sie die Informationen im Abschnitt [Anmeldeeinstellungen eines Benutzers verwalten](/docs/iam?topic=iam-loginsettings#loginsettings).
