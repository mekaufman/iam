---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-28"

keywords: advantage of access groups, access assignment process, assign access, best practice, access management, strategy

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Melhores práticas para designar acesso
{: #account_setup}

Para simplificar o processo de designação de acesso, é possível aproveitar os grupos de acesso para designar um número mínimo de políticas, fornecendo o mesmo acesso a todos os usuários e IDs de serviço que pertencem ao mesmo grupo de acesso. Use essas melhores práticas para saber mais sobre como fornecer aos usuários acesso a recursos, grupos de recursos e serviços de gerenciamento de conta.
{:shortdesc}

Para assegurar que sua conta esteja totalmente configurada para o sucesso, consulte [Melhores
práticas para configurar sua conta](/docs/account?topic=account-account_setup#account_setup) e [Melhores práticas para organizar recursos em grupos de recursos](/docs/resources?topic=resources-bp_resourcegroups#bp_resourcegroups).
{: tip}

## O que é uma boa estratégia de grupo de acesso?
{: #rg_strategy}

Um grupo de acesso é um agrupamento de IDs de usuário e de serviço aos quais o mesmo acesso do IAM pode ser concedido. É possível designar uma política única ao grupo em vez de designar o mesmo acesso múltiplas vezes por usuário ou ID de serviço individual.

Supondo que você tenha seguido as [melhores práticas para configurar sua conta](/docs/account?topic=account-account_setup#account_setup), uma maneira lógica de designar acesso é criando um grupo de acesso por nível desejado de acesso. Em seguida, é possível mapear cada grupo de acesso para os grupos de recursos criados anteriormente. Por exemplo, para controlar o acesso ao projeto `CustApp`, é possível criar os grupos de acesso a seguir:

* Auditor-Grupo
* Desenvolvedor-Grupo
* Administrador-Grupo

Para o Auditor-Grupo, designe duas políticas de acesso que concedam acesso de visualizador aos grupos de recursos `CustApp-Test` e `CustApp-Prod`. Para o Desenvolvedor-Grupo, designe duas políticas de acesso que concedam acesso de editor aos ambientes `CustApp-Dev` e `CustApp-Test`. Para o Administrador-Grupo, designe três políticas de acesso que concedam acesso de administrador a todos os três grupos de recursos `CustApp`.

Embora essas sugestões sejam projetadas para um cenário hipotético, é possível configurar o grupo de acesso para o mapeamento do grupo de recursos conforme julgar necessário.

## Criando grupos de acesso
{: #access-group-setup}

Para criar um grupo de acesso, conclua as etapas a seguir:

1. No console do {{site.data.keyword.Bluemix}}, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Clique em **Criar**.
3. Insira o nome e a descrição para o grupo.
4. Clique em **Criar**.

Depois de criar um grupo de acesso, é possível incluir usuários e IDs de serviço no grupo.

## Como as políticas de acesso do IAM fornecem acesso
{: #how_access}

Uma política consiste em um assunto, um destino e uma função. O assunto nesse caso é o grupo de acesso. O destino é o que você deseja que o assunto acesse, como um conjunto de recursos, uma instância de serviço, todos os serviços na conta ou todas as instâncias de um serviço. A função define o nível de acesso que é concedido a um usuário.

As funções mais comumente usadas são visualizador, editor e administrador. A função de visualizador fornece a menor quantidade de acesso para visualizar instâncias e grupos de recursos em uma conta. A função de editor possui mais acesso para criar, editar, excluir e ligar instâncias de serviço. A função de administrador inclui tudo para trabalhar com uma instância de serviço e pode designar acesso a outros. No entanto, há duas categorias diferentes de funções que devem ser consideradas: plataforma e serviço. Para obter mais informações sobre as funções que podem ser designadas, consulte as [funções do IAM Cloud](/docs/iam?topic=iam-iamusermanrol#iamusermanrol).

## Designando acesso a grupos de acesso
{: #assigning-access}

É possível organizar os recursos em um grupo de recursos e usuários e IDs de serviço em um grupo de acesso para tornar a designação de acesso o mais simples possível. Após configurar cada um, é possível criar políticas de acesso para os grupos de acesso para fornecer aos usuários em sua conta acesso aos recursos que você criou.

1. Clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Selecione o nome do grupo de acesso para o qual você deseja designar acesso.
3. Selecione a guia **Políticas de acesso** e, em seguida, clique em **Designar acesso**. Você tem as opções a seguir para designar acesso:

  * **Designar acesso a recursos dentro de um grupo de recursos**: use essa opção para fornecer a política de duas partes que é necessária para os usuários que criam recursos do catálogo e designam os recursos a um grupo de recursos. Ao usar essa opção, é possível fornecer acesso ao próprio grupo de recursos e a todos os recursos em um grupo de recursos específico ou apenas a um serviço ou instância no grupo de recursos.
  * **Designar acesso a recursos**: use essa opção para designar acesso a todos os serviços ativados para IAM na conta ou a um único serviço na conta, mas não a um nível de instância.
  * **Designar acesso aos serviços de gerenciamento de conta**: use essa opção para fornecer a um usuário acesso aos serviços de gerenciamento de conta como uma maneira de delegar alguns de seus recursos de proprietário da conta. Por exemplo, é possível delegar a capacidade para visualizar faturamento e uso, convidar e remover usuários, gerenciar grupos de acesso, gerenciar serviços de catálogo ou gerenciar IDs de serviço. É possível fornecer acesso a
todos os serviços de gerenciamento de conta ou a apenas um.

Forneça facilmente a vários usuários acesso de administrador a tudo em uma conta, criando um grupo de acesso e designando duas políticas a ele. Para criar a primeira política, use a opção **Designar acesso aos recursos** e selecione **Todos os serviços ativados por identidade e
acesso** com a função de administrador designada. Para criar a segunda política, use a opção **Designar acesso a serviços de gerenciamento de conta** e selecione **Todos os serviços de gerenciamento de conta** com a função de administrador designada.
{: tip}
