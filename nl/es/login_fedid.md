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

# Inicio de sesión con un ID federado
{: #federated_id}

Como usuario federado que utiliza un ID de inicio de sesión único corporativo o de empresa, puede iniciar una sesión en {{site.data.keyword.Bluemix}} desde la interfaz de línea de mandatos (CLI) mediante un código de acceso de un solo uso o una clave de API.
{: shortdesc}

## Utilización de un código de acceso de un solo uso
{: #onetime_passcode}

Cuando utiliza la opción de código de acceso de un solo uso para iniciar sesión con un ID federado, debe especificar el parámetro de inicio de sesión único (SSO) para obtener un código de acceso de un solo uso, que especificará luego en el inicio de sesión.

Dado que un código de acceso de un solo uso recupera código de la consola de {{site.data.keyword.Bluemix_notm}}, hace que falle el uso de un ID federado en su script de automatización. Evite problemas utilizando la opción de la clave de API con un script automatizado.
{: tip}

### Desde la CLI de {{site.data.keyword.Bluemix_notm}}
{: #login_cli}
1. Especifique la opción `--sso` con el mandato `ibmcloud login`.
2. Siga el URL en la solicitud para obtener un código de acceso de un solo uso.
3. Copie y pegue el valor del código de acceso en la CLI como su entrada.

  ```
  ibmcloud login --sso
  Punto final de API: https://cloud.ibm.com

  Obtener un código de un solo uso de https://identity-2.us-south.iam.cloud.ibm.com/identity/passcode para continuar.
  ¿Abrir el URL en el navegador predeterminado? [S/n]>
  Código de un solo uso >
  Autenticando...
  Correcto

  ```

### Desde la CLI de Cloud Foundry
{: #login_cf_cli}

1. Especifique la opción `--sso` con el mandato `cf login`.
2. Siga el URL en la solicitud para obtener un código de acceso de un solo uso.
3. Copie y pegue el valor del código de acceso en la CLI como su entrada.

  ```
  cf login -a  https://api.us-south.cf.cloud.ibm.com --sso

  Punto final de API: https://api.us-south.cf.cloud.ibm.com

  Código de un solo uso (Obtener uno en https://login.us-south.cf.cloud.ibm.com/UAALoginServerWAR/passcode)>
  Autenticando...
  Correcto

  ```

## Utilización de la clave de API
{: #api_key}

La clave de API necesaria es la clave de API de {{site.data.keyword.Bluemix_notm}} utilizada para autenticarse con la plataforma de {{site.data.keyword.Bluemix_notm}}, no la clave de API de la infraestructura clásica ni la clave de API del servicio de {{site.data.keyword.Bluemix_notm}}.

1. Cree una clave de API con el mandato [`ibmcloud iam api-key-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_create). Utilice la opción `-f` para generar un archivo de claves de API en lugar de mostrar la clave en la ventana de mandatos:

   ```
   ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]

   ```

2. Inicie la sesión con su clave de API.

  Puede utilizar la clave de API con la CLI de {{site.data.keyword.Bluemix_notm}} en cualquiera de las formas siguientes:

    * Llame a la clave de API directamente:

      ```
      ibmcloud login --apikey <api_key_string>

      ```

    * Llame a la clave de API con el archivo de claves:

      ```
      ibmcloud login --apikey @key_file_name

      ```

    * Establece una variable de entorno. Además, también puede establecer una variable de entorno en el sistema. Por ejemplo, IBMCLOUD_API_KEY=api_key_string, donde `api_key_string` es el valor personalizado de la clave de API. Después de establecer la variable de entorno, puede especificar `ibmcloud login` desde la CLI.

   Para Windows 10 PowerShell, utilice `'@key_file_name'` y especifique el nombre del archivo de claves entre comillas simples.
   {: tip}

  Para iniciar una sesión utilizando la CLI de Cloud Foundry, especifique `apikey` como el nombre de usuario y la serie de claves de API como la contraseña:

    ```
    cf login -a https://api.us-south.cf.cloud.ibm.com

    Punto final de API: https://api.us-south.cf.cloud.ibm.com

    Correo electrónico> apikey

    Contraseña>
    Autenticando...
    Correcto

    ```
