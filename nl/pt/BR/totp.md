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

# Ativando a MFA de senha descartável para um usuário
{: #totp}

Como um administrador com o acesso correto, é possível ativar a opção para que um usuário seja solicitado a fornecer uma senha descartável baseada em tempo (TOTP) no login por meio da página Detalhes do usuário no console do {{site.data.keyword.Bluemix}}. Esse tipo de autenticação de diversos fatores (MFA) é necessário somente para a conta na qual a configuração está ativada, diferentemente da MFA baseada em ID. Para obter mais informações, veja [Tipos de autenticação de diversos fatores](/docs/iam?topic=iam-types#types).
{:shortdesc}

Se você tiver qualquer um dos acessos a seguir, será possível atualizar essa configuração para outros usuários em sua conta:

* Função de Editor ou superior no serviço de gerenciamento de usuários
* Você é um antecessor na hierarquia de infraestrutura clássica para o usuário e tem a permissão Gerenciar a infraestrutura clássica de usuários designada

Para ativar a configuração de login para que um usuário seja solicitado para a MFA TOTP, conclua as etapas a seguir.

Para ativar essa opção de MFA para um usuário, ele ou ela deverá primeiro [configurar a TOTP](/docs/account?topic=account-MFA#MFA) na página Configurações de login do perfil.
{: note}

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Selecione um usuário da lista.
3. Na página **Detalhes do usuário** na seção **Gerenciar login do usuário**, configure a opção **MFA com senha descartável baseada em tempo** como ativada.

Será possível gerenciar essa configuração para si mesmo se você tiver a configuração Login gerenciado pelo usuário ativada na página Detalhes do usuário.
{: tip}

