---

copyright:

  years: 2018, 2019
lastupdated: "2019-03-05"

keywords: MFA, multifactor authentication, IBMid MFA, two-factor authentication, account MFA, time-based one-time passcode, TOTP

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Exigence de l'authentification multi-facteur pour les utilisateurs de votre compte
{: #enablemfa}

En tant qu'administrateur ou propriétaire de compte {{site.data.keyword.Bluemix}} pour le service de facturation, vous pouvez choisir que l'authentification multi-facteur (MFA) soit exigée pour chaque utilisateur du compte. Tous les utilisateurs ayant un IBMid utilisent une méthode d'authentification multi-facteur avec un code d'accès à usage unique à durée limitée (TOTP). Tout utilisateur ayant un autre type d'ID doit pouvoir utiliser séparément la méthode d'authentification externe, la méthode utilisant des questions de sécurité ou la méthode TOTP.  
{:shortdesc}

## Avant de commencer
{: #considerations}

Consultez les remarques suivantes avant d'activer l'authentification multi-facteur avec IBMid pour votre compte afin de savoir comment elle affecte tous les utilisateurs de votre compte :

* Lorsque vous activez l'authentification multi-facteur (MFA) pour votre compte, les utilisateurs doivent se soumettre au processus d'authentification multi-facteur lors de la connexion.
* Les clés d'API pour vos utilisateurs et les ID de service continuent de fonctionner après l'activation de l'authentification multi-facteur.
* Si la connexion par interface de ligne de commande CF ou interface utilisateur dans Cloud Foundry est nécessaire, vous devez utiliser des clés d'API ou un code d'accès unique une fois que l'authentification multi-facteur est activée pour le compte.
* L'authentification multi-facteur pour votre compte s'applique à la connexion d'un utilisateur mais ne s'applique pas aux appels d'API. Si un utilisateur dispose des droits lui permettant d'effectuer des appels d'API vers des ressources de votre compte, il peut effectuer cette même action sans procéder à l'authentification multi-facteur. Si l'utilisateur appartient à d'autres comptes, il peut effectuer des appels d'API vers des ressources de votre compte en utilisant une clé d'API d'un compte pour lequel l'authentification multi-facteur n'est pas requise.
* Si vous êtes un utilisateur fédéré, l'authentification multi-facteur n'est pas prise en charge.
* Si vous exigez que votre compte utilise l'authentification multi-facteur et que certains utilisateurs de votre compte n'ont pas d'IBMid, vous devez activer une des autres options d'authentification multi-facteur pour cet utilisateur sur la page Détails de l'utilisateur de la console {{site.data.keyword.Bluemix_notm}}. Pour plus d'informations, voir [Types d'authentification multi-facteur](/docs/iam?topic=iam-types#types).
* Planifiez une stratégie de communication et de support pour les utilisateurs ajoutés à votre compte :
  * Choisissez une date et une heure d'activation de l'authentification multi-facteur dont l'impact sur votre activité doit être minimal.
  * Une fois l'authentification multi-facteur activée, informez les utilisateurs de votre compte en leur envoyant des informations leur expliquant comment la [configurer](/docs/iam?topic=iam-enablemfa#setupapp).

Lorsque le paramètre de compte d'authentification multi-facteur est activé, tous les utilisateurs IBMid de votre compte sont invités à choisir l'authentification multi-facteur IBMid lors de la connexion. Si vous avez d'autres méthodes d'authentification multi-facteur configurées pour des utilisateurs IBMid de votre compte, ces derniers ne sont plus invités à appliquer ces méthodes d'authentification multi-facteur.
{: tip}

## Activation de l'authentification multi-facteur pour tous les utilisateurs de votre compte
{: #enabling}

Pour activer l'authentification multi-facteur (MFA), vous devez être administrateur ou propriétaire du compte pour le service de gestion de compte de facturation. Cette activation n'a pas d'incidence sur les utilisateurs déjà connectés, vu que l'application de l'authentification multi-facteur sur le compte ne prend effet que lors des nouvelles connexions. Pensez à notifier vos utilisateurs de compte que l'authentification multi-facteur est activée et indiquez-leur les conséquences de cette authentification lors de la prochaine connexion.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Paramètres**.
2. Sélectionnez **Mettre à jour** pour le paramètre Connexion au compte.
3. Sélectionnez **Aucun(e)** ou **Utilisateurs non fédérés uniquement** en fonction du type d'authentification devant être exigé.
4. si vous avez sélectionné l'option Utilisateurs non fédérés uniquement, sélectionnez la case à cocher pour confirmer que vous avez bien compris les conséquences liées à l'authentification multi-facteur pour les utilisateurs de votre compte. 
5. Cliquez sur **Sauvegarder**.

## Configuration de votre authentification TOTP
{: #setupapp}

Une fois l'authentification multi-facteur (MFA) activée pour votre compte, vous devez configurer le code d'accès à utilisation unique avec une application d'authentification à votre prochaine connexion. Tous les utilisateurs de votre compte doivent également utiliser le code d'accès à utilisation unique à leur prochaine connexion.

Procédez comme suit pour configurer votre code d'accès à utilisation unique avec une application d'authentification pour la première fois :

1. Connectez-vous avec votre IBMid et le mot de passe associé.

  Cinq minutes peuvent s'écouler avant que vous ne puissiez vous reconnecter avec l'authentification multi-facteur.
  {: note}

2. Sélectionnez **Verify** sur l'écran **Verification is required** pour configurer l'authentification multi-facteur avec une application d'authentification.
3. Sélectionnez **Setup your authenticator app** pour obtenir un code d'accès à utilisation unique envoyé à votre adresse électronique afin de pouvoir continuer à configurer l'application d'authentification.
4. Sélectionnez **Verify**.
5. Scannez le code à barres avec votre application ou cliquez sur **Can't scan the bar?** pour entrer une clé.
6. Cliquez sur **Continue** pour entrer votre code.
7. Entrez votre code et sélectionnez **Verify**.

Si un message d'erreur s'affiche vous indiquant que vous avez déjà configuré l'authentification, mais que votre code de vérification ne fonctionne pas ou si vous ne disposez pas du code de vérification à saisir, vous devez contacter le [centre d'assistance](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe") pour réinitialiser votre inscription à l'authentification multi-facteur (MFA).
{: note}
{: #mfahelp}

## Désactivation de l'authentification multi-facteur requise pour tous les utilisateurs de votre compte
{: #disablemfa}

Pour désactiver l'authentification multi-facteur, vous devez être administrateur ou propriétaire du compte pour le service de facturation de gestion de compte. La désactivation de l'authentification multi-facteur n'a aucune incidence sur les utilisateurs déjà connectés. Cette action prend effet lors de toute nouvelle connexion.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Paramètres**.
2. Sélectionnez **Editer** pour le paramètre Connexion au compte.
3. Sélectionnez **Aucun(e)**.
4. Cliquez sur **Sauvegarder**.

