---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Retrait d'utilisateurs
{: #remove}

Lorsque vous retirez un utilisateur du compte, l'utilisateur ne peut plus se connecter à la console, accéder à votre compte s'il appartient toujours à un autre compte ou accéder à des ressources de compte.
{:shortdesc}

Seuls les utilisateurs ou les propriétaires de compte avec l'accès suivant peuvent retirer des utilisateurs d'un compte :

* Règle IAM pour le service de gestion des comptes Gestion des utilisateurs avec le rôle Administrateur affecté. Vous devez être gestionnaire d'organisation Cloud Foundry si l'utilisateur appartient à une organisation Cloud Foundry.
* Si vous avez une infrastructure classique dans votre compte, un utilisateur doit avoir une règle IAM pour le service de gestion de compte Gestion des utilisateurs avec le rôle Administrateur affecté. Vous devez être gestionnaire d'organisation Cloud Foundry si l'utilisateur appartient à une organisation Cloud Foundry et être un ancêtre de l'utilisateur dans la hiérarchie d'utilisateurs de l'infrastructure classique avec le droit de gestion correspondant affecté. 

Pour retirer un utilisateur d'un compte, procédez comme suit : 

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sur la ligne de l'utilisateur à retirer, sélectionnez **Retirer l'utilisateur** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg). 

