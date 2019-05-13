---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: IBM Cloud service APIs, IAM token, API key, authenticate with service API

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 调用 {{site.data.keyword.cloud_notm}} 服务 API
{: #iamapikeysforservices}

要通过 API 调用 {{site.data.keyword.Bluemix}} 服务，请将凭证传递到服务的 API 来认证您的用户身份和访问权，以便在该服务的上下文中执行操作。
{:shortdesc}

可以通过以下其中一种方式来识别调用者：

* {{site.data.keyword.Bluemix_notm}} API 密钥或服务标识 API 密钥
* {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 令牌

[{{site.data.keyword.Bluemix_notm}} API 密钥](/docs/iam?topic=iam-userapikey#userapikey)、[服务标识 API 密钥](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)和 IAM 令牌可唯一标识调用者的身份。调用者身份是在 {{site.data.keyword.Bluemix_notm}} 帐户中创建的 {{site.data.keyword.Bluemix_notm}} 用户或服务标识。

API 密钥是由一长串随机字符或数字组成的凭证。一个 {{site.data.keyword.Bluemix_notm}} 身份可以拥有多个 API 密钥。每个 API 密钥都可以单独进行管理；即，如果此 API 密钥仅由您的服务使用，那么您可以删除此 API 密钥而不中断其他某个组件。

您可以使用 API 密钥来[登录到 {{site.data.keyword.Bluemix_notm}} 命令行界面 (CLI)](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_login#ibmcloud_login) 或[生成 IAM 令牌](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey)。虽然建议不要将 API 密钥用于生产用途，但您还是可以将 API 密钥发送到 {{site.data.keyword.Bluemix_notm}} 服务。

## 传递 {{site.data.keyword.Bluemix_notm}} API 密钥以向服务 API 进行认证
{: #apikey_auth}

API 客户机可以将 {{site.data.keyword.Bluemix_notm}} API 密钥直接传递到目标服务的 API。为此，请使用基本授权 HTTP 头将 `apikey` 关键字作为用户名，并将 {{site.data.keyword.Bluemix_notm}} API 密钥作为密码发送到目标服务。

目标服务 API 必须使用 {{site.data.keyword.Bluemix_notm}} IAM 服务来检查 {{site.data.keyword.Bluemix_notm}} API 密钥。下图显示了三种 API 交互。{{site.data.keyword.Bluemix_notm}} API 密钥会传递到每个目标服务的 API，因此每个目标服务必须通过调用 {{site.data.keyword.Bluemix_notm}} IAM 来查找 {{site.data.keyword.Bluemix_notm}} API 密钥详细信息。

![使用 API 密钥通过服务 API 进行认证](images/APIkeyauth.svg "将 API 密钥传递到目标服务，随后目标服务会将 API 密钥传递给 IAM 来验证凭证")

使用 {{site.data.keyword.Bluemix_notm}} API 密钥很方便，并且可以轻松发现新的 API 并快速试用原型。但此方法需要您以可读格式将 {{site.data.keyword.Bluemix_notm}} API 密钥发送到目标服务的 API，这会导致不必要地泄露 API 密钥。此外，由于目标服务的 API 必须始终内省 API 密钥，因此这种方法的性能较低，所以建议不要用于生产工作负载。

要使用 API 密钥向服务的 API 进行认证，请完成以下步骤：

  1. 首先，[创建 {{site.data.keyword.Bluemix_notm}} API 密钥](/docs/iam?topic=iam-userapikey#create_user_key)（如果尚未创建）。
  2. 将 {{site.data.keyword.Bluemix_notm}} API 密钥作为 HTTP 头“Authorization”发送，如 [RFC 7617](https://tools.ietf.org/html/rfc7617){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 中所定义。将 `apikey` 用作用户名，将 API 密钥值用作密码。

例如，以下步骤假定 API 密钥为 0a1A2b3B4c5C6d7D8e9E：

  1.	将用户名 `apikey` 和 API 密钥连在一起并以冒号分隔：`apikey:0a1A2b3B4c5C6d7D8e9E`
  2.	对字符串进行 Base64 编码：`base64("apikey:0a1A2b3B4c5C6d7D8e9E") => YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`
  3.	使用模式 Basic 来设置 HTTP 头 Authorization，例如 `Authorization: Basic YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`。使用 curl 命令时，可以使用 -u 参数来传递此项：

    ```
    curl -u "apikey:<IBM Cloud API key value>"
    ```

  如果使用其他工具，那么可能必须以不同方式指定这些凭证。
  {: tip}

## 传递 {{site.data.keyword.Bluemix_notm}} IAM 令牌以向服务 API 进行认证
{: #token_auth}

要检索 IAM 访问令牌，API 客户机必须首先调用 {{site.data.keyword.Bluemix_notm}} IAM API 以认证和检索该令牌。{{site.data.keyword.Bluemix_notm}} 服务 API 客户机的首选方法是使用 IAM API 密钥来获取 IAM 访问令牌。IAM 访问令牌可用于对接受 IAM 访问令牌作为认证方法的 {{site.data.keyword.Bluemix_notm}} 服务进行多次调用。由于 IAM 访问令牌通过非对称密钥进行数字签名，因此 {{site.data.keyword.Bluemix_notm}} 服务无需调用任何外部服务就能验证 IAM 访问令牌。这将显著提高调用 API 的性能。

![使用访问令牌通过服务 API 进行认证](images/tokenauth.svg "使用 API 密钥从 IAM 检索令牌并将访问令牌传递到目标服务以验证凭证")

要使用访问令牌向服务的 API 进行认证，请完成以下步骤：

  1. 首先，[创建 {{site.data.keyword.Bluemix_notm}} API 密钥](/docs/iam?topic=iam-userapikey#create_user_key)（如果尚未创建）。
  2. API 客户机的下一个步骤是检索 IAM 访问令牌，如[通过 API 密钥获取 IAM 令牌](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey)中所述。
  3. 从响应中，抽取 `access_token` 属性以获取 IAM 访问令牌。`expires_in` 指示 IAM 访问令牌距离 `access_token` 到期之前的秒数。使用此相对值或使用基于 [UNIX 时间](https://en.wikipedia.org/wiki/Unix_time){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 的绝对时间戳记 `expiration`。
  4. 发送 IAM 访问令牌，如 [RFC 6750 的第 2.1.节 Authorization Request Header Field](https://tools.ietf.org/html/rfc6750#page-5){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 中所述：

查看以下示例：

  1.	使用 HTTP 头 Authorization
  2.	使用字面值 `Bearer: Bearer eyJhbGciOiJSUzI1Ng...` 作为 IAM 访问令牌的前缀
  3.	将带前缀的 IAM 访问令牌添加到该 HTTP 头：`Authorization: Bearer eyJhbGciOiJSUzI1Ng...`。使用 curl 命令时，可以使用 -H 参数来传递此项：

    ```
    curl -H "Authorization: Bearer eyJhbGciOiJSUzI1Ng..."
    ```

  将同一 IAM 访问令牌用于后续的 IBM Cloud 服务 API 调用，以实现最佳性能和可扩展性。
  {: tip}
