---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gerenciamento de usuários para empresas
{: #enterprise-access}

As empresas do {{site.data.keyword.cloud}} são valiosas para grandes empresas ou organizações que precisam agrupar um conjunto de contas enquanto ainda mantêm uma separação e isolamento entre as contas para diferentes departamentos ou equipes. O gerenciamento de usuários e seu acesso a recursos em cada conta permanecem totalmente separados, mesmo quando as contas são incluídas e organizadas em uma empresa.
{:shortdesc}

Consulte [O que é uma empresa?](/docs/account?topic=account-enterprise) para obter mais informações sobre empresas.

A lista de usuários para cada conta-filha em uma empresa é acessível apenas aos usuários na conta-filha. Isso significa que os usuários que são convidados para a empresa e os usuários que são convidados para as contas dentro da empresa permanecem completamente separados. Isso é benéfico porque é possível incluir múltiplas contas em uma empresa e organizá-las conforme necessário em grupos de contas, mas manter as listas de usuários restritas de outras contas.

Na maioria dos casos, você deseja incluir apenas os usuários em sua conta corporativa que precisam da capacidade de gerenciar a empresa. Dependendo da função que o usuário é designado no [Serviço de gerenciamento de conta corporativa](/docs/iam?topic=iam-assign-access-enterprise), ele tem níveis variados de acesso para gerenciar a empresa. Por exemplo, um usuário designado à função de Administrador no Serviço corporativo pode renomear a empresa, atualizar o domínio, visualizar o uso, criar contas e muito mais. No entanto, um usuário com a função de visualizador ou operador está limitado a visualizar a hierarquia de contas e grupos de contas da empresa.

Convidar usuários para a conta corporativa não fornece acesso para gerenciar qualquer uma das contas-filhas dentro da empresa ou seus recursos. Se você incluir um usuário em uma conta corporativa que contenha várias contas, esses usuários não terão acesso automaticamente para gerenciar essas contas no que se refere ao gerenciamento de usuários, faturamento e mais. Os usuários da conta corporativa também não têm acesso a nenhum recurso em outras contas dentro da empresa.

Se você deseja que um usuário gerencie a empresa e tenha acesso a recursos em contas-filhas, deve-se convidá-los para ambas as contas. Designar políticas de acesso na conta corporativa permite que o usuário gerencie a empresa. Além disso, a designação de políticas de acesso dentro da conta-filha permite que o usuário gerencie recursos específicos ou conclua as tarefas de gerenciamento de conta somente dentro dessa conta.
{: note}

Para obter informações sobre como designar acesso a usuários em uma empresa, consulte [Designando acesso corporativo](/docs/iam?topic=iam-assign-access-enterprise).
