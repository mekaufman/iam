---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: Cloud Foundry access, assign access, add user to organization, Cloud Foundry roles

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gerenciando o acesso ao Cloud Foundry
{: #mngcf}

Para gerenciar o acesso a organizações e espaços da conta, deve-se ser o proprietário da conta, gerenciador de organização ou gerenciador de espaço.
{:shortdesc}

## Atualizando o acesso ao Cloud Foundry
{: #update_cf_access}

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Na linha para o usuário que você deseja designar acesso, selecione o menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) e, em seguida, clique em **Designar acesso**.
3. Selecione **Designar usando o Cloud Foundry**.
4. Expanda a linha para a organização à qual o usuário está designado para visualizar o acesso do usuário aos espaços e suas funções nesses espaços.
5. No menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) na seção Cloud Foundry, é possível:

  * Remover o usuário da organização
  * Editar a função de organização
  * Editar a função de espaço

## Incluindo um usuário em uma organização
{: #add_to_org}

Caso seja o gerenciador de uma organização da qual o usuário ainda não é um membro, você designará o usuário a essa organização.

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Na linha para o usuário que você deseja designar acesso, selecione o menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) e, em seguida, clique em **Designar acesso**.
3. Selecione **Designar usando o Cloud Foundry**.
4. Selecione **Designar organização**.
5. Designe o acesso de usuário:
   * Escolha uma organização na qual incluir o usuário
   * Designe uma função de organização
   * Escolha uma região
   * Escolha um espaço
   * Designe uma função de espaço
7. Clique em **Designar**.

## Revisando seu acesso designado
{: #review_my_access}

Se for necessário revisar seu acesso designado em uma conta à qual tenha sido incluído, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Selecione seu nome.
3. Clique em **Acesso do Cloud Foundry**.
3. Expanda a linha da organização e revise suas funções designadas.

Se você precisa de acesso adicional, deve-se entrar em contato com o gerenciador de organização ou proprietário da conta para atualizar sua função designada do Cloud Foundry.
