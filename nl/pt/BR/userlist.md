---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: user list visibility, users page setting, user view access, limit access to users list, user list access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Configurando o acesso de visualização do usuário
{: #userlistview}

Como um proprietário da conta do {{site.data.keyword.Bluemix}}, é possível visualizar todos os usuários em sua conta e definir como os usuários podem visualizar outros usuários na conta.
{:shortdesc}

Quando a opção **Visualização sem restrição** é selecionada, qualquer usuário na conta pode visualizar outros usuários da página Usuários no console do {{site.data.keyword.Bluemix_notm}}. Quando a opção **Visualização restrita** é selecionada, os usuários podem visualizar somente tipos específicos de usuários na conta:

* Usuários convidados pelo usuário
* Usuários que compartilham uma organização Cloud Foundry com o usuário
* Usuários que são seus descendentes na hierarquia do usuário de infraestrutura clássica, o que significa que os usuários convidaram ou que um de seus descendentes convidou.

Por padrão, a visualização sem restrição é configurada para sua conta. Para atualizar essa configuração, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Configurações**.
2. Selecione **Visualização restrita** para a configuração **Visibilidade da lista de usuários**.
