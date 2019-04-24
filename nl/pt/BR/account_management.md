---

copyright:

  years: 2019

lastupdated: "2019-02-11"

keywords: account management, access, access policy, account administrator

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

Como o proprietário da conta ou o administrador de um serviço de gerenciamento de conta, é possível usar os serviços de gerenciamento de conta para conceder aos usuários na conta acesso para convidar usuários para a conta, rastrear o faturamento e o uso e trabalhar com casos de suporte. Os usuários com acesso também podem gerenciar IDs de serviço, políticas de acesso, entradas do catálogo e grupos de acesso.

## Criando políticas para acesso ao serviço de gerenciamento de conta
{: #account-management-access}

Para designar acesso a um ou todos os serviços de gerenciamento de conta, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e, em seguida, selecione **Usuários**.
2. Na linha para o usuário que você deseja designar acesso, selecione o menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) e, em seguida, clique em **Designar acesso**.
3. Selecione para designar acesso aos **Serviços de gerenciamento de conta**.
4. Selecione **Todos os serviços de gerenciamento de conta** ou selecione um serviço de gerenciamento de conta específico.
5. Selecione qualquer combinação de funções para designar o acesso desejado.

Para conceder a outro usuário acesso total à conta para propósitos de gerenciamento de acesso de usuário e de todos os recursos da conta, deve-se designar duas políticas. Uma política que conceda ao usuário
acesso a todos os recursos na conta selecionando **Todos os serviços ativados para Identity and Access** com a função **Administrador** designada. Uma política que conceda ao usuário acesso a todos os serviços de gerenciamento de conta na conta selecionando
**Todos os serviços de gerenciamento de conta** com a função **Administrador** designada.
{: tip}

## Ação para mapeamentos de função para serviços de gerenciamento de conta
{: #account-management-actions-roles}

As tabelas a seguir descrevem as ações que os usuários podem executar quando uma função específica é designada a eles para cada serviço de gerenciamento de conta. Revise as informações para assegurar-se de que esteja designando o nível correto de acesso a seus usuários.

| Funções | Ações |
|:-------|----------|
| Visualizador |   Visualizar grupos de acesso e membros     |
| Operador | Não aplicável    |
| Aplicativos |  Visualizar, criar, editar e excluir grupos <br><br> Incluir ou remover usuários de grupos     |
| Administrador |  Visualizar, criar, editar e excluir grupos <br><br> Incluir ou remover usuários <br><br> Designar acesso a um grupo <br><br> Gerenciar o acesso para trabalhar com os grupos de acesso   |
{: caption="Tabela 1. Funções e ações de exemplo para o serviço Grupos de acesso" caption-side="top"}

| Funções | Ações |
|:-------|----------|
| Visualizador |  Visualizar usuários na conta <br><br> Visualizar configurações do perfil do usuário     |
| Operador | Visualizar usuários na conta <br><br> Visualizar configurações do perfil do usuário  |
| Aplicativos |  Visualizar, convidar, remover e atualizar usuários da conta <br><br> Visualizar e atualizar as configurações do perfil do usuário    |
| Administrador | Visualizar, convidar, remover e atualizar usuários da conta <br><br> Visualizar e atualizar as configurações do perfil do usuário    |
{: caption="Tabela 2. Funções e ações de exemplo para o serviço Gerenciamento de usuário" caption-side="top"}

| Funções | Ações |
|:-------|----------|
| Visualizador |  Visualizar casos <br><br> Procurar casos      |
| Operador |  Não aplicável    |
| Aplicativos |  Visualizar casos <br><br> Procurar casos <br><br> Atualizar casos <br><br> Criar casos     |
| Administrador |  Visualizar casos <br><br> Procurar casos <br><br> Atualizar casos <br><br> Criar casos    |
{: caption="Tabela 3. Funções e ações de exemplo para o serviço Centro de suporte" caption-side="top"}

| Funções | Ações |
|:-------|----------|
| Visualizador | Visualizar configurações de recursos da conta <br><br> Visualizar assinaturas na conta <br><br> Visualizar o nome da conta <br><br> Visualizar grupos de recursos   |
| Operador | Visualizar configurações de recursos da conta <br><br> Visualizar assinaturas na conta <br><br> Visualizar e mudar o nome da conta <br><br> Visualizar e atualizar grupos de recursos    |
| Aplicativos |  Visualizar e atualizar as configurações de recursos da conta <br><br> Visualizar assinaturas na conta <br><br> Visualizar ofertas na conta <br><br> Visualizar e aplicar códigos de recurso <br><br> Visualizar e mudar o nome da conta <br><br> Visualizar e atualizar os limites de gastos <br><br> Visualizar, criar e atualizar grupos de recursos    |
| Administrador |  Visualizar e atualizar as configurações de recursos da conta <br><br> Visualizar assinaturas na conta <br><br> Visualizar ofertas na conta <br><br> Visualizar e aplicar códigos de recurso <br><br> Visualizar e mudar o nome da conta <br><br> Visualizar e atualizar os limites de gastos <br><br> Visualizar saldos de assinatura e uso de faixa <br><br> Visualizar, criar, atualizar e designar acesso para gerenciar grupos de recursos  |
{: caption="Tabela 4. Funções e ações de exemplo para o serviço Faturamento" caption-side="top"}

| Funções | Ações |
|:-------|----------|
| Visualizador |   Visualizar IDs     |
| Operador | Criar e excluir IDs e chaves API   |
| Aplicativos |  Crie, atualize e exclua IDs e chaves API  |
| Administrador |  Crie, atualize e exclua IDs e chaves API <br><br> Designar políticas de acesso aos IDs  |
{: caption="Tabela 5. Funções e ações de exemplo para o serviço Identidade do IAM" caption-side="top"}

Para o Serviço de identidade do IAM, essas ações se aplicam aos IDs de serviço dentro da conta que o usuário não criou. Todos os usuários podem criar IDs de serviço. Eles são os administradores desses IDs e podem criar a chave de API associada e as políticas de acesso. No entanto, esse serviço de gerenciamento de conta se aplica à capacidade de visualizar, excluir e designar acesso aos IDs de serviço na conta criada por outros usuários.
{: note}

| Funções | Ações |
|:-------|----------|
| Visualizador |   Visualizar serviços privados    |
| Operador | Não aplicável    |
| Aplicativos |   Mudar metadados do objeto, mas não é possível mudar a visibilidade para serviços privados     |
| Administrador |  Mudar metadados do objeto ou a visibilidade para serviços privados, além de restringir a visibilidade de um serviço público   |
{: caption="Tabela 6. Funções e ações de exemplo para o serviço Catálogo global" caption-side="top"}

| Funções | Ações |
|:-------|----------|
| Visualizador |  Todas as ações da função de visualizador para os serviços de gerenciamento de conta     |
| Operador |  Todas as ações da função de operador para os serviços de gerenciamento de conta     |
| Aplicativos |  Todas as ações da função de editor para os serviços de gerenciamento de conta     |
| Administrador |  Todas as ações da função de administrador para os serviços de gerenciamento de conta   |
{: caption="Tabela 7. Funções e ações de exemplo para uma política em todos os serviços de identidade e acesso" caption-side="top"}
