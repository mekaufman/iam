---

copyright:

  years: 2017, 2019

lastupdated: "2019-05-16"

keywords: get started with IAM, IAM tutorial, IAM quick start

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Tutoriel d'initiation
{: #getstarted}

Ce tutoriel a pour objectif de vous aider à démarrer et à travailler rapidement avec IBM Cloud Identity and Access Management (IAM) en invitant les utilisateurs de votre compte et en affectant des droits d'accès Cloud IAM à ces utilisateurs.
{:shortdesc}

Ce tutoriel concerne les ressources activées par IAM. Pour les services qui ne prennent pas en charge la création de règles Cloud IAM pour la gestion de l'accès, vous pouvez utiliser l'[accès Cloud Foundry](/docs/iam?topic=iam-cfaccess#cfaccess) ou les [droits d'infrastructure classique](/docs/iam?topic=iam-infrapermission#infrapermission).
{: note}

## Avant de commencer
{: #iam-before-you-begin}

Si vous n'êtes pas encore habitué à utiliser IAM, consultez la documentation suivante pour mieux comprendre les fonctions, concepts et composants du système de gestion des accès :

* [IBM Cloud Identity and Access Management](/docs/iam?topic=iam-iamoverview) qui donne un rapide aperçu d'IAM dans le cadre de {{site.data.keyword.Bluemix_notm}}, des fonctions disponibles et des liens vers les documentations relatives à l'interface de ligne de commande et aux API.
* [Concepts IAM](/docs/iam?topic=iam-iamconcepts) qui présente les concepts de haut niveau d'IAM qui vous aideront à mieux appréhender les différents composants lorsque vous démarrez.
* [Accès IAM](/docs/iam?topic=iam-userroles) qui examine plus en profondeur le fonctionnement de la gestion des accès par le biais de règles d'accès.


## Etape 1. Inviter des utilisateurs et leur affecter un accès initial
{: #step1}

Vous pouvez inviter un ou plusieurs utilisateurs et définir une règle d'accès initiale sur l'invitation pour les utilisateurs. Si vous invitez plusieurs utilisateurs avec une seule invitation, le même accès est accordé à chacun de ces utilisateurs. Dans la section Accès de la page Inviter des utilisateurs, vous ne voyez que les sections que vous êtes autorisé à affecter.

En tant que propriétaire de compte, vous pouvez affecter des rôles Cloud IAM aux utilisateurs que vous invitez dans la section Services. Vous pouvez accorder un accès à toutes les ressources d'un groupe de ressources, à toutes les ressources d'un service spécifique dans un groupe de ressources, à tous les services activés pour IAM dans le compte, à une ressource unique dans le compte ou encore à tous les services de gestion de compte :

1. Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Cliquez sur **Inviter des utilisateurs**.
3. Indiquez l'adresse électronique de l'utilisateur que vous voulez inviter.
4. Dans la section **Accès**, développez l'option **Services**.
5. Sélectionnez d'accorder l'accès à une **Ressource**, à des ressources dans un **Groupe de ressources** ou aux **Services de gestion des comptes**.
6. En fonction de votre sélection, suivez les invites pour définir l'accès souhaité. Si vous avez sélectionné l'option Groupe de ressources, vous pouvez également accorder à l'utilisateur le droit d'afficher, d'éditer ou de gérer l'accès au groupe de ressources en sélectionnant un rôle pour l'accès au groupe de ressources.
7. Si vous détenez le droit approprié, vous pouvez également affecter un accès à Cloud Foundry ou à l'infrastructure lors de l'invitation.
8. Cliquez sur **Inviter des utilisateurs**.

Pour plus d'informations, voir [Invitation d'utilisateurs et affectation d'accès](/docs/iam?topic=iam-iamuserinv#iamuserinv).

## Etape 2. Créer des groupes d'accès
{: #step2}

Pour rationaliser le processus d'affectation d'accès à des utilisateurs de votre compte, vous pouvez créer des groupes d'accès. Ces derniers permettent d'organiser des utilisateurs et des ID de service auxquels vous pouvez facilement affecter l'accès en définissant une règle unique pour l'ensemble du groupe.

### Configuration de vos groupes
{: #group_setup}

Pour créer un groupe d'accès, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Cliquez sur **Créer**.
3. Entrez un nom et une description facultative pour votre groupe
4. Cliquez sur **Créer**.

Ensuite, continuez de configurer votre groupe en ajoutant des utilisateurs ou des ID de service :

1. Sélectionnez le nom du groupe sur lequel vous voulez effectuer des ajouts.
2. Cliquez sur **Ajouter des utilisateurs**.
3. Sélectionnez dans la liste les utilisateurs que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.
4. Pour ajouter des ID de service au groupe, cliquez sur **ID de service**.
5. Sélectionnez dans la liste les ID que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**.

### Affectation d'accès à vos groupes
{: #group_access}

Une fois votre groupe créé, vous pouvez affecter des accès à toutes les entités du groupe en utilisant une seule règle ou plusieurs règles.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le nom du groupe auquel vous voulez affecter des accès.
3. Dans l'onglet **Règles d'accès**, cliquez sur **Affecter un accès** pour configurer une règle d'accès. Répétez cette action autant de fois que nécessaire pour affecter des accès supplémentaires.

Le fait d'organiser des ressources en groupes de ressources et des utilisateurs en groupes d'accès vous permet d'affecter un groupe d'accès utilisateur à un groupe de ressources à l'aide d'une seule règle et de réduire ainsi le nombre global de règles que vous devez gérer.
{: tip}


## Etape 3. Gérer l'accès d'utilisateurs existants
{: #user_access_manage}

Après avoir invité des utilisateurs, leur avoir affecté un accès initial et avoir créé des groupes d'accès, vous voudrez sans doute leur affecter des accès supplémentaires ou éditer leur accès initial pour vous assurer que tous les utilisateurs et groupes de votre compte bénéficient du niveau d'accès souhaité.

### Affectation d'un nouvel accès
{: #new_access}

Pour affecter une nouvelle règle d'accès, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sélectionnez le nom de l'utilisateur auquel vous voulez affecter un accès.
3. Cliquez sur **Règles d'accès**.
4. Cliquez sur **Affecter un accès**.
5. Choisissez comment vous voulez affecter l'accès :
    * Sélectionnez **Affecter l'accès au sein d'un groupe de ressources** pour accorder l'accès à toutes les ressources d'un groupe ou uniquement aux ressources d'un service spécifique du groupe. Vous pouvez également accorder à l'utilisateur le droit d'afficher, d'éditer ou de gérer l'accès au groupe de ressources en sélectionnant un rôle pour l'accès au groupe de ressources. Sélectionnez **Aucun accès** si vous souhaitez que l'utilisateur ait accès uniquement à la ressource spécifiée et non au groupe auquel elle appartient.
    * Sélectionnez **Affecter l'accès aux ressources** pour affecter l'accès à toutes les ressources du compte pour lesquelles l'offre Identity and Access est activée, à toutes les ressources d'un service spécifique du compte, à une seule instance ou à une seule ressource d'une instance de service spécifique.
    * Sélectionnez **Affecter l'accès aux services de gestion des comptes** pour accorder l'accès à tous les services de gestion de compte ou bien à un seul.
5. Sélectionnez toute combinaison de rôles afin de définir la portée de l'accès. Pour plus d'informations, voir [Rôles Cloud IAM](/docs/iam?topic=iam-iamusermanrol#iamusermanrol).
6. Cliquez sur **Affecter**.


### Edition d'un accès existant
{: #editing_access}

Vous pouvez mettre à jour un accès existant en éditant les rôles affectés à un utilisateur.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sélectionnez le nom de l'utilisateur dont vous voulez éditer l'accès.
3. Cliquez sur **Règles d'accès**.
4. Cliquez sur **Editer** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg) sur la ligne correspondant à la règle à éditer.
4. Editez la règle en mettant à jour les rôles affectés.
5. Cliquez sur **Sauvegarder**.

Vous pouvez supprimer l'accès d'un utilisateur en cliquant sur l'option **Retirer** du menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg) pour la règle à retirer.

## Etapes suivantes
{: #next}

Explorez les autres possibilités offertes par Cloud IAM en consultant la liste [Fonctionnalités de Cloud IAM](/docs/iam?topic=iam-features#features).
