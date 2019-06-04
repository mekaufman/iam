---

copyright:

  years: 2017, 2019

lastupdated: "2019-05-16"

keywords: get started with IAM, IAM tutorial, IAM quick start

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Tutorial Introdução
{: #getstarted}

Este tutorial é destinado a ajudá-lo a deixar o IBM Cloud Identity and Access Management (IAM) funcionando rapidamente, convidando usuários para sua conta e designando acesso ao Cloud IAM para esses usuários.
{:shortdesc}

Este tutorial é para recursos ativados para IAM. Para serviços que não suportam a criação de políticas do Cloud IAM para gerenciar o acesso, é possível usar o [Acesso do Cloud Foundry](/docs/iam?topic=iam-cfaccess#cfaccess) ou as [permissões de infraestrutura clássica](/docs/iam?topic=iam-infrapermission#infrapermission).
{: note}

## Antes de começar
{: #iam-before-you-begin}

Se você for novo no uso do IAM, consulte a documentação a seguir para entender mais sobre os recursos, conceitos e componentes do sistema de gerenciamento de acesso:

* O [IBM Cloud Identity and Access Management](/docs/iam?topic=iam-iamoverview) fornece uma visão geral rápida do que é o IAM no {{site.data.keyword.Bluemix_notm}}, dos recursos disponíveis e dos links para docs de CLI e API disponíveis.
* [Conceitos do IAM](/docs/iam?topic=iam-iamconcepts) descreve os conceitos de alto nível no IAM que podem ajudá-lo a entender os diferentes componentes à medida que você começar.
* O [acesso ao IAM](/docs/iam?topic=iam-userroles) fornece uma revisão mais detalhada de como o gerenciamento de acesso funciona usando as políticas de acesso.


## Etapa 1. Convidar os usuários e designar o acesso inicial
{: #step1}

É possível convidar um ou múltiplos usuários e configurar uma política de acesso inicial para os usuários no
convite. Se você convidar múltiplos usuários em um convite, o mesmo acesso será designado a cada um deles. Na seção de acesso da página Convidar usuários, você vê somente as seções que você tem acesso para designar.

Como proprietário da conta, é possível designar funções do Cloud IAM para usuários que você convida na seção Serviços. É possível fornecer acesso a todos os recursos em um grupo de recursos, a todos os recursos para um serviço específico
em um grupo de recursos, a todos os serviços ativados para o Identity and Access na conta, a um único recurso na conta ou
aos serviços de gerenciamento de conta:

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Clique em **Convidar usuários**.
3. Especifique o endereço de e-mail dos usuários que você deseja convidar.
4. Na seção **Acesso**, expanda a opção **Serviços**.
5. Escolha designar acesso a um **Recurso**, aos recursos em um **Grupo de
recursos** ou aos **Serviços de gerenciamento de conta**.
6. Dependendo de sua seleção, siga os prompts para especificar o acesso desejado. Se você selecionou a opção de grupo de recursos, também é possível fornecer ao usuário o acesso para visualizar, editar ou gerenciar acesso para o grupo de recursos, selecionando uma função para acesso ao grupo de recursos.
7. Se você tiver permissão, também será possível designar o acesso ao Cloud Foundry ou à infraestrutura no convite.
8. Clique em **Convidar usuários**.

Para obter mais informações, veja [Convidando usuários e designando acesso](/docs/iam?topic=iam-iamuserinv#iamuserinv).

## Etapa 2. Criar grupos de acesso
{: #step2}

Para aperfeiçoar o processo de designação de acesso a usuários em sua conta, é possível criar grupos de acesso. Os grupos de acesso são uma maneira de organizar usuários e IDs de serviço para os quais é possível designar facilmente o acesso, definindo uma única política para o grupo inteiro.

### Configure seus grupos
{: #group_setup}

Para criar um grupo de acesso, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Clique em **Criar**.
3. Insira um nome e uma descrição opcional para seu grupo
4. Clique em **Criar**.

Em seguida, continue a configurar seu grupo incluindo usuários ou IDs de serviço:

1. Selecione o nome do grupo que deseja incluir.
2. Clique em **Incluir usuários**.
3. Selecione os usuários que deseja incluir na lista e clique em **Incluir no grupo**.
4. Para incluir IDs de serviço no grupo, clique em **IDs de serviço**.
5. Selecione os IDs que deseja incluir na lista e clique em **Incluir no grupo**.

### Designe acesso aos seus grupos
{: #group_access}

Depois de criar seus grupos, é possível designar acesso a todas as entidades dentro do grupo com uma única política ou múltiplas políticas.

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Selecione o nome do grupo para o qual você deseja designar acesso.
3. Na guia **Políticas de acesso**, clique em **Designar acesso** para configurar uma política de acesso. Repita conforme necessário para designar mais acesso.

Organizando recursos em grupos de recursos e usuários em grupos de acesso, é possível designar a um grupo de usuários acesso a um grupo de recursos com uma única política, o que reduz o número geral de políticas que você precisa gerenciar.
{: tip}


## Etapa 3. Gerenciar o acesso para os usuários existentes
{: #user_access_manage}

Depois de convidar usuários, designar o acesso inicial e criar seus grupos de acesso, você talvez deseje designar mais acesso ou editar o acesso inicial designado para assegurar que todos os usuários e grupos em sua conta tenham o nível desejado de acesso.

### Designando novo acesso
{: #new_access}

Para designar uma nova política de acesso, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Selecione o nome do usuário para o qual você deseja designar acesso.
3. Clique em **Políticas de acesso**.
4. Clique em **Designar acesso**.
5. Escolha como deseja designar o acesso:
    * Selecione **Designar acesso dentro de um grupo de recursos** para designar acesso a todos os recursos em um grupo ou apenas a recursos para um serviço específico em um grupo. Também é possível fornecer ao usuário o acesso para visualizar, editar ou gerenciar acesso para o grupo de recursos, selecionando uma função para acesso ao grupo de recursos. Selecione **Sem acesso** se você desejar que o usuário tenha acesso somente ao recurso especificado e não ao grupo no qual ele está organizado.
    * Selecione **Designar acesso a recursos** para designar acesso a todos os recursos ativados pelo Identity and Access na conta, todos os recursos de um serviço específico na conta, uma única instância ou um único recurso em uma instância de serviço específica.
    * Selecione **Designar acesso aos serviços de gerenciamento de conta** para designar
acesso a todos os serviços de gerenciamento de conta ou a apenas um serviço de gerenciamento de conta.
5. Selecione qualquer combinação de funções para definir o escopo de acesso. Para obter mais informações, veja [Funções do Cloud IAM](/docs/iam?topic=iam-userroles#iamusermanrol).
6. Clique em **Designar**.


### Editando acesso existente
{: #editing_access}

É possível atualizar o acesso existente editando as funções designadas para um usuário.

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Selecione o nome do usuário para o qual você deseja editar o acesso.
3. Clique em **Políticas de acesso**.
4. Clique em **Editar** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) na linha para a política que você deseja editar.
4. Edite a política atualizando as funções designadas.
5. Clique em **Salvar**.

É possível remover o acesso de um usuário clicando na opção **Remover** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) para a política que você deseja remover.

## Próximas Etapas
{: #next}

Saiba o que mais é possível fazer com o Cloud IAM verificando a lista [Recursos do Cloud IAM](/docs/iam?topic=iam-iamoverview#features).
