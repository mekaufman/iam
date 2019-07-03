---

copyright:

  years: 2015, 2019

lastupdated: "2019-06-25"

keywords: invite, invite users, invitation access, vpn-only user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Convidando usuários
{: #iamuserinv}

Use o {{site.data.keyword.Bluemix}} Identity and Access Management (IAM) para convidar usuários, cancelar convites e reenviar um convite pendente para um usuário convidado. Além disso, é possível convidar um único usuário ou múltiplos usuários de uma vez.
{:shortdesc}

Para convidar usuários e gerenciar convites pendentes, deve-se ser um proprietário da conta, um gerenciador de organização, um usuário com uma política de acesso do IAM com a função de Editor ou superior no serviço de gerenciamento de usuários ou deve-se ter permissões de infraestrutura clássica para incluir usuários.

## Configurando um convite
{: #invitations}

Para convidar usuários ou gerenciar convites de usuários em sua conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Clique em **Convidar usuários**.
3. Especifique o endereço de e-mail do usuário. Se você estiver convidando mais de um usuário com um convite único, eles serão todos designados ao mesmo acesso.
4. Inclua uma ou mais das opções de acesso que você gerencia. Deve-se designar pelo menos uma opção de acesso. Para quaisquer opções de acesso adicionais que você não incluir nem configurar, o valor padrão de
**no access** é designado. É possível ver uma ou todas as seguintes opções de acesso, dependendo
das opções que você estiver autorizado a gerenciar:

  * **Serviços  **
  * **Acesso ao Cloud Foundry**
  * **Acesso de infraestrutura clássica**.

  Para obter mais informações, veja [Designando acesso de usuário](/docs/iam?topic=iam-iamuserinv#assignaccess).

Se você determinar que um usuário não precisa de acesso, será possível cancelar um convite para quaisquer usuários que são mostrados em um estado Processando ou Pendente na coluna Status. Se um usuário convidado não tiver recebido um convite, será possível reenviar o convite para qualquer usuário em um estado Pendente.

### Convidando usuários usando a CLI
{: #cli-invite}

Para convidar usuários usando a interface da linha de comandos (CLI), execute o comando a seguir:

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

Usando a CLI, é possível optar por designar o acesso ao Cloud Foundry ou nenhum acesso e trabalhar na designação do acesso mais tarde. Para obter mais informações sobre os parâmetros de comando, consulte [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite). 

### Convidando usuários usando a API
{: #api-invite}

É possível usar a [API](https://cloud.ibm.com/apidocs/user-management#invite-users){: external} para convidar usuários em massa. Todos os usuários que estão incluídos em um único convite são designados ao mesmo acesso. Ao convidar usuários usando a API, você insere e-mails em uma lista separada por vírgulas com cada entrada incluída entre aspas, por exemplo:


```
curl -X POST \
  https://user-management.cloud.ibm.com/v2/accounts/987d4cfd77b04e9b9e1a6asdcc861234/users \
  -H 'Authorization: Bearer <IAM_TOKEN>'
  -H 'Content-Type: application/json' \
    -d '{
      "users": [
      {
        "email": "cloud_api_example_member@ibm.com", "second_user@ibm.com", "third_user@ibm.com",
        "account_role": "Member"
      }],
      "iam_policy": [
      {
        "roles": [ {
          "id": "crn:v1:bluemix:public:iam::::role:Viewer"
        }],
        "resources": [
        {
          "accountId": "111d4cfd77b04e9b9e1a6asdcc861234",
          "resourceType": "resource-group",
          "resource": "111449dd871049c29ec3a53853ce123e"
        }]
      }]
    }'
```
{: codeblock}

## Designando acesso de usuário por meio de um convite
{: #assignaccess}

Você designa acesso para usuários à medida que os convida, designando as políticas do {{site.data.keyword.Bluemix}} IAM, o acesso do Cloud Foundry e as permissões de infraestrutura clássica. Dependendo das opções de acesso que você está autorizado a gerenciar, é possível convidar e fornecer acesso para usuários na conta, grupos de recursos, organizações, espaços, instâncias de serviço e infraestrutura clássica. As seções a seguir descrevem os três tipos de acesso que podem ser designados a um usuário convidado.

### Serviços
{: #invite_services}

É possível designar acesso criando uma política de acesso inicial do {{site.data.keyword.Bluemix_notm}} IAM quando você convida um novo usuário. Na seção Serviços, é possível fornecer a um usuário acesso a serviços de gerenciamento de conta, serviços em um grupo de recursos com acesso para gerenciar o grupo de recursos ou a um recurso individual na conta.

Após o usuário aceitar o convite, é possível designar mais acesso. Veja [Gerenciando o acesso a recursos](/docs/iam?topic=iam-iammanidaccser#iammanidaccser) para obter detalhes sobre a edição de políticas para incluir funções extras, a designação de mais acesso ou a remoção de uma política para um usuário.

Dependendo de qual serviço você seleciona ao designar a política, talvez não veja todos os campos que são descritos nos procedimentos a seguir.
{: note}

#### Acesso aos serviços de gerenciamento de conta
{: #invite_acct_mgmt}

Para delegar algumas de suas responsabilidades como um proprietário da conta, é possível fornecer a um usuário acesso aos serviços de gerenciamento de conta. Por exemplo, é possível delegar a capacidade para visualizar o faturamento e o uso,
convidar e remover usuários, gerenciar os grupos de acesso ou gerenciar os IDs de serviço. É possível fornecer acesso a
todos os serviços de gerenciamento de conta ou a apenas um.

1. Na página Convidar usuários, expanda a seção Serviços.
2. Selecione **Serviços de gerenciamento de conta** na lista **Designar acesso a**. 
3. Selecione **Todos os serviços de gerenciamento de conta** ou selecione um serviço de
gerenciamento de conta específico.
4. Selecione qualquer combinação de funções para designar o acesso desejado.

#### Acesso ao grupo de recursos
{: #invite_rgs}

É possível designar acesso a todos os serviços em um grupo de recursos ou a um único tipo de serviço em um grupo de recursos.

1. Na página Convidar usuários, expanda a seção Serviços.
2. Selecione **Grupo de recursos** na lista **Designar acesso a**.
3. Selecione um grupo de recursos.
4. Selecione uma função na lista **Designar acesso a um grupo de recursos** para permitir que o usuário visualize o grupo de recursos na lista de recursos, edite o nome do grupo de recursos ou gerencie o acesso de usuário para o grupo. Será possível selecionar **Sem acesso** se você desejar que o usuário seja capaz de acessar somente o recurso que você especificar e não o grupo no qual ele está organizado.
5. Selecione um serviço no grupo de recursos ou opte por fornecer acesso a todos os serviços no grupo selecionado.
6. Selecione qualquer combinação de funções para designar o acesso desejado. Este acesso só se aplica aos recursos que você selecionou para a política. Ela não fornece acesso ao contêiner real que é o grupo de recursos.

#### Acesso ao recurso
{: #invite_resources}

É possível designar acesso a um único recurso em sua conta para a instância.

1. Na página Convidar usuários, expanda a seção Serviços.
2. Selecione **Recurso** na lista **Designar acesso a**. 
3. Selecione um serviço.
4. Selecione **Todas as regiões atuais** ou uma região específica, se solicitado.
5. Selecione **Todas as instâncias de serviço atuais** ou selecione uma instância de serviço específica.
6. Dependendo do serviço que você selecionou, poderá ver os campos a seguir. Se você não digitar valores para esses campos, a política será designada no nível da instância de serviço em vez do nível de depósito.
    * **Tipo de recurso**: insira `depósito`.
    * **ID do recurso**: Insira o nome do bucket.
7. Selecione qualquer combinação de funções para designar o acesso desejado.

Para obter mais informações sobre as funções que são usadas quando você designa acesso, veja [Acesso do IAM](/docs/iam?topic=iam-userroles#iamusermanrol).

### Acesso ao Cloud Foundry
{: #invite_cf}

Ao convidar novos usuários, é possível escolher incluir o usuário em uma organização na conta. Se você incluir o usuário em uma organização, será possível designar a ele uma função de organização. Em seguida, você optará por fornecer ao usuário convidado acesso a qualquer um ou a todos os espaços na organização selecionada com uma função de espaço designada.

1. Na página Convidar usuários, expanda a seção de acesso do Cloud Foundry.
2. Selecione uma organização na qual incluir o usuário.
3. Selecione uma função de organização para definir o nível de acesso para a organização selecionada.
4. Opcional: clique em **Incluir função de organização** para especificar uma função extra.
5. Selecione **Todas as regiões atuais** ou uma região específica.
6. Selecione **Todos os espaços atuais** ou um espaço específico.
7. Selecione uma função de espaço para definir o nível de acesso para os espaços selecionados.
8. Opcional: clique em **Incluir função de espaço** para especificar uma função extra.

Para obter mais informações sobre as funções que são usadas quando você designa acesso, veja [Funções do Cloud Foundry](/docs/iam?topic=iam-cfaccess#cfroles).

É possível incluir uma função do Cloud Foundry usando o comando da CLI [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite), mas o console deve ser usado para designar outro acesso ou permissões.
{: tip}

### Acesso à infraestrutura clássica
{: #invite_classicinfra}

As permissões designadas são limitadas automaticamente ao subconjunto de permissões que você tem. Você se torna o usuário pai de qualquer usuário que é convidado.

1. Na página Convidar usuários, expanda a seção de acesso de Infraestrutura clássica.
2. Selecione um conjunto de permissões para designar permissões predefinidas em massa.

O acesso a dispositivos é concedido separadamente após o usuário ser incluído. Acesse a opção de acesso **Infraestrutura clássica** para um usuário no console.
{: note}

Para obter informações sobre como configurar o acesso para usuários após eles serem incluídos em sua conta, veja [Gerenciando o acesso de infraestrutura clássica](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra).

## Incluindo usuários somente VPN
{: #add-vpn-only}

Como o proprietário da conta ou um usuário com a permissão Gerenciar a infraestrutura clássica de usuários, é possível incluir um usuário somente VPN.

1. Na página Usuários, clique em **Incluir usuário somente VPN**.
2. Insira os detalhes de informações pessoais para o usuário.
3. Clique em **Salvar**.
