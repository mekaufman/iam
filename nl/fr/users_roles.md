---

copyright:

  years: 2015, 2019

lastupdated: "2019-01-21"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:new_window: target="_blank"}

# Accès IAM
{: #userroles}

Tous les services organisés en un groupe de ressources dans votre compte sont gérés via {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM). Le rôle d'administrateur des accès au compte pour le service Cloud IAM est automatiquement affecté aux propriétaires de compte. En tant qu'administrateur de compte, vous pouvez affecter et gérer l'accès des utilisateurs, créer des groupes de ressources, créer des groupes d'accès, afficher les informations de facturation et de suivi, et créer des instances de service. Vous accordez l'accès aux utilisateurs, aux ID de service et aux groupes d'accès en créant des règles qui définissent une cible pour l'accès de l'objet de la règle et un rôle qui définit le type d'accès autorisé.
{: shortdesc}

## Quelles sont les règles Cloud IAM et qui peut les affecter ?
{: #iamusermanpol}

Une règle accorde à un objet un ou plusieurs rôles sur un ensemble de ressources de sorte que des actions spécifiques puissent être engagées dans le contexte des ressources cible spécifiées. Vous pouvez affecter et gérer des règles si le rôle approprié vous a été attribué. Le tableau suivant décrit les tâches de gestion des règles et le rôle requis pour chacune.

| Action | Rôle requis |
|----------|---------|
| Créer une règle dans un compte pour tous les services et instances | Propriétaire de compte ou administrateur de tous les services de gestion de compte et de tous les services activés pour IAM | 
| Créer une règle sur un service dans un compte | Propriétaire du compte, administrateur de tous les services activés pour IAM, ou administrateur du service dans le compte |
| Créer une règle sur une instance de service | Propriétaire du compte, administrateur de tous les services activés pour IAM, ou administrateur du service dans le compte, administrateur de tous les services dans le groupe de ressources pertinent, ou administrateur de l'instance de service |
{: caption="Tableau 1. Utilisateurs autorisés à créer des règles d'accès" caption-side="top"} 

Lorsque vous affectez une règle, vous commencez avec l'objet. Une fois que vous avez sélectionné l'objet de la règle, vous pouvez choisir de la définir pour un groupe de ressources, une ressource individuelle ou un service de gestion des comptes. 

Ensuite, selon votre sélection initiale, vous pouvez choisir l'une des options suivantes :
  
  * Un service dans un groupe de ressources
  * Toutes les ressources d'un groupe de ressources
  * Toutes les instances ou une instance pour la ressource sélectionnée
  * Tous les services activés par IAM dans le compte
  * Un service de gestion des comptes 

D'autres options de configuration peuvent être disponibles, selon le service que vous sélectionnez. Enfin, vous sélectionnez les rôles à affecter. 

## Types de règles d'accès courantes
{: #policytypes}

Vous pouvez attribuer un accès à granularité fine aux utilisateurs, aux ID de service ou aux groupes d'accès en affectant les types de règles d'accès suivants :

* Tous les services de gestion des comptes
* Service de gestion de compte spécifique
* Toutes les ressources d'un compte
* Toutes les ressource de tous les services appartenant à un groupe de ressources spécifique avec la possibilité de gérer le groupe de ressources
* Toutes les ressources d'un seul service dans un groupe de ressources avec la possibilité de gérer le groupe de ressources
* Toutes les ressources d'un seul service du compte, quel que soit le groupe de ressources auquel elles sont affectées
* Les ressources d'une instance individuelle
* Un seul type de ressource dans une instance, par exemple, un compartiment dans une instance {{site.data.keyword.objectstorageshort}}

Pour accorder à un autre utilisateur l'accès complet au compte à des fins de gestion des accès utilisateur et de gestion de toutes les ressources de compte, vous devez affecter deux règles. Une règle octroiera à l'utilisateur l'accès à toutes les ressources en sélectionnant **Tous les services avec l'offre Identity and Access activée** en lui affectant le rôle **Administrateur**. L'autre règle octroiera à l'utilisateur l'accès à tous les services de gestion des comptes du compte en sélectionnant **Tous les services de gestion des comptes** en lui affectant le rôle **Administrateur**.
{: tip}

## Rôles Cloud IAM
{: #iamusermanrol}

Cloud IAM vous permet de gérer et de définir les droits d'accès des utilisateurs et des ressources dans votre compte. Types de rôles pouvant être affectés : rôles de gestion de la plateforme et rôles d'accès aux services.

<dl>
<dt>Rôles de gestion de plateforme</dt> 
<dd>Les rôles de gestion de plateforme couvrent une gamme d'actions, notamment la possibilité de créer et de supprimer des instances, de gérer des alias, des liaisons, des données d'identification et de gérer les accès. Les rôles de plateforme sont les suivants : administrateur, éditeur, opérateur, afficheur. Les rôles de gestion de plateforme s'appliquent également aux services de gestion de compte qui permettent aux utilisateurs d'inviter des utilisateurs, de gérer les ID de service, les règles d'accès, les entrées de catalogue et d'effectuer le suivi de la facturation et de l'utilisation compte tenu du rôle qui leur est affecté dans un compte de gestion de service.</dd>
<dt>Rôles Accès au service</dt>
<dd>Les rôles d'accès au service définissent la capacité qu'a un utilisateur ou un service d'exécuter des actions sur une instance de service, par exemple, accéder à la console ou effectuer des appels API. Les rôles d'accès au service sont les suivants : responsable, auteur et lecteur. </dd>
</dl> 

Tous les rôles listés ici ne seront pas forcément affichés lorsque vous affectez des règles dans l'interface utilisateur vu que seuls sont affichés les rôles disponibles pour le service choisi. Pour plus d'informations sur les rôles qui sont activés et sur les actions que chaque rôle d'accès autorise pour chaque service, reportez-vous à la documentation du service concerné.
{: note}

### Rôles de gestion de plateforme
{: #platformroles}

Les rôles de gestion de plateforme permettent d'attribuer aux utilisateurs des degrés d'autorisation différents pour effectuer des actions de plateforme dans le compte et sur un service. Par exemple, les rôles de gestion de plateforme affectés pour les ressources de catalogue permettent aux utilisateurs d'effectuer des actions comme la création, la suppression, l'édition et l'affichage d'instances de service. Les services de gestion de plateforme affectés pour les services de gestion de service permettent aux utilisateurs d'effectuer des actions comme l'invitation et la suppression d'utilisateurs, l'utilisation de groupes de ressources et l'affichage des informations de facturation. Pour plus d'informations sur les services de gestion de compte, voir [Tableau 3. Exemple d'actions et de rôles de gestion de plateforme pour les services de gestion de compte](#platformrolestable2).

Les tableaux suivants fournissent des exemples de certaines actions de gestion de plateforme que les utilisateurs peuvent effectuer dans le contexte de ressources de catalogue, de groupes de ressources et de services de gestion de compte. Pour comprendre comment les rôles s'appliquent aux utilisateurs dans le contexte du service que vous utilisez, reportez-vous à la documentation pour chaque offre de catalogue.

La première ligne du tableau décrit différentes options que vous pouvez sélectionner lors de la création d'une règle, et la première colonne décrit les rôles sélectionnés pour la règle. Les cellules restantes sont associées au rôle sélectionné dans la première colonne et au type de règle sélectionné dans les options de la première ligne.

| Détails de la règle d'accès | Actions sur les services du compte | Actions sur les ressources des groupes de ressources | Actions pour l'accès à des groupes de ressources |
|:--------------|:------------|:-------------|:-------------|
|  | Un ou tous les services activés pour IAM | Service sélectionné dans un groupe de ressources | Groupe de ressources sélectionné |
| Rôle Afficheur | Afficher des instances, des alias, des liaisons et des données d'identification | Afficher uniquement des instances spécifiées du groupe de ressources | Afficher un groupe de ressources |
| Rôle Opérateur |  Afficher des instances et gérer des alias, des liaisons et des données d'identification |  Non applicable | Non applicable |
| Rôle Editeur |  Créer, supprimer, éditer et afficher des instances. Gérer des alias, des liaisons et des données d'identification | Créer, supprimer, éditer, suspendre, reprendre, afficher et lier uniquement des instances spécifiées du groupe de ressources | Afficher et éditer le nom d'un groupe de ressources |
| Rôle Administrateur |  Toutes les actions de gestion pour des services | Toutes les actions de gestion pour des instances spécifiées du groupe de ressources | Afficher, éditer et gérer l'accès pour le groupe de ressources |
{: caption="Tableau 2. Exemples de rôles et d'actions de gestion de plateforme pour les services dans un compte" caption-side="top"}
{: #platformrolestable1}

Le tableau suivant décrit les actions courantes que vous pouvez effectuer compte tenu du rôle qui vous est affecté pour chaque service de gestion de compte. Faites défiler l'écran à l'horizontale pour visualiser toutes les entrées du tableau.
{: #acctmgmt}

Si vous affectez une règle d'accès sur **Tous les services de gestion des comptes**, selon le rôle que vous sélectionnez, l'utilisateur peut effectuer les actions suivantes pour chaque service d'après ce rôle. De plus, ce type de règle permet à l'utilisateur d'accéder aux informations de facturation et la possibilité de suivi de l'utilisation compte tenu du rôle qui lui est affecté. Pour plus de détails, reportez-vous au tableau suivant.
{: note}

La première ligne du tableau décrit des services spécifiques que vous pouvez sélectionner lors de la création d'une règle, et la première colonne décrit le type de rôle sélectionné pour la règle. Les cellules restantes sont associées au rôle sélectionné dans les options de la première colonne et au type de règle sélectionné dans les options de la première ligne.

| Détails de la règle d'accès |  Actions pour les ID de service  | Actions pour la gestion des groupes d'accès | Actions pour la gestion d'accès au catalogue | Actions pour l'accès afin de gérer les utilisateurs | Actions de support | Actions de facturation | Actions pour tous les services de gestion de compte | 
|:--------------|:-------------|:--------------|:--------------|:-----------|:--------------|:--------------|:--------------|
|  |  Service d'identité IAM |  Groupes d'accès IAM |  Catalogue de ressources globales |  Gestion des utilisateurs  | Centre de support | Facturation et utilisation | Tous les services de gestion des comptes |
| Rôle Afficheur |  <ul><li>Afficher les ID</li></ul> |  <ul><li>Afficher des groupes d'accès et des membres</li></ul> | <ul><li>Afficher les services privés</li></ul>  |  <ul><li>Afficher les utilisateurs du compte</li><li>Afficher les paramètres du profil utilisateur</li></ul> | <ul><li>Afficher les cas</li><li>Rechercher des cas</li></ul> | <ul><li>Afficher les paramètres des fonctions du compte</li><li>Afficher les abonnements dans le compte</li><li>Afficher le nom du compte</li><li>Afficher les groupes de ressources</li></ul> |Toutes les actions du rôle Afficheur pour les services de gestion de compte |
| Rôle Opérateur | <ul><li>Créer et supprimer des ID et des clés d'API</li></ul> |  <ul><li>Non applicable</li></ul> | <ul><li>Non applicable</li></ul> |  <ul><li>Afficher les utilisateurs du compte</li><li>Afficher les paramètres du profil utilisateur</li></ul> | <ul><li>Non applicable</li></ul> | <ul><li>Afficher les paramètres des fonctions du compte</li><li>Afficher les abonnements dans le compte</li><li>Afficher et modifier le nom du compte</li><li>Afficher et mettre à jour les groupes de ressources</li></ul> | Toutes les actions du rôle Opérateur pour les services de gestion de compte |
| Rôle Editeur |  <ul><li>Créer, mettre à jour et supprimer des ID et clés d'API</li></ul> |  <ul><li>Afficher, créer, éditer et supprimer des groupes</li><li>Ajouter ou supprimer des utilisateurs dans des groupes</li></ul> | <ul><li>Peut changer les métadonnées d'objet mais ne peut pas changer la visibilité des services privés</li></ul>  | <ul><li>Afficher, inviter, retirer et mettre à jour des utilisateurs dans le compte</li><li>Afficher et mettre à jour les paramètres de profil utilisateur</li></ul> | <ul><li>Non applicable</li></ul> | <ul><li>Afficher et mettre à jour les paramètres de fonctions du compte</li><li>Afficher les abonnements dans le compte</li><li>Afficher les offres dans le compte</li><li>Afficher et appliquer les codes de fonction</li><li>Afficher et modifier le nom du compte</li><li>Afficher et mettre à jour le plafond des dépenses</li><li>Afficher, créer et mettre à jour les groupes de ressources</li></ul> | Toutes les actions du rôle Editeur pour les services de gestion de compte |
| Rôle Administrateur |   <ul><li>Créer, mettre à jour et supprimer des ID et clés d'API</li><li>Affecter des règles d'accès aux ID</li></ul> |  <ul><li>Afficher, créer, éditer et supprimer des groupes</li><li>Ajouter ou supprimer des utilisateurs</li><li>Affecter l'accès à un groupe</li><li>Gérer l'accès pour utiliser des groupes d'accès</li></ul> | <ul><li>Peut changer les métadonnées d'objet ou la visibilité des services privés et peut restreindre la visibilité d'un service public</li></ul> | <ul><li>Afficher, inviter, retirer et mettre à jour des utilisateurs dans le compte</li><li>Afficher et mettre à jour les paramètres de profil utilisateur</li></ul> |  <ul><li>Afficher les cas</li><li>Rechercher des cas</li><li>Mettre à jour les cas</li><li>Créer des cas</li></ul> |  <ul><li>Afficher et mettre à jour les paramètres de fonctions du compte</li><li>Afficher les abonnements dans le compte</li><li>Afficher les offres dans le compte</li><li>Afficher et appliquer les codes de fonction</li><li>Afficher et modifier le nom du compte</li><li>Afficher et mettre à jour le plafond des dépenses</li><li>Afficher le solde des abonnements et effectuer le suivi de l'utilisation</li><li>Afficher, créer, mettre à jour et affecter un accès pour la gestion des groupes de ressources</li></ul> | Toutes les actions du rôle Administrateur pour les services de gestion de compte|
{: caption="Tableau 3. Exemples de rôles et d'actions de gestion de plateforme pour les services de gestion de comptes" caption-side="top"}
{: #platformrolestable2}

Pour le service d'identité IAM, ces actions s'appliquent aux ID de service dans le compte que l'utilisateur n'a pas créés. Tous les utilisateurs peuvent créer des ID de service. Ils sont administrateurs de ces ID et ils peuvent créer la clé d'API et les règles d'accès associées, mais ce service de gestion des comptes s'applique à la possibilité d'afficher, de supprimer et d'affecter l'accès aux ID de service dans le compte créé par d'autres utilisateurs.
{: note}

Certains services peuvent mapper des actions spécifiques aux rôles de gestion de plateforme qui sont liés à la gestion du service plutôt qu'à l'accès du service. A titre d'exemple, reportez-vous au tableau suivant dans lequel sont décrites les actions de service {{site.data.keyword.containershort_notm}} mappées à ces rôles.

| Rôles de gestion de plateforme | Actions | Exemples d'action pour {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Afficheur | Afficher des instances de service, sans pouvoir les modifier  | <ul><li>Répertorier les clusters</li><li>Afficher les détails d'un cluster</li></ul>|
| Editeur | Effectuer toutes les actions de plateforme à l'exception de la gestion du compte et de l'affectation de règles d'accès |<ul><li>Lier un service à un cluster</li><li>Créer un webhook</li></ul> |
| Opérateur | Effectuer les actions de plateforme requises pour configurer et exploiter des instances de service, par exemple, l'affichage de tableau de bord d'un service. | <ul><li>Ajouter ou retirer des noeuds d'agent</li><li>Redémarrer ou recharger des noeuds worker</li><li>Lier un service à un cluster</li></ul> |
| Administrateur | Effectuer toutes les actions de plateforme en fonction de la ressource pour laquelle ce rôle est affecté, y compris l'affectation de règles d'accès à d'autres utilisateurs. |<ul><li>Retirer un cluster</li><li>Créer un cluster</li><li>Mise à jour des règles d'accès utilisateur</li><li>Toutes les actions qu'un afficheur, un éditeur et un opérateur peuvent effectuer</li></ul>|
{: caption="Tableau 4. Exemple d'actions et de rôles de gestion de plateforme pour le service {{site.data.keyword.containershort_notm}}" caption-side="top"}

### Rôles Accès au service

Les rôles Accès au service permettent aux utilisateurs de se voir affecter différents niveaux de droits pour appeler l'API du service et accéder à l'interface utilisateur du service. Le tableau ci-après présente des exemples d'actions qui peuvent être exécutées en fonction des rôles affectés lors de l'utilisation du service {{site.data.keyword.objectstorageshort}}.

Les actions qui peuvent être exécutées en fonction de chaque rôle affecté varient selon le service que vous avez sélectionné pour la règle. Les services n'utilisent pas tous ces types de rôle. Pour plus d'informations, voir la documentation du service.
{: note}

| Rôle Accès au service | Actions | Exemples d'action pour {{site.data.keyword.objectstorageshort}} Service |
|:-----------------|:-----------------|:-----------------|
|  Lecteur | Effectuer des actions en lecture seule dans un service, par exemple, afficher les ressources spécifiques d'un service. | Répertorier et télécharger des objets |
| Auteur | Droits en plus du rôle de lecteur, notamment, créer et éditer des ressources pour un service. | Créer et détruire des compartiments et des objets |
| Responsable | Droits en plus du rôle d'auteur pour effectuer des actions privilégiées définies par le service, plus créer et éditer des ressources spécifiques des services. | Gérer tous les aspects de stockage de données. Créer et détruire des compartiments et des objets. |
{: caption="Tableau 5. Exemples d'actions et de rôles utilisateur d'accès au service" caption-side="top"}



