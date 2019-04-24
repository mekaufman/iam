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

# Tipos de autenticação de diversos fatores
{: #types}

A autenticação de diversos fatores (MFA) inclui uma camada extra de segurança em sua conta, requerendo que todos os usuários se autentiquem usando um método de autenticação adicional além de um ID e uma senha. Isso também é conhecido geralmente como autenticação de dois fatores (2FA).
{:shortdesc}

Os dois tipos de opções de MFA a seguir podem ser ativados para sua conta:

<dl>
<dt>MFA baseada em ID</dt>
<dd>Uma opção que é ativada por um proprietário da conta em uma das contas para as quais você é um membro. Esse tipo de MFA é associado com o seu IBMid e autentica você ao longo de todas as contas das quais é um membro. Portanto, é necessário se autenticar somente uma vez.</dd>
<dt>Opções baseadas em conta</dt>
<dd>Opções como perguntas de segurança, usando uma senha descartável baseada em tempo, e opções de autenticação externa, como a autenticação da Symantec e baseada em telefone. Esses tipos de MFA são específicos por conta, o que significa que, se você tem um tipo diferente configurado para cada conta à qual pertence, deve-se autenticar de uma maneira diferente cada vez que alterna as contas. Essas opções de MFA anteriores estão disponíveis somente com contas antigas de infraestrutura clássica.</dd>
</dl>

A MFA do IBMid satisfaz o requisito de autenticação para que você não seja solicitado a fornecer quaisquer outros tipos de MFA mesmo se eles estiverem ativados. Portanto, se algum proprietário de uma conta na qual você é um membro ativar essa opção, esse será o único tipo de MFA solicitado no login. Se você for um novo usuário, use a opção MFA do IBMid baseada em ID para assegurar que seu login seja fácil e seguro.
{: tip}

## Opção MFA baseada em ID
{: #id-based}

A MFA do IBMid para uma conta requer uma senha descartável baseada em tempo, além de um IBMid padrão e uma senha durante o login. Esse tipo de MFA é ativado no nível de conta pelo proprietário da conta. Quando esse recurso está ativado, você deve usar o padrão de segurança extra no login e todos os usuários incluídos em sua conta também. Esse tipo de MFA se aplica a todos os recursos da conta. Será possível ativá-lo ou desativá-lo na página **Gerenciar** > ** Acesso (IAM)** > **Configurações** no console do {{site.data.keyword.Bluemix}} somente se você for o proprietário da conta.

Um dos benefícios da MFA do IBMid é que ela é gratuita e ligada ao seu ID, em vez de apenas à conta específica em que você está. Se você pertencer a muitas contas, será necessário se autenticar somente uma vez quando efetuar login no console. Para obter mais informações sobre a MFA do IBMid, as considerações que devem ser revisadas antes de você requerer a MFA do IBMid para sua conta e como configurá-la você mesmo, veja [Requerendo MFA para usuários em sua conta](/docs/iam/mfa.html#setting-up-ibmid-mfa).

## Opções de MFA baseadas em conta
{: #account-based}

Um administrador de conta deve ativar qualquer uma das opções de MFA a seguir para ser configurada e usada por um usuário na conta. Esse tipo de MFA é ligado à conta atual de um usuário. Se um administrador ativar uma opção de MFA diferente para cada conta na qual um usuário for um membro, o usuário será solicitado a autenticar-se de uma maneira diferente cada vez que alternar as contas. 

Se um proprietário da conta requerer a MFA do IBMid para todos os usuários na conta, esse método substituirá qualquer outra opção de MFA que estiver ativada e configurada na conta de um usuário. Portanto, mesmo se um usuário tiver outras opções de MFA, como a configuração a seguir, elas não serão solicitadas ao usuário no login.

As seguintes opções de MFA anteriores estão disponíveis somente com as antigas contas de infraestrutura clássica.

<dl>
<dt>Autenticação de senha descartável baseada em tempo (TOTP)</dt>
<dd>A TOTP pode ser configurada usando um app de autenticação. Um proprietário ou um administrador da conta poderá ativar essa configuração para um usuário na página Detalhes do usuário somente se o usuário configurar a autenticação na página Configurações de login do perfil. Se essa configuração estiver ativada para um usuário, a senha será solicitada a ele durante o login. Os usuários com acesso para gerenciar suas próprias configurações de login, tendo a configuração Login gerenciado pelo usuário ativada em sua página Detalhes do usuário, podem ativá-la e desativá-la.</dd>
<dt>Perguntas de segurança</dt>
<dd>Os usuários podem configurar respostas para as perguntas de segurança que estão disponíveis na página Configurações de login do perfil. O usuário deve configurar as perguntas e respostas de segurança antes que um proprietário ou um administrador da conta possa ativar essa configuração na página Detalhes do usuário. Os usuários com acesso para gerenciar suas próprias configurações de login, tendo a configuração Login gerenciado pelo usuário ativada em sua página Detalhes do usuário, podem ativá-la e desativá-la. </dd>
<dt>Autenticação externa</dt>
<dd>Há duas opções de autenticação externa de terceiros que podem ser pedidas por um custo mensal: a autenticação da Symantec e baseada em telefone. Um proprietário ou um administrador da conta deve solicitar essas opções para um usuário e ativá-las para serem usadas na página Detalhes do usuário para o usuário. Para a Symantec, o administrador deve trabalhar com o usuário para obter o ID de credencial desse usuário para concluir a ordem. E, para configurar a autenticação baseada em telefone, o administrador deve pedi-la e, em seguida, o usuário deve configurá-la em sua página Detalhes do usuário para que o administrador possa ativá-la para o uso. Os usuários com acesso para gerenciar suas próprias configurações de login, tendo a configuração Login gerenciado pelo usuário ativada em sua página Detalhes do usuário, podem ativá-la e desativá-la.</dd>
</dl>

Para obter mais informações sobre a configuração de opções de MFA, veja [Configurando a segurança de login](/docs/account/login_settings.html#login-settings). E, se você for um proprietário ou um administrador da conta que gerencia as configurações de login de outros usuários ou tiver a capacidade de gerenciar suas próprias configurações de login, veja [Gerenciando as configurações de login de um usuário](/docs/iam/user_login.html#loginsettings).

