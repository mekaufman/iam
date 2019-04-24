---



copyright:

  years: 2018, 2019

lastupdated: "2019-03-19"

keywords: frequently asked question, faq

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:faq: data-hd-content-type='faq'}
{:note: .note}

# FAQ
{: #iamfaq}

## O que é o  {{site.data.keyword.cloud_notm}}  Identity and Access Management?
{: #whatisiam}
{: faq}

O Identity and Access Management (IAM) permite que você autentique com segurança os usuários para os serviços da
plataforma e controle o acesso aos recursos na plataforma {{site.data.keyword.cloud_notm}}. Um conjunto de
serviços do IBM Cloud é ativado para usar o Cloud IAM para controle de acesso. Eles são organizados em grupos de
recursos dentro da conta para permitir que o acesso rápido e fácil a mais de um recurso de cada
vez seja concedido aos usuários. As políticas de acesso ao Cloud IAM são usadas para designar aos usuários e IDs de serviço o acesso aos recursos em sua conta. Para obter mais informações, consulte [{{site.data.keyword.cloud_notm}}
Identity and Access Management](/docs/iam?topic=iam-iamoverview#iamoverview).

## O que é um serviço ativado para IAM?
{: #iam-enabled}
{: faq}

Um serviço ativado para IAM deve estar em um grupo de recursos e o acesso ao serviço é fornecido por meio do uso
das políticas de acesso do IAM. Ao criar um serviço ativado para IAM por meio do catálogo, deve-se designá-lo a um grupo
de recursos. Para obter mais informações, consulte [O que é um recurso?](/docs/resources?topic=resources-resource#resource)

O {{site.data.keyword.containerlong_notm}} é a única exceção; ele é controlado pelo acesso do IAM, mas é sempre designado ao grupo de recursos padrão. Portanto, você não tem a opção de escolher um ao criá-lo por meio do catálogo. Além
disso, ele não pode ser designado a nenhum outro grupo de recursos


## O IAM e o Cloud Foundry estão relacionados?
{: #iam-cloudfoundry}
{: faq}

Eles não estão relacionados. O Cloud Foundry é uma plataforma de software livre que usa as organizações, os
espaços e as funções do Cloud Foundry para o gerenciamento de acesso. O IAM é a maneira segura de autenticar os usuários
para os serviços da plataforma e controlar o acesso aos recursos na plataforma {{site.data.keyword.cloud_notm}}
usando os grupos de recursos e as funções de acesso do IAM.

Os sistemas de gerenciamento de acesso são completamente diferentes. Os recursos do IAM pertencem a um grupo de
recursos e os recursos do Cloud Foundry pertencem a uma organização e um espaço. As políticas de acesso do IAM são
usadas para fornecer acesso aos recursos em um grupo de recursos. As funções de espaço e de organização do Cloud
Foundry são usadas para fornecer aos usuários acesso aos recursos do Cloud Foundry em um espaço. O IAM não concede
acesso a nada dentro dos espaços do Cloud Foundry e as funções do Cloud Foundry não podem conceder acesso aos recursos
dentro de um grupo de recursos.

## Como descobrir ao que tenho acesso?
{: #iam-access}
{: faq}

Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione seu nome na página Usuários. Então, dependendo do acesso que esteja procurando, abra as diferentes guias:

* Para determinar o acesso que você tem nos grupos de acesso aos quais está designado, selecione **Grupos de acesso**.
* Para ver as políticas de acesso do IAM designadas a você, selecione as **Políticas de acesso**.
* Para ver o seu acesso ao Cloud Foundry para todas as organizações e os espaços, selecione **Acesso ao Cloud Foundry**.


## Como solicitar acesso a um recurso?
{: #request-access}
{: faq}

O proprietário da conta pode atualizar o seu acesso a qualquer recurso na conta ou é possível entrar em contato
com qualquer usuário que tenha a função de administrador designada no serviço ou na instância de serviço.

## Por que devo usar grupos de recursos e grupos de acesso?
{: #resource-groups}
{: faq}

Um grupo de recursos é um contêiner lógico para os recursos. Quando um recurso é criado, ele é designado a um
grupo de recursos e não pode ser movido depois de ser incluído.

Um grupo de acesso é usado para organizar facilmente um conjunto de usuários e IDs de serviço em uma única
entidade para facilitar as designações de acesso. É possível designar uma política única a um grupo de acesso para
conceder a todos os membros essas permissões. Se você tiver mais de um usuário ou ID de serviço que precisa do mesmo
acesso, crie um grupo de acesso em vez de designar o mesmo acesso múltiplas vezes por usuário ou ID de serviço
individual.

Usando os grupos de recursos e os grupos de acesso, é possível aperfeiçoar a política de cessão de acesso designando um número limitado de políticas. É possível organizar todos os recursos aos quais um grupo específico de
usuários e de IDs de serviço precisa de acesso em um único grupo de recursos, agrupar todos os usuários ou IDs de serviço
em um grupo de acesso e, em seguida, designar uma política única que fornece acesso a todos os recursos no grupo de
recursos.

Para obter mais informações, veja [Melhores práticas para designar acesso](/docs/iam?topic=iam-account_setup#account_setup).

## Como assegurar que os usuários possam criar recursos em um grupo de recursos?
{: #resources}
{: faq}

Para criar um recurso em um grupo de recursos, o usuário deve ter duas políticas de acesso: uma designada ao
próprio grupo de recursos e uma designada aos recursos no grupo. O acesso ao próprio grupo de recursos é
simplesmente o acesso ao contêiner que organiza os recursos e esse tipo de política permite que um usuário visualize,
edite ou gerencie o acesso ao grupo, mas não aos recursos dentro dele. O acesso aos serviços dentro do grupo de recursos
permite que um usuário trabalhe com as instâncias de serviço, o que significa que o usuário pode criar uma instância de
serviço.

Portanto, minimamente, o usuário deve ter o seguinte acesso:

* Função de visualizador ou superior no próprio grupo de recursos
* Função de editor ou superior no serviço ou em todos os serviços no grupo de recursos


## Qual acesso é necessário para fornecer acesso aos outros?
{: #user-access}
{: faq}

Para serviços ativados para o IAM, deve-se ter a função de Administrador no serviço ou recurso para o qual você deseja designar acesso aos usuários. Se você desejar designar acesso a todos os serviços ou recursos na conta, precisará de uma política sobre todos os serviços ativados para o Identity and Access com a função de Administrador. Além disso, para designar aos usuários acesso para serviços de gerenciamento de conta, deve-se estar designado à função de Administrador no serviço específico ou em todos os serviços de gerenciamento de conta.

Para serviços do Cloud Foundry, deve-se ter as funções de gerenciador de organização e espaço do Cloud Foundry para fornecer acesso aos recursos do Cloud Foundry.

Para a infraestrutura clássica, deve-se ter a permissão Gerenciar a infraestrutura clássica de usuários e as permissões de categoria de serviço e dispositivo para os recursos aos quais você deseja fornecer o acesso de usuário.

## Qual é a diferença entre fornecer acesso para gerenciar um grupo de recursos e fornecer acesso a recursos
dentro de um grupo de recursos?
{: #providing-access}
{: faq}

Quando você tem acesso para gerenciar um grupo de recursos, é possível visualizar, editar o nome e gerenciar o
acesso para o próprio grupo de recursos, dependendo da função designada. O acesso ao próprio grupo de recursos não
concede a um usuário acesso aos recursos dentro do grupo.

Quando você tem acesso aos recursos dentro de um grupo de recursos, é possível editar, excluir e criar instâncias
ou ter todas as ações de gerenciamento para os serviços especificados no grupo de recursos, dependendo da função
designada.

Por exemplo, funções e ações de gerenciamento de plataforma para serviços de gerenciamento de conta, veja [Tabela de funções da plataforma](/docs/iam?topic=iam-userroles#platformrolestable2).

## Quem pode remover usuários?
{: #remove-users}
{: faq}

O proprietário da conta pode remover quaisquer usuários da conta e qualquer usuário com o acesso a seguir pode remover usuários de uma conta:

* Uma política do IAM para o serviço de gerenciamento de conta de gerenciamento de usuários com a função de Administrador designada e ser o gerente da organização do Cloud Foundry se o usuário pertencer a uma organização do Cloud Foundry.
* Se você tiver uma infraestrutura clássica em sua conta, um usuário deverá ter uma política do IAM para o serviço de gerenciamento de conta de gerenciamento de usuários com a função de Administrador designada, ser o gerente da organização do Cloud Foundry se o usuário pertencer a uma organização do Cloud Foundry e ser um antecessor do usuário na hierarquia do usuário de infraestrutura clássica com a permissão Gerenciar a infraestrutura clássica de usuários designada.

## Como requerer a autenticação de diversos fatores do IBMid para minha conta?
{: #multi-factor}
{: faq}

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **Configurações**.
2. Na seção de login da Conta, selecione **Atualizar** para selecionar a MFA para todos os usuários ou apenas para os usuários não federados.

Para obter mais informações, veja [Requerendo MFA para usuários em sua conta](/docs/iam?topic=iam-enablemfa#enablemfa).

## Qual é a diferença entre as funções do serviço e da plataforma?
{: #service-platform-roles}
{: faq}

As funções do serviço e da plataforma são dois tipos diferentes de funções:

* As funções da plataforma se referem a como você trabalha com um serviço dentro de uma conta, como a criação
de instâncias, a ligação de instâncias e o gerenciamento do acesso do usuário ao serviço. Para os serviços da plataforma,
essas funções permitem que os usuários criem os grupos de recursos e gerenciem os IDs de serviço, por exemplo. As
funções da plataforma são: administrador, editor, operador e visualizador.

* As funções de serviço definem a capacidade de executar ações em um serviço e são específicas para todos os
serviços, como a execução de chamadas API ou o acesso à UI. As funções de serviço são: gerenciador, gravador e leitor. Para obter mais informações sobre como essas funções se aplicam, consulte a documentação do serviço específico.

## Qual é a diferença entre um grupo de recursos e as organizações e os espaços do Cloud Foundry?
{: #groups-organizations}
{: faq}

Com o início do {{site.data.keyword.Bluemix_notm}}, um serviço da plataforma de software livre para
controle de acesso e organização de recursos chamado Cloud Foundry era o único método para organizar e controlar o
acesso aos recursos. Como o {{site.data.keyword.Bluemix_notm}} expandiu, foi necessário um novo método que pode ser usado por todos os tipos de serviços e recursos. Os grupos de recursos agora são usados para agrupar e organizar muitos tipos de recursos e o IAM é usado para controlar consistentemente o acesso aos serviços e recursos. Vários serviços já foram adotados usando grupos de recursos e IAM e os serviços adicionais serão movidos ao longo do tempo para o novo método para organizar recursos e gerenciar o acesso.

O controle de acesso e a organização do recurso da conta são as principais diferenças entre os grupos de recursos
e as organizações e os espaços do Cloud Foundry. Os grupos de recursos organizam os serviços ativados para o IAM em uma
conta que tem o acesso controlado por meio do uso das políticas do IAM. As organizações e os espaços são gerenciados
usando as funções do Cloud Foundry para controle de acesso e os recursos do Cloud Foundry são designados aos espaços. As
organizações e os espaços podem ser usados para organizar e controlar o acesso aos recursos somente dentro da região do
Cloud Foundry, enquanto os grupos de recursos e o IAM podem ser usados para múltiplos tipos de recursos no {{site.data.keyword.Bluemix_notm}}.

## Como delegar recursos do administrador de conta?  
{: #account-administrator}
{: faq}

Para delegar os recursos do administrador de conta, designe o acesso a seguir:

* Uma política do IAM com a função de Administrador em Todos os serviços ativados para o Identity and Access, que permite a um usuário criar instâncias de serviço e designar aos usuários acesso a todos os recursos na conta.
* Uma política do IAM com a função de Administrador em Todos os serviços de gerenciamento de conta, que permite que um usuário conclua tarefas como convidar e remover usuários, gerenciar grupos de acesso, gerenciar IDs de serviço, gerenciar ofertas do catálogo privado e rastrear faturamento e uso.
* A permissão de Superusuário configurada para a infraestrutura clássica
* Gerenciador do Cloud Foundry para todas as organizações


## Qual é a diferença entre um administrador de conta e um proprietário da conta?
{: #owner-administrator}
{: faq}

Os proprietários da conta são designados automaticamente como o administrador de conta para o {{site.data.keyword.Bluemix_notm}} IAM. Como o administrador de conta, é possível convidar usuários, designar e gerenciar o acesso para usuários, criar grupos de recursos, requerer a MFA para todos os usuários na conta e criar instâncias de serviço. Se você deseja tornar outros usuários em sua conta um administrador de conta, designe a eles o acesso a seguir:

* Uma política do IAM com Administrador em Todos os serviços ativados para o Identity and Access, que permite a um usuário criar instâncias de serviço e designar aos usuários acesso a todos os recursos na conta.
* Uma política do IAM com Administrador em Todos os serviços de gerenciamento de conta, que permite que um usuário conclua tarefas como convidar usuários, gerenciar grupos de acesso, gerenciar IDs de serviço, gerenciar ofertas do catálogo privado e controlar faturamento e uso.
* A permissão de Superusuário configurada para a infraestrutura clássica
* Gerenciador do Cloud Foundry para todas as organizações

## Como designar acesso a infraestrutura e dispositivos?
{: #infrastructure-devices}
{: faq}

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.
2. Selecione o nome de um usuário.
3. Clique em **Infraestrutura clássica**.
4. Designe permissões na seção **Permissões**, designe acesso a dispositivos na seção **Dispositivos** e designe acesso a sub-redes VPN para os dispositivos aos quais o usuário tem acesso designado na seção **Acesso à VPN **.

## Todos os usuários em minha conta podem ver todos os outros usuários?
{: #users}
{: faq}

Um proprietário da conta pode visualizar todos os usuários na conta e escolher como os usuários podem visualizar outros usuários na conta na página Usuários. Um proprietário da conta pode ajustar a [configuração de visibilidade da lista de usuários](/docs/iam?topic=iam-userlistview#userlistview) na página Configurações, selecionando uma das opções a seguir:

* **Visualização sem restrição**: todos os usuários em sua conta podem visualizar todas as pessoas na conta.
* **Visualização restrita**: limita a capacidade de visualizar usuários na página Usuários para somente aqueles que tiveram acesso explícito concedido, juntamente com aqueles que têm visibilidade de outros usuários por meio de uma organização do Cloud Foundry compartilhada ou um relacionamento de hierarquia do usuário de infraestrutura clássica.


## Eu tenho que designar acesso a um usuário quando o convido para a conta?
{: #account-invite}
{: faq}

Sim. Deve-se designar um acesso de usuário dentro de um dos três sistemas de gerenciamento de acesso:

* Uma política de acesso do IAM em um recurso, grupo de recursos ou serviços de gerenciamento de conta
* Uma função do Cloud Foundry para uma organização e um espaço
* Uma permissão configurada para a infraestrutura clássica


## Como incluir a autenticação em meus apps móveis e da web?
{: #appid}
{: faq}

O IAM é usado para gerenciar o acesso a seus serviços e recursos do {{site.data.keyword.cloud_notm}}. Com o {{site.data.keyword.appid_full_notm}}, é possível levar a segurança de nuvem um passo adiante, incluindo a autenticação em seus apps móveis e da web. Com apenas algumas linhas de código, é possível proteger facilmente seus apps e serviços nativos da Nuvem que são executados no {{site.data.keyword.cloud_notm}}. Pronto para iniciar? [Verifique os docs](/docs/services/appid?topic=appid-getting-started#getting-started). 
