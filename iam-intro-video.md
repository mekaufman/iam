---

copyright:
  years: 2019
lastupdated:  "2019-10-10"

keywords: IAM, what is IAM, Identity and Access Management video, introduction to IAM

subcollection: iam

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:download: .download}
{:script: data-hd-video='script'}

# Video - {{site.data.keyword.cloud_notm}} IAM introduction video
{: #show_me_video}

With {{site.data.keyword.cloud}} Identity and Access Management (IAM), you can add and remove users to your account, assign users access, and more. Create access groups to quickly assign groups of users the same access, or assign individual access to all types of resources, including IAM, Cloud Foundry, and classic infrastructure.
{: shortdesc}

<div class="embed-responsive embed-responsive-16by9" data-hd-video="video">
  <iframe class="embed-responsive-item" id="youtubeplayer" title="Quick look: IBM Cloud Identity and Access Management" type="text/html" width="640" height="390" src="https://www.youtube.com/embed/Q1JI1Zk849k" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen> </iframe>
</div>

## Video transcript
{: #transcript-lite-account}
{: script}
{: notoc}

Welcome to an introduction on Identity and Access Management in {{site.data.keyword.cloud_notm}}, the one-stop shop for managing your users and their access to account resources.

Identity and Access Management is also commonly known as "IAM". {{site.data.keyword.cloud_notm}} IAM is a service integrated into the {{site.data.keyword.cloud_notm}} platform and free for you to use.

Get started by going to Manage > Access (IAM) in the {{site.data.keyword.cloud_notm}} console.

This is where you can invite users [highlight Invite users button on Users page] or manage users already added to your account [clicks a user's name on the Users page to show the Manage user page].

You can also create and manage your API keys [clicks IBM Cloud API keys from the navigation menu], which can be used to automate your login with the command-line interface or authenticate with {{site.data.keyword.cloud_notm}} APIs.

When you're ready to start managing access for users in your account, you can start by creating an access group, which can save you time and effort when assigning access [clicks Access groups from the navigation menu, clicks Create button, adds a name and description for a new access group, and clicks Create button].

Access groups are helpful when you have a team or group of users that you want to assign the same access, whether it's the ability to complete account management tasks or working with different types of resources. 

You can add users and service IDs to an access group [clicks Add users button after access group is created, selects users, clicks Add button] assign one or even a couple access policies, and with just a few clicks, you can quickly give the access that is needed to your users for building and developing on {{site.data.keyword.cloud_notm}} [clicks Access policies tab, clicks Assign access button, and scrolls the services list for assigning an access policy].

If you have one user that you want to assign specific access to or you want to provide access to classic infrastructure resources, you can start by selecting that user's name from your Users list [clicks Users from the navigation menu, selects a user's name, and selects Access policies tab for that user].


You can assign the user a policy to work with an IAM resource [highlights Assign access to resources tile], complete account management tasks [highlights Assign access to account management services tile], or access to all resources in a resource group [highlights Assign access within a resource group tile]. Next, if you have classic infrastructure [highlights Assign access to classic infrastructure tile] or Cloud Foundry resources [highlights Assign access by using Cloud Foundry tile], you can also assign this type of resource access from the same place.

This video covered just a few of the main capabilities available to you by using IAM [Graphic showing IAM in the center with IAM feature names such as API keys, access groups, managing users, and managing access connected by lines]. If you're interested in learning more about setting up multifactor authentication, access groups, service IDs, or learning best practices for managing access in your account, check out the {{site.data.keyword.cloud_notm}} documentation for Identity and Access Management [graphic expands to include other items users can learn about from the documentation including IAM tokens, event tracking, federated IDs, dynamic rules, service to service access, multifactor authentication, and service IDs].
