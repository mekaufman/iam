---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: remove user, delete user, user management

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Removendo usuários
{: #remove}

Quando você remove um usuário da conta, ele não pode mais efetuar login no console, alternar para sua conta (se ele ainda pertence a outra conta) nem acessar recursos da conta.
{:shortdesc}

Somente proprietários da conta ou usuários com o acesso a seguir podem remover usuários de uma conta:

* Uma política do IAM para o serviço de gerenciamento de conta de gerenciamento de usuários com a função de Administrador designada e ser o gerente da organização do Cloud Foundry se o usuário pertencer a uma organização do Cloud Foundry.
* Se você tiver uma infraestrutura clássica em sua conta, um usuário deverá ter uma política do IAM para o serviço de gerenciamento de conta de gerenciamento de usuários com a função de Administrador designada, ser o gerente da organização do Cloud Foundry se o usuário pertencer a uma organização do Cloud Foundry e ser um antecessor do usuário na hierarquia do usuário de infraestrutura clássica com a permissão Gerenciar a infraestrutura clássica de usuários designada.

Para remover um usuário de uma conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Na linha do usuário que você deseja remover, selecione **Remover usuário** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg).
