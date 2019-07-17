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

# Pedindo a MFA de autenticação externa para um usuário
{: #external}

Como administrador com o acesso correto, é possível solicitar autenticação
externa e ativar a opção de autenticação de diversos fatores (MFA) para o login de um
usuário. Você é cobrado por uma taxa mensal para as opções de autenticação externa. Esse tipo de autenticação de diversos fatores (MFA) é necessário somente para a conta na qual a configuração está ativada, diferentemente da MFA baseada em ID. Para obter mais informações, veja [Tipos de autenticação de diversos fatores](/docs/iam?topic=iam-types#types).
{:shortdesc}

## Pedindo autenticação externa
{: #ordering}

Se você tiver qualquer um dos acessos a seguir, será possível pedir a autenticação externa para um usuário:

* Função de Editor ou superior no serviço de gerenciamento de usuários
* Você é um antecessor na hierarquia de infraestrutura clássica para o usuário e tem a permissão Gerenciar a infraestrutura clássica de usuários designada

Para pedir autenticação externa, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Selecione um usuário da lista.
3. Na página **Detalhes do usuário**, selecione **Pedir autenticação externa** na seção Gerenciar login do usuário.
4. Selecione **Proteção de identidade da Symantec** ou **Proteção de identidade baseada em telefone**.
    * Para autenticação da Symantec, o usuário deve fazer download do app [Symantec VIP](https://vip.symantec.com/){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg) e obter um ID de credencial para continuar com o processo de pedido.
    * Para autenticação baseada em telefone, é possível continuar com a ordem, mas seu usuário deve [definir sua configuração](/docs/account?topic=account-login-settings#setting-up-phone-based-authentication) antes de poder ativar a opção.
5. Com base em sua seleção, siga os prompts para revisar o preço e os termos antes de colocar a ordem.
6. Clique em **Ordem** para finalizar a sua seleção.

Após a autenticação da Symantec ser pedida, é possível ativar a opção para o usuário na página Detalhes do usuário. E, após a autenticação baseada em telefone ser pedida e, em seguida, configurada pelo usuário, é possível ativar a opção para o usuário na página Detalhes do usuário.

## Desativando as opções de autenticação externa
{: #disable}

É possível desativar a MFA da Symantec ou baseada em telefone para um usuário a qualquer momento.

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Selecione um usuário da lista.
3. Na página **Detalhes do usuário**, configure a opção **Autenticação da Symantec** ou **Autenticação baseada em telefone** como desativada.

## Cancelando opções de autenticação externa
{: #cancel}

É possível cancelar sua ordem para autenticação externa a qualquer momento, se você tem o acesso correto. É possível escolher cancelar imediatamente sem nenhum reembolso ou escolher cancelá-la na marca de um ano a partir do momento em que foi pedida.

Para cancelar uma ordem para autenticação externa, deve-se ser um proprietário da conta ou ter todos os acessos a seguir:

* Permissão Gerenciar a infraestrutura clássica de usuários
* Permissão Cancelar a infraestrutura clássica de serviços
* Administrador para o serviço de gerenciamento de conta do Centro de Suporte ou as permissões de visualização, edição e inclusão de infraestrutura clássica migrada pelo chamado que não estão disponíveis nos [grupos de acesso de permissão migrados](/docs/iam?topic=iam-migrated_permissions).

Para cancelar a ordem de autenticação externa, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione Usuários.
2. Selecione um usuário da lista.
3. Na página **Detalhes do usuário**, clique em **Excluir** ![Ícone Excluir](../icons/icon_trash.svg) para a linha **Autenticação da Symantec** ou **Autenticação baseada em telefone**, dependendo da qual você solicitou.
4. Selecione quando removê-la.
5. Clique em **Remove**.
