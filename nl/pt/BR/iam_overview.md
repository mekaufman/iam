---

copyright:

  years: 2017, 2019

lastupdated: "2019-07-25"

keywords: user identities, service ID, policies, access management, roles, actions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:external: target="_blank" .external}

# Conceitos do IAM
{: #iamconcepts}

Dois conceitos principais se destacam quando você deseja aprender sobre o {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM): gerenciamento de identidade e acesso.Além disso, é possível aprender sobre grupos de acesso, grupos de recursos, usuários, funções, políticas de acesso e muito mais.
{: shortdesc}

## Identidade
{: #identity}

O conceito de identidade no {{site.data.keyword.Bluemix_notm}} IAM consiste em identidades do usuário, identidades de serviço e app, chaves de API e recursos. Os usuários são identificados por seu IBMid ou ID da conta do SoftLayer. Os IDs de serviço são um segundo tipo de identidade que é usado em uma conta. Os IDs de serviço são o recurso Cloud IAM que é usado para fornecer uma identidade separada para serviços e aplicativos. É possível criar um ID de serviço para ser usado por um aplicativo que precisa de acesso a seus serviços do {{site.data.keyword.Bluemix_notm}} para que as credenciais do usuário individuais não tenham que ser usadas.

Para se autenticar com uma API ou uma CLI como um ID de usuário ou de serviço, as chaves de API do {{site.data.keyword.cloud_notm}} podem ser usadas. Essas chaves API são fornecidas por meio do Cloud IAM e, portanto, não podem ser usadas geralmente para autenticar com o IBMid fora do IBM Cloud. Um usuário também pode ter uma única chave de API de infraestrutura clássica que pode ser usada para acessar as APIs de infraestrutura clássica; no entanto, isso não é necessário porque é possível usar as chave de API do {{site.data.keyword.cloud_notm}} para acessar as mesmas APIs.

A parte final do conceito de identidade no IAM são recursos do {{site.data.keyword.Bluemix_notm}}, que são identificados por seus nomes de recurso em nuvem (CRN). Para obter mais informações, veja [Cloud Resource Names](/docs/overview?topic=overview-crn#crn).

## Gerenciamento de acesso
{: #am}

O conceito de gerenciamento de acesso no {{site.data.keyword.Bluemix_notm}} consiste em alguns componentes inter-relacionados, incluindo usuários, recursos, políticas, funções, ações e o sistema do controle do {{site.data.keyword.Bluemix_notm}} IAM, que permitem que os usuários executem ações em recursos dentro de uma conta.

O {{site.data.keyword.Bluemix_notm}} IAM segue um padrão [eventualmente consistente](https://en.wikipedia.org/wiki/Eventual_consistency){: external} que é comum a muitos serviços nativos de nuvem, o que permite que o IAM permaneça altamente disponível e eficaz em múltiplas regiões globais. As mudanças que são feitas em políticas de acesso do IAM, autorizações, IDs de serviço, chaves de API, grupos de acesso, grupos de recursos, usuários ou quaisquer outros controles de acesso são registradas e propagadas em todos os componentes do IAM e serviços ativados pelo IAM em todo o mundo. As mudanças de acesso podem não entrar em vigor até que o processo de propagação seja concluído.

### Usuários
{: #iam-users}

Todos os usuários dentro de uma conta são identificados por seus IBMids de seus IDs de conta do SoftLayer. Os usuários podem ser convidados para a conta e receber acesso aos recursos. As políticas de acesso começam com o assunto que geralmente é um usuário em sua conta. O acesso pode ser designado a serviços de gerenciamento de conta, a recursos individuais até o nível de instância ou a um conjunto de recursos que são organizados em um grupo de recursos de conta.


### Grupos de acesso
{: #access-groups-iam}

Um grupo de usuários e IDs de serviço podem ser criados de modo que o mesmo acesso possa ser designado a todas as entidades dentro do grupo com uma ou mais políticas. Usando os grupos de acesso, é possível simplificar o processo de designação de acesso para que seja possível gerenciar uma quantidade menor de políticas e reduzir o número de políticas em uma conta, o que aumenta o desempenho. Depois que seus grupos são configurados, é possível iniciar a designação de políticas selecionando um grupo de acesso como o assunto da política. Para obter mais informações, consulte [Configurando grupos de acesso](/docs/iam?topic=iam-groups).

### Resources
{: #resources-access-management}

Os recursos de conta são as ofertas de serviços provisionados que são selecionadas do catálogo ou recursos de baixa granularidade em uma instância de serviço. Esses recursos são incluídos em um grupo de recursos quando eles são criados por meio do catálogo. O gerenciamento de acesso ao IAM permite acesso de baixa granularidade, o que significa que uma política pode ser configurada em uma escala mais ampla, para todos os recursos em um grupo de recursos, por exemplo, ou para um tipo de recurso específico, como um depósito do {{site.data.keyword.cos_full_notm}} dentro de uma instância específica.


### Políticas de acesso
{: #access-policies-concept}

As políticas de acesso são como os usuários, os IDs de serviço e os grupos de acesso na conta recebem permissão para acessar os recursos da conta. As políticas incluem um assunto, o destino e a função. O assunto é o usuário, o ID do serviço ou o grupo de acesso ao qual você está concedendo acesso. O destino da política é o recurso ao qual você deseja fornecer acesso. Além disso, as funções servem para definir o nível de acesso ou as ações permitidas no destino da política. Há diferentes tipos de políticas que permitem o acesso aos recursos da conta: uma política de grupo de recursos, uma
política de instância de recurso, uma política de toda a conta para acesso a todos os serviços ativados para o Identity
and Access e uma política em todos ou em um serviço de gerenciamento de conta. Dependendo de suas seleções, as opções de
configuração customizadas, como a definição de acesso aos recursos em uma região específica ou a definição de acesso ao
nível granular de um recurso específico de serviço em uma instância, podem estar disponíveis.

### Funções
{: #iam-roles-concept}

As funções de acesso do Cloud IAM permitem que um usuário conclua tarefas específicas no recurso que é definido na política. Há dois tipos de funções de acesso: gerenciamento de plataforma e acesso de serviço. 

As funções de gerenciamento de plataforma definem as ações permitidas para gerenciar recursos no nível de plataforma, como acesso de usuário e criação de instâncias de serviço. As funções da plataforma também se aplicam a ações que podem ser tomadas dentro do contexto de serviços de gerenciamento de conta, como convidar e remover usuários, gerenciar grupos de acesso, gerenciar IDs de serviço e ofertas do catálogo privado. 

As funções de acesso de serviço definem as ações permitidas dentro do contexto de uso do serviço, como as APIs de serviço de chamada. Essas funções são customizadas com base no serviço que é selecionado dentro da política.

### Ações
{: #iam-roles-actions}

As ações são mapeadas para as funções do Cloud IAM para permitir que os usuários executem somente tarefas específicas quando eles são designados a funções diferentes. As ações permitidas para cada função podem mudar com base no serviço que está sendo acessado porque cada serviço define como essa função é mapeada para o uso do serviço.

### Sistema de gerenciamento de acesso
{: #access-management-system}

O sistema de controle do Cloud IAM permite ou nega ações por usuários dentro do contexto de um serviço com base na política designada. Quando um usuário tenta concluir uma ação específica, o sistema de controle usa os atributos que são definidos na política para determinar se o usuário tem permissão para executar essa tarefa.
