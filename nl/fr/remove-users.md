---

copyright:

  years: 2018, 2019

lastupdated: "2019-08-09"

keywords: remove user, delete user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Suppression d'utilisateurs d'un compte
{: #remove}

Lorsque vous supprimez un utilisateur d'un compte, l'utilisateur ne peut plus se connecter à la console, basculer sur votre compte s'il appartient encore à un autre compte ou accéder à des ressources de compte. La suppression d'un utilisateur d'un compte ne supprime pas l'IBMid de l'utilisateur.{:shortdesc}

Seuls les utilisateurs ou les propriétaires de compte avec l'accès suivant peuvent retirer des utilisateurs d'un compte :

* Règle IAM pour le service de gestion des comptes Gestion des utilisateurs avec le rôle Administrateur affecté. Vous devez être gestionnaire d'organisation Cloud Foundry si l'utilisateur appartient à une organisation Cloud Foundry.
* Si vous avez une infrastructure classique dans votre compte, un utilisateur doit avoir une règle IAM pour le service de gestion de compte utilisateur avec le rôle Administrateur affecté. Vous devez être gestionnaire d'organisation Cloud Foundry si l'utilisateur appartient à une organisation Cloud Foundry et être un ancêtre de
l'utilisateur dans la hiérarchie d'utilisateurs de l'infrastructure classique avec le droit de gestion correspondant affecté.

Pour retirer un utilisateur d'un compte, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sur la ligne de l'utilisateur à retirer, sélectionnez **Retirer l'utilisateur** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg).

Toutes les ressources créées par l'utilisateur restent dans le compte. Toutefois, l'utilisateur n'a plus accès au travail avec ces ressources, de sorte que le propriétaire du compte ou un administrateur pour ce service ou cette instance de service peut affecter d'autres utilisateurs à travailler avec les ressources ou les supprimer du compte.

Si vous recevez un message d'erreur indiquant qu'un utilisateur d'infrastructure classique ne peut pas être supprimé, assurez-vous qu'un [nouveau parent a
été affecté](/docs/iam?topic=iam-update-parent) dans la hiérarchie à tous les descendants de cet utilisateur ou que ceux-ci ont été [désactivés dans le compte](/docs/iam?topic=iam-status), ou supprimés, puis renouvelez l'opération.
{: tip}
