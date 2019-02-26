---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Conceitos do IAM
{: #iamconcepts}

## Identidade
{: #identity}

O conceito de identidade no {{site.data.keyword.Bluemix_notm}} IAM consiste nos componentes a seguir:

<dl>
<dt>Identidades do usuário</dt>
<dd>Todos os usuários são identificados por seus IBMids.</dd>
<dt>Identidades de serviço e app</dt>
<dd>Os IDs de serviço são o recurso Cloud IAM que é usado para fornecer uma identidade separada para serviços e aplicativos. É possível criar um ID de serviço para ser usado por um aplicativo que precisa de acesso a seus serviços do {{site.data.keyword.Bluemix_notm}} para que as credenciais do usuário individuais não tenham que ser usadas.</dd>
<dt>Chaves API (interface de programação de aplicativos)</dt>
<dd>As chaves de API do {{site.data.keyword.cloud_notm}} estão disponíveis por meio do Cloud IAM para que você use para autenticar usando a API ou a CLI como um ID do usuário ou do serviço. Essas chaves API são fornecidas por meio do Cloud IAM e, portanto, não podem ser usadas geralmente para autenticar com o IBMid fora do IBM Cloud. Um usuário também pode ter uma única chave de API de infraestrutura clássica que pode ser usada para acessar as APIs de infraestrutura clássica; no entanto, isso não é necessário porque é possível usar as chave de API do {{site.data.keyword.cloud_notm}} para acessar as mesmas APIs. </dd>
<dt>Resources</dt>
<dd>Os recursos do {{site.data.keyword.Bluemix_notm}} são identificados por seus cloud resource names (CRN). Para obter mais informações, veja [Cloud Resource Names](/docs/overview?topic=overview-crn#crn).</dd>
</dl>

## Gerenciamento de acesso
{: #am}

O conceito de gerenciamento de acesso no {{site.data.keyword.Bluemix_notm}} consiste em alguns componentes inter-relacionados, incluindo usuários, recursos, políticas, funções, ações e o sistema de controle Cloud IAM, que permitem que os usuários tomem ações em recursos dentro de uma conta. 

É possível revisar a lista a seguir para saber mais sobre esses componentes do Cloud IAM:

<dl>
<dt>Usuários</dt>
<dd>Todos os usuários dentro de uma conta são identificados por seus IBMids. Os usuários podem ser convidados para a conta e receber acesso aos recursos. O acesso pode ser designado a recursos individuais, até o nível da instância ou a um conjunto de recursos que são organizados em um grupo de recursos da conta.</dd>
<dt>Grupo de acesso</dt>
<dd>Um grupo de usuários e IDs de serviço pode ser criado pelo proprietário da conta para que o mesmo acesso
possa ser designado a todas as entidades dentro do grupo com uma política única.</dd>
<dt>Resources</dt>
<dd>Os recursos de conta são as ofertas de serviços provisionados que são selecionadas do catálogo ou recursos de baixa granularidade em uma instância de serviço.</dd>
<dt>Políticas</dt>
<dd>As políticas são como a permissão é concedida aos usuários, aos IDs de serviço e aos grupos de acesso na conta para acessar os recursos da conta. As políticas incluem um assunto, o destino e a função. O assunto é o usuário, o ID do serviço ou o grupo de acesso ao qual você está concedendo acesso. O destino da política é o recurso ao qual você deseja fornecer acesso. Além disso, as funções servem para definir o nível de acesso ou as ações permitidas no destino da política. Há diferentes tipos de políticas que permitem o acesso aos recursos da conta: uma política de grupo de recursos, uma
política de instância de recurso, uma política de toda a conta para acesso a todos os serviços ativados para o Identity
and Access e uma política em todos ou em um serviço de gerenciamento de conta. Dependendo de suas seleções, as opções de
configuração customizadas, como a definição de acesso aos recursos em uma região específica ou a definição de acesso ao
nível granular de um recurso específico de serviço em uma instância, podem estar disponíveis.</dd>
<dt>Funções</dt>
<dd>As funções de acesso do Cloud IAM permitem que um usuário conclua tarefas específicas no recurso que é definido na política. Há dois tipos de funções de acesso: gerenciamento de plataforma e acesso de serviço. As funções de gerenciamento da plataforma definem as ações permitidas para gerenciar os recursos no nível da plataforma,
como o acesso do usuário e a criação de instâncias de serviço. As funções da plataforma também se aplicam a ações que podem ser tomadas dentro do contexto de serviços de gerenciamento de conta, como convidar e remover usuários, gerenciar grupos de acesso, gerenciar IDs de serviço e ofertas do catálogo privado. Além disso, as
funções de acesso de serviço definem as ações permitidas dentro do contexto do uso do serviço, como a chamada das APIs
de serviço. Essas funções são customizadas com base no serviço que é selecionado dentro da política.</dd>
<dt>Ações</dt>
<dd>As ações são mapeadas para as funções do Cloud IAM para permitir que os usuários executem somente tarefas específicas quando eles são designados a funções diferentes. As ações permitidas para cada função podem mudar com base no serviço que está sendo acessado porque cada serviço define como essa função é mapeada para o uso do serviço. </dd>
<dt>Sistema de gerenciamento de acesso</dt>
<dd>O sistema de controle do Cloud IAM permite ou nega ações por usuários dentro do contexto de um serviço com base na política designada. Quando um usuário tenta concluir uma ação específica, o sistema de controle usa os atributos que são definidos na política para determinar se o usuário tem permissão para executar essa tarefa.</dd>
</dl>






