---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

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

Quando você remove um usuário da conta, o usuário não pode mais efetuar login no console, alternar para conta nem acessar recursos da conta.
{:shortdesc}

Somente proprietários da conta ou usuários com o acesso a seguir podem remover usuários de uma conta:

* Uma política do IAM para o serviço de gerenciamento de conta de gerenciamento de usuários com a função de Administrador designada e ser o gerente da organização do Cloud Foundry se o usuário pertencer a uma organização do Cloud Foundry.
* Se você tiver a infraestrutura clássica em sua conta, um usuário deverá ser um antecessor do usuário na hierarquia do usuário da infraestrutura clássica com a permissão Gerenciar infraestrutura clássica do usuário designada. Também deve-se ter uma política do IAM para o Serviço de gerenciamento de conta de gerenciamento de usuário com a função Administrador designada ou ser o gerente da organização Cloud Foundry se o usuário pertencer a uma organização Cloud Foundry.

Para remover um usuário de uma conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Na linha do usuário que você deseja remover, selecione **Remover usuário** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg).

Se você obtiver uma mensagem de erro de que um usuário de infraestrutura clássica não pode ser removido, certifique-se de que qualquer descendente na hierarquia do usuário para esse usuário tenha [um novo pai designado](/docs/iam?topic=iam-update-parent), tenha sido [desativado na conta](/docs/iam?topic=iam-status) ou excluído e, em seguida, tente novamente.
{: tip}
