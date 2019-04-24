---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: service ID, service ID API key, lock service ID API key, delete service ID API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Gerenciando chaves API do ID de serviço
{: #serviceidapikeys}

Os IDs de serviço são criados para permitir acesso aos serviços do {{site.data.keyword.Bluemix_notm}} por aplicativos hospedados dentro e fora do {{site.data.keyword.Bluemix_notm}}. As chaves API são usadas por um aplicativo para autenticar como um ID de serviço específico e receber o acesso associado a esse ID de serviço.

Depois de criar um ID de serviço, será possível começar a criar as chaves API e designar políticas de serviço. Cada política especifica o nível de acesso permitido quando a chave API é usada para autenticação nos serviços. Para obter mais informações sobre como criar um ID do serviço e designar políticas, veja [Criando e trabalhando com IDs de serviço](/docs/iam?topic=iam-serviceids#serviceids). Para obter detalhes sobre os comandos da CLI que são usados para gerenciar as chaves de API do ID do serviço, veja [Gerenciando o acesso do IAM, chaves de API, IDs de serviço e grupos de acesso](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_commands_iam).

Cada chave API que estiver associada a um ID de serviço herdará a política que tiver sido designada ao ID de serviço. Por exemplo, se você desejar que um aplicativo seja capaz de simplesmente visualizar recursos em um serviço, será necessário usar uma chave de API associada a um ID do serviço que tenha uma política designada com a função de Visualizador. E, se você desejar que outro aplicativo seja capaz de ter acesso total dentro de um serviço, será necessário usar uma chave de API associada a um segundo ID do serviço que tenha uma política designada com a função de Administrador.

Para obter mais informações, consulte
[Exemplos de como usar um ID de serviço](/docs/iam?topic=iam-serviceids#examples_serviceid).

## Criando uma chave API para um ID de serviço
{: #create_service_key}

Crie uma chave API para associar a um ID de serviço.

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **IDs de serviço**.
2. Se você não tiver um ID de serviço já criado, crie o ID de serviço.
3. No menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg), clique em **Gerenciar ID do serviço**.
4. Clique em **Chaves de API**.
5. Clique em **Criar**.
6. Inclua um nome e uma descrição para identificar facilmente a chave API.
7. Clique em **Criar**.
8. Salve sua chave API copiando ou fazendo download dela em um local seguro.

Por motivos de segurança, a chave API está disponível apenas para ser copiada ou transferida por download no momento da criação. Se a chave API for perdida, uma nova chave API deverá ser criada.
{: note}

Para criar uma chave API para um ID de serviço usando a CLI, é possível usar o comando [ibmcloud iam service-api-key-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_create).
```
ibmcloud iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [--file FILE] [-f, --force]
```
{: codeblock}

## Atualizando uma chave API para um ID de serviço
{: #update_service_key}

É possível atualizar uma chave API editando o nome ou a descrição usada para identificar a chave na UI.

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **IDs de serviço**.
2. No menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg), clique em **Gerenciar ID do serviço**.
3. Clique em **Chaves de API**.
4. No menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg), clique em **Editar nome e descrição**.

Para atualizar uma chave API para um ID de serviço usando a CLI, é possível usar o comando [ibmcloud iam service-api-key-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_update).
```
ibmcloud iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```
{: codeblock}

## Bloqueando um ID da chave API de serviço
{: #lockkey}

Para chaves API que representam a identidade do ID do serviço, é possível evitar que a chave API seja excluída bloqueando-a. Uma chave API bloqueada é indicada pelo ícone ![Ícone Bloqueado](images/locked.svg "Bloqueado") na UI.

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **IDs de serviço**.
2. Identifique a linha do ID do serviço para o qual você deseja selecionar uma chave API e selecione o nome do ID do serviço.
3. Clique em **Chaves de API**.
4. Passe o mouse sobre a linha da chave de API que você deseja bloquear e clique no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg) para abrir uma lista de opções.
5. Clique em **Bloquear API key**.

É possível desbloquear sua chave API a qualquer momento para atualizar, excluir ou incluir uma política de acesso ou para remover a chave API.
{: tip}

### Bloqueando ou desbloqueando uma chave API do ID do serviço com a CLI
{: #lock_unlock_cli}

Para bloquear uma chave API do ID do serviço, use o comando a seguir:

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>APIKEY_NAME (necessário)</dt>
  <dd>Nome da chave API, exclusivo com APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necessário)</dt>
  <dd>UUID da chave API, exclusivo com APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necessário)</dt>
  <dd>Nome do ID do serviço, exclusivo com SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necessário)</dt>
  <dd>UUID do ID do serviço, exclusivo com SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Bloquear a chave API de serviço `sample-key` do ID do serviço `sample-service`:

```
Ibmcloud iam service-api-key-bloqueio sample-key sample-service
```

Para desbloquear uma chave API do ID do serviço, use o comando a seguir:

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## Excluindo uma chave API de um ID de serviço
{: #delete_service_key}

É possível excluir uma chave API associada a um ID de serviço. No entanto, a exclusão de uma chave API atualmente em uso por um aplicativo removerá a capacidade de autenticação desse aplicativo nos serviços.

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **IDs de serviço**.
2. Se você não tiver um ID de serviço já criado, crie o ID de serviço.
3. No menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg), clique em **Gerenciar ID do serviço**.
4. Clique em **Chaves de API**.
5. No menu **Ações** ![Icone Lista de ações](../icons/action-menu-icon.svg), clique em **Excluir**.

Para excluir uma chave API para um ID de serviço usando a CLI, é possível usar o comando [ibmcloud iam service-api-key-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_delete).
```
ibmcloud iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```
{: codeblock}
