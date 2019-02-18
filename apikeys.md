---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Understanding API keys
{: #manapikey}

An application programming interface key (API key) is a unique code that is passed in to an API to identify the calling application or user. API keys are used to track and control how the API is being used, for example to prevent malicious use or abuse of the API. The API key often acts as both a unique identifier and a secret token for authentication, and generally has a set of access that is specific to the identity associated with it.
{:shortdesc}

To view your API keys, go to **Manage** > **Access (IAM)**, and select **Users**. Then, select a user to navigate to the API keys section that's included on the User details page. 

## {{site.data.keyword.cloud_notm}} API keys
{: #ibm-cloud-api-keys}

{{site.data.keyword.cloud}} API keys are created from the User details page in the {{site.data.keyword.cloud_notm}} console for a user and are associated with the user's identity. Only the user for which the API key is associated with can create and delete it. You can use the {{site.data.keyword.cloud_notm}} API keys in the command-line interface (CLI) or as part of automation to log in as your user identity. You can also use {{site.data.keyword.cloud_notm}} API keys to access classic infrastructure APIs. For more information about using an API key associated with your user identity, see [Managing user API keys](/docs/iam?topic=iam-userapikey#userapikey).

You can also use API keys that are associated with service IDs that you create. Service IDs are used to connect an application inside or outside of {{site.data.keyword.Bluemix_notm}} to an {{site.data.keyword.Bluemix_notm}} service. For more information about creating API keys associated with a service ID, see [Managing service ID API keys](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys).

## Other types of API keys
{: #othertypes}

In addition to your {{site.data.keyword.cloud_notm}} API keys, a couple of other types of API keys are available that you might use:

* Classic infrastructure API keys
* Service-specific API keys

Classic infrastructure API keys are used to call the APIs for classic infrastructure services. You can create only one classic infrastructure API key at a time. You can create a classic infrastructure API key for a user from the User details page.

{{site.data.keyword.cloud_notm}} API keys can also be used to access classic infrastructure APIs.
{: tip}

Some services in {{site.data.keyword.Bluemix_notm}} might also provide an API key for you to use when you work with the service. For example, if you are viewing the offering details of a Watson service from your resource list, you can create a credential, which includes an API key and secret that is specific to just that service on the Service credentials page.


