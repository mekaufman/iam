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

# Mise à jour d'un utilisateur parent d'un utilisateur
{: #update-parent}

Si vous disposez de l'accès correct, vous pouvez mettre à jour le parent d'un utilisateur. La mise à jour de l'utilisateur parent a des conséquences sur la manière dont un utilisateur voit les autres utilisateurs dans le compte lorsque le paramètre de visibilité de liste d'utilisateurs a la valeur Restreint. Les utilisateurs voient uniquement les utilisateurs dont ils sont parents ainsi que les utilisateurs invités par les descendants de l'utilisateur parent.
{:shortdesc}

Pour plus de détails sur le paramètre, voir le [paramètre de visibilité de liste d'utilisateurs](/docs/iam?topic=iam-userlistview#userlistview). 

Si vous disposez de l'accès suivant, vous pouvez mettre à jour le parent pour un autre utilisateur :

* Règle IAM avec un rôle Editeur ou supérieur dans le service Gestion des utilisateurs.
* Vous êtes un ancêtre dans la hiérarchie d'infrastructure classique pour l'utilisateur. Vous disposez également du droit de gestion d'infrastructure classique d'utilisateur.


Pour mettre à jour le parent d'un utilisateur, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.  
2. Sélectionnez un nom d'utilisateur dans la liste.
3. Sur la page Détails de l'utilisateur, sélectionnez un nouvel utilisateur parent dans le menu **Parent**.
4. Cliquez sur **Appliquer**.
