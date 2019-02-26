---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gerenciando chaves API do usuário
{: #userapikey}

Um usuário federado ou não federado pode criar uma chave API a ser usada na CLI ou como parte da automação para efetuar login como sua identidade do usuário. É possível usar a UI ou CLI para gerenciar suas chaves API, listando suas chaves, criando chaves, atualizando chaves ou excluindo chaves. Para gerenciar as chaves de API do {{site.data.keyword.Bluemix_notm}} que estão associadas à sua identidade do usuário, acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**. Em seguida, clique em seu nome na lista e selecione a opção **Detalhes do usuário** para ver uma lista de suas chaves de API com descrições e datas. Em seguida, é possível criar, editar ou excluir chaves API. E, para obter uma lista completa de comandos da CLI disponíveis, veja [`ibmcloud iam api-keys`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_keys).

Como um [usuário federado](/docs/account?topic=account-signup#signup), é possível usar uma chave de API para efetuar login usando a variável de ambiente `IBMCLOUD_API_KEY`. Para obter mais informações sobre como usar uma chave API para efetuar login, veja [Efetuando login com um ID federado](/docs/iam?topic=iam-federated_id#federated_id).
{:shortdesc}

## Criando uma chave API
{: #create_user_key}

Como um usuário do {{site.data.keyword.Bluemix_notm}}, você pode desejar usar uma chave API quando ativar um programa ou script sem distribuir sua senha para o script. É possível que um benefício de uso de uma chave API seja que um usuário ou uma organização possa criar várias chaves API para diferentes programas e que as chaves API poderão ser excluídas independentemente se comprometidas sem interferir com outras chaves API ou até mesmo com o usuário. É possível criar até 20 chaves API.

Para criar uma chave API para sua identidade do usuário na UI, conclua as etapas a seguir:

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**. Em seguida, clique em seu nome na lista e selecione a opção **Detalhes do usuário**.
2. Clique em **Criar uma chave de API do {{site.data.keyword.Bluemix_notm}}**.
3. Insira um nome e uma descrição para sua chave API.
4. Clique em **Criar**.
5. Em seguida, clique em **Mostrar** para exibir a chave de API para copiá-la e salvá-la para mais tarde ou clique em **Fazer download**.

Por motivos de segurança, a chave API está disponível apenas para ser copiada ou transferida por download no momento da criação. Se a chave API for perdida, uma nova chave API deverá ser criada.
{: tip}

Para criar uma chave API usando a CLI, use o comando a seguir:

1. Insira `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` no prompt de comandos e especifique um nome, uma descrição e um arquivo para salvar sua chave. Consulte o exemplo a seguir:

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
``` 


## Atualizando uma chave API
{: #update_user_key}

Se desejar mudar o nome ou a descrição de uma chave API, conclua as etapas a seguir na UI ou na CLI.

Para editar uma chave API, conclua as etapas a seguir:

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**. Em seguida, clique em seu nome na lista e selecione a opção **Detalhes do usuário**.
2. Identifique a linha da chave de API que você deseja atualizar e selecione **Editar** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg).
3. Atualize as informações de sua chave API.
4. Clique em **Aplicar**.

Para editar uma chave API usando a CLI, insira o comando a seguir:

1. Insira `ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` no prompt de comandos, especificando o nome antigo, o novo nome e a nova descrição para a chave. Por exemplo:

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## Bloqueando uma chave API
{: #lock_user_key}

Para chaves API da plataforma que representam sua identidade do usuário, é possível evitar que a chave API seja excluída bloqueando-a. Uma chave API bloqueada é indicada pelo ícone ![Ícone Bloqueado](images/locked.svg "Bloqueado"). É possível bloquear e desbloquear sua chave API usando a UI ou CLI.

### Bloqueando e desbloqueando uma chave API da UI
{: #lockui}

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**. Em seguida, clique em seu nome na lista e selecione a opção **Detalhes do usuário**.
2. Identifique a linha da chave de API que você deseja bloquear e selecione **Bloquear** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg).

É possível desbloquear sua chave de API a qualquer momento para atualizar ou remover a chave de API de sua conta. Selecione a chave de API na tabela que você deseja desbloquear e selecione **Desbloquear** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg).
{: tip}

### Bloqueando e desbloqueando uma chave API usando a CLI
{: #lockcli}

Para bloquear uma chave de API, use o comando a seguir:

```
Ibmcloud iam api-key-bloqueio (NAME | UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>NAME (necessário)</dt>
<dd>Nome da chave API a ser bloqueada, exclusiva com UUID.</dd>
<dt>UUID (necessário)</dt>
<dd>UUID da chave API a ser bloqueada, exclusiva com NAME.</dd>
<dt>-f, --force</dt>
<dd>Força o bloqueio sem confirmação.</dd>
</dl>

<strong>Exemplo</strong>:

Bloquear chave API `test-api-key`

```
Ibmcloud iam api-key-bloqueio de teste api-key
```

Para desbloquear uma chave de API, execute o comando a seguir:

```
Ibmcloud iam api-key-desbloquear (NAME | UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>NAME (necessário)</dt>
<dd>Nome da chave API a ser desbloqueada, exclusiva com UUID.</dd>
<dt>UUID (necessário)</dt>
<dd>UUID da chave API a ser desbloqueada, exclusiva com NAME.</dd>
<dt>-f, --force</dt>
<dd>Forças desbloquear sem confirmação.</dd>
</dl>

<strong>Exemplo</strong>:

Desbloquear chave API `test-api-key`

```
Ibmcloud iam api-key-unlock-api-chave de teste
```


## Excluindo uma chave API
{: #delete_user_key}

Se você está usando uma estratégia de rotação de chave, talvez queira excluir uma chave mais antiga e substituí-la por uma nova.

Para excluir uma chave API, conclua as etapas a seguir: 

1. Acesse **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**. Em seguida, clique em seu nome na lista e selecione a opção **Detalhes do usuário**.
2. Identifique a linha da chave de API que você deseja excluir e selecione **Excluir** no menu **Ações** ![Ícone Lista de ações](../icons/action-menu-icon.svg).
3. Em seguida, confirme a exclusão clicando em **Excluir**.

Para excluir uma chave API usando a CLI:
1. Insira `ibmcloud iam api-key-delete NAME` no prompt de comandos, especificando o nome da chave a ser excluída.
