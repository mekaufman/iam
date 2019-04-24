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
{:important: .important}

# Gestion des paramètres de connexion d'un utilisateur 
{: #loginsettings}

Un propriétaire de compte ou un utilisateur disposant de l'accès approprié peut gérer les paramètres de connexion d'un utilisateur. Il peut, par exemple, commander des options d'authentification externe, activer un code à usage unique à utiliser lors de la connexion, activer l'utilisation des questions de sécurité lors de la connexion et définir une période d'expiration pour le mot de passe.
{:shortdesc}

Procédez comme suit pour gérer les paramètres de connexion pour un utilisateur spécifique :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**. 
2. Sélectionnez un utilisateur dans la liste puis cliquez sur **Détails de l'utilisateur**. 
3. Dans la section **Gérer la connexion de l'utilisateur**, vous pouvez activer ou désactiver les options suivantes pour l'utilisateur sélectionné : 
    
    * Authentification du code d'accès à usage unique à durée limitée : Activez cette option pour que l'utilisateur soit invité à entrer un code d'accès à usage unique lors de la connexion. L'utilisateur doit configurer l'authentification multi-facteur avec code d'accès à usage unique à durée limitée sur la page Paramètres de connexion. Pour plus d'informations, voir [Activation de l'authentification multi-facteur avec code d'accès à usage unique pour un utilisateur](/docs/iam?topic=iam-totp#totp).
    
    * Commander une authentification externe : Sélectionnez cette option pour acheter à un coût mensuel l'authentification Symantec ou l'authentification par téléphone. Une seule option peut être commandée et utilisée à la fois. Pour plus d'informations, voir [Commande d'authentification multi-facteur externe pour un utilisateur](/docs/iam?topic=iam-external#external).

        * Authentification par téléphone : L'utilisateur peut avoir recours à cette option en utilisant la configuration définie sur la page Détails de l'utilisateur une fois la commande effectuée par le propriétaire du compte. 
        * Authentification Symantec : L'utilisateur peut utiliser l'option une fois que le propriétaire du compte l'a commandée. Pour qu'un administrateur puisse commander cette option, l'utilisateur doit tout d'abord indiquer l'ID de données d'identification.

    * Poser des questions de sécurité d'authentification multi-facteur lors de la connexion : Activez cette option pour qu'un utilisateur soit invité à entrer les réponses aux questions de sécurité, éléments configurés sur la page Paramètres de connexion. Vous ne pouvez pas activer cette option si l'utilisateur n'a pas déjà configuré les questions de sécurité. Pour plus d'informations, voir [Activation des questions de sécurité d'authentification multi-facteur pour un utilisateur](/docs/iam?topic=iam-questions#questions).

    * Connexion gérée par l'utilisateur : Activez cette option pour que l'utilisateur définisse une expiration de mot de passe, qu'il active les questions de sécurité pour la connexion et qu'il définisse des adresses IP autorisées pour les API d'infrastructure classique et de connexion {{site.data.keyword.cloud_notm}}. 

    * Expiration du mot de passe : Définissez une expiration en sélectionnant une option dans la liste. Cette option est disponible uniquement pour les utilisateurs disposant d'un ID SoftLayer. Si l'utilisateur peut gérer ses propres paramètres de connexion, il peut également définir cette expiration sur la page Paramètres de connexion. Seuls les utilisateurs disposant des droits suivants peuvent définir une expiration de mot de passe pour un utilisateur :
        
        * Tout utilisateur ayant une règle IAM affectée avec un rôle Editeur ou supérieur dans le service Gestion des utilisateurs.
        * Tout utilisateur pour lequel la connexion gérée par l'utilisateur est activée sur la page Détails de l'utilisateur par l'administrateur.
        * Tout ancêtre de la hiérarchie d'infrastructure classique pour l'utilisateur auquel le droit de gestion d'infrastructure classique d'utilisateurs est affecté.

Une seule option d'authentification multi-facteur doit être activée à la fois. Si l'authentification multi-facteur avec IBMid est requise pour un compte dont l'utilisateur est membre, elle remplace toute autre authentification multi-facteur activée et l'utilisateur n'est pas invité à appliquer un autre type d'authentification multi-facteur.
{: important}



