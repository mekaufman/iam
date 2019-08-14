---

copyright:

  years: 2018, 2019

lastupdated: "2019-08-08"

keywords: remove user, delete user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Removendo usuários de uma conta
{: #remove}

Quando você remove um usuário de uma conta, o usuário não pode mais efetuar login no console, alternar para sua conta se ele ainda pertencer à outra conta ou acessar recursos da conta.
{:shortdesc}

Somente proprietários da conta ou usuários com o acesso a seguir podem remover usuários de uma conta:

* Uma política do IAM para o serviço de gerenciamento de conta de gerenciamento de usuários com a função de Administrador designada e ser o gerente da organização do Cloud Foundry se o usuário pertencer a uma organização do Cloud Foundry.
* Se você tiver uma infraestrutura clássica em sua conta, um usuário deverá ter uma política do IAM para o serviço de gerenciamento de conta de Gerenciamento de usuário com a função de Administrador designada, ser o gerenciador de organização do Cloud Foundry se o usuário pertencer a uma organização do Cloud Foundry e ser um antecessor do usuário na hierarquia do usuário da infraestrutura clássica com a permissão Gerenciar infraestrutura clássica do usuário designada.

Para remover um usuário de uma conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Na linha do usuário que você deseja remover, selecione **Remover usuário** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg).

Quaisquer recursos criados pelo usuário permanecem na conta. No entanto, o usuário não tem mais acesso para trabalhar com esses recursos, portanto, o proprietário da conta ou um administrador desse serviço ou instância de serviço pode designar outros usuários para trabalhar com os recursos ou excluí-los da conta.

Se você obtiver uma mensagem de erro informando que um usuário de infraestrutura clássica não pode ser removido, certifique-se de que quaisquer descendentes na hierarquia de usuário desse usuário tenham sido [designados a um novo pai](/docs/iam?topic=iam-update-parent), [desativados na conta](/docs/iam?topic=iam-status) ou excluídos e, em seguida, tente novamente.
{: tip}
