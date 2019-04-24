---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: Cloud Foundry roles, Cloud Foundry access, auditor, manager, developer, billing manager

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Acesso ao Cloud Foundry
{: #cfaccess}

Atualmente, nem todos os serviços podem ser gerenciados usando o Cloud IAM. É possível continuar a usar
funções do Cloud Foundry para acessar essas instâncias de serviço. Os usuários são incluídos na organização e
no espaço aos quais a instância pertence com uma função do Cloud Foundry designada.
{:shortdesc}


![Acesso usando organizações e espaços do Cloud Foundry em uma conta](images/cf-diagram.svg "Como o acesso em uma conta funciona usando organizações,espaços e funções do Cloud Foundry")



## Funções do Cloud Foundry
{: #cfroles}

As funções do Cloud Foundry concedem acesso a organizações e espaços dentro da conta. As funções do Cloud Foundry não ativam as permissões de usuário para concluir ações dentro do contexto de um serviço na conta.

As funções a seguir podem ser designadas no nível de organização:

| Função organizacional | Permissões |
|-------------------|-------------|
|Gerente | Os gerenciadores de organização podem criar, visualizar, editar ou excluir espaços dentro da organização, visualizar o uso e cota da organização, convidar os usuários para a organização, gerenciar quem tem acesso à organização e suas funções na organização, além de gerenciar domínios customizados para a organização. |
|Gerenciador de faturamento | Gerenciadores de faturamento podem visualizar informações de uso de tempo de execução e serviço para a organização na página de Painel de uso.  |
|Auditor | Auditores da organização podem visualizar o conteúdo do aplicativo e do serviço na organização. Os auditores também podem visualizar os usuários na organização e suas funções designadas, além da cota da organização. |
{:caption="Tabela 1. Funções e permissões de organização" caption-side="top"}

As funções a seguir podem ser designadas no nível de espaço:

| Função de espaço | Permissões |
|------------|-------------|
|Gerente | Os gerenciadores de espaço podem incluir usuários existentes e gerenciar funções dentro do espaço. O gerenciador de espaço também pode visualizar o número de instâncias, ligações de serviço e
o uso recurso para cada aplicativo no espaço. |
|Desenvolvedor | Desenvolvedores de espaço podem criar, excluir e gerenciar aplicativos e serviços dentro do espaço. Algumas das tarefas de gerenciamento incluem implementação de apps, início ou parada de aplicativos,
renomeação de um app, exclusão de um app, renomeação de um espaço, ligação ou desvinculação de um serviço para
um aplicativo, visualização do número ou de instâncias, ligações de serviço e uso de recurso para cada
aplicativo no espaço. Além disso, o desenvolvedor de espaço pode associar uma URL interna ou externa com um aplicativo no espaço.   |
|Auditor | Auditores de espaço têm acesso somente leitura a todas as informações sobre o espaço, como informações sobre o número de instâncias, ligações de serviço e uso de recurso para cada aplicativo no
espaço. |
{:caption="Tabela 2. Funções e permissões de espaço" caption-side="top"}

Os usuários que são designados à função de espaço de gerenciador ou desenvolvedor podem acessar a variável de ambiente VCAP_SERVICES. No entanto, um usuário designado à função de auditor não pode acessar VCAP_SERVICES.
{: note}
