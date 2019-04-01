---

copyright:

  years: 2019

lastupdated: "2019-03-25"

keywords: public access, anonymous access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Ativando o acesso público aos recursos
{: #public}

O acesso público aos recursos permite que todos os usuários e IDs de serviço possam acessar um recurso específico em sua conta. Isso significa que um usuário ou um ID do serviço não precisa ser autenticado com o {{site.data.keyword.Bluemix}} para acessar informações em um depósito do {{site.data.keyword.cos_full_notm}}, por exemplo. Somente determinados serviços suportam a capacidade de fornecer acesso público a tipos de recursos específicos para o serviço. Portanto, você está limitado a criar políticas somente para serviços que suportam esse recurso.
{:shortdesc}

Para acesso público a recursos, deve-se usar o grupo de acesso **Acesso público** que é fornecido em sua conta. Esse grupo de acesso inclui todos os usuários e IDs de serviço por padrão. Não é possível excluir o grupo ou mudar a associação do grupo, mas é possível incluir, editar e excluir políticas de acesso para o grupo.

## Criando uma política para o grupo de acesso público
{: #public_policy}

Conclua as etapas a seguir para designar uma política a seu grupo de acesso público. A tarefa a seguir usa o serviço Cloud Object Storage como um exemplo para designar acesso público a um depósito denominado `mybucket123`.

1. Na barra de menus, clique em **Gerenciar** &gt; ** Acesso (IAM)** e selecione **Grupos de acesso**.
2. Selecione o grupo **Acesso público**.
3. Clique em **Designar acesso**.
4. Selecione **Cloud Object Storage** na lista de serviços.
5. Insira `bucket` para o tipo de recurso.
6. Insira `mybucket123` para o ID do recurso.
7. Clique em **Designar**.
8. Clique em **Sim** para confirmar que você deseja designar a política de acesso público ao recurso e, em seguida, clique em **Designar**.
