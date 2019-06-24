---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: user list visibility, users page setting, user view access, limit access to users list, user list access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Définition de l'accès à la vue utilisateur
{: #userlistview}

En tant que propriétaire de compte {{site.data.keyword.Bluemix}}, vous pouvez voir tous les utilisateurs de votre compte et définir comment les utilisateurs peuvent voir les utilisateurs du compte.
{:shortdesc}

Lorsque l'option **Affichage non restreint** est sélectionnée, tout utilisateur du compte peut voir les autres utilisateurs sur la page Utilisateurs dans la console {{site.data.keyword.Bluemix_notm}}. Lorsque l'option **Affichage restreint** est sélectionnée, les utilisateurs peuvent uniquement afficher des types spécifiques d'utilisateurs dans le compte : 

* Les utilisateurs invités par l'utilisateur
* Les utilisateurs partageant une organisation Cloud Foundry avec l'utilisateur
* Les utilisateurs descendants de ces utilisateurs dans la hiérarchie utilisateur d'infrastructure classique, à savoir les utilisateurs qu'ils ont invités ou que l'un de leurs descendants a invités.

Par défaut, l'affichage non restreint est défini pour votre compte. Pour mettre à jour ce paramètre, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Paramètres**.
2. Sélectionnez **Affichage restreint** pour le paramètre **Visibilité de la liste d'utilisateurs**.
