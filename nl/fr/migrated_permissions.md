---

copyright:

  years: 2019

lastupdated: "2019-05-13"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}


# Gestion des droits de compte SoftLayer migrés
{: #migrated_permissions}

Les groupes d'accès incluent désormais un ensemble migré de droits de compte SoftLayer pour l'affichage et la gestion des informations de facturation et l'utilisation des cas de support. Les utilisateurs de votre compte auxquels ces droits ont été précédemment affectés sont désormais affectés au groupe d'accès des droits migrés respectifs. Par conséquent, les droits peuvent être directement gérés en utilisant des règles d'accès IAM. {:shortdesc}

Ces groupes d'accès spéciaux incluent toutes les règles IAM appropriées pour conserver le comportement d'origine des droits de compte SoftLayer. Par exemple, pour qu'un utilisateur continue de voir toutes les mises à jour apportées à un cas de support par tous les utilisateurs, les groupes d'accès de droits migrés pour les droits de compte SoftLayer de demande de service incluent une règle IAM supplémentaire concernant le service Gestion des utilisateurs avec le rôle Afficheur affecté. Pour plus d'informations, voir [Attribution d'accès utilisateur pour l'utilisation de cas de support](/docs/get-support?topic=get-support-access#access).

Vous pouvez continuer à gérer ces droits d'infrastructure classique migrés pour les utilisateurs directement via IAM en les ajoutant et en les retirant dans des groupes d'accès de droits migrés. Les droits dont disposent ces groupes d'accès sont verrouillés afin de conserver le comportement d'accès pour leurs membres. Pour que les nouveaux utilisateurs IAM puissent bénéficier de cette facilité d'utilisation, évitez de supprimer ces groupes d'accès.

Une fois que les droits d'infrastructure classique sont migrés, vous devez arrêter de les utiliser. Consultez le tableau suivant présentant tous les droits d'infrastructure classique faisant désormais partie des groupes d'accès IAM.
{: important}

| Nom du groupe d'accès de droits migrés | Actions autorisées |
|----------|---------|
| Afficher le récapitulatif de compte | Afficher la page récapitulative de compte ainsi que les factures et les paiements.  |
| Obtenir le rapport de conformité | Demander des rapports de conformité. |
| Editer le profil de société | Editer les informations de profil de société. |
| Paiements ponctuels | Effectuer des paiements ponctuels sur le compte de l'utilisateur. |
| Mettre à jour les détails de paiement |Mettre à jour les informations relatives au paiement mensuel. |
| Limiter les restrictions de cas de support de l'Union européenne | Activer ou désactiver l'option Support dans l'Union européenne qui restreint les données de cas de support à l'Union européenne.  |
| Ajouter des cas de support et afficher les commandes | Créer des cas de support et voir toutes les commandes.  |
| Editer les cas de support | Editer les cas de support. |
| Rechercher des cas de support | Rechercher tous les cas de support si le droit d'affichage de cas est également affecté. |
| Afficher les cas de support | Afficher tous les cas de support. |
{: caption="Tableau 1. Groupes d'accès prédéfinis" caption-side="top"}

