---

copyright:

  years: 2015, 2019

lastupdated: "2019-01-29"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:new_window: target="_blank"}

# Acesso ao IAM
{: #userroles}

Todos os serviços que são organizados em um grupo de recursos em sua conta são gerenciados usando o {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM). Os proprietários de contas são designados automaticamente à função de administrador de conta para o Cloud IAM. Como o administrador de conta, é possível designar e gerenciar o acesso para usuários, criar grupos de recursos, criar grupos de acesso, visualizar detalhes do faturamento, controlar o uso e criar instâncias de serviço. Forneça
acesso a usuários, IDs de serviço e grupos de acesso criando políticas que configurem um destino para o
assunto da política a ser acessada e uma função que defina qual tipo de acesso será permitido.
{: shortdesc}

## O que são políticas do Cloud IAM e quem pode designá-las?
{: #iamusermanpol}

Uma política concede a um sujeito uma ou múltiplas funções a um conjunto de recursos para que ações específicas possam ser executadas dentro do contexto dos recursos de destino especificados. Será possível designar e gerenciar políticas se você possuir a função adequada. A tabela a seguir mostra as tarefas de gerenciamento de política e a função que é necessária para cada uma.

| Ações | Função necessária |
|----------|---------|
| Criar uma política em uma conta para todos os serviços e instâncias | Proprietário da conta ou administrador em todos
os serviços de gerenciamento de conta e todos os serviços ativados para o Identity and Access | 
| Criar uma política em um serviço em uma conta | Proprietário da conta, administrador em todos os serviços ativados para
o Identity and Access ou administrador no serviço na conta |
| Criar uma política em uma instância de serviço | Proprietário da conta, administrador em todos os serviços ativados
para o Identity and Access, administrador no serviço na conta, administrador em todos os serviços no grupo de
recursos relevantes ou administrador na instância de serviço |
{: caption="Tabela 1. Usuários que têm permissão para criar políticas de acesso" caption-side="top"} 

Ao designar uma política, você
inicia com o assunto. Depois de selecionar o assunto da política, é possível optar por configurar a política para um grupo de recursos, um recurso individual ou um serviço de gerenciamento de conta. 

Em seguida, dependendo de sua seleção inicial, é possível selecionar dentre as opções:
  
  * Um serviço dentro de um grupo de recursos
  * Todos os recursos em um grupo de recursos
  * Todas as instâncias ou uma única instância para o recurso selecionado
  * Todos os serviços ativados para IAM na conta
  * Um serviço de gerenciamento de conta 

Mais opções de configuração podem estar disponíveis, dependendo do serviço selecionado. Finalmente, você seleciona as funções a serem designadas. 

## Tipos de política de acesso comum
{: #policytypes}

É possível fornecer acesso de baixa granularidade para os usuários, os IDs de serviço ou os grupos de acesso
designando os tipos de políticas de acesso a seguir:

* Todos os serviços de gerenciamento de conta
* Serviço gerenciamento de conta específico
* Todos os recursos na conta
* Todos os recursos dentro de todos os serviços que pertencem a um grupo de recursos individuais com a capacidade de
gerenciar o grupo de recursos
* Todos os recursos dentro de um único serviço em um grupo de recursos com a capacidade de gerenciar o grupo de
recursos
* Todos os recursos dentro de um único serviço na conta, independentemente do grupo de recursos ao qual eles estão designados
* Recursos em uma instância individual
* Um tipo de recurso único dentro de uma instância, por exemplo, um depósito em uma instância do {{site.data.keyword.objectstorageshort}}

Para conceder a outro usuário acesso total à conta para os propósitos de gerenciamento de acesso de usuário e gerenciamento de todos os recursos de conta, deve-se designar duas políticas. Uma política que conceda ao usuário
acesso a todos os recursos na conta selecionando **Todos os serviços ativados para Identity and Access** com a função **Administrador** designada. Uma política que conceda ao usuário acesso a todos os serviços de gerenciamento de conta na conta selecionando
**Todos os serviços de gerenciamento de conta** com a função **Administrador** designada.
{: tip}

## Funções do Cloud IAM
{: #iamusermanrol}

Com o Cloud IAM, é possível gerenciar e definir acesso para usuários e recursos em sua conta. Dois tipos de
funções podem ser designadas: funções de gerenciamento de plataforma e funções de acesso de serviço.

<dl>
<dt>Funções de gerenciamento de plataforma</dt> 
<dd>As funções de gerenciamento da plataforma abrangem uma gama de ações, incluindo a capacidade de criar e
excluir instâncias, gerenciar aliases, ligações, credenciais e acesso. As funções da plataforma são administrador,
editor, operador, visualizador. As funções de gerenciamento de plataforma também se aplicam a serviços de gerenciamento de conta que permitem que os usuários convidem usuários, gerenciem IDs de serviço, políticas de acesso, entradas do catálogo e rastreiem faturamento e uso, dependendo de sua função designada em um serviço de gerenciamento de conta.</dd>
<dt>Funções de acesso de serviço</dt>
<dd>As funções de acesso de serviço definem a capacidade de um usuário ou serviço executar ações em uma instância de serviço, como acessar o console ou executar chamadas API. As funções de acesso de serviço são gerenciador, gravador e leitor. </dd>
</dl> 

Você pode não ver todas as funções que estão listadas aqui como opções ao designar as políticas na UI, pois
somente as funções disponíveis para o serviço escolhido serão exibidas. Para obter mais informações sobre quais funções estão ativadas e quais ações cada função de acesso permite para cada serviço, veja a documentação para esse serviço.
{: note}

### Funções de gerenciamento de plataforma
{: #platformroles}

Com as funções de gerenciamento de plataforma, os usuários podem receber níveis variados de permissão para executar ações de plataforma dentro da conta e em um serviço. Por exemplo, as funções de gerenciamento
da plataforma que são designadas para os recursos do catálogo permitem que os usuários concluam ações como, criar,
excluir, editar e visualizar instâncias de serviço. Além disso, as funções de gerenciamento da plataforma que são
designadas para os serviços de gerenciamento de conta permitem que os usuários concluam ações como, convidar e remover
usuários, trabalhar com grupos de recursos e visualizar as informações de faturamento. Para obter mais informações sobre os serviços de gerenciamento de conta, consulte [Tabela 3. Exemplo de funções de gerenciamento de plataforma e ações para serviços de gerenciamento de conta](#platformrolestable2).

As tabelas a seguir fornecem exemplos para algumas das ações de gerenciamento de plataforma que os usuários podem executar dentro do contexto de recursos de catálogo, grupos de recursos e serviços de gerenciamento de conta. Consulte a documentação para cada oferta de catálogo para entender como as funções se aplicam aos usuários dentro do contexto do serviço que está sendo usado.

A primeira linha da tabela descreve opções separadas que podem ser escolhidas ao criar uma política e a primeira
coluna descreve as funções selecionadas para a política. As células restantes mapeiam qual função é selecionada na
primeira coluna e o tipo de política selecionado nas opções da primeira linha.

| Detalhes da política de acesso | Ações em serviços na conta | Ações em recursos em grupos de recursos | Ações para acesso a grupos de recursos |
|:--------------|:------------|:-------------|:-------------|
|  | Um ou todos os serviços ativados por IAM | Serviço selecionado em um grupo de recursos | Grupo de recursos selecionados |
| Função de visualizador | Visualizar instâncias, aliases, ligações e credenciais | Visualizar somente instâncias especificadas no grupo de recursos | Visualizar grupo de recursos |
| Função de operador |  Visualizar instâncias e gerenciar aliases, ligações e credenciais |  Não aplicável | Não aplicável |
| Função do editor |  Criar, excluir, editar e visualizar instâncias. Gerenciar aliases, ligações e credenciais | Criar, excluir, editar, suspender, continuar, visualizar e ligar somente as instâncias especificadas no grupo de recursos | Visualizar e editar o nome do grupo de recursos |
| Função de administrador |  Todas as ações de gerenciamento para serviços | Todas as ações de gerenciamento para as instâncias especificadas no grupo de recursos | Visualizar, editar e gerenciar o acesso para o grupo de recursos |
{: caption="Tabela 2. Exemplo de funções de gerenciamento da plataforma e ações para os serviços em uma conta" caption-side="top"}
{: #platformrolestable1}

A tabela a seguir descreve as ações comuns que podem ser executadas com base na função designada para cada serviço de gerenciamento de conta. Role horizontalmente para ver todas as entradas na tabela.
{: #acctmgmt}

Se você designar uma política de acesso em **Todos os serviços de gerenciamento de conta**, dependendo da função selecionada, o usuário poderá concluir as ações a seguir para cada serviço para essa função. Além disso, esse tipo de política fornece acesso do usuário às informações de faturamento e à capacidade de rastrear o uso com base em sua função designada. Consulte a tabela a seguir para obter detalhes.
{: note}

A primeira linha da tabela descreve serviços específicos que podem ser escolhidos ao criar uma política e a primeira
coluna descreve o tipo selecionado de função para a política. As células restantes mapeiam qual função
é selecionada nas opções da primeira coluna e o tipo de política selecionado nas opções da primeira linha.

| Detalhes da política de acesso |  Ações para IDs de serviço  | Ações para gerenciar grupos de acesso | Ações para gerenciar o acesso ao catálogo | Ações para acesso para gerenciar usuários | Ações para Suporte | Ações para faturamento | Ações para todos os serviços de gerenciamento de conta | 
|:--------------|:-------------|:--------------|:--------------|:-----------|:--------------|:--------------|:--------------|
|  |  Serviço de identidade do IAM |  Grupos de acesso ao IAM |  Catálogo de recursos global |  Gerenciamento de usuários  | Centro de suporte | Faturamento e uso | Todos os serviços de gerenciamento de conta |
| Função de visualizador |  <ul><li>Visualizar IDs</li></ul> |  <ul><li>Visualizar grupos de acesso e membros</li></ul> | <ul><li>Visualizar serviços privados</li></ul>  |  <ul><li>Visualizar usuários na conta</li><li>Visualizar configurações do perfil do usuário</li></ul> | <ul><li>Visualizar casos</li><li>Procurar casos</li></ul> | <ul><li>Visualizar configurações de recursos da conta</li><li>Visualizar assinaturas na conta</li><li>Visualizar o nome da conta</li><li>Visualizar grupos de recursos</li></ul> | Todas as ações da função de visualizador para os serviços de gerenciamento de conta |
| Função de operador | <ul><li>Criar e excluir IDs e chaves API</li></ul> |  <ul><li>Não aplicável</li></ul> | <ul><li>Não aplicável</li></ul> |  <ul><li>Visualizar usuários na conta</li><li>Visualizar configurações do perfil do usuário</li></ul> | <ul><li>Não aplicável</li></ul> | <ul><li>Visualizar configurações de recursos da conta</li><li>Visualizar assinaturas na conta</li><li>Visualizar e mudar o nome da conta</li><li>Visualizar e atualizar grupos de recursos</li></ul> | Todas as ações da função de operador para os serviços de gerenciamento de conta |
| Função do editor |  <ul><li>Crie, atualize e exclua IDs e chaves API</li></ul> |  <ul><li>Visualizar, criar, editar e excluir grupos</li><li>Incluir ou remover usuários de grupos</li></ul> | <ul><li>É possível mudar os metadados do objeto, mas não é possível mudar a visibilidade para serviços privados</li></ul>  | <ul><li>Visualizar, convidar, remover e atualizar usuários da conta</li><li>Visualizar e atualizar as configurações do perfil do usuário</li></ul> |  <ul><li>Visualizar casos</li><li>Procurar casos</li><li>Atualizar casos</li><li>Criar casos</li></ul> | <ul><li>Visualizar e atualizar as configurações de recursos da conta</li><li>Visualizar assinaturas na conta</li><li>Visualizar ofertas na conta</li><li>Visualizar e aplicar códigos de recurso</li><li>Visualizar e mudar o nome da conta</li><li>Visualizar e atualizar os limites de gastos</li><li>Visualizar, criar e atualizar grupos de recursos</li></ul> | Todas as ações da função de editor para os serviços de gerenciamento de conta |
| Função de administrador |   <ul><li>Crie, atualize e exclua IDs e chaves API</li><li>Designar políticas de acesso aos IDs</li></ul> |  <ul><li>Visualizar, criar, editar e excluir grupos</li><li>Incluir ou remover usuários</li><li>Designar acesso a um grupo</li><li>Gerenciar o acesso para trabalhar com os grupos de acesso</li></ul> | <ul><li>É possível mudar metadados do objeto ou visibilidade para serviços privados e restringir a visibilidade de um serviço público</li></ul> | <ul><li>Visualizar, convidar, remover e atualizar usuários da conta</li><li>Visualizar e atualizar as configurações do perfil do usuário</li></ul> |  <ul><li>Visualizar casos</li><li>Procurar casos</li><li>Atualizar casos</li><li>Criar casos</li></ul> |  <ul><li>Visualizar e atualizar as configurações de recursos da conta</li><li>Visualizar assinaturas na conta</li><li>Visualizar ofertas na conta</li><li>Visualizar e aplicar códigos de recurso</li><li>Visualizar e mudar o nome da conta</li><li>Visualizar e atualizar os limites de gastos</li><li>Visualizar saldos de assinatura e uso de faixa</li><li>Visualizar, criar, atualizar e designar acesso para gerenciar grupos de recursos</li></ul> | Todas as ações da função de administrador para os serviços de gerenciamento de conta|
{: caption="Tabela 3. Exemplo de funções de gerenciamento da plataforma e as ações para os serviços degerenciamento de conta" caption-side="top"}

{: #platformrolestable2}

Para o Serviço de identidade do IAM, essas ações se aplicam aos IDs de serviço dentro da conta que o usuário não criou. Todos os usuários podem criar IDs de serviço. Eles são o administrador desses IDs e podem criar a chave de API associada e as políticas de acesso, mas esse serviço de gerenciamento de conta se aplica à capacidade de visualizar, excluir e designar acesso aos IDs de serviço na conta criada por outros usuários.
{: note}

Alguns serviços podem mapear ações específicas para as funções de gerenciamento de plataforma que estão relacionadas ao gerenciamento do serviço em vez do acesso do serviço. Como um exemplo, consulte a tabela a seguir que detalha as ações de serviço do {{site.data.keyword.containershort_notm}} mapeadas para essas funções.

| Função de gerenciamento da plataforma | Ações | Exemplo de ações para o {{site.data.keyword.containershort_notm}} |
|:-----------------|:-----------------|:-----------------|
| Visualizador | Pode visualizar instâncias de serviço, mas não pode modificá-las  | <ul><li>Listar clusters</li><li>Visualizar detalhes para um cluster</li></ul>|
| Aplicativos | Executar todas as ações da plataforma, exceto para gerenciar a conta e designar políticas de acesso |<ul><li>Ligar um serviço a um cluster</li><li>Criar um webhook</li></ul> |
| Operador | Executar ações de plataforma necessárias para configurar e operar instâncias de serviço, como visualizar o painel de um serviço | <ul><li>Incluir ou remover nós do trabalhador</li><li>Reiniciar ou recarregar nós do trabalhador</li><li>Ligar um serviço a um cluster</li></ul> |
| Administrador | Executar todas as ações da plataforma com base no recurso para o qual essa função está sendo designada, incluindo a designação de políticas de acesso a outros usuários |<ul><li>Remover um cluster</li><li>Criar um cluster</li><li>Atualizar políticas de acesso de usuário</li><li>Todas as ações que um visualizador, um editor e um operador podem executar</li></ul>|
{: caption="Tabela 4. Exemplo de funções de gerenciamento da plataforma e as ações para o serviço do{{site.data.keyword.containershort_notm}}" caption-side="top"}


### Funções de acesso de serviço

As funções de acesso ao serviço permitem que os usuários sejam designados a diferentes níveis de permissão para chamar a API do serviço e acessar a UI para o serviço. A tabela a seguir fornece exemplos de ações que podem ser tomadas dependendo das funções designadas com base no uso do serviço {{site.data.keyword.objectstorageshort}}.

As ações que podem ser executadas com base em cada função designada variam com base no serviço que você selecionou para a política. Nem todos os serviços usam esses tipos de funções. Consulte a documentação para o serviço para obter mais detalhes.
{: note}

| Função de acesso de serviço | Ações | Exemplo de ações para o serviço do {{site.data.keyword.objectstorageshort}} |
|:-----------------|:-----------------|:-----------------|
|  Leitor | Executar ações somente leitura em um serviço, como visualizar recursos específicos do serviço | Listar e fazer download de objetos |
| Gravador | Permissões além da função de leitor, incluindo criar e editar recursos específicos do serviço | Criar e destruir depósitos e objetos |
| Gerente | Permissões além da função de gravador para concluir ações privilegiadas, conforme definido pelo serviço, além de criar e editar recursos específicos do serviço | Gerenciar todos os aspectos de armazenamento de dados, criar e destruir depósitos e objetos |
{: caption="Tabela 5. Exemplo de funções e ações de usuário de acesso de serviço" caption-side="top"}



