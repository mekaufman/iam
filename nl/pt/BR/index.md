---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: what is IAM, IBM Cloud IAM, IAM features, IAM API

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} Identity and Access Management
{: #iamoverview}

## O que é Cloud IAM?
{: #what_is_IAM}

O {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) permite que você autentique os usuários com segurança para os serviços de plataforma e controle o acesso aos recursos de forma consistente no {{site.data.keyword.Bluemix_notm}}. ''''''junto de serviços do {{site.data.keyword.Bluemix_notm}} é ativado para usar o Cloud IAM para controle de acesso e é organizado em [grupos de recursos](/docs/resources?topic=resources-rgs#rgs) dentro de sua conta para permitir que seja fornecido aos usuários acesso rápido e fácil a mais de um recurso de cada vez. As políticas de acesso ao Cloud IAM são usadas para designar aos usuários e IDs de serviço o acesso aos recursos em sua conta. É possível agrupar usuários e IDs de serviço em um [grupo de acesso](/docs/iam?topic=iam-getstarted#getstarted) para fornecer facilmente a todas as entidades dentro do grupo o mesmo nível de acesso.

Uma política designa a um assunto, que é um usuário, [ID de
serviço](/docs/iam?topic=iam-serviceids#serviceids) ou grupo de acesso, uma ou mais funções com uma combinação de atributos que definem o escopo do acesso
a um destino. A política pode fornecer acesso a um único serviço até o nível da instância, a um conjunto de recursos
organizados juntos em um grupo de recursos ou aos serviços de gerenciamento de conta. Dependendo das
[funções do IAM](/docs/iam?topic=iam-userroles#iamusermanrol) designadas, é concedido ao assunto níveis
variados de acesso para concluir as tarefas de gerenciamento de conta, trabalhar com as instâncias de
serviço ou acessar um serviço usando a UI ou concluindo as chamadas API.


![IAM para controle de acesso em uma conta](images/iam-diagram.svg "Como o gerenciamento de acesso funciona em uma conta usandoo IAM")


Para serviços que não suportam a criação de políticas do Cloud IAM para gerenciar o acesso, é possível usar o [Acesso do Cloud Foundry](/docs/iam?topic=iam-cfaccess#cfaccess) ou as [Permissões de infraestrutura clássica](/docs/iam?topic=iam-infrapermission#infrapermission).


## Quais recursos o Cloud IAM fornece?
{: #features}

<dl>
<dt>Gerenciamento de usuários</dt>
<dd>O gerenciamento de usuários unificado permite que você inclua e exclua usuários em uma conta para serviços de plataforma e de infraestrutura clássica. É possível organizar um grupo de usuários em um grupo de acesso para tornar a designação de acesso para mais de um usuário de cada vez uma tarefa rápida e fácil.</dd>
<dt>Controle de acesso de baixa granularidade</dt>
<dd>O acesso para os usuários, os IDs de serviço e os grupos de acesso é definido por uma política. Dentro da política,
o escopo do acesso para um usuário, ID de serviço ou grupo de acesso pode ser designado a um conjunto de recursos em um
grupo de recursos, a um único recurso ou a serviços de gerenciamento de conta. Após o escopo ser configurado, é possível definir quais ações são permitidas pelo assunto da política selecionando as funções de acesso. As funções fornecem uma maneira de customizar o nível de acesso que é concedido ao assunto da política para executar
ações no destino da política, sejam elas tarefas de gerenciamento da plataforma dentro da conta, o acesso a uma UI
de serviço ou a conclusão de chamadas API.</dd>
<dt>Chaves API para autenticação do usuário</dt>
<dd>Múltiplas chaves API podem ser criadas para um usuário para suportar cenários de rotação de chave e a mesma chave pode ser usada para acessar múltiplos serviços. As chaves de API do {{site.data.keyword.cloud_notm}} permitem que os usuários que usam a autenticação de dois fatores ou um ID federado automatizem a autenticação para o console por meio da linha de comandos. Um usuário também pode ter uma única chave de API de infraestrutura clássica que pode ser usada para acessar as APIs de infraestrutura clássica; no entanto, isso não é necessário porque é possível usar as chave de API do {{site.data.keyword.cloud_notm}} para acessar as mesmas APIs.</dd>
<dt>IDs de Serviço</dt>
<dd>Um ID de serviço identifica um serviço ou um aplicativo semelhante a como um ID de usuário identifica um usuário. Estes são os IDs que podem ser usados por aplicativos para autenticar com um serviço do {{site.data.keyword.Bluemix_notm}}. As políticas podem ser designadas a cada ID do serviço para controlar o nível de acesso que é permitido por um aplicativo que usa o ID do serviço e uma chave de API pode ser criada para ativar a autenticação.</dd>
</dl>


## Como usar o Cloud IAM?
{: #howto}

É possível acessar e usar o Cloud IAM por meio da IU do Access (IAM), da CLI ou da API.

* Para acessar o Cloud IAM usando a UI, acesse **Gerenciar** &gt; **Acesso (IAM)**.
* Acesse [Gerenciando o acesso do IAM, chaves de API, IDs de serviço e grupos de acesso](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_commands_iam) para revisar os comandos da CLI disponíveis.
* Acesse os docs de API a seguir para revisar as APIs disponíveis:
    * [API de serviços de identidade do IAM](https://{DomainName}/apidocs/iam-identity-token-api){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")
    * [API de grupos de acesso do IAM](https://{DomainName}/apidocs/iam-access-groups){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")
    * [API de gerenciamento de política do IAM](https://{DomainName}/apidocs/iam-policy-management){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")
