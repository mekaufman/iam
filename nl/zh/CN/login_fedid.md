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

# 使用联合标识登录
{: #federated_id}

作为使用公司或企业单点登录标识的联合用户，您可以使用一次性密码或使用 API 密钥通过命令行界面 (CLI) 登录到 {{site.data.keyword.Bluemix}}。
{: shortdesc}

## 使用一次性密码
{: #onetime_passcode}

如果使用一次性密码选项通过联合标识登录，请指定单点登录 (SSO) 参数以获取一次性密码，然后在登录时输入该密码。

由于一次性密码是通过 {{site.data.keyword.Bluemix_notm}} 控制台检索密码的，因此会导致在自动化脚本中使用联合标识失败。通过将 API 密钥选项与自动脚本配合使用可避免此问题。
{: tip}

### 在 {{site.data.keyword.Bluemix_notm}} CLI 中
{: #login_cli}
1. 为 `ibmcloud login` 命令指定 `--sso` 选项。
2. 访问提示中的 URL 以获取一次性密码。
3. 复制密码值并将其作为输入粘贴到 CLI 中。

  ```
  ibmcloud login --sso
  API endpoint: https://cloud.ibm.com
      
  Get One Time Code from https://identity-2.us-south.iam.cloud.ibm.com/identity/passcode to proceed.
  Open the URL in the default browser? [Y/n]>
  One Time Code >
  Authenticating...
  OK
      
  ```

### 在 Cloud Foundry CLI 中
{: #login_cf_cli}

1. 为 `cf login` 命令指定 `--sso` 选项。
2. 访问提示中的 URL 以获取一次性密码。
3. 复制密码值并将其作为输入粘贴到 CLI 中。

  ```
  cf login -a  https://api.us-south.cf.cloud.ibm.com --sso
  
  API endpoint: https://api.us-south.cf.cloud.ibm.com
      
  One Time Code (Get one at https://login.us-south.cf.cloud.ibm.com/UAALoginServerWAR/passcode)>
  Authenticating...
  OK
      
  ```

## 使用 API 密钥
{: #api_key}

所需的 API 密钥是用于向 {{site.data.keyword.Bluemix_notm}} 平台认证的 {{site.data.keyword.Bluemix_notm}} API 密钥，而不是经典基础架构 API 密钥或 {{site.data.keyword.Bluemix_notm}} 服务 API 密钥。

1. 使用 [`ibmcloud iam api-key-create` 命令](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_create)创建 API 密钥。使用 `-f` 选项来生成 API 密钥文件，而不在命令窗口中显示密钥：

   ```
   ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]

   ```

2. 使用 API 密钥登录。

  可以使用以下任何一种方法将 API 密钥用于 {{site.data.keyword.Bluemix_notm}} CLI：

    * 直接调用 API 密钥：

      ```
ibmcloud login --apikey <api_key_string>

      ```

    * 使用密钥文件调用 API 密钥：

      ```
ibmcloud login --apikey @key_file_name

      ```

    * 设置环境变量。此外，还可以在系统上设置环境变量。例如，IBMCLOUD_API_KEY=api_key_string，其中 `api_key_string` 是 API 密钥的定制值。设置环境变量后，可以直接通过 CLI 指定 `ibmcloud login`。

   对于 Windows 10 PowerShell，需要使用 `'@key_file_name'`，即用单引号将密钥文件名称括起。
   {: tip}

  要使用 Cloud Foundry CLI 登录，请指定 `apikey` 作为用户名，并指定 API 密钥字符串作为密码：

    ```
    cf login -a https://api.us-south.cf.cloud.ibm.com

    API endpoint: https://api.us-south.cf.cloud.ibm.com

    Email> apikey

    Password>
    Authenticating...
    OK

    ```
