---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: application programming interface key, API key, API, classic infrastructure API key, IBM Cloud API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 了解 API 密钥
{: #manapikey}

应用程序编程接口密钥（API 密钥）是传入到 API 的唯一代码，用于确定调用应用程序或用户。API 密钥用于跟踪和控制 API 的使用情况，例如阻止恶意使用或滥用 API。API 密钥经常充当进行认证的唯一标识和私钥令牌，而且通常有一组特定于其关联身份的访问权。
{:shortdesc}

要管理 API 密钥，请转至**管理** > **访问权 (IAM)**，然后选择**用户**。然后，选择用户以浏览至“用户详细信息”页面上包含的“API 密钥”部分。

## {{site.data.keyword.cloud_notm}}API 密钥
{: #ibm-cloud-api-keys}

{{site.data.keyword.cloud}} API 密钥是在 {{site.data.keyword.cloud_notm}} 控制台的“用户详细信息”页面中为用户创建的，并与该用户的身份相关联。只有与 API 密钥关联的用户才能创建和删除该 API 密钥。您可以在命令行界面 (CLI) 中使用 {{site.data.keyword.cloud_notm}} API 密钥，或者作为自动化的一部分使用 API 密钥，以便以您的用户身份登录。您还可以使用 {{site.data.keyword.cloud_notm}} API 密钥来访问经典基础架构 API。有关使用与用户身份关联的 API 密钥的更多信息，请参阅[管理用户 API 密钥](/docs/iam?topic=iam-userapikey#userapikey)。

您还可以使用与您创建的服务标识关联的 API 密钥。服务标识用于将 {{site.data.keyword.Bluemix_notm}} 内部或外部的应用程序连接到 {{site.data.keyword.Bluemix_notm}} 服务。有关创建与服务标识关联的 API 密钥的更多信息，请参阅[管理服务标识 API 密钥](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)。

## 其他类型的 API 密钥
{: #othertypes}

除了 {{site.data.keyword.cloud_notm}} API 密钥之外，还有两个其他类型的 API 密钥可使用：

* 经典基础架构 API 密钥
* 特定于服务的 API 密钥

经典基础架构 API 密钥用于调用经典基础架构服务的 API。一次只能创建一个经典基础架构 API 密钥。您可以在“用户详细信息”页面中为用户创建经典基础架构 API 密钥。

{{site.data.keyword.cloud_notm}} API 密钥还可用于访问经典基础架构 API。
{: tip}

{{site.data.keyword.Bluemix_notm}} 中的某些服务可能还会提供 API 密钥，供您在使用服务时运用。例如，如果要在资源列表中查看 Watson 服务的服务详细信息，那么可以在“服务凭证”页面上创建仅特定于该服务的凭证（包括 API 密钥和私钥）。
