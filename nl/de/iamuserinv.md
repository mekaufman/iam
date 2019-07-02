---

copyright:

  years: 2015, 2019

lastupdated: "2019-06-25"

keywords: invite, invite users, invitation access, vpn-only user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Benutzer einladen
{: #iamuserinv}

Verwenden Sie {{site.data.keyword.Bluemix}} Identity and Access Management (IAM), um Benutzer einzuladen, Einladungen zu stornieren und eine ausstehende Einladung an einen eingeladenen Benutzer erneut zu senden. Darüber hinaus können Sie einen einzelnen Benutzer oder mehrere Benutzer gleichzeitig einladen.
{:shortdesc}

Zum Einladen von Benutzern und Verwalten ausstehender Einladungen müssen Sie entweder ein Kontoeigner, ein Organisationsmanager oder ein Benutzer mit einer IAM-Zugriffsrichtlinie mit der Rolle 'Editor' oder höher für den Benutzermanagementservice sein oder Sie müssen über Berechtigungen für die klassische Infrastruktur zum Hinzufügen von Benutzern verfügen.

## Einladung einrichten
{: #invitations}

Führen Sie die folgenden Schritte aus, um Benutzer einzuladen oder Einladungen in Ihrem Konto zu verwalten:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Klicken Sie auf **Benutzer einladen**.
3. Geben Sie die E-Mail-Adresse des Benutzers an. Wenn Sie mehrere Benutzer mit einer einzigen Einladung einladen, dann wird diesen Benutzern der gleiche Zugriff erteilt.
4. Fügen Sie eine oder mehrere der von Ihnen verwalteten Zugriffsoptionen hinzu. Sie müssen mindestens eine Zugriffsoption zuweisen. Für alle weiteren Zugriffsoptionen, die Sie nicht hinzufügen und konfigurieren, wird der Standardwert **Kein Zugriff** zugewiesen. Abhängig von den Optionen, zu deren Verwaltung Sie berechtigt sind, zeigt das System eine oder alle der folgenden Zugriffsoptionen an:

  * **Services**
  * **Cloud Foundry-Zugriff**
  * **Zugriff auf die klassische Infrastruktur**.

  Weitere Informationen zu diesem Thema erhalten Sie in [Benutzerzugriff zuweisen](/docs/iam?topic=iam-iamuserinv#assignaccess).

Wenn Sie entscheiden, dass ein Benutzer keinen Zugriff benötigt, können Sie eine Einladung für beliebige Benutzer abbrechen, die in der Spalte "Status" mit dem Status "Verarbeitung läuft" oder "Anstehend" angezeigt werden. Wenn ein eingeladener Benutzer keine Einladung empfangen hat, können Sie die Einladung an jeden Benutzer mit dem Status "Anstehend" erneut senden.

### Benutzer über die Befehlszeilenschnittstelle (CLI) einladen
{: #cli-invite}

Wenn Sie Benutzer über die Befehlszeilenschnittstelle (Command-Line Interface, CLI) einladen möchten, verwenden Sie den folgenden Befehl:

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

Wenn Sie die Befehlszeilenschnittstelle verwenden, können Sie Cloud Foundry-Zugriffsberechtigungen zuweisen oder Sie können die Zugriffsberechtigungen zu einem späteren Zeitpunkt zuweisen. Weitere Informationen zu den Befehlsparametern finden Sie in [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite). 

### Benutzer über die API einladen
{: #api-invite}

Sie können die [API](https://cloud.ibm.com/apidocs/user-management#invite-users){: external} verwenden, um Benutzer über eine Massenoperation einzuladen. Allen Benutzern, die in eine einzelne Einladung einbezogen sind, werden dieselben Zugriffsberechtigungen zugewiesen. Wenn Sie Benutzer über die API einladen, geben Sie die E-Mail-Adressen in einer durch Kommas getrennten Liste ein, wobei die einzelnen Einträge in Anführungszeichen eingeschlossen sind. Beispiel:


```
curl -X POST \
  https://user-management.cloud.ibm.com/v2/accounts/987d4cfd77b04e9b9e1a6asdcc861234/users \
  -H 'Authorization: Bearer <IAM_TOKEN>'
  -H 'Content-Type: application/json' \
    -d '{
      "users": [
      {
        "email": "cloud_api_example_member@ibm.com", "second_user@ibm.com", "third_user@ibm.com",
        "account_role": "Member"
      }],
      "iam_policy": [
      {
        "roles": [
        {
          "id": "crn:v1:bluemix:public:iam::::role:Viewer"
        }],
        "resources": [
        {
          "accountId": "111d4cfd77b04e9b9e1a6asdcc861234",
          "resourceType": "resource-group",
          "resource": "111449dd871049c29ec3a53853ce123e"
        }]
      }]
    }'
```
{: codeblock}

## Benutzerzugriff über eine Einladung zuweisen
{: #assignaccess}

Wenn Sie Benutzer einladen, weisen Sie ihnen Zugriffsberechtigungen zu. Dazu führen Sie eine Zuweisung von {{site.data.keyword.Bluemix}} IAM-Richtlinien, Cloud Foundry-Zugriffsrechten und Berechtigungen für die klassische Infrastruktur durch. Abhängig von den Zugriffsoptionen, zu deren Verwaltung Sie berechtigt sind, können Sie Benutzer aus dem gesamten Konto, den Ressourcengruppen, Organisationen, Bereichen, Serviceinstanzen und der klassischen Infrastruktur einladen und diesen Benutzern Zugriffsberechtigungen erteilen. In den folgenden Abschnitten werden die drei Arten von Zugriff beschrieben, die Sie einem eingeladenen Benutzer zuweisen können.

### Services
{: #invite_services}

Sie können Zugriff erteilen, indem Sie eine Ausgangsrichtlinie für den Zugriff auf {{site.data.keyword.Bluemix_notm}} IAM erstellen, wenn Sie einen neuen Benutzer einladen. Im Abschnitt 'Services' können Sie einem Benutzer den Zugriff auf Kontoverwaltungsservices, auf Services in einer Ressourcengruppe mit Zugriff zur Verwaltung der Ressourcengruppe oder auf eine einzelne Ressource im Konto erteilen.

Nachdem der Benutzer die Einladung akzeptiert hat, können Sie weitere Zugriffsberechtigungen zuweisen. Detaillierte Informationen zum Bearbeiten von Richtlinien für das Hinzufügen zusätzlicher Rollen, zum Zuweisen weiterer Zugriffsberechtigungen oder zum Entfernen einer Richtlinie für einen Benutzer finden Sie in [Zugriff auf Ressourcen verwalten](/docs/iam?topic=iam-iammanidaccser#iammanidaccser).

Abhängig von dem Service, den Sie beim Zuweisen der Richtlinie ausgewählt haben, werden möglicherweise nicht alle in den folgenden Arbeitsschritten beschriebenen Felder angezeigt.
{: note}

#### Zugriff auf Kontoverwaltungsservices
{: #invite_acct_mgmt}

Wenn Sie einen Teil Ihrer Verantwortlichkeiten als Kontoeigner delegieren möchten, können Sie einem Benutzer Zugriff auf Kontoverwaltungsservices erteilen. So können Sie z. B. die Fähigkeit delegieren, Abrechnung und Nutzung einzusehen, Benutzer einzuladen und zu entfernen und Zugriffsgruppen oder Service-IDs zu verwalten. Sie können Zugriff auf alle Kontoverwaltungsservices oder nur auf einen einzigen bereitstellen.

1. Erweitern Sie auf der Seite "Benutzer einladen" den Abschnitt "Services".
2. Wählen Sie aus der Liste **Zugriff zuweisen für** die Option **Kontoverwaltungsservices** aus. 
3. Wählen Sie **Alle Kontoverwaltungsservices** oder einen bestimmten Kontoverwaltungsservice aus.
4. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen.

#### Zugriff auf Ressourcengruppen
{: #invite_rgs}

Sie können Zugriff auf alle Services in einer Ressourcengruppe oder aber auf einen einzelnen Servicetyp in einer Ressourcengruppe erteilen.

1. Erweitern Sie auf der Seite "Benutzer einladen" den Abschnitt "Services".
2. Wählen Sie aus der Liste **Zugriff zuweisen für** die Option **Ressourcengruppe** aus.
3. Wählen Sie eine Ressourcengruppe aus.
4. Wählen Sie aus der Liste **Zugriff für eine Ressourcengruppe zuweisen** eine Rolle aus, um dem Benutzer die Anzeige der Ressourcengruppe für die Ressourcenliste, die Bearbeitung des Ressourcengruppennamens oder die Verwaltung des Benutzerzugriffs auf die Gruppe zu ermöglichen. Sie können **Kein Zugriff** auswählen, wenn der Benutzer ausschließlich auf die von Ihnen angegebene Ressource Zugriff erhalten soll, jedoch nicht auf die Gruppe, in der die Ressource enthalten ist.
5. Wählen Sie einen Service in der Ressourcengruppe aus oder wählen Sie aus, dass der Zugriff auf alle Services in der ausgewählten Gruppe bereitgestellt werden soll.
6. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen. Dieser Zugriff gilt nur für die Ressourcen, die Sie für die Richtlinie ausgewählt haben. Der Zugriff auf den Container selbst, der die Ressourcengruppe darstellt, wird hingegen nicht erteilt.

#### Ressourcenzugriff
{: #invite_resources}

Sie können Zugriffsberechtigungen für eine einzelne Ressource innerhalb Ihres Kontos bis auf die Instanzebene zuweisen.

1. Erweitern Sie auf der Seite "Benutzer einladen" den Abschnitt "Services".
2. Wählen Sie aus der Liste **Zugriff zuweisen für** die Option **Ressource** aus. 
3. Wählen Sie einen Service aus.
4. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus, wenn Sie vom System dazu aufgefordert werden.
5. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
6. Abhängig vom ausgewählten Service können die folgenden Felder angezeigt werden. Wenn Sie für diese Felder keine Werte eingeben, wird die Richtlinie nicht auf der Bucketebene, sondern auf der Serviceinstanzebene zugewiesen.
    * **Ressourcentyp**: Geben Sie `Bucket` ein.
    * **Ressourcen-ID**: Geben Sie den Namen des Buckets ein.
7. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen.

Weitere Informationen zu den Rollen, die bei der Zuweisung von Zugriff verwendet werden, finden Sie im Abschnitt zum [IAM-Zugriff](/docs/iam?topic=iam-userroles#iamusermanrol).

### Cloud Foundry-Zugriff
{: #invite_cf}

Wenn Sie neue Benutzer einladen, können Sie den Benutzer zu einer Organisation im Konto hinzuzufügen. Wenn Sie den Benutzer zu einer Organisation hinzufügen, können Sie ihm eine Organisationsrolle zuweisen. Anschließend können Sie dem eingeladenen Benutzer Zugriff auf einen, mehrere oder alle Bereiche in der ausgewählten Organisation mit einer zugewiesenen Bereichsrolle erteilen.

1. Erweitern Sie auf der Seite "Benutzer einladen" den Abschnitt "Cloud Foundry-Zugriff".
2. Wählen Sie eine Organisation aus, zu der der Benutzer hinzugefügt werden soll.
3. Wählen Sie eine Organisationsrolle aus, um die Zugriffsebene für die ausgewählte Organisation zu definieren.
4. Optional: Klicken Sie auf **Organisationsrolle hinzufügen**, um eine zusätzliche Rolle anzugeben.
5. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus.
6. Wählen Sie **Alle aktuellen Bereiche** oder einen bestimmten Bereich aus.
7. Wählen Sie eine Bereichsrolle aus, um die Zugriffsebene für die ausgewählten Bereiche zu definieren.
8. Optional: Klicken Sie auf **Bereichsrolle hinzufügen**, um eine zusätzliche Rolle anzugeben.

Weitere Informationen zu den Rollen, die bei der Zuweisung von Zugriff verwendet werden, finden Sie im Abschnitt zu [Cloud Foundry-Rollen](/docs/iam?topic=iam-cfaccess#cfroles).

Sie können eine Cloud Foundry-Rolle mithilfe des CLI-Befehls [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite) hinzufügen, aber zum Zuweisen anderer Zugriffsrechte oder Berechtigungen müssen Sie die Konsole verwenden.
{: tip}

### Zugriff auf die klassische Infrastruktur
{: #invite_classicinfra}

Die zugewiesenen Berechtigungen sind automatisch auf die Untergruppe von Berechtigungen eingeschränkt, über die Sie verfügen. Sie sind damit jedem von Ihnen eingeladenen Benutzer übergeordnet.

1. Erweitern Sie auf der Seite "Benutzer einladen" den Abschnitt "Zugriff auf die klassische Infrastruktur".
2. Weisen Sie ein Berechtigungsset aus, um eine Massenzuweisung von Berechtigungen durchzuführen.

Der Zugriff auf Geräte wird separat erteilt, nachdem ein Benutzer hinzugefügt wurde. Rufen Sie dazu in der Konsole für den entsprechenden Benutzer die Zugriffsoption für die **Klassische Infrastruktur** auf.
{: note}

Informationen zum Konfigurieren des Zugriffs für Benutzer, nachdem diese zu Ihrem Konto hinzugefügt wurden, finden Sie in [Zugriff auf die klassische Infrastruktur verwalten](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra).

## Benutzer mit Status 'Nur VPN' hinzufügen
{: #add-vpn-only}

Als der Kontoeigner oder als Benutzer mit der Berechtigung der klassischen Infrastruktur zum Verwalten von Benutzern können Sie Benutzer mit dem Status 'Nur VPN' hinzufügen.

1. Klicken Sie auf der Seite "Benutzer" auf **Benutzer mit Status 'Nur VPN' hinzufügen**.
2. Geben Sie die personenbezogenen Daten des Benutzers ein.
3. Klicken Sie auf **Speichern**.
