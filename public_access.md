---

copyright:

  years: 2019

lastupdated: "2019-03-25"

keywords: public access, anonymous access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Enabling public access to resources
{: #public}

Public access to resources enables all users and service IDs to be able to access a specific resource in your account. This means that a user or service ID does not need to authenticate with {{site.data.keyword.Bluemix}} to access information in an {{site.data.keyword.cos_full_notm}} bucket, for example. Only certain services support the ability to provide public access to specific resource types for the service. Therefore, you are limited to creating policies only for services that support this feature.
{:shortdesc}

To enable public access for resources, you must use the **Public Access** access group that is provided for you in your account. This access group includes all users and service IDs by default. You can't delete the group or change the membership of the group, but you can add, edit, and delete access policies for the group.

## Creating a policy for the public access group
{: #public_policy}

Complete the following steps to assign a policy to your public access group. The following task uses the Cloud Object Storage service as an example for assigning public access to a bucket called `mybucket123`.

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Access groups**.
2. Select the **Public Access** group.
3. Click **Assign access**.
4. Select **Cloud Object Storage** from the services list.
5. Enter `bucket` for the resource type.
6. Enter `mybucket123` for the resource ID.
7. Click **Assign**.
8. Click **Yes** to confirm that you want to assign the public access policy to the resource, and then click **Assign**.
