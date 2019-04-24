---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

keywords: access groups, access group, create group, assign access to group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Configurando grupos de acesso
{: #groups}

Um grupo de acesso pode ser criado para organizar um conjunto de usuários e IDs de serviço em uma única entidade que torne mais fácil para você designar acesso. É possível designar uma política única ao grupo em vez
de designar o mesmo acesso múltiplas vezes por usuário ou ID de serviço individual.
{:shortdesc}

Para gerenciar ou criar novos grupos de acesso, deve-se ser o proprietário da conta, o administrador ou o editor no serviço de Grupos de acesso do IAM na conta ou o administrador ou editor designado para todos os Serviços de Gerenciamento de Conta. Além disso, um administrador ou editor pode ter acesso designado para gerenciar um grupo individual criando
uma política de acesso em que o recurso é o ID do grupo de acesso. Para obter mais informações sobre políticas de acesso e funções para o serviço de Grupos de acesso do IAM, veja [Acesso do IAM](/docs/iam?topic=iam-userroles#userroles).

Para facilitar ainda mais a designação e o gerenciamento de acesso, é possível configurar
grupos de recursos para organizar um conjunto de recursos ao qual você deseja que um grupo de usuários
tenha acesso. Quando seu grupo de recursos é configurado, é possível designar uma política fornecendo acesso a
todos os recursos dentro desse grupo em vez de criar políticas de acesso para instâncias de serviço
individuais dentro de sua conta.
{: tip}

## Criando um grupo de acesso
{: #create_ag}

Para criar um grupo de acesso, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Clique em **Criar**.
3. Insira um nome e uma descrição opcional para seu grupo e clique em **Criar**.

Em seguida, continue a configurar seu grupo incluindo usuários ou IDs de serviço:

1. Selecione o nome do grupo que deseja incluir.
2. Clique em **Incluir usuários** na guia **Usuários**.
3. Selecione os usuários que deseja incluir na lista e clique em **Incluir no grupo**.
4. Para incluir IDs de serviço no grupo, clique na guia **IDs de serviço** e
clique em **Incluir ID de serviço**.
5. Selecione os IDs que deseja incluir na lista e clique em **Incluir no grupo**.

É possível excluir um grupo selecionando a opção **Remover grupo**. Ao remover um grupo da conta, você está removendo todos os usuários e IDs de serviço do grupo e todo o acesso que é designado ao grupo.
{: note}

Para criar um grupo de acesso usando a CLI, é possível usar o comando [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create).
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}


## Designando acesso a um grupo
{: #access_ag}

Depois de configurar seu grupo com usuários e IDs de serviço, é possível designar uma política de acesso
comum para o grupo. Lembre-se, qualquer política que você configura para o grupo se aplica a todas as
entidades dentro do grupo.

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Selecione o nome do grupo ao qual você deseja designar acesso.
3. Clique em **Políticas de acesso**.
4. Clique em **Designar acesso**.
5. Escolha para designar acesso por recursos dentro de um grupo de recursos, recursos individuais disponíveis dentro da conta ou serviços de gerenciamento de conta.

Para criar uma política de grupo de acesso usando a CLI, é possível usar o comando [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create).
```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}
