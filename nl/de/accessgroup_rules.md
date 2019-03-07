---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: dynamic rules, access groups, specific identity attributes

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Dynamische Regeln für Zugriffsgruppen erstellen
{: #rules}

Sie können dynamische Regeln erstellen, um föderierte Benutzer auf der Basis bestimmter Identitätsattribute automatisch zu Zugriffsgruppen hinzuzufügen. Wenn sich Benutzer mit einer föderierten IUD anmelden, werden die vom Identitätsprovider bereitgestellten Daten dazu verwendet, die Benutzer auf der Basis der von Ihnen festgelegten Regeln dynamisch einer Zugriffsgruppe zuzuordnen.
{:shortdesc}

Benutzer verfügen bereits über bestimmte Identitätsinformationen innerhalb Ihrer Unternehmensdomäne und wenn sich diese Benutzer mit einer föderierten ID anmelden, können diese Daten mithilfe von SAML-Zusicherungen weitergeleitet werden. Die SAML-Zusicherungen oder Attributanweisungen, die im Identitätsprovider konfiguriert sind, liefern die Daten, die zur Erstellung der einzelnen Regeln verwendet werden. Beispielsweise kann anhand einer Attributanweisung mit dem Wert 'true' oder 'false' ein Benutzer als Manager definiert werden. Diese Informationen können dazu verwendet werden, alle Benutzer, die als Manager definiert sind, zu einer bestimmten Zugriffsgruppe für Manager hinzuzufügen, die Sie in Ihrem {{site.data.keyword.Bluemix_notm}}-Konto erstellt haben. Weitere Informationen hierzu finden Sie in [Beispielregel](/docs/iam?topic=iam-rules#example).

Nur Benutzer, die bereits zum Konto eingeladen wurden, können mithilfe dynamischer Regeln Zugriffsgruppen zugeordnet werden.
{: note}

## Regeln festlegen
{: #setup_rules}

Dynamische Regeln werden erstellt, indem Bedingungen festgelegt werden. Diese Bedingungen müssen von den Daten erfüllt werden, die im Identitätsprovider konfiguriert sind und während der Anmeldung mit der föderierten ID eines Benutzers übergeben werden. Führen Sie die folgenden Schritte aus, um eine Regel zu erstellen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Wählen Sie den Namen der Zugriffsgruppe aus, für die eine Regel erstellt werden soll, um die Detailseite der Gruppe zu öffnen.
3. Wählen Sie die Registerkarte **Dynamische Regeln** aus.
4. Klicken Sie auf **Regel hinzufügen**.
5. Geben Sie die Informationen des Identitätsproviders ein. Die folgende Liste enthält Details zu jedem erforderlichen Feld.

<dl>
<dt>Name</dt>
<dd>Geben Sie einen benutzerdefinierten Namen für die Regel ein, anhand dessen Sie die Benutzertypen identifizieren können, die Sie zu einer Zugriffsgruppe hinzufügen.</dd>
<dt>Identitätsprovider</dt>
<dd>Geben Sie den URI für den Identitätsprovider ein. Hierbei handelt es sich um das SAML-Feld "entityId", auch als Aussteller-ID bezeichnet, für den Identitätsprovider als Teil der Föderierungskonfiguration für das Onboarding mit der IBMid.</dd>
<dt>Ablauf (in Stunden)</dt>
<dd>Mit dieser Option können Sie zusätzliche Sicherheit implementieren, indem Sie ein Zeitlimit für den zugewiesenen Zugriff festlegen. Jeder Benutzer muss sich alle 24 Stunden anmelden, um seinen Zugriff zu aktualisieren, Sie können jedoch einen kürzeren Zeitraum für das Ablaufen des Zugriffs festlegen. Der Mindestzeitraum beträgt eine Stunde. Die Gruppenzugehörigkeit wird nach dem Ablauf dieses Zeitraums widerrufen.</dd>
<dt>Benutzer in den folgenden Fällen hinzufügen</dt>
<dd>Der Name der Attributanweisung muss in diesem Feld eingegeben werden. Dieser Wert ist für Ihren Identitätsprovider spezifisch.</dd>
<dt>Vergleichsoperator</dt>
<dd>Mögliche Werte: 'Gleich', 'Ungleich', 'Gleich (ohne Beachtung der Groß-/Kleinschreibung)', 'Ungleich (ohne Beachtung der Groß-/Kleinschreibung)', 'In' und 'Enthält'. Verwenden Sie die Option 'Enthält', wenn die Attributanweisung einen Arraytyp aufweist. Die Angabe der Option 'In' ermöglicht das Eingeben mehrerer Werte für eine Übereinstimmung.</dd>
<dt>Wert</dt>
<dd>Geben Sie den Attributwert für die Attributanweisung für den Vergleich mit der Regel ein.</dd>
</dl>

Sie können mehr als eine Bedingung für eine Regel hinzufügen. Alle in der Regel festgelegten Bedingungen müssen erfüllt sein, damit ein Benutzer zu einer Zugriffsgruppe hinzugefügt wird.
{: tip}

## Beispielregel
{: #example}

Das folgende Beispiel enthält Werte für die einzelnen Felder auf der Seite **Regel hinzufügen**. In dieser Regel werden Benutzer, die im Provider der föderierten ID als Manager identifiziert werden, einer {{site.data.keyword.Bluemix_notm}}-Zugriffsgruppe zugeordnet, in der spezifische Zugriffsberechtigungen ausschließlich für Manager festgelegt sind.

| Feld | Wert |
|----------|---------|
| Name | Managergruppenregel |
| Identitätsprovider | `https://idp.example.org/SAML2` |
| Ablauf (in Stunden) | 12 |
| Benutzer in den folgenden Fällen hinzufügen (Attributname) | isManager |
| Vergleichsoperator | Gleich  |
| Wert |  true |
{: caption="Tabelle 1. Beispiele für dynamische Regeln für Zugriffsgruppen" caption-side="top"}
