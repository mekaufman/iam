---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-28"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}

# Mise à jour du statut d'un utilisateur
{: #status}

Le statut affecté d'un utilisateur varie en fonction des situations suivantes : l'utilisateur a accepté l'invitation à rejoindre le compte, l'utilisateur est de type VPN uniquement ou l'administrateur a défini l'utilisateur en tant qu'utilisateur désactivé d'infrastructure classique.
{:shortdesc}

Si vous disposez de l'accès suivant, vous pouvez mettre à jour le statut d'un autre utilisateur :

  * Règle IAM avec un rôle Editeur ou supérieur dans le service Gestion des utilisateurs.
  * Vous êtes un ancêtre dans la hiérarchie d'infrastructure classique pour l'utilisateur. Vous disposez également du droit de gestion d'infrastructure classique d'utilisateurs.

Pour plus d'informations sur les différents types de statut utilisateur, voir [Statut de l’utilisateur](/docs/iam?topic=iam-user_status#user_status).

## Options de modification du statut d'un utilisateur
{: #status_options}

Pour mettre à jour le statut d'un utilisateur, vous pouvez choisir une des options suivantes :

<dl>
<dt>Actif</dt>
<dd>L'utilisateur dispose d'un accès complet à la console {{site.data.keyword.cloud_notm}} en fonction des droits d'accès affectés et des droits d'infrastructure classique.</dd>
<dt>Infrastructure classique désactivée</dt>
<dd>L'utilisateur ne peut plus accéder aux ressources d'infrastructure classique mais peut continuer à se connecter à la console et à accéder aux ressources de plateforme.</dd>
<dt>VPN uniquement</dt>
<dd>L'utilisateur ne peut pas se connecter à la console mais il a accès aux périphériques et aux sous-réseaux VPN affectés à l'infrastructure classique lorsqu'il se connecte directement au dispositif.</dd>
</dl>

Lorsque vous mettez à jour un utilisateur ayant le statut VPN uniquement afin qu'il ait le statut Actif, l'utilisateur doit connaître le mot de passe pour se connecter à la console. Dans la plupart des cas, il s'agit du mot de passe de l'ID SoftLayer. Il peut être nécessaire de réinitialiser ce dernier. Dans de rares cas où l'utilisateur dispose déjà d'un IBMid, il doit se connecter avec l'IBMid et le mot de passe.
{: note}

## Mise à jour du statut d'un utilisateur
{: #update_user_status}

Pour changer le statut d'un utilisateur, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**. 
2. Sélectionnez un utilisateur dans la liste.
3. Sur la page Détails de l'utilisateur, sélectionnez une option dans le menu **Statut de l'utilisateur**.  
4. Cliquez sur **Appliquer**.


