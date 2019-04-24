---

copyright:

  years: 2017, 2018

lastupdated: "2018-11-30"

keywords: SoftLayer permissions, classic infrastructure access, classic infrastructure permission, migrated SoftLayer permissions, migrated permission access group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}

# Droits d'infrastructure classique
{: #infrapermission}

Lorsque vous invitez un utilisateur à rejoindre votre compte, vous pouvez effectuer un choix parmi les trois ensembles de droits d'infrastructure classique qui affectent un accès en bloc : Affichage uniquement, Utilisateur de base, Superutilisateur.
{:shortdesc}

Vous pouvez définir des droits supplémentaires une fois que l'utilisateur a accepté l'invitation. Par exemple, l'ensemble de droits initiaux accordé lors de l'invitation ne donne pas accès aux périphériques. Par conséquent, vous devez octroyer l'accès aux périphériques une fois que l'utilisateur a accepté l'invitation. Pour plus d'informations, voir [Gestion de l'accès à l'infrastructure classique](/docs/iam/mnginfra.html#mngclassicinfra).

Lorsque vous invitez une personne à rejoindre le compte, seul vous, le propriétaire du compte ou un utilisateur disposant du droit Gestion de l'infrastructure classique d'utilisateur, pouvez adapter les droits pour l'utilisateur. Si vous affectez des droits et que vous n'êtes pas le propriétaire du compte, vous pouvez affecter uniquement le niveau de droits ou un sous-ensemble de droits dont vous disposez. Un propriétaire de compte peut mettre à jour les droits de n'importe quel utilisateur du compte afin de lui accorder le niveau d'accès souhaité.


## Droits d'infrastructure classique migrés
{: #predefined}

Un ensemble de droits d'infrastructure classique pour l'affichage et la gestion des informations de facturation et l'utilisation des cas de support est désormais migré vers des groupes d'accès. Les utilisateurs de votre compte auxquels ces droits ont été précédemment affectés sont désormais affectés au groupe d'accès des droits migrés respectifs. Par conséquent, les droits d'infrastructure classique peuvent être directement gérés en utilisant des règles d'accès IAM.

Ces groupes d'accès spéciaux incluent toutes les règles IAM appropriées pour conserver le comportement d'origine des droits d'infrastructure classique. Par exemple, pour qu'un utilisateur continue de voir toutes les mises à jour apportées à un cas de support par tous les utilisateurs, les groupes d'accès de droits migrés pour les droits d'infrastructure classique de demande de service incluent une règle IAM supplémentaire concernant le service Gestion des utilisateurs avec le rôle Afficheur affecté. Pour plus d'informations, voir [Attribution d'accès utilisateur pour l'utilisation de cas de support](/docs/get-support/support_access.html#access).

Vous pouvez continuer à gérer ces droits d'infrastructure classique migrés pour les utilisateurs directement via IAM en les ajoutant et en les retirant dans des groupes d'accès de droits migrés. Les droits dont disposent ces groupes d'accès sont verrouillés afin de conserver le comportement d'accès pour leurs membres. Pour que les nouveaux utilisateurs IAM puissent bénéficier de cette facilité d'utilisation, évitez de supprimer ces groupes d'accès.

Une fois que les droits d'infrastructure classique sont migrés, vous devez arrêter de les utiliser. Consultez le tableau suivant présentant tous les droits d'infrastructure classique faisant désormais partie des groupes d'accès IAM.
{: important}

| Nom du groupe d'accès de droits migrés | Actions autorisées |
|----------|---------|
| Afficher le récapitulatif de compte | Afficher la page récapitulative de compte ainsi que les factures et les paiements |
| Obtenir le rapport de conformité | Demander des rapports de conformité |
| Editer le profil de société | Editer les informations de profil de société |
| Paiements ponctuels | Effectuer des paiements ponctuels sur le compte de l'utilisateur |
| Mettre à jour les détails de paiement | Mettre à jour les informations de paiement mensuel récurrentes |
| Limiter les restrictions de cas de support de l'Union européenne | Activer ou désactiver l'option Support dans l'Union européenne qui restreint les données de cas de support à l'Union européenne  |
| Ajouter des cas de support et afficher les commandes | Créer des cas de support et voir toutes les commandes.  |
| Editer les cas de support | Editer les cas de support |
| Rechercher des cas de support | Rechercher tous les cas de support tant que le droit d'affichage de cas est également affecté |
| Afficher les cas de support | Afficher tous les cas de support |
{: caption="Tableau 1. Groupes d'accès prédéfinis" caption-side="top"}

Vous pouvez continuer de gérer des utilisateurs pour les groupes d'accès. Toutefois, il peut être utile de créer des groupes d'accès qui incluent un ensemble de règles pour les [services de gestion de compte IAM](/docs/iam?topic=iam-account-services#account-services) afin de faciliter l'affectation d'accès aux tâches de gestion de compte et l'utilisation de cas de support.
