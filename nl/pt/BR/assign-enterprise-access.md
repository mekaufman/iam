---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise policy, enterprise access, assign enterprise access, enterprise service

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Designando acesso corporativo
{: #assign-access-enterprise}

Para designar o acesso a um usuário para gerenciar uma empresa {{site.data.keyword.Bluemix}}, deve-se convidá-lo para a conta corporativa e designar um acesso ao serviço de gerenciamento de conta corporativa.
{:shortdesc}

O acesso para gerenciar a [empresa](/docs/account?topic=account-enterprise) requer uma política de acesso dentro da conta corporativa. Quando você designa a um usuário uma Política de serviço de gerenciamento de conta corporativa dentro de uma conta-filha em uma empresa, o usuário não pode gerenciar a empresa à qual a conta pertence. Dependendo da função designada do usuário ao Serviço de gerenciamento de conta corporativa na conta corporativa, o usuário pode executar ações específicas:

* Criar novas contas na empresa
* Criar e nomear grupos de contas
* Mover contas entre grupos de contas
* Importar contas existentes para a empresa
* Atualizar o nome corporativo ou o domínio
* Visualizar os relatórios de uso para a empresa, um grupo de contas específico e seus grupos de contas ou contas dentro dele ou uma conta específica

Uma política que fornece a um usuário acesso ao serviço corporativo pode ser designada à empresa inteira ou apenas a um grupo de contas específico ou conta única.
{: tip}

Geralmente, a conta corporativa em si não contém muitos recursos. Em vez disso, os recursos são criados nas contas-filhas da empresa. É dentro de cada uma dessas contas que os usuários podem ser convidados e receber acesso para gerenciar e trabalhar com recursos. O acesso e a associação que um usuário tem na conta corporativa não se aplicam aos grupos de contas e às contas-filhas na hierarquia corporativa. O gerenciamento de usuários e o gerenciamento de acesso permanecem isolados para cada conta, conforme é possível ver descrito nos diagramas a seguir.

O primeiro diagrama mostra como é possível designar uma política a um usuário na conta corporativa para gerenciar a empresa inteira ou uma política com escopo definido para um grupo de contas, que fornece acesso para gerenciar apenas esse grupo de contas e os outros grupos de contas ou contas-filhas que são organizados dentro dele.

![Acesso corporativo](images/enterprise-access.svg "Diagrama que mostra que os usuários corporativos têm acesso para gerenciar apenas as entidades corporativas")

O destino e a função da política são importantes para determinar o escopo de acesso. Um usuário, o ID de serviço ou o grupo de acesso em uma empresa, que é o assunto da política, pode concluir tarefas de gerenciamento corporativo na empresa inteira, um grupo de contas que pode conter outros grupos de contas e contas ou até mesmo uma única conta. Por exemplo, se você designar a um usuário, na conta corporativa, uma política de acesso no Serviço de gerenciamento de conta corporativa com um destino com escopo definido para um grupo de contas específico, ele terá acesso para concluir tarefas dentro do grupo de contas. O usuário não pode concluir ações que afetam a empresa como um todo, como atualizar o nome ou o domínio da empresa, quando o destino está configurado para uma conta ou um grupo de contas específico.

É possível designar usuários em uma conta-filha nas políticas de acesso corporativo que se aplicam ao gerenciamento apenas dessa conta ou aos recursos que ela contém. Se você designar a um usuário, em uma conta-filha, uma função no Serviço de gerenciamento de conta corporativa, por exemplo, o usuário não poderá executar ações no nível de conta corporativa. Deve-se incluí-los na conta corporativa e designar a política nesse contexto.

![Acesso da conta](images/account-access.svg "Diagrama que mostra que os usuários da conta-filha têm acesso somente dentro de suas contas e não ao restante da empresa")

## Políticas necessárias para tarefas específicas
{: #sample-enterprise-policies}

Dependendo da tarefa que precisa ser executada, uma combinação de políticas de acesso poderá ser necessária para um usuário que não é o proprietário da empresa. Os exemplos a seguir fornecem o conjunto de políticas de acesso que devem ser designadas a um usuário na empresa para que possam concluir tarefas específicas.

Se você for um proprietário de uma conta que não faz parte de uma empresa, mas quiser que outro usuário em sua conta seja capaz de converter sua conta para uma empresa, será possível designar a esse usuário a função de Administrador no Serviço de gerenciamento de conta de faturamento.
{: note}

### Visualizando o uso e gerenciando o faturamento na empresa
{: #billing-admin-enterprise}

Para que um usuário [visualize relatórios de uso](/docs/billing-usage?topic=billing-usage-enterprise-usage) para todas as contas na empresa, faça pagamentos e visualize faturas, deve-se designar todas as políticas de acesso a seguir:

* Função de visualizador de relatórios de uso para o Serviço de gerenciamento de conta corporativa na conta corporativa
* Função de administrador para o Serviço de gerenciamento de conta de cobrança na conta corporativa

### Importando uma conta existente para a empresa
{: #add-account}

Para que um usuário [importe uma conta do IBM Cloud existente para a empresa](/docs/account?topic=account-enterprise-add#add-accounts), deve-se designar todas as políticas de acesso a seguir:

* Função de administrador no Serviço de gerenciamento de conta de cobrança na conta que deve ser importada
* Função de Administrador ou de Editor no Serviço de gerenciamento de conta corporativa para o grupo de contas ou conta corporativa na qual a conta será incluída
* Função de administrador no Serviço de gerenciamento de conta de cobrança para a conta corporativa

### Movendo uma conta
{: #move-accountgroup}

Para que um usuário [mova uma conta em uma empresa](/docs/account?topic=account-enterprise-organize#move-accounts), deve-se designar as políticas de acesso a seguir:

* Função de administrador para o Serviço de gerenciamento de conta de cobrança na conta corporativa

Em seguida, uma das duas opções a seguir:

* Função de Administrador ou de Editor para o Serviço de gerenciamento de conta corporativa para a empresa inteira
* Função de Administrador ou de Editor no grupo de contas atual e de destino para o qual essa conta será movida

Para obter detalhes sobre quais ações os usuários podem executar para cada função, consulte [Ações e funções para serviços de gerenciamento de conta](/docs/iam?topic=iam-account-services#account-management-actions-roles).

## Designando acesso no console
{: #enterprise-access-console}

Para designar uma política de acesso a um usuário existente na conta corporativa, conclua as etapas a seguir:

É possível configurar o destino da política para que seja para a empresa inteira, um grupo de contas específico, o que pode incluir acesso a todas as contas dentro dele ou até mesmo uma conta específica em um grupo de contas.
{: tip}

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Na linha para o usuário que você deseja designar acesso, selecione o menu **Ações**![Ícone Lista de ações](../icons/action-menu-icon.svg) e clique em **Designar acesso**.
3. Selecione para designar acesso aos **Serviços de gerenciamento de conta**.
4. Selecione **Empresa** como o serviço.
5. Opcional: defina o escopo da política para a empresa, grupo de contas ou conta.
6. Selecione qualquer combinação de funções para designar o acesso desejado.

| Funções | Ações |
|:-------|----------|
| Visualizador |  Visualizar a empresa, os grupos de contas e as contas    |
| Operador |  Visualizar a empresa, os grupos de contas e as contas    |
| Editor |  Visualizar e atualizar a empresa editando o nome e o domínio, criar contas e grupos de contas, visualizar relatórios de uso e importar contas |
| Administrador |  Visualizar e atualizar a empresa editando o nome e o domínio, criar contas e grupos de contas, mover contas entre grupos de contas, importar contas existentes e visualizar relatórios de uso  |
| Visualizador de relatório de uso | Visualizar as contas corporativas, contas e grupos de contas e visualizar os relatórios de uso para todas as contas na empresa |
{: caption="Tabela 1. Funções e ações de exemplo para o Serviço de gerenciamento de conta corporativa" caption-side="top"}

## Designando acesso usando a CLI
{: #enterprise-cli-policy}

Para criar uma nova política de acesso para um usuário, execute o comando **`ibmcloud iam user-policy-create`**. No exemplo de comando, um arquivo JSON é usado para especificar os detalhes da política. Revise o exemplo na seção [Designando acesso usando a API](#enterprise-api-policy) para obter um exemplo do que deve ser incluído no arquivo JSON.

Criar uma política de usuário:
```
$ ibmcloud iam user-policy-create name@example.com -f policy.json
```

Para obter mais informações, consulte [ibmcloud iam user-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_create).

## Designando acesso usando a API
{: #enterprise-api-policy}

O exemplo de solicitação a seguir designa uma política para um usuário com a função de Editor no Serviço corporativo em uma conta corporativa com escopo definido para um grupo de contas. Esse tipo de política é hierárquico e se aplica a todos os objetos descendentes na hierarquia, o que significa todos os grupos de contas ou contas dentro do grupo de contas de destino especificado.  

```
curl -X POST \
'https://iam.cloud.ibm.com/v1/policies' \
-H 'Authorization: $TOKEN' \
-H 'Content-Type: application/json' \
-d '{
  "type": "access",
  "subjects": [
    {
      "attributes": [
        {
          "name": "iam_id",
          "value": "<IBMid-example>"
        }
      ]
    }
  ],
  "roles":[
    {
      "role_id": "crn:v1:bluemix:public:iam::::role:Editor"
    }
  ],
  "resources":[
    {
      "attributes": [
        {
          "name": "accountId",
          "value": "<account-id-example>"
        },
        {
          "name": "serviceName",
          "value": "enterprise"
        },
        {
          "name": "accountGroupId",
          "value": "<accountGroupId-example>"
        }
      ]
    }
  ]
}'
```
{: codeblock}

Para obter mais informações, consulte [Criar uma política](https://cloud.ibm.com/apidocs/iam-policy-management#create-a-policy){: external}.
