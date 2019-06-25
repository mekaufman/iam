---

copyright:

  years: 2015，2019

lastupdated: "2019-03-27"

keywords: federated ID, enterprise SSO, single sign-on ID, API key login, one-time passcode login

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Efetuando login com um ID federado
{: #federated_id}

Como um usuário federado que usa um ID de conexão única corporativo, é possível efetuar login no {{site.data.keyword.Bluemix}} por meio da interface da linha de comandos (CLI) usando uma senha descartável ou uma chave de API.
{: shortdesc}

## Usando uma senha única
{: #onetime_passcode}

Ao usar a opção de senha única para efetuar login com um ID federado, você especifica o parâmetro single-sign on (SSO) para obter uma senha única, que será então inserida no login.

Como uma senha única recupera código do console do {{site.data.keyword.Bluemix_notm}}, ela faz com que o uso de um ID federado em seu script de automação falhe. Evite problemas usando a opção de chave API com um script automatizado.
{: tip}

### No {{site.data.keyword.Bluemix_notm}} CLI
{: #login_cli}
1. Especifique a opção `--sso` com o comando `ibmcloud login`.
2. Siga a URL no prompt para obter a senha única.
3. Copie e cole o valor da senha na CLI como sua entrada.

  ```
  ibmcloud login --sso
  API endpoint: https://cloud.ibm.com

  Get One Time Code from https://identity-2.us-south.iam.cloud.ibm.com/identity/passcode to proceed.
  Abrir a URL no navegador padrão? [Y/n]>
  One Time Code >
  Authenticating...
  OK

  ```

### Por meio da CLI do Cloud Foundry
{: #login_cf_cli}

1. Especifique a opção `--sso` com o comando `cf login`.
2. Siga a URL no prompt para obter a senha única.
3. Copie e cole o valor da senha na CLI como sua entrada.

  ```
  cf login -a  https://api.us-south.cf.cloud.ibm.com --sso

  API endpoint: https://api.us-south.cf.cloud.ibm.com

  One Time Code (Get one at https://login.us-south.cf.cloud.ibm.com/UAALoginServerWAR/passcode)>
  Authenticating...
  OK

  ```

## Usando uma chave API
{: #api_key}

A chave de API necessária é a chave de API do {{site.data.keyword.Bluemix_notm}} usada para autenticar com a plataforma {{site.data.keyword.Bluemix_notm}}, não a chave de API da infraestrutura clássica ou a chave de API de serviço do {{site.data.keyword.Bluemix_notm}}.

1. Crie uma chave de API com o comando [`ibmcloud iam api-key-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_create). Use a opção `-f` para gerar um arquivo de chave API, em vez de mostrar a chave na janela de comando:

   ```
   ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]

   ```

2. Efetue login com a chave API.

  É possível usar a chave API com a CLI do {{site.data.keyword.Bluemix_notm}} em qualquer uma das maneiras a seguir:

    * Chamar a chave API diretamente:

      ```
      ibmcloud login --apikey <api_key_string>

      ```

    * Chamar a chave API com o arquivo-chave:

      ```
      ibmcloud login --apikey @key_file_name

      ```

    * Configurar uma variável de ambiente. Além disso, também é possível configurar uma variável de ambiente em seu sistema. Por exemplo, IBMCLOUD_API_KEY=api_key_string, em que `api_key_string` é o valor customizado da chave de API. Após a configuração da variável de ambiente, basta especificar `ibmcloud login` por meio da CLI.

   Para o Windows 10 PowerShell, você deseja usar `'@key_file_name'` com aspas simples ao redor do nome do arquivo-chave.
   {: tip}

  Para efetuar login usando a CLI do Cloud Foundry, especifique `apikey` como o nome do usuário e a keystring API como a senha:

    ```
    cf login -a https://api.us-south.cf.cloud.ibm.com

    API endpoint: https://api.us-south.cf.cloud.ibm.com

    Email> apikey

    Password>
Authenticating...
OK

    ```
