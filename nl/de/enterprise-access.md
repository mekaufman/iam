---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Benutzermanagement für Unternehmen
{: #enterprise-access}

{{site.data.keyword.cloud}}-Unternehmen eignen sich für große Firmen oder Organisationen, die Konten gruppieren müssen, die aber gleichzeitig die Konten für verschiedene Abteilungen oder Teams getrennt halten und voneinander isolieren müssen. Das Management der Benutzer und ihr Zugriff auf die Ressourcen in jedem Konto bleiben völlig getrennt, auch wenn die Konten zu einem Unternehmen hinzugefügt und im Unternehmen organisiert werden.
{:shortdesc}

Weitere Informationen finden Sie im Abschnitt [Was ist ein Unternehmen?](/docs/account?topic=account-enterprise).

Die Benutzerliste für jedes untergeordnete Konto in einem Unternehmen ist nur für die Benutzer in diesem untergeordneten Konto zugänglich. Dies bedeutet, dass die Benutzer, die für das Unternehmen eingeladen werden, und die Benutzer, die für die Konten in dem Unternehmen eingeladen werden, weiterhin vollständig voneinander getrennt bleiben. Das ist von Vorteil, weil Sie einem Unternehmen mehrere Konten hinzufügen und diese nach Bedarf in Kontogruppen organisieren können, die Benutzerlisten aber von anderen Konten nicht zugänglich sind.

In den meisten Fällen möchten Sie nur die Benutzer zu Ihrem Unternehmenskonto hinzufügen, die in der Lage sein sollen, das Unternehmen zu verwalten. Abhängig von der Rolle, die dem Benutzer im [Unternehmenskontoverwaltungsservice](/docs/iam?topic=iam-assign-access-enterprise) zugewiesen ist, verfügt er über unterschiedliche Zugriffsebenen für die Verwaltung des Unternehmens. Beispiel: Ein Benutzer, dem die Rolle "Administrator" für den Unternehmensservice zugewiesen ist, kann das Unternehmen umbenennen, die Domäne aktualisieren, die Nutzung anzeigen, Konten erstellen und vieles mehr. Ein Benutzer mit der Rolle "Anzeigeberechtigter" oder "Operator" kann dagegen nur die Hierarchie der Konten und Kontogruppen für das Unternehmen anzuzeigen.

Wenn Benutzer für das Unternehmenskonto eingeladen werden, erhalten sie dadurch keinen Zugriff auf die Verwaltung eines der untergeordneten Konten innerhalb des Unternehmens oder der zugehörigen Ressourcen. Wenn Sie Benutzer zu einem Unternehmenskonto hinzufügen, das eine Reihe von Konten enthält, erhalten diese Benutzer nicht automatisch Zugriff auf die Verwaltung dieser Konten (Benutzermanagement, Abrechnung usw.). Die Benutzer des Unternehmenskontos haben auch keinen Zugriff auf Ressourcen in anderen Konten innerhalb des Unternehmens.

Wenn Sie möchten, dass ein Benutzer das Unternehmen verwalten und Zugriff auf Ressourcen in untergeordneten Konten haben soll, müssen Sie ihn für beide Konten einladen. Durch das Zuweisen von Zugriffsrichtlinien im Unternehmenskonto kann der Benutzer das Unternehmen verwalten. 
Das Zuweisen von Zugriffsrichtlinien im untergeordneten Konto ermöglicht es dem Benutzer, in diesem Konto bestimmte Ressourcen zu verwalten oder Kontoverwaltungstasks auszuführen.
{: note}

Informationen dazu, wie Sie den Benutzern in einem Unternehmen Zugriff zuweisen, finden Sie unter [Unternehmenszugriff zuweisen](/docs/iam?topic=iam-assign-access-enterprise).
