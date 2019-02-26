---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Atualizando o usuário pai de um usuário
{: #update-parent}

Se você tiver o acesso correto, será possível atualizar o pai para um usuário. A atualização do usuário pai afeta como um usuário vê outros usuários na conta quando a configuração de visibilidade da lista de usuários é configurada como restrita. Os usuários veem apenas outros usuários para os quais são pais e quaisquer outros usuários convidados por esses descendentes do usuário pai.
{:shortdesc}

Veja [configuração de visibilidade da lista de usuários](/docs/iam?topic=iam-userlistview#userlistview) para obter mais detalhes sobre a configuração. 

Se você tiver o acesso a seguir, será possível atualizar o pai para outro usuário:

* Uma política do IAM com a função de Editor ou superior no serviço de gerenciamento de usuários.
* Você é um antecessor na hierarquia de infraestrutura clássica para o usuário e tem a permissão Gerenciar a infraestrutura clássica de usuários designada


Para atualizar o pai de um usuário, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**.  
2. Selecione um nome de usuário na lista.
3. Na página Detalhes do usuário, selecione um novo usuário pai no menu **Pai**.
4. Clique em **Aplicar**.
