---

copyright:

  years: 2019

lastupdated: "2019-03-25"

keywords: public access, anonymous access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Activation de l'accès public aux ressources
{: #public}

L'accès public aux ressources permet à tous les utilisateurs et aux ID de service de pouvoir accéder à une ressource spécifique de votre compte. Cela signifie qu'un utilisateur ou un ID de service n'a pas besoin de s'authentifier auprès d'{{site.data.keyword.Bluemix}} pour accéder aux informations d'un compartiment {{site.data.keyword.cos_full_notm}}, par exemple. Seuls certains services prennent en charge la possibilité d'accorder un accès public à des types de ressource spécifiques pour le service. C'est pourquoi, vous ne pouvez créer des règles que pour les services qui prennent en charge cette fonction.
{:shortdesc}

Pour activer l'accès public aux ressources, vous devez utiliser le groupe d'accès **Accès public** mis à votre disposition dans votre compte. Ce groupe d'accès inclut tous les utilisateurs et les ID de service par défaut. Vous ne pouvez pas supprimer le groupe ou changer l'appartenance du groupe mais vous pouvez ajouter, éditer et supprimer des règles d'accès pour le groupe.

## Création d'une règle pour le groupe d'accès public
{: #public_policy}

Procédez comme suit pour affecter une règle à votre groupe d'accès public. La tâche suivante utilise le service Cloud Object Storage en tant qu'exemple pour l'affectation de l'accès public à un compartiment appelé `mybucket123`.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le groupe **Accès public**.
3. Cliquez sur **Affecter un accès**.
4. Sélectionnez **Cloud Object Storage** dans la liste de services.
5. Entrez `bucket` comme type de ressource.
6. Entrez `mybucket123` comme ID de ressource.
7. Cliquez sur **Affecter**.
8. Cliquez sur **Oui** pour confirmer le fait que vous souhaitez affecter la règle d'accès public à la ressource puis cliquez sur **Affecter**.
