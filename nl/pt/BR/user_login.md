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

# Gerenciando as configurações de login de um usuário 
{: #loginsettings}

Um proprietário da conta ou um usuário que tem o acesso correto pode gerenciar as configurações de login de um usuário, por exemplo, pedir opções de autenticação externa, ativar uma senha descartável a ser usada durante o login, ativar o uso de perguntas de segurança no login e configurar um prazo de expiração de senha.
{:shortdesc}

Conclua as etapas a seguir para gerenciar as configurações de login para um usuário específico:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**. 
2. Selecione um usuário na lista e clique em **Detalhes do usuário**. 
3. Na seção **Gerenciar login do usuário**, é possível ativar ou desativar as opções a seguir para o usuário selecionado: 
    
    * MFA com senha descartável baseada em tempo: ative essa opção para permitir que o usuário seja solicitado a fornecer a senha descartável no login. O usuário deve configurar a MFA TOTP por meio da página Configurações de login. Para obter mais informações, veja [Ativando a MFA de senha descartável para um usuário](/docs/iam?topic=iam-totp#totp).
    
    * Pedir autenticação externa: selecione essa opção para comprar a autenticação da Symantec ou com base em telefone por um custo mensal. Somente uma opção pode ser pedida e usada por vez. Para obter mais informações, veja [Pedindo a autenticação externa MFA para um usuário](/docs/iam?topic=iam-external#external).

        * Autenticação baseada em telefone: o usuário pode usar essa opção usando a configuração que ele definiu na página Detalhes do usuário após o pedido do proprietário da conta. 
        * Autenticação da Symantec: o usuário pode usar a opção após o pedido do proprietário da conta. Para que um administrador peça essa opção, o usuário deve fornecer seu ID de credencial primeiro.

    * Perguntas de segurança de MFA no login: ative essa opção para requerer que um usuário seja solicitado a fornecer perguntas e respostas de segurança que ele configurou na página Configurações de login. Não é possível ativar essa opção, a menos que o usuário já tenha configurado suas perguntas de segurança. Para obter mais informações, veja [Ativando perguntas de segurança de MFA para um usuário](/docs/iam?topic=iam-questions#questions).

    * Login gerenciado pelo usuário: ative essa opção para permitir que o usuário configure uma expiração de senha, ative as perguntas de segurança para login e especifique endereços IP permitidos para APIs de login e de infraestrutura clássica do {{site.data.keyword.cloud_notm}}. 

    * Expiração de senha: configure uma expiração selecionando uma opção na lista. Essa opção está disponível somente para usuários com um ID do SoftLayer. Se o usuário puder gerenciar suas próprias configurações de login, ele poderá configurar essa expiração em sua página Configurações de login. Somente usuários com as permissões a seguir podem configurar uma expiração de senha para um usuário:
        
        * Qualquer usuário designado a uma política do IAM com a função de Editor ou superior no serviço de gerenciamento de usuários.
        * Qualquer usuário que tenha Login gerenciado pelo usuário ativado em sua página Detalhes do usuário por seu administrador.
        * Qualquer antecessor na hierarquia de infraestrutura clássica para o usuário com a permissão Gerenciar a infraestrutura clássica de usuários designada.

Somente uma opção de MFA deve ser ativada por vez. Se a MFA do IBMid for necessária para qualquer conta da qual o usuário é um membro, ela substituirá qualquer outra MFA que estiver ativada e o usuário não será solicitado a fornecer nenhum outro tipo de MFA.
{: important}



