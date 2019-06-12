---

copyright:

  years: 2017, 2019

lastupdated: "2019-06-03"

keywords: what is IAM, IBM Cloud IAM, IAM features, IAM API

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# {{site.data.keyword.Bluemix_notm}} Identity and Access Management
{: #iamoverview}

## 什么是 Cloud IAM？
{: #what_is_IAM}

通过 {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM)，您可以在整个 {{site.data.keyword.Bluemix_notm}} 上一致、安全地对两个平台服务的用户进行认证并控制对资源的访问权。支持一组 {{site.data.keyword.Bluemix_notm}} 服务使用 Cloud IAM 进行访问控制，这些服务在您的帐户中组织成[资源组](/docs/resources?topic=resources-rgs#rgs)，让用户能够快速、轻松地一次访问多个资源。Cloud IAM 访问策略用于为用户和服务标识分配对帐户中资源的访问权。可以将用户和服务标识分组到一个[访问组](/docs/iam?topic=iam-getstarted#getstarted)中，以轻松向该组内所有实体授予相同级别的访问权。

策略向主体（即用户、[服务标识](/docs/iam?topic=iam-serviceids#serviceids)或访问组）分配一个或多个角色，其中具有定义目标的访问权作用域的属性组合。策略可以提供对下至实例级别的单个服务、汇集在一个资源组的一组资源或者帐户管理服务的访问权。根据分配的 [IAM 角色](/docs/iam?topic=iam-userroles#iamusermanrol)，主体可以具有不同级别的访问权，以通过使用 UI 或执行 API 调用完成帐户管理任务，使用服务实例或者访问服务。


![用于控制帐户中访问权的 IAM](images/iam-diagram.svg "如何使用 IAM 在帐户中进行访问权管理")

对于不支持创建 Cloud IAM 策略以管理访问权的服务，您可以使用 [Cloud Foundry 访问权](/docs/iam?topic=iam-cfaccess#cfaccess)或[经典基础架构许可权](/docs/iam?topic=iam-infrapermission#infrapermission)。



## Cloud IAM 提供哪些功能？
{: #features}

<dl>
<dt>用户管理</dt>
<dd>通过统一用户管理，您可以在一个帐户中添加和删除平台和经典基础架构服务的用户。您可以将一组用户组织成一个访问组，以便快速、轻松地一次为多个用户分配访问权。</dd>
<dt>细颗粒度访问控制</dt>
<dd>用户、服务标识和访问组的访问权由策略定义。在策略中，可以将用户、服务标识或访问组的访问权作用域分配给资源组中的一组资源、单个资源或者帐户管理服务。设置作用域后，可以通过选择访问角色来定义策略主题允许的操作。角色用于提供定制为策略主体授予的访问权级别的方法，以对策略目标执行操作，无论是帐户中的平台管理任务，还是访问服务的 UI 或执行 API 调用。</dd>
<dt>用于用户认证的 API 密钥</dt>
<dd>可以为用户创建多个 API 密钥来支持密钥轮换方案，并且同一密钥可用于访问多个服务。{{site.data.keyword.cloud_notm}} API 密钥支持使用双因子认证或联合标识的用户通过命令行自动向控制台执行认证。用户还可以具有单个经典基础架构 API 密钥，可用于访问经典基础架构 API；但是，这不是必需的，因为您可以使用 {{site.data.keyword.cloud_notm}} API 密钥来访问相同的 API。</dd>
<dt>服务标识</dt>
<dd>服务标识识别服务或应用程序的方式与用户标识识别用户的方式相似。这些是应用程序可以用于向 {{site.data.keyword.Bluemix_notm}} 服务进行认证的标识。可以为每个服务标识分配策略，以控制使用服务标识的应用程序允许的访问级别，并且可以创建 API 密钥来启用认证。</dd>
</dl>


## 如何使用 Cloud IAM？
{: #howto}

您可以通过“访问权 (IAM)”UI、CLI 或 API 来访问和使用 Cloud IAM。

* 要使用 UI 来访问 Cloud IAM，请转至**管理** &gt; **访问权 (IAM)**。
* 转至[管理 IAM 访问权、API 密钥、服务标识和访问组](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam)以查看可用的 CLI 命令。
* 转至以下 API 文档以查看可用的 API：
    * [IAM Identity Services API](https://{DomainName}/apidocs/iam-identity-token-api){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")
    * [IAM Access Groups API](https://{DomainName}/apidocs/iam-access-groups){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")
    * [IAM Policy Management API](https://{DomainName}/apidocs/iam-policy-management){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")
