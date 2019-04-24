---

copyright:

  years: 2018,2019
lastupdated: "2019-01-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Types d'authentification multi-facteur
{: #types}

L'authentification multi-facteur (MFA) ajoute une couche de sécurité supplémentaire à votre compte en exigeant que tous les utilisateurs s'authentifient en utilisant une méthode d'authentification supplémentaire (outre l'utilisation d'un ID et d'un mot de passe). Ce type d'authentification est également communément appelé authentification à deux facteurs (2FA).
{:shortdesc}

Les deux types d'option d'authentification multi-facteur peuvent être activés pour votre compte :

<dl>
<dt>Authentification multi-facteur avec ID</dt>
<dd>Option activée par un propriétaire de compte dans un des comptes dont vous êtes membre. Ce type d'authentification multi-facteur est associé à votre IBMid et vous authentifie dans tous les comptes dont vous êtes membre. Par conséquent, il vous suffit de vous identifier une seule fois.</dd>
<dt>Options dépendant du compte</dt>
<dd>Options, telles que des questions de sécurité, l'utilisation d'un code d'accès à usage unique à durée limitée et des options d'authentification externe, telles que l'authentification Symantec et l'authentification par téléphone. Ces types d'authentification multi-facteur sont spécifiques à chaque compte. Ce qui signifie que si pour chaque compte auquel vous appartenez, le type d'authentification configuré est différent, vous devez vous authentifier chaque fois que vous changez de compte. Les options d'authentification multi-facteur existantes sont disponibles uniquement avec les anciens comptes d'infrastructure classique.</dd>
</dl>

L'authentification multi-facteur avec IBMid répond aux exigences d'authentification. Par conséquent, aucune invite ne s'affiche vous demandant d'autres types d'authentification multi-facteur même si ces derniers sont activés. Ainsi, si un propriétaire d'un compte dont vous êtes membre active cette option, il s'agit du seul type d'authentification multi-facteur qui vous est demandé lors de la connexion. Si vous êtes un nouvel utilisateur, utilisez l'option d'authentification multi-facteur avec IBMid pour une connexion simple et sécurisée.
{: tip}

## Option d'authentification multi-facteur avec ID
{: #id-based}

L'authentification multi-facteur avec IBMid pour un compte exige un code d'accès à usage unique à durée limitée en complément d'un IBMid standard et d'un mot de passe lors de la connexion. Ce type d'authentification multi-facteur est activé au niveau du compte par le propriétaire du compte. Lorsque cette fonction est activée, vous devez utiliser la norme de sécurité supplémentaire lors de la connexion et tous les utilisateurs ajoutés à votre compte sont également requis. Ce type d'authentification multi-facteur s'applique à toutes les ressources de compte. Vous pouvez l'activer ou le désactiver à partir de la page **Gérer** > **Accès (IAM)** > **Paramètres** de la console {{site.data.keyword.Bluemix}} uniquement si vous êtes propriétaire du compte.

L'authentification multi-facteur avec IBMid est gratuite et est liée à votre ID et non uniquement au compte spécifique dans lequel vous vous trouvez, ce qui constitue un avantage. Si vous êtes membre de plusieurs comptes, il vous est demandé de vous authentifier une seule fois lorsque vous vous connectez à la console. Pour plus d'informations sur l'authentification multi-facteur avec IBMid, pour connaître les points à vérifier avant de demander une authentification multi-facteur avec IBMid pour votre compte et pour savoir comment configurer l'authentification multi-facteur avec IBMid, voir [Exigence de l'authentification multi-facteur pour les utilisateurs de votre compte](/docs/iam/mfa.html#setting-up-ibmid-mfa).

## Options d'authentification multi-facteur dépendant du compte
{: #account-based}

Un administrateur de compte doit autoriser la configuration d'une des options d'authentification multi-facteur suivante et son utilisation par un utilisateur de votre compte. Ce type d'authentification est lié à un compte actuel d'un utilisateur. Si un administrateur active une autre des options d'authentification multi-facteur pour chaque compte dont un utilisateur est membre, l'utilisateur est invité à s'authentifier différemment chaque fois qu'il change de compte. 

Si un propriétaire de compte exige l'authentification multi-facteur avec IBMid pour tous les utilisateurs du compte, cette méthode remplace toute autre option d'authentification multi-facteur activée et configurée dans un compte d'utilisateur. C'est pourquoi, même si un utilisateur a d'autres options d'authentification multi-facteur (comme la configuration suivante), l'utilisateur n'est pas invité à les appliquer lors de la connexion.

Les options d'authentification multi-facteur suivantes sont disponibles uniquement avec les anciens comptes d'infrastructure classique.

<dl>
<dt>Authentification par code d'accès à usage unique à durée limitée (TOTP)</dt>
<dd>L'authentification TOTP peut être configurée en utilisant une application d'authentification. Un propriétaire ou un administrateur de compte peut activer ce paramètre pour un utilisateur sur la page Détails de l'utilisateur uniquement si l'utilisateur a configuré l'authentification sur la page Paramètres de connexion du profil. Si ce paramètre est activé pour un utilisateur, ce dernier est invité à indiquer le code d'accès lors de la connexion. En activant ou désactivant l'option Connexion gérée par l'utilisateur qui se trouve sur la page Détails de l'utilisateur, les utilisateurs peuvent gérer leurs propres paramètres de connexion.</dd>
<dt>Questions de sécurité</dt>
<dd>Les utilisateurs peuvent configurer les réponses aux questions de sécurité disponibles sur la page Paramètres de connexion du profil. L'utilisateur doit configurer les questions de sécurité et les réponses avant qu'un propriétaire ou un administrateur de compte puisse activer ce paramètre sur la page Détails de l'utilisateur. En activant ou désactivant l'option Connexion gérée par l'utilisateur qui se trouve sur la page Détails de l'utilisateur, les utilisateurs peuvent gérer leurs propres paramètres de connexion. </dd>
<dt>Authentification externe</dt>
<dd>Il existe deux options d'authentification tierces externes pouvant être commandées à un coût mensuel : authentification Symantec et authentification par téléphone. Un propriétaire ou un administrateur de compte doit commander ces options pour un utilisateur et les activer sur la page Détails de l'utilisateur afin qu'elles puissent être utilisées. Pour Symantec, l'administrateur doit contacter l'utilisateur afin d'obtenir son ID de données d'identification pour effectuer la commande. Pour configurer l'authentification par téléphone, l'administrateur doit tout d'abord commander cette authentification puis l'utilisateur doit la configurer sur la page Détails de l'utilisateur afin que l'administrateur puisse l'activer. En activant ou désactivant l'option Connexion gérée par l'utilisateur qui se trouve sur la page Détails de l'utilisateur, les utilisateurs peuvent gérer leurs propres paramètres de connexion.</dd>
</dl>

Pour plus d'informations sur la configuration des options d'authentification multi-facteur, voir [Configuration de la sécurité de connexion](/docs/account/login_settings.html#login-settings). Si vous êtes propriétaire ou administrateur de compte et que vous gérez les paramètres de connexion d'autres utilisateurs ou si vous avez la possibilité de gérer vos propres paramètres de connexion, voir [Gestion des paramètres de connexion d'un utilisateur](/docs/iam/user_login.html#loginsettings).

