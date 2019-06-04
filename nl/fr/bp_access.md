---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-28"

keywords: advantage of access groups, access assignment process, assign access, best practice, access management, strategy

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Meilleures pratiques pour l'affectation d'accès
{: #account_setup}

Pour rationaliser le processus d'affectation d'accès, vous pouvez tirer parti des groupes d'accès pour affecter un nombre minimal de règles en octroyant le même accès à tous les utilisateurs et ID de service qui appartiennent à un même groupe d'accès. Utilisez ces meilleures pratiques pour en apprendre davantage sur les moyens de fournir aux utilisateurs un accès aux ressources, groupes de ressources et services de gestion des comptes.
{:shortdesc}

Pour être certain de réussir avec un compte correctement configuré, voir [Meilleures pratiques pour la configuration de votre compte](/docs/account?topic=account-account_setup#account_setup) et [Meilleures pratiques pour l'organisation des ressources dans un groupe de ressources](/docs/resources?topic=resources-bp_resourcegroups#bp_resourcegroups).
{: tip}

## Qu'est-ce qu'une bonne stratégie de groupe d'accès ?
{: #rg_strategy}

Un groupe d'accès est un regroupement d'utilisateurs et d'ID de service auquel le même accès IAM peut être accordé. Vous pouvez affecter une seule règle au groupe au lieu d'affecter individuellement le même accès plusieurs fois pour chaque utilisateur ou ID de service.

En partant du principe que vous avez suivi les instructions décrites dans la rubrique [Meilleures pratiques pour la configuration de votre compte](/docs/account?topic=account-account_setup#account_setup), vous pouvez logiquement affecter un accès en créant un groupe d'accès par niveau d'accès souhaité. Ensuite, vous pouvez mapper chaque groupe d'accès aux groupes de ressources précédemment créés. Par exemple, pour contrôler l'accès au projet `CustApp`, vous pouvez créer les groupes d'accès suivants :

* Auditor-Group
* Developer-Group
* Admin-Group

Pour Auditor-Group, affectez deux règles d'accès qui octroient les droits d'accès Afficheur aux groupes de ressources `CustApp-Test` et `CustApp-Prod`. Pour Developer-Group, affectez deux règles d'accès qu octroient les droits d'accès Editeur aux environnements `CustApp-Dev` et `CustApp-Test`. Pour Admin-Group, affectez trois règles d'accès qui octroient les droits d'accès Administrateur à l'ensemble des trois groupes de ressources `CustApp`.

Bien que ces suggestions soient conçues pour un scénario hypothétique, vous pouvez configurer le groupe d'accès pour mappage des groupes de ressources comme bon vous semble.

## Création de groupes d'accès
{: #access-group-setup}

Pour créer un groupe d'accès, procédez comme suit :

1. Dans la console {{site.data.keyword.Bluemix}}, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Cliquez sur **Créer**.
3. Entrez le nom et la description du groupe.
4. Cliquez sur **Créer**.

Après avoir créé un groupe d'accès, vous pouvez y ajouter des utilisateurs et des ID de service.

## De quelle façon les règles d'accès IAM fournissent-elles un accès ?
{: #how_access}

Une règle est composée d'un objet, d'une cible et d'un rôle. L'objet de ce scénario est le groupe d'accès La cible est ce à quoi l'objet doit pouvoir accéder, par exemple, un ensemble de ressources, une instance de service, tous les services du compte ou toutes les instances d'un service. Le rôle définit le niveau d'accès qui est octroyé à un utilisateur.

Les rôles les plus fréquemment utilisés sont Afficheur, Editeur et Administrateur. Le rôle Afficheur fournit l'accès minimum et permet d'afficher des instances et des groupes de ressources dans un compte. Le rôle Editeur dispose de davantage d'accès et permet de créer, d'éditer, de supprimer et de lier des instances de service. Le rôle Administrateur comprend tout ce qui permet de gérer une instance de service et peut affecter un accès aux autres utilisateurs. Cependant, il convient de prendre en compte deux catégories de rôles distinctes, Plateforme et Service. Pour plus d'informations sur les rôles qui peuvent être affectés, voir [Rôles cloud IAM](/docs/iam?topic=iam-userroles#iamusermanrol).

## Affectation d'accès à des groupes d'accès
{: #assigning-access}

Vous pouvez organiser des ressources dans un groupe de ressources et des utilisateurs et des ID de service dans un groupe d'accès afin de simplifier au maximum le processus d'affectation d'accès. Après avoir configuré chacun d'eux, vous pouvez créer des règles d'accès pour les groupes d'accès afin de fournir aux utilisateurs de votre compte l'accès aux ressources que vous avez créées.

1. Cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le nom du groupe d'accès auquel vous souhaitez affecter un accès.
3. Sélectionnez l'onglet **Règles d'accès**, puis cliquez sur **Affecter un accès**. Vous disposez des options suivantes pour affecter un accès :

  * **Affecter l'accès aux ressources d'un groupe de ressources** : Utilisez cette option pour accorder la règle en deux parties nécessaire aux utilisateurs qui créent des ressources à partir du catalogue et qui affectent les ressources à un groupe de ressources. Lorsque vous utilisez cette option, vous pouvez octroyer l'accès au groupe de ressources proprement dit et à toutes les ressources d'un groupe de ressources spécifique ou à juste un service ou une instance du groupe de ressources.
  * **Affecter l'accès aux ressources** : Utilisez cette option pour affecter l'accès à tous les services activés par IAM dans le compte ou à un seul service du compte, mais pas à une instance.
  * **Affecter l'accès aux services de gestion des comptes** : Utilisez cette option pour accorder à un utilisateur l'accès aux services de gestion des comptes et ainsi déléguer certaines de vos fonctions de propriétaire de compte. Par exemple, vous pouvez déléguer l'aptitude à afficher la facturation et l'utilisation, à inviter et retirer des utilisateurs, à gérer des groupes d'accès, à gérer des services de catalogue ou à gérer des ID de service. Vous pouvez octroyer l'accès à tous les services de gestion de compte ou bien à un seul.

Accordez facilement à plusieurs utilisateurs les droits d'accès Administrateur sur tout ce que contient un compte en créant un groupe d'accès et en lui affectant deux règles. Pour créer la première règle, utilisez l'option **Affecter l'accès aux ressources** et sélectionnez **Tous les services avec l'offre Identity and Access activée** avec le rôle Administrateur affecté. Pour créer la seconde règle, utilisez l'option **Affecter l'accès aux services de gestion des comptes** et sélectionnez **Tous les services de gestion des comptes** avec le rôle Administrateur affecté.
{: tip}
