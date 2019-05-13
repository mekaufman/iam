---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: MFA, multifactor authentication, external authentication, order authentication, Symantec, phone-based authentication, cancel authentication order

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Commande d'authentification multi-facteur externe pour un utilisateur
{: #external}

En tant qu'administrateur disposant de l'accès approprié, vous pouvez commander l'authentification externe et activer l'option d'authentification multi-facteur pour la connexion d'un utilisateur. Un forfait mensuel vous est alors facturé pour les options d'authentification externe. Ce type d'authentification multi-facteur est requis uniquement pour le compte dans lequel le paramètre est activé, contrairement à l'authentification multi-facteur avec ID. Pour plus d'informations, voir [Types d'authentification multi-facteur](/docs/iam?topic=iam-types#types).
{:shortdesc}

## Commande d'authentification externe
{: #ordering}

Si vous disposez de l'accès suivant, vous pouvez commander l'authentification externe pour un utilisateur :

* Editeur ou rôle supérieur dans le service Gestion des utilisateurs
* Vous êtes un ancêtre dans la hiérarchie d'infrastructure classique pour l'utilisateur. Vous disposez également du droit de gestion d'infrastructure classique d'utilisateurs.

Pour commander l'authentification externe, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sélectionnez un utilisateur dans la liste.
3. Sur la page **Détails de l'utilisateur**, sélectionnez **Commander une authentification externe** dans la section Gérer la connexion de l'utilisateur.
4. Sélectionnez **Protection de l'identité Symantec** ou **Protection de l'identité par téléphone**.
    * Pour l'authentification Symantec, l'utilisateur doit télécharger l'application [Symantec VIP](https://vip.symantec.com/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg) et obtenir un ID de données d'identification pour poursuivre le processus de commande.
    * Pour l'authentification par téléphone, vous pouvez effectuer la commande mais votre utilisateur doit [effectuer la configuration](/docs/account?topic=account-third-party-MFA#setting-up-phone-based-authentication) avant que vous ne puissiez activer l'option.
5. En fonction de votre sélection, suivez les invites pour consulter le prix et les conditions avant de valider la commande.
6. Cliquez sur **Commande** pour finaliser votre sélection.

Une fois que l'authentification Symantec est commandée, vous pouvez activer l'option pour l'utilisateur sur la page Détails de l'utilisateur. Une fois que l'authentification par téléphone est commandée puis configurée par l'utilisateur, vous pouvez activer l'option pour l'utilisateur sur la page Détails de l'utilisateur.

## Désactivation des options d'authentification externe
{: #disable}

Vous pouvez désactiver l'authentification multi-facteur par téléphone ou Symantec pour un utilisateur à tout moment.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sélectionnez un utilisateur dans la liste.
3. Sur la page **Détails de l'utilisateur**, désactivez l'option **Authentification Symantec** ou **Authentification par téléphone**.

## Annulation des options d'authentification externe
{: #cancel}

Vous pouvez annuler votre commande d'authentification externe à tout moment, si vous disposez de l'accès approprié. Vous pouvez choisir d'annuler la commande immédiatement sans aucun remboursement ou de l'annuler à la première date anniversaire.

Pour annuler une commande d'authentification externe, vous devez être propriétaire d'un compte ou disposer de tous les accès suivants :

* Gestion du droit d'infrastructure classique des utilisateurs
* Annulation du droit d'infrastructure classique des services
* Administration du service de gestion de compte Centre de support ou droits d'infrastructure classique migrés d'affichage, d'édition et d'ajout de ticket non disponibles dans les [groupes d'accès des droits migrés](/docs/iam?topic=iam-predefined#predefined).

Pour annuler la commande d'authentification externe, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez Utilisateurs.
2. Sélectionnez un utilisateur dans la liste.
3. Sur la page **Détails de l'utilisateur**, cliquez sur **Supprimer** ![Icône Supprimer](../icons/icon_trash.svg) pour la ligne **Authentification Symantec** ou **Authentification par téléphone** en fonction de la méthode commandée.
4. Sélectionnez quand vous souhaitez que le retrait ait lieu.
5. Cliquez sur **Retirer**.
