---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gerenciando o acesso aos recursos
{: #iammanidaccser}

Para gerenciar o acesso ou designar um novo acesso para usuários usando políticas do IAM, deve-se ser o proprietário da conta, o administrador em todos os serviços na conta ou o administrador designado para o serviço ou a instância de serviço específica. Para obter mais informações sobre funções e políticas de acesso, veja [Acesso ao IAM](/docs/iam?topic=iam-userroles#userroles).
{:shortdesc} 

## Editando acesso existente
{: #edit_existing}

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Selecione o nome do usuário para o qual você deseja designar acesso.
3. Na linha para a política que você deseja editar, selecione o menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) e, em seguida, clique em **Editar política**.
4. Edite a política.
5. Clique em **Salvar**.

Para atualizar uma política do usuário usando a CLI, é possível usar o comando [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_update).
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

Ao editar o acesso para um usuário ou um grupo, você pode receber uma mensagem sobre não permitir políticas duplicadas. Se você estiver editando uma política existente e as mudanças feitas estiverem em conflito com o acesso que já está designado, será possível escolher mudar a política que está sendo editada atualmente para fornecer acesso diferente ou ir para a política existente com a qual está em conflito para revisar e fazer mudanças, se necessário. Você poderá desejar excluir a política que está sendo editada, se já existir uma política duplicada que atenda às suas necessidades.
{: note}

## Designando novo acesso
{: #assign_new_access}

É possível designar acesso ao recurso usando dois tipos de políticas: 

* Acesso aos recursos dentro de um grupo de recursos, incluindo a opção para apenas um ou todos
* Acesso aos recursos na conta, incluindo a opção para apenas um tipo ou todos os tipos

Se você deseja permitir que um usuário tenha acesso total de administrador para concluir tarefas de [gerenciamento de conta](/docs/iam?topic=iam-account-services#account-services), como convidar e remover usuários, visualizar faturamento e uso, gerenciar IDs de serviço, gerenciar grupos de acesso, gerenciar acesso de usuário e acesso a todos os recursos da conta, deve-se criar duas políticas: uma em **Todos os serviços ativados pelo Identity and Access** com o administrador de função e outra em **Todos os serviços de gerenciamento de conta** com o administrador de função.
{: tip}

### Acesso aos recursos dentro de um grupo de recursos 
{: #access_to_resources}

Para designar acesso a todos os recursos em um grupo de recursos ou a apenas um serviço em um grupo de recursos, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Na linha para o usuário que você deseja designar acesso, selecione o menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) e, em seguida, clique em **Designar acesso**.
3. Selecione **Designar acesso dentro de um grupo de recursos**.
4. Selecione um grupo de recursos.
5. Escolha uma função para o campo **Designar acesso a um grupo de recursos** para permitir que o usuário visualize o grupo de recursos em sua lista de recursos, edite o nome do grupo de recursos ou gerencie o acesso de usuário ao grupo. Será possível selecionar **Sem acesso**, se desejar que o usuário tenha acesso somente ao recurso especificado e não ao grupo no qual ele está organizado.
6. Selecione um serviço no grupo de recursos ou opte por fornecer acesso a todos os serviços no grupo selecionado.
7. Escolha qualquer combinação de funções para designar o acesso desejado ao usuário. Este acesso só se aplica aos recursos que você selecionou para a política. Ele não fornece acesso ao contêiner real que é o grupo de recursos.
8. Clique em **Designar**.

### Acesso a recursos
{: #resourceaccess}

Para designar acesso a um recurso individual na conta ou acesso a todos os recursos na conta, conclua as etapas a seguir: 

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Na linha para o usuário que você deseja designar acesso, selecione o menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) e, em seguida, clique em **Designar acesso**.
3. Selecione **Designar acesso a recursos**.
4. Selecione um serviço ou selecione **Todos os serviços ativados pelo Identity and Access**.
5. Selecione **Todas as regiões atuais** ou uma região específica, se solicitado. 
6. Selecione **Todas as instâncias de serviço atuais** ou selecione uma instância de serviço específica.
7. Dependendo do serviço que você selecionou, será possível ver os campos a seguir. Se você não inserir valores para esses campos, a política será designada no nível da instância de serviço em vez de no nível do depósito. 
    * **Tipo de recurso**: insira **depósito**.
    * **ID do recurso**: Insira o nome do bucket.
8. Escolha qualquer combinação de funções para designar o acesso desejado ao usuário.
9. Clique em **Designar**.

## Removendo o acesso
{: #removing_access}

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Selecione o nome do usuário para o qual você deseja remover o acesso.
3. Na guia **Políticas de acesso**, selecione o menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) na linha para a política que você deseja remover e clique em **Remover**.  
4. Revise os detalhes da política do usuário que você está prestes a remover e, em seguida, confirme clicando em **Remover**.

Para remover uma política do usuário usando a CLI, é possível usar o comando [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_delete#ibmcloud_iam_user_policy_delete).
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## Revisando seu acesso designado
{: #review_your_access}

Se for necessário revisar o acesso designado em uma conta à qual você foi incluído, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
3. Selecione seu nome.
4. Revise seu acesso designado na seção **Políticas de acesso**.

Se você precisa de mais acesso, deve-se entrar em contato com o proprietário da conta para atualizar seu acesso ou entrar em contato com o administrador para o serviço ou instância de serviço para atualizar a política de acesso do Cloud IAM.
