---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Allowing specific IP addresses for a user
{: #ips}

By default, all IP addresses can be used to log in to the {{site.data.keyword.cloud}} console and access classic infrastructure APIs. You can specify which IP addresses have access, and only the specified addresses are allowed can be used and all others are restricted.
{:shortdesc}

You cannot access classic infrastructure pages on [https://cloud.ibm.com](https://cloud.ibm.com){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon") if you have restricted IP addresses. You must go to [https://control.softlayer.com](https://control.softlayer.com){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon").
{: important}

If you have the following assigned access, you can update the restricted IP addresses for another user:

  * An IAM policy with the Editor or higher role on the User management service.
  * You are an ancestor in the classic infrastructure hierarchy for the user and you have the Manage users classic infrastructure permission assigned
  
You can manage this setting for yourself if you have the User-managed login setting enabled on your User details page.
{: tip}

To restrict a user to using only specific IP addresses, complete the following steps: 

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**. 
2. Select a user from the list.
3. From the User details page, go to the **IP address restrictions** section. 
4. For **Cloud platform**, enter the IP addresses. The IP addresses listed are the only ones from which this user can log in to {{site.data.keyword.Bluemix}}.
5. For **Classic infrastructure**, enter the IP addresses. The IP addresses listed are the only ones from which the user can call a classic infrastructure API. 
  
  To enter a classic infrastructure IP address, the user must already have a classic infrastructure API key created.
  {: note}
 


