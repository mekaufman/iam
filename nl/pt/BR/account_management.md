---

copyright:

  years: 2019

lastupdated: "2019-07-01"

keywords: account management, access, access policy, account administrator, user management, account management services, use account management services to grant users in the account access to invite users to the account, billing service, support center service, identity service, global catalog service, enterprise service

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Designando acesso a serviços de gerenciamento de conta
{: #account-services}

Como proprietário da conta ou administrador de um serviço de gerenciamento de conta, é possível usar esses serviços para conceder aos usuários acesso a tarefas completas, como convidar usuários para a conta, rastrear faturamento e uso e trabalhar com casos de suporte. Os usuários com políticas de acesso de gerenciamento de conta também podem gerenciar IDs de serviço, políticas de acesso, entradas no catálogo e grupos de acesso.
{:shortdesc}

## Criando políticas para acesso ao serviço de gerenciamento de conta
{: #account-management-access}

Para designar acesso a um ou todos os serviços de gerenciamento de conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e, em seguida, selecione **Usuários**.
2. Na linha para o usuário que você deseja designar acesso, selecione o menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) e, em seguida, clique em **Designar acesso**.
3. Selecione para designar acesso aos **Serviços de gerenciamento de conta**.
4. Selecione **Todos os serviços de gerenciamento de conta** ou selecione um serviço de gerenciamento de conta específico.
5. Selecione qualquer combinação de funções para designar o acesso desejado.

Para conceder a outro usuário acesso total à conta para propósitos de gerenciamento de acesso de usuário e de todos os recursos da conta, deve-se designar duas políticas. Uma política que fornece ao usuário acesso a todos os recursos na conta, selecionando
**Todos os serviços ativados de Identidade e Acesso** com a função de
**Administrador** e **Gerente** designada. Uma política que conceda ao usuário acesso a todos os serviços de gerenciamento de conta na conta selecionando **Todos os serviços de gerenciamento de conta** com a função **Administrador** designada.
{: tip}

## Ações e funções para serviços de gerenciamento de conta
{: #account-management-actions-roles}

As tabelas a seguir descrevem as ações que os usuários podem executar quando uma função específica é designada a eles para cada serviço de gerenciamento de conta. Revise as informações para assegurar-se de que esteja designando o nível correto de acesso a seus usuários. 

### Serviço de grupos de acesso do IAM
{: #access-groups-account-management}

É possível fornecer aos usuários acesso para visualizar, criar, editar e excluir grupos de acesso na conta, usando o serviço de gerenciamento de conta de grupos de acesso. 

| Funções | Ações |
|:-------|----------|
| Visualizador |   Visualizar grupos de acesso e membros     |
| Operador | Não aplicável    |
| Editor |  Visualizar, criar, editar e excluir grupos <br><br> Incluir ou remover usuários de grupos     |
| Administrador |  Visualizar, criar, editar e excluir grupos <br><br> Incluir ou remover usuários <br><br> Designar acesso a um grupo <br><br> Gerenciar o acesso para trabalhar com os grupos de acesso   |
{: caption="Tabela 1. Funções e ações de exemplo para o serviço Grupos de acesso" caption-side="top"}

### Gerenciamento de usuários
{: #user-management-account-management}

É possível fornecer aos usuários acesso para visualizar usuários em uma conta, convidar e remover usuários e visualizar e atualizar as configurações de perfil do usuário com o serviço de gerenciamento de conta de gerenciamento de usuários. 

| Funções | Ações |
|:-------|----------|
| Visualizador |  Visualizar usuários na conta <br><br> Visualizar configurações do perfil do usuário     |
| Operador | Visualizar usuários na conta <br><br> Visualizar configurações do perfil do usuário  |
| Editor |  Visualizar, convidar, remover e atualizar usuários da conta <br><br> Visualizar e atualizar as configurações do perfil do usuário    |
| Administrador | Visualizar, convidar, remover e atualizar usuários da conta <br><br> Visualizar e atualizar as configurações do perfil do usuário    |
{: caption="Tabela 2. Funções e ações de exemplo para o serviço Gerenciamento de usuário" caption-side="top"}

A função de visualizador no serviço de gerenciamento de usuários é uma função comumente designada para os usuários também serem designados a uma função para visualizar ou gerenciar casos de suporte. Isso é porque se um proprietário da conta restringe a visibilidade da lista de usuários nas configurações do IAM, isso pode fazer com que os usuários não possam ver os casos de suporte abertos por outros usuários na conta. No entanto, se for designada a eles a função de visualizador para o serviço de gerenciamento de usuários, a configuração de visibilidade da lista de usuários não afetará a capacidade deles de visualizar casos na conta
{: tip}

### Centro de suporte
{: #support-center-account-management}

É possível fornecer aos usuários acesso para gerenciar casos de suporte usando o serviço de centro de suporte.

| Funções | Ações |
|:-------|----------|
| Visualizador |  Visualizar casos <br><br> Procurar casos      |
| Operador |  Não aplicável    |
| Editor |  Visualizar casos <br><br> Procurar casos <br><br> Atualizar casos <br><br> Criar casos     |
| Administrador |  Visualizar casos <br><br> Procurar casos <br><br> Atualizar casos <br><br> Criar casos    |
{: caption="Tabela 3. Funções e ações de exemplo para o serviço Centro de suporte" caption-side="top"}

É comum designar aos usuários a função de visualizador no serviço de gerenciamento de usuários, além de uma política de acesso ao centro de suporte para assegurar que os usuários possam ver todos os casos na conta, independentemente de como o proprietário da conta tenha definido a configuração de visibilidade da lista de usuários. Se a configuração de visibilidade da lista de usuários estiver definida como restrita, tornando-a para que os usuários sejam restritos de ver outros usuários na conta, isso pode limitar a capacidade de um usuário de visualizar, procurar e gerenciar casos de suporte em uma conta que eles mesmos não abriram.
{: tip}

### Faturamento
{: #billing-acct-mgmt}

É possível fornecer aos usuários acesso para atualizar as configurações de conta, visualizar assinaturas, visualizar ofertas, aplicar códigos de recurso, atualizar limites de gastos e rastrear o uso utilizando o serviço de faturamento.

| Funções | Ações |
|:-------|----------|
| Visualizador | Visualizar configurações de recursos da conta <br><br> Visualizar assinaturas na conta <br><br> Visualizar o nome da conta <br><br> Visualizar grupos de recursos   |
| Operador | Visualizar configurações de recursos da conta <br><br> Visualizar assinaturas na conta <br><br> Visualizar e mudar o nome da conta <br><br> Visualizar e atualizar grupos de recursos    |
| Editor |  Visualizar e atualizar as configurações de recursos da conta <br><br> Visualizar assinaturas na conta <br><br> Visualizar ofertas na conta <br><br> Visualizar e aplicar códigos de recurso <br><br> Visualizar e mudar o nome da conta <br><br> Visualizar e atualizar os limites de gastos <br><br> Visualizar, criar e atualizar grupos de recursos    |
| Administrador |  Visualizar e atualizar as configurações de recursos da conta <br><br> Visualizar assinaturas na conta <br><br> Visualizar ofertas na conta <br><br> Visualizar e aplicar códigos de recurso <br><br> Visualizar e mudar o nome da conta <br><br> Visualizar e atualizar os limites de gastos <br><br> Visualizar saldos de assinatura e uso de faixa <br><br> Visualizar, criar, atualizar e designar acesso para gerenciar grupos de recursos  |
{: caption="Tabela 4. Funções e ações de exemplo para o serviço Faturamento" caption-side="top"}

### Serviço de identidade do IAM
{: #identity-service-account-management}

É possível fornecer aos usuários acesso para gerenciar IDs de serviço usando o serviço de identidade do IAM. Para o serviço de identidade do IAM, essas ações se aplicam a IDs de serviço dentro da conta que o usuário não criou. Todos os usuários podem criar IDs de serviço. Eles são os administradores para esses IDs e podem criar a chave de API associada e as políticas de acesso. No entanto, esse serviço de gerenciamento de conta se aplica à capacidade de visualizar, excluir e designar acesso aos IDs de serviço na conta criada por outros usuários.

| Funções | Ações |
|:-------|----------|
| Visualizador |   Visualizar IDs     |
| Operador | Criar e excluir IDs e chaves API   |
| Editor |  Crie, atualize e exclua IDs e chaves API  |
| Administrador |  Crie, atualize e exclua IDs e chaves API <br><br> Designar políticas de acesso aos IDs  |
{: caption="Tabela 5. Funções e ações de exemplo para o serviço Identidade do IAM" caption-side="top"}
{: #identity-service-acct-mgmt}


### Catálogo global
{: #global-catalog-account-management}

É possível fornecer aos usuários acesso para visualizar serviços privados no catálogo ou mudar a visibilidade de outros usuários para serviços privados usando o serviço de catálogo global.

| Funções | Ações |
|:-------|----------|
| Visualizador |   Visualizar serviços privados    |
| Operador | Não aplicável    |
| Editor |   Mudar metadados do objeto, mas não é possível mudar a visibilidade para serviços privados     |
| Administrador |  Mudar metadados do objeto ou a visibilidade para serviços privados, além de restringir a visibilidade de um serviço público   |
{: caption="Tabela 6. Funções e ações de exemplo para o serviço Catálogo global" caption-side="top"}


### Opção de todos os serviços de gerenciamento de contas
{: #all-account-management}

Para fornecer rapidamente aos usuários um amplo conjunto de acesso de gerenciamento de contas, é possível designar uma política na opção de todos os serviços de gerenciamento de conta. Dependendo da função que é selecionada, todas as ações aplicáveis por cada função selecionada para cada serviço de gerenciamento de conta podem ser concluídas pelo assunto da política.


| Funções | Ações |
|:-------|----------|
| Visualizador |  Todas as ações da função de visualizador para os serviços de gerenciamento de conta     |
| Operador |  Todas as ações da função de operador para os serviços de gerenciamento de conta     |
| Editor |  Todas as ações da função de editor para os serviços de gerenciamento de contas e a capacidade de criar grupos de recursos    |
| Administrador |  Todas as ações da função de administrador para os serviços de gerenciamento de contas e a capacidade de criar grupos de recursos   |
{: caption="Tabela 7. Funções e ações de exemplo para uma política em todos os serviços de identidade e acesso" caption-side="top"}


