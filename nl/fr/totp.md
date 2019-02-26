---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Activation de l'authentification multi-facteur avec code d'accès à usage unique pour un utilisateur
{: #totp}

En tant qu'administrateur disposant de l'accès approprié, vous pouvez sur la page Détails de l'utilisateur de la console {{site.data.keyword.Bluemix}} activer l'option permettant qu'un utilisateur soit invité à entrer un code d'accès à usage unique à durée limitée (TOTP) lors de la connexion. Ce type d'authentification multi-facteur est requis uniquement pour le compte dans lequel le paramètre est activé, contrairement à l'authentification multi-facteur avec ID. Pour plus d'informations, voir [Types d'authentification multi-facteur](/docs/iam?topic=iam-types#types).
{:shortdesc}

Si vous disposez d'un des accès suivants, vous pouvez mettre à jour ce paramètre pour d'autres utilisateurs de votre compte :

* Editeur ou rôle supérieur dans le service Gestion des utilisateurs
* Vous êtes un ancêtre dans la hiérarchie d'infrastructure classique pour l'utilisateur. Vous disposez également du droit de gestion d'infrastructure classique d'utilisateurs.

Pour activer le paramètre de connexion pour qu'un utilisateur soit invité à choisir l'authentification multi-facteur par code d'accès à usage unique à durée limitée, procédez comme suit.

Pour activer cette option d'authentification multi-facteur pour un utilisateur, ce dernier doit tout d'abord [configurer un code d'accès à usage unique à durée limitée](/docs/account?topic=account-MFA#MFA) sur la page Paramètres de connexion du profil.
{: note}

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sélectionnez un utilisateur dans la liste.
3. Sur la page **Détails de l'utilisateur** de la section **Gérer la connexion de l'utilisateur**, activez l'option **Code d'accès à usage unique à durée limitée**.

Vous pouvez gérer ce paramètre pour votre compte si l'option Connexion gérée par l'utilisateur est activée sur votre page Détails de l'utilisateur.
{: tip}

