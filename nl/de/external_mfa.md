---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: MFA, multifactor authentication, external authentication, order authentication, Symantec, phone-based authentication, cancel authentication order

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Externe Authentifizierung mit Mehrfaktorauthentifizierung (MFA) für einen Benutzer bestellen
{: #external}

Als Administrator mit den entsprechenden Zugriffsberechtigungen können Sie die externe Authentifizierung bestellen und die Option der Mehrfaktorauthentifizierung (MFA) für die Anmeldung eines Benutzers aktivieren. Für die Optionen der externen Authentifizierung wird Ihnen eine monatliche Gebühr berechnet. Dieser Typ von Mehrfaktorauthentifizierung (MFA) ist im Gegensatz zur ID-basierten Mehrfaktorauthentifizierung nur für ein Konto erforderlich, für das die Einstellung aktiviert ist. Weitere Informationen finden Sie in [Arten der Mehrfaktorauthentifizierung](/docs/iam?topic=iam-types#types).
{:shortdesc}

## Externe Authentifizierung bestellen
{: #ordering}

Wenn Sie über eine der folgenden Zugriffsberechtigungen verfügen, können Sie die externe Authentifizierung für einen Benutzer bestellen:

* Rolle 'Editor' oder höher für den Benutzermanagementservice
* Sie gelten in der Hierarchie der klassischen Infrastruktur als 'Vorfahre' eines Benutzers und Ihnen ist für die klassische Infrastruktur die Berechtigung zum Verwalten von Benutzern zugewiesen

Führen Sie die folgenden Schritte aus, um die externe Authentifizierung zu bestellen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie einen Benutzer aus der Liste aus.
3. Wählen Sie auf der Seite **Benutzerdetails** die Option **Externe Authentifizierung bestellen** im Abschnitt für die Benutzeranmeldung aus.
4. Wählen Sie **Symantec Identity Protection** oder **Telefongestützter Schutz personenbezogener Daten** aus.
    * Für die Authentifizierung mit Symantec muss der Benutzer die App [Symantec VIP](https://vip.symantec.com/){: new_window} ![Symbol für externen Link](../icons/launch-glyph.svg) herunterladen und eine Berechtigungsnachweis-ID anfordern, um mit dem Bestellablauf fortfahren zu können.
    * Für die telefongestützte Authentifizierung können Sie mit der Bestellung fortfahren, Ihr Benutzer muss jedoch zuerst seine [Konfiguration einrichten](/docs/account?topic=account-login-settings#setting-up-phone-based-authentication), bevor Sie die Option aktivieren können.
5. Gehen Sie entsprechend den Eingabeaufforderungen für die von Ihnen getroffene Auswahl vor und überprüfen Sie den Preis und die Bedingungen, bevor Sie die Bestellung aufgeben.
6. Klicken Sie auf **Bestellen**, um Ihre Auswahl abzuschließen.

Nachdem die Bestellung der Symantec-Authentifizierung erfolgt ist, können Sie auf der Seite 'Benutzerdetails' die Option für den Benutzer aktivieren. Nachdem die telefongestützte Authentifizierung bestellt und vom Benutzer konfiguriert worden ist, können Sie auf der Seite 'Benutzerdetails' die Option für den Benutzer aktivieren.

## Optionen für die externe Authentifizierung inaktivieren
{: #disable}

Sie können die MFA mit Symantec bzw. die telefongestützte MFA für einen Benutzer jederzeit inaktivieren.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie einen Benutzer aus der Liste aus.
3. Inaktivieren Sie auf der Seite **Benutzerdetails** die Option **Symantec-Authentifizierung** bzw. **Telefongestützte Authentifizierung**.

## Optionen für die externe Authentifizierung stornieren
{: #cancel}

Sofern Sie über die richtige Zugriffsberechtigung verfügen, können Sie Ihre Bestellung für die externe Authentifizierung zu jedem beliebigen Zeitpunkt stornieren. Dabei können Sie frei entscheiden, ob Sie die sofortige Stornierung ohne Rückerstattung wünschen oder ob Sie die Option ein Jahr nach Ablauf eines Jahres ab dem Bestellzeitpunkt stornieren wollen.

Um eine Bestellung für die externe Authentifizierung stornieren zu können, müssen Sie ein Kontoeigner sein oder über alle die folgenden Zugriffsberechtigungen verfügen:

* Berechtigung der klassischen Infrastruktur zum Verwalten von Benutzern
* Berechtigung der klassischen Infrastruktur zum Stornieren von Services
* Rolle des Administrators für den Kontoverwaltungsservice von Support Center oder migrierte Berechtigungen der klassischen Infrastruktur zum Anzeigen, Bearbeiten und Hinzufügen von Tickets, die in den [Zugriffsgruppen für migrierte Berechtigungen](/docs/iam?topic=iam-migrated_permissions) nicht verfügbar sind.

Führen Sie die folgenden Schritte aus, um die Bestellung der externen Authentifizierung zu stornieren:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie einen Benutzer aus der Liste aus.
3. Klicken Sie auf der Seite **Benutzerdetails** auf **Löschen** ![Löschsymbol](../icons/icon_trash.svg) für die Zeile **Symantec-Authentifizierung** oder **Telefongestützte Authentifizierung**, abhängig davon, welche Option Sie bestellt haben.
4. Wählen Sie aus, zu welchem Zeitpunkt die Option entfernt werden soll.
5. Klicken Sie auf **Entfernen**.
