---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gerenciando políticas de acesso do ID de serviço
{: #serviceidpolicy}

Ao criar um ID do serviço, é possível designar políticas de serviço para esse ID do serviço para controlar o nível de acesso que é permitido quando ele é usado para autenticar com seus serviços. É possível atualizar essas políticas de acesso designadas a qualquer momento mudando uma política existente, excluindo uma política ou designando uma nova.
{:shortdesc}

Se você excluir ou editar uma política existente para um ID do serviço atualmente sendo usado, isso poderá causar a interrupção do serviço.
{: note}

## Designando novo acesso
{: #access_new}

Para designar acesso a todos os recursos em um grupo de recursos ou a apenas um serviço em um grupo de recursos, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **IDs de serviço**.
2. Selecione o ID de serviço na tabela para a qual você deseja designar uma política de serviço.
3. Clique em **Políticas de acesso**.
4. Clique em **Designar acesso**.
5. Selecione **Designar por grupo de recursos**.
6. Selecione um grupo de recursos.
7. Escolha uma função para o campo **Designar acesso ao grupo de recursos**. Essa opção permite que o usuário visualize o grupo de recursos em sua lista de recursos, edite o nome do grupo de recursos ou gerencie o acesso de usuário ao grupo. Será possível selecionar **Sem acesso**, se desejar que o usuário tenha acesso somente ao recurso especificado e não ao grupo ao qual ele está designado.
8. Selecione um serviço no grupo de recursos ou opte por fornecer acesso a todos os serviços no grupo selecionado.
9. Escolha qualquer combinação de funções para designar o acesso desejado ao usuário. Este acesso só se aplica aos recursos que você selecionou para a política. Ele não fornece acesso ao contêiner real que é o grupo de recursos.
10. Selecione **Designar**.

Para designar acesso a um recurso individual na conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **IDs de serviço**.
2. Selecione o ID de serviço na tabela para a qual você deseja designar uma política de serviço.
3. 3. Clique em **Políticas de acesso**.
4. Clique em **Designar acesso**.
5. Selecione **Designar por recurso**.
6. Selecione um serviço.
7. Selecione **Todas as regiões atuais** ou uma região específica, se solicitado.
8. Selecione **Todas as instâncias de serviço atuais** ou selecione uma instância de serviço específica.
9. Dependendo do serviço que você selecionou, será possível ver os campos a seguir. Se você não inserir valores para esses campos, a política será designada no nível da instância de serviço em vez de no nível do depósito.
    * **Tipo de recurso**: insira **depósito**.
    * **ID do recurso**: Insira o nome do bucket.
10. Escolha qualquer combinação de funções para designar o acesso desejado ao usuário.
11. Selecione **Designar**.

Para designar acesso a um serviço de gerenciamento de conta individual ou a todos os serviços de gerenciamento de
conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e, em seguida, selecione **IDs de serviço**.
2. Selecione o ID de serviço na tabela para a qual você deseja designar uma política de serviço.
3. Clique em **Políticas de acesso**.
4. Clique em **Designar acesso**.
5. Selecione para designar acesso aos **Serviços de gerenciamento de conta**
6. Selecione **Todos os serviços de gerenciamento de conta** ou selecione um serviço de gerenciamento de conta específico.
7. Selecione qualquer combinação de funções para designar o acesso desejado.

Você pode receber uma mensagem de que existe uma política para os detalhes selecionados. Se uma política com os detalhes e as funções exatos estiver sendo criada, você será solicitado a fazer mudanças na nova política, pois as políticas duplicadas não são permitidas. Se você estiver criando uma política com os mesmos detalhes, mas designações de função diferentes de uma política existente, será solicitado que revise e atualize a política existente com as designações de função que deseja designar.
{: tip}

## Editando acesso existente
{: #access_edit}

Para editar uma política existente:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **IDs de serviço**.
2. Selecione o ID de serviço na tabela para a qual você deseja editar uma política de serviço.
3. Clique em **Políticas de acesso**.
4. Identifique a linha da política que você deseja editar e selecione **Editar política** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg).
5. Faça suas mudanças e, em seguida, salve a política.

Para atualizar uma política de serviço usando a CLI, é possível usar o comando [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_update#ibmcloud_iam_service_policy_update).
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

Ao editar o acesso para um ID do serviço, você pode receber uma mensagem sobre não permitir políticas duplicadas. Se você estiver editando uma política existente e as mudanças feitas estiverem em conflito com o acesso que já está designado, será possível escolher mudar a política que está sendo editada atualmente para fornecer acesso diferente ou ir para a política existente com a qual está em conflito para revisar e fazer mudanças, se necessário. Você poderá desejar excluir a política que está sendo editada, se existir uma política duplicada que atenda às suas necessidades.
{: tip}

## Removendo o acesso
{: #access_remove}

Para remover uma política existente:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **IDs de serviço**.
2. Selecione o ID de serviço na tabela da qual você deseja excluir uma política de serviço.
3. Clique em **Políticas de acesso**. 
4. Identifique a linha da política que você deseja excluir e selecione **Remover** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg).
5. Revise os detalhes da política que você está prestes a remover e, em seguida, clique em **Remover** para confirmar.

Para excluir uma política de serviço usando a CLI, é possível usar o comando [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_update#ibmcloud_iam_service_policy_delete).
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
